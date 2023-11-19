# LSTM
## Embedding
定义： 
embedding = nn.Embedding(vocab_size, embedding_size) # 单词数量，词向量维度

使用：
embedding = self.embedding(x)  
x输入[128,10] batch大小，每个batch的词数量
输出[128,10,100] batch大小，每个batch的词数量, 词向量维度


## LSTM层
定义
self.lstm = nn.LSTM(input_size=embedding_size,
                            hidden_size=256,
                            num_layers=2,
                            batch_first=True)
使用
out, _ = self.lstm(embedding)
输入为embedding
输出out， [batch_size, seq_len, hidden_size]   [128,10,256]
