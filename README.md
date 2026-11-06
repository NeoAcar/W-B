# W&B MNIST demo

`wandb_demo.ipynb` trains a PyTorch CNN on MNIST and demonstrates W&B runs, metrics, sweeps, and model artifacts. MNIST is downloaded into `data/` on first use.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook wandb_demo.ipynb
```

Select the environment as the notebook kernel and sign in to W&B. Half of the official 60,000 training images are selected and split into 24,000 training and 6,000 validation examples; the official 10,000-image test set is kept separate.

W&B's local files live under `runs/wandb/`; model checkpoints are stored at `runs/<run-id>/model.pt`, and downloaded artifacts under `runs/artifacts/`. The final cell loads `mnist-cnn:latest` from W&B after a training run has uploaded it.

The second training example currently sets 1,000 epochs and can take a very long time on MNIST. Sweeps and artifact downloads require an online W&B connection.
