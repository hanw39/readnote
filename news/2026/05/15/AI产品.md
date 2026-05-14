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
