# AI产品

## 一、Claude集成Microsoft 365全线产品：Excel/PPT/Word GA，Outlook公测【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/collaborate-with-claude-across-excel-powerpoint-word-and-outlook
**关键词**：Claude、Microsoft 365、Excel、PowerPoint、Word、Outlook、企业级

### 摘要

Claude 正式全面集成 Microsoft 365 办公套件——Claude for Excel、PowerPoint、Word 转为 GA（正式可用），Claude for Outlook 进入公开测试。这意味着你可以在日常办公软件里直接跟 Claude 对话，不用切换到网页或独立客户端。

**核心卖点：一条对话跨四个应用**
Claude 在 Office 应用之间保持上下文贯通：在 Outlook 里处理邮件 → 点开附件在Word里起草备忘录 → 在Excel搭分析模型 → 做成PPT演示文稿，全程不需要重新解释你在做什么。如果在 Excel 里改了一个数字，PPT里的图表和Word文档的数字会自动更新。

**Claude for Outlook：**
可以帮你分类收件箱——哪些需要你亲自回复、哪些它帮你起草、哪些是垃圾。回复以草稿形式出现在 Outlook 撰写窗口，收件人、主题和正文都填好了。日历邀请可以检查参会者忙闲状态。所有内容需要你审核后才能发出。

**企业部署：**
IT 管理员可以通过 Microsoft AppSource 统一部署，支持 OpenTelemetry 追踪每个应用中的 prompts 和 tool calls，也支持 Analytics API 按用户、按应用、按天拆分使用数据。企业还可以选择通过自己的 LLM Gateway 路由到 AWS Bedrock、GCP Vertex AI 或 Microsoft Foundry 上运行的 Claude 模型。

**Significance：** 这不是简单的"加个插件"，而是 AI 助手深度嵌入办公流程的标志性事件。Claude 从一个聊天窗口变成了 Excel 里的公式助手、PPT里的设计搭档、Word里的写作搭档——而且对话语境跨应用共享。这是对 Microsoft 365 Copilot 最直接的挑战。

---

## 二、Claude Managed Agents 重大更新：Dreaming、Outcomes、多Agent编排【⭐⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/new-in-claude-managed-agents
**关键词**：Anthropic、Managed Agents、Dreaming、Outcomes、多Agent编排、Agentic AI

### 摘要

Anthropic 为 Claude Managed Agents 推出三项重大能力，目标是让 Agent 能自我改进、自我审核、并行工作。

**1. Dreaming（梦境，研究预览版）：**
Agent 在空闲时回顾之前的会话和记忆库，提取模式、修复记忆、跨 Agent 共享学习。你可以选择让 dreaming 自动更新记忆，或者审核后再应用。Harvey（法律AI公司）用了 dreaming 后，任务完成率提升了约6倍。

**2. Outcomes（成果评估）：**
你写一个"什么算好"的评分标准，Agent 完成后由独立的 grader（评测器）用独立的上下文窗口评分——避免 Agent 自己的推理影响自我评价。不达标就自动重做。内部测试显示 outcomes 让任务成功率提升最多10个百分点，docx 生成质量+8.4%，pptx +10.1%。

**3. 多Agent编排：**
主 Agent 把大任务拆成小块，分给不同专业 Agent 并行处理——比如一个调查主Agent可以同时派出子Agent去查部署历史、错误日志、指标和工单。所有子Agent在共享文件系统上并行工作，事件持久化，每个Agent都能记住自己做了什么。进度可以在 Claude Console 里全链路追踪。

**案例：**
- Netflix 的平台团队用多Agent编排并行分析数百个构建的日志，只把值得关注的模式呈报给人类
- Every 的 Spiral 写作工具让 Haiku 版做主Agent接需求，Opus 版做子Agent写草稿，多份草稿并行生成

---

## 三、GPT-5.5 发布：新SOTA但更爱胡说八道【⭐⭐⭐】
**来源：** The Batch
**链接：** https://www.deeplearning.ai/the-batch/issue-351/
**关键词**：OpenAI、GPT-5.5、GPT-5.5 Pro、推理、Hallucination、API

### 摘要

OpenAI 发布 GPT-5.5，闭源视觉语言模型，针对 Agent 编程、Computer Use 和知识工作优化。GPT-5.5 Pro 版本支持推理 token 并行处理。

**关键指标：**
- 最大输入：API 100万token / Codex 40万token，最大输出12.8万token
- 支持5级推理强度（xhigh/high/medium/low/none）
- 新特性：Tool Search（按需加载工具，不用一次全塞进 prompt）
- Codex独占Fast模式：1.5倍速度，2.5倍价格

**性能表现：**
- Artificial Analysis 智能指数 60分，领先 Claude Opus 4.7（57）和 Gemini 3.1 Pro（57）
- ARC-AGI-2 85.0%（$1.87/task），击败 Gemini 3 Deep Think 84.6%（$13.62/task）——性价比大幅提升
- Terminal-Bench 2.0 SOTA、SWE-Bench Verified SOTA

**但是：更会胡说了。** OpenAI 披露 GPT-5.5 在倾向性评估（Preference Eval）上表现不如 GPT-5.4，尤其是在"知道不知道"这件事上——模型更倾向于自信地回答错误答案。这是当前推理模型的一个共性趋势：推理能力越强，幻觉越难检测。

**价格：** GPT-5.5 API $5/$0.50/$30（输入/缓存/输出），比 GPT-5.4 贵约一倍；GPT-5.5 Pro $30/$180（输入/输出，无缓存折扣）

---

## 四、Claude for Creative Work：连接创意工具生态【⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/claude-for-creative-work
**关键词**：Claude、创意工具、Ableton、Adobe、Blender、SketchUp、3D建模、Connector

### 摘要

Anthropic 发布一系列针对创意行业的新 connectors，让 Claude 能直接操作专业创意工具。覆盖领域从音频制作到3D建模到VJ现场表演：

- **Ableton**：Claude 能基于官方文档回答 Live/Push 的使用问题
- **Adobe（创意方向）**：连接 50+ 款 Creative Cloud 应用，包括 Photoshop、Premiere、Express
- **Affinity by Canva**：自动批量调整图片、重命名图层、导出文件
- **Autodesk Fusion**：通过对话创建和修改3D模型
- **Blender**：自然语言接口连接 Blender Python API，可调试场景、批量修改对象
- **Resolume Arena/Wire**：VJ和现场视觉艺术家实时控制
- **SketchUp**：用自然语言描述房间/家具/概念，直接在 SketchUp 打开编辑
- **Splice**：在 Claude 内搜索免版税采样库

Claude Design（Anthropic Labs 新产品）可以把设计的软件体验原型导出到 Canva。Claude Code 还能帮创意人员写脚本、插件、生成系统——比如自定义着色器、程序动画、参数化模型。

---

## 五、Windsurf 集成 Devin Review：代码审查Agent【⭐⭐】
**来源：** Windsurf Changelog
**链接：** https://windsurf.com/blog/devin-review-windsurf
**关键词**：Windsurf、Devin Review、代码审查、AI Agent

### 摘要

Windsurf（原 Codeium 推出的 AI IDE）将 Cognition 的 Devin Review 能力集成进编辑器，让代码审查变成全自动流程。开发者可以一键让 Devin Review 扫描 PR 级别的变更，生成详细的审查意见和修复建议。

---

## 六、Claude Security 公开测试版发布【⭐⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/claude-security-public-beta
**关键词**：Claude Security、代码安全、漏洞扫描、Opus 4.7、企业级

### 摘要

Claude Security 从研究预览转为公开测试，所有 Claude Enterprise 用户可用。Claude Security（之前叫 Claude Code Security）能扫描整个代码仓库，像安全研究员一样推理代码中的漏洞——不是靠规则模式匹配，而是理解文件之间的交互和数据流。

**关键能力：**
- 多阶段校验管道：每个发现独立验证后再交给安全分析师，降低误报率
- 置信度评分：每个漏洞附有可信度评级
- 生成修复补丁：可直接在 Claude Code on the Web 中打开修复
- 支持定时扫描和定向扫描

已经过数百家企业测试，多名用户反馈"从扫描到修复补丁一次性完成"。Opus 4.7 驱动的扫描能力也被 CrowdStrike、Palo Alto Networks、SentinelOne、Wiz 等安全工具集成。

---

## 七、Grok 多项产品更新：Imagine质量模式、Connectors、自定义语音【⭐⭐】
**来源：** xAI News
**链接：** https://x.ai/news/grok-imagine-quality-mode
**关键词**：xAI、Grok、Imagine、Connectors、语音

### 摘要

xAI 近期推出多项 Grok 产品更新：
- **Grok Imagine 质量模式 API**：图片生成质量提升，支持更精细的控制
- **Connectors 上线 Grok Web**：Grok 可以连接外部数据源和工具，类似 Claude 的 Connector 模式
- **自定义语音和语音库**：用户可以创建自己的语音模型，Grok 语音库新增更多预设声音

---

## 八、@supabase/server 发布：服务端开发的样板终结者【⭐⭐】
**来源：** Supabase Blog
**链接：** https://supabase.com/blog/introducing-supabase-server
**关键词**：Supabase、@supabase/server、Edge Functions、后端开发、TypeScript

### 摘要

Supabase 发布 `@supabase/server`（公开测试版），一个处理服务端样板代码的 TypeScript 包。它自动处理：auth 验证、客户端初始化、请求上下文、CORS——开发者只需声明谁能调用端点。

**核心设计：**
```typescript
Deno.serve(
  withSupabase({ auth: 'user' }, async (req, ctx) => {
    const { data } = await ctx.supabase.from('todos').select()
    return Response.json(data)
  })
)
```

`ctx` 对象包含两个预配客户端：`ctx.supabase`（用户级，自动遵循 RLS）和 `ctx.supabaseAdmin`（管理员级，使用 service role）。支持 Edge Functions、Vercel Functions、Cloudflare Workers、Hono 和 Bun。

Supabase 分析了 25,000 个已部署的 Edge Functions，发现每个函数都在重复同样的认证/客户端创建/CORS 代码。`@supabase/server` 就是为了消灭这些重复。

---

## 九、Claude API Skill 嵌入 CodeRabbit/JetBrains/Resolve AI/Warp【⭐】
**来源：** Claude Blog
**链接：** https://claude.com/blog/claude-api-skill
**关键词**：Claude API Skill、CodeRabbit、JetBrains、Warp、开发者工具

### 摘要

Claude 的 API Skill 从 Claude Code 扩展到更多开发者工具。CodeRabbit、JetBrains、Resolve AI、Warp 现在都内置了这个技能，让开发者可以在各自工具里直接获得 Claude API 的最佳实践——包括 prompt caching 优化、模型迁移指南、Agent 模式选择等。

例如在 JetBrains 里让 Claude 帮忙升级到 Opus 4.7，skill 会自动更新模型引用、把 manual thinking 改成 adaptive thinking、清理过时参数。

---

## 十、ghostty 离开 GitHub：18年重度用户正式告别【⭐】
**来源：** Mitchell Hashimoto
**链接：** https://mitchellh.com/writing/ghostty-leaving-github
**关键词**：Ghostty、GitHub、Mitchell Hashimoto、开源、代码托管

### 摘要

Mitchell Hashimoto（HashiCorp 联合创始人、Ghostty 终端模拟器作者）宣布 Ghostty 项目将离开 GitHub。他是 GitHub 2008年2月第1299号用户，18年来每天打开 GitHub 多次。但他记录了一个月的"X"日记——每天只要 GitHub 故障影响工作就打一个X——几乎每天都有。最近的大规模 Elasticsearch 故障（4月27日）是导火索。

Ghostty 将在未来几个月公布迁移目标（可能是 commercial 或 FOSS 方案），当前 URL 保留只读镜像。Mitchell 的个人项目和其他工作暂时保留在 GitHub。
