# Image Processing and Computer Vision Project

## Overview
This repository contains various scripts and notebooks for an image processing and computer vision project. The project focuses on feature detection, denoising, and instance identification in image scenes. It is divided into several parts, each addressing different aspects of the task. Detailed methodologies, analysis, and conclusions are provided.

## Repository Structure

- **task_definition.ipynb**: Definition of the domain of the task.
- **IPCV2_FINAL_RESULTS.ipynb**: Contains the final results and analysis of the task.
- **description.pdf**: Detailed description of the tasks and methodologies used.
- **Other Notebooks**: Contains background works and tests related to the project.

## Task Breakdown

### Part 1: Feature Detection and Matching

#### DenseNet-like Architecture with Transfer Learning
- **Architecture**:
  - Custom DenseNet structure with initial convolutional layer, dense blocks, transition layers, and global average pooling followed by a fully connected layer.
  - Pre-trained on ImageNet and fine-tuned on the specific dataset.
- **Training Strategy**:
  - Optimizer: AdamW with learning rate scheduling.
  - Early Stopping to prevent overfitting.
- **Analysis and Conclusions**:
  - Achieved significant accuracy improvements through custom DenseNet architecture and transfer learning.
  - The model was effective in detecting features and matching them across different image scenes.

### Part 2: Data Augmentation and Regularization Techniques

#### MixCut Augmentation and Regularization
- **Techniques**:
  - MixCut Augmentation: Combines parts of two images to create new training samples.
  - Regularization: Applied dropout, weight decay, and gradient clipping to prevent overfitting.
- **Observations**:
  - MixCut and regularization techniques improved the generalization of the model.
  - Applied to the transfer learning model, these techniques helped achieve robust performance.

## Denoising Part


## Results Overview

### Model Architecture and Training
- **Base Model**: ResNet-18 pre-trained on ImageNet, adjusted for 43 classes.
- **Class Balancing**: Used class weights to handle class imbalance.
- **Data Augmentation**: Implemented Mixup augmentation to improve robustness.
- **Training Enhancements**: Applied gradient clipping and used AdamW optimizer with learning rate schedulers.
- **Early Stopping**: Implemented to halt training when validation loss stopped improving.
- **Hyperparameter Tuning**: Experimented with various learning rates, weight decays, and schedulers.

### Evaluation and Performance
- **Accuracy and Loss**: Tracked both training and validation accuracy and loss to monitor performance.
- **Final Results**:
  - Achieved significant improvements in validation accuracy through persistent experimentation and innovative techniques.
  - Final model met the project's accuracy requirements, demonstrating substantial improvement from initial attempts.

## Conclusion
Despite numerous challenges and setbacks, including lost data and initially low accuracy, we achieved our target accuracy through persistent experimentation and innovative techniques such as ensemble learning, DenseNet architecture, and transfer learning. Our final model met the project's accuracy requirements, demonstrating significant improvement from our initial attempts.

## References
- [DnCNN GitHub Repository](https://github.com/ocimakamboj/DnCNN)

## Usage
Clone the repository and navigate through the notebooks to understand and execute the code for each part of the project.

```bash
git clone https://github.com/pm78p/MachineLearning-instance.detection-classification/
cd MachineLearning-instance.detection-classification/classification-super market product
