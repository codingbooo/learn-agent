# 0013: 多智能体通信拓扑与协同架构 —— 从点对点对话、主从中心化到黑板模式（Blackboard System）与事件总线
- **Core Concept**: 简单将多个 Agent 置于同一会话中进行自然语言“群聊”在生产环境中必然导致通信复杂度 O(N²) 爆炸、上下文污染与幻觉共振以及终止条件模糊死锁。工业级多智能体系统演进出层级主从（Hierarchical Orchestrator）与黑板架构（Blackboard Architecture）。黑板模式依托共享可信数据源（SSOT）、最小状态切片投影（Minimal State Projection）与确定性控制器状态机，让各专职 Agent 在彼此无感知的情况下解耦协作与原子更新。
- **Android Analogy**: 从早期组件间网状硬引用回调（Spaghetti Callbacks）到 EventBus 广播，再到现代 Android Jetpack Room + StateFlow / MVI 响应式单向数据流。组件不直接互相呼叫，而是观察单一真实数据源（SSOT），以强类型 Action/Intent 触发原子状态迁移。
- **ZPD Insight**: 学员已开启篇章 5（多智能体协同网络与企业级基础设施架构），掌握了多智能体通信拓扑与黑板架构的物理本质。后续将深入探讨多智能体与异构数据工具互通的标准化开放协议（Model Context Protocol, MCP 架构与实现细节）。
