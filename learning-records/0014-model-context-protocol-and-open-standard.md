# 0014: 模型上下文协议（Model Context Protocol, MCP）—— 解耦工具集成与多源数据管道的标准化架构
- **Core Concept**: 传统 Agent 与异构数据工具集成面临 N×M 烟囱式适配困境与凭证散落风险。Anthropic 主导开源的 Model Context Protocol (MCP) 建立了基于 JSON-RPC 2.0 的开放 Client-Server 协议规范。MCP 将数据管道与能力清晰抽象为三大核心原语：只读数据流资源（Resources）、带副作用的受限执行工具（Tools）、预置工作流提示词模板（Prompts），并通过本地 stdio 进程管道（天然进程隔离）与远程 SSE+HTTP 网络通道实现即插即用。
- **Android Analogy**: 类似 Android 生态从早期混乱的私有数据库文件操作演进为通过 ContentProvider 与统一 URI (`content://...`) 暴露只读数据，以及通过 HAL 驱动模型与 Binder AIDL 暴露标准化 RPC 硬件服务能力，彻底终结了上层 Framework 与异构芯片/外设之间的强耦合。
- **ZPD Insight**: 学员已深入理解多智能体基础设施中的 MCP 标准化解耦架构与三原语分工。篇章 5 接下来将推进至 Agent 的持久化记忆湖泊、多 Agent 冲突消解机制（Consensus & Voting / Multi-Agent Conflict Resolution）以及生产级可观测性链路（Tracing, OpenTelemetry & AgentOps）。
