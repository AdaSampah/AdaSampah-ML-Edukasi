# AdaSampah - ML Model for Garbage Classification

A machine learning project for classifying garbage into 10 different categories using Convolutional Neural Networks (CNN) with transfer learning. 

---
## Overview
This project implements a garbage classification system using deep learning techniques. The model can classify waste items into 10 different categories and give a suggestion on how to handle (reuse, reduce, recycle) said waste. Each class represents a type of waste with its own recommended method of disposal or treatment.

---
## Dataset

The project uses a [dataset](https://www.kaggle.com/datasets/sudipp/garbage-dataset-9-classes/data) from Kaggle with 10 classes, containing over 20,000 images distributed across:

1. battery: 1889
2. biological: 1982
3. cardboard: 2328
4. clothes: 2106
5. glass: 2011
6. metal: 1789
7. paper: 2310
8. plastic: 1993
9. shoes: 1977
10. trash: 1644 (general waste that couldn't be grouped)

![classDistribution]("assets/classDistribution.png")

---
## Data Distribution
### Data Training
### Data Validation
### Data Test


## Model Architecture and Training

The model uses **Transfer Learning** with MobileNetV2 as the base model:

### Model Configuration
- **Base Model**: MobileNetV2 (pre-trained on ImageNet, frozen layers)
- **Input Shape**: 256×256×3 RGB images
- **Additional Layers**:
  - 4 CNN layers with BatchNormalization and MaxPooling
  - Flatten layer
  - Dense layer (128 units) with ReLU activation
  - Dropout layer (0.3)
  - Output layer (10 units) with Softmax activation

### Training Parameters
**Optimizer**: Adam (learning rate: 0.001)
**Loss Function**: Categorical Crossentropy.
**Epochs**: 10
**Callbacks**: 
- early_stop: Monitors validation loss and stops training early (overfitting preventions)
- reduce_lr: Monitors validation loss and reduces learning rate by half (helps in fine-tune training)

### Model Performance
- **Initial Training Accuracy**: 0.6499 (Epoch 1)
- **Final Training Accuracy**: 0.9951
- **Test Accuracy**: 0.95~
- **Optimizer**: Adam (learning_rate=0.001)
- **Loss Function**: Categorical Crossentropy

---




