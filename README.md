# 🚨 Network Intrusion Detection using Machine Learning (CIC-IDS2017)

This project focuses on building a Machine Learning–based **Intrusion Detection System (IDS)** using the **CIC-IDS2017** dataset.  
It includes a complete preprocessing pipeline, feature selection, normalization, and exploratory visualizations to prepare the data for classification models.

---

## 📌 Project Summary

The CIC-IDS2017 dataset contains several days of real network traffic including both **benign flows** and multiple **attack types** (DDoS, PortScan, Web Attacks, Botnet, Brute Force, etc.).  
Raw data is noisy, highly imbalanced, and contains redundant or corrupted numeric fields.  
Therefore, a strong preprocessing pipeline is essential before training ML models.

## ⚙️ Preprocessing Steps

- Loading and merging CIC-IDS2017 CSV files  
- Cleaning invalid values (INF, -INF, sensor errors, extremely large values)  
- Removing outliers **only from BENIGN traffic** using IQR  
- Reducing the feature space by removing highly correlated features (>0.95)  
- Merging very small attack classes into a single “RareAttack” category  
- Creating Train / Validation / Test splits  
- Scaling the data using **Standard**, **MinMax**, and **Robust** scalers  
- Computing class weights to address class imbalance  
- PCA visualization to observe traffic distribution  

## 📈 Model Performance (Results)

The performance of three machine learning models was evaluated using **5-Fold Cross-Validation**.  
Due to strong class imbalance in intrusion detection datasets, **macro-averaged metrics** are emphasized.

### 🔍 Evaluation Metrics
- **Precision (Macro)**
- **Recall (Macro)**
- **F1-score (Macro)** 
- **F1-score (Weighted)**
- **Overfit Gap** – difference between training and test macro F1

---

### 📊 Performance Comparison

| Model               | Precision (Macro) | Recall (Macro) | F1 (Macro) | F1 (Weighted) | Overfit Gap |
|--------------------|-------------------|----------------|------------|---------------|-------------|
| Logistic Regression | 0.7985            | 0.8887         | 0.7942     | 0.9889        | 0.0060      |
| Random Forest       | 0.8908            | 0.8685         | 0.8753     | 0.9987        | 0.1247      |
| XGBoost             | 0.9355            | 0.8881         | 0.8982     | 0.9987        | 0.0483      |

---



