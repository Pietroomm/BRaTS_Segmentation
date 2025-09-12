# BraTS 2D Lesion-Centered MRI Segmentation

This repository contains the implementation of a brain tumor segmentation task on the BraTS dataset, using 2D slices of MRI scans with four modalities: T1, T1ce, T2, and T2-FLAIR. Our project improves upon the original implementation by optimizing hyperparameters, enhancing the model, and addressing critical limitations.
This project is aimed at segmenting different tumor tissues in MRI scans, including:

## Project Overview
- Tumor Core
- Enhancing Tumor
- Whole Tumor

## Dataset
The dataset consists of 2D lesion-centered MRI slices:

- Slices: 00, 01, and 10.
- Modalities:
  - T1-weighted
  - T1-contrast-enhanced (T1ce)
  - T2-weighted
  - T2 Fluid Attenuated Inversion Recovery (T2-FLAIR)

Ground truth masks are provided as 3-channel tensors indicating tumor tissue types.

## Key Features

1-  Enhanced Data Pipeline
  - Selected T1ce and FLAIR modalities for best segmentation performance.
  - Applied data augmentation (random flips, Gaussian noise, brightness adjustments, zoom) for training robustness.
  - Split dataset into training (70%), validation (20%), and test (10%).

2- Improved Model
  - Used a UNet architecture with:
    -Two input channels for modalities.
    - Instance normalization.
    - Optimized hyperparameters using Optuna (dropout, learning rate).
  - Increased maximum filters to 512 and included a learning rate scheduler.
    
3- Hyperparameter Tuning
  - Automated tuning with Optuna for dropout and learning rate.
    
4- Quantitative Evaluation
  - Metrics: Dice loss, Dice score, IoU, Precision, Recall.
  - Achieved strong results across all slices.
