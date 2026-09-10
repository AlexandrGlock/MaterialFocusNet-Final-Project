# MaterialFocusNet: Household Waste Classification

**Student:** Abdullayev Namig  
**Course:** Deep Learning Final Project

## Project summary

MaterialFocusNet is a custom PyTorch convolutional neural network for classifying a single household-waste item in an image as cardboard, glass, metal, paper, plastic, or trash. The project compares MaterialFocusNet with a simpler baseline CNN on the public TrashNet dataset.

## Live Colab notebook

[Open the completed Google Colab notebook](https://colab.research.google.com/drive/11XVpxZEz2z1RzJpUQywqjCbJDPmSs-6V)

## Final held-out test results

| Model | Accuracy | Macro Precision | Macro Recall | Macro F1 |
|---|---:|---:|---:|---:|
| Baseline CNN | 69.74% | 68.81% | 69.56% | 69.02% |
| MaterialFocusNet | **72.63%** | **71.82%** | **71.26%** | **71.43%** |

MaterialFocusNet improves macro F1 by 2.41 percentage points over the baseline.

## Repository files

- `MaterialFocusNet_TrashNet_Final_Project.ipynb`: structured PyTorch notebook source.
- `MaterialFocusNet_Video_Presentation_Abdullayev_Namig.pptx`: presentation for the recorded project video.

## Method

- Dataset: TrashNet, 2,527 RGB images in six classes.
- Split: reproducible stratified 70% training, 15% validation, 15% held-out testing.
- Preprocessing: 224 x 224 images, training-only normalization, crop, flip, rotation, and colour-jitter augmentation.
- Custom model: convolutional blocks with Batch Normalization, ReLU, dropout, and Squeeze-and-Excitation channel attention.
- Training: AdamW, weighted cross-entropy loss, batch size 32, maximum 60 epochs, and validation macro F1 checkpoint selection.

## Dataset source

TrashNet: https://github.com/garythung/trashnet
