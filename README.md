# 🚗 Car Insurance Claim Analysis

## 📌 Overview

This project analyzes car insurance claim data to identify factors influencing claim occurrences. By examining various customer and vehicle attributes, we aim to uncover patterns that can assist insurance companies in risk assessment and policy structuring.

## 📊 Dataset Description

- **Total Records:** 10,000
- **Features:** 19 (including demographic, vehicle, and driving history attributes)
- **Target Variable:** `OUTCOME` (indicates whether a claim was made)

## 🧹 Data Preprocessing

- **Missing Values:** Handled using `SimpleImputer` with appropriate strategies for different data types.
- **Categorical Encoding:**
  - *Ordinal Features:* Encoded using `OrdinalEncoder` with defined category orders.
  - *Nominal Features:* Encoded using `OneHotEncoder`.
- **Feature Scaling:** Applied `StandardScaler` to numerical features.
- **Pipeline Construction:** Utilized `ColumnTransformer` and `Pipeline` to streamline preprocessing steps.

## 📈 Exploratory Data Analysis (EDA)

- **Demographic Insights:** Analyzed distributions of age, gender, race, education, and income.
- **Driving History:** Examined the impact of driving experience, past accidents, DUIs, and speeding violations on claim likelihood.
- **Vehicle Attributes:** Investigated the relationship between vehicle type/year and claim occurrences.
- **Visualizations:** Employed bar plots and count plots to illustrate feature distributions and their correlation with the target variable.

## 🤖 Modeling Approach

- **Model Used:** Random Forest Classifier
- **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score
- **Feature Importance:** Assessed using permutation importance to determine the most influential features on claim prediction.

## 🔍 Key Findings

- **High-Risk Factors:** Past accidents, DUIs, and speeding violations significantly increase claim probability.
- **Demographic Influence:** Certain age groups and income levels show varying claim tendencies.
- **Vehicle Impact:** Newer vehicles and specific types correlate with different claim rates.

## 📂 Repository Structure

- `Car_Insurance_Claim_Analysis.ipynb`: Main analysis notebook containing data preprocessing, EDA, modeling, and conclusions.

---

*Note: For detailed code and visualizations, please refer to the [Car_Insurance_Claim_Analysis.ipynb](https://github.com/baraa-hakawati/Car-Insurance-Claim-Analysis/blob/main/Car_Insurance_Claim_Analysis.ipynb) notebook.*
