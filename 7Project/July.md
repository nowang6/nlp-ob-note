
# Alpaca-Lora

```bash
python -u finetune.py \
--base_model '/root/autodl-tmp/llama-7b-hf' \
--data_path '/root/autodl-tmp/alpaca-cleaned' \
--output_dir './lora-alpaca'
```

# Review GPT

```bash

apt-get install openmpi-bin libopenmpi-dev zip

conda create -n longqlora python=3.10.13


pip install torch==2.1.2
pip install packaging
pip install flash_attn
pip install bitsandbytes
pip install transformers==4.37.2
pip install accelerate peft loguru
pip install deepspeed
pip install SentencePiece
pip install protobuf 
pip install tensorboard
pip install mpi4py
pip install einops


rm /opt/conda/envs/longqlora/compiler_compat/ld
scp -P 41175 -r My-LongQLoRA-main.zip root@40.135.94.101:/root -L 8080:localhost:8080

ssh -p  root@ -L 8080:localhost:8080
```


```
absl-py==2.1.0
accelerate==0.28.0
annotated-types==0.6.0
bitsandbytes==0.43.0
certifi==2024.2.2
charset-normalizer==3.3.2
deepspeed==0.14.0
einops==0.7.0
filelock==3.13.1
flash-attn==2.5.6
fsspec==2024.3.0
grpcio==1.62.1
hjson==3.1.0
huggingface-hub==0.21.4
idna==3.6
Jinja2==3.1.3
loguru==0.7.2
Markdown==3.6
MarkupSafe==2.1.5
mpi4py==3.1.5
mpmath==1.3.0
networkx==3.2.1
ninja==1.11.1.1
numpy==1.26.4
nvidia-cublas-cu12==12.1.3.1
nvidia-cuda-cupti-cu12==12.1.105
nvidia-cuda-nvrtc-cu12==12.1.105
nvidia-cuda-runtime-cu12==12.1.105
nvidia-cudnn-cu12==8.9.2.26
nvidia-cufft-cu12==11.0.2.54
nvidia-curand-cu12==10.3.2.106
nvidia-cusolver-cu12==11.4.5.107
nvidia-cusparse-cu12==12.1.0.106
nvidia-nccl-cu12==2.18.1
nvidia-nvjitlink-cu12==12.4.99
nvidia-nvtx-cu12==12.1.105
packaging==24.0
peft==0.9.0
protobuf==5.26.0
psutil==5.9.8
py-cpuinfo==9.0.0
pydantic==2.6.4
pydantic_core==2.16.3
pynvml==11.5.0
PyYAML==6.0.1
regex==2023.12.25
requests==2.31.0
safetensors==0.4.2
sentencepiece==0.2.0
six==1.16.0
sympy==1.12
tensorboard==2.16.2
tensorboard-data-server==0.7.2
tokenizers==0.15.2
torch==2.1.2
tqdm==4.66.2
transformers==4.37.2
triton==2.1.0
typing_extensions==4.10.0
urllib3==2.2.1
Werkzeug==3.0.1
```

# 3月份辅导e
Build a Large Language Model (From Scratch) (manning.com)](https://www.manning.com/books/build-a-large-language-model-from-scratch)



阿里data-juicer

![[Pasted image 20240318194511.png]]


[OpenCompass](https://opencompass.org.cn/home)