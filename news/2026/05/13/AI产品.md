## 一、Anthropic 举办 Code w/ Claude SF 2026 开发者大会，发布多项新功能【⭐⭐⭐】

**来源：** Claude Blog
**链接：** https://claude.com/blog/code-w-claude-sf-2026-sf
**关键词：** Anthropic, Claude Code, Managed Agents, Dreaming, 多智能体编排, 开发者大会

### 摘要

本周 Anthropic 在旧金山举办了年度开发者大会 **Code w/ Claude SF 2026**，主题是"Building on the AI Exponential"。大会核心传递的信息很明确：**从想法到生产软件的距离正在急剧缩短**，而那些最会利用 AI 的团队，正在围绕"AI 指数级增长"来设计他们的工程流程，而非被动应对。

**发布的重点更新有：**

**1. 额度翻倍（立即生效）**
- Claude Code 的 rate limit 翻倍
- Claude Opus 的 API 调用上限提升
- 对开发者、创业公司和企业的规模化部署是实打实的利好

**2. Claude Managed Agents 四大新能力**

- **Dreaming（回顾学习）**：一个定时跑的后台进程，会自动回顾 agent 之前执行过的 session，找出重复出现的失败模式、共享的工作流、团队偏好等，然后把它们整理到 memory store 里。相当于 agent 有了一个"自我复盘"机制，每次运行之间会变聪明。

- **多智能体编排（Multiagent Orchestration）**：一个 lead agent 可以把任务拆解，委托给多个 specialist subagents 并行工作，这些 subagents 跑在共享文件系统上，各自有独立的模型、prompt 和工具。整个流程可以在 Claude Console 里追踪查看。这基本就是 Anthropic 版的"多个 agent 协作干活"方案。

- **Outcomes（结果评估）**：开发者可以预先定义"什么算一个好结果"的评分标准。然后一个独立的 grader 会用自己的上下文窗口去评估 agent 的输出，达不到标准就让 agent 重来，直到达标。Anthropic 内部测试显示，在最难的任务上，Outcomes 能把成功率提升最多 10 个百分点。

- **Webhooks**：设定好 Outcome 之后，可以配置 webhook 通知。agent 跑完自动通知你，无需轮询。

**其他信息：**
- 大会还邀请了 Asana、Cursor、GitHub、Replit、Vercel 等公司分享他们如何在生产环境部署 agent。
- Code w/ Claude 接下来还会去伦敦（5/19-18）和东京（6/5-6），会有直播。
- 所有 keynote 和 breakout session 的录像已上传 YouTube。
