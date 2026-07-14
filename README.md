<div align="center">

# 🚀 BlueprintAI

### Fine-Tuning of Stable Diffusion using LoRA for Aerospace Engineering Blueprint Generation

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-red.svg)](https://pytorch.org/)
[![Diffusers](https://img.shields.io/badge/Diffusers-HuggingFace-yellow.svg)](https://github.com/huggingface/diffusers)
[![Transformers](https://img.shields.io/badge/Transformers-HuggingFace-orange.svg)](https://huggingface.co/)
[![LoRA](https://img.shields.io/badge/LoRA-Low--Rank%20Adaptation-success.svg)](https://arxiv.org/abs/2106.09685)
[![Stable Diffusion](https://img.shields.io/badge/Stable%20Diffusion-v1.5-purple.svg)](https://huggingface.co/runwayml/stable-diffusion-v1-5)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00.svg)](https://colab.research.google.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Fine-tuning of **Stable Diffusion v1.5** using **LoRA (Low-Rank Adaptation)** to generate **technical aerospace engineering blueprints** from textual prompts.

Developed for the course **Generative Artificial Intelligence and Multimodal Models** at **Centro Universitário de Brasília (UniCEUB)**.

</div>

---

# 📖 Overview

BlueprintAI specializes the Stable Diffusion model to generate engineering-style technical drawings inspired by aerospace documentation.

Instead of reproducing artistic styles, the model learns the visual characteristics of engineering blueprints using public-domain technical illustrations from NASA.

The project demonstrates the complete workflow of:

- Dataset construction
- Caption engineering
- LoRA fine-tuning
- Diffusers training pipeline
- Image generation
- Hugging Face model publication

---

# Features

- Stable Diffusion v1.5
- LoRA Fine-Tuning
- Engineering Blueprint Style
- Aerospace Technical Illustrations
- NASA Public Domain Dataset
- Hugging Face Diffusers
- Google Colab Training
- Prompt Conditioning
- Reproducible Training Pipeline

---

# 🏗 Project Architecture

```text
                    NASA Public Domain Images
                               │
                               ▼
                     Dataset Construction
                               │
                               ▼
                   Manual Caption Generation
                               │
                               ▼
                    metadata.jsonl Creation
                               │
                               ▼
                Stable Diffusion v1.5 + LoRA
                               │
                               ▼
                  Fine-Tuning using Diffusers
                               │
                               ▼
                    Trained LoRA Weights
                               │
                               ▼
                  Aerospace Blueprint Images
```

---

# 📂 Repository Structure

```text
BlueprintAI/

│
├── dataset/
│   ├── images/
│   ├── captions/
│   ├── metadata.jsonl
│   └── fontes.csv
│
├── notebooks/
│   ├── 01_dataset.ipynb
│   ├── 02_training.ipynb
│   └── 03_evaluation.ipynb
│
├── lora/
│
├── docs/
│
├── assets/
│
├── README.md
├── requirements.txt
└── LICENSE
```

---

# 📊 Dataset

The dataset was manually curated using **22 technical aerospace engineering illustrations**.

All images originate from **public-domain NASA archives** and **Wikimedia Commons**, respecting copyright and licensing requirements.

Every sample contains:

- source URL
- author
- license
- manually reviewed caption
- training token

The token adopted for the project is:

```text
estilo_blueprint_aeroespacial
```

---

## Dataset Example

| ID | Object | Source | License | Caption |
|----|--------|--------|----------|----------|
|001|Landsat 1 Technical Drawing|NASA|Public Domain|estilo_blueprint_aeroespacial, blueprint engineering drawing of the Landsat 1 Earth observation satellite, orthographic projection, black line drawing, white background|
|002|Landsat 4-5 Technical Drawing|NASA|Public Domain|estilo_blueprint_aeroespacial, blueprint engineering drawing of the Landsat 4 and 5 Earth observation satellite, orthographic projection|
|003|Earth Observation Satellite|NASA|Public Domain|estilo_blueprint_aeroespacial, blueprint engineering drawing of an Earth observation satellite, orthographic engineering illustration|
|004|Apollo Technical Diagram|NASA|Public Domain|estilo_blueprint_aeroespacial, blueprint engineering drawing of the Apollo spacecraft structural layout|
|005|Landsat Detailed Schematic|NASA|Public Domain|estilo_blueprint_aeroespacial, detailed blueprint engineering drawing of an Earth observation spacecraft platform|

**Total images:** 22

---

# ⚙️ Training Configuration

| Parameter | Value |
|------------|------:|
| Base Model | Stable Diffusion v1.5 |
| Method | LoRA |
| Resolution | 512 × 512 |
| Batch Size | 1 |
| Gradient Accumulation | 4 |
| Learning Rate | 1e-4 |
| Scheduler | Cosine |
| Rank | 8 |
| Precision | FP16 |
| Training Steps | 1000 |

Training was performed using the official **Hugging Face Diffusers** implementation on **Google Colab (Tesla T4 GPU)**.

---

# 🖼 Results

The trained LoRA successfully learned the visual characteristics of engineering blueprint illustrations, producing images with:

- orthographic projection
- technical documentation aesthetics
- monochromatic engineering lines
- aerospace structural layouts
- blueprint-style representations

Example prompts:

```text
estilo_blueprint_aeroespacial, futuristic satellite blueprint
```

```text
estilo_blueprint_aeroespacial, spacecraft propulsion system
```

```text
estilo_blueprint_aeroespacial, lunar exploration vehicle
```

*(Generated examples can be found in the `results/` directory.)*

---

# 🤗 Hugging Face

The trained LoRA weights are available at:

https://huggingface.co/JaysagABRIELLY/blueprint-aerospace-lora

---

# Installation

Clone the repository

```bash
git clone https://github.com/el-pitchula/BlueprintAI.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Requirements

Main libraries

```text
torch
diffusers
transformers
accelerate
datasets
peft
huggingface_hub
bitsandbytes
safetensors
Pillow
numpy
pandas
matplotlib
```

---

# 📚 References

- NASA Image Library
- NASA Science Image Gallery
- Wikimedia Commons
- Hugging Face Diffusers
- Stable Diffusion v1.5
- Hu et al. (2021) — LoRA: Low-Rank Adaptation of Large Language Models

---

# ⚖️ Ethical Considerations

This project exclusively uses public-domain engineering illustrations.

No copyrighted artistic styles or living artists were imitated during training.

The generated images are intended solely for educational and research purposes.
