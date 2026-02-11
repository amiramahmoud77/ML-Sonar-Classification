# PCA-Powered Sonar Signal Classifier for Naval Security

## Overview
This project classifies sonar signals as either **Mines (M)** or **Rocks (R)** using **Principal Component Analysis (PCA)** for dimensionality reduction and **Logistic Regression** for binary classification.

The main goal is to reduce noise from 60 correlated features while maintaining high accuracy for underwater threat detection.

---

## Dataset
- **Source:** [UCI Machine Learning Repository – Connectionist Bench (Sonar, Mines vs. Rocks)](https://archive.ics.uci.edu/ml/datasets/connectionist+bench+sonar+mines+vs.+rocks)
- **Samples:** 208
- **Features:** 60 numerical sonar measurements
- **Classes:** 
  - `M` (Mine) – 111 samples  
  - `R` (Rock) – 97 samples

---

## Methodology

### 1. Data Loading & Preprocessing
- Loaded dataset directly from UCI repository  
- Encoded classes (`R=0`, `M=1`) using `LabelEncoder`  
- Standardized features with `StandardScaler`  

### 2. Exploratory Data Analysis (EDA)
- Scatter plots, histograms, correlation heatmap, boxplots  
- Checked class distribution  
- Found high correlation among features, indicating noise  

### 3. Principal Component Analysis (PCA)
- Applied **SVD-based PCA**  
- Reduced dimensionality from 60 features to 20 principal components  
- Captured ~88.4% of the variance  
- Visualization showed better class separation after PCA  

### 4. Model Training
- **Algorithm:** Logistic Regression (`C=10`, `max_iter=1000`)  
- **Data Split:** 80/20 train-test split with stratification  

### 5. Performance
- **Accuracy:** 90.48%  
- **ROC AUC:** 0.90  
- **Precision / Recall / F1-score:** ~0.90 (balanced)  
- **Confusion Matrix:** Only 4 misclassifications out of 42 test samples  

---

## Technologies Used
- **Python**  
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`  
  - Logistic Regression  
  - PCA (via SVD)  
  - Performance metrics  

---

## Conclusion
This project demonstrates that **dimensionality reduction via PCA** significantly improves classification performance by removing noisy correlated features. The trained Logistic Regression model achieves high accuracy in detecting underwater mines versus rocks, making it suitable for naval security applications.
