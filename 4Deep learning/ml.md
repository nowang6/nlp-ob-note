回归，分类，聚类
![[Pasted image 20231028193522.png]]

# 回归
## 线性回归


# 分类
## 朴素贝叶斯
邮件，文本分类
训练过程：计算垃圾/非垃圾邮件里，每个词出现的概率
预测过程：每个词概率的乘积

## 逻辑回归 

最大熵的特例

# SVM支持向量机 
最大化间隔获得更好的分类边界

## 核函数


## 决策树 （分类）
综合各种机器学习算法





# 聚类

## KNN 
记住所有数据，通过多少表决进行分类
牧师的例子



# 感知机(PLA）

神经元的基本单位

# 优化理论

## 梯度
随机梯度下降：从样本集里，随机找一个数据算梯度，随机指选取数据的方式
梯度下降：把所有的样本的lost平均算一个梯度
Mini-batch/batch: 神经网络里采用的方便，小批量梯度下降，综合了随机和全量梯度的优点


# 生成模型
HMM

# 判别模型


# 损失的种类
## MSE 均方差损失
计算实际值与预测值之差的平方的平均值，用于评估预测的准确性
## MAE 平均绝对损失
计算实际值与预测值之差的绝对值的平均值

## 对数损失 / 交叉熵损失
评估分类模型的概率预测的准确性，值越小表示模型性能越好。**一般用于分类问题**

## 交叉熵损失


# 距离
## 欧式距离
## 曼哈顿距离
## cos距离，内积距离
## KL距离
不具备对称性，A与B的距离不等于B与A的距离
物理意义：信息量差异的加权求和
