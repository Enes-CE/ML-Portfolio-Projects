# 🏡 House Price Analysis & Insurance Price Prediction

> A dual regression study — predicting residential property prices and insurance costs within a single end-to-end ML pipeline.

[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-blue?logo=kaggle)](https://www.kaggle.com/brahimenesulusoy)
[![Python](https://img.shields.io/badge/Python-3.x-yellow?logo=python)](https://python.org)
[![Type](https://img.shields.io/badge/Type-Regression-blue)](https://scikit-learn.org)

---

## 📌 Problem Statement

Two industries — real estate and insurance — share a common challenge: accurately pricing risk and value from structured tabular data. This project tackles both simultaneously, demonstrating how the same ML pipeline can be adapted across different prediction targets.

---

## 🎯 Objectives

- Build separate regression models for house prices and insurance costs
- Compare feature importance across both domains
- Demonstrate the full pipeline: raw data → cleaned data → trained model → evaluation
- Extract interpretable business insights from each model

---

## 📊 Datasets

### 🏠 House Price Dataset

| Feature | Description |
|---|---|
| Area | Property size (sq ft / m²) |
| Bedrooms | Number of bedrooms |
| Bathrooms | Number of bathrooms |
| Floors | Number of storeys |
| Year Built | Construction year |
| Condition | Property condition rating |
| Location | Neighbourhood / region |
| Price | **Target** — sale price |

### 🛡️ Insurance Dataset

| Feature | Description |
|---|---|
| Age | Policyholder age |
| Sex | Gender |
| BMI | Body mass index |
| Children | Number of dependents |
| Smoker | Smoking status (Yes/No) |
| Region | Geographic region |
| Charges | **Target** — annual insurance cost |

---

## 🔍 Key Insights

**House Prices:**
- Area and location are dominant price drivers
- Property condition has a non-linear effect — "good" vs "excellent" matters less than "poor" vs "fair"
- Year built affects price mainly through condition proxy

**Insurance Costs:**
- Smoking status is the single most powerful predictor — smokers pay 3–4× more
- BMI has a threshold effect — high BMI combined with smoking creates extreme charges
- Age shows steady positive correlation with costs

---

## 🛠️ Methodology

```
1. Data Cleaning
   ├── Missing value imputation
   ├── Outlier detection and treatment
   └── Type corrections

2. EDA
   ├── Distribution plots
   ├── Correlation analysis
   └── Categorical feature analysis

3. Feature Engineering
   ├── Encoding categorical variables
   ├── Feature scaling
   └── Log-transformation of skewed targets

4. Modelling (both datasets)
   ├── Linear Regression (baseline)
   ├── Random Forest Regressor
   └── Gradient Boosting Regressor

5. Evaluation
   └── MAE, RMSE, R² for each model and dataset
```

---

## 📈 Results Summary

**House Price Model:** Best R² ~0.88 (Random Forest)  
**Insurance Cost Model:** Best R² ~0.87 (Gradient Boosting)

---

## 🧰 Tech Stack

```python
pandas · numpy · matplotlib · seaborn
scikit-learn · scipy
```

---

## 🔗 Full Notebook

👉 [View on Kaggle](https://www.kaggle.com/brahimenesulusoy)

---

## 💼 Need a pricing model for your business?

- 🌐 [enesulusoy-portfolio.netlify.app](https://enesulusoy-portfolio.netlify.app)
- 📧 c.enes.eng@gmail.com

