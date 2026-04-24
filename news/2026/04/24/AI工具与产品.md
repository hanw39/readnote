# AI工具与产品

## 一、Built-in memory for Claude Managed Agents【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/claude-managed-agents-memory
**关键词**：Claude Managed Agents、记忆系统、跨会话学习、企业级Agent、生产力

### 摘要

Anthropic 宣布 Claude Managed Agents（企业级托管Agent）推出内置记忆功能，现在进入公开测试阶段。这是一个面向生产环境的重要升级——Agent 不再是"每次对话从零开始"，而是可以从每一次会话中学习和积累经验。

**核心设计：文件系统挂载的记忆层**

记忆系统直接挂载到文件系统，Claude 可以像操作普通文件一样读写记忆。这意味着企业不需要改变现有的开发工作流——Agent 用什么工具（bash、代码执行），记忆系统就用什么方式工作。最新模型（Opus 4.7）在文件系统记忆上表现更好，能保存更完整、结构化的记忆，且对"该记住什么"更敏锐。

**企业级特性：可移植、可审计、可回滚**

记忆是文件，企业可以随时导出、通过 API 管理，完全掌控 Agent 保留了什么。所有变更都有详细审计日志，可以追溯"这条记忆是哪个 Agent、哪个会话产生的"。支持回滚到早期版本，也支持从历史记录中删除内容。在 Claude Console 里，所有记忆变更都作为会话事件展示，开发者可以追踪 Agent 学到了什么、来自哪里。

**权限控制：跨Agent共享记忆**

支持跨多个 Agent 共享记忆库，且可以设置不同访问范围。比如全公司共用的记忆库设为只读，而每个用户的记忆库允许读写。多个 Agent 可以同时操作同一个记忆库而不会互相覆盖。

**真实案例效果**

- **Netflix**：Agent 可以在不同会话间携带上下文，包括需要多轮才能发现的洞察，以及人工中途纠正的内容，不用再手动更新 prompt 和 skills
- **Rakuten**：基于任务的长运行 Agent 通过记忆避免重复犯错，一审错误率降低 **97%**
- **Wisedocs**：用跨会话记忆让 Agent 发现并记住常见的文档问题，审校速度提升 **30%**
- **Ando**：构建工作场所消息平台时用记忆捕获每个组织与 Agent 的交互方式，不用自己搭记忆基础设施

**一句话总结**

Claude Managed Agents 的记忆功能让 Agent 在生产环境中实现持续学习：错误率降低 97%，成本降低 27%，延迟降低 34%——且记忆的范围和变化都在企业可控范围内。

---

## 二、New connectors in Claude for everyday life【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/connectors-for-everyday-life
**关键词**：Claude Connectors、日常生活应用、200+连接器、AI助手生态

### 摘要

Anthropic 宣布 Claude 的连接器（Connectors）功能大规模扩展——从工作场景扩展到日常生活工具，涵盖旅行、美食、出行、音乐、健康等领域的 15 个新应用。同时还改进了连接器在对话中的呈现方式，Claude 会主动推荐当前任务最相关的应用。

**新接入的 15 个应用**

AllTrails、A Audible、Booking.com、Instacart、Intuit Credit Karma、Intuit TurboTax、Resy、Spotify、StubHub、Taskrabbit、Thumbtack、TripAdvisor、Uber、Uber Eats、Viator——基本上覆盖了一个人从周末出行到日常生活的方方面面。

自 2025 年 7 月上线以来，Claude Directory 已接入超过 200 个连接器。用户经常在一个对话里组合使用多个应用——比如一个产品经理从 Amplitude 拉数据，转成 Canva 演示文稿，再把链接丢进 Asana，全程不用离开对话。

**连接器智能推荐**

现在 Claude 会在对话中主动推荐适合当前任务的连接器——比如检测到你需要找餐厅预订，它就会弹出 Resy；检测到你需要打车，就推荐 Uber。这基于你之前告诉 Claude 的偏好和当前对话上下文。当两个以上的连接器都能回答你的问题时，Claude 会把两个都展示出来，让你选择，而不是擅自选一个。

**隐私承诺**

Anthropic 明确承诺 Claude 无广告，不会出现付费植入或赞助回答。当两个连接器都可能有用时，你看到的是按对你的有用程度排名，而非按谁付钱多排名。连接一个服务意味着给 Claude 代表你访问该应用的权限，但该应用看不到你其他的 Claude 对话，且你的数据不会用于训练 Anthropic 的模型。在帮用户实际下单或购买前，Claude 会主动确认，不会擅自行动。

---

## 三、Bringing memory to Claude【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/memory
**关键词**：Claude Memory、项目记忆、Incognito模式、工作场景、隐私

### 摘要

Anthropic 正式向 Team 和 Enterprise 用户推出 Claude 的记忆功能（Memory）——Claude 会记住你和你的团队的项目、偏好，不用每次重新解释上下文，多线程工作也能无缝衔接。Pro 和 Max 用户也在后续开放中。

**工作场景的记忆设计**

Memory 专注于学习用户的职业背景和工作模式：团队的工作流程、客户需求、项目细节、优先级。销售团队跨交易记住客户背景，产品团队跨迭代维护规格说明，高管追踪跨 Initiative 不用每次重建上下文。

如果你使用 Projects，Claude 会为每个 Project 创建独立记忆——产品发布规划和工作客户项目互不干扰，机密讨论和日常运营分开。这些边界本身就是一种安全护栏，确保敏感对话被隔离管理。

**记忆摘要：可查看、可编辑**

Claude 用一个"记忆摘要"来聚合所有记忆，用户可以在设置里查看 Claude 记住了什么，随时通过对话修改摘要。基于你让 Claude 关注什么或忽略什么，Claude 会相应调整它引用的记忆。

**Incognito 模式**

不想留下任何记忆？Incognito 聊天不进入对话历史，也不保存到记忆——适合敏感头脑风暴、机密策略讨论，或者只是想开一个全新对话不想带任何历史包袱。Incognito 对所有 Claude 用户开放。

**安全性测试**

Anthropic 在推出记忆功能前，进行了大量针对敏感话题的专项安全测试——包括记忆是否会在对话中强化有害模式、是否会导致过度迁就用户、是否可能被尝试绕过安全护栏。通过这些测试，团队识别出了需要改进的地方，并做了针对性调整，确保记忆功能既有用又安全。

---

## 四、Building real-world on-device AI with LiteRT and NPU【⭐⭐】
**来源：** Google AI
**链接：** https://developers.googleblog.com/building-real-world-on-device-ai-with-litert-and-npu/
**关键词**：LiteRT、NPU、本地AI、Google AI Edge、性能优化、端侧AI

### 摘要

Google 介绍了 LiteRT——一个跨平台的生产级端侧 AI 框架，如何通过解锁 NPU（神经处理单元）为移动端带来高性能 AI 体验。NPU 是专门为 AI 推理任务设计的硬件，兼顾设备热管理和电池续航，让应用在不卡顿的前提下实现实时 AI 功能。

**LiteRT 是什么**

LiteRT 是一个跨平台生产就绪框架，支持 CPU、GPU、NPU 加速，覆盖手机、桌面和 IoT 设备。它提供统一 API，抽象了与不同 NPU SDK 对接的复杂性，让开发者无需写厂商特定代码，就能针对不同芯片做优化。LiteRT 已经在 Google 自家产品、各种流行应用和 SDK 中经过了充分验证。

**真实案例：性能提升显著**

- **Google Meet**：借助移动端 NPU，成功部署了比上一代大 **25 倍**的超高清分割模型，推理速度没有牺牲。在典型 20-30 分钟会议中维持稳定的功耗曲线，为全程高质量背景替换创造了散热空间
- **Epic Games**：Live Link Face（Beta）应用通过 LiteRT 在 NPU 上运行，在支持的 Android 设备上实现最高 **30 FPS** 的实时 MetaHuman 面部动画，支持从单摄像头实时驱动 Unreal Engine 中的数字人面部
- **Argmax**：Argmax Pro SDK 通过 LiteRT + Google Play AI Pack 在 Android 上实现顶级语音识别精度和实时速度。从 GPU 升级到 NPU 带来 **2 倍以上**速度提升，且 NPU 的功耗优势让长时间实时转录成为可能（例：Heidi Health 医疗客户的长时间录音转写场景）

**跨平台支持：手机到工业边缘**

LiteRT 不仅限于手机，还支持工业边缘场景（如高通 IQ8 系列驱动的机器人和智能制造）和 AI PC（通过 Intel Core Ultra 系列 2/3 代处理器的 OpenVINO 集成实现本地 GenAI 负载的功耗节省和响应速度提升）。

**Google AI Edge Gallery**

Google 推出了 AI Edge Gallery App（Android），帮助开发者测试和验证 NPU 加速性能，内置 Gemma 模型基准测试工具，开发者可以直观看到移动硬件上 AI 的真实性能。

**一句话总结**

LiteRT 用统一 API 解决了 NPU 碎片化问题，让开发者用一套代码在手机、边缘设备、AI PC 上释放 NPU 性能——Google Meet 分割模型大了 25 倍不掉速，Epic Games 数字人跑出 30 FPS，Argmax 语音延迟降了一半。

## 一、Anthropic 详解 Claude Code 质量下降事件：三次变更叠加导致用户体验恶化【⭐⭐⭐】
**来源：** Anthropic Engineering
**链接：** https://www.anthropic.com/engineering/april-23-postmortem
**关键词**：Claude Code、质量问题、postmortem、推理努力、缓存bug、系统提示词

### 摘要

过去一个月，部分用户反映 Claude Code 回答质量变差。Anthropic 调查后确认这是三次独立变更叠加的结果，三者分别在不同时间影响不同模型群体，影响范围和表现不一，汇总起来看起来像"全面性的、不一致的"体验恶化。三次问题均已在 4 月 20 日前全部修复。

**第一次变更（3月4日）：推理努力默认值从 high 降为 medium**

Opus 4.6 发布时，默认推理努力设为 high，但有用户反馈高模式延迟过高、界面卡顿。Anthropic 内部测试发现 medium 延迟更低且"大多数任务"质量差距不大，于是将默认值改为 medium。实施后大量用户反馈 Claude Code"变笨了"。团队尝试通过启动提示、内联选择器等方式让用户自己调节，但大部分用户未主动更改。4 月 7 日，Anthropic 恢复默认值：Opus 4.7 默认为 xhigh，其他型号为 high。

**第二次变更（3月26日）：缓存优化 bug 导致会话越来越健忘**

Claude 的推理过程会保留在对话历史中，以便后续轮次理解之前的决策。Anthropic 原本的优化逻辑是：会话空闲超过 1 小时则清除旧推理内容（反正缓存也会失效），节省未缓存 token 的发送量。实现中有一个 bug：不是"只清除一次"，而是"之后每轮都清除"。导致会话一旦跨越空闲阈值，之后每一轮都丢弃旧的推理块，越来越"失忆"，表现为重复、遗忘、奇怪的工具调用。同时因为持续丢 token 导致缓存命中失效，用户报告用量限制消耗异常快。4 月 10 日修复。

**第三次变更（4月16日）：系统提示词限制回复长度，严重影响编码质量**

Opus 4.7 发布时有一个问题：回答偏啰嗦。Anthropic 在系统提示词中加入了一条指令："工具调用之间文字不超过 25 词，最终回复不超过 100 词，除非任务需要更多细节。"内部测试数周未见回归，于是随 Opus 4.7 一起发布。4 月 20 日调查时才发现，该变更叠加其他 prompt 变化导致编码质量显著下降（ ablation 测试显示 Opus 4.6 和 4.7 均下降 3%）。当日回滚。

**调查过程中的困难**

三个问题各自在不同的流量切片、不同时间线上发生，汇总效应难以与正常用户反馈波动区分。内部用量和 evals 均未能在早期复现这些问题。值得一提的是，在复盘时用 Opus 4.7 做代码审查——把有问题的代码仓库完整提供给模型——Opus 4.7 发现了这个 bug，而 Opus 4.6 没有。这推动了 Anthropic 决定将代码仓库上下文引入 Claude Code Review 功能。

**后续行动**

Anthropic 宣布：① 让更多内部员工使用与外部用户完全相同的 Claude Code 正式版；② 改进内部 Code Review 工具并开放给自定义模型用户；③ 为所有 4 月订阅用户重置用量限制。

**对普通开发者的意义**

这次事件本身是一次工程失误，但暴露了 Claude Code 作为产品（而非纯 API）面临的独特挑战：产品层的默认值、UI 交互和系统提示词与模型能力之间的耦合极为紧密，一个看似无害的改动可能产生非线性的质量影响。这也说明用 Claude Code 类工具做关键编码任务的开发者，需要注意它并不是纯 API，它的"健康状态"需要主动关注——如果突然感觉 Claude"变笨了"，不一定是大模型本身的问题，可能是产品层的配置变更。

---

## 二、Anthropic 详解 Managed Agents 架构：将"大脑"与"手"解耦【⭐⭐⭐】
**来源：** Anthropic Engineering
**链接：** https://www.anthropic.com/engineering/managed-agents
**关键词**：Managed Agents、Agent架构、Session抽象、Sandbox、安全隔离、多脑多手

### 摘要

Anthropic 发布了一篇深度技术文章，详细阐述 Claude Managed Agents（企业级托管 Agent）的系统架构设计思路，核心洞察是：将 Claude"大脑"（推理和 harness）与"手"（代码执行沙箱、Sandbox）和"记忆"（Session 事件日志）彻底解耦，是一个类似于操作系统虚拟化硬件的思路，使得各组件可以独立演进、替换和扩展。

**从"宠物"到"牛群"的转变**

最初的设计把 Session、Agent harness 和 Sandbox 全放在同一个容器里，文件编辑直接是系统调用，没有服务边界。但这样做带来了"宠物问题"：容器挂了 Session 就丢了，容器卡了只能人工慢慢恢复。调试手段只有 WebSocket 事件流，无法区分 harness bug、网络丢包还是容器本身挂了，而要打开 shell 调试又因为容器里有用户数据而无法操作。

解耦方案：将 harness 移出容器，通过 execute(name, input) → string 接口调用容器，就像调用任何其他工具一样。容器变成了"牛群"：死了就换一个，不需要抢救。Session 日志独立于 harness 存在，harness 崩溃后新的 harness 可以用 wake(sessionId) + getSession(id) 恢复所有事件日志，无缝接续。

**安全边界：凭证如何与沙箱隔离**

在耦合架构中，未信任代码和凭证在同一容器里运行，prompt injection 只要说服 Claude 读取自己的环境就能拿到凭证。解决方案：凭证要么绑定在资源上（如 Git 仓库 token 在初始化时注入本地 git remote，Agent 推送拉取不需要处理 token 本身），要么存在外部 vault（如 MCP 的 OAuth token 通过专用代理访问，代理从 vault 取凭证，harness 完全不知道凭证内容）。

**Session 不是 Context Window**

Agent 跑长任务会超出上下文窗口。标准方案（compaction、memory tool、context trimming）都涉及不可逆的信息丢弃决策。Managed Agents 的 Session 是一个独立于 Context Window 的持久化对象，通过 getEvents() 接口让大脑按需查询历史事件片段（可以取当前位置、倒带几步看上下文、做事先重新读取），且 harness 可以在传给 Claude 前对事件做转换（组织上下文以提高缓存命中率等）。这个设计将"持久化存储"和"上下文工程"两个关注点分离。

**多脑多手带来的性能提升**

将大脑放进独立容器导致每个大脑都需要独立容器实例，每个 Session 即使不需要沙箱也要等容器完全启动（包括 clone repo、启动进程、获取待处理事件），导致 time-to-first-token（TTFT）成为瓶颈。解耦后沙箱按需启动（通过工具调用才创建），不需要沙箱的 Session 可以立即开始推理。采用新架构后 p50 TTFT 下降约 60%，p95 下降超过 90%。

多脑多手还允许每个大脑连接多个执行环境，Claude 可以跨多个沙箱分配任务，且一个大脑可以将手（执行环境）移交给另一个大脑。

**对开发者的意义**

Anthropic 将 Managed Agents 定性为"元 harness"——它不规定具体实现，只定义接口（Session、Harness、Sandbox），所以它能适应未来可能出现的任何 harness。这和操作系统用几十年是一个思路：read() 接口不关心底层是磁盘还是 SSD。这个设计选择意味着 Anthropic 在 Agent 基础设施上的赌注相当大，Managed Agents 未来可能成为企业 AI Agent 部署的事实标准底层。

---

## 三、研究发现：基础设施配置能以超过 SOTA 模型差距的幅度影响 Agent 编程评测结果【⭐⭐】
**来源：** Anthropic Engineering
**链接：** https://www.anthropic.com/engineering/infrastructure-noise
**关键词**：Agent评测、基础设施、SWE-bench、Terminal-Bench、资源配置、测量误差

### 摘要

Anthropic 在调试 Terminal-Bench 2.0 评测环境时发现：基础设施配置本身就能产生超过 SOTA 模型之间差距的分数差异。在同一 Claude 模型、同一评测任务的不同资源配额下，最宽松 vs 最严格配置的评测分数相差 6 个百分点（p < 0.01）——而目前顶级编程模型在排行榜上的差距往往只有几个百分点。

**怎么发现的**

Anthropic 在 GKE 集群上跑 Terminal-Bench 2.0 时发现分数与官方排行榜不一致，基础设施错误率高达 6%。追查原因：他们的 Kubernetes 实现把 per-task 的资源规格同时作为"保证下限"和"硬上限"，即容器 reserved 了资源但不能超用，一超过就 OOM kill。Terminal-Bench 官方的排行榜用了另一个沙箱提供商，实现更宽松，允许暂时超用。两种执行方式代表了"严格资源控制"和"宽松资源容忍"两种哲学。

**实验设计**

Anthropic 在 Terminal-Bench 2.0 上跑了 6 种资源配置：严格 1x（资源规格 = 保证 = 上限）→ 逐步宽松 → 完全不设上限。结果：

- 基础设施错误率：严格 1x 为 5.8%，完全不设上限为 0.5%（逐步下降，每步都显著）
- 1x 到 3x 之间：分数在噪声范围内（p=0.40），多出的资源主要是修复了 infra 错误而不是让任务变简单
- 3x 以上：分数开始明显上升，因为额外资源让 Agent 可以执行"只有在宽松资源下才能成功"的策略（如拉取大型依赖、运行内存密集型测试套件）
- 完全不设上限相比 1x：总分提升 6 个百分点（p < 0.01）

在 SWE-bench 上做了交叉验证，RAM 从 1x 到 5x 也有类似趋势（提升 1.54 个百分点），幅度较小是因为 SWE-bench 任务本身资源需求更低。

**更广泛的影响**

不同资源限制实际上在测不同的东西：严格限制奖励"写得精简高效"的 Agent，宽松限制奖励"大力出奇迹"的 Agent，两者都是合法能力，但混在同一分数里无法区分。另外实测发现任务通过率在一天内随时间波动（可能与 API 延迟随流量变化有关），说明"模型能力"和"基础设施行为"之间的边界比单看排行榜数字要模糊得多。

**建议**

- 评测应该将资源规格的 guarantee 和 kill threshold 分开设置，而不是设成同一个值
- guarantee 到 kill threshold 之间的 buffer 应该调校到"分数在两者之间落在噪声范围内"为止（Anthropic 建议 3x 作为 Terminal-Bench 2.0 的合理起始点）
- 排行榜差异小于 3 个百分点时需要谨慎解读，除非评测配置被完整披露

**对模型开发者的意义**

对于 Labs：这个发现意味着 Agent 编程评测的资源配置应该被当作"一级实验变量"来对待，和 prompt 格式、采样温度一样重要。对于评测维护方：公布执行方法论（包括 enforcement methodology）可以大幅减少测量误差。对于普通用户：如果你在两个模型之间看到 2 分的差距，在没有看到完整评测配置说明之前，不要轻易下结论。SOTA 可能只是拥有更强机器的 SOTA。

---
