
# 优化的几种方式
## 稀疏注意力减少Q-K
基于位置的注意力机制
全局，局部，带状

## FlashAttention
寄存器：线程访问
共享内存：线程快访问
全局内存（显存）：所有线程共享

torch.backedn.cuda.enable_flash_sdp()

## 多查询注意力, 减少Q-K
不同的注意力头共享K和V


## 滑动窗口注意力mistral
