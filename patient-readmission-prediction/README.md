
#  Patient Readmission Prediction

This project predicts whether a patient will be readmitted to the hospital within 30 days of discharge using clinical and demographic data. The goal is to help healthcare providers reduce unnecessary readmissions and improve patient outcomes.

---

## Objective

To classify patients based on their likelihood of being readmitted within 30 days post-discharge, using machine learning models trained on hospital records and patient attributes.

---

## Dataset Summary

- **Source**: UCI Diabetes 130-US hospitals dataset
- **Records**: ~100,000 hospital visits
- **Target variable**: `readmitted` (`<30`, `>30`, `NO`)
- **Features include**:
  - Patient demographics (age, race, gender)
  - Medical data (diagnosis codes, medications, procedures)
  - Hospitalization history (length of stay, number of inpatient visits)

---

## Exploratory Data Analysis

- Examined class imbalance: `<30 days` readmissions were the minority
- Top predictors included:
  - `time_in_hospital`
  - `number_inpatient`
  - `num_lab_procedures`
- Bar charts and pair plots helped reveal patterns in categorical and numerical features

---

## Data Preprocessing

- Removed high-cardinality and irrelevant columns (e.g., `weight`, `payer_code`, `medical_specialty`)
- Encoded categorical features using Label Encoding
- Converted `readmitted` to binary target: `1 = <30 days`, `0 = otherwise`
- Applied **SMOTE** for class balancing
- Train-test split: 80/20 with stratification

---

## Models Trained

| Model               | Description                             |
|--------------------|-----------------------------------------|
| Logistic Regression| Baseline interpretable linear classifier|
| Random Forest       | Tree-based ensemble, good for tabular data|
| XGBoost Classifier  | Gradient boosting model, best performer |

---

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

---

## Results

- **XGBoost** achieved the highest ROC-AUC and F1 score
- SMOTE helped improve recall on the minority class (readmissions)
- Feature importance from Random Forest and XGBoost provided useful insights

---

## Libraries Used

```bash
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
imblearn (SMOTE)
```
## Future Improvements
- Integrate sequence modeling (e.g., patient visit history using LSTM)

- Feature engineering for diagnosis and medication embeddings

- Model deployment as a clinical dashboard or API

- Test with time-based validation for generalizability
