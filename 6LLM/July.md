# 第一阶段
## 训练三阶段
SFT（Supervised Fine-Tuning）监督微调
RM（Reward Model）
PPO（Proximal Policy Optimization）
RLHF (Reinforcement Learning from Human Feedback)
University of Colorado Boulder


# Alpaca-Lora微调

https://github.com/tloen/alpaca-lora

```bash

python -u finetune.py \
--base_model '/home/niwang/llm/llama-7b-hf' \
--data_path '/home/niwang/llm/alpaca-cleaned' \
--output_dir '/home/niwang/llm/lora-alpaca' \
```


# 环境

``` bash
export XDG_CACHE_HOME = /cache
export CACHE_HOME = /cache
export MODELSCOPE_CACHE = /cache/modelscope/hub
```


# 模型

llama-7b-hf
MiniGPT-4
moss-moon-sft-int4