# 归一化函数

## SigMoid 二分类

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


## SoftMax 多分类

## Batch Norm

## Layer Norm

### RMS Norm
RMS Norm是一般LayerNorm的一种变体，可以在梯度下降时令损失更加平滑，与layerNorm相比，RMS Norm的主要区别在于去掉了减去均值的部分(re-centering)，只保留方差部分(re-scaling)

# 激活函数


## Relu

## SwiGLU
x*SigMoid


### Sigmoid函数 (0,1)之间

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

# RNN


## LSTM
### Embedding
定义： 
embedding = nn.Embedding(vocab_size, embedding_size) # 单词数量，词向量维度

使用：

embedding = self.embedding(x)  

x输入[128,10] batch大小，每个batch的词数量

输出[128,10,100] batch大小，每个batch的词数量, 词向量维度



### LSTM层
定义

self.lstm = nn.LSTM(input_size=embedding_size,
                            hidden_size=256,
                            num_layers=2,
                            batch_first=True)
使用

out, _ = self.lstm(embedding)

输入为embedding

输出out， [batch_size, seq_len, hidden_size]   [128,10,256]


### Linner

self.fc = torch.nn.Linear(hidden_size*self.n_directions, output_size) 

### Forward

embedding = nn.Embedding(vocab_size, embedding_size) 

embedding = self.embedding(x) 

输出：[batch_size, seq_len, embedding_size] 




batch_size = x.size(0)

hidden = self.init_hidden(batch_size)

输出：[layers, batch_size, hidden_size] 




lstm_out, hidden_out = self.lstm(embeds, hidden)

hidden_out: [layers, batch_size, hidden_size]

hidden_cat = torch.cat([hidden_out[-1], hidden_out[-2]], dim=1)

hidden_cat: [50*512]  [batch_size, hidden_size*n_directions]



fc_output = self.fc(hidden_cat)
fc_output = [batch_size, out_size]


