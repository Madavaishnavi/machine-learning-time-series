# Patient Readmission Prediction – Project Description

### Overview:

This project focuses on predicting patient readmission within 30 days after discharge using machine learning. The goal is to identify high-risk patients to help hospitals improve post-discharge care and reduce avoidable readmissions.

The dataset contains demographic, medical history, and hospital visit details of diabetes patients, including factors such as age, medications, and previous hospital visits.

#### Key Features:

##### Data Preprocessing:

- Handling missing values with imputation techniques. Encoding categorical variables for ML compatibility.Scaling numerical features using MinMaxScaler.

- Feature Engineering: Creating interaction terms like age * time_in_hospital. One-hot encoding key categorical variables.

- Class Imbalance Handling: Applied SMOTE & SMOTE-Tomek to balance minority classes.

Machine Learning Models Used:

Logistic Regression, 
Random Forest, 
XGBoost (Best Performing Model)

Model Evaluation:

- Precision, Recall, F1-Score, ROC-AUC, Confusion Matrix.
- Feature Importance Analysis to determine key risk factors.

Threshold Optimization:

- Used Precision-Recall curve to fine-tune the decision boundary.

File Descriptions

- patient readmission prediction.ipynb	Jupyter Notebook with full implementation of the project.

Results:

XGBoost performed best with an ROC-AUC of 0.67, indicating a moderate ability to predict readmission.

## Why is This Useful?

Reduces Healthcare Costs: Predicting patient readmission helps hospitals reduce penalties and costs associated with excessive readmissions.

Improves Patient Care: Identifies high-risk patients who need follow-up care.

Optimizes Resource Allocation: Helps hospitals prioritize patients needing intensive post-discharge care.

Next Steps

- Fine-tune models with advanced feature selection.
- Implement deep learning models (e.g., LSTMs).
- Deploy as an API using Flask or FastAPI.
