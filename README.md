# House Price Prediction – EDA & Feature Engineering

## 📌 Project Overview
This project focuses on **Exploratory Data Analysis (EDA)** and **Feature Engineering** for a house price prediction dataset (Ames Housing dataset style). The primary goal is to understand data characteristics, handle missing values intelligently, and prepare a clean, well-structured dataset for machine learning models.

## 🛠 Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn

## 🔍 Key Steps & Insights
### 1. Data Understanding
- Identified three primary data types: **Numerical (int/float)**, **Categorical**, and **Date/Time**.
- Inspected feature distributions and correlations with the target variable (`SalePrice`).

### 2. Handling Missing Values
- Features like `Alley`, `MasVnrType`, `FireplaceQu`, `PoolQC`, `Fence`, and `MiscFeatures` had **>50% missing values**.
- Instead of dropping them, evaluated whether missingness had predictive value:
  - Example: Houses with missing `PoolQC` had significantly lower median sale prices → encoded as a separate category ("No Pool").
- Applied domain-aware imputations and categorical encodings.

### 3. Feature Engineering
- Converted missing categories into meaningful labels.
- Normalized and transformed skewed features.
- Prepared datasets for future model training.

### 4. Visual Analysis
- Correlation heatmaps to identify highly predictive features.
- Distribution plots for numerical features to detect outliers and skewness.
- Categorical feature impact analysis on `SalePrice`.

## 📈 Outcome
- Generated a **clean, analysis-ready dataset** that retains valuable signals from missingness.
- Established a strong foundation for predictive modeling with improved data quality and interpretability.

