# LatentCOT

chain-of-thought in latent space instead of token space. base model is llama-3.2-1B, trained on gsm8k and synthetic multiplication.

normally the model has to verbalize each reasoning step. here the reasoning happens as continuous embeddings between the prompt and the final answer, and only the answer itself gets decoded back to tokens. training uses an MSE loss on the latent steps and a standard CE loss on the answer.

## running

```
pip install -r requirements.txt
wandb login
python sft/latent_cot_sft.py -c configs/latent_cot_sft/4x4/<config>.yaml
```

training scripts are in `sft/`, eval in `eval/`, configs in `configs/`, slurm launchers in `run/`.

— joseph
