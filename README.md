# 🍊 Orange Defect Detection and Spoilage Estimation using Machine Learning & Deep Learning

## 📌 Project Overview

This project develops a **computer vision pipeline** to detect and classify **different types of orange defects** and estimate the **spoilage percentage** of the fruit.

Fruit quality inspection is an important task in the agriculture and food supply chain. Traditionally, fruit inspection is done manually, which is **time-consuming, inconsistent, and subjective**.  

This project uses **Machine Learning and Deep Learning techniques** to automate the process of fruit defect detection.

Two different approaches were implemented and compared:

1. **Classical Machine Learning** using handcrafted features and Support Vector Machine (SVM)
2. **Deep Learning** using a pretrained Convolutional Neural Network (MobileNetV2)

The system also estimates the **spoilage severity percentage** based on the predicted defect type.

---

# 📂 Dataset

The dataset contains images of oranges belonging to **four different classes** representing fruit health conditions.

| Class | Description |
|------|-------------|
| Blackspot | Fungal infection causing dark spots |
| Canker | Bacterial disease affecting citrus fruits |
| Fresh | Healthy oranges |
| Greening | Severe citrus disease |

### Dataset Size

| Dataset | Images |
|--------|--------|
| Training | 991 |
| Testing | 99 |

Dataset Link:
https://drive.google.com/drive/folders/1ndQzEiMmiUViYZIiQHt5IJK-ENsxXjlq?usp=sharing


---

# 🧠 Project Pipeline

The overall workflow of the system is shown below:
Dataset
↓
Data Preprocessing
↓
Feature Extraction
↓
SVM Model
↓
CNN Model (MobileNetV2)
↓
Model Evaluation
↓
Spoilage Percentage Estimation

---

# 🔍 Data Analysis

## Class Distribution

The dataset shows **moderate class imbalance**.

| Class | Images | Percentage |
|------|-------|-----------|
| Blackspot | 184 | 18.57% |
| Canker | 179 | 18.06% |
| Fresh | 281 | 28.36% |
| Greening | 347 | 35.02% |

Class imbalance can affect model performance since models may learn dominant classes better.

---

## Image Size Analysis

Images in the dataset have different resolutions:

- Minimum size: **138 × 144**
- Maximum size: **800 × 800**
- Average size: **661 × 671**

To maintain consistency, all images were **resized to 224 × 224 pixels** before training.

---

# 🔄 Data Augmentation

To improve model generalization and reduce overfitting, the following augmentation techniques were used:

- Rotation
- Horizontal Flip
- Zoom
- Width Shift
- Height Shift

This increases dataset diversity without collecting additional images.

---

# ⚙️ Approach 1: Classical Machine Learning (SVM)

## Feature Extraction

Two types of features were extracted from images:

### Color Features
Mean RGB values representing average color information of the fruit.

### Texture Features
Local Binary Pattern (LBP) used to capture texture patterns related to fruit defects.

Total features extracted per image:
3 color features + 10 texture features = 13 features

## Model Used

Support Vector Machine (SVM) with **RBF kernel**.

### Why SVM?

- Works well with small to medium datasets
- Effective in high dimensional spaces
- Can model non-linear decision boundaries

## SVM Model Performance

Accuracy achieved:83%

---

# 🤖 Approach 2: Deep Learning (CNN)

A **MobileNetV2 Convolutional Neural Network** was used with **transfer learning**.

## Why MobileNetV2?

- Lightweight architecture
- Pretrained on ImageNet
- Works well with smaller datasets
- Faster training

## CNN Architecture
MobileNetV2 Base Model
↓
Global Average Pooling
↓
Dense Layer (128 neurons)
↓
Softmax Output Layer (4 classes)

The base model layers were **frozen**, and only the final classification layers were trained.

## Training Details

| Parameter | Value |
|----------|-------|
| Image Size | 224 × 224 |
| Epochs | 10 |
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |

---

# 📊 Model Performance

| Model | Accuracy |
|------|---------|
| SVM | 83% |
| CNN (MobileNetV2) | 94–96% |

The CNN model significantly outperformed the classical SVM model because CNNs automatically learn **complex visual patterns** from images.

---

# 🍊 Spoilage Percentage Estimation

Each defect type was mapped to an estimated spoilage severity level.

| Class | Spoilage Percentage |
|------|---------------------|
| Fresh | 0% |
| Blackspot | 50% |
| Canker | 70% |
| Greening | 90% |

### Example Prediction
Predicted Class: Blackspot
Estimated Spoilage: 50%


This provides a practical estimate of fruit quality for real-world applications.

---

# 📊 Example Outputs

### Confusion Matrix (CNN Model)

(Add image)

### Training Accuracy & Loss

(Add training plot)

---

# 🛠 Technologies Used

- Python
- OpenCV
- TensorFlow / Keras
- Scikit-learn
- NumPy
- Matplotlib
- Seaborn
- Google Colab

---


# 🚀 Future Improvements

Possible improvements for this project include:

- Increasing dataset size
- Fine-tuning pretrained CNN layers
- Using advanced architectures (ResNet, EfficientNet)
- Real-time defect detection using camera input
- Deploying the model as a **web or mobile application**

---

# 👨‍💻 Author

**Ojas Yeole**

📧 Email: ojasyeole1271@gmail.com  

🔗 LinkedIn  
https://www.linkedin.com/in/ojasyeole/

💻 GitHub  
https://github.com/ojasssss  

🌐 Portfolio  
https://ojas-yeole-data-rgi3390.gamma.site/

---

# ⭐ If you found this project useful, please consider giving it a star!
