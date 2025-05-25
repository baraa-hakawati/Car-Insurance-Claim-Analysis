# 🧠 Car Insurance Claim Prediction: Exploratory Analysis and Machine Learning

This project implements a complete data science pipeline to predict the likelihood of car insurance claims using machine learning. It includes data wrangling, exploratory data analysis (EDA), preprocessing, model training, and performance evaluation across multiple model pipelines.

---

## 📂 Dataset Overview

The dataset includes demographics, driving history, and vehicle characteristics of insurance policyholders. The primary target is the `OUTCOME` variable:

- `0` = No claim filed  
- `1` = Claim filed

---

## 🔍 Exploratory Data Analysis (EDA)

### 🔗 Correlation Heatmap

A correlation heatmap was used to explore relationships among numeric features. Key negative correlations with `OUTCOME` include:

- `VEHICLE_OWNERSHIP`: -0.38  
- `CREDIT_SCORE`: -0.33  
- `PAST_ACCIDENTS`: -0.31  
- `SPEEDING_VIOLATIONS`: -0.29  

These features have predictive value for claim classification.

![Feature Correlation Heatmap](images/corr.png)

---

## 💡 Feature Importance

Feature importance was analyzed using permutation importance. The most influential features in the base model include:

1. `DRIVING_EXPERIENCE`  
2. `VEHICLE_OWNERSHIP`  
3. `VEHICLE_YEAR`  
4. `POSTAL_CODE`  
5. `GENDER`  
6. `PAST_ACCIDENTS`  
7. `SPEEDING_VIOLATIONS`  
8. `RACE`  
9. `DUIS`  
10. `VEHICLE_TYPE`  

These were key across all model configurations.

![Feature Importance](images/Feature_importance.png)

---

## 🤖 Model Training & Evaluation

### 1. **Base Random Forest Model**
| Metric        | Class 0 (No Claim) | Class 1 (Claim) |
|---------------|-------------------|-----------------|
| Precision     | 0.86              | 0.76            |
| Recall        | 0.90              | 0.67            |
| F1-Score      | 0.88              | 0.71            |
| **Accuracy**  | **0.83** overall  |                 |

### 2. **Random Forest + PCA (3 Components)**
| Metric        | Class 0           | Class 1         |
|---------------|-------------------|-----------------|
| Precision     | 0.83              | 0.69            |
| Recall        | 0.88              | 0.60            |
| F1-Score      | 0.85              | 0.64            |
| **Accuracy**  | **0.79**          |                 |

### 3. **Random Forest + KMeans + RFE Feature Selection**
| Metric        | Class 0           | Class 1         |
|---------------|-------------------|-----------------|
| Precision     | 0.86              | 0.73            |
| Recall        | 0.89              | 0.68            |
| F1-Score      | 0.87              | 0.71            |
| **Accuracy**  | **0.82**          |                 |

---

## 🔁 Feature Comparison Across Models

| Feature                 | Base Model | PCA Model | KMeans+RFE Model |
|-------------------------|------------|-----------|------------------|
| DRIVING_EXPERIENCE      | ✅         | ✅        | ✅               |
| VEHICLE_OWNERSHIP       | ✅         | ✅        | ✅               |
| VEHICLE_YEAR            | ✅         | ✅        | ✅               |
| POSTAL_CODE             | ✅         | ✅        | ✅               |
| GENDER                  | ✅         | ✅        | ✅               |
| PAST_ACCIDENTS          | ✅         | ✅        | ✅               |
| SPEEDING_VIOLATIONS     | ✅         | ✅        | ✅               |
| RACE                    | ✅         | ✅        | ✅               |
| DUIS                    | ✅         | ✅        | ✅               |
| VEHICLE_TYPE            | ✅         | ✅        | ✅               |
| PCA Components          | ❌         | ✅        | ❌               |
| Cluster ID (KMeans)     | ❌         | ❌        | ✅               |

- **Consistent Features:** All models agreed on the importance of driving experience, ownership, past driving behavior (accidents, violations), and demographic characteristics like gender and race.
- **New Features:** The KMeans model introduces **cluster IDs** as a new engineered feature. The PCA model reduces dimensionality but may lose interpretability.
- **Feature Selection:** RFE in the final model helps narrow down to the 10 most critical features from a broader set, improving performance marginally with less complexity.

---

## ✅ Key Insights

- Driving behavior and demographics are highly predictive of claim likelihood.
- All models achieve solid performance (~79–83% accuracy), with trade-offs between interpretability and dimensionality.
- The **base model** performs best on Class 1 recall (safety-critical), while the **KMeans+RFE model** balances both precision and recall.
- PCA is effective but reduces performance slightly due to transformation loss.

---

## 🔧 Future Improvements

- Addressing class imbalance using SMOTE or cost-sensitive learning  
- Hyperparameter tuning for ensemble models  
- Exploring more robust feature engineering (e.g., time-based patterns)  
- Model interpretability techniques (e.g., SHAP values)

---

📧 Contact: bara-hakawati@hotmail.com  
📂 Full Notebook: [Car_Insurance_Claim_Analysis.ipynb](https://github.com/baraa-hakawati/Car-Insurance-Claim-Analysis/blob/main/Car_Insurance_Claim_Analysis.ipynb)
