# AdaSampah - ML Model for Garbage Classification
Sebuah proyek pembelajaran mesin untuk mengklasifikasikan sampah ke dalam 10 kategori yang berbeda menggunakan Convolutional Neural Networks (CNN) dengan pembelajaran transfer. 

---
## Overview
Proyek ini mengimplementasikan sistem klasifikasi sampah dengan menggunakan teknik deep learning. Model ini dapat mengklasifikasikan sampah ke dalam 10 kategori yang berbeda dan memberikan saran tentang bagaimana menangani (reuse, reduce, recycle) sampah tersebut. Setiap kelas mewakili jenis sampah dengan metode pembuangan atau pengolahan yang direkomendasikan.

---
## Dataset

Proyek ini menggunakan [dataset](https://www.kaggle.com/datasets/sudipp/garbage-dataset-9-classes/data) dari Kaggle dengan 10 kelas, yang berisi lebih dari 20.000 gambar yang didistribusikan:

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

### **Visualisasi untuk setiap kelas**
![classDistribution](/assets/classDistribution.png)


---
## Data Distribution
### Data Training
![dataTraining](/assets/dataTraining.png)
### Data Validation
![dataValidation](/assets/dataValidation.png)
### Data Test
![dataTest](/assets/dataTest.png)


## Model Architecture and Training

Model ini menggunakan **Transfer Learning** dengan MobileNetV2 sebagai base model:

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
- early_stop: Memantau kehilangan validasi dan menghentikan pelatihan lebih awal (pencegahan overfitting)
- reduce_lr: Memantau kehilangan validasi dan mengurangi laju pembelajaran hingga setengahnya (membantu dalam menyempurnakan pelatihan)

### Model Performance
- **Initial Training Accuracy**: 0.6499 (Epoch 1)
- **Final Training Accuracy**: 0.9951
- **Test Accuracy**: 0.95~
- **Optimizer**: Adam (learning_rate=0.001)
- **Loss Function**: Categorical Crossentropy

---




