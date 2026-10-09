# 0003: 记忆分层与上下文压缩
- **Core Concept**: 向量数据库非万能；工业级方案为 FTS5 倒排索引 + 结构化元数据；高水位触发 Compaction 垃圾回收。
- **Android Analogy**: RAM -> SQLite(Room) -> 磁盘/云端冷存储。
- **Milestone Status**: 篇章 1 闭环，已产出综合架构评审复习卡。
