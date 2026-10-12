# 0006: 任务规划与分层拆解架构
- **Core Concept**: 超过 6 步长链路任务时，单步贪心 ReAct 必然遭遇上下文污染、注意力稀释与误差级联。三代演进（Plan-and-Solve -> Re-planning -> Hierarchical Sub-agent）。Sub-agent 的本质是为模型上下文建立物理级隔离边界，父 Agent 调度并收集摘要，避免噪声侵蚀全局注意力。三大工程底线：上下文物理隔离、有界树状深度（Max Depth ≤ 2）、DAG 状态持久化与局部重试。
- **Android Analogy**: WorkManager Task DAG 与多进程独立隔离（单步 ReAct 类似于在 UI 主线程阻塞堆叠长任务；Plan-and-Solve 对应 WorkManager 构建 WorkContinuation 拓扑；Sub-agent 对应 AMS 派发任务到独立子进程 :sync，享有独立虚拟内存，通过 IPC/Binder 仅回传极简结果 Bundle）。
- **ZPD Insight**: 学员已掌握运行时控制流（循环、工具安全、规划分层拓扑），具备完成篇章 2 并进入篇章阶段里程碑复习与后续评估/评测体系（Eval / Guardrails）的前提。
