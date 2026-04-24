# 💳 Credit Card Fraud Detection

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![GitHub last commit](https://img.shields.io/github/last-commit/Mathsyuan/creditcard-fraud-detection)](https://github.com/Mathsyuan/creditcard-fraud-detection)

## 📌 Project Description

This project aims to detect fraudulent credit card transactions using **Machine Learning**. The main challenge is the **extreme class imbalance** (fraudulent transactions account for only ~0.17% of all transactions).

## 📊 Dataset

- **Source**: [Kaggle Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Time period**: September 2013 (European cardholders)
- **Size**: 284,807 transactions
- **Features**:
  - `V1` - `V28`: PCA-transformed anonymized features
  - `Time`: Seconds since the first transaction
  - `Amount`: Transaction amount
  - `Class`: 0 = legitimate, 1 = fraud

## 🎯 Methodology (8 Steps)

| Step | Description |
|------|-------------|
| ① | **EDA** - Time series analysis, correlation, interaction effects |
| ② | **Data Preprocessing** - RobustScaler, TimeSeriesSplit |
| ③ | **Handle Imbalance** - SMOTE, SMOTE+Tomek, Random Undersampling |
| ④ | **Feature Selection** - Chi-squared test, L1 regularization |
| ⑤ | **Model Training** - Logistic Regression, Random Forest |
| ⑥ | **Cross Validation** - Stratified K-Fold, TimeSeriesSplit |
| ⑦ | **Hyperparameter Tuning** - GridSearchCV |
| ⑧ | **Evaluation** - Precision-Recall curve, F1-score, ROC-AUC |

## 📈 Results

### Best Model: Random Forest (Tuned)

| Metric | Score |
|--------|-------|
| **Accuracy** | 99.94% |
| **Precision (Fraud)** | 74.68% |
| **Recall (Fraud)** | 78.67% |
| **F1-Score** | 76.62% |
| **ROC-AUC** | 98.24% |

### Sampling Methods Comparison

| Method | ROC-AUC | Recall (Fraud) | Precision (Fraud) |
|--------|---------|----------------|-------------------|
| Baseline (Imbalanced) | 0.945 | 66.67% | 98.04% |
| SMOTE | 0.953 | 74.67% | 96.55% |
| **SMOTE + Tomek** | **0.960** | 73.33% | 98.21% |
| Random Undersampling | 0.991 | 77.33% | 60.42% |

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Mathsyuan/creditcard-fraud-detection.git
cd creditcard-fraud-detection
