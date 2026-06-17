# 🫁 Lung Nodule Classification using 3D Dual-Path Deep Learning

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red)
![Medical Imaging](https://img.shields.io/badge/Domain-Medical%20Imaging-green)
![Accuracy](https://img.shields.io/badge/Accuracy-90.98%25-success)

</div>

---

## 📌 Overview

This project presents a deep learning framework for automated lung nodule classification using CT scan data from the LIDC-IDRI dataset.

The model classifies pulmonary nodules into:

- Benign
- Malignant

A custom 3D dual-path architecture is used to simultaneously learn:

- Fine-grained nodule characteristics
- Surrounding anatomical context

The framework incorporates:

- 5-Fold Cross Validation
- Ensemble Learning
- Test Time Augmentation (TTA)
- Attention-Based Feature Fusion
- Grad-CAM++ Explainability

---

## 🎯 Results

### Overall Performance

| Metric | Score |
|----------|----------|
| Accuracy | **90.98%** |
| Benign Recall | **92.12%** |
| Malignant Recall | **88.61%** |
| Benign Precision | **94.41%** |
| Malignant Precision | **84.34%** |
| Macro F1 Score | **89.27%** |

---

## 📊 Confusion Matrix

| | Predicted Benign | Predicted Malignant |
|---|---:|---:|
| Actual Benign | 152 | 13 |
| Actual Malignant | 9 | 70 |

Total Test Samples: **244**

Correct Predictions: **222**

---

## 🏗 Architecture

Input CT Volume
↓
Small Patch Branch
↓
3D CNN Encoder

Large Patch Branch
↓
3D CNN Encoder

↓
Feature Fusion Gate
↓
Classification Head
↓
Benign / Malignant

---

## ✨ Key Features

- 3D Volumetric Analysis
- Dual-Path Feature Extraction
- Attention-Based Fusion
- Center-Focused Supervision
- Test-Time Augmentation
- Ensemble Prediction
- Class Imbalance Handling
- Grad-CAM++ Visualization
- ROC-AUC Based Model Selection

---

## 📂 Dataset

Dataset: LIDC-IDRI

The dataset contains:

- Thoracic CT Scans
- Radiologist Annotations
- Nodule Malignancy Ratings
- Benign and Malignant Labels

---

## 🔄 Training Pipeline

1. CT Scan Preprocessing
2. Nodule Patch Extraction
3. Data Augmentation
4. 5-Fold Training
5. Model Ensembling
6. Test-Time Augmentation
7. Grad-CAM++ Analysis

---

## 🛠 Technologies Used

- Python
- PyTorch
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- Kaggle GPU Environment

---

## 📈 Future Improvements

- Transformer-Based Architectures
- Multi-Scale Attention Mechanisms
- Patient-Level Classification
- Clinical Metadata Integration
- Web-Based Deployment

---

## 👨‍💻 Author

Akash Senigarapu

Artificial Intelligence & Machine Learning

Chaitanya Bharathi Institute of Technology (CBIT)
