## 一、Anthropic 用 Claude Code 搭建了自己的网络安全威胁检测平台【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/how-anthropic-uses-claude-cybersecurity
**关键词：** Anthropic, Claude Code, 安全检测, CLUE, 告警自动化, 威胁响应, AI Agent

### 摘要

Anthropic 的安全检测平台工程团队（Detection Platform Engineering Team）在技术负责人 Jackie Bow 的带领下，用自家产品 Claude Code 搭建了一个名为 CLUE（Claude Looks Up Evidence）的检测与响应平台，用来解决安全团队面临的三个核心痛点：

1. **告警过载**：安全分析师每天面对大量告警，手动分类真假阳性非常耗时。CLUE 的 Triage 模块能在人工介入前完成首轮筛查，自动关联 Slack 消息、内部文档、代码仓库、数据仓库等多源上下文判断告警性质（误报/真阳性/恶意/预期行为），并给出置信度评分。部署后误报率从 33% 降到 7%。

2. **上下文碎片化**：安全调查需要跨五六种工具来回切换（每种的查询语法都不一样）。CLUE 用自然语言接口替代了这一切——分析师可以直接问"过去一天这个系统有哪些登录失败？"，Claude 自动生成并执行 SQL 查询。单次调查平均 25 次工具调用、近 11 次查询，远超人工能手动执行的数量。

3. **低置信度信号被忽略**：过去低优先级告警根本没时间看。现在 CLUE 批量处理数千条之前被忽略的信号。30 天数据表明，CLUE 自动化了约 12000 次查询和 27000 次工具调用，折合约 1870 小时的工作量（约 234 个工作日），相比人工调查节省 5-10 倍时间。

最值得关注的是 CLUE 的原理复用性——它不是又一个仪表盘工具，而是用 Claude 的 Tool Use 能力把 Anthropic 内部系统（Slack、代码仓库、数仓等）串联成一个统一的 Agent。这套模式完全可以被其他安全团队复制。

---

## 二、Claude 发布 20+ 法律行业 MCP 连接器和 12 个实践领域插件【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/claude-for-the-legal-industry
**关键词：** Anthropic, Claude, 法律行业, MCP, 插件, 合同管理, 诉讼, 合规, 知识产权

### 摘要

Anthropic 今天发布了一整套法律行业工具——20+ 个 MCP 连接器 + 12 个实践领域插件，目标是让 Claude 能直接对接法律团队使用的各种专业系统。

**连接器覆盖的领域非常全面：**
- **合同生命周期**：Definely（合同结构解析）、Docusign（协议工作流）、Ironclad（合同库问答）
- **交易室与文档管理**：Box、Datasite（M&A 虚拟数据室）、iManage、NetDocuments、Lawve AI 等
- **电子证据开示与诉讼**：Everlaw、RelativityOne 等
- **法律研究**：Thomson Reuters（CoCounsel，链接 Westlaw/KeyCite 权威法源）、Midpage、Trellis（美国州法院数据库）、Free Law Project（CourtListener）
- **知识产权**：Solve Intelligence（专利检索与撰写）
- **司法公正**：Courtroom5（无律师诉讼当事人辅助）、BoardWise（州律师协会事务）、Descrybe（判例研究）

**12 个实践领域插件覆盖了常见的法律角色：**
- 商业法务（NDA 审查）、公司法务（M&A 全流程）、雇佣法务、隐私法务（DPA 审查、DSAR 回复）
- 产品法务（上线审查）、合规法务（法规监控）、AI 治理法务（AI 用例分级评估）
- 知识产权法务（商标、DMCA、开源合规）、诉讼法务等

**关键亮点：**
- 法律专业人士已成为 Claude Cowork 各职能中最活跃的用户群
- Opus 4.7 在 Harvey 的 BigLaw Bench 上达到 90.9%，是目前最高分
- 所有连接器和插件开源，企业管理员可在工作区设置中启用
- Claude 可直接在 Word、Outlook、Excel、PowerPoint 里工作，跨应用保持上下文
- 与 Free Law Project、Justice Technology Association 等合作推进法律服务可及性

这套工具的推出意味着 AI 在法律行业从「辅助写作」正式进入「与专业系统深度对接」的阶段，对律所、公司法务部门以及法律科技创业公司来说都是重要信号。
