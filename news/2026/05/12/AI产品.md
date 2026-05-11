## 一、Claude Platform on AWS 正式 GA【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/claude-platform-on-aws
**关键词：** Anthropic, AWS, Claude Managed Agents, 企业级AI平台, AWS IAM, CloudTrail

### 摘要

Anthropic 宣布「Claude Platform on AWS」正式 GA（General Availability），这是 Anthropic 首个面向 AWS 客户的全功能 Claude API 平台产品，意义重大。

核心变化：AWS 客户现在可以直接通过 AWS IAM 认证、CloudTrail 审计日志、统一 AWS 账单来使用 Claude 的全部平台能力——包括最新的 Claude Managed Agents（Beta）、Advisor 策略、Web Search、代码执行等。所有新功能和 Beta 功能在同一天同步上线，和原生 Claude API 保持一致。

这意味着 AWS 大客户可以：
- 用自己的 AWS 凭证和 IAM 策略直接访问 Claude 全部能力
- 通过 AWS 账单统一结算，可抵扣已有承诺消费（commitment retirement）
- CloudTrail 审计所有 API 调用，满足合规要求

版本支持：Claude Opus 4.7、Sonnet 4.6、Haiku 4.5 均可用，新模型会在发布当天同步上线。

和 Bedrock 的区别：这俩不是竞品，是不同定位。
- **Claude Platform on AWS**：Anthropic 运营服务，数据处理在 AWS 边界外。适合想要完整 Claude 平台体验的公司。
- **Claude on Bedrock**：AWS 作为数据处理方，在 AWS 边界内运行。适合有严格数据驻留要求的公司。

客户案例：OpenRouter 和另外几家安全/工程公司已经在用，评价集中在「功能一致」「新能力同步快」「支持体验好」上。

## 二、Claude Code 推出 Agent View：一个终端接管所有并行 Agent【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/agent-view-in-claude-code
**关键词：** Claude Code, Agent View, 终端UI, 并行Agent, 开发工具

### 摘要

Anthropic 为 Claude Code 推出了「Agent View」（Agent 视图），一个让你在终端里统一管理所有 Claude Code 会话的界面。

**解决了什么问题？**

之前同时跑多个 Agent，你需要在多个终端标签页、tmux 网格之间来回切换，还要自己记每个 Agent 跑到哪了。Agent View 把所有会话放在一张表里，一眼能看到哪些 Agent 在等你回复、哪些还在跑、哪些已经完成。

**怎么用？**
- 在任何会话中按左箭头或运行 `claude agents` 打开 Agent 视图
- 每个会话显示名字、是否需要你输入、最后响应内容和最后互动时间
- 选中一个会话可以快速查看最后一条回复，如果需要你决定，直接原地回复就行
- 按 Enter 进入完整会话查看上下文
- `/bg` 命令把当前会话放到后台，或者直接用 `claude --bg [task]` 直接后台启动一个会话

**开发者实际用法：**
1. 同时跑多个思路，每个配合 skill，回来时一堆 PR 已经准备好了
2. 管理长跑 Agent：PR 看守、仪表盘更新等循环任务的状态一目了然
3. 快速上下文切换：在一个会话中按左箭头，开个新任务，再回来看结果

**评价：** 不是炫酷功能，但非常实用。对重度使用 Claude Code 的开发者来说，多 Agent 并行管理从「痛苦」变成了「顺手的事」。
