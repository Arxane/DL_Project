# FedBiP: Heterogeneous One-Shot Federated Learning with Personalized Latent Diffusion Models

This is the official code repository for the CVPR 2025 paper titled "FedBiP: Heterogeneous One-Shot Federated Learning with Personalized Latent Diffusion Models". Please do not hesitate to reach out for any questions.


## Installation Instructions

This code has been verified with python 3.9 and CUDA version 11.7. To get started, navigate to the `InterpretDiffusion` directory and install the necessary packages using the following commands:

```bash
git clone git@github.com:HaokunChen245/FedBiP.git
cd FedBiP
pip install -r requirements.txt
pip install -e diffusers
```

## Data Preparation
Download the dataset and put them in the ``/data`` der
* PACS: https://huggingface.co/datasets/flwrlabs/pacs


## Training
* Concept-level personalization
```bash
bash train.sh
```

* Image Generation
```bash
bash generate.sh
```

* Classification Model Training
```bash
bash clf_train.sh
```

## Performance & Communication Optimizations
This repository has been optimized for low-bandwidth communication and minimal VRAM usage:

VQ-VAE Integration: Replaced the standard KL-Autoencoder with a discrete VQ-VAE to compress the latent space representation and reduce quantization artifacts during parameter transfer.

Native 16-bit Precision: All model weights, embeddings, and gradients are explicitly cast to fp16 (or bf16), reducing network communication payloads by 50%.

## Citing our work
If our work has contributed to your research, we would greatly appreciate an acknowledgement by citing us as follows:
```
@article{chen2024fedbip,
  title={Fedbip: Heterogeneous one-shot federated learning with personalized latent diffusion models},
  author={Chen, Haokun and Li, Hang and Zhang, Yao and Bi, Jinhe and Zhang, Gengyuan and Zhang, Yueqi and Torr, Philip and Gu, Jindong and Krompass, Denis and Tresp, Volker},
  journal={arXiv preprint arXiv:2410.04810},
  year={2024}
}
 
