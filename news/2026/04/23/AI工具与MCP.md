# AI工具与MCP

## 一、Building agents that reach production systems with MCP【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/building-agents-that-reach-production-systems-with-mcp
**关键词**：MCP、Agent、工具调用、上下文效率、生产部署

### 摘要

Agent 能做多少事，本质上取决于它能连接多少系统。Anthropic 这篇博客梳理了三种让 Agent 连接外部系统的路径——直连 API、CLI、以及 MCP，并解释了为什么生产级 Agent 最终都走向 MCP。

**三种连接方式的适用场景**

直接 API 调用：适合 1 对 1 的简单集成，但规模上来后维护成本高。每个 Agent-服务对都是独立定制，认证、工具描述、边界情况各有一套，形成 M×N 的维护噩梦。

CLI：轻量快速，适合本地开发环境。但问题在于它依赖本地容器，无法延伸到移动端、Web 端和云端服务，且认证通常靠磁盘上的凭证文件，不适合需要安全隔离的场景。

MCP（Model Context Protocol）：作为协议层，它把认证、发现、语义都标准化了。一个远程 MCP Server 可以对接任何兼容客户端（Claude、ChatGPT、Cursor、VS Code 等），在任何部署环境都能跑。

**MCP 现状**

MCP SDK 月下载量已突破 3 亿次（年初才 1 亿），企业级采用和主流 Agent 平台都在用。MCP 已经支撑了 Claude Cowork、Claude Managed Agents、Claude Code Channels 等核心产品。

**构建优秀 MCP Server 的设计模式**

1. **构建远程 Server**：远程配置才能覆盖 Web、移动端和云端 Agent，是唯一真正的分发方式。

2. **按意图分组工具，而非 API 镜像**：不要把 API 一对一地包装成工具。要围绕"用户意图"聚合，一个 `create_issue_from_thread` 工具比 `get_thread + parse_messages + create_issue + link_attachment` 四个工具好用的多。

3. **大表面 API 用代码编排**：如果你的服务有数百种操作（如 Cloudflare、AWS、Kubernetes），意图分组覆盖不过来。正确做法是暴露一个接受代码的薄工具层，Agent 写脚本在沙盒里执行，Cloudflare 的 MCP Server 就是标杆——两个工具（search + execute）覆盖约 2500 个端点，只需约 1K token。

4. **用 MCP Apps 交付富语义**：MCP Apps 允许工具返回可交互界面（图表、表单、仪表盘），直接渲染在对话界面里。用了 MCP Apps 的 Server，用户粘性明显更高。

5. **用标准化认证（CIMD）**：MCP spec 支持 CIMD（Client ID Metadata Documents），实现快速首次认证，减少重复授权弹窗。配合 Claude Managed Agents 的 Vaults，OAuth token 注册一次就能在会话生命周期内自动注入和刷新，无需自己搭密钥存储。

**让 MCP Client 更省上下文**

- **工具搜索（Tool Search）**：不在启动时加载全部工具定义，而是在运行时按需从目录拉取。测试显示 Token 消耗降低 85%+，同时选择准确性基本不变。

- **代码编排工具调用（Programmatic Tool Calling）**：工具结果在代码沙盒里处理（循环、过滤、聚合），只有最终输出进入上下文。复杂多步工作流 Token 消耗再降约 37%。

**MCP + Skills 的配合**

MCP 给你外部系统的工具和数据，Skills 教 Agent 怎么用这些工具完成任务，两者互补。最佳实践是把 Skills 和 MCP Server 打包成 Plugin（如 Cowork 的 Data Plugin：10 个 Skills + 8 个 MCP Server，覆盖 Snowflake、Databricks、BigQuery 等）。

MCP 社区还在推进从 Server 直接分发 Skills 的协议扩展，目标是让客户端自动继承相关专业知识，随 API 版本一同演进。

**核心结论**

生产级 Agent 走向云端是大趋势，MCP 是那个"复利层"——今天你构建的远程 Server，明天就能被所有兼容客户端使用，无需额外开发。而这个生态越丰富，每个集成投入的回报就越高。
