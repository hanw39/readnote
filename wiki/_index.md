# Wiki 入口

这是 readnote 知识库的**语义索引层**。所有按主题组织的长青条目都在这里。原始素材（RSS 摘要、论文剪藏、读书笔记等）在仓库根目录的 `raw/` 下。

## 目录

- **people/** — 人物（研究者、KOL、创始人）
- **orgs/** — 组织（公司、实验室、社区）
- **products/** — 具体产品和工具
- **concepts/** — 技术/方法概念（小颗粒，定义清晰）
- **topics/** — 宽领域主题（大颗粒，方向性）
- **notes/** — 个人原创思考（不依附具体实体）

## 命名约定

- 文件名 **kebab-case**：`andrej-karpathy.md`、`prompt-caching.md`
- 双链使用 `[[文件名]]`，**不带路径、不带扩展名**——Obsidian 会在整个 vault 内自动定位
- 跨目录引用也用 `[[文件名]]`，例如在 `people/karpathy.md` 里写 `[[2026-05-17-karpathy-llm-os]]` 就能跳到 `raw/papers/...`

## 怎么区分 concepts/ 和 topics/

- **concepts/** = 边界清晰的技术点，几句话能定义（"prompt caching 是什么"）
- **topics/** = 边界模糊的领域/方向，本身是一片地（"AI 安全"涵盖多个子概念）
- 拿不准就先放 `concepts/`，将来长大了再迁

## 当前状态

立项日：2026-05-17

本 wiki 由 LLM 从 `raw/` 增量编译。当前阶段尚未实施编译 skill，条目需手动起步或等待 `wiki-compile` skill 完成后批量回填。

设计文档详见 hanw-skills 仓库下的 `docs/readnote-wiki-design.md`。
