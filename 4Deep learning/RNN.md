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


## Linner

self.fc = torch.nn.Linear(hidden_size*self.n_directions, output_size) 

## Forward

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


