# 评价
正例数量 << 反例数量
![[Pasted image 20240218195752.png|600]]
![[Pasted image 20240218195852.png|600]]
## Accuracy 准确率 
not Enough

```python
>>> accuracy_metric = evaluate.load("accuracy") 
>>> results = accuracy_metric.compute(references=[0, 1], predictions=[0, 1]) 
>>> print(results) {'accuracy': 1.0}
```
## Percision精准率/精确率/查准率
分母： TP
分子：TP+FP
正例预测对1个，反例预测错2个，精准率33%
```python
precision_metric = evaluate.load("precision")
results = precision_metric.compute(references=[1, 1, 0, 0, 0, 0, 0], predictions=[1, 0, 1, 1, 0, 0, 0])
print(results)
```
## Recall  召回率
分母： TP
分子：TP+FN
 一共2个正例，预测正确1个，召回率为50%
```python
recall_metric = evaluate.load('recall')
results = recall_metric.compute(references=[1, 1, 0, 0, 0, 0], predictions=[1, 0, 1, 1, 0, 0])
print(results)
```

## F1
https://huggingface.co/spaces/evaluate-metric/f1



CRF: https://www.julyedu.com/video/play/351/9777

# 场景

## 情感分类


## 命名实体识别

数据集：人民日报，微软亚洲研究院
## 关系抽取

## 知识图谱

Neo4j

## 聊天机器人
UltraChat

## 搜索
AnyQ

# Kaggle

1. Sentiment Analysis on Movie Reviews: [https://www.kaggle.com/c/sentiment-analysis-on-movie-reviews](https://www.kaggle.com/c/sentiment-analysis-on-movie-reviews)
2. Quora Question Pairs: [https://www.kaggle.com/c/quora-question-pairs](https://www.kaggle.com/c/quora-question-pairs)
3. Toxic Comment Classification Challenge: [https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge)
4. Natural Language Processing with Disaster Tweets: [https://www.kaggle.com/c/nlp-getting-started](https://www.kaggle.com/c/nlp-getting-started)
5. Jigsaw Multilingual Toxic Comment Classification: [https://www.kaggle.com/c/jigsaw-multilingual-toxic-comment-classification](https://www.kaggle.com/c/jigsaw-multilingual-toxic-comment-classification)
6. Google QUEST Q&A Labeling: [https://www.kaggle.com/c/google-quest-challenge](https://www.kaggle.com/c/google-quest-challenge)
7. Text Normalization Challenge: [https://www.kaggle.com/c/text-normalization-challenge-english-language](https://www.kaggle.com/c/text-normalization-challenge-english-language)
8. Natural Language Processing 2: [https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification](https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification)



