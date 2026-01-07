## Telco Customer Churn: Predictive Retention Analytics

## Project Overview

Customer churn is one of the most significant KPIs in the telecom industry. This project utilizes a dataset of 7,043 customers to build a machine learning pipeline that predicts which customers are likely to cancel their service.

**The Goal:** Move from reactive to proactive retention. By identifying high-risk customers, the business can offer targeted incentives (discounts, contract extensions) to reduce churn and protect revenue.

---

## 📈 Executive Summary

* **Best Performing Model:** Tuned XGBoost Classifier.
* **Key Metric (Recall):** **82%** (Capturing the vast majority of potential churners).
* **Financial Impact:** High-risk customers were found to be primarily on **month-to-month contracts** and **fiber optic** services, providing a clear roadmap for marketing intervention.

---

## 🛠️ The Data Pipeline

### 1. Exploratory Data Analysis (EDA)

We uncovered three critical "Churn Drivers":

* **Contract Type:** Month-to-month customers account for the highest churn volume.
* **Payment Method:** Electronic check users churn at a significantly higher rate than those with automated payments.
* **Tenure:** Customers are most likely to leave within the first **6 months** of their subscription.

### 2. Feature Engineering & Preprocessing

* **Handling Imbalance:** Applied **SMOTE** to balance the classes (Churn vs. No Churn).
* **Scaling:** Used `StandardScaler` on numerical features like `MonthlyCharges` and `TotalCharges`.
* **Encoding:** Transformed categorical variables using One-Hot Encoding for non-ordinal data.

### 3. Machine Learning Models

We evaluated multiple models to find the best balance between Precision and Recall:
| Model | Accuracy | Recall (Churn) | ROC-AUC |
| :--- | :--- | :--- | :--- |
| Logistic Regression | 79.2% | 71.0% | 0.83 |
| Random Forest | 80.5% | 66.0% | 0.82 |
| **XGBoost (Final)** | **82.1%** | **81.5%** | **0.86** |

---

## 📂 Repository Structure

```text
├── data/               # Dataset (ignored by git)
├── notebooks/          # EDA, Feature Engineering, and Modeling
├── src/                # Python scripts for the production pipeline
├── models/             # Saved model objects (.pkl)
├── requirements.txt    # Library dependencies
├── .gitignore          # Keeps the repo clean
└── LICENSE             # MIT License

```

---

## 🚀 Strategic Recommendations

Based on the model's findings, the following actions are recommended:

1. **Contract Migration:** Offer a 10% discount to month-to-month customers who switch to a 1-year contract.
2. **Onboarding Focus:** Implement a "First 90 Days" customer success program to reduce early-tenure churn.
3. **Service Quality:** Audit Fiber Optic service complaints, as this segment shows higher-than-average churn despite higher revenue.

---

## ⚙️ Setup & Installation

1. **Clone the Repository:**
```bash
git clone https://github.com/your-username/telco-churn-prediction.git


License
This project is licensed under the **MIT License** - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.
