# 🩺 Medical Cost Analysis: Insurance Price Prediction

> **An end-to-end Linear Regression pipeline predicting annual medical insurance charges from health and demographic data — with a custom prediction engine for real-world use.**

---

## 📌 Project Overview

This project predicts individual annual medical insurance costs using personal health and demographic features. The focus is not just on model accuracy but on **interpretability** — understanding *which factors drive healthcare costs* and building a reusable prediction function for real-world input.

**Model:** Linear Regression  
**Dataset:** 1,338 observations | 7 features

---

## 🏆 Model Performance

| Metric | Score |
|--------|-------|
| **R² Score** | **0.78** |
| **RMSE** | **~$5,796** |

> The model explains **78% of the variance** in medical charges. The average prediction error is approximately **$5,796** per individual.

---

## 📂 Dataset

| Feature | Type | Description |
|---------|------|-------------|
| `age` | Numerical | Age of the insured individual |
| `sex` | Categorical | Gender (male / female) |
| `bmi` | Numerical | Body Mass Index |
| `children` | Numerical | Number of dependents |
| `smoker` | Categorical (Binary) | Smoking status (yes / no) |
| `region` | Categorical | US geographic region |
| `charges` | **Target** | Annual insurance cost ($) |

**Target distribution:** Right-skewed — most individuals have lower costs, with a smaller group incurring very high expenses (extreme cases are harder to predict).

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Target variable distribution analysis (right-skewed)
- Age vs. Charges scatter plots segmented by smoking status
- BMI and regional cost comparisons
- **Key finding:** Smoking status, age, and BMI are the three primary cost drivers

### 2. Data Preprocessing
- **Label Encoding** for binary categorical variables (`sex`, `smoker`)
- **One-Hot Encoding** for multi-class categorical variable (`region`)
- **Train/Test Split:** 80% training | 20% testing
- **StandardScaler** applied to normalize numerical features (age, BMI)

### 3. Model Training
```
LinearRegression().fit(X_train, y_train)
```

### 4. Prediction Engine
A custom function `predict_insurance_cost()` was built for real-world usability:
```python
predict_insurance_cost(age=35, sex='male', bmi=28.5, children=2, smoker='no', region='southeast')
```
- Accepts human-readable string inputs
- Applies the same encoding and scaling pipeline from training
- Returns a dollar-denominated cost estimate

---

## 📊 Key Findings

- **Smoking** is by far the most dominant predictor — smokers pay dramatically higher premiums
- **Age** and **BMI** are the second and third most important features respectively
- **Geographic region** has the least impact on insurance costs
- Lifestyle factors outweigh demographic factors in determining insurance charges

---

## 🚀 Future Work

- Explore **Random Forest** and **Gradient Boosting (XGBoost)** to capture non-linear relationships and reduce RMSE
- Apply **log transformation** to the target variable to address right-skewness
- Test **interaction features** (e.g., smoker × BMI) which may reveal compounding risk effects

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-9cf)

```
pandas | numpy | matplotlib | seaborn
scikit-learn (LinearRegression, StandardScaler, train_test_split)
```

---

## 📁 File Structure

```
medical-cost-prediction/
│
└── medical-cost-analysis-insurance-price-predict.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*

