作者：karpathy
地址：https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
# LLM Wiki

一种使用 LLM 构建个人知识库的模式。

A pattern for building personal knowledge bases using LLMs.

这是一个想法文件，设计为可直接复制粘贴到你自己的 LLM Agent 中（如 OpenAI Codex、Claude Code、OpenCode / Pi 等）。其目标是传达核心思想，但你的 Agent 会与你协作，把具体细节落实到位。

This is an idea file, it is designed to be copy pasted to your own LLM Agent (e.g. OpenAI Codex, Claude Code, OpenCode / Pi, or etc.). Its goal is to communicate the high level idea, but your agent will build out the specifics in collaboration with you.

## 核心思想

## The core idea

大多数人对 LLM 和文档的体验，看起来像 RAG：你上传一堆文件，LLM 在查询时检索相关片段，然后生成回答。这确实能工作，但 LLM 每次都要从头重新发现知识，没有积累。问一个需要综合五份文档才能回答的微妙问题，LLM==每次都得找到并拼凑相关片段。什么也没沉淀下来==
NotebookLM、ChatGPT 文件上传、以及大多数 RAG 系统都是这样运作的。

Most people's experience with LLMs and documents looks like RAG: you upload a collection of files, the LLM retrieves relevant chunks at query time, and generates an answer. This works, but the LLM is rediscovering knowledge from scratch on every question. There's no accumulation. Ask a subtle question that requires synthesizing five documents, and the LLM has to find and piece together the relevant fragments every time. Nothing is built up. NotebookLM, ChatGPT file uploads, and most RAG systems work this way.

这里的思路不同。LLM 不是在查询时从原始文档中检索，而是==**增量式地构建和维护一个持久化的 wiki** ==—— 一个==结构化的、相互链接的 ==markdown 文件集合，它位于你和原始资料之间。当你添加新资料时，LLM 不只是为后续检索建索引。它会读取资料，提取关键信息，并将其整合到现有 wiki 中 —— 更新实体页面、修订主题摘要、标注新数据与旧论述的矛盾之处、强化或挑战不断演进的综合观点。知识被编译一次，然后*保持更新*，而不是每次查询重新推导。

The idea here is different. Instead of just retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** — a structured, interlinked collection of markdown files that sits between you and the raw sources. When you add a new source, the LLM doesn't just index it for later retrieval. It reads it, extracts the key information, and integrates it into the existing wiki — updating entity pages, revising topic summaries, noting where new data contradicts old claims, strengthening or challenging the evolving synthesis. The knowledge is compiled once and then *kept current*, not re-derived on every query.


> [!question] 疑问
> 以什么样的形式标注出矛盾

这就是关键区别：**wiki 是一个持久化的、不断累积的产物。** 交叉引用已经做好了，矛盾已经标注出来了，综合观点已经反映了你读过的所有内容。每添加一个资料、每问一个问题，wiki 都会变得更丰富。

This is the key difference: **the wiki is a persistent, compounding artifact.** The cross-references are already there. The contradictions have already been flagged. The synthesis already reflects everything you've read. The wiki keeps getting richer with every source you add and every question you ask.

你永远不（或几乎不）自己写 wiki —— LLM 编写和维护所有内容。你负责策展资料、探索和提出好问题。LLM 做所有苦活 —— ==摘要、交叉引用、归档和整理==，这些才是让知识库长期有用的东西。实践中，我一边开着 LLM Agent，一边开着 Obsidian。LLM 根据我们的对话进行编辑，我实时浏览结果 —— 跟踪链接、查看图谱视图、阅读更新后的页面。Obsidian 是 IDE，LLM 是程序员，wiki 是代码库。

You never (or rarely) write the wiki yourself — the LLM writes and maintains all of it. You're in charge of sourcing, exploration, and asking the right questions. The LLM does all the grunt work — the summarizing, cross-referencing, filing, and bookkeeping that makes a knowledge base actually useful over time. In practice, I have the LLM agent open on one side and Obsidian open on the other. The LLM makes edits based on our conversation, and I browse the results in real time — following links, checking the graph view, reading the updated pages. Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase.

这可以应用于很多不同场景。举几个例子：

This can apply to a lot of different contexts. A few examples:

- **个人**：追踪你自己的目标、健康、心理、自我提升 —— 归档日记、文章、播客笔记，逐步构建关于你自己的结构化图景。
- **研究**：花几周或几个月深入研究一个主题 —— 阅读论文、文章、报告，逐步构建一个带有演进论点的综合性 wiki。
- **阅读一本书**：逐章归档，逐步建立人物、主题、情节线及其相互关联的页面。读完时你就有了一部丰富的伴读 wiki。想想像 [Tolkien Gateway](https://tolkiengateway.net/wiki/Main_Page) 这样的粉丝 wiki —— 数千个相互链接的页面，涵盖人物、地点、事件、语言，由志愿者社区多年建设而成。你可以在阅读时自己构建类似的东西，LLM 负责所有交叉引用和维护。
- **商业/团队**：由 LLM 维护的内部 wiki，信息源来自 Slack 讨论串、会议记录、项目文档、客户通话。可能有人工审核更新。wiki 保持最新，因为 LLM 做了团队中没人愿意做的维护工作。
- **竞品分析、尽职调查、旅行规划、课程笔记、爱好深度研究** —— 任何你随着时间积累知识并希望有组织而不是散落各处的场景。

- **Personal**: tracking your own goals, health, psychology, self-improvement — filing journal entries, articles, podcast notes, and building up a structured picture of yourself over time.
- **Research**: going deep on a topic over weeks or months — reading papers, articles, reports, and incrementally building a comprehensive wiki with an evolving thesis.
- **Reading a book**: filing each chapter as you go, building out pages for characters, themes, plot threads, and how they connect. By the end you have a rich companion wiki. Think of fan wikis like [Tolkien Gateway](https://tolkiengateway.net/wiki/Main_Page) — thousands of interlinked pages covering characters, places, events, languages, built by a community of volunteers over years. You could build something like that personally as you read, with the LLM doing all the cross-referencing and maintenance.
- **Business/team**: an internal wiki maintained by LLMs, fed by Slack threads, meeting transcripts, project documents, customer calls. Possibly with humans in the loop reviewing updates. The wiki stays current because the LLM does the maintenance that no one on the team wants to do.
- **Competitive analysis, due diligence, trip planning, course notes, hobby deep-dives** — anything where you're accumulating knowledge over time and want it organized rather than scattered.

## 架构

## Architecture

有三层：

There are three layers:

**原始资料** —— 你策展收集的源文档。文章、论文、图片、数据文件。这些是不可变的 —— LLM 从中读取但从不修改。这是你的事实来源。

**Raw sources** — your curated collection of source documents. Articles, papers, images, data files. These are immutable — the LLM reads from them but never modifies them. This is your source of truth.

**Wiki** —— 一个由 LLM 生成的 markdown 文件目录。摘要、实体页面、概念页面、对比、概览、综合论述。LLM 完全拥有这一层。它创建页面，在新资料到来时更新页面，维护交叉引用，保持一切一致。你阅读它；LLM 编写它。

**The wiki** — a directory of LLM-generated markdown files. Summaries, entity pages, concept pages, comparisons, an overview, a synthesis. The LLM owns this layer entirely. It creates pages, updates them when new sources arrive, maintains cross-references, and keeps everything consistent. You read it; the LLM writes it.

**Schema** —— 一个文档（如 Claude Code 的 CLAUDE.md 或 Codex 的 AGENTS.md），告诉 LLM wiki 如何组织、有哪些约定、以及在摄取资料、回答问题或维护 wiki 时遵循什么工作流。这是关键的配置文件 —— 它使 LLM 成为有纪律的 wiki 维护者，而非通用聊天机器人。你随 LLM 一起共同演进这个文件，在这个过程中逐步摸索出适合你领域的方式。

**The schema** — a document (e.g. CLAUDE.md for Claude Code or AGENTS.md for Codex) that tells the LLM how the wiki is structured, what the conventions are, and what workflows to follow when ingesting sources, answering questions, or maintaining the wiki. This is the key configuration file — it's what makes the LLM a disciplined wiki maintainer rather than a generic chatbot. You and the LLM co-evolve this over time as you figure out what works for your domain.

## 操作

## Operations

**摄取。** 你把新资料放入原始资料集，告诉 LLM 去处理它。一个示例流程：LLM 读取资料，与你讨论关键要点，在 wiki 中撰写摘要页面，更新索引，更新整个 wiki 中相关的实体和概念页面，并在日志中追加一条记录。单份资料可能涉及 10-15 个 wiki 页面的更新。我个人偏好一次摄取一份资料并保持参与 —— 我阅读摘要、检查更新，并引导 LLM 关注哪些重点。但你也可以在有较少监督的情况下批量摄取多份资料。由你来摸索适合你风格的工作流，并将其记录在 schema 中供后续会话使用。

**Ingest.** You drop a new source into the raw collection and tell the LLM to process it. An example flow: the LLM reads the source, discusses key takeaways with you, writes a summary page in the wiki, updates the index, updates relevant entity and concept pages across the wiki, and appends an entry to the log. A single source might touch 10-15 wiki pages. Personally I prefer to ingest sources one at a time and stay involved — I read the summaries, check the updates, and guide the LLM on what to emphasize. But you could also batch-ingest many sources at once with less supervision. It's up to you to develop the workflow that fits your style and document it in the schema for future sessions.

**查询。** 你对 wiki 提问。LLM 搜索相关页面，读取它们，综合后给出带引用的回答。回答可以根据问题类型采取不同形式 —— markdown 页面、对比表格、幻灯片（Marp）、图表（matplotlib）、画布。重要的洞察：**好的回答可以归档回 wiki 成为新页面。** 你要求的一个对比、一份分析、一个你发现的关联 —— 这些都有价值，不应该消失在聊天记录里。这样你的探索也能像摄取的资料一样在知识库中不断积累。

**Query.** You ask questions against the wiki. The LLM searches for relevant pages, reads them, and synthesizes an answer with citations. Answers can take different forms depending on the question — a markdown page, a comparison table, a slide deck (Marp), a chart (matplotlib), a canvas. The important insight: **good answers can be filed back into the wiki as new pages.** A comparison you asked for, an analysis, a connection you discovered — these are valuable and shouldn't disappear into chat history. This way your explorations compound in the knowledge base just like ingested sources do.

**检查。** 定期让 LLM 对 wiki 做健康检查。查找：页面之间的矛盾、已被新资料取代的过时论述、没有入站链接的孤立页面、被提及但缺少专属页面的重要概念、缺失的交叉引用、可以通过网络搜索填补的数据空白。LLM 擅长建议新的调查问题和新的资料来源。这能保持 wiki 在增长过程中健康有序。

**Lint.** Periodically, ask the LLM to health-check the wiki. Look for: contradictions between pages, stale claims that newer sources have superseded, orphan pages with no inbound links, important concepts mentioned but lacking their own page, missing cross-references, data gaps that could be filled with a web search. The LLM is good at suggesting new questions to investigate and new sources to look for. This keeps the wiki healthy as it grows.

## 索引与日志

## Indexing and logging

两个特殊文件帮助 LLM（和你）在 wiki 不断增长时导航。它们有不同用途：

Two special files help the LLM (and you) navigate the wiki as it grows. They serve different purposes:

**index.md** 是内容导向的。它是 wiki 中所有内容的目录 —— 每个页面带链接、一行摘要，以及可选的元数据如日期或资料来源数量。按类别组织（实体、概念、资料等）。LLM 在每次摄取时更新它。回答查询时，LLM 先读索引来找到相关页面，然后深入那些页面。这在中型规模（~100 份资料，~数百个页面）下出奇地好用，避免了基于嵌入的 RAG 基础设施。

**index.md** is content-oriented. It's a catalog of everything in the wiki — each page listed with a link, a one-line summary, and optionally metadata like date or source count. Organized by category (entities, concepts, sources, etc.). The LLM updates it on every ingest. When answering a query, the LLM reads the index first to find relevant pages, then drills into them. This works surprisingly well at moderate scale (~100 sources, ~hundreds of pages) and avoids the need for embedding-based RAG infrastructure.

**log.md** 是时间顺序的。它是一个只追加的记录，记录什么时间发生了什么 —— 摄取、查询、检查。一个实用建议：如果每条记录都以一致的前缀开头（如 `## [2026-04-02] 摄取 | 文章标题`），日志就可以用简单的 unix 工具解析 —— `grep "^## \[" log.md | tail -5` 给你最近 5 条记录。日志让你看到 wiki 演进的时间线，也帮助 LLM 理解最近做了什么。

**log.md** is chronological. It's an append-only record of what happened and when — ingests, queries, lint passes. A useful tip: if each entry starts with a consistent prefix (e.g. `## [2026-04-02] ingest | Article Title`), the log becomes parseable with simple unix tools — `grep "^## \[" log.md | tail -5` gives you the last 5 entries. The log gives you a timeline of the wiki's evolution and helps the LLM understand what's been done recently.

## 可选：CLI 工具

## Optional: CLI tools

到了某个阶段，你可能想构建一些小工具，帮助 LLM 更高效地操作 wiki。最明显的就是 wiki 页面的搜索引擎 —— 在小规模时索引文件就够了，但随着 wiki 增长，你会需要真正的搜索。[qmd](https://github.com/tobi/qmd) 是一个不错的选择：它是一个本地 markdown 文件搜索引擎，具有混合 BM25/向量搜索和 LLM 重排序功能，全部在设备端运行。它既有 CLI（所以 LLM 可以调 shell 用），也有 MCP 服务器（所以 LLM 能作为原生工具使用）。你也可以自己构建更简单的东西 —— 随着需求出现，LLM 可以帮你 vibe-code 一个朴素的搜索脚本。

At some point you may want to build small tools that help the LLM operate on the wiki more efficiently. A search engine over the wiki pages is the most obvious one — at small scale the index file is enough, but as the wiki grows you want proper search. [qmd](https://github.com/tobi/qmd) is a good option: it's a local search engine for markdown files with hybrid BM25/vector search and LLM re-ranking, all on-device. It has both a CLI (so the LLM can shell out to it) and an MCP server (so the LLM can use it as a native tool). You could also build something simpler yourself — the LLM can help you vibe-code a naive search script as the need arises.

## 小贴士与技巧

## Tips and tricks

- **Obsidian Web Clipper** 是一个浏览器扩展，能将网页文章转换为 markdown。非常适合快速将资料收集到你的原始资料集中。
- **下载图片到本地。** 在 Obsidian 设置 → 文件和链接中，将"附件文件夹路径"设为一个固定目录（如 `raw/assets/`）。然后在设置 → 快捷键中，搜索"下载"找到"下载当前文件的附件"并绑定一个快捷键（如 Ctrl+Shift+D）。剪藏文章后，按快捷键，所有图片就下载到本地磁盘了。这是可选的但很有用 —— 它让 LLM 能直接查看和引用图片，而不是依赖可能失效的 URL。注意，LLM 无法一次性地原生读取带内联图片的 markdown —— 变通方案是让 LLM 先读文本，然后分别查看部分或全部引用的图片来获取额外上下文。有点笨拙但够用。
- **Obsidian 的图谱视图** 是查看 wiki 形态的最佳方式 —— 什么和什么相连，哪些页面是枢纽，哪些是孤立的。
- **Marp** 是一种基于 markdown 的幻灯片格式。Obsidian 有对应插件。适合直接从 wiki 内容生成演示文稿。
- **Dataview** 是一个在页面 frontmatter 上跑查询的 Obsidian 插件。如果你的 LLM 为 wiki 页面添加 YAML frontmatter（标签、日期、资料数量），Dataview 可以生成动态表格和列表。
	
  > [!question] 
> 这里是说用wiki来管理嘛？

- wiki 就是 markdown 文件的 git 仓库。你免费获得版本历史、分支和协作功能。

- **Obsidian Web Clipper** is a browser extension that converts web articles to markdown. Very useful for quickly getting sources into your raw collection.
- **Download images locally.** In Obsidian Settings → Files and links, set "Attachment folder path" to a fixed directory (e.g. `raw/assets/`). Then in Settings → Hotkeys, search for "Download" to find "Download attachments for current file" and bind it to a hotkey (e.g. Ctrl+Shift+D). After clipping an article, hit the hotkey and all images get downloaded to local disk. This is optional but useful — it lets the LLM view and reference images directly instead of relying on URLs that may break. Note that LLMs can't natively read markdown with inline images in one pass — the workaround is to have the LLM read the text first, then view some or all of the referenced images separately to gain additional context. It's a bit clunky but works well enough.
- **Obsidian's graph view** is the best way to see the shape of your wiki — what's connected to what, which pages are hubs, which are orphans.
- **Marp** is a markdown-based slide deck format. Obsidian has a plugin for it. Useful for generating presentations directly from wiki content.
- **Dataview** is an Obsidian plugin that runs queries over page frontmatter. If your LLM adds YAML frontmatter to wiki pages (tags, dates, source counts), Dataview can generate dynamic tables and lists.
- The wiki is just a git repo of markdown files. You get version history, branching, and collaboration for free.

## 为什么这能行

## Why this works

维护知识库的繁琐之处不在于阅读或思考 —— 而在于整理。更新交叉引用、保持摘要的时效性、标注新数据与旧论述的矛盾、维护几十个页面之间的一致性。人类放弃 wiki 是因为维护负担的增长速度超过了价值。LLM 不会无聊、不会忘记更新某个交叉引用、一次能处理 15 个文件。wiki 得以持续维护，因为维护成本接近零。

The tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping. Updating cross-references, keeping summaries current, noting when new data contradicts old claims, maintaining consistency across dozens of pages. Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass. The wiki stays maintained because the cost of maintenance is near zero.

人的工作是策展资料、引导分析、提出好问题、思考这一切意味着什么。LLM 的工作是其余所有事情。

The human's job is to curate sources, direct the analysis, ask good questions, and think about what it all means. The LLM's job is everything else.

这个想法在精神上与 Vannevar Bush 的 Memex（1945）相关 —— 一个个人策展的知识仓库，文档之间有关联轨迹。Bush 的愿景更接近这个而非后来互联网的样子：私人的、主动策展的，文档之间的连接与文档本身同等重要。他没能解决的部分是谁来做维护。LLM 接手了这件事。

The idea is related in spirit to Vannevar Bush's Memex (1945) — a personal, curated knowledge store with associative trails between documents. Bush's vision was closer to this than to what the web became: private, actively curated, with the connections between documents as valuable as the documents themselves. The part he couldn't solve was who does the maintenance. The LLM handles that.


## 说明

## Note

本文档故意保持抽象。它描述的是思想，不是具体实现。确切的目录结构、schema 约定、页面格式、工具 —— 所有这些都取决于你的领域、你的偏好和你选择的 LLM。上述所有内容都是可选和模块化的 —— 选有用的，忽略不需要的。例如：你的资料可能只有文字，所以你完全不需要图片处理。你的 wiki 可能足够小，索引文件就够了，不需要搜索引擎。你可能不关心幻灯片，只想要 markdown 页面。你可能想要一套完全不同的输出格式。正确的使用方式是把它分享给你的 LLM Agent，一起协作实例化一个适合你需求的版本。这份文档的唯一职责是传达这个模式。你的 LLM 能搞定其余的。

This document is intentionally abstract. It describes the idea, not a specific implementation. The exact directory structure, the schema conventions, the page formats, the tooling — all of that will depend on your domain, your preferences, and your LLM of choice. Everything mentioned above is optional and modular — pick what's useful, ignore what isn't. For example: your sources might be text-only, so you don't need image handling at all. Your wiki might be small enough that the index file is all you need, no search engine required. You might not care about slide decks and just want markdown pages. You might want a completely different set of output formats. The right way to use this is to share it with your LLM agent and work together to instantiate a version that fits your needs. The document's only job is to communicate the pattern. Your LLM can figure out the rest.