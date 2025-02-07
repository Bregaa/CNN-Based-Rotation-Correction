# CNN-Based Rotation Correction

## Introduction
This project explores the use of Convolutional Neural Networks (CNNs) for predicting and correcting image rotations. Initially focusing on quarter-turn rotations (0°, 90°, 180°, 270°), the project compares different CNN-based approaches, including hand-crafted CNNs, feature extraction, and fine-tuning. The best-performing method is then extended to handle full-range rotations (0° to 360°).

## How to Use

### Setting Up the Environment
1. **Google Colab**: Open the provided notebook in Google Colab. You can place the notebook in any directory within your Colab environment.

2. **Dataset**: 
   - Download the dataset zip file (and the two extensions), extract it and re-zip it into a single compressed file with the same name (rotation_dataset.zip), and upload it to the root folder of your Google Drive (`myDrive`). The compressed folder had to be divided to avoid GitHub's 100MB maximum file size.
   - Do not rename the dataset's zip file.

3. **Pre-Computed Models and Results**:
   - If you want to use pre-computed models and results, download the "BRC Models" folder and place it in the root folder of your Google Drive (`myDrive`).
   - This folder contains trained models and results that can be directly used for inference or further analysis.

## Results Recap

### Quarter-Turn Rotations (0°, 90°, 180°, 270°)
- **Hand-Crafted CNN**: Achieved **98% accuracy** on the test set, outperforming feature extraction and fine-tuning approaches.
  - Misclassifications were rare and often clustered around specific images, indicating potential dataset limitations (generalization).

- **Feature Extraction with SVM**: Achieved **81-82% accuracy**, struggling to distinguish between 90° and 270° rotations due to insufficient feature information.

- **Fine-Tuned CNN**: Achieved **96% accuracy** after extensive fine-tuning, but required significant computational effort and time. Before un-freezing the base network, it struggled similarly to the features extraction approach.

### Full-Range Rotations (0° to 360°)
- **Hand-Crafted CNN**: Adapted for full-range rotation prediction, achieving an **average error of 27°**.
  - The model was modified to output rotation values in a continuous circular space, avoiding discontinuities in predictions.
  - Results were promising but highlighted the need for a larger and more diverse dataset and a better architectural approach for further improvement.