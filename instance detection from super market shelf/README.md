# Image Processing and Computer Vision Project

## Overview
This repository contains various scripts and notebooks for an image processing and computer vision project. The project focuses on feature detection, denoising, and instance identification in image scenes. It is divided into several parts, each addressing different aspects of the task. Detailed methodologies, analysis, and conclusions are provided.

## Repository Structure

- **task_definition.ipynb**: Definition of the domain of the task.
- **IPCV1_1_FINAL.ipynb**: Contains the main code for part 1.1 of the task.
- **IPCV1_2_FINAL.ipynb**: Contains the main code for part 1.2 of the task.
- **DnCNN_denoiser.ipynb**: Contains the code for the Denoising Convolutional Neural Network (DnCNN).
- **denoiser_with_median&bilateral_filters.ipynb**: Contains the code for denoising images using median and bilateral filters.
- **description.pdf**: Detailed description of the tasks and methodologies used.

## Task Breakdown

### Part 1: Feature Detection and Matching

#### 1.1 Feature Detection and Matching
- **Objective**: Detect keypoints and match features between model and scene images using SIFT and FLANN-based matcher.
- **Steps**:
  1. **Denoising**: Images of models and scenes are denoised using Gaussian filters.
  2. **Keypoint Extraction**: SIFT method is used to extract keypoints and descriptors.
  3. **Feature Matching**: Features are matched using the FLANN matcher with k-NN search.
  4. **Homography Calculation**: Homography transformation matrix is computed to map points between model and scene images.
  5. **Non-Maximum Suppression (NMS)**: Applied to filter out redundant detections and retain the best-scoring matches.

- **Analysis and Conclusions**:
  - The method works well for images in scenes 1-5 but struggles with scenes 6-12.
  - The key challenges include the need for hyperparameter tuning and the limitations of the FLANN matcher in more complex scenes.

#### 1.2 Instance Identification
- **Objective**: Identify all instances of objects in images using a grid-based method.
- **Steps**:
  1. **Boundary Box Detection**: Initial boundary boxes are detected using methods from part 1.1.
  2. **Brute Force Algorithm**: For detected instances, grids are placed adjacent to each detection to find new instances.
  3. **ZNCC Score Calculation**: Zero-Normalized Cross-Correlation scores are used to evaluate similarity between instances and grids.
  4. **Threshold and IoU Filtering**: Thresholds are applied to ZNCC scores, and high Intersection over Union (IoU) values are filtered out.
  5. **Grid Adjustment**: Grid positions are refined within a neighborhood to find the best match.
  6. **Final Filtering and NMS**: Final thresholds and NMS are applied to select the best grids.

- **Analysis and Conclusions**:
  - The method is effective in detecting repeated items on shelves, leveraging the similarity in dimensions and appearance of adjacent products.
  - The use of ZNCC proved advantageous despite its challenges, offering a balance between speed and accuracy.
  - The approach successfully identified all instances with a low rejection rate, although managing grids and filters was time-consuming.

### Denoising Part

#### DnCNN Denoiser
- **Objective**: Denoise images using a Denoising Convolutional Neural Network (DnCNN).
- **Steps**:
  1. **Dataset Preparation**: BSDS500 dataset is loaded and Gaussian noise is added.
  2. **Model Training**: The DnCNN model is trained to reconstruct original images from noisy inputs.

- **Analysis and Conclusions**:
  - The DnCNN method effectively denoised images, demonstrating the potential of deep learning models for complex denoising tasks.
  - The approach outperformed traditional filters but required substantial computational resources and training time.

#### Median and Bilateral Filters
- **Objective**: Address denoising issues in specific scenes using median and bilateral filters.
- **Steps**:
  1. **Median Filter**: Applied to remove salt-and-pepper noise.
  2. **Bilateral Filter**: Used to preserve edges while reducing noise.
  3. **Parameter Testing**: Combinations of filter parameters were tested to optimize results for specific scenes.

- **Analysis and Conclusions**:
  - Median and bilateral filters provided a simple yet effective solution for scenes with specific types of noise.
  - The bilateral filter's sensitivity to parameters across different images posed a challenge, requiring careful tuning for optimal performance.
  - The combined use of these filters with the CNN denoiser improved detection accuracy in problematic scenes.

## Conclusion
The methods implemented in this project aim to achieve robust feature detection, matching, and denoising in complex image scenes. Despite some challenges, the approaches provide a foundation for further improvements and applications in real-world scenarios. The project highlights the importance of tailored solutions for different aspects of image processing tasks, from feature detection to denoising.

## References
- [DnCNN GitHub Repository](https://github.com/ocimakamboj/DnCNN)

## Usage
Clone the repository and navigate through the notebooks to understand and execute the code for each part of the project.

```bash
git clone https://github.com/pm78p/MachineLearning-instance.detection-classification/
cd MachineLearning-instance.detection-classification/instance detection from super market shelf
