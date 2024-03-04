
# 概率论

## 条件概率
![[Pasted image 20230910215215.png]]


## 贝叶斯公式

![[Pasted image 20230910215138.png]]



## 高斯概率密度函数

![[Pasted image 20230910203403.png]]


## 条件概率和贝叶斯

A盒子：3黑，一共7
B 盒子：1黑，一共9

P(Black|BoxA):  已知巧克力来自A盒，请问黑色的概率
P(BoxA):  巧克力来自A盒的概率
P(Black and BoxA):  巧克力来自A盒，并且是黑色的概率
![[ml-1.png|500]]
已知来自A盒，黑色的概率？
![[ml-2.png|200]]

```
已知是黑色，来自A盒的概率？
P(BoxA | Black): 已知黑色，来自A盒的概率
P(Black):  黑色的概率, 全概率公式， 3/7*7/16 + 1/9 * 9/16
P(Black and BoxA)= P(Black | BoxA) * P(BoxA) = 3/7 * 7/16
```

![[ml-3.png|300]]


![[ml-4.png|200]]



# 信息论

## 交叉熵
- KL散度 = 交叉熵 - 熵
- 交叉熵永远大于熵，因为KL散度永远大于等于零
CrossEntropy Loss

## KL散度(相对熵)
