## 一、Google ADK 发布长期运行 AI Agent 教程：让 Agent 能"睡觉"也能"醒来"【⭐⭐】

**来源：** Google AI Blog
**链接：** https://developers.googleblog.com/build-long-running-ai-agents-that-pause-resume-and-never-lose-context-with-adk/
**关键词**：Google ADK, 长期运行 Agent, 有状态, 状态机, 持久化会话, 多 Agent 委托

### 摘要

Google 发布了一篇重磅教程，教你怎么用 Agent Development Kit (ADK) 构建能跑几周的 AI Agent。核心突破就一个：Agent 可以暂停，等几天，再无缝恢复，**不会丢任何上下文**。

这件事的背景很实在。大多数 Agent 教程最后做出来的就是个"无状态聊天机器人"——用户问一句答一句，容器重启一切归零。但真实的业务流程根本不是这样：HR 入职流程要跑两周，发票争议处理要等供应商回复好几天，销售跟进要跨越一个月。这些流程里大部分是"空闲时间"——Agent 啥也不干，就等着人签字、设备发货、审批通过。

教程用一个"新员工入职协调 Agent"做例子，完整展示了三种关键架构转变：

1. **持久化状态机**：不用对话历史记录进度，而是显式定义状态（START → WELCOME_SENT → DOCUMENTS_SIGNED → IT_PROVISIONED → HARDWARE_DELIVERED → COMPLETED），Agent 每一步都从状态里读当前进度，不会跳步也不会幻觉出没发生的事
2. **事件驱动的休眠门**：Agent 在等人回复时自动"睡觉"，不浪费 token，有人回复了再"醒来"，改用 webhook 触发而不是轮询
3. **多 Agent 委托**：IT 配置这类工作交给专门的子 Agent 处理，而不是让一个 Agent 做所有事情

对比传统方式，这篇文章指出了无状态 Agent 的三个致命问题：① 上下文污染——几百次对话塞一起，模型搞不清自己到哪步了；② Token 爆炸——两周对话历史每次推理都要重放；③ 空闲时间幻觉——停几天再恢复时，模型会脑补出中间步骤。

这个方向对做 AI 应用落地的人来说非常重要。现在大部分 AI Agent 只能做实时对话，没法真正处理企业里那种"等几天、做一步、再等几天"的真实流程。Google ADK 这套方案把 Agent 从"聊天框"升级成了"后台任务系统"。

完整代码已开源到 GitHub。
