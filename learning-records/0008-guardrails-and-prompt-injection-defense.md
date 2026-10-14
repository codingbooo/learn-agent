# 0008: 运行时安全护栏（Guardrails）与防注入架构 —— 从 Prompt Injection 到双系统拦截网
- **Core Concept**: 提示词注入（Prompt Injection 与越狱）的本质是大模型控制信令（Instructions）与业务数据（Data）完全混在同带 Token 序列中（In-band Signaling），导致模型沦为混淆代理人（Confused Deputy）。绝不能依赖 System Prompt 进行自我合规审查。必须在外围构筑输入护栏（Input Guardrails，PII脱敏与越狱检测）、工具门禁（Tool Gatekeeper，最小权限与审批熔断）、输出护栏（Output Guardrails，敏感信息外泄阻断）。对高危不可信数据（爬虫网页、PDF、邮件）应采用 Dual-LLM 沙箱隔离模式，由无权限解析器提取结构化数据，斩断注入链路。
- **Android Analogy**: Android 系统安全与权限模型（SELinux MAC 强制访问控制与 AppOps/SystemServer 审计）。Android 绝不依赖 App 在自身进程代码中自查权限，而是通过独立的内核态 UID 沙箱与 Framework 服务作为外部裁判；同理，Guardrails 是独立于模型推理循环之外的强制安全子系统。
- **ZPD Insight**: 学员已掌握 Evals 评测（离线验收契约）与 Guardrails 护栏（运行时安全拦截），接下来可深入探讨确定性受限解码（Structured Outputs / Grammar-constrained Decoding / JSON Schema 严格对齐），从而在代码生成与格式约束上实现数学级确定性收敛。
