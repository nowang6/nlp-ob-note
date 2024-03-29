# 评估指标

## ROUGE（Recall-Oriented Understudy for Gisting Evaluation）/ 对话
自动摘要评价指标， 也可以用于对话模型

## GLUE General Language Understanding Evaluation / 自然语言理解
9 个 NLU 的任务， 8 个分类任务（1个三分类，7 个二分类），一个回归任务(STS-B)

# Chinese Language Understanding Evaluation Benchmark(CLUE)

## BLEU Bilingual Evaluation Understudy
翻译评估, 衡量模型生成的文本与一组参考文本的相似度

## METEOR（Metric for Evaluation of Translation with Explicit ORdering）
在解决早期自动评价指标（如BLEU）存在的一些局限性，特别是在更好地与人类评价结果对齐方面



# 词嵌入Embedding
Leaderboard: https://huggingface.co/spaces/mteb/leaderboard
## MTEB: Massive Text Embedding Benchmark(海量⽂本嵌⼊基准)
https://huggingface.co/spaces/mteb/leaderboard

## C-MTEB


# 微调

## P-Tuning
P=prompt
只对输入层进行训练，训练Soft prompts

##  Prefix-Tuning
在模型的每一个解码步骤前添加可以学习的向量


## Adapter 
更老




# 激活函数
## Sigmoid/Logistic/逻辑函数
$$
σ(x) = \frac{1}{1 + e^{-x}}
$$


## ReLU


## SwiGLU
f(x) = x * sigmoid(βx)
- β 趋近于0 时，Swish 函数趋近于线性函数y = x
- 当β 趋近于无穷大时，Swish 函数趋近ReLU激活函数
- β 取值为1 时，Swish 函数是光滑且非单调。模型一般使用这个值

# 位置编码
## 正余弦函数

## 旋转位置编码
RMS Norm
https://spaces.ac.cn/
使用欧拉公式构造旋转矩阵，分别将q和k旋转到空间中对应的位置，实现对计算结果添加位置信息，再计算qm@kn


# 上下文扩展

YaRN
RoPE
ALiBi位置编码具备良好的外推性

# 归一化

## LayerNorm

## RMSNoram
对LayerNorm进行简化，去除了计算均值进行平移


# RLHF框架
- Deepspeed Chat
- Transformer Reinforcement Learning
- PaLM-RLHF

