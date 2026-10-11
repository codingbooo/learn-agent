# 0005: 工具调用协议与沙箱隔离
- **Core Concept**: 工具调用不是模型自主执行代码，而是宿主与模型之间的应用层 RPC 协议（JSON Schema 契约 + tool_calls 序列化）。三代演进（Prompt 约定 -> Native Function Calling -> MCP 开放标准）。必须在宿主层建立间接提示词注入防护、特权分离与沙箱隔离。
- **Android Analogy**: AIDL / Binder IPC 与 Android 权限沙箱（LLM 是低权限 untrusted client，JSON Schema 是 .aidl 契约，tool_calls 是 Parcel 包，宿主充当系统服务做 permission check 与系统调用）。
- **ZPD Insight**: 学员已掌握工具调用协议与安全边界，具备进入下一讲结构化规划与分层拆解（Planning / Sub-agent / 分解拓扑）的前提。
