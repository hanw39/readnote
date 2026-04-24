# AI

## 一、Claude Opus 4.7 发布【⭐⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/claude-opus-4-7
**关键词：** Claude Opus 4.7、大模型、编程、Agent、视觉

### 摘要

Anthropic 发布了 Claude Opus 4.7，这是其 Opus 系列的最新旗舰模型。相比 Opus 4.6 在多个维度有显著提升：

**编程能力大幅增强。** 在内部 93 项编程基准测试中，Opus 4.7 比 Opus 4.6 提升了 13%，包括 4 个此前两个版本都无法解决的任务。在 CursorBench 上从 58% 提升到 70%。早期测试用户报告，它能够接手"之前需要密切监督的最困难编码工作"，而且用起来比 Opus 4.6 更"省力"——"低投入使用 Opus 4.7 大约等同于中等投入使用 Opus 4.6"。Hex 的评价是"这是我们评估过的最强模型"。

**Agent 能力突出。** Opus 4.7 在 Anthropic 内部的研究 Agent 基准测试中，总分 0.715，与最强模型持平。在需要长程自主性的任务（如 Devin 平台）上表现出色，能够"连贯运行数小时、攻克难题而不是放弃"。Hebbia 的测试显示，双位数提升在准确率和规划能力上，在 Notion Agent 上工具调用错误减少了三分之一。

**视觉能力升级。** 支持更高分辨率的图像理解，在 Chemical structure reading 到复杂技术图表解读都有进步。Solve Intelligence 用它来构建生命科学专利工作流程的工具。

**有意思的安全设计。** Opus 4.7 是 Anthropic 第一个内置网络安防范护的模型——它会自动检测并拦截表明禁止或高风险网络攻击使用的请求。这是 Anthropic 在部署更强大的 Mythos 系列模型之前的一个实验性步骤，网络安全专业人员如果想用于合法目的（漏洞研究、渗透测试、红队），可以申请加入 Cyber Verification Program。

定价与 Opus 4.6 相同：$5/百万输入 token，$25/百万输出 token。已在 Claude API、Amazon Bedrock、Google Vertex AI、Microsoft Foundry 全平台上架。

---

## 二、GPT-Rosalind：OpenAI 发布生命科学专用推理模型【⭐⭐⭐】
**来源：** OpenAI Research
**链接：** https://openai.com/index/introducing-gpt-rosalind/
**关键词：** GPT-Rosalind、生命科学、药物发现、Domain-Specific AI

### 摘要

OpenAI 推出了 GPT-Rosalind，这是一个面向生命科学研究的专用推理模型系列，名字致敬了帮助揭示 DNA 结构的 Rosalind Franklin 女士。

**为什么重要。** 新药从靶点发现到 FDA 批准平均需要 10-15 年，早期发现阶段的效率提升会级联放大到整个流程。科学家需要横跨大量文献、专业数据库、实验数据和不断演化的假设来生成和评估新想法——这些工作流本身就很耗时、碎片化，难以规模化。GPT-Rosalind 旨在帮助研究者加速这些早期发现阶段。

**模型能力。** 这是 OpenAI 第一个专门针对生物学、化学、蛋白质工程和基因组学优化的模型系列。在 BixBench（生物信息学基准）上取得了已发布模型中的领先性能。在 LABBench2 的 11 项任务中，6 项超越了 GPT-5.4，特别是在 CloningQA（需要端到端设计 DNA 和酶试剂用于分子克隆）上有最显著提升。它在工具使用上更有效——可以连接超过 50 个科学工具和数据源。

**合作伙伴。** 与 Amgen、Moderna、Allen Institute、Thermo Fisher Scientific 等机构合作，以研究预览形式在 ChatGPT、Codex 和 API 中提供。OpenAI 命名暗示了其在 DNA/生物学领域的野心，这是继 AlphaFold 之后科学 AI 领域的又一次重大推进。

---

## 三、Meta 发布 Muse Spark：放弃开源策略后的首款产品【⭐⭐】
**来源：** The Batch (DeepLearning.ai)
**链接：** https://www.deeplearning.ai/the-batch/issue-349/
**关键词：** Meta、Muse Spark、多模态、推理、Superintelligence Labs

### 摘要

Meta 发布了 Muse Spark，这是其 Superintelligence Labs（成立仅 9 个月）推出的首个产品，也标志着 Meta 从 Llama 时代"开源权重"策略的重大转向。

**核心信息。** Muse Spark 是一个原生多模态推理模型，支持文本、图像、语音输入（最高 262,000 token），有三种推理模式：即时（instant）、思考（thinking）、沉思（contemplating）。在 Artificial Analysis 智能指数排名第四，在健康和多媒体基准上领先，但在编程和 Agent 工作方面不如 Meta 自己的 Llama 4 Maverick——Meta 将这描述为验证一种全新架构设计。

**有意思的技术。** Meta 重新设计了预训练方法、模型架构、优化和数据管理流程，声称用"一个数量级更少的处理资源"达到了 Llama 4 Maverick 的能力。在后训练中使用了强化学习，并引入了一种叫做"思维压缩"（thought compression）的技术：先惩罚模型用过长的推理 token，模型先通过更长的推理来改进，然后学会压缩推理，再进一步扩展推理。

**沉思模式（Contemplating mode）。** 不同于单链思维，它启动多个 Agent 并行提出方案、互相精炼、聚合结果。Meta 称这实现了更好的性能同时延迟相当。

**可及性。** 通过 meta.ai 和 Meta AI 应用免费使用；即将上线 WhatsApp、Instagram、Facebook、Messenger 和 Ray-Ban Meta AI 眼镜；API 仅向部分合作伙伴预览。

**对开发者的意义。** Meta 从"开源权重"转向"闭源产品"是一个重要信号——Llama 的开放时代可能暂时告一段落，Meta 在筹备更强大的模型。

---

## 四、Claude Code 与 Opus 4.7 配合最佳实践【⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/best-practices-for-using-claude-opus-4-7-with-claude-code
**关键词：** Claude Code、Opus 4.7、最佳实践、开发工作流

### 摘要

Claude 官方博客发布了 Opus 4.7 与 Claude Code 配合使用的最佳实践指南，涵盖 prompt 优化、工具使用技巧和工作流配置建议，帮助开发者充分发挥 Opus 4.7 在代码任务中的能力。

---

## 五、MaxText 新增 SFT 和 RL 微调支持（单 TPU 即可）【⭐】
**来源：** Google AI (Developers Blog)
**链接：** https://developers.googleblog.com/maxtext-expands-post-training-capabilities-introducing-sft-and-rl-on-single-host-tpus/
**关键词：** MaxText、SFT、RL、微调、TPU、开源

### 摘要

Google 宣布 MaxText 新增单主机 TPU 配置（如 v5p-8、v6e-8）上的 Supervised Fine-Tuning（SFT）和 Reinforcement Learning（RL）支持，让开发者可以在单个 TPU 上用 JAX 和 Tunix 库对预训练模型进行后训练微调。

**SFT（监督微调）。** 可以对 MaxText 或 Hugging Face 检查点（如 Gemma 3）进行微调，原生支持 Hugging Face 数据集（如 ultrachat_200k）。

**RL（强化学习）。** 支持 GRPO（Group Relative Policy Optimization）等前沿算法，使用 vLLM 进行训练循环中的高吞吐推理，用于数学、编程等需要复杂推理的任务。

**意义。** 降低了用 RL 方法训练模型的门槛——以前可能需要大规模集群，现在单 TPU 8 卡就能跑，降低了研究和小规模实验的成本。
