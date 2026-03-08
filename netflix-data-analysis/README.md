# 🎬 Netflix Global Content & Pricing Analysis

> **A comprehensive exploratory data analysis of Netflix's content library and subscription pricing across countries — uncovering regional disparities, content distribution patterns, and pricing strategies.**

---

## 📌 Project Overview

This project dives into Netflix's global footprint by analyzing two key dimensions: **content availability** (how many movies and TV shows each country gets) and **subscription pricing** (what users pay for Basic, Standard, and Premium plans). 

Rather than building a predictive model, the goal here is pure **insight extraction** — letting the data tell the story of Netflix's international strategy through rich, multi-library visualizations.

---

## 📂 Dataset

**Source:** Netflix Subscription Price in Different Countries  
**File:** `netflix price in different countries.csv`

| Feature | Description |
|---------|-------------|
| `Country` | Country where Netflix is available |
| `Total Library Size` | Total number of movies + TV shows available |
| `No. of TV Shows` | Number of TV series available in that country |
| `No. of Movies` | Number of movies available in that country |
| `Cost Per Month - Basic ($)` | Monthly price of the Basic plan |
| `Cost Per Month - Standard ($)` | Monthly price of the Standard plan |
| `Cost Per Month - Premium ($)` | Monthly price of the Premium plan |

**Data Quality:** Zero missing values — clean dataset ready for direct analysis.

---

## 🔍 Analysis Structure

### 1. Data Profiling
- Automated `pandas_profiling` report for full statistical overview
- Shape, data types, distributions, and correlation summary

### 2. Univariate Analysis
- **Categorical:** Country-level breakdown
- **Numerical:** Distribution histograms for `Total Library Size`, `No. of TV Shows`, `No. of Movies`

### 3. Missing Value & Uniqueness Check
- Confirmed: **no missing values** across all columns
- Unique country count analysis

### 4. Data Visualization (3 Libraries)

**Plotly (Interactive)**
- Bar chart: Basic plan prices by country (color-scaled)
- Pie chart: Standard plan market share by country
- Scatter plot: Premium plan pricing across countries
- Bar chart: Total library size with TV show / movie breakdown on hover

**Seaborn**
- Country vs. Total Library Size bar chart
- Country vs. No. of TV Shows bar chart
- Country vs. No. of Movies bar chart
- Correlation heatmap across all numerical features

**Matplotlib**
- Country vs. Total Library Size scatter plot

---

## 📊 Key Findings

- Significant **regional disparity** exists in content library sizes — some countries receive dramatically more titles than others
- **Subscription pricing varies widely** across countries, reflecting local purchasing power and market positioning
- `Total Library Size`, `No. of TV Shows`, and `No. of Movies` are **highly correlated** — countries with more content get more of everything
- The correlation heatmap reveals pricing tiers (Basic/Standard/Premium) move closely together within each country

---

## 🚀 Future Work

- Add subscriber count data to correlate pricing with market penetration
- Time-series analysis of how library sizes and prices changed over the years
- Clustering countries by content profile and price sensitivity
- Predictive modeling: estimating library size or optimal pricing by region

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-purple?logo=plotly)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical-9cf)
![Pandas](https://img.shields.io/badge/Pandas-Data-green?logo=pandas)

```
pandas | numpy | matplotlib | seaborn | plotly | pandas_profiling
```

---

## 📁 File Structure

```
netflix-data-analysis/
│
└── netflix-data-analysis.ipynb   # Main analysis notebook
```

---

*Part of the [ML Portfolio Projects](https://github.com/Enes-CE/ML-Portfolio-Projects) — real-world ML from EDA to production-ready models.*
