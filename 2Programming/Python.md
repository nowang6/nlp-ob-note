# 环境
```
conda create --name llm python=3.9 -y
conda activate d2l
pip install torch==1.12.0
pip install torchvision==0.13.0
pip install d2l==0.17.6
```

```
pip freeze > requirement.txt
```

```bash
jupyter lab --ip='*' --port=8701 --notebook-dir='/home/niwang' --no-browser
```

# Pandas
华映量云
输出每个地区销售最好的产品名称和总销售量，以及销售最好的产品的购买者姓名和购买量
```csv
region,customer,product,quantity,price
Beijing,A,P1,2,100
Beijing,A,P2,4,200
Shanghai,B,P1,1,100
Shanghai,C,P2,3,200
Beijing,B,P3,2,150
Shanghai,C,P3,1,150
```

``` python
df = pd.read_csv('data.csv')
cities = df['region'].drop_duplicates()
s = df.groupby(['region','product'])['quantity'].sum()
best_prods = []
for city in cities:
    best_prod_in_city = s[(city)].idxmax()
    best_prods.append(best_prod_in_city)
    best_prod_quantity_in_city = s[(city)].max()

print("%s best product: %s, quantity: %s" % (city, best_prod_in_city, best_prod_quantity_in_city))
print(df[df['product'].isin(best_prods)])
```

# 基础

## Iterators and Iterables
[Python 迭代器(Iterators and Iterables) - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/527777736)

## Map函数

``` python
def chen(x:int, y:int):
    return x*y
a = (1,2,3,4,5)
b = (1,2,3,4,5)
c = list(map(chen,a,b))

print (c)
```

## Filter 函数

```Python
def is_double(x:int):
    return x%2 == 0
a = (1,2,3,4,5)
c = list(filter(is_double,a))
print (c)
```

## Reduce 函数
```Python
from functools import reduce

a = [1, 2, 3, 4, 5]

def add(x, y):
    return x + y
print(reduce(add, a))
```


## 闭包和装饰器

```
在函数嵌套（函数里面再定义函数）的前提下
内部函数使用了外部函数的变量（参数）
外部函数的返回值是内部函数的引用
```

装饰器是一种闭包


# 框架

## FastAPI
pydantic
数据接口定义检查与设置管理的库,  第7课
https://www.bilibili.com/video/BV1iN411X72b?p=7&vd_source=f9f5dc62e3d675eacc7d6206b764e9eb


## matplotlib

### 画三维向量

```

```


### sigmod函数

```Python
import numpy as np
	def sigmoid(x):
	return 1/(1 + np.exp(-x))

x = -1
sigmoid_x = sigmoid(x)

print(sigmoid_x)

import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 100)
y = sigmoid(x)
plt.plot(x, y)
plt.xlabel("x")
plt.ylabel("Sigmoid(X)")
```

## Pytest

**（1）.py测试文件必须以“test_”开头（或“_test”结尾）**

**（2）测试类必须以Test开头，并且不能有init方法**

**（3）测试方法必须以“test_”开头**

（4）断言必须使用assert**



# Debug

python -m pdb linked-list-cycle.py

```
n  #执行下一行
b 33 #第33行插入短点
c  #执行到断点
s  #进入函数
bt #查看函数调用链
p 变量名 #输出变量值

where 当前的调用stack
up 跳到上面一个调用stack
down 进入下面一个调用stack

help
help (up) 查看help的帮助文档
```



|命令|解释|
|---|---|
|break 或 b 设置断点|设置断点|
|continue 或 c|继续执行程序|
|list 或 l|查看当前行的代码段|
|step 或 s|进入函数|
|return 或 r|执行代码直到从当前函数返回|
|exit 或 q|中止并退出|
|next 或 n|执行下一行|
|pp|打印变量的值|
|help|帮助|


# Pandas

传ArrayLik ,  是竖起来的
```python
s = pd.Series(list("abc"))  
df = pd.DataFrame(s)

   0
0  a
1  b
2  c

```
传Series列表，是躺着的
```python
s = pd.Series(list("abc"))  
df = pd.DataFrame([s,s])

   0  1  2
0  a  b  c
1  a  b  c
```