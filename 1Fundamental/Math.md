
# 实数和复数

形如a+bi（a、b均为实数）的数为复数，其中，a被称为实部，b被称为虚部，i为虚数单位。
i的平方等于-1


# 微积分
## 定积分
从a到b, 跟x轴的面积

```
∫a _bf(x)dx = F(b) - F(a)
```

t表示时间，v表示速度，面积表示这段时间行驶的距离

![xx|500](20230827132608.png)





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
CrossEntropy Loss


# 函数

### Sigmoid函数 (0,1)之间
它的导数，正态分布

$\frac{1} {1 + e^(-x) }$

```python
def sigmoid(x):  
    return 1/(1 + np.exp(-x))

x = np.linspace(-10, 10, 100)  
y = sigmoid(x)  
plt.plot(x, y)  
plt.xlabel("x")  
plt.ylabel("Sigmoid(X)")  
plt.show()

```

## tanh函数取值（-1，1）
, 多用于循环神经网络
```python
x = np.linspace(-10, 10, 100)
y = np.tanh(x)
plt.plot(x, y)
plt.show()
```


## softmax函数
多用于分类
``` python
def softmax(x):
	e_x = np.exp(x)
	return e_x / e_x.sum(axis=0)
	
x = np.array([1.0, 2.0, 3.0])
softmax_x = softmax(x)
print(softmax_x)

```

## 似然估计
### 对数似然
把概率的乘积转换为加法
