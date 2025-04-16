# Credit Card Fraud Detection using Machine Learning

This project explores a real-world credit card transaction dataset to identify fraudulent activity. It applies a variety of machine learning models, balancing techniques like SMOTE, and an ensemble Stacking Classifier to improve fraud detection accuracy in a highly imbalanced setting.

---

## Objective

To detect fraudulent transactions with **high precision** and **low false positives**, using a range of supervised and unsupervised models, and boost predictive performance through ensemble learning.

---

## Dataset Overview

- **Source**: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Transactions**: 284,807
- **Features**: 30 (anonymized)
- **Fraud Cases**: 492 (~0.17%)
- **Time Series**: Includes `Time` feature, used for time-based EDA and validation splits

---

## Exploratory Data Analysis (EDA)

- Detected **temporal trends** using `Time` column
- Visualized **fraud vs non-fraud distributions**
- Boxplots, correlation heatmaps, and PCA-based variance analysis
- Observed **class imbalance** 

---

## Preprocessing

- **SMOTE** for oversampling minority (fraud) class
- Feature **scaling** with `StandardScaler`
- **PCA** (Principal Component Analysis) tested for dimensionality reduction
- Created **train/test split** using stratification and time-aware slicing

---

## Models Trained

| Model                  | Type               | Description                                  |
|------------------------|--------------------|----------------------------------------------|
| Logistic Regression    | Supervised         | Baseline linear classifier                   |
| Decision Tree          | Supervised         | Simple model, interpretable splits           |
| Random Forest          | Supervised         | Ensemble of trees with improved accuracy     |
| K-Nearest Neighbors    | Supervised         | Distance-based model                         |
| Support Vector Machine | Supervised         | High-dimensional boundary optimization       |
| XGBoost                | Supervised         | Gradient boosting with tree-based models     |
| Isolation Forest       | Unsupervised       | Anomaly detection approach                   |
| **Stacking Classifier**| **Ensemble**       | Combines all above models for final prediction |

---

## Stacking Classifier (Final Model)

- Combined base models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - KNN
  - SVM
  - XGBoost  
- Final Estimator: Logistic Regression / XGBoost  
- Significantly improved **F1-score** and **AUC**

---

## Evaluation Metrics

| Metric         | Best Model (Stacking) |
|----------------|------------------------|
| Accuracy       | 99.4%                  |
| Precision      | 92%                    |
| Recall         | 87%                    |
| F1-Score       | 89%                    |
| ROC-AUC        | **0.92**               |

> SMOTE helped boost **recall** substantially, enabling more frauds to be detected.

---

## Libraries Used

```bash
scikit-learn
xgboost
imblearn
matplotlib
seaborn
numpy
pandas
```
## Key Takeaways
- Class imbalance is a critical challenge in fraud detection

- Ensemble learning, especially stacking, provided superior performance

- SMOTE + XGBoost outperformed individual classifiers

- Isolation Forest is useful for anomaly-based scenarios but less accurate here

- Proper feature scaling and stratified splits are essential for performance

## Future Improvements

- Use advanced imbalance handling (e.g., ADASYN, GAN-based oversampling)

- Test with real-time streaming data (Kafka/Spark)

- Deploy final model as a REST API using FastAPI or Flask

- Explore deep learning architectures like AutoEncoders or LSTM for time modeling
