# 评估指标

## BLEU Bilingual Evaluation Understudy
翻译评估, 衡量模型生成的文本与一组参考文本的相似度

## METEOR（Metric for Evaluation of Translation with Explicit ORdering）
在解决早期自动评价指标（如BLEU）存在的一些局限性，特别是在更好地与人类评价结果对齐方面

## ROUGE（Recall-Oriented Understudy for Gisting Evaluation）
自动摘要评价指标， 也可以用于对话模型

## GLUE General Language Understanding Evaluation 
9 个 NLU 的任务， 8 个分类任务（1个三分类，7 个二分类），一个回归任务(STS-B)

# Chinese Language Understanding Evaluation Benchmark(CLUE)

# 模型结果

## Encode Only
BERT

## Decode Only
GPT
Lamma


## Encode-Decode
T5


# Embedding
Leaderboard: https://huggingface.co/spaces/mteb/leaderboard
## MTEB: Massive Text Embedding Benchmark(海量⽂本嵌⼊基准)
https://huggingface.co/spaces/mteb/leaderboard


## C-MTEB


## bge智源
bpe是Byte Pair Encoding， transfomers里的子词切分算法
https://blog.csdn.net/v_JULY_v/article/details/135311471



# In-Context Leaning

![[Pasted image 20240203101100.png|500]]



# Chain of thought




# SFT Supervised Fine-Tuning

监督式微调



# RLHF Reinforcement Learning from Human Feedback



# 微调

## P-Tuning
P=prompt
只对输入层进行训练，训练Soft prompts

##  Prefix-Tuning
在模型的每一个解码步骤前添加可以学习的向量


## Adapter 

更老

## LoRA


## LoRA Hub

=======
# 模型
## LLaMA
- 前置层归一化 Pre-Layer-Norm
- 使用RMSNorm函数
- 激活函数从ReLU替换为SwiGLU
- 位置编码从正余弦函数变为旋转位置编码（Rotary Position Embeeding）RoPE


# 归一化
## RMSNorm函数
RMS Norm是一般LayerNorm的一种变体，可以在梯度下降时令损失更加平滑，与layerNorm相比，RMS Norm的主要区别在于去掉了减去均值的部分(re-centering)，只保留方差部分(re-scaling)


# 激活函数
## ReLU

## SwiGLU

# 位置编码
## 正余弦函数

## 旋转位置编码
https://spaces.ac.cn/

# 对比学习
ConSERT
SimCSE

# 上下文扩展

YaRN
RoPE

# 其他

## 打印模型参数
```python
for name,param in model.named_parameters():
  print(name,param.dtype)
```
