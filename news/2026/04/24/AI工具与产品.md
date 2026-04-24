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
