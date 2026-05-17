## 一、Claude Computer Use 最佳实践官方指南【⭐⭐⭐】

**来源：** Claude Blog
**链接：** https://claude.com/blog/best-practices-for-computer-and-browser-use-with-claude
**关键词：** Claude Computer Use, click accuracy, screenshot scaling, thinking effort, Opus 4.7, Sonnet 4.6

### 摘要

Anthropic 发布了 Claude Computer Use（电脑操作）的官方最佳实践指南，覆盖了从截图分辨率到思维调节的完整最佳实践。这不是一篇宣告新功能的文章，而是基于大量内部实验的实操指南。

核心要点：

**1. 截图缩放——影响点击精度的头号因素**

很多人点不准的根本原因很简单：截图尺寸不对。Claude API 对输入图片有隐式限制：

- **4.6 系列模型**：最大长边 1568px，最大总像素 115 万（≈1.15MP）
- **Opus 4.7**：上限更高——长边 2576px，总像素 375 万（≈3.75MP）

如果截图超过限制会被自动缩放，但返回的坐标匹配的是你设定的 display_width/height，坐标空间和实际看到的图不匹配，点击就会偏。解决方法是：**发送前自己先缩放到 API 限制以内**。

推荐起点：**1280x720**（4.6 系列）；**1080p**（Opus 4.7）。他们还提供了一个 `compute_max_api_fit` 函数，可以算出每张图的最优缩放尺寸。

**2. 内容顺序也有讲究**

text instruction 要放在 image 前面，让模型在看图之前已经知道"要找什么"。这个顺序本身就能提升点击精度。

**3. 模型选择：Sonnet 4.6 点得准，Opus 4.7 全能**

内部测试发现：Sonnet 4.6 在机械点击上更精确（更好的空间精度、更少打偏），尤其是需要大幅缩放的场景下表现更稳健；Opus 4.6 推理强但点击精度不如 Sonnet。而 **Opus 4.7 基本拉平了这个差距**——点击精度和 Sonnet 4.6 差不多，同时有更高的分辨率预算（3.75MP vs 1.15MP），减少缩放损失。

**4. 思维调节（Thinking Effort）指南**

Opus 4.7 推荐用 **high** 作为默认——在效果接近 max 的同时只用大约一半的 token。复杂一次性任务用 max。简单/高吞吐场景改成 Sonnet 4.6。

4.6 系列模型的甜点是 **medium**——花一半的高 token 就能达到高相近的成功率（重试之后甚至完全一致）。**low 也有惊喜**：实际总输出 token 比完全不开启思考还少（因为减少错误和重试）。

**5. 小目标处理**

对付 checkbox、图标、toggle 等小元素：启用 `enable_zoom: True`（支持模型放大观察局部）；尽量用键盘快捷键替代点击；4K 高分辨率屏幕的问题尤其突出——一个 16px 的 checkbox 缩到 720p 只剩大约 5px。

**6. 几项没用的方案**

他们把常见优化方案测了一遍，发现以下方法没有稳定提升：把截图切成小块分开发送；在截图上叠加网格坐标辅助定位；不同的缩放算法（PIL LANCZOS 和其他方案结果一致）。

**一句话**：这是目前最权威的 Claude Computer Use 调优手册，如果你在用 Computer Use API，值得通读一遍。

---
## 二、Arm SME2 + Google AI Edge：端侧AI推理提速5倍【⭐⭐】

**来源：** Google AI
**链接：** https://developers.googleblog.com/accelerating-on-device-ai-a-look-at-arm-and-google-ai-edge-optimization/
**关键词：** Arm SME2, Google AI Edge, LiteRT, KleidiAI, 端侧推理, XNNPACK, AI Edge Quantizer, Model Explorer, Stability AI, 音频生成

### 摘要

Google 和 Arm 联合发布了一套端到端的端侧 AI 优化方案，核心是 **Arm SME2（可扩展矩阵扩展2）** 和 **Google AI Edge** 软件栈的深度集成。简单说，就是把 CPU 变成一个高性能 AI 加速器，不需要额外的 NPU/GPU 就能在手机和笔记本上跑生成式 AI 模型。

**核心技术栈：**

- **Arm SME2**：在 CPU 集群内集成了专用的矩阵计算单元，专门为生成式 AI 的矩阵运算设计，宣称推理速度最多提升 **5倍**
- **LiteRT**（原 TensorFlow Lite）：自动利用 SME2 指令集，通过 XNNPACK + KleidiAI 实现硬件加速。开发者不需要写汇编代码
- **AI Edge Quantizer**：自动化模型压缩工具，处理复杂的量化配置
- **Model Explorer**：可视化模型图，帮助开发者快速找到性能瓶颈和量化安全层

**实操案例——在手机/笔记本上跑 Stability Audio 开源模型：**

Google 用 Stability AI 的 `stable-audio-open-small`（约 1B 参数）开源音频模型演示了整个流程：

1. **Convert**：用 LiteRT-Torch 直接把 PyTorch 模型转成 .tflite 格式
2. **Optimize**：用 Model Explorer 可视化模型图，定位 DiT（扩散 Transformer）子模块是计算热点。用 AI Edge Quantizer 把 DiT 子模块从 FP32 量化为 INT8（只量影响小的层，关键层保持 FP16），结果 DiT 性能提升 **3倍**，内存占用减少 **4倍**
3. **Deploy**：在 Android 或 Mac 上运行，XNNPACK 自动调用 KleidiAI 微内核实现 SME2 加速

**实测数据：**
- Apple MacBook M4：音频生成从 10 秒降到 **4.3 秒**（2x+ 加速）
- Arm SME2 Android 设备（单线程）：从 14 秒降到 **6.6 秒**
- 内存：DiT 子模型体积缩小约 4x
- 音频质量：与原始 FP32 版本感知无差异

**对开发者的意义：** 这是一套完整的 PyTorch → 端侧部署工具链，而且完全免费开源。如果你们在做端侧 AI 功能（图像生成、语音合成等），LiteRT + KleidiAI 提供了一条开箱即用的加速路径，不用写一行汇编代码。
