# 🏎️ Mercedes-Benz USA (2005–2025): Luxury Price Prediction & Analysis

> **A two-decade study of the Mercedes-Benz secondary market — comparing 9 regression algorithms to find the most reliable used car price predictor, with a strong focus on overfitting detection and model generalization.**

---

## 📌 Project Overview

This project analyzes **108 curated Mercedes-Benz listings** sourced from *Cars.com* (February 2026), covering model years from 2005 to 2025. The goal goes beyond simple price prediction: it investigates **depreciation curves**, **AMG/4MATIC value premiums**, and **which factors truly drive luxury vehicle pricing**.

A key theme throughout: with a small dataset (n=108), avoiding overfitting is just as important as maximizing accuracy.

---

## 🏆 Model Performance — Full Comparison (9 Models)

| Rank | Model | Test R² | CV Mean R² | Overfit Gap | MAE (USD) | Status |
|------|-------|---------|------------|-------------|-----------|--------|
| **1** | **Linear Regression** | **~0.48** | **0.708** | **0.03** | **~$13,800** | 🏆 Champion |
| **1** | **Ridge Regression** | **~0.48** | **0.708** | **0.03** | **~$13,800** | 🏆 Champion |
| **2** | Polynomial (Tuned, α=50, deg=2) | 0.41 | 0.653 | 0.16 | ~$14,600 | ✅ Stable Runner-up |
| **3** | XGBoost | 0.45 | 0.635 | 0.47 | ~$13,700 | ⚠️ Highly Overfitted |
| **4** | SVR | 0.38 | 0.190 | 0.58 | ~$14,700 | ❌ Poor Generalization |
| — | Lasso | — | — | — | — | Evaluated |
| — | Random Forest | — | — | — | — | Evaluated |
| — | LightGBM | — | — | — | — | Evaluated |
| — | KNN | — | — | — | — | Evaluated |

> **Best Model: Ridge Regression (Log-Transformed)** — highest CV score (0.708) with the lowest overfit gap (0.03)

**Verdict: For this dataset, Simplicity Wins.** XGBoost achieved Train R² > 0.90 but suffered a 0.47 gap — effectively memorizing the data rather than learning from it.

---

## 📂 Dataset

**108 listings** | **13 engineered features** | Source: *Cars.com*, February 2026

| Feature | Description |
|---------|-------------|
| `Year` / `Vehicle_Age` | Model year (2005–2025) and calculated age |
| `Price_USD` | **Target variable** — $6,420 to $169,995 |
| `Mileage_Miles` | Odometer reading (avg: ~47,528 mi) |
| `Is_AMG` | Binary flag for AMG performance trim |
| `Is_4MATIC` | Binary flag for AWD system |
| `Model_Series` | Mercedes model class (C, E, S, GLE, etc.) |
| `Trim_Level` | Specific trim configuration |
| `Body_Type` | Sedan, SUV, Coupe, Convertible, etc. |
| `Horsepower` | Engine output |

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Price range analysis: $6,420 (budget) to $169,995 (AMG flagship)
- Average fleet age: ~5.4 years | Average mileage: ~47,528 miles
- Correlation heatmap: near-perfect negative correlation (−1.00) between `Year` and `Vehicle_Age`
- AMG and 4MATIC premium analysis

### 2. Feature Selection & Data Cleaning
Dropped to prevent data leakage and multicollinearity:
- `Vehicle_Name` (decomposed into individual features)
- `Year` (perfectly correlated with `Vehicle_Age`)
- `Price_Category` and `Mileage_Category` (derived from target/mileage)

### 3. Encoding
**Label Encoding** chosen over One-Hot Encoding — keeps dimensionality low on a small dataset (108 rows) while preserving categorical patterns across model series and trim levels.

### 4. Target Transformation
**Log transformation** applied to `Price_USD` to address right-skewness and improve linear model performance. Predictions are inverse-transformed (`expm1`) for final evaluation.

### 5. Model Evaluation Strategy
All models evaluated across three dimensions:
- **Test R²** — direct accuracy on held-out data
- **CV Mean R²** — 5-fold cross-validation for generalization
- **Overfit Gap** (Train R² − Test R²) — key stability indicator

---

## 📊 Key Findings

- **Mileage** is the strongest depreciation driver — high-mileage cars lose value rapidly regardless of model
- **AMG trims** command a significant price premium but also introduce high variance
- **XGBoost and tree-based models** overfit severely on small datasets — CV scores expose what test scores hide
- **Ridge Regression** with L2 regularization (α=1.0) handles multicollinearity between `Mileage` and `Vehicle_Age` effectively
- **Polynomial Regression** (degree=2) captures non-linear depreciation curves but requires careful tuning (α=50) to stay stable

---

## 🚀 Future Work

- **Feature Engineering:** Interaction terms between `Model_Series` and `Horsepower`
- **Data Augmentation:** Expanding beyond 108 rows to allow gradient boosting models to generalize properly
- **External Data:** Adding economic indicators (inflation, fuel prices) and Carfax history data

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-Boosting-red)
![LightGBM](https://img.shields.io/badge/LightGBM-Boosting-lightgreen)

```
pandas | numpy | matplotlib | seaborn
scikit-learn (LinearRegression, Ridge, Lasso, PolynomialFeatures,
              RandomForest, SVR, KNN, Pipeline, GridSearchCV)
xgboost | lightgbm
```

---

## 📁 File Structure

```
mercedes-benz-price-prediction/
│
└── mercedes-benz-detailed-eda-price-prediction.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
