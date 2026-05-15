# AI产品

## 一、How Claude Code works in large codebases: Best practices and where to start【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/how-claude-code-works-in-large-codebases-best-practices-and-where-to-start
**关键词：** Claude Code、企业部署、大型代码库、CLAUDE.md、Hooks、Skills、LSP、MCP
### 摘要
Anthropic 发布了"Claude Code at scale"系列的首篇文章，系统阐述了如何在百万行级别的大型代码库中规模化部署 Claude Code。

核心观点是：真正决定 Claude Code 性能的不是模型本身，而是围绕它构建的"生态体系"（harness）。文章详细介绍了5个扩展点：**CLAUDE.md**（每个会话自动加载的项目上下文）、**Hooks**（会话前后自动执行的脚本）、**Skills**（按需加载的专业知识）、**Plugins**（打包技能/hooks/MCP的安装包）、以及 **MCP Servers**（连接内部工具和数据源的通道）。另外还有两个重要能力：**LSP集成**（让Claude像IDE一样用符号级精度导航代码）和 **Subagents**（子智能体隔离执行探索性任务）。

文章还给出了3个规模化配置模式：让代码库对Claude可导航、主动维护CLAUDE.md以适配模型能力迭代、以及指定专人（Agent Manager）负责Claude Code的配置管理和推广部署。

这篇文章对大企业工程团队有直接参考价值——尤其是那些正在评估或已经部署了AI编码工具的组织。

---

## 二、The founder's playbook: Building an AI-native startup【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/the-founders-playbook
**关键词：** AI创业、创始人指南、MVP、产品市场契合、Agentic工作流
### 摘要
Anthropic 发布了一套面向AI原生创业者的实践手册，将创业生命周期重映射为四个阶段——Idea（创意验证）、MVP（最小可行产品）、Launch（发布）、Scale（规模化），并为每个阶段配上了AI驱动的练习、框架和提示词。

核心内容包括：如何用AI进行问题假设验证、竞争格局分析和客户发现；AI生成的MVP代码如何避免技术债务积累；如何区分真正的产品市场契合与早期炒作；以及"发布阶段操作系统"——用Agentic工作流替代创始人的重复性注意力投入。

文章还包含多个创始人案例研究（Ambral、Anything、Carta Healthcare、HumanLayer、Vulcan Technologies），以及一份详细的产品矩阵图，说明在创业各阶段何时使用Chat、Claude Cowork和Claude Code。适合从零开始构建AI原生公司的创始人和早期团队成员阅读。

---

## 三、PwC is deploying Claude to build technology, execute deals, and reinvent enterprise functions for clients【⭐⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/pwc-expanded-partnership
**关键词：** PwC、Anthropic、企业部署、Claude Code、Claude Cowork、保险核保、财务办公室、战略合作
### 摘要

Anthropic 与四大会计师事务所之一 **PwC（普华永道）** 宣布大幅扩展战略合作，推动 Claude 进入企业核心业务场景。这是目前公开信息中，Claude 在大型企业级部署中最深入的一次合作。

**合作的三个核心方向：**

1. **Agentic Technology Build（Agent 技术构建）**：PwC 的工程团队将用 **Claude Code** 为客户交付生产级软件，交付周期从季度压缩到数周。涉及金融、医药、医疗、消费等行业。
2. **AI-native Deal-making（AI 原生交易执行）**：PwC 正在用 Agent 改造并购交易的全流程——从尽职调查、价值创造到整合——让私募基金和企业买家的交易周期大幅压缩。
3. **Reinvention of Enterprise Function（企业职能再造）**：PwC 已经在财务、供应链、HR、网络安全等企业职能中规模化运行 Claude 驱动的系统，而不是跑概念验证。

**关键数字：**
- PwC 计划对其数十万名员工逐步推广 Claude Code 和 Claude Cowork，先从美国团队开始
- 双方将成立联合**卓越中心（Center of Excellence）**，并计划培训认证 **30,000 名 PwC 专业人员**使用 Claude
- PwC 正在组建新的业务部门 **Office of the CFO**（首席财务官办公室），以 Claude 技术为基础，专注受监管行业（银行、保险、医疗）的财务流程改造

**已在生产的落地案例：**
- **保险核保**：从 10 周缩短到 10 天，打开了以前经济上不可行的业务线
- **网络安全**：应急响应从数小时缩短到数分钟
- **大型机现代化**：COBOL 代码库规模翻倍，依然按时在预算内完成
- **HR 转型**：一周构建原型，两个月上线完整应用，每天处理数千笔交易
- **体育运营**：用 Agentic-first 方式重建了数字粉丝互动和体育管理运营
- **医疗健康**：Advocate Health（全美最大的医疗系统之一）已开始在 16.7 万名员工中推广 Claude

**这件事的意义：**
这份合作展示了 Claude 在企业级市场迈出的重要一步。PwC 同时扮演了
