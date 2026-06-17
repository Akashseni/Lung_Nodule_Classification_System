Lung Nodule Classification using 3D Deep Learning
> **Binary classification of lung nodules into Benign and Malignant using 3D CT patch volumes, with ensemble inference and interpretability through Grad-CAM.**
![Confusion Matrix](images/confusion_matrix.png)
Overview
Lung cancer is one of the most serious and life-threatening diseases worldwide, and early analysis of pulmonary nodules can help support timely diagnosis. This project focuses on nodule-level classification rather than detection.
The model takes pre-extracted 3D CT nodule patches as input and predicts whether a nodule is:
Benign
Malignant
This repository contains a complete deep learning workflow for:
loading and preprocessing volumetric CT data,
training a custom 3D neural network,
handling class imbalance,
evaluating performance using clinically relevant metrics,
improving predictions through fold-wise ensembling and test-time augmentation,
visualizing model attention using Grad-CAM.
---
Key Highlights
3D volumetric classification
Binary output: Benign vs Malignant
Custom dual-path architecture
5-fold cross-validation
Ensemble inference
Test-Time Augmentation (TTA)
Class weighting / imbalance handling
Threshold tuning for better classification
Grad-CAM / interpretability support
Designed for medical imaging research and academic project presentation
---
Dataset
This project uses the LIDC-IDRI dataset, a public lung CT dataset with radiologist annotations.
Input Format
The notebook expects preprocessed NumPy arrays such as:
`X.npy` → 3D nodule patches
`X_large.npy` → larger contextual 3D patches
`y.npy` → binary labels
Label Mapping
`0` → Benign
`1` → Malignant
Typical Sample Structure
Each sample represents a lung nodule extracted from CT scans and converted into a 3D tensor suitable for deep learning.
---
Model Summary
The model is built to learn from both:
local nodule details
surrounding contextual tissue
This helps the network capture subtle differences between benign and malignant nodules.
The training pipeline includes:
3D CNN-based feature extraction
dual-input or multi-branch fusion
regularization for robust learning
fold-wise model saving
ensemble prediction across folds
---
Workflow
1. Data Loading
The notebook loads 3D patch data and labels from NumPy files.
2. Train/Validation/Test Split
The dataset is split carefully to evaluate generalization.
3. Model Training
The network is trained with:
weighted loss,
augmentation,
early stopping,
learning-rate scheduling,
fold-based validation.
4. Threshold Selection
Instead of using a fixed threshold blindly, the best decision threshold is selected from validation outputs.
5. Final Evaluation
The best model or ensemble is evaluated using:
accuracy,
precision,
recall,
F1-score,
confusion matrix.
6. Explainability
Grad-CAM is used to highlight the image regions that influence the prediction.
---
Results
The final evaluation on the test set achieved:
Metric	Value
Accuracy	90.98%
Benign Precision	94.41%
Benign Recall	92.12%
Benign F1-score	93.25%
Malignant Precision	84.34%
Malignant Recall	88.61%
Malignant F1-score	86.42%
Macro F1-score	89.84%
Weighted F1-score	91.04%
Confusion Matrix
Actual \ Predicted	Benign	Malignant
Benign	152	13
Malignant	9	70
Interpretation
The model correctly classifies most benign nodules.
Malignant recall is strong, which is important in medical classification.
The balance between benign and malignant performance makes the result more meaningful than accuracy alone.
---
Why This Project Is Useful
This project demonstrates skills in:
Deep learning
3D medical image processing
Binary classification
Model evaluation
Class imbalance handling
Ensemble learning
Interpretability with Grad-CAM
Python / TensorFlow / PyTorch / Keras-style workflow depending on the notebook version
It is suitable for:
GitHub portfolio
internship applications
resume projects
academic presentation
medical AI experimentation
---
Repository Structure
```text
├── fold-method-lung-nodule-classification.ipynb
├── README.md
├── requirements.txt
├── images/
│   ├── confusion_matrix.png
│   └── gradcam_example.png
├── data/
│   ├── X.npy
│   ├── X_large.npy
│   └── y.npy
└── models/
    ├── fold_0_model
    ├── fold_1_model
    ├── fold_2_model
    ├── fold_3_model
    └── fold_4_model
```
---
Installation
Install the required dependencies:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn torch torchvision
```
If the notebook uses TensorFlow/Keras instead of PyTorch, install:
```bash
pip install tensorflow keras
```
---
How to Run
Clone the repository.
Place the preprocessed `.npy` files in the expected data folder.
Open the notebook in Kaggle or Jupyter Notebook.
Run the cells step by step.
Train the model or load saved weights.
Evaluate the final predictions.
Generate the confusion matrix and Grad-CAM visualization.
---
Notes
This project works on pre-extracted 3D patches, not raw full CT scans.
The classification task is nodule-level malignancy prediction.
Metrics may vary slightly depending on the random seed, fold split, and threshold choice.
The reported results are based on the final test evaluation shown in the notebook.
---
Future Improvements
Possible next steps for this project:
train on larger 3D CT context volumes,
add attention-based fusion modules,
experiment with focal loss,
add calibration metrics,
compare against simpler 2D CNN baselines,
build a web demo using Streamlit or Gradio,
extend the system to detection and segmentation.
---
Acknowledgements
LIDC-IDRI dataset contributors
open-source deep learning libraries
Kaggle / notebook environment used for experimentation
---
License
This project is intended for educational and research purposes.
If you plan to publish or reuse it, add an appropriate license file to the repository.
---
