# EE-5102/CS-6304 — Assignment 0: Advanced Topics in Machine Learning

**Name:** Mubeen Ahmed  
**Roll No:** 25280101  
**Course:** EE-5102/CS-6304 — Advanced Topics in Machine Learning  
**Assignment:** PA 0  
**Repository:** [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME](https://github.com/YOUR_USERNAME/YOUR_REPO_NAME)  
**Report:** [`report/neurips_report.pdf`](report/neurips_report.pdf)

---

## Overview

This repository contains the implementation, experiments, and analysis for **Assignment 0** of **EE-5102/CS-6304 — Advanced Topics in Machine Learning**.

The assignment covers foundational deep learning topics through four practical tasks:

1. **ResNet and Transfer Learning**
2. **Vision Transformers and Self-Attention Visualization**
3. **CLIP Zero-Shot Classification and Modality Gap Analysis**
4. **Variational Autoencoders on MNIST**

The goal of this assignment is to demonstrate reproducible machine learning experiments, proper documentation, model analysis, and a professional reporting format.

---

## Assignment Deliverables

This repository includes:

- Jupyter notebooks for all required tasks
- Experiment logs and saved figures where applicable
- Checkpoints and reusable artifacts where applicable
- A NeurIPS-style report
- Instructions to reproduce the experiments

---

## Task Summary

| Task | Notebook | Description |
|---|---|---|
| Task 1 | [`Task1_RESNET.ipynb`](Task1_RESNET.ipynb) | ResNet-152 experiments, residual connections, feature visualization, and transfer learning |
| Task 2 | [`Task2_ViT.ipynb`](Task2_ViT.ipynb) | Vision Transformer inference, attention visualization, patch masking, and linear probing |
| Task 3 | [`Task3_CLIP.ipynb`](Task3_CLIP.ipynb) | CLIP zero-shot classification on STL-10, prompt comparison, and modality gap analysis |
| Task 4 | [`Task4_VAE.ipynb`](Task4_VAE.ipynb) | MLP Variational Autoencoder on MNIST, latent-space analysis, reconstruction, generation, and Doersch comparison |

---

## Task 1: ResNet and Transfer Learning

**Notebook:** [`Task1_RESNET.ipynb`](Task1_RESNET.ipynb)

This task investigates the internal behavior and transfer-learning performance of ResNet models.

### Main Experiments

- Baseline fine-tuning using ResNet-152
- Residual connection analysis by disabling skip connections in selected layers
- Feature extraction and visualization using t-SNE
- Transfer learning comparison:
  - Frozen backbone with trainable classifier
  - Fine-tuning only the final block
  - Fine-tuning the full backbone
  - Training from random initialization

### Key Analyses

- Effect of skip connections on training stability and accuracy
- Quality of learned representations
- Comparison between pretrained and randomly initialized models
- Generalization performance on CIFAR-10

---

## Task 2: Vision Transformer and Attention Visualization

**Notebook:** [`Task2_ViT.ipynb`](Task2_ViT.ipynb)

This task explores a pretrained Vision Transformer model and analyzes its self-attention behavior.

### Model Used

- `google/vit-base-patch16-224`

### Main Experiments

- Image classification using a pretrained ViT
- CLS-token attention extraction
- Attention map overlay on input images
- Per-head attention visualization
- Patch-masking robustness experiment
- Linear probing using:
  - CLS token features
  - Mean-pooled patch features

### Key Analyses

- Which image regions receive high attention from the ViT
- Whether attention aligns with the predicted object
- Effect of masking central patches versus random patches
- Comparison of CLS-token and mean-pooled representations

---

## Task 3: CLIP Zero-Shot Classification and Modality Gap

**Notebook:** [`Task3_CLIP.ipynb`](Task3_CLIP.ipynb)

This task uses OpenAI CLIP for zero-shot classification and investigates the image-text modality gap.

### Dataset

- STL-10

### CLIP Model

- `ViT-B/32`

### Main Experiments

- Zero-shot classification using:
  - Plain class labels
  - Simple template prompts
  - Descriptive prompts
- Prompting strategy comparison
- Image-text embedding visualization
- Modality gap analysis
- Procrustes alignment between image and text embeddings
- Classification accuracy before and after alignment
- 2D embedding visualization using:
  - UMAP
  - t-SNE

### Key Analyses

- Effect of prompt design on zero-shot accuracy
- Separation between image and text embeddings
- Whether Procrustes alignment reduces the modality gap
- Effect of alignment on classification performance

---

## Task 4: Variational Autoencoder

**Notebook:** [`Task4_VAE.ipynb`](Task4_VAE.ipynb)

This task implements a basic MLP Variational Autoencoder on MNIST and analyzes its latent space, reconstructions, and generations.

### Dataset

- MNIST

### Main Experiments

- MLP VAE implementation
- Training with ELBO loss:
  - Reconstruction loss
  - KL divergence loss
- Latent-space visualization
- Reconstruction analysis
- Sample generation from the prior distribution
- Comparison across different latent dimensions:
  - `latent_dim = 2`
  - `latent_dim = 10`
  - `latent_dim = 20`
- Comparison with Doersch’s VAE tutorial implementation

### Key Analyses

- Latent-space structure and class separation
- Reconstruction quality for different latent dimensions
- Generated digit quality
- Effect of latent dimensionality on ELBO, reconstruction loss, and KL loss
- Discussion of Doersch’s claim about VAE insensitivity to latent dimensionality

---

## Repository Structure

```text
.
├── README.md
├── Task1_RESNET.ipynb
├── Task2_ViT.ipynb
├── Task3_CLIP.ipynb
├── Task4_VAE.ipynb
│
├── report/
│   └── neurips_report.pdf
│
├── data/
│   ├── cifar10/
│   ├── mnist/
│   └── stl10/
│
├── checkpoints/
│   └── saved model checkpoints
│
├── logs/
│   └── training and evaluation logs
│
└── figures/
    └── saved plots and visualizations
