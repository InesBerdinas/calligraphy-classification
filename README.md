# Calligraphy Classification using EfficientNet-B0

This repository contains the notebooks, trained weights, and inference pipeline used for writer identification from handwriting samples using transfer learning.

## Dataset

The dataset It was collected and processed manually and it is hosted on Hugging Face:

**Dataset:** https://huggingface.co/datasets/InesBerdinas/calligraphy-classification-dataset

The dataset is organized into training, validation, and test splits, with samples belonging to five different writers:

* Persona_01
* Persona_02
* Persona_03
* Persona_04
* Persona_05

## Model

The project uses **EfficientNet-B0** pre-trained on ImageNet as the backbone architecture.

The training process was performed in two stages:

1. **Feature Extraction:** only the classification head was trained while keeping the convolutional backbone frozen.
2. **Fine-Tuning:** selected layers of the backbone were unfrozen and further optimized on the handwriting dataset.

## Repository Contents

* `Training_and_Validation.ipynb` – Training, validation, feature extraction, and fine-tuning, Profiling and Optimization.
* `Inference.ipynb` – Inference pipeline and model evaluation.
* `feature_extraction_weights.pth` – Weights obtained after feature extraction.
* `fine_tuning_weights.pth`  – Final fine-tuned model weights.

## Requirements

Main dependencies:

* Python
* PyTorch
* Torchvision
* NumPy
* Matplotlib
* Hugging Face Hub

## Reproducibility

The inference notebook automatically:

1. Downloads the dataset from Hugging Face.
2. Downloads the trained weights from this repository.
3. Loads the EfficientNet-B0 architecture.
4. Performs predictions on handwriting samples from the test set.

## Author

María Inés Berdiñas
