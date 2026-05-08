# AI行业动态

## 一、Anthropic与SpaceX达成算力合作，覆盖30万GPU，同时大幅提升使用限额【⭐⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/higher-limits-spacex
**关键词**：Anthropic、SpaceX、Colossus 1、算力、Claude Code、API限额

### 摘要

Anthropic 宣布与 SpaceX 达成算力合作，获得 SpaceX Colossus 1 数据中心全部算力——超过300兆瓦、22万+NVIDIA GPU容量，本月内即可上线。这意味着 Claude Pro 和 Max 用户的性能瓶颈将得到显著缓解。

**同时生效的三项提升：**
1. Claude Code 的5小时速率限制——Pro/Max/Team/Enterprise 用户全部翻倍
2. 取消 Pro 和 Max 账户的峰时限制降低
3. Claude Opus 模型的 API 速率限制大幅提升

**Anthropic 的算力版图全景：**
- Amazon：最高5GW协议，2026年底接近1GW上线
- Google + Broadcom：5GW协议，2027年开始启用
- Microsoft + NVIDIA：包含300亿美元 Azure 容量
- Fluidstack：500亿美元美国 AI 基础设施投资
- SpaceX：30万+NVIDIA GPU，本月内上线
- 还在与 SpaceX 探讨开发多GW轨道AI算力

**国际化扩张：** 部分新增容量将部署在亚洲和欧洲，以满足金融、医疗、政府客户的合规和数据驻留要求。

---

## 二、Anthropic联合Blackstone/高盛等成立企业AI服务公司【⭐⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/enterprise-ai-services-company
**关键词**：Anthropic、Blackstone、Goldman Sachs、企业服务、系统集成

### 摘要

Anthropic 联合 Blackstone（黑石）、Hellman & Friedman、Goldman Sachs（高盛）成立一家新 AI 服务公司，面向中型企业（社区银行、区域制造商、医疗系统）提供 Claude 部署服务。该公司同时获得 General Atlantic、Leonard Green、Apollo、GIC、Sequoia Capital 等顶级资管机构注资。

**运作模式：**
典型合作从一个小团队开始，深入客户现场了解业务流程，然后由 Anthropic 应用AI工程师与合作方的工程团队一起，构建定制的 Claude 驱动系统。例如一家多站点医疗服务集团——医生每天花数小时在文书、编码、审批上——工程师会与临床医生和 IT 一起开发嵌入现有流程的工具。

**意义：** 这表明 Anthropic 意识到仅靠大型系统集成商（Accenture、Deloitte、PwC）服务不了广大中型企业市场。新公司填补了这一空白，而且由顶级资本背书，说明企业AI部署正在从"做不做"进入"怎么做"的新阶段。

---

## 三、Anthropic发布10个金融服务Agent模板【⭐⭐】
**来源：** Anthropic News
**链接：** https://www.anthropic.com/news/finance-agents
**关键词**：Anthropic、金融服务、Agent模板、Claude Cowork、Claude Code

### 摘要

Anthropic 针对金融服务行业一次性释放10个即用型 Agent 模板，涵盖投行、资管、合规、审计等场景。每个模板包含技能指令、数据连接器、以及子 Agent 的参考架构。

**10个Agent完整列表：**

研究和客户覆盖类：
1. **Pitch Builder**：生成目标清单、可比公司分析、起草Pitchbook
2. **Meeting Preparer**：会前准备客户和交易对手简报
3. **Earnings Reviewer**：读财报和电话会议记录，更新模型，标记与投研主题相关的变化
4. **Model Builder**：从财报/数据源创建和维护金融模型
5. **Market Researcher**：追踪行业和发行人动态，综合新闻/研报/中介研究

财务和运营类：
6. **Valuation Reviewer**：检查估值是否匹配可比公司和方法论
7. **General Ledger Reconciler**：对账总账科目，计算NAV
8. **Month-end Closer**：跑结账清单、准备分录、出具结账报告
9. **Statement Auditor**：审核财报一致性和完整性
10. **KYC Screener**：整理实体文件、审核来源文件、打包上报合规审查

这些模板可以当作 Claude Cowork/Claude Code 的插件运行（分析师桌面工具），也可以部署为 Claude Managed Agent（全自动后台运行）。Claude Opus 4.7 在 Vals AI 的 Finance Agent 排行榜以64.37%排名第一。

---

## 四、GPT-5.5发布，竞争格局再变：算力支出成关键壁垒【⭐⭐】
**来源：** The Batch
**链接：** https://www.deeplearning.ai/the-batch/issue-351/
**关键词**：GPT-5.5、OpenAI、Kimi K2.6、开源模型、AI气候、战略推理

### 摘要

DeepLearning.AI 的 The Batch 第351期除了 GPT-5.5（详见AI产品分类），还覆盖了：

**Kimi K2.6 领跑开源LLM：** 月之暗面（Moonshot AI）的 Kimi K2.6（6710亿参数MoE，每次激活370亿）在多个基准测试中超越 Llama 4.3（1万亿参数）、DeepSeek-V4、Qwen 4 Max 等。但开源模型与 GPT-5.5、Claude Opus 4.7、Gemini 3.1 Pro 仍有显著差距。

**AI能耗与气候承诺：** 随着 AI 基础设施投资暴涨（IEA预测到2027年AI用电量是2024年的12倍），谷歌、微软、亚马逊的气候承诺面临压力。谷歌2025年排放量比2019年上升了50.5%，微软因数据中心扩张放弃了部分地区碳中和目标。核能（SMR）成为科技巨头争夺的新资源——但商业化至少要到2030年代。

**战略推理差距：** 一项新研究比较了 LLM 和人类在战略资源分配任务上的表现——AI 在很多方面超越人类，但在需要"区分承诺与威胁"的场景中表现不佳，容易被误导。

---

## 五、Anthropic 开源安全工具 Petri 捐赠给社区【⭐】
**来源：** Anthropic Research
**链接：** https://www.anthropic.com/research/donating-open-source-petri
**关键词**：Anthropic、Petri、开源、AI安全、对齐

### 摘要

Anthropic 将其内部使用的开源对齐工具 Petri 捐赠给社区。Petri 是一个评估 AI 系统对齐性的自动化工具框架，之前主要用于 Anthropic 内部的安全测试。开源后可供其他 AI 团队和研究机构使用。

---

## 六、Anthropic Institute 发布政策重点领域【⭐】
**来源：** Anthropic Research
**链接：** https://www.anthropic.com/research/anthropic-institute-agenda
**关键词**：Anthropic Institute、AI政策、安全治理

### 摘要

Anthropic 新成立的研究机构 Anthropic Institute 发布了其政策研究和倡导的重点领域，涵盖 AI 安全标准、模型评估方法、产业治理框架等方向。这是 Anthropic 从技术研究向政策影响力扩展的标志性举措。

---

## 七、人们如何向 Claude 寻求个人指导【⭐】
**来源：** Anthropic Research
**链接：** https://www.anthropic.com/research/claude-personal-guidance
**关键词**：Anthropic、Claude、个人指导、用户行为研究

### 摘要

Anthropic 发布了一份关于用户如何向 Claude 寻求个人指导的社会影响研究。研究发现用户越来越多地将 Claude 当作个人顾问——从职业决策到人际关系到心理健康——并分析了这种使用模式对社会和个体决策的潜在影响。

---

## 八、Supabase Branching Without Git 默认可用【⭐】
**来源：** Supabase Blog
**链接：** https://supabase.com/blog/branching-without-git-is-now-the-default
**关键词**：Supabase、Branching、数据库、开发者体验

### 摘要

Supabase 宣布其无需 Git 的分支功能（Branching Without Git）现在默认可用。开发者可以在 Supabase 平台上为每个开发环境创建独立的数据库分支，无需管理 Git 仓库。配合刚刚发布的 @supabase/server，Supabase 正在系统性降低全栈开发的入门门槛。

---

## 九、Supabase 发布 OSSCAR 开源指数【⭐】
**来源：** Supabase Blog
**链接：** https://supabase.com/blog/introducing-osscar-index
**关键词**：Supabase、OSSCAR、开源指数

### 摘要

Supabase 推出 OSSCAR 指数（Open Source Security, Compliance, Activity, and Reliability Index），一个开源项目健康度评分系统。帮助企业在选择开源依赖时评估项目的安全性、合规性、活跃度和可靠性。
