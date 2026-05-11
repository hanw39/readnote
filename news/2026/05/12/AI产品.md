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
