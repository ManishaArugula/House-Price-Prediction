# 🏡 House Price Prediction – EDA & Feature Engineering

## 📌 Project Overview

This project focuses on **Exploratory Data Analysis (EDA)** and **Feature Engineering** for a house price prediction dataset (Ames Housing dataset style). The primary goal is to understand data characteristics, handle missing values intelligently, and prepare a clean, well-structured dataset for machine learning models.

## 🛠 Tools & Libraries

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

## 🔍 Key Steps & Insights

### 1. Data Understanding

* Identified three primary data types: **Numerical (int/float)**, **Categorical**, and **Date/Time**.
* Inspected feature distributions and correlations with the target variable (**SalePrice**).

### 2. Handling Missing Values

* Features like *Alley, MasVnrType, FireplaceQu, PoolQC, Fence,* and *MiscFeatures* had >50% missing values.
* Instead of dropping them, evaluated whether missingness carried predictive value.

  * Example: Houses with missing `PoolQC` had significantly lower median sale prices → encoded as a separate category (`"No Pool"`).
* Applied **domain-aware imputations** and **categorical encodings**.

### 3. Feature Engineering

* Converted missing categories into meaningful labels.
* Normalized and log-transformed skewed features (e.g., `SalePrice`, `LotArea`, `GrLivArea`).
* Scaled numerical variables for consistency.
* Prepared analysis-ready datasets for downstream model training.

### 4. Visual & Statistical Analysis

* **Univariate Analysis:**

  * Distribution of `SalePrice` is **right-skewed** with the **median range between 100K–200K**.
* **Bivariate Analysis:**

  * Recently **remodeled houses** and houses with **garage built** tend to have higher sale prices.
  * Houses with **full bathrooms** show a clear uplift in sale price.
  * Houses with overall **higher quality and better materials** correlate strongly with higher sale price.
  * Strong positive correlation observed between `SalePrice` and both **1st Floor Surface Area** and **Above-Ground Living Area (GrLivArea)**.
* Plotted **correlation  plots**, **distribution plots**, and **box plots** to quantify feature-target relationships.

### 5. Feature Selection

* Applied **Lasso Regression (`alpha=0.005`) with `SelectFromModel`** for feature selection.
* Out of **81 input features**, **17 were retained (\~21%)** as most predictive of `SalePrice`.
* Retained features included a mix of:

  * **Structural attributes:** `TotalBsmtSF`, `2ndFlrSF`, `GrLivArea`
  * **Quality indicators:** `OverallCond`, `ExterCond`, `BsmtQual`
  * **Utility & amenities:** `CentralAir`, `Fireplaces`, `GarageType`, `GarageYrBlt`
* This reduced dimensionality while keeping interpretability, improving the dataset’s readiness for machine learning.

### 6. 📊 Modeling & Prediction
After preparing the dataset and selecting key features using Lasso Regression, a Linear Regression model was implemented to predict house prices. The model achieved R² = 90%, a mean absolute error (MAE) of 10%, and an RMSE of 13%, demonstrating strong predictive performance using the most relevant features.

## 📈 Outcome

* Generated a **clean, analysis-ready dataset** that retains valuable signals, even from missingness.
* Extracted key business insights about which property features drive higher house prices.
* Reduced dimensionality from 81 → **17 key features**, focusing the predictive model on the most relevant variables.
* Established a strong foundation for predictive modeling with improved **data quality, interpretability, and feature relevance**.
* Utilised a simple Linear Regression Model to estimate house price prediciton resulting an R-square value of 90%.  

---

