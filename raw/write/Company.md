
## Scale AI

**一句话**：把「给 AI 喂高质量数据」做成生意的公司——数据标注与评估起家，如今是大模型训练数据、评估基准（如 SWE-bench Pro）的重要供应商。

**命名含义**
- Scale = 规模化。寓意把「数据标注/评估」这件原本依赖人力、难以规模化的事，用平台+众包+工具链做成可大规模交付的服务。

**2025 年的关键转折：Meta 入股**
- 2025 年 6 月，Meta 对 Scale AI 投资约 **143 亿美元**，取得显著少数股权，投后估值约 **290 亿美元**。
- 这笔交易实质是「投资 + 挖人」：创始人兼 CEO Alexandr Wang（时年 28 岁）带队加入 Meta，主导其「超级智能（superintelligence）」实验室。采用入股而非整体收购的结构，部分是为了规避反垄断审查。
- Wang 离开后，原首席战略官 **Jason Droege** 接任 CEO（先为临时 CEO，后转正）。他公开否认了「Scale 在 Meta 交易后逐渐收缩」的说法，强调公司仍在运营和增长。

 **SWE-bench Pro** 就是由 Scale AI 维护的评估基准；Scale 也运营公开 leaderboard。这正是它「数据 + 评估」核心业务的体现。

## Cognition

**一句话**：AI 编程公司，做出自主软件工程师 Agent「Devin」；本笔记里的 FrontierCode (Diamond) 由它发布。

**基本情况**
- 主打产品 Devin——号称「自主 AI 软件工程师」，能端到端接管编码任务，曾成为高盛的首个「AI 员工」。
- 2025 年 7 月收购了 AI 编程工具公司 Windsurf；之后融资约 5 亿美元，估值接近 100 亿美元。

**命名含义**：Cognition = 认知。寓意让 AI 具备工程师式的「认知/推理」能力来写代码。

**关联基准**：FrontierCode (Diamond)。

## OpenAI

**一句话**：ChatGPT、GPT 系列模型的开发者；本笔记里的 GDPval、HealthBench 都由它发布。

**基本情况**
- 2015 年成立，旧金山。先后推出 GPT 系列、ChatGPT、o 系列推理模型等，是当前最主流的前沿模型实验室之一。
- 评估方向上开源了 simple-evals 等评测代码，并发布 GDPval（经济价值任务）、HealthBench（医疗）等面向真实场景的基准。

**命名含义**：OpenAI = Open + AI，初衷强调「开放的人工智能研究」（尽管后期模型转向闭源）。

**关联基准**：GDPval-AA、HealthBench Professional。

## Anthropic

**一句话**：Claude 系列模型的开发者，主打 AI 安全；本笔记里的 BioMysteryBench 由它发布。

**基本情况**
- 由前 OpenAI 成员创立，以「AI 安全 / 对齐」为核心理念，提出 Constitutional AI 等方法。
- 主力产品是 Claude 系列大模型。出于安全考虑，BioMysteryBench 只公开样本、完整集不公开。

**命名含义**：Anthropic = 取自希腊语 anthropos（人）词根，对应「关注 AI 对人类影响」的定位。

**关联基准**：BioMysteryBench。

## Zapier

**一句话**：老牌「自动化工作流」SaaS 公司，把上千款 App 用「触发器→动作」连起来；本笔记里的 AutomationBench 由它发布。

**基本情况**
- 创立于 2011 年，核心产品让非程序员也能用「if this then that」式规则把各类 App 串成自动化流程。
- 2026 年 4 月发布 AutomationBench，衡量 Agent 完成真实自动化工作流的能力，贴近自家产品场景。

**命名含义**：Zapier 源自「Zap」——平台里一条自动化流程就叫一个 Zap，词感上像「啪一下自动搞定」。

**关联基准**：AutomationBench。

## Andon Labs

**一句话**：YC 背景的 AI 评估/安全公司，主题是「无人在环的自主组织」；本笔记里的 Blueprint-Bench 由它发布。

**基本情况**
- 主张研究 Agent 在长周期、少人工干预下的真实表现，代表作 Vending-Bench（让 Agent 长期经营一台虚拟自动售货机，考查长程一致性），甚至在旧金山真租门面让 AI 实际运营。
- Blueprint-Bench 则考查空间推理——根据照片/描述重建建筑平面图。

**命名含义**：Andon = 取自精益生产的「安灯」系统（产线出问题拉灯报警），呼应其对「自主系统何时该求助/暴露问题」的关注。

**关联基准**：Blueprint-Bench 2。

## Epoch AI

**一句话**：专注 AI 进展研究与评测的机构，跟踪算力、数据、模型能力趋势；本笔记里的 FrontierMath 由它发布。

**基本情况**
- 以「量化分析 AI 发展趋势」著称，发布大量关于训练算力、数据规模、模型能力增长的研究与数据集。
- 评估方向上发布 FrontierMath——数学家原创、保密、可自动核验的高级数学推理基准，难到连前沿模型与数学博士都常被难住。

**命名含义**：Epoch = 训练里的「轮次」，也指「纪元/时代」，呼应其追踪 AI 时代演进的定位。

**关联基准**：FrontierMath (Tier 1–4)。

## Google DeepMind

**一句话**：Google 旗下的前沿 AI 实验室，Gemini 系列模型的开发者；本笔记里的 IMOAnswerBench（IMO-Bench 套件）由它发布。

**基本情况**
- 由 DeepMind 与 Google Brain 合并而来，主力产品是 Gemini 系列大模型，在数学、科学推理方向投入很深。
- 发布 IMO-Bench 套件（含只判答案的 IMOAnswerBench 与评证明的 IMO-ProofBench），由 IMO 奖牌得主参与设计。

**命名含义**：DeepMind = 深度（学习）+ 心智，寓意构建具备智能的系统。

**关联基准**：IMOAnswerBench。

## Mercor

**一句话**：做 AI 人才评估/数据的公司，推出 APEX 系列「真实职业长程任务」基准。

**基本情况**
- APEX 系列含 480 个贴近真实专业工作的长程任务，考查 Agent 的多步推理与持续执行，另有 APEX-SWE 软件工程变体。

**命名含义**：Apex = 顶点/巅峰，寓意衡量能力上限。

**关联基准**：Apex / Apex Shortlist。

## Tongyi-Zhiwen（通义智文）

**一句话**：阿里通义旗下、面向长文档理解的方向/团队，发布超长上下文基准 CorpusQA。

**基本情况**
- CorpusQA 完整版达 1000 万 token，考查在整个语料库层面跨文档综合与推理（区别于单点「大海捞针」）。

**命名含义**：通义 = 阿里大模型品牌；智文 = 智能处理文档/长文，对应其长文档理解定位。

**关联基准**：CorpusQA 1M。

## 研究机构 / 高校

- **XLANG Lab（xlang-ai）**：香港大学相关的 NLP/Agent 研究组，发布 OSWorld（Computer-use 桌面环境基准）。
- **HKUST-NLP**：香港科技大学 NLP 组，联合 CMU 发布 Toolathlon（Tool Decathlon，工具使用「全能竞技」基准）。
- **CAIS（Center for AI Safety，AI 安全中心）**：AI 安全研究机构，联合发起 Humanity's Last Exam。
- **UC Berkeley（加州大学伯克利分校）**：RDI / Sunblaze 研究组发布 CyberGym（真实世界网络安全评测框架）。
- **普林斯顿大学（Princeton）**：提出原始 SWE-bench，奠定「真实 GitHub issue → 通过单元测试的补丁」这一评估范式。
- **CMU（卡内基梅隆大学）**：发布 ExploitBench（LLM 网络安全 Agent 的能力阶梯基准），并参与 Toolathlon。
