# AI 资讯日报

**日期：** 2026年4月16日（北美时间）

---

## 一、GPT-Rosalind：OpenAI 发布专用于生命科学的推理模型

**来源：** OpenAI Research  
**链接：** https://openai.com/index/introducing-gpt-rosalind/

### 摘要

OpenAI 推出了 GPT-Rosalind，这是其首个专为基础科学（biology、drug discovery、translational medicine）构建的前沿推理模型。名字取自 Rosalind Franklin——那位帮助揭示 DNA 结构、为现代分子生物学奠定基础的科学家。

这个模型的核心定位是**加速药物研发最早期的发现阶段**。传统上，一款新药从靶点发现到 FDA 批准上市，平均需要 10-15 年。其中早期发现阶段的效率提升，能在整个流程中产生连锁反应——更好的靶点选择→更强的生物学假说→更高质量的实验。

**主要能力：**

- 在 BixBench（真实生物信息学基准）上取得了发布模型中的领先成绩
- 在 LABBench2 的 11 项任务中，有 6 项超越了 GPT-5.4，尤其是在 CloningQA（DNA 分子克隆协议端到端设计）上提升显著
- 与 Dyno Therapeutics 合作，用 RNA 序列到功能的预测和生成任务做实测：模型生成的十个候选序列中，最好的那个排名超过了 95% 的人类专家；在序列生成任务上约达到 84% 的人类专家水平
- 配套推出 Life Sciences research plugin for Codex，集成 50+ 科学工具和数据库，涵盖人类遗传学、功能基因组学、蛋白质结构、生化、临床证据等领域

**商业合作方：** Amgen、Moderna、Allen Institute、Thermo Fisher Scientific 等。

---

## 二、Claude Opus 4.7 正式发布：Anthropic 最强旗舰编码模型

**来源：** Anthropic News  
**链接：** https://www.anthropic.com/news/claude-opus-4-7

### 摘要

Anthropic 发布了 Claude Opus 4.7，这是其目前最强的通用旗舰模型（Opus 系列），重点提升了**高级软件工程**能力，尤其在最困难任务上有显著进步。

用户报告说，以前需要密切监督才能交给 AI 做的"硬编码活儿"，现在可以放心地交给 Opus 4.7 了——它能处理复杂、长周期的任务，严谨且一致，能精确遵循指令，并在汇报结果前主动验证自己的输出。

**核心升级点：**

- 编码能力大幅提升：在 93 个任务的编码基准测试中，比 Opus 4.6 提升了 13%，其中 4 个任务连 Opus 4.6 和 Sonnet 4.6 都无法解决
- 视觉能力增强：支持更高分辨率的图像读取，在化学结构识别、复杂技术图表解读上表现更好
- 创造力提升：完成专业任务时更有品味，能产出更高质量的界面、幻灯片和文档
- 定价不变：$5/百万输入 tokens，$25/百万输出 tokens

**安全设计：** Opus 4.7 是 Anthropic 首个内置自动拦截高风险网络安全请求功能的模型。公司表示将先在 Opus 4.7 上测试网络安全保护措施，积累经验后再推进更强大的 Mythos 系列模型的广泛发布。有正当用途的安全专业人员可以申请加入 Cyber Verification Program。

---

## 三、Claude Opus 4.7 + Claude Code 最佳实践

**来源：** Claude Blog  
**链接：** https://claude.com/blog/best-practices-for-using-claude-opus-4-7-with-claude-code

### 摘要

官方发布了 Opus 4.7 与 Claude Code 搭配使用的详细指南，包含几个值得关注的要点：

**关于思维模式的新设计：** Opus 4.7 不再支持"固定思维预算的扩展思考"，改为**自适应思维（adaptive thinking）**——模型会在每个步骤自主决定是否启用更多思考，比之前更不容易"过度思考"了。用户也可以通过 prompt 引导：让它仔细思考，或者让它快速响应。

**默认 effort 设为 xhigh：** 这是新引入的档位（介于 high 和 max 之间），Claude 官方推荐大多数编程和 agentic 工作使用这个设置。

**行为变化：** Opus 4.7 默认回答更简洁（简单查询不再啰嗦），工具调用频率降低但单次质量更高，子代理启动也更审慎了——意味着它更倾向于直接完成能处理的工作，而非动不动就分叉出去。

---

## 四、Claude Code 会话管理与百万 token 上下文

**来源：** Claude Blog  
**链接：** https://claude.com/blog/using-claude-code-session-management-and-1m-context

### 摘要

Claude Code 官方发布了一篇深度指南，讲如何在 100 万 token 上下文的背景下有效管理会话。

**核心概念：**

- **上下文衰减（Context Rot）**：模型性能会随着上下文增长而轻微下降，因为注意力被分散到了更多 token 上，过时的无关内容会干扰当前任务
- **Compaction**：上下文接近窗口上限时自动压缩，任务被总结后在新窗口继续；但压缩是"有损"的，如果任务方向不清晰，重要细节可能被丢弃
- **Rewind（双击 Esc）**：跳回之前的消息重新执行，比纠正（"那样不行，试试 X"）更高效

**实操建议：**
- 同任务且上下文仍相关 → 继续当前会话
- Claude 走了弯路 → Rewind 到文件读取后重新提示
- 任务切换 → /clear 另起新会话
- 长时间运行的任务 → 预先 /compact 并指定焦点

---

## 五、Claude Code 推出 Routines：可编排的自动化工作流

**来源：** Claude Blog  
**链接：** https://claude.com/blog/introducing-routines-in-claude-code

### 摘要

Claude Code 正式推出 **Routines** 功能（研究预览版），这是一个可配置、可编排的 AI 自动化引擎——配置一次（包含 prompt、代码仓库、连接器），之后按计划（定时/API/Webhook）自动运行。

**三种触发方式：**

- **定时任务**：比如每天凌晨 2 点从 Linear 拉取最高优先级 bug，尝试修复并提 draft PR
- **API 触发**：为每个 Routine 生成独立端点和 token，CI/CD 流水线、监控系统、内部工具都可以直接调用
- **GitHub Webhook**：PR 合并时自动触发，为每个 PR 跑检查清单、代码审查等

**典型使用场景：**
- 夜间 bug 分类 + 分配 + Slack 汇总
- 每周扫描合并的 PR，检查文档是否过时并提更新 PR
- 部署后自动跑冒烟测试、扫描错误日志并推送结论
- 告警接入：拉取 trace、关联近期部署、提前生成修复草案

**用量限制：** Pro 用户每天最多 5 个 Routine，Max 用户 15 个，Team/Enterprise 25 个。

---

## 📊 综合分析

今天的 AI 资讯有三个值得关注的趋势：

**第一，垂直领域 AI 正在加速落地。** OpenAI 的 GPT-Rosalind 专门针对生命科学优化，不是一个通用模型，而是真正理解 DNA、蛋白质、基因路径的工具。与 Dyno Therapeutics 的实测数据很说明问题——最好的候选序列已经超过了 95% 的人类专家。这不是"可能有用"，是"已经比大多数人类做得更好"了。制药行业可能是 AI 下一波爆发的领域。

**第二，Claude Opus 4.7 代表了"编码 AI 自主化"的临界点。** Anthropic 的说法很直接——以前需要密切监督的硬编码任务，现在可以放心交给 Opus 4.7，而且它会主动验证自己的输出。这意味着 AI coding 正在从"辅助工具"进化到"可以独立负责一个完整任务"的阶段。4 个连 Opus 4.6 和 Sonnet 4.6 都无法解决的问题被 Opus 4.7 攻克，这个进步幅度不小。

**第三，Claude Code 的 Routines 功能是 AI Agent 走向生产自动化的标志性事件。** 过去用 Claude Code 自动化工作流需要自己搭 cron + MCP 服务器，现在官方直接把这个能力做成了产品。按计划执行、API 触发、GitHub Webhook 事件驱动——这是把 AI 从"对话工具"变成"自动化员工"的关键步骤。结合之前发布的百万 token 上下文和会话管理最佳实践，Claude Code 正在成为工程团队的基础设施层。
