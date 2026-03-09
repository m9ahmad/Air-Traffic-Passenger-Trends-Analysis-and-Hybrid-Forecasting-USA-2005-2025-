# Air Traffic Passenger Trends Analysis and Hybrid Forecasting (USA 2005-2025)

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Prophet](https://img.shields.io/badge/Forecasting-Prophet-blue)](https://facebook.github.io/prophet/)
[![XGBoost](https://img.shields.io/badge/ML-XGBoost-EE4C2C?style=flat&logo=xgboost&logoColor=white)](https://xgboost.ai/)
[![Pandas](https://img.shields.io/badge/Data-Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

A modern, industrial-grade forecasting engine that combines **Meta's Prophet** (for structural seasonality) with **XGBoost** (for residual error correction). This project analyzes 20 years of US air traffic to predict demand horizons and quantify post-pandemic recovery across global geographical regions.

---

## 🚀 Project Overview
This repository implements a **Hybrid Time-Series Pipeline** to solve the limitations of standalone statistical models. By stacking Gradient Boosting on top of additive models, we capture both macro-level trends and micro-level volatility in passenger demand.

### Key Highlights:
* **Hybrid Architecture:** Prophet + XGBoost Residual Boosting.
* **Temporal Scope:** 2005 – May 2025 (20 years of high-fidelity data).
* **Recovery Analysis:** Comparative "Pre-Pandemic Baseline" benchmarking by GEO Region.
* **Economic Indicators:** Tracking the "Low-Fare vs. Premium" shift as a lead demand indicator.

---

## 🛠️ Technology Stack
| Category | Tools |
| :--- | :--- |
| **Language** | ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) |
| **Forecasting** | **Prophet (Meta)**, **Statsmodels** (STL Decomposition) |
| **Machine Learning** | ![XGBoost](https://img.shields.io/badge/XGBoost-EE4C2C?style=for-the-badge&logo=xgboost&logoColor=white), **Scikit-Learn** |
| **Data Science** | ![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white), ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white) |
| **Visualization** | **Seaborn**, **Matplotlib**, **Plotly** |
| **Utilities** | `kagglehub`, `holidays` |

---

## 📈 Methodology: The Hybrid Workflow

### 1. Feature Engineering & Decomposition
* **Signal Extraction:** Decomposed global traffic into Trend, Seasonal, and Residual components.
* **Log-Scaling:** Applied variance stabilization to handle multiplicative growth in passenger volume.
* **Temporal Markers:** Engineered `Is_Summer_Peak` and `Quarterly` features to capture cyclical surges.

### 2. The Forecasting Engine (Prophet + XGBoost)
* **Base Layer (Prophet):** Modeled the "Macro" signal. Included **US Federal Holidays** as exogenous regressors to account for holiday-driven demand spikes.
* **Residual Layer (XGBoost):** Extracted the errors (residuals) from Prophet and trained an XGBoost regressor using **Lagged Features** ($t-1$, $t-12$).
* **Fusion:** Combined the structural forecast with the boosted error prediction to minimize Mean Squared Error (MSE).

### 3. Regional Recovery & Segmentation
* **Baseline Benchmarking:** Calculated the 2019 pre-pandemic average as a 100% "Recovery Target."
* **Market Leaders:** Identified regions like **Central America** and **Australia/Oceania** that have surpassed 2019 levels as of 2025.

---

## 🔍 Key Insights
* **The "Chaos Hour" of Demand:** Confirmed that seasonal swings are multiplicative—as volume grows, the intensity of peak months increases.
* **Consumer Shift:** Visualized the **Low Fare vs. Other** ratio, identifying a significant post-pandemic pivot toward budget-conscious travel categories.
* **Model Efficacy:** The Hybrid approach successfully corrected Prophet's tendency to under-predict during volatile short-term shifts by utilizing XGBoost's non-linear pattern recognition.
* 

---
