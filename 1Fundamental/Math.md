# 数
## 实数
有理数：可以用分号，小数表示
无理数：根号2， π，e等

## 虚数
i**2=-1

## 复数

形如a+bi（a、b均为实数）的数为复数，其中，a被称为实部，b被称为虚部，i为虚数单位。
i的平方等于-1

# 微积分
## 微分
函数在某一点的变化率/切线，某一点的导数

## 定积分
从a到b, 跟x轴的面积

```
∫a _bf(x)dx = F(b) - F(a)
```

t表示时间，v表示速度，面积表示这段时间行驶的距离

![xx|500](20230827132608.png)

## 牛顿求根发
$$
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
$$

求根号2，求解f(x)=x\*\*2 - 2， 在y=0点的根
猜测x<sub>0</sub>=2
x<sub>1</sub> = 2 - (2\*\*2-2)/2*2= 1.5



## 微积分
x（向量）是叶子节点，z（向量）是中间节点，y（标量）是输出节点
Tensor的属性，requires_grad， grad微分值，grad_fn微分函数
- 当叶子节点的requires_grad为True时，信息流过该节点，所有中间节点的requires_grad都变为true
- 只要在输出节点调用backward(), Pytorch就会自动更新叶子节点的微分值，存储在叶子节点的grad属性里
- 只有叶子节点的grad属性能被更新
### 梯度-前向传播
```python
x = torch.ones(2)
x.requires_grad=True
z= 4*x
tensor([4., 4.], grad_fn=<MulBackward0>) # tensor是一个矢量
y=z.norm()
tensor(5.6569, grad_fn=<LinalgVectorNormBackward0>) # tensor是一个标量
```
### 梯度-反向传播
tensor做计算都会产生计算图，用于反向传播，计算梯度
```python
x.backward() # 报错grad can be implicitly created only for scalar outputs， 只能作用于标量
y.backward()
x.grad
tensor([2.8284, 2.8284])
z.grad
y.grad
```

计算函数y=x*x的梯度
```python
a = torch.arange(-3,4, dtype=torch.float32)
a.requires_grad = True
b = a * a
c = b.norm()
c.backward()

print(a.grad)
tensor([-3.8571, -1.1429, -0.1429,  0.0000,  0.1429,  1.1429,  3.8571]) # 在0点的梯度为0， 2边梯度逐渐变大
```
**backward() 只能作用于标量，如果是矢量，需要增加一个参数gradient, gradientde的形状跟输出节点的形状保持一致，而且元素均值为1**
