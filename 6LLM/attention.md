
# 优化的几种方式
## 稀疏注意力减少Q-K
基于位置的注意力机制
全局，局部，带状

## FlashAttention
寄存器：线程访问
共享内存：线程快访问
全局内存（显存）：所有线程共享

torch.backedn.cuda.enable_flash_sdp()

## 多查询注意力, 减少K-V
不同的注意力头共享K和V


## 滑动窗口注意力mistral


# 注意力架构

| 架构        | 设计者                                               | 特点                                     | 链接                                                                                                   |
| ----------- | ---------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Transformer | Google                                               | 最流行，几乎所有大模型都用它             | [OpenAI 的代码](https://github.com/openai/finetune-transformer-lm/blob/master/train.py)                |
| RWKV        | [PENG Bo](https://www.zhihu.com/people/bopengbopeng) | 可并行训练，推理性能极佳，适合在端侧使用 | [官网](https://www.rwkv.com/)、[RWKV 5 训练代码](https://github.com/BlinkDL/RWKV-LM/tree/main/RWKV-v5) |
| Mamba       | CMU & Princeton University                           | 性能更佳，尤其适合长文本生成             | [GitHub](https://github.com/state-spaces/mamba)                                                        |
