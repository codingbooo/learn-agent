# 0016: 端侧小模型（SLM）与边缘推理运行时 —— 从 GGUF/AWQ 量化、NPU 硬件加速到端侧内存与功耗治理
- **Core Concept**: 纯云端 Agent 架构面临弱网/离线失效、首字延迟（TTFT 400ms~1500ms）无法满足实时交互、高灵敏隐私（相册/即时通讯）无法上云以及海量 Token 算力成本高昂等物理与经济学瓶颈。端侧小模型（SLM, 1B~3B 如 Gemma 2 2B、Llama 3.2 1B/3B、Qwen 2.5 1.5B/3B）成为端侧智能系统的破局核心。端侧落地核心依托模型量化技术（FP16 -> W4A16 / AWQ / GGUF，体积削减 70%~75%）与 KV Cache 量化（FP8/INT4），打破 LPDDR 移动统一内存带宽墙。通过平台级 NPU 硬件推理运行时（如 Qualcomm QNN、ExecuTorch、LiteRT）进行离线计算图编译与异构加速，规避 CPU 算子回退黑洞，将功耗锁定在移动设备的 Thermal 包络内。
- **Android Analogy**: 
  1. 犹如 ART 虚拟机安装期通过 `dex2oat` 将 DEX 字节码 AOT 编译为特定 ARM64 本地指令 ELF，QNN/ExecuTorch 将计算图离线编译为针对 Hexagon NPU 的硬件专属二进制 Blob，消除运行时解析开销；
  2. 针对物理内存约束，犹如 Linux `lmkd` 依据 `oom_score_adj` 水线精准查杀进程，端侧 SLM 必须压缩至 1GB~1.5GB 并采用 `mmap` 零拷贝映射，严防挤占前台 GraphicBuffer/Camera 导致 OOM 崩溃；
  3. 针对发热功耗，正如 Android `Thermal HAL` 在结温过高时强制降频，端侧推理必须依靠 NPU 的超高能效比替代 CPU 暴力死磕，并在高负载时自适应休眠。
- **ZPD Insight**: 学员已完成前五个核心篇章（底层心智、运行时、评测与安全、Vibe Coding 代码工程、多智能体协同网络）的全局认知沉淀。今日正式开辟“篇章 6：端侧智能与端云协同架构”，将 Agent 架构从云端服务器延伸至移动与边缘物理硬件，建立模型参数压缩、内存水线防护、NPU 硬件异构调度与能效比治理的底层软硬件协同心智。
