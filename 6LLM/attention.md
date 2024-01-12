
# 优化的几种方式
## 稀疏注意力减少Q-K
基于位置的注意力机制
全局，局部，带状

## FlashAttention
线程独占：寄存器，共享内存
线程共享：全局内存
torch.backedn.cuda.enable_flash_sdp()

## 多查询注意力, 减少Q-K
不同的注意力头共享K和V


## 滑动窗口注意力mistral
