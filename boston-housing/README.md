# 🏙️ Boston Real Estate: Predictive Pricing Analysis

> **Predicting median home values using socio-economic, environmental, and structural features — with a full ML pipeline from EDA to hyperparameter-tuned Gradient Boosting.**

---

## 📌 Project Overview

This project applies a structured machine learning workflow to the classic **Boston Housing Dataset** to uncover the key drivers of residential property values in 1970s Boston. Beyond simple price prediction, this analysis serves as a **technical audit of urban real estate valuation** — combining rigorous preprocessing, statistical insight, and ensemble modeling.

**Final Model Performance:**
| Metric | Score |
|--------|-------|
| R² Score | **~0.88** |
| RMSE | **2.94 ($1000s)** |
| Best Model | **Tuned Gradient Boosting Regressor** |

---

## 🎯 Objectives

- Build a robust regression model to predict **Median Home Value (MEDV)**
- Identify the primary socio-economic and structural **price drivers**
- Evaluate **environmental factors** (air pollution, river proximity) on housing demand
- Mitigate **multicollinearity** and handle **outliers** with principled preprocessing

---

## 📂 Dataset

The dataset contains **506 samples** across **13 features** representing census tracts in Boston.

| Feature | Description |
|---------|-------------|
| `Crime_Rate` | Per capita crime rate by town |
| `Large_Lot_Zone_Pct` | % of residential land zoned for large lots |
| `Business_Acres_Pct` | % of non-retail business acres per town |
| `River_Border` | Charles River adjacency (binary) |
| `Air_Pollution_Index` | Nitric oxides concentration (ppm × 10) |
| `Avg_Rooms` | Average number of rooms per dwelling |
| `Pre_1940_Units_Pct` | % of owner-occupied units built before 1940 |
| `Dist_Employment_Centers` | Weighted distance to employment hubs |
| `Highway_Access_Index` | Accessibility to radial highways |
| `Property_Tax` | Full-value property-tax rate per $10,000 |
| `Student_Teacher_Ratio` | Pupil-teacher ratio by town |
| `Social_Index_B` | Racial composition index |
| `Lower_Income_Pct` | % of population classified as lower-status |

**Target:** `Median_Home_Price` — median value of owner-occupied homes in $1000s

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Correlation heatmap to identify feature relationships
- Distribution analysis (box plot, violin plot, histogram with KDE)
- Scatter plots with regression lines for top predictors

### 2. Feature Engineering & Preprocessing
- **Log Transformation** applied to target variable and `Lower_Income_Pct` to correct right-skewness
- **RobustScaler** used to handle outliers (scales by IQR instead of standard deviation)
- **Multicollinearity Reduction**: `Property_Tax` removed due to 0.91 correlation with `Highway_Access_Index`

### 3. Model Comparison
Seven models were evaluated on the held-out test set:

| Model | RMSE | MAE | R² |
|-------|------|-----|----|
| Linear Regression | — | — | — |
| Ridge Regression | — | — | — |
| Lasso Regression | — | — | — |
| SVR | — | — | — |
| Random Forest | — | — | — |
| **Gradient Boosting** | **Best** | **Best** | **~0.88** |
| XGBoost | — | — | — |

### 4. Hyperparameter Tuning
Final Gradient Boosting model fine-tuned for optimal bias-variance tradeoff.

---

## 📊 Key Findings

- **`Lower_Income_Pct`** and **`Avg_Rooms`** are the dominant price predictors
- Log-transforming `Lower_Income_Pct` revealed a strong linear relationship with the target
- The dataset contains **censored values at $50k**, introducing unavoidable noise for high-end predictions
- Geographic features like `River_Border` have **negligible predictive power**

---

## 🚀 Future Work

- Address the $50,000 upper cap to improve high-value home accuracy
- Implement **Stacking Ensembles** (XGBoost + Gradient Boosting)
- Explore SHAP values for deeper model interpretability

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-Boosting-red)
![Pandas](https://img.shields.io/badge/Pandas-Data-green?logo=pandas)
![Plotly](https://img.shields.io/badge/Plotly-Visualization-purple?logo=plotly)

```
pandas | numpy | matplotlib | seaborn | plotly
scikit-learn | xgboost
```

---

## 📁 File Structure

```
boston-housing/
│
└── boston-housing-eda-gradient-boosting-mastery.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
