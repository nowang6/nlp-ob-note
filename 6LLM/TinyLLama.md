
# Data

```sh
git clone https://huggingface.co/datasets/cerebras/SlimPajama-627B
python scripts/prepare_slimpajama.py --source_path /path/to/SlimPajama --tokenizer_path data/llama  --destination_path data/slim_star_combined --split validation --percentage 1.0
python scripts/prepare_slimpajama.py --source_path /path/to/SlimPajama --tokenizer_path data/llama  --destination_path data/slim_star_combined --split train --percentage 1.0
```