# 二个阶段
BERT整体框架包含**pre-train**和**fine-tune**两个阶段
pre-train阶段模型是在无标注的标签数据上进行训练，fine-tune阶段，BERT模型首先是被pre-train模型参数初始化，然后所有的参数会用下游的有标注的数据进行训练
# Embedding

- **Token Embeddings**是词向量，第一个单词是CLS标志，可以用于之后的分类任务
- **Segment Embeddings**用来区别两种句子，因为预训练不光做LM还要做以两个句子为输入的分类任务
- **Position Embeddings**和之前文章中的Transformer不一样，不是三角函数而是学习出来的


# pre-train的2个任务
MLM：Mask Language Model
Next Sentence Prediction（NSP）


# ALBERT 轻量级BERT

ALBERT针对BERT的修改主要有两点，

- **嵌入参数化进行因式分解**
- **跨层参数共享**
- **NSP任务更改为SOP任务**,  句子顺序预测

# RoBERT
训练时间更长，batch size更大，数据更多
删除了 NSP
动态MASK

![[Pasted image 20240106170104.png]]
The key differences introduced by RoBERTa are:
- Removing the next sentence prediction task from pre-training (binary-classification task of predicting whether two sentences are a pair from the same text).
- Using dynamic masking instead of static masking.


# 训练
batch size: 32
学习率：bert本身10的-5次方，添加的层10的-3次方
epoches：2，3，4