# 🚗 Car Insurance Claim Classification Project

## 📌 Overview

This project focuses on building a **classification model** to predict whether a customer will file a car insurance claim or not based on their personal, demographic, driving, and vehicle-related features. This analysis aims to help insurance companies assess risk and make better-informed underwriting decisions.

---

## 🎯 Project Objectives

- Predict the likelihood of a customer **filing an insurance claim** (`OUTCOME`).
- Understand the **key factors** that influence this outcome.
- Provide **business insights** using explanatory visualizations.
- Build a **reproducible pipeline** that handles preprocessing, modeling, and evaluation.

---

## 📊 Dataset Description

- **Target Variable:** `OUTCOME` (Binary Classification)
- **Rows Represent:** Individual drivers/customers
- **Total Rows:** 10,000
- **Total Features:** 14 (13 predictors + 1 target)
- **Feature Types:**
  - Ordinal Categorical (e.g., AGE, EDUCATION)
  - Nominal Categorical (e.g., GENDER, VEHICLE_TYPE)
  - Numerical (e.g., ANNUAL_MILEAGE, SPEEDING_VIOLATIONS)

---

## 🧹 Data Cleaning and Preprocessing

### ✅ Steps Taken:

- **Missing Values** handled using `SimpleImputer` (constant or mean depending on feature type).
- **Ordinal Encoding** used for features with an inherent order:
  - Example: AGE (`16–25` < `26–39` < `40–64` < `65+`)
- **One-Hot Encoding** for nominal categorical features.
- **Feature Scaling** using `StandardScaler` after encoding.
- Built a **custom pipeline** using `ColumnTransformer` and `Pipeline` to ensure consistent preprocessing.

---

## 📈 Exploratory Data Analysis (EDA)

We performed comprehensive EDA to uncover patterns and trends:
- Age and driving experience impact claim likelihood.
- Higher DUIs, speeding violations, and past accidents correlate with higher claim risk.
- Visualizations included count plots, heatmaps, and bar plots.

---

## 🤖 Modeling Approach

- Used **Random Forest Classifier** for its robustness and ability to capture nonlinear patterns.
- Applied a default model to establish a performance baseline.
- Evaluated model performance using:
  - Accuracy
  - F1 Score
  - ROC-AUC

---

## 🧠 Feature Importance (Permutation Importance)

### 🔟 Top 10 Features:
1. `PAST_ACCIDENTS`
2. `DUIS`
3. `SPEEDING_VIOLATIONS`
4. `ANNUAL_MILEAGE`
5. `DRIVING_EXPERIENCE`
6. `AGE`
7. `EDUCATION`
8. `INCOME`
9. `GENDER`
10. `VEHICLE_YEAR`

These features make intuitive sense from a business perspective:
- More accidents or violations → higher risk.
- Mileage and age → exposure and maturity levels.
- Income and education → behavioral correlation with risk.

---

## 📊 Explanatory Visualizations

To communicate results to non-technical stakeholders, we created clear, informative, and business-relevant visuals:

### 1️⃣ DUIs vs Claim Likelihood

![DUIs vs Claims](https://github.com/baraa-hakawati/Car-Insurance-Claim-Analysis/blob/main/visuals/duis_vs_claims.png)

> 📌 **Insight:** Drivers with more DUIs are significantly more likely to file insurance claims. This supports using DUIs as a key underwriting criterion.

---

### 2️⃣ Annual Mileage vs Claim Probability

![Mileage vs Claims](https://github.com/baraa-hakawati/Car-Insurance-Claim-Analysis/blob/main/visuals/mileage_vs_claims.png)

> 📌 **Insight:** The probability of filing a claim increases with higher mileage. Higher road exposure raises the risk of accidents, making this a critical risk factor.

---

## 📉 Dimensionality Reduction and Feature Selection

- **Permutation Importance** was used to identify the most relevant features.
- Reducing to the top 10 features improved model interpretability with negligible performance loss.
- This can help deploy a lightweight model in production settings.

---

## ⚠️ Challenges Faced

- Proper encoding of **ordinal variables** required careful mapping.
- Dealing with **imbalanced class distribution** in the target variable.
- Feature selection and importance analysis needed to balance accuracy with interpretability.

---

## 📂 GitHub Repository

This project and all associated code, visualizations, and documentation are available at:

🔗 [Car Insurance Claim Classification GitHub Repository](https://github.com/baraa-hakawati/Car-Insurance-Claim-Analysis)

---

## 📌 Next Steps

- Apply cross-validation and hyperparameter tuning for optimal model performance.
- Test additional models such as XGBoost or LightGBM.
- Deploy the model using a web interface (e.g., Streamlit).
- Incorporate SHAP values for advanced interpretability.

---

## 🙌 Acknowledgments

Special thanks to the [DataCamp](https://www.datacamp.com) and [Scikit-Learn](https://scikit-learn.org) communities for tutorials and examples that helped build this project pipeline.

---

