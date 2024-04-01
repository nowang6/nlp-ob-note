```python
import os
from transformers import LlamaTokenizer, LlamaForCausalLM

path = os.getenv("MODEL")
tokenizer = LlamaTokenizer.from_pretrained(path,trust_remote_code=True)
model = LlamaForCausalLM.from_pretrained(path,trust_remote_code=True)

inputs = tokenizer("The capital of the United States is Washington, D.C", return_tensors = "pt")
res = model(input_ids = inputs["input_ids"], labels = inputs["input_ids"])

```