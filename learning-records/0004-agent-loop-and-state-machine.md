# 0004: Agent 运行循环与状态机
- **Core Concept**: Agent 不是神秘生物，而是宿主进程驱动的 ReAct 事件循环与有限状态机（FSM）；主控权与防御性熔断（Max Steps、循环检测、输出截断）必须由宿主硬性把控。
- **Android Analogy**: Looper / Handler / MessageQueue 驱动机制。LLM 是无状态解码器，运行时是 Looper，上下文数组是 MessageQueue。
- **ZPD Insight**: 学员已掌握 Agent 核心运行循环与状态转移拓扑，具备进入下一讲工具调用协议（Tool Call / IPC / 沙箱）的前提。
