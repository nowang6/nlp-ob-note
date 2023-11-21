# TorchText
## 文件处理

```python
import torchdata.datapipes as dp

FILE_PATH = 'data\\train.tsv'
data_files = dp.iter.FileOpener([FILE_PATH], mode='rb')
data_pipe = data_files.parse_csv(skip_lines=1, delimiter='\t', as_tuple=True)

for sample in data_pipe:
    print(sample)
```


## 构建词典
```python
import io
from torchtext.datasets import AG_NEWS
from torchtext.data.utils import get_tokenizer
from torchtext.vocab import build_vocab_from_iterator

tokenizer = get_tokenizer("basic_english")
# from file
def yield_tokens(file_path):
  with io.open(file_path, encoding = 'utf-8') as f:
    for line in f:
      yield tokenizer(line.strip())
vocab = build_vocab_from_iterator(yield_tokens("data\\datasets\\AG_NEWS\\train.csv"), specials=["<unk>", "<pad>"])

# from datasets
train_iter = AG_NEWS(root="data",split='train')
def yield_tokens(data_iter):
  for _, text in data_iter: 
    yield tokenizer(text) 
vocab = build_vocab_from_iterator(yield_tokens(train_iter), specials=["<unk>", "<pad>"])
```

# Forward函数

model(data)之所以等价于model.forward(data)，就是因为在类（class）中使用了__call__函数

