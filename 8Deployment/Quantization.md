模型压缩技术
- 量化
- 稀疏
- 低秩分解
  - SVD分解
- NAS 神经网络结构搜索 模型设计阶段
- 知识蒸馏


![[Pasted image 20240404065001.png]]

# 硬件

![[Pasted image 20240404101727.png]]
Adreno GPU (ATI技术)
Hexagon NPU (AI专用处理器)

# 工具

## dipoorlet - 商汤
内部工具
https://github.com/ModelTC/Dipoorlet

## Openppl PPQ
面向开源
https://github.com/openppl-public/ppq

## MLC.AI.  Machine Learning Compilation



# 模型
Qwen 1.5 - 1.8B - Chat



# 量化技术
对称量化，非对称量化
均匀量化，非均匀量化
静态量化，动态量化


# 数据校准
MinMax
KL Divergence （TensorRT使用）
MSE
Histogram



[MQBench: Towards Reproducible and Deployable Model Quantization Benchmark 论文学习-CSDN博客](https://blog.csdn.net/qq_31993233/article/details/123893593)

# 离线和在线量化
Post Training Quantization PTQ 离线量化
Quantization Aware Training 在线量化
![[Pasted image 20240406184740.png]]

# 开发板
qcm6125

[Hexagon SDK - Tools - Qualcomm Developer Network](https://developer.qualcomm.com/software/hexagon-dsp-sdk/tools)

为了将AI“装进”手机：通过NPU和异构计算开启终端侧生成式AI-高通白皮书