
# Weather Forecasting using Statistical Regression Modeling

This project applies statistical regression techniques to model and forecast the **maximum daily temperature** using multivariate weather observations. By leveraging historical meteorological features—including cloud cover, solar radiation, humidity, and precipitation—the analysis constructs an interpretable **linear regression model** to evaluate predictive relationships and trends.

The model was developed and validated within an R environment using a robust data preprocessing pipeline, feature engineering, and time-based dataset partitioning. Forecast accuracy was measured using **Root Mean Squared Error (RMSE)**, making this a foundational exercise in **supervised regression modeling** for time-dependent weather data.


## Project Overview

- **Goal**: Predict `Next_Tmax` (next day's maximum temperature)
- **Technique**: Linear Regression
- **Language**: R
- **Document**: RMarkdown (`weather_forecasting_analysis.Rmd`)
- **Model Evaluation**: Root Mean Squared Error (RMSE)

---

## Dataset

- **Name**: `Bias_correction_ucl.csv`
- **Source**: Meteorological dataset
- **Features Include**:
  - `Solar radiation`
  - Humidity measures (`RH`)
  - Cloud cover measures (`CC`)
  - Precipitation (`PPT`)
  - Forecasted values from various LDAPS models
- **Target**: `Next_Tmax`

---

## Preprocessing & Feature Engineering

- Removed rows with missing values
- Renamed `Solar radiation` → `Solar_radiation`
- Dropped unused target `Next_Tmin`
- Engineered new features:
  - `LDAPS_CC` = average of 4 cloud cover predictors
  - `LDAPS_PPT` = average of 4 precipitation predictors

---

## Data Splitting Strategy

- Data split **chronologically** using the `Date` column:
  - 60% for training
  - 20% for validation
  - 20% for testing

---

## Modeling

A linear regression model was trained using:

```r
init_model <- lm(Next_Tmax ~ ., data = train)
```
## Evaluated on validation data

​
 
- Validation RMSE: ~1.51
---
## R Packages Used
```bash
readr
```
```bash
dplyr
```
```bash
Base R (lm, summary, predict)
```

## Key Insights
- LDAPS_RHmin, LDAPS_RHmax, LDAPS_CTot, and LDAPS_LH were among important predictors.

- Many features were statistically insignificant → potential for model simplification.

- RMSE indicated the model could reasonably approximate Next_Tmax.

