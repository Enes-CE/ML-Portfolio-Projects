# 🏠 Boston Housing: EDA & Gradient Boosting Mastery

> A deep-dive into one of machine learning's most studied datasets — demonstrating how proper EDA and gradient boosting methods consistently outperform linear baselines.

[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-blue?logo=kaggle)](https://www.kaggle.com/brahimenesulusoy)
[![Python](https://img.shields.io/badge/Python-3.x-yellow?logo=python)](https://python.org)
[![Model](https://img.shields.io/badge/Model-Gradient_Boosting-orange)](https://scikit-learn.org)

---

## 📌 Problem Statement

Housing price prediction is a fundamental regression problem with real business value — from real estate agencies to mortgage providers. This project demonstrates a complete ML workflow on the classic Boston Housing dataset, with a focus on EDA depth and model comparison.

---

## 🎯 Objectives

- Conduct thorough EDA to understand urban housing price dynamics
- Identify and interpret the socioeconomic features that drive property values
- Demonstrate the performance gap between linear models and boosting methods
- Build an interpretable regression model with actionable feature importance

---

## 📊 Dataset Features

| Feature | Description |
|---|---|
| CRIM | Per capita crime rate by town |
| ZN | Proportion of residential land zoned for large lots |
| INDUS | Proportion of non-retail business acres |
| CHAS | Charles River dummy variable (1 if tract bounds river) |
| NOX | Nitric oxide concentration |
| RM | Average number of rooms per dwelling |
| AGE | Proportion of units built before 1940 |
| DIS | Weighted distance to employment centres |
| RAD | Accessibility to radial highways |
| TAX | Property-tax rate |
| PTRATIO | Pupil-teacher ratio |
| B | 1000(Bk - 0.63)² — neighbourhood demographics index |
| LSTAT | % lower status population |
| MEDV | **Target** — Median home value ($000s) |

---

## 🔍 EDA Highlights

- **RM (rooms)**: Strongest positive correlation with price — more rooms = higher value
- **LSTAT (socioeconomic status)**: Strongest negative correlation — a key price driver
- **NOX (pollution)**: Higher pollution areas show significantly lower home values
- **Crime rate**: Non-linear relationship — most towns have low crime, but outliers drag prices down sharply
- **CHAS (river access)**: Properties bordering the Charles River command a price premium

---

## 🛠️ Methodology

```
1. Data Overview
   ├── Null checks, dtypes, statistical summary
   └── Target variable distribution analysis

2. Univariate EDA
   ├── Histograms for all 13 features
   └── Skewness and kurtosis analysis

3. Bivariate EDA
   ├── Correlation heatmap
   ├── Scatter plots vs target (MEDV)
   └── Pairplot for top correlated features

4. Feature Engineering
   ├── Log transforms for skewed features
   └── Interaction terms (RM × LSTAT)

5. Modelling
   ├── Baseline: Linear Regression
   ├── Ridge / Lasso Regression
   ├── Random Forest
   └── Gradient Boosting (best performer)

6. Evaluation
   └── MAE, MSE, RMSE, R² — compared across all models
```

---

## 📈 Results

| Model | R² Score |
|---|---|
| Linear Regression | ~0.72 |
| Ridge Regression | ~0.74 |
| Random Forest | ~0.87 |
| **Gradient Boosting** | **~0.91** |

EDA finding translated directly into model performance: log-transforming LSTAT and RM improved R² by ~4 percentage points.

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

## 💼 Need a forecasting or regression model?

- 🌐 [enesulusoy-portfolio.netlify.app](https://enesulusoy-portfolio.netlify.app)
- 📧 c.enes.eng@gmail.com

