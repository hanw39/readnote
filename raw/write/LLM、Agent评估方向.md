模型、Agent基准测试的侧重点

> **命名小词典**
> - **SWE** = Software Engineering（软件工程）。SWE-bench、SWE-Check、SWE-bench Pro 都属同一谱系：给模型一个真实 GitHub 仓库的 issue，让它生成能通过单元测试的补丁。SWE-bench 由普林斯顿提出。
> - **Bench / Benchmark** = 基准测试集，一组带标准答案或可自动判分的任务。
> - **Eval / val** = Evaluation（评估）的缩写，如 GDPval = GDP + eval。
> - **Verified / Pro / Hard / Diamond** = 同一基准的不同子集：人工核验过的「干净版」、加难版、精选高难子集等。

## Knowledge & Reasoning（知识与推理）

**MMLU-Pro (EM)**
- **简介**：MMLU（大规模多任务语言理解）的加强版，覆盖数十个学科的选择题，Pro 版选项更多、更难、更防套路。EM = Exact Match（精确匹配），即答案完全对才算分。
- **命名含义**：MMLU = Massive Multitask Language Understanding；Pro = 加难版。

**SimpleQA-Verified / **Chinese-SimpleQA **
- **简介**：考查模型对「简短事实性问题」的准确性与抗幻觉能力——问题答案唯一、易核验，专门暴露模型「一本正经胡说」的毛病。Chinese-SimpleQA 是中文版。Pass@1 = 只给一次作答机会的正确率。
- **命名含义**：SimpleQA = 简单事实问答；Verified = 经核验的干净子集。

**GPQA Diamond**
- **简介**：研究生级别、Google 都难搜到答案的高难科学题（物理/化学/生物），Diamond 是其中专家高度一致、质量最高的子集。考查深层科学推理。
- **命名含义**：GPQA = Graduate-Level Google-Proof Q&A（研究生级、防搜索问答）；Diamond = 最高质量子集。

**LiveCodeBench**
- **简介**：用「持续更新的新题」考查模型写代码/解算法题的能力，因题目较新可缓解数据污染，Live 体现其滚动更新。
- **命名含义**：Live = 实时/滚动更新；Code = 编程；Bench = 基准。

**Codeforces (Rating)**
- **简介**：直接用知名竞赛编程平台 Codeforces 的题目评测，并换算成与人类选手可比的 **Rating（天梯分）**，衡量模型的竞赛级算法能力。
- **命名含义**：Codeforces = 竞赛平台名；Rating = 天梯积分。

**HMMT 2026 Feb**
- **简介**：取自哈佛-MIT 数学竞赛（HMMT）2026 年 2 月赛的题目，考查高中顶尖竞赛级数学能力。用新一届赛题可缓解数据污染。
- **命名含义**：HMMT = Harvard-MIT Math Tournament；2026 Feb = 具体赛事场次。

**IMOAnswerBench**
- 项目主页：[https://imobench.github.io/](https://imobench.github.io/)
- 论文地址：[https://huggingface.co/papers/2511.01846](https://huggingface.co/papers/2511.01846)
- **简介**：[[Company#Google DeepMind|Google DeepMind]] 的 IMO-Bench 套件之一，由 IMO 奖牌得主参与设计。只考「最终答案对不对」的奥数题（对应的 IMO-ProofBench 则评证明过程），目标是抗套路的稳健数学推理。
- **命名含义**：IMO = 国际数学奥林匹克；AnswerBench = 只判最终答案的基准。

**Apex / Apex Shortlist**
- 论文地址：[https://arxiv.org/pdf/2601.14242v2](https://arxiv.org/pdf/2601.14242v2)
- **简介**：[[Company#Mercor|Mercor]] 的 APEX 系列，480 个贴近真实职业的长程任务，考查多步推理与持续执行（另有 APEX-SWE 软件工程变体）。Shortlist 应为精选高难子集。
- **命名含义**：Apex = 顶点/巅峰，寓意能力上限；Shortlist = 入围精选（高难子集）。



**SWE-Bench Pro**：
- Hugging Face 数据集：[https://hf-mirror.com/datasets/Schwerli/SWE-bench_Pro](https://link.wtturl.cn/?target=https%3A%2F%2Fhf-mirror.com%2Fdatasets%2FSchwerli%2FSWE-bench_Pro&scene=im&aid=497858&lang=zh "autolink")
- GitHub：[https://github.com/scaleapi/SWE-bench_Pro-os](https://link.wtturl.cn/?target=https%3A%2F%2Fgithub.com%2Fscaleapi%2FSWE-bench_Pro-os&scene=im&aid=497858&lang=zh "autolink")
- 官方说明：[https://scale.com/leaderboard/swe_bench_pro_public](https://link.wtturl.cn/?target=https%3A%2F%2Fscale.com%2Fleaderboard%2Fswe_bench_pro_public&scene=im&aid=497858&lang=zh "autolink")
- **简介**：原始 SWE-bench 的「专业加强版」，由 [[Company#Scale AI|Scale AI]] 维护。沿用「给真实 GitHub issue + 仓库，让 Agent 生成能跑通单元测试的补丁」的范式，但任务更难、更贴近企业级代码库，并做了防数据污染处理，可信度更高。
- **命名含义**：SWE = Software Engineering（软件工程）；Pro = Professional，相对初版更专业、更难。

**SWE Verified / SWE Multilingual (Resolved)**
- **简介**：同属 SWE-bench 谱系。**SWE-bench Verified** 是 OpenAI 等人工核验过的 500 题干净子集，剔除描述不清/无法判定的样例，是当前最常被引用的「标准跑分版」；**SWE-bench Multilingual** 把范式扩展到多种编程语言（不止 Python），考查跨语言修 bug 能力。Resolved = 成功解决（补丁通过测试）的比例。
- **命名含义**：Verified = 经人工核验的干净子集；Multilingual = 多语言（多编程语言）。

**FrontierCode (Diamond)**
- 项目主页：[https://benchlm.ai/benchmarks/frontierCode](https://link.wtturl.cn/?target=https%3A%2F%2Fbenchlm.ai%2Fbenchmarks%2FfrontierCode&scene=im&aid=497858&lang=zh "autolink")
- 说明：Diamond 是该基准的 50 个高难度任务子集，由 [[Company#Cognition|Cognition]] 发布
- **简介**：面向「前沿/最难」编码任务的基准，衡量 Agent 在复杂工程问题上的真实能力上限。Diamond 子集是从中精选的最硬骨头，用来拉开顶尖模型之间的差距。
- **命名含义**：Frontier = 前沿（能力边界）；Code = 编码任务；Diamond（钻石）= 最高难度档位，类似段位里的「钻石级」。

**Terminal-Bench 2.1**
-  官网：[https://www.tbench.ai/news/terminal-bench-2-1](https://link.wtturl.cn/?target=https%3A%2F%2Fwww.tbench.ai%2Fnews%2Fterminal-bench-2-1&scene=im&aid=497858&lang=zh "autolink")
-  Harbor 数据集：[https://hub.harborframework.com/datasets/terminal-bench/terminal-bench-2-1/latest](https://link.wtturl.cn/?target=https%3A%2F%2Fhub.harborframework.com%2Fdatasets%2Fterminal-bench%2Fterminal-bench-2-1%2Flatest&scene=im&aid=497858&lang=zh "autolink")
- **简介**：考查 Agent 在真实命令行/终端环境里完成任务的能力——装环境、跑脚本、调试、文件操作等，全程通过 shell 交互完成，更接近运维与开发的日常。2.1 是其迭代版本。
- **命名含义**：Terminal = 终端/命令行；Bench = 基准；2.1 = 版本号。

**Expert-SWE (Internal)**
- 说明：标注 Internal，为模型厂商自建、未公开的内部基准，无公开数据集/论文地址。
- **简介**：面向「专家级软件工程」任务的内部评测，沿用 SWE 谱系（真实仓库 issue → 通过测试的补丁），但题目由厂商内部挑选、难度更高，主要用于自家模型的内部对比，不对外发布以避免污染。
- **命名含义**：Expert = 专家级（难度更高）；SWE = Software Engineering；Internal = 内部、未公开。

## Knowledge work

**GDPval-AA**
- Hugging Face 数据集：[https://huggingface.co/datasets/openai/gdpval](https://link.wtturl.cn/?target=https%3A%2F%2Fhuggingface.co%2Fdatasets%2Fopenai%2Fgdpval&scene=im&aid=497858&lang=zh "autolink")
- 论文地址：[https://arxiv.org/html/2510.04374](https://link.wtturl.cn/?target=https%3A%2F%2Farxiv.org%2Fhtml%2F2510.04374&scene=im&aid=497858&lang=zh "autolink")
- **简介**：[[Company#OpenAI|OpenAI]] 于 2025 年 9 月发布。不考学术难题，而是衡量模型在「真实、有经济价值的知识工作」上的表现——任务取自占 GDP 较大比重的多个行业/职业的真实交付物（报告、方案、设计稿等），由资深专业人士出题并对照人类专家成果打分。AA 应为其某一评测档/聚合口径。
- **命名含义**：GDP = Gross Domestic Product（国内生产总值），强调任务的经济价值导向；val = evaluation（评估）。

**GDP.pdf**：推测为 GDPval 的视觉 / 文档理解变体，暂无独立公开地址，相关数据在 GDPval 项目中可查

## Long Context（长上下文）

**MRCR 1M (MMR)**
- **简介**：超长上下文检索/推理基准，在约 100 万 token 的上下文里放入多条易混淆的相似内容，要求模型精确找回指定那一条，考查长程「大海捞针 + 抗干扰」能力。1M 指上下文长度档。
- **命名含义**：MRCR = Multi-Round Co-reference Resolution（多轮指代消解）一类的长文检索任务；1M = 100 万 token。

**CorpusQA 1M (ACC)**
- GitHub：[https://github.com/Tongyi-Zhiwen/CorpusQA](https://github.com/Tongyi-Zhiwen/CorpusQA)
- 论文地址：[https://arxiv.org/html/2601.14952](https://arxiv.org/html/2601.14952)
- **简介**：[[Company#Tongyi-Zhiwen（通义智文）|Tongyi-Zhiwen]] 发布，完整版达 1000 万 token，1M 为百万档。不同于「单点捞针」，它要求在整个语料库层面跨文档综合、推理后作答。ACC = Accuracy（准确率）。
- **命名含义**：Corpus = 语料库（整库级）；QA = 问答；1M = 100 万 token。



## Spatial reasoning（空间推理）

**FrontierMath (Tier 1–4)**
- 项目主页：[https://epoch.ai/frontiermath](https://epoch.ai/frontiermath)
- Tier 4 单独追踪：[https://epoch.ai/benchmarks/frontiermath-tier-4](https://epoch.ai/benchmarks/frontiermath-tier-4)
- 论文地址：[https://arxiv.org/html/2411.04872v7](https://arxiv.org/html/2411.04872v7)
- **简介**：由 [[Company#Epoch AI|Epoch AI]] 发布的高级数学推理基准。题目均为数学家原创、未公开、答案可自动核验，专测真实数学推理而非记忆/套路；因题目保密，能有效防数据污染，难到连前沿模型和数学博士都常被难住。
- **分层**：Tier 1–3 难度递增，Tier 4 为研究级最难档，被单独作为一个基准追踪。
- **命名含义**：Frontier = 前沿（能力边界）；Math = 数学；Tier = 难度档位。

**Blueprint-Bench 2**
- 项目主页：[https://andonlabs.com/evals/blueprint-bench-2](https://link.wtturl.cn/?target=https%3A%2F%2Fandonlabs.com%2Fevals%2Fblueprint-bench-2&scene=im&aid=497858&lang=zh "autolink")
- 论文地址：[https://arxiv.org/html/2509.25229v1/](https://link.wtturl.cn/?target=https%3A%2F%2Farxiv.org%2Fhtml%2F2509.25229v1%2F&scene=im&aid=497858&lang=zh "autolink")
- 代码仓库：[https://github.com/AndonLabs/Blueprint-Bench-generation](https://link.wtturl.cn/?target=https%3A%2F%2Fgithub.com%2FAndonLabs%2FBlueprint-Bench-generation&scene=im&aid=497858&lang=zh "autolink")
- **简介**：考查模型的空间推理能力——根据房间照片、文字描述等输入，重建/绘制出建筑平面图（户型图）。难点在于把零散的二维视觉信息整合成正确的空间布局。由 [[Company#Andon Labs|Andon Labs]] 发布。
- **命名含义**：Blueprint = 蓝图/建筑平面图；Bench = 基准；2 = 第二代。

## Tool use / Computer use

**BrowseComp**
- 项目主页：[https://openai.com/index/browsecomp/](https://openai.com/index/browsecomp/)
- 论文地址：[https://arxiv.org/html/2504.12516](https://arxiv.org/html/2504.12516)
- **简介**：[[Company#OpenAI|OpenAI]] 于 2025 年 4 月发布，考查浏览型 Agent「在全网深挖难找信息」的能力——答案藏得很深、但找到后易于核验，奖励多步检索与推理，而非一次性查询。是 Deep Research 一类产品的代表评测。
- **命名含义**：Browse = 网页浏览；Comp = Competition/Comparison（竞赛/对比评测）。

**Toolathlon（Tool Decathlon）**
- 项目主页：[https://toolathlon.xyz/introduction](https://toolathlon.xyz/introduction)
- GitHub：[https://github.com/hkust-nlp/toolathlon](https://github.com/hkust-nlp/toolathlon)
- 论文地址：[https://openreview.net/forum?id=z53s5p0qhf](https://openreview.net/forum?id=z53s5p0qhf)
- **简介**：由 [[Company#研究机构 / 高校|HKUST-NLP]]（联合 CMU）发布，从「多样性、真实性、长程执行」三方面考查语言 Agent 的工具使用能力——覆盖众多领域的工具，任务贴近真实工作流，需要串起大量工具调用并在长序列里保持连贯。
- **命名含义**：Tool + athlon（取自 decathlon「十项全能」）= 工具使用的「全能竞技」；强调一专多能、综合考核。

**MCPAtlas Public
- GitHub：[https://github.com/scaleapi/mcp-atlas](https://github.com/scaleapi/mcp-atlas)
- 论文地址：[https://arxiv.org/html/2602.00933](https://arxiv.org/html/2602.00933)
- Leaderboard：[https://labs.scale.com/leaderboard/mcp_atlas](https://labs.scale.com/leaderboard/mcp_atlas)
- **简介**：由 [[Company#Scale AI|Scale AI]] 发布，用**真实 MCP 服务器**（而非模拟/打桩）大规模考查 Agent 的工具使用能力，更贴近真实接入场景。Public 为公开子集。
- **命名含义**：MCP = Model Context Protocol（模型上下文协议）；Atlas = 图集/大全，寓意覆盖广；Public = 公开子集。

**AutomationBench**
- 论文地址：[https://arxiv.org/pdf/2604.18934v1](https://link.wtturl.cn/?target=https%3A%2F%2Farxiv.org%2Fpdf%2F2604.18934v1&scene=im&aid=497858&lang=zh "autolink")
- 发布方：Zapier，暂无独立公开数据集页面
- **简介**：由 [[Company#Zapier|Zapier]] 于 2026 年 4 月发布，衡量 Agent 完成真实「自动化工作流」任务的能力——理解需求、调用各类 App/工具、把多个步骤串成可运行的自动化流程，贴近 Zapier 自身的产品场景。
- **命名含义**：Automation = 自动化（工作流）；Bench = 基准。

**OSWorld-Verified** 
- 项目官网：[https://os-world.github.io/](https://link.wtturl.cn/?target=https%3A%2F%2Fos-world.github.io%2F&scene=im&aid=497858&lang=zh "autolink")
-  GitHub：[https://github.com/xlang-ai/OSWorld](https://link.wtturl.cn/?target=https%3A%2F%2Fgithub.com%2Fxlang-ai%2FOSWorld&scene=im&aid=497858&lang=zh "autolink")
-  Hugging Face 数据集：[https://huggingface.co/datasets/xlangai/windows_osworld](https://link.wtturl.cn/?target=https%3A%2F%2Fhuggingface.co%2Fdatasets%2Fxlangai%2Fwindows_osworld&scene=im&aid=497858&lang=zh "autolink")
- **简介**：考查 Agent 在真实操作系统桌面环境（点击、输入、操作软件窗口）里完成跨应用任务的能力，是 Computer-use 方向的代表基准。由 [[Company#研究机构 / 高校|XLANG Lab]] 发布。Verified 版对任务做了人工核验，剔除有歧义/不可解的样例，分数更可信。
- **命名含义**：OS = Operating System（操作系统）；World = 完整的桌面环境世界；Verified = 经人工核验的子集。

## Specialized domains（专业领域）


**CyberGym**
- 项目主页：[https://www.cybergym.io/](https://www.cybergym.io/)
- GitHub：[https://github.com/sunblaze-ucb/cybergym](https://github.com/sunblaze-ucb/cybergym)
- 论文地址：[https://openreview.net/forum?id=2YvbLQEdYt](https://openreview.net/forum?id=2YvbLQEdYt)
- **简介**：由 [[Company#研究机构 / 高校|UC Berkeley]]（RDI / Sunblaze 组）发布的真实世界网络安全评测框架。基于大型生产代码库里的真实漏洞，让 Agent 复现漏洞（生成能触发崩溃的 PoC 输入），再对照修补版验证是否真复现。强调规模与真实性，目前模型整体通过率很低。
- **命名含义**：Cyber = 网络安全；Gym = 训练/评测「健身房」，呼应强化学习里 Gym 式的环境概念。


**Legal Agent Benchmark**
- GitHub：[https://github.com/cjj826/LegalAgentBench](https://link.wtturl.cn/?target=https%3A%2F%2Fgithub.com%2Fcjj826%2FLegalAgentBench&scene=im&aid=497858&lang=zh "autolink")
- 论文地址：[https://preview.aclanthology.org/navbar-space/2025.acl-long.116.pdf](https://link.wtturl.cn/?target=https%3A%2F%2Fpreview.aclanthology.org%2Fnavbar-space%2F2025.acl-long.116.pdf&scene=im&aid=497858&lang=zh "autolink")
- **简介**：法律领域的 Agent 基准，考查模型完成真实法律工作的能力——检索法条/案例、合同与文书分析、多步法律推理等，强调专业准确性。
- **命名含义**：Legal = 法律；Agent = 智能体；Benchmark = 基准。

**Humanity's Last Exam**
- 项目主页：[https://lastexam.ai/](https://link.wtturl.cn/?target=https%3A%2F%2Flastexam.ai%2F&scene=im&aid=497858&lang=zh "autolink")
- Hugging Face 数据集：[https://huggingface.co/datasets/cais/hle](https://link.wtturl.cn/?target=https%3A%2F%2Fhuggingface.co%2Fdatasets%2Fcais%2Fhle&scene=im&aid=497858&lang=zh "autolink")
- 论文地址：[https://fileserver-az.core.ac.uk/download/722297654.pdf](https://link.wtturl.cn/?target=https%3A%2F%2Ffileserver-az.core.ac.uk%2Fdownload%2F722297654.pdf&scene=im&aid=497858&lang=zh "autolink")
- **简介**：由 [[Company#研究机构 / 高校|CAIS]] 等机构发起，集合各学科顶尖专家出的「极难」题目，专门挑战前沿模型的知识与推理上限。当主流基准被模型刷满分后，它用来继续区分模型能力，号称是人类能给 AI 出的「最后一场考试」。
- **命名含义**：Humanity's Last Exam = 「人类的最后一场考试」，寓意题目难到接近人类出题能力的极限。
- **HLE w/tools (Pass@1)**：HLE 的「允许调用工具」变体（w/tools = with tools），即模型可借助搜索、代码执行等外部工具作答，考查「工具增强后」的推理上限，分数通常高于无工具版。

**BioMysteryBench**
- 公开样本：[https://huggingface.co/datasets/anthropic/BioMysteryBench](https://link.wtturl.cn/?target=https%3A%2F%2Fhuggingface.co%2Fdatasets%2Fanthropic%2FBioMysteryBench&scene=im&aid=497858&lang=zh "autolink")
- 说明：由 Anthropic 发布，完整数据集未完全公开
- **简介**：[[Company#Anthropic|Anthropic]] 的「解谜式」生物学推理基准，给出实验现象/数据等线索，要求模型像科学家一样推断背后的生物学机制或成因，侧重多步科学推理而非记忆。出于安全考虑只公开样本，完整集不公开。
- **命名含义**：Bio = Biology（生物学）；Mystery = 谜题（待破解的现象）；Bench = 基准。

**ExploitBench (Cap%)**
- 论文地址：[https://arxiv.org/pdf/2605.14153](https://link.wtturl.cn/?target=https%3A%2F%2Farxiv.org%2Fpdf%2F2605.14153&scene=im&aid=497858&lang=zh "autolink")
- 说明：由 CMU 发布，代码 / 容器开源，数据在 Hugging Face 可查
- **简介**：由 [[Company#研究机构 / 高校|CMU]] 发布，面向 LLM 网络安全 Agent 的「能力阶梯」基准，把任务按难度分层（从识别漏洞到实际利用），用于在受控环境中评估模型的攻防安全能力。Cap% 指其能力上限/通过率口径的指标。
- **命名含义**：Exploit = 漏洞利用；Bench = 基准；Cap% = capability/通过率百分比指标。

**HealthBench Professional**
- Hugging Face 数据集：[https://huggingface.co/datasets/openai/healthbench-professional](https://link.wtturl.cn/?target=https%3A%2F%2Fhuggingface.co%2Fdatasets%2Fopenai%2Fhealthbench-professional&scene=im&aid=497858&lang=zh "autolink")
- GitHub：[https://github.com/openai/simple-evals](https://link.wtturl.cn/?target=https%3A%2F%2Fgithub.com%2Fopenai%2Fsimple-evals&scene=im&aid=497858&lang=zh "autolink")
- 论文地址：[https://arxiv.org/html/2604.27470v1](https://link.wtturl.cn/?target=https%3A%2F%2Farxiv.org%2Fhtml%2F2604.27470v1&scene=im&aid=497858&lang=zh "autolink")
- **简介**：[[Company#OpenAI|OpenAI]] 的医疗健康评估基准（初版 2025 年 5 月发布）。围绕数千段真实多轮医疗对话，用医生撰写的评分细则（rubric）打分，覆盖急症识别、不确定性处理、面向不同对象的沟通等维度。Professional 面向「专业医护」场景，要求更高的临床准确性。
- **命名含义**：Health = 健康/医疗；Bench = 基准；Professional = 面向专业医护人员的进阶档。

