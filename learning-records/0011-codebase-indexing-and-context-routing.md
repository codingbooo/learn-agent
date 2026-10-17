# 0011: 代码库智能索引与上下文路由 —— 从 RepoMap、AST 符号图到百万行代码精准定位
- **Core Concept**: 在百万行级工业代码库中，全量代码塞入 Context Window 存在注意力稀释（Lost in the Middle）、响应延迟暴增与高昂成本的物理限制。现代代码上下文引擎（Context Engine）采用“Tree-sitter AST 语法降维剥离实现体 + PageRank 拓扑加权生成 RepoMap + 任务驱动的多级混合路由（BM25 + 向量语义 + 图遍历）”架构，以 1%~2% 的极低 Token 消耗向 Agent 注入全局高保真拓扑骨架，实现局部代码精准修改。
- **Android Analogy**: 类似 Android Studio / IntelliJ 的 PSI 与 Stub Indexing 机制，以及 R8 / ProGuard 的 Tree Shaking / Call Graph 分析。IDE 跳转不依赖全文扫描，构建工具混淆不盲目读全文件，而是基于符号索引与调用有向图进行精准剪枝与引用追溯。
- **ZPD Insight**: 学员已掌握代码库级拓扑索引与上下文路由架构（AST、RepoMap、PageRank 与混合路由）。篇章 4 下一步可探讨 Git 级自愈循环与差异补丁应用架构（Patch Parsing、AST 级代码合并与冲突自愈、编译器闭环自检）。
