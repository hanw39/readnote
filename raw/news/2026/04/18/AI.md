# AI 资讯 | 2026-04-18

## 核心主题

**多模态推理全面爆发，AI 正在从"能说会道"进化到"能看会做"。** 本周最重磅的新闻集中在模型能力升级：大模型在软件工程、多模态理解、推理效率上同时突破，而 AI 辅助药物研发传来了可能是迄今为止最有说服力的一次临床数据。

---

## 一、Claude Opus 4.7 发布——Anthropic 的最强代码模型

**来源：** Anthropic News，2026-04-16

Anthropic 发布了 Claude Opus 4.7，这是其 Opus 系列的最新旗舰模型。相比 Opus 4.6，在高级软件工程任务上有显著提升，尤其体现在最困难的任务上。用户反馈称，以前需要密切监督才能完成的硬编码任务，现在可以放心交给 Opus 4.7 了。

### 核心能力提升

- **软件工程**：内部 93 个编码任务基准测试中，Opus 4.7 比 Opus 4.6 提升了 13% 的分辨率，其中 4 个任务连 Opus 4.6 和 Sonnet 4.6 都无法解决；
- **视觉理解**：支持更高分辨率的图像理解，在图表、界面截图等视觉任务上表现更强；
- **专业创意**：在完成专业任务时更有品味和创造力，能输出更高质量的界面、幻灯片和文档；
- **推理效率**：推理时能主动发现逻辑错误，在规划阶段就自我修正；
- **长上下文**：多步工作场景中效率基线最强，六个模块综合得分 0.715，遥遥领先。

### 定价不变

输入 $5/百万 token，输出 $25/百万 token，与 Opus 4.6 相同。可通过 Claude API、Amazon Bedrock、Google Vertex AI、Microsoft Foundry 获取。

### 附带网络安全护栏

值得注意的是，Opus 4.7 是 Anthropic 第一个内置网络攻击防御机制的模型。它能自动检测并阻断有网络攻击风险的使用请求（漏洞研究、渗透测试、红队演练除外）。Anthropic 还启动了"网络验证计划"（Cyber Verification Program），邀请安全研究人员申请使用。这是 Anthropic 在 Mythos Preview（最强网络攻击能力模型）全面开放之前，先在小规模部署中测试安全护栏的策略。

### 横向对比

Claude Opus 4.7 在 The Batch 引用的 Artificial Analysis Intelligence Index 综合榜单中（thinking 模式），得分为 53，落后于 GPT-5.4（57）和 Gemini 3.1 Pro Preview（57），与 Claude Opus 4.6 持平。但它是目前公认的最强编程模型，多个金融科技公司和工程团队给出了极高评价，认为它"低投入就能达到以前中投入才能达到的效果"。

---

## 二、Claude Design 发布——Anthropic 正式进军 AI 设计工具

**来源：** Anthropic News，2026-04-17

Anthropic 在发布 Opus 4.7 的第二天，顺势推出了 **Claude Design**，这是一款与 Claude 协作创建可视化作品的产品，定位是让设计师能够大规模探索创意，同时让非设计师也能产出专业级视觉内容。

### 能做什么

- **真实可交互原型**：把静态设计稿变成可分享、可用户测试的交互原型，无需代码审查或 PR；
- **产品线框图和高保真稿**：产品经理可以直接生成产品功能流程图，还能直接交给 Claude Code 实现；
- **设计方向探索**：设计师可以快速生成多个不同方向；
- **融资路演和演示文稿**：从大纲到完整 PPT，一键导出或发送到 Canva；
- **营销物料**：落地页、社交媒体图、活动视觉；
- **前沿交互**：语音、视频、Shader、3D、内置 AI 的代码驱动原型。

### 工作流程亮点

1. **上线引导时，Claude 读取团队的代码库和设计文件，自动生成一套品牌设计系统**（颜色、字体、组件），此后所有项目自动沿用这套系统；
2. 支持文字描述、图片文档（DOCX、PPTX、XLSX）或直接指向代码库启动项目；
3. 支持画布内评论、组件直接编辑、参数滑块微调；
4. **直接移交 Claude Code**：设计完成后，Claude 打包成交接包，一句话就能让 Claude Code 实现；
5. 导出为内部 URL、文件夹、Canva、PDF、PPTX 或独立 HTML 文件。

### 合作伙伴

Canva CEO Melanie Perkins 亲自背书，双方正在深化整合——Claude Design 的作品可以直接发到 Canva 变成可编辑的协作设计。

**获取方式：** 面向 Claude Pro、Max、Team 和 Enterprise 订阅用户，逐步开放。

---

## 三、Meta Muse Spark——Llama 时代结束，闭源多模态时代开启

**来源：** The Batch（DeepLearning.AI），2026-04-17

Meta 推出了 Muse Spark，这是 Meta 一年来的首个新模型，也是其超级智能实验室（Superintelligence Labs，成立仅九个月）的第一个产品。**这是 Meta 首次发布非开源权重的模型，标志着其正式从"开源旗手"转向商业闭源竞争。**

### 模型定位

Muse Spark 是原生多模态推理模型，支持文字、图像、语音输入（最多 26 万 token），支持工具调用和多智能体编排。

### 性能表现

- Artificial Analysis Intelligence Index（thinking 模式）：排名第 4（52分），落后于 GPT-5.4（57）、Gemini 3.1 Pro Preview（57）和 Claude Opus 4.6（53）；
- **但 token 效率极高**：完成同样评测仅用了 5900 万 token，而 Claude Opus 4.6 用掉了 1.58 亿 token；
- MMMU Pro（多学科视觉问题）：排名第 2（81%），仅次于 Gemini 3.1 Pro（82%）；
- Coding Index：47 分，明显落后于 GPT-5.4（57）和 Gemini 3.1 Pro Preview（56）；
- HealthBench Hard：Meta 自测 42.8%，领先 GPT-5.4（40.1%），是其最大亮点；
- Humanity's Last Exam（contemplating 模式）：Meta 报告 58%，评测机构实测 39.9%——两者差距悬殊。

### 三种推理模式

- **即时（Instant）**：快速响应；
- **思考（Thinking）**：深度推理；
- **沉思（Contemplating）**：多个智能体并行提案、互评、聚合，延迟与单链推理相当。Meta 称这是实现"更强性能同时不增加延迟"的关键设计。

### 背后的战略转移

Muse Spark 的发布伴随着 Meta AI 战略的重大转变：

- 过去 Llama 系列是 Meta 作为"美国开源 champion"的标志性资产，开发者社区依赖它构建项目；
- 现在 Muse Spark 不公开参数规模、架构、训练数据，API 也仅向部分合作伙伴预览；
- Meta 已在 2025 年 6 月向 Scale AI 投资 143 亿美元（占股 49%），任命联合创始人 Alexandr Wang 为首席 AI 官，招聘规模耗资数亿美元；
- 其闭源策略让很多基于 Llama 构建的开发者社区面临失去上游支持的风险。

**值得关注：** Muse Spark 的 contemplating 模式和多智能体编排，代表了行业的一个新趋势——不再一味堆大模型参数，而是通过推理时的多智能体协作来提升性能。

---

## 四、AI 药物研发最大订单——Eli Lilly 向 Insilico 投资 27.5 亿美元

**来源：** The Batch（DeepLearning.AI），2026-04-17

制药巨头 Eli Lilly（全球市值最高的药企）与 AI 药物发现公司 Insilico Medicine 达成协议，最高投资 27.5 亿美元：首期支付 1.15 亿美元获得某种尚未在人体测试的药物的独家开发与销售权，后续里程碑付款另计。这是两家公司 2023 年以来的第三次合作。

### Insilico 的成绩单

Insilico 成立于 2014 年，专注于用生成式 AI 全流程辅助药物发现：

- 已开发 **28 个候选药物**，约一半进入临床试验；
- 最先进的药物 **Rentosertib**（治疗特发性肺纤维化，IPF），在 Phase 2a 试验中，高剂量组用力肺活量平均增加 98.4 毫升，安慰剂组减少 20.3 毫升——**这是 AI 设计药物首次在临床试验中显示出对患者的明显益处**；
- 第二个药物 **Garutadustat**（治疗炎症性肠病）已于 2026 年 1 月进入 Phase 2a。

### AI 是怎么做到的

传统药物发现通常需要筛选 20 万到 100 万个现有化合物，再合成和测试数百个候选分子。Insilico 的流程：

1. 用 **PandaOmics** 分析生物数据集、论文、专利、临床试验等，找出与疾病最相关的蛋白质靶点；
2. 对 IPF，AI 找到了 **TNIK** 蛋白——之前从未有人尝试过用阻断 TNIK 来治疗 IPF；
3. 用 **Chemistry42**（约 30 个生成模型并行运行）设计分子结构，优化靶向结合力、毒性、溶解度等属性；
4. 科学家只评价和微调了不到 **80 个化合物**，就找到了临床前候选分子；
5. 全流程只用了 **18 个月**，传统方式通常需要 5-6 年。

### 重要警示

目前**没有任何一款 AI 发现的药物获得监管批准**。进入 Phase 2 的候选药物，约 70% 会失败，包括 BenevolentAI 和 Recursion Pharmaceuticals 的 AI 设计药物。Insilico 的 Phase 2a 数据是迄今最令人鼓舞的早期证据，但距离真正成药还有很长的路。

---

## 五、监管碎片化继续——美国各州加速推进 AI 立法

**来源：** The Batch（DeepLearning.AI），2026-04-17

尽管特朗普政府试图阻止各州独立立法，推动全国统一标准，但各州 AI 立法势头不减。据纽约时报统计，目前全美 40 个州已有 100 多部现行 AI 相关法律，另有 1500 多部法案正在审议中。

主要方向包括：

- **限制未成年人使用聊天机器人**
- **要求使用版权材料训练 AI 前须获得许可**
- **要求对 AI 系统进行安全测试**

加州最为激进，已建立美国最全面的 AI 法律体系（2026-03-30）。

### 对开发者意味着什么

在美国开发 AI 产品，需要同时满足多个州的不同要求，合规成本显著上升。这对创业公司和小型开发者尤其不利。

---

## 本周趋势总结

| 趋势 | 代表事件 | 意味 |
|------|---------|------|
| 模型能力分工细化 | Claude Opus 4.7 主攻工程，Muse Spark 主攻健康 | 垂直场景优化成为新竞争维度 |
| 开源 vs 闭源格局重塑 | Meta 放弃开源策略 | 美国大厂全面走向闭源，开发者社区受影响 |
| 多智能体推理成为主流 | Muse Spark contemplating 模式、Kimi K2.5 Agent Swarm | 不再只堆大模型，推理时协作成为新范式 |
| AI 设计工具井喷 | Claude Design 发布 | AI 原型设计赛道正式开打，Canva、Framer 等面临压力 |
| AI 制药临床数据首获验证 | Rentosertib Phase 2a 积极结果 | AI 制药从"故事"进入"证据"阶段 |

---

## 延伸阅读

- Claude Opus 4.7 技术博客：https://www.anthropic.com/news/claude-opus-4-7
- Claude Design 介绍：https://www.anthropic.com/news/claude-design-anthropic-labs
- The Batch Issue 349：https://www.deeplearning.ai/the-batch/issue-349/
