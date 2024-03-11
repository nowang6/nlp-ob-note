# 向量的运算

## 加和减

![[Screen Shot 2023-08-27 at 4.11.18 PM.png|500]]

##  哈达玛积（Hadamard Product）
对应元素乘积， 结果是一个向量，在反向传播和梯度下降中使用
```
a = torch.arange(20, dtype=torch.float32).reshape(5, 4)
b = a.clone()
c = a * b
tensor([[  0.,   1.,   4.,   9.],
        [ 16.,  25.,  36.,  49.],
        [ 64.,  81., 100., 121.],
        [144., 169., 196., 225.],
        [256., 289., 324., 361.]])
```

##  点积（Dot Product）结果是矢量
对应元素乘积的和， 结果是一个标量
点积>=0
0, 正交
```python 
torch.dot(x, y) == torch.sum(x * y)
```

物理：做的功
```
（a,b).(c,d) = a*c + b*d
```
跟矩阵的乘法是相通的
```
(a,b)  .  (c,  =a*c+b*d
           d)     
```

![[Screen Shot 2023-08-27 at 4.14.44 PM.png]]


## 叉积（Cross Product）

仅适用于三维向量
![[Screen Shot 2023-08-27 at 4.16.44 PM.png]]

# 矩阵
## 矩阵乘向量torch.mv， 结果为向量
```python
a = torch.arange(20, dtype=torch.float32).reshape(5, 4)
b = torch.arange(4, dtype=torch.float32)

tensor([[ 0.,  1.,  2.,  3.],
        [ 4.,  5.,  6.,  7.],
        [ 8.,  9., 10., 11.],
        [12., 13., 14., 15.],
        [16., 17., 18., 19.]])

tensor([ 0.,  1.,  2.,  3.])

torch.mv(a, b)
tensor([ 14.,  38.,  62.,  86., 110.])

```

## 矩阵乘矩阵torch.mm， 结果为矩阵
```python
a = torch.arange(20, dtype=torch.float32).reshape(5, 4)
b = torch.arange(20, dtype=torch.float32).reshape(4, 5)
tensor([[ 0.,  1.,  2.,  3.],
        [ 4.,  5.,  6.,  7.],
        [ 8.,  9., 10., 11.],
        [12., 13., 14., 15.],
        [16., 17., 18., 19.]])

tensor([[ 0.,  1.,  2.,  3.,  4.],
        [ 5.,  6.,  7.,  8.,  9.],
        [10., 11., 12., 13., 14.],
        [15., 16., 17., 18., 19.]])
torch.mm(a,b)
```

## 矩阵的秩 - 极大线性无关组
![[Pasted image 20230909181453.png]]


## 矩阵的乘法

前行乘后列， 前面的第一行，乘以后面的第三列
![[Pasted image 20230909170157.png]]

向量乘矩阵

a1 * b
a2 * b
a3 * b


![[Pasted image 20230923165405.png]]


## 已知基底，求向量的坐标

![[Pasted image 20230909173346.png]]

# 范数

## 二范数和夹角

![[2023-08-271.png | 500]]
![[Screen Shot 2023-08-27 at 4.33.29 PM.png|300]]


```python
u = torch.tensor([3.0, -4.0])
torch.norm(u)

#计算向量夹角
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

cos_angle = np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))
angle = np.arccos(cos_angle)

#余弦相似度
import torch.nn.functional as F

vec1 = torch.FloatTensor([1, 2, 3, 4])
vec2 = torch.FloatTensor([5, 6, 7, 8])

cos_sim = F.cosine_similarity(vec1, vec2, dim=0)
```

## 计算2个点之间的距离
```python
a = torch.tensor([3.0, -4.0])
b = torch.tensor([1,1])
res = torch.norm(a-b)
```


## 标准正交基


# 资料
https://mp.weixin.qq.com/s/zOp7JvpmQDToCUHEcmokyw


# 其他

## 共现矩阵 / co-occurrence matrix

