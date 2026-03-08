# 📊 ML Portfolio Projects

> Real-world machine learning projects — from exploratory data analysis to production-ready predictive models.

Each project tackles a genuine business or scientific problem using structured ML workflows: data cleaning, EDA, feature engineering, model selection, hyperparameter tuning, and performance evaluation.

---

## 🗂️ Projects

### 🏎️ [Mercedes-Benz USA (2005–2025): Luxury Price Prediction](https://www.kaggle.com/code/brahimenesulusoy/mercedes-benz-detailed-eda-price-prediction)
**Goal:** Predict used car prices across two decades of Mercedes-Benz listings using model, mileage, AMG/4MATIC flags, and trim level.  
**Highlights:** 9 models compared · Overfitting analysis · Log transformation · Ridge vs XGBoost  
**Result:** Ridge Regression wins with CV R² = 0.708 and near-zero overfit gap (0.03) — XGBoost overfitted severely despite high train score  
`Regression` `Ridge` `XGBoost` `Overfitting Detection` `Feature Engineering`

---

### 🎓 [Career Placement: 8-Model Predictive Analysis](https://www.kaggle.com/code/brahimenesulusoy/placement-analysis-8-models-xgboost-excellence)
**Goal:** Predict student employment outcomes using academic performance, coding skills, and internship experience.  
**Highlights:** 8 algorithms benchmarked · 5-fold cross-validation · Overfitting detection · Feature importance  
**Result:** XGBoost achieved **96.80% test accuracy** (CV Mean: 0.9648) — Decision Tree dropped 14.2% from train to test  
`Classification` `XGBoost` `Model Benchmarking` `Cross-Validation`

---

### 💧 [Global Water Scarcity: 99.6% Accuracy with XGBoost](https://www.kaggle.com/code/brahimenesulusoy/water-scarcity-99-6-accuracy-with-xgboost)
**Goal:** Classify regional water scarcity levels (Low / Moderate / High) across 200+ countries from 2000–2025.  
**Highlights:** 8 models compared · Zero overfitting validated · Groundwater depletion as #1 predictor (56% importance)  
**Result:** XGBoost achieved **99.62% test accuracy** with only 0.003 train-test gap  
`Classification` `XGBoost` `LightGBM` `Environmental ML` `Multi-Class`

---

### 🏙️ [Boston Housing: EDA & Gradient Boosting Mastery](https://www.kaggle.com/code/brahimenesulusoy/boston-housing-eda-gradient-boosting-mastery)
**Goal:** Predict median home values using socioeconomic, environmental, and structural features.  
**Highlights:** 7 models compared · Log transformation · RobustScaler · Multicollinearity mitigation  
**Result:** Tuned Gradient Boosting achieved **R² = 0.88, RMSE = $2,940** — Lower income % and avg rooms as top drivers  
`Regression` `Gradient Boosting` `EDA` `Feature Engineering`

---

### 🏠 [House Price & Insurance Cost Prediction](https://www.kaggle.com/code/brahimenesulusoy/house-price-analysis-insurance-price-predict)
**Goal:** Dual-dataset regression — King County residential pricing + medical insurance cost estimation.  
**Highlights:** 4 models compared · GridSearchCV tuning · Polynomial features · SVR vs Decision Tree  
**Result:** Tuned Decision Tree achieved **R² = 0.7908** on 21,613 housing records  
`Regression` `Decision Tree` `Polynomial Regression` `SVR` `GridSearchCV`

---

### 🩺 [Medical Cost Analysis: Insurance Price Prediction](https://www.kaggle.com/code/brahimenesulusoy/medical-cost-analysis-insurance-price-predict)
**Goal:** Predict individual annual medical insurance costs from health and demographic data.  
**Highlights:** End-to-end pipeline · Custom prediction function · Feature importance via coefficients  
**Result:** Linear Regression achieved **R² = 0.78, RMSE = $5,796** — smoking status identified as dominant cost driver  
`Regression` `Linear Regression` `EDA` `Feature Importance`

---

### 🎬 [Netflix Global Content & Pricing Analysis](https://www.kaggle.com/code/brahimenesulusoy/netflix-data-analysis)
**Goal:** Explore Netflix's content library size and subscription pricing across countries.  
**Highlights:** Multi-library visualisation (Plotly · Seaborn · Matplotlib) · Pandas Profiling · Regional pricing patterns  
**Result:** Identified significant regional disparities in both content availability and pricing strategy  
`EDA` `Data Visualisation` `Plotly` `Pandas Profiling`

---

## 🛠️ Tech Stack

```
Core ML      │ Scikit-learn · XGBoost · LightGBM · Gradient Boosting
Analysis     │ Pandas · NumPy · SciPy
Visualisation│ Matplotlib · Seaborn · Plotly
Environment  │ Jupyter Notebook · Kaggle Kernels
```

---

## 📈 Methodology

Every project follows a consistent, professional workflow:

1. **Problem Definition** — What business question are we answering?
2. **Exploratory Data Analysis** — Distributions, correlations, outliers
3. **Feature Engineering** — Encoding, scaling, new feature creation
4. **Model Selection** — Multiple algorithms compared objectively
5. **Hyperparameter Tuning** — Grid search / cross-validation
6. **Evaluation** — Metrics relevant to the problem type

---

## 🔗 All Notebooks on Kaggle

Full interactive notebooks with outputs, visualisations, and commentary are available on Kaggle:  
👉 **[kaggle.com/brahimenesulusoy](https://www.kaggle.com/brahimenesulusoy)**

---

## 💼 Need a Predictive Model Built?

I build custom ML solutions for businesses — sales forecasting, churn prediction, price estimation, and more.

- 🔗 **LinkedIn**: [ibrahim-enes-ulusoy](https://www.linkedin.com/in/ibrahim-enes-ulusoy-9646551b9/)
- 🌐 **Portfolio**: [enesulusoy-portfolio.netlify.app](https://enesulusoy-portfolio.netlify.app)
- 📧 **Email**: [c.enes.eng@gmail.com](mailto:c.enes.eng@gmail.com)
