# 🎓 Career Placement Prediction: 8-Model Benchmarking Analysis

> **Predicting student employment outcomes using academic and technical features — benchmarking 8 classification algorithms with XGBoost achieving 96.8% accuracy and best-in-class generalization.**

---

## 📌 Project Overview

This project predicts whether a student will be **Placed** or **Not Placed** based on their academic performance, technical skills, and extracurricular activities. Beyond pure prediction, the analysis identifies the key career success drivers and rigorously compares 8 algorithms for both **accuracy** and **overfitting resistance**.

**Task:** Binary Classification (Placed / Not Placed)  
**Dataset:** 10,000 student records | 6 features  
**Best Result:** XGBoost — **96.80% Test Accuracy**

---

## 🏆 Full Model Comparison (8 Models)

| Rank | Model | Train Acc | Test Acc | CV Mean | Overfit Gap | Status |
|------|-------|-----------|----------|---------|-------------|--------|
| **1** | **XGBoost** | — | **96.80%** | **0.9648** | **Low** | 🏆 Champion |
| 2 | Gradient Boosting | — | — | — | Low | ✅ Strong |
| 3 | AdaBoost | — | — | — | Very Low | 🛡️ Most Stable |
| 4 | SVC | — | — | — | Low | ✅ Reliable |
| 5 | Logistic Regression | — | — | — | Low | ✅ Solid Baseline |
| 6 | Naive Bayes | — | — | — | Very Low | 🛡️ Stable |
| 7 | Random Forest | ~100% | — | — | High | ⚠️ Overfitted |
| 8 | Decision Tree | 100% | — | — | **14.2%** | ❌ Severely Overfitted |

> **Evaluation method:** 5-fold Cross-Validation on all models  
> **Key insight:** Decision Tree dropped **14.2%** from train to test — a textbook overfitting case. XGBoost captured complex non-linear patterns without memorizing noise.

---

## 📂 Dataset

**10,000 records** | **Balanced classes** (~5,000 Placed / ~5,000 Not Placed) | **6 engineering branches**

| Feature | Type | Description |
|---------|------|-------------|
| `Gender` | Categorical | Male / Female |
| `Branch` | Categorical | IT, CSE, EEE, Mechanical, etc. |
| `CGPA` | Numerical | Cumulative Grade Point Average |
| `Coding Skills` | Numerical | Technical coding proficiency score |
| `Internships` | Numerical | Number of completed internships |
| `Hackathons` | Categorical | Number of hackathon participations |
| `Placement` | **Target** | Placed / Not Placed |

**Data quality:** Zero missing values | Balanced classes — no bias in model training.

---

## 🔧 Methodology

### 1. Exploratory Data Analysis
- Categorical distribution analysis (gender, branch, hackathon participation)
- Numerical feature histograms (CGPA, coding scores, internships)
- Correlation heatmap — identified **CGPA**, **Internships**, and **Coding Skills** as top predictors
- Gender showed near-zero correlation with placement → merit-based dataset
- Placed vs. Not Placed comparison across all key metrics

### 2. Data Preprocessing
- **Label Encoding** for categorical variables (`Gender`, `Branch`, `Hackathon_Participation`)
- **Train/Test Split:** 80% training | 20% testing
- Tree-based models (XGBoost, Random Forest) used without scaling — invariant to feature magnitude

### 3. Model Training & Evaluation
All 8 models evaluated on:
- **Test Accuracy** — performance on unseen data
- **Train vs. Test Gap** — overfitting detector
- **5-Fold CV Mean & Std** — generalization consistency

### 4. Feature Importance (XGBoost)
Post-training Plotly bar chart showing each feature's contribution to placement prediction.

---

## 📊 Key Findings

- **CGPA** and **Coding Skills** are the top two predictors of placement success — academic and technical merit dominate
- **Internship experience** is the third strongest signal — practical exposure significantly improves placement odds
- **Gender** has near-zero correlation with placement — the dataset reflects a statistically unbiased hiring process
- **XGBoost** is the only model that achieves both high accuracy (96.8%) and stable cross-validation (0.9648)
- **Decision Tree** memorizes training data entirely (100% train accuracy) but generalizes poorly — a clear overfitting trap

---

## 🚀 Future Work

- Hyperparameter tuning for XGBoost (learning rate, max depth, n_estimators) to push beyond 97%
- SHAP value analysis for individual-level placement explanations
- Deploy as a student career advisory tool — input CGPA + internships → get placement probability
- Incorporate additional features: projects, certifications, communication skills assessment

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![XGBoost](https://img.shields.io/badge/XGBoost-96.8%25-red)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-purple?logo=plotly)

```
pandas | numpy | matplotlib | seaborn | plotly
scikit-learn (LogisticRegression, SVC, GaussianNB, DecisionTreeClassifier,
              RandomForestClassifier, AdaBoostClassifier, GradientBoostingClassifier)
xgboost
```

---

## 📁 File Structure

```
placement-analysis/
│
└── placement-analysis-8-models-xgboost-excellence.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
