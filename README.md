# Optimizing ResNet Architecture for Image Classification: A Study on Parameter Efficiency

This repository contains the code and report for the study on fine-tuning strategies and hyperparameters to optimize the Residual Network (ResNet) architecture, specifically ResNet18, for image classification tasks using the CIFAR-10 dataset.

## Abstract

In this study, I explore various hyperparameters and optimization strategies to construct an efficient ResNet18 model for image classification on the CIFAR-10 dataset. My goal is to achieve high test accuracy while ensuring that the total number of trainable parameters does not exceed 5 million.

**Keywords**: AdamW, Data Augmentation, ResNet, Image Classification

## Overview

Residual Networks (ResNet) are a type of convolutional neural network (CNN) that utilize skipped connections or shortcuts to jump over some layers. This unique architecture allows ResNets to effectively learn from significantly more layers than traditional CNNs without the problem of vanishing gradients.

I experiment with various hyperparameters in the architecture, including the number of channels, filter size, kernel size in the skip connection, and the pool size in the average pool layer, among others. Additionally, I explore different optimization strategies, data augmentation techniques, regularization methods, and learning rate schedules to improve the performance of our model.

## Methodology

The ResNet architecture was implemented using the PyTorch framework. I trained three different models with varying configurations:

1. **First Model**:
   - Optimizer: Stochastic Gradient Descent (SGD) with momentum and weight decay.
   - Learning rate scheduling: Learning rate reduced by a factor of 0.1 every 10 epochs.
   - Number of epochs: 100

2. **Second Model**:
   - Optimizer: AdamW
   - Learning rate: 0.01
   - Learning rate scheduling: Learning rate reduced by a factor of 0.1 every 10 epochs.
   - Number of epochs: 80

3. **Third Model**:
   - Optimizer: AdamW*
   - Learning rate scheduling: Cosine Annealing
   - Data Augmentation: Heavy data augmentation
   - Number of epochs: 80

## How to Run

1. Clone this repository:

git clone https://github.com/BhairaviVSD/DeepLearning.git

2. Install the required dependencies

3. Run the code

## Results

### First Model (SGD)
- Test Accuracy: 91.11%

### Second Model (AdamW)
- Test Accuracy: 92.62%

### Third Model (AdamW with heavy data augmentation)
- Test Accuracy: 93.39%
