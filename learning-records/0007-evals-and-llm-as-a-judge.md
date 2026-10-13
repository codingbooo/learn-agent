# 0007: Agent 评测体系与质量门禁 —— 从断言失效到 Evals 与 LLM-as-a-Judge
- **Core Concept**: 概率系统使传统 assertEquals 确定性测试断言全面失效，肉眼抽检（Vibe Check）与硬编码补丁导致打地鼠式隐蔽回归。必须构筑三层评测金字塔（L1 硬规则断言、L2 结构化模型裁判 LLM-as-a-Judge、L3 沙箱端到端执行验收）。LLM-as-a-Judge 必须实施细粒度 Rubrics 量表、位置偏差双向消解与结构化 CoT 输出。全团队践行 EDD（Eval-Driven Development），将评测集作为 CI/CD 质量门禁。
- **Android Analogy**: Android 碎片化机型 CTS（Compatibility Test Suite）与单元测试分层。无法仅靠简单 JUnit 断言评估多机型动画手感与驱动兼容性，正如 Google 用 CTS 黑盒套件作为出厂契约，Agent 系统以标准化 Evals 测试集作为模型、Prompt 与工具演进的不可变验收契约。
- **ZPD Insight**: 学员已掌握确定性评测与质量保障（Evals / LLM-as-a-Judge / EDD），具备在工程上治理模型幻觉并进一步探索 Guardrails（输入输出安全护栏与运行时对齐）的基础。
