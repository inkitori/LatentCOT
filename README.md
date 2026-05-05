# LatentCOT

chain-of-thought in latent space instead of token space. llama-3.2-1B, trained on gsm8k and synthetic multiplication.

normally the model has to verbalize each reasoning step. we sft the model instead to learn a superposition of embeddings to compress the reasoning chains

## running

```
pip install -r requirements.txt
wandb login
python sft/latent_cot_sft.py -c configs/latent_cot_sft/4x4/<config>.yaml
```

training scripts are in `sft/`, eval in `eval/`, configs in `configs/`, slurm launchers in `run/`.
