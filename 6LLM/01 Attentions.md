


**通常K和V是同源的**

# 注意力的几种方式
## 自注意力
q, k, v都是同源的

## 多头注意力
问题
- 训练过程：不会显著影响
- 推理过程：反复加载巨大的 KV Cache



# 优化的几种方式

## 多查询注意力
不同的注意力头共享K和V, 减少KV Cache大小



## FlashAttention
寄存器：线程访问
共享内存：线程快访问
全局内存（显存）：所有线程共享

torch.backedn.cuda.enable_flash_sdp()



# 注意力架构

| 架构        | 设计者                                               | 特点                                     | 链接                                                                                                   |
| ----------- | ---------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Transformer | Google                                               | 最流行，几乎所有大模型都用它             | [OpenAI 的代码](https://github.com/openai/finetune-transformer-lm/blob/master/train.py)                |
| RWKV        | [PENG Bo](https://www.zhihu.com/people/bopengbopeng) | 可并行训练，推理性能极佳，适合在端侧使用 | [官网](https://www.rwkv.com/)、[RWKV 5 训练代码](https://github.com/BlinkDL/RWKV-LM/tree/main/RWKV-v5) |
| Mamba       | CMU & Princeton University                           | 性能更佳，尤其适合长文本生成             | [GitHub](https://github.com/state-spaces/mamba)                                                        |


## Decode-Only / Cacsual Decoder-Only
有良好的扩展性和Zeo-Shot性能
CPT, LlaMA

## Prefix-Decoder / Non - Causal Decoded - Only
输入双向注意力，输出为单向自注意力
GLM


## Encode - Decode







# PE Position Encode位置编码
## 三角函数
## 旋转位置编码



# Transfomers
## Transfomers的意义
Transforme它于2017年由Google的论文《Attention is All You Need》中提出。主要有意向创新点
1. 自注意机制：它允许模型在处理序列数据时直接计算序列中任意两个位置之间的依赖关系，无需像传统RNN和CNN那样逐步传递信息或依赖固定大小的窗口。**自注意力操作本身并不涉及元素在序列中的位置信息，它只关注元素间的关系，而不是它们的相对或绝对位置**
2. 多头注意力：Transformer可以从不同的表示子空间捕获丰富的信息，增强了模型的表示能力。
3. 位置编码：
4. 并行处理能力：
5. 灵活的架构：可以堆叠。

## Transfomers的影响和局限
1. 预训练模型的兴起。
2. 大模型。
3. CV领域

## 问题：
1. 计算资源要求高
2. 长序列处理能力。


## Transfomer结构
Transformer模型的结构是基于编码器-解码器（Encoder-Decoder）架构的，旨在处理序列到序列（seq2seq）的任务，如机器翻译。

### 编码器（Encoder）
编码器由N个相同的层堆叠而成（典型的N值为6）。每一层包含两个主要的子层：
- 自注意力层（Self-Attention Layer）：这个层允许每个位置的输入序列在编码时考虑到序列中的其他所有位置，从而捕获了序列内的全局依赖关系。
- 前馈神经网络（Feed-Forward Neural Network）：对自注意力层的输出进行处理的一个全连接的前馈网络。每个位置都会使用相同的前馈网络，但是它们不共享参数。
每个子层之前都有残差连接（Residual Connection），并且每个子层的输出都会进行层归一化（Layer Normalization）。


## 解码器（Decoder）
- 遮蔽自注意力层（Masked Self-Attention Layer）：与编码器中的自注意力层类似，但添加了遮蔽（Masking）以确保位置只能依赖于之前的位置，这对于预防信息泄露至解码器尚未生成的部分至关重要。
- 编码器-解码器注意力层（Encoder-Decoder Attention Layer）：这个层使解码器能够关注（Attention）到编码器的输出。具体来说，解码器的查询（Q）来自于前一个解码器层的输出，而键（K）和值（V）来自于编码器的输出。
- 前馈神经网络：与编码器中的前馈网络相同，但参数是独立的。

解码器的每个子层同样使用了残差连接和层归一化
