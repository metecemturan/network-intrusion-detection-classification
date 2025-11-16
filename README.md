# 🚨 Network Intrusion Detection using Machine Learning (CIC-IDS2017)

This project focuses on building a Machine Learning–based **Intrusion Detection System (IDS)** using the **CIC-IDS2017** dataset.  
It includes a complete preprocessing pipeline, feature selection, normalization, and exploratory visualizations to prepare the data for classification models.

---

## 📌 Project Summary

The CIC-IDS2017 dataset contains several days of real network traffic including both **benign flows** and multiple **attack types** (DDoS, PortScan, Web Attacks, Botnet, Brute Force, etc.).  
Raw data is noisy, highly imbalanced, and contains redundant or corrupted numeric fields.  
Therefore, a strong preprocessing pipeline is essential before training ML models.

This project implements:

- Loading and merging CIC-IDS2017 CSV files  
- Cleaning invalid values (INF, -INF, sensor errors, extremely large values)  
- Removing outliers **only from BENIGN traffic** using IQR  
- Reducing the feature space by removing highly correlated features (>0.95)  
- Merging very small attack classes into a single “RareAttack” category  
- Creating Train / Validation / Test splits  
- Scaling the data using **Standard**, **MinMax**, and **Robust** scalers  
- Computing class weights to address class imbalance  
- PCA visualization to observe traffic distribution  

The final preprocessed dataset is ready for training models such as  
Random Forest, XGBoost, CatBoost, Logistic Regression, and SVM.

---

## 📊 Visualizations

The notebook generates several helpful plots, including:

- PCA scatter plot with class labels  
- Raw vs cleaned class distributions  
- Correlation heatmap  
- Heatmap of removed features  
- Histogram comparisons (before vs after cleaning)  
- Skewness analysis of numeric features  

These visualizations help understand dataset structure and validate each preprocessing step.



