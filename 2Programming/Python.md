# 环境
```
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
conda create --name llm python=3.9 -y
conda activate llm
pip install torch transformers
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

## 参数解析
```python
import argparse
parser = argparse.ArgumentParser()
parser.add_argument('--bert_path', help='config file', default='/home/data/tmp/bert-base-chinese')
args = parser.parse_args()
args.bert_path
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
### Starlette
web服务器

### pydantic
数据接口定义检查与设置管理的库,  第7课
https://www.bilibili.com/video/BV1iN411X72b?p=7&vd_source=f9f5dc62e3d675eacc7d6206b764e9eb


## matplotlib

### 画三维向量


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


# Jupter
```bash
pip install jupyterlab

nohup jupyter lab --ip 0.0.0.0 --port 8080 &
```

# PDF解析

![[Pasted image 20240208180623.png]]
# 并发编程
## 并发 vs  并行
并发：同一时刻，只有一个thread/task执行，thread对应threading库， task对应asyncio库， 应用于I/O操作频繁的场景， 比如爬虫。

并行：使用multi-processing启动多个进程，应用于CPU heavy的场景。

### 使用原则
如果是I/O bound，并且I/O操作很慢，需要很多任务/线程协同实现，那么使用Asyncio更合适。

如果是I/O bound，但是I/O操作很快，只需要有限数量的任务/线程，那么使用多线程Threading就可以了。

如果是CPU bound，则需要使用多进程来提高程序运行效率


# Pytorch 


## 工具
wisdom 可视化工具
np.meshgrdi
## 变量
tensor不能反向传播，variable可以反向传播
## Tensor (张量)


## Variable（变量）
variable(废弃)是封装了tensor并提供自动求导功能的对象
```python
from torch.autograd import Variable

```


