# 0002: 上下文窗口与 KV 缓存
- **Core Concept**: 上下文是易失性 RAM；KV Cache 依赖严格前缀哈希，中途篡改 System Prompt 会导致命中率归零。
- **Android Analogy**: 销毁重建的 Activity 与 savedInstanceState Bundle 序列化。
- **ZPD Insight**: 学员已掌握成本与延迟杀手机制，可以进入多级存储治理。
