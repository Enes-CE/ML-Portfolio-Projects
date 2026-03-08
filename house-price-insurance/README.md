# 🏠 House Price & Insurance Cost Prediction

> **A dual-dataset regression study combining King County real estate pricing and medical insurance cost prediction — comparing Linear, Polynomial, SVR, and Decision Tree models.**

---

## 📌 Project Overview

This notebook tackles two related regression problems under one structured ML workflow:

1. **King County House Price Prediction** — Predicting residential sale prices using architectural and location features (Washington, 2014–2015)
2. **Medical Insurance Cost Prediction** — Estimating individual insurance charges based on demographic and health factors

Both problems share the same pipeline: EDA → Feature Engineering → Model Comparison → Hyperparameter Tuning.

---

## 🏆 Final Model Results

### King County — House Price Prediction

| Model | R² Score |
|-------|----------|
| Linear Regression | 0.6959 |
| Polynomial Regression (Degree 2) | 0.7810 |
| SVR (Tuned) | 0.6420 |
| **Decision Tree (Tuned)** | **0.7908 ✅** |

> **Best Model: Tuned Decision Tree Regressor** with R² = 0.7908

### Insurance — Charges Prediction

| Model | Metrics |
|-------|---------|
| Linear Regression | MSE / MAE / RMSE / R² reported |
| Polynomial Regression (Degree 2) | MSE / MAE / RMSE / R² reported |
| SVR (Tuned — GridSearchCV) | MSE / MAE / RMSE / R² reported |
| Decision Tree (Tuned — GridSearchCV) | R² reported |

> Both datasets use identical evaluation metrics: **MSE, MAE, RMSE, R²**

---

## 📂 Datasets

### 1. King County Housing Data (`kc_house_data.csv`)
- **21,613 records** | **21 features**
- Sales between May 2014 – May 2015

| Key Feature | Description |
|-------------|-------------|
| `price` | Target — sale price of the house |
| `bedrooms` / `bathrooms` | Room counts |
| `sqft_living` | Interior living space (sq ft) |
| `grade` | Construction quality (1–13 scale) |
| `yr_built` | Year of construction |
| `zipcode` | Geographic location |

### 2. Medical Insurance Data
- Demographic and health features → insurance charge prediction
- Target: `charges` (annual insurance cost)

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Price distribution analysis (right-skewed, $300k–$800k concentration, luxury tail up to $7.7M)
- Correlation analysis between features and target
- Categorical and numerical feature profiling

### 2. Feature Engineering
- Type conversion and unique value analysis
- Feature extraction from date/time columns
- Encoding of categorical variables

### 3. Preprocessing
- **StandardScaler** applied to all features before model training
- Train/test split for both datasets

### 4. Models & Hyperparameter Tuning

**Linear Regression** — Baseline model

**Polynomial Regression** — Degree sweep to find optimal complexity
```
Pipeline: PolynomialFeatures → StandardScaler → LinearRegression
```

**SVR (Support Vector Regression)** — Tuned via GridSearchCV

**Decision Tree Regressor** — Tuned via GridSearchCV
```
Grid: criterion, max_depth, min_samples_split, min_samples_leaf
CV: 5-fold, scoring='r2'
```

---

## 📊 Key Findings

- **Decision Tree** outperforms all other models on house price prediction (R² = 0.7908)
- **Polynomial Regression (Degree 2)** is a strong runner-up (R² = 0.7810), capturing non-linear relationships efficiently
- **SVR** underperforms on this dataset (R² = 0.6420), likely due to the high feature variance and large dataset size
- Price distribution's heavy right-skew (luxury properties up to $7.7M) reduces linear model accuracy

---

## 🚀 Future Work

- Add ensemble methods (Random Forest, Gradient Boosting) for comparison
- Apply log transformation to the target for better linear model performance
- Incorporate geospatial features (lat/long clustering) for King County data
- Explore regularization (Ridge, Lasso) to reduce overfitting in polynomial models

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-9cf)

```
pandas | numpy | matplotlib | seaborn
scikit-learn (LinearRegression, PolynomialFeatures, SVR, DecisionTreeRegressor, GridSearchCV)
```

---

## 📁 File Structure

```
house-price-insurance/
│
└── house-price-analysis-insurance-price-predict.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
