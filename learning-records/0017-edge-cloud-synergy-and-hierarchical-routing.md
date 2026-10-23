# 0017: 端云协同分层架构与动态路由 —— 从意图门禁分流、端云投机解码（Speculative Decoding）到隐私脱敏管道
- **Core Concept**: 单纯的端侧架构受限于移动硅片面积与能耗包络，存在知识密度与复杂长程推理的物理上限；纯云端架构则面临不可控的网络 RTT 延迟、弱网瘫痪、隐私穿透与高昂 Token 算力成本。端云协同（Edge-Cloud Synergy）是移动与终端智能体的终局形态。核心架构由三大支柱组成：1) 端侧轻量意图门禁与状态路由器（结合网络 QoS、电量、Thermal 状态与 PII 敏感度动态分流）；2) 端云投机解码（Speculative Decoding，端侧 SLM 高速产出 Token Draft，云端大模型单次 Forward 批验证纠偏，折叠网络与计算等待）；3) 隐私数据沙箱与特征投影管道（端侧本地结构化提取与敏感信息脱敏，仅上传匿名特征或脱敏语义）。
- **Android Analogy**: 
  1. 类似 Android 经典三级缓存设计（Memory Cache -> SQLite/Room 本地数据库 -> Retrofit 远端网络），端侧 SLM 充当智能本地缓存，拦截 70% 轻量意图，仅将重型复杂推理穿透给云端；
  2. 类似 `WorkManager` 的约束调度（NetworkType.CONNECTED, BatteryNotLow），智能体根据移动设备实际网络与电量/温控状态动态决断本地执行、脱敏上云或降级离线；
  3. 类似 Android RenderThread 预录制绘制指令与 SurfaceFlinger 合成校验，端云投机解码由端侧本地极速生成 Draft 草稿，云端做最终确定性验证与纠偏。
- **ZPD Insight**: 学员在前一讲掌握了端侧小模型与 NPU 推理运行时的底层硬件约束，今日进一步打通端侧与云端的协同管道，理解意图分级路由、端云投机解码的时延优化以及隐私脱敏的架构边界，为构建工业级生产端云智能体系统夯实架构认知。
