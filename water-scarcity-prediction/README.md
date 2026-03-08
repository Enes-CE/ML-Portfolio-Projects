# 🌊 Global Water Consumption & Scarcity Classification

> **A multi-class classification study predicting regional water scarcity levels (Low / Moderate / High) across 200+ countries from 2000–2025 — with XGBoost achieving 99.62% accuracy and zero meaningful overfitting.**

---

## 📌 Project Overview

Water scarcity is one of the most critical global challenges of the 21st century. This project transforms raw consumption and environmental data into an actionable **machine learning classifier** that can identify at-risk regions before crisis escalates.

Using 25 years of data (2000–2025) across 200+ countries, the model identifies which factors — agricultural demand, groundwater extraction, rainfall, population growth — are the true drivers of water stress.

**Task:** Multi-Class Classification (Low / Moderate / High scarcity)  
**Best Result:** XGBoost — **99.62% Test Accuracy | Gap: 0.003**

---

## 🏆 Full Model Comparison (8 Models)

| Rank | Model | Test Accuracy | Overfit Gap | Verdict |
|------|-------|--------------|-------------|---------|
| **1** | **XGBoost** | **99.62%** | **0.003** | 🏆 Champion |
| **2** | **LightGBM** | **99.49%** | **0.005** | ⚡ High Efficiency |
| **3** | **Random Forest** | **99.10%** | Solid | ✅ Reliable Baseline |
| 4 | Gradient Boosting | — | Low | ✅ Strong |
| 5 | SVM | — | Low | ✅ Reliable |
| 6 | KNN | — | — | Evaluated |
| 7 | **Naive Bayes** | **92.69%** | Good | 🛡️ Stable Logic |
| 8 | Logistic Regression | — | — | Evaluated |

> **Zero Overfitting Validated:** Top models (XGBoost, LightGBM, Gradient Boosting) show less than **0.5% decay** from training to test scores — patterns are universal, not memorized.

---

## 📂 Dataset

**200+ countries/regions** | **2000–2025** (25 years)

| Feature | Description |
|---------|-------------|
| `Year` | 2000–2025 temporal coverage |
| `Total Water Consumption` | Billion m³ per region |
| `Per Capita Water Use` | Liters per day |
| `Agricultural Water Use (%)` | Share of water used in farming |
| `Industrial Water Use (%)` | Share of water used in industry |
| `Household Water Use (%)` | Share of water used domestically |
| `Annual Rainfall (mm)` | Environmental water input |
| `Groundwater Depletion Rate (%)` | Rate of underground water extraction |
| `Population` | Regional population |
| `Water Scarcity Level` | **Target** — Low / Moderate / High |

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Statistical distribution of Total Water Consumption
- Global choropleth map of water scarcity by country
- Temporal trend analysis (2000–2025): Is scarcity static or worsening?
- Sector breakdown: Agriculture vs. Industry vs. Household usage
- Scatter analysis: Agricultural burden vs. Groundwater Depletion
- Per capita usage comparison across Low / High scarcity classes

### 2. Data Preprocessing
- **Label Encoding** for target variable (`Water Scarcity Level` → numerical labels)
- **StandardScaler** applied before model training
- **Train/Test Split:** Standard 80/20 split

### 3. Model Training & Evaluation
All 8 models evaluated on:
- **Test Accuracy** — performance on unseen regional data
- **Train vs. Test Gap** — overfitting detector
- **Confusion Matrix** for XGBoost — class-level validation

### 4. Feature Importance (XGBoost)
Interactive Plotly bar chart showing each feature's predictive weight.

---

## 📊 Key Findings

- **Groundwater Depletion Rate** is the #1 predictor with **56% feature importance** — the crisis is driven by unsustainable extraction, not just lack of rainfall
- **XGBoost** achieves 99.62% accuracy with only a 0.003 train-test gap — true generalization, not memorization
- **Agricultural Water Use** is the strongest secondary driver — farming dominates water consumption globally
- Per capita usage alone is **not** sufficient to classify scarcity — regional extraction and depletion patterns matter far more
- Water scarcity shows **temporal worsening trends** across multiple regions (2000–2025)

---

## 🚀 Future Work

- Time-series forecasting of future scarcity levels by region (LSTM / Prophet)
- Integration of climate change projections as external features
- Regional policy recommendation engine based on predicted scarcity class
- Deploy as an interactive global water risk dashboard

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![XGBoost](https://img.shields.io/badge/XGBoost-99.62%25-red)
![LightGBM](https://img.shields.io/badge/LightGBM-99.49%25-lightgreen)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-purple?logo=plotly)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)

```
pandas | numpy | matplotlib | seaborn | plotly
scikit-learn (LogisticRegression, RandomForestClassifier, GradientBoostingClassifier,
              SVC, KNeighborsClassifier, GaussianNB, StandardScaler)
xgboost | lightgbm
```

---

## 📁 File Structure

```
water-scarcity-prediction/
│
└── water-scarcity-99-6-accuracy-with-xgboost.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
