# Wheat Yield Prediction using Machine Learning

## Overview

This project analyzes the impact of environmental factors, soil characteristics, and agricultural practices on wheat yield across multiple global regions.

The goal is to build predictive models capable of estimating wheat yield (tons/ha) and to identify the most important factors affecting crop performance.

The project follows the CRISP-DM methodology and combines statistical analysis with machine learning techniques.

---

## Objectives

- Predict wheat yield using supervised machine learning models
- Identify key drivers of crop performance (fertilizer, pests, environment)
- Apply statistical analysis to understand data distributions and relationships
- Explore dimensionality reduction using Principal Component Analysis (PCA)
- Provide insights to improve agricultural decision-making

---

## Dataset

- **Rows:** 900
- **Features:** 9
- **Type:** Mixed (numerical + categorical)

### Variables include:

- Fertilizer Usage (kg/ha)
- Pest Infestation Level (%)
- Market Price per Ton ($)
- Production Cost ($/ha)
- Region, Weather Conditions, Soil Type
- Wheat Yield (target variable)

---

## Methodology

### Data Preparation

- Removed missing values (<0.5%)
- Checked duplicates
- Renamed variables for clarity
- Analyzed distributions and outliers (boxplots)

### Exploratory Data Analysis (EDA)

- Correlation analysis → weak linear relationships detected
- Bivariate and multivariate analysis → no strong single predictors
- Identified need for non-linear modeling approaches

### Feature Engineering

- One-hot encoding for categorical variables
- Standardization using **StandardScaler**

### Dimensionality Reduction

- Applied **PCA**
- Retained 99.5% variance → 17 components

---

## Modeling

### Models Used

- Linear Regression
- Random Forest Regressor

### Techniques

- Train/test splits (75/25 and 80/20)
- 10-fold cross-validation
- Hyperparameter tuning using **GridSearchCV**

---

## Results

### Best Model: Random Forest

| Model | RMSE | R² | MAE |
|------|------|----|-----|
| Random Forest (80/20 + PCA) | 1.24 | 0.48 | 1.00 |

### Key Insights

- Random Forest significantly outperformed Linear Regression
- Linear models failed due to lack of linear relationships
- PCA slightly improved model performance
- Moderate overfitting observed but acceptable generalization

---

## Statistical Analysis

- Non-normal distributions confirmed (Shapiro-Wilk test)
- Bootstrapping used for confidence intervals
- Inferential analysis showed **weather significantly impacts yield (p = 0.003)**
- Density analysis revealed more stable yields in certain soil types (peat, silt)

---

## Feature Importance

Top predictors identified by Random Forest:

- Pest Infestation Level (~21%)
- Fertilizer Usage (~21%)
- Market Price (~18%)
- Production Cost (~17%)

---

## Key Takeaways

- Non-linear models are essential for complex agricultural data
- Pest control and fertilizer usage are critical for yield optimization
- Statistical assumptions (normality, linearity) do not hold in real-world datasets
- Combining statistics + machine learning improves insights and performance

---

## Limitations

- Dataset relatively small (900 rows)
- No temporal dynamics or external climate datasets
- Moderate model performance (R² < 0.5)

---

## Tools & Technologies

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn

---

## Future Work

- Incorporate weather time-series data
- Test advanced models (XGBoost, Neural Networks)
- Deploy as predictive tool or dashboard

---

## AI Usage Disclosure

This project used ChatGPT (OpenAI) to assist with code review and writing refinement. All analysis, modeling, and interpretation were conducted by the author.