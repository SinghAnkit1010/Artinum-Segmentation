# 3D MRI Atrium Segmentation

## Overview

This repository contains the code and information related to a project on Atrium segmentation using 3D MRI data stored in NIFTI (Neuroimaging Informatics Technology Initiative) file format. The goal of this project is to segment Atrium regions from 3D MRI scans of a patient using a UNet model.
## Dataset

- The 3D MRI data is stored in the NIFTI file format.
- The dataset consists of 20 MRI scans of patients with Atrium regions segmented.
- the following figure is a single slice of a MRI,after augmentation
  
![download (3)](https://github.com/SinghAnkit1010/Artinum-Segmentation/assets/103994994/d1309596-fb92-4b24-93bb-4acf8f1f3a12)

  

## Model

The U-Net model used in this project consists of an encoder-decoder architecture with skip connections. The encoder extracts features through convolutional blocks and downsampling (max-pooling) operations. The bottleneck layer further captures high-level representations. The decoder upsamples the feature maps and concatenates them with the corresponding skip connections from the encoder. The final layer predicts the probability of each pixel sigmoid activation function

## Preprocessing

The following preprocessing steps are applied to the 3D MRI data before training the UNet model:

1. **Normalization**: The pixel intensities in the MRI scans are normalized to have a consistent scale. This helps in improving the model's convergence during training.

2. **Standardization**: Standardization of pixel intensities is performed to give the data a zero mean and unit variance, which aids in faster and more stable training.

3. **Cropping**: The MRI scans are cropped to focus on the regions of interest, reducing unnecessary background information and minimizing computational complexity.

## Training

- The UNet model is trained on the preprocessed slices of MRIs.
- Training data and validation data are split from the dataset to evaluate model performance.
- The training process involves optimizing the model's parameters using an aploss Dice loss and Adam optimizer
- The model is trained for 30 epochs of  batch size 16.

## Evaluation

- The model's performance is evaluated using the Dice coefficient on the validation dataset.
- A Dice coefficient of 87% is achieved, indicating a strong performance in segmenting Artinum regions in 3D MRI scans.
- Following image shows model prediction of some slices of a 3D MRI
  
  ![download (2)](https://github.com/SinghAnkit1010/Artinum-Segmentation/assets/103994994/8645f2ea-6e7c-482e-8ede-43f0feb7c1f7)
  ![download](https://github.com/SinghAnkit1010/Artinum-Segmentation/assets/103994994/14b90aea-3e1f-4823-a8be-2f2b366c0660)

finally model is evaluated on test data,the following animation shows the segmentation of a 3D MRI of a person



https://github.com/SinghAnkit1010/Artinum-Segmentation/assets/103994994/95752222-68c2-4bcf-babd-ffd88feebed5


## Acknowledgments 
The model is trained on dataset taken from medicaldecathlon
https://drive.google.com/file/d/1wEB2I6S6tQBVEPxir8cA5kFB8gTQadYY/view?usp=sharing

## Author

- Include your name and contact information.

Feel free to customize this README file further to include additional details or instructions specific to your project.
