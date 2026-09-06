# Customer Churn Prediction

Predicting telecom customer churn using EDA and a Random Forest Classifier — analyzing 7,000+ customers to identify key churn drivers.

## Dataset
- 7,043 telecom customers, 21 features (demographics, services subscribed, billing info)
- Target: `Churn` (Yes/No) — ~26.6% churn rate

## Approach
1. Data cleaning (handled missing values, fixed data types)
2. Exploratory Data Analysis — visualized churn patterns across contract type, tenure, payment method, and services
3. Feature engineering — label encoding for categorical variables
4. Model: Random Forest Classifier (`class_weight='balanced_subsample'` to address class imbalance)

## Key Findings
- Month-to-month contract customers churn at ~75%, vs. ~3% for two-year contracts
- Customers without online security or tech support are significantly more likely to churn
- Top predictive features: `TotalCharges`, `MonthlyCharges`, `tenure`, `Contract`

## Model Performance
- Accuracy: 79.2%
- Recall (churned customers): 48%
- Precision (churned customers): 64%

*Note: Recall on churned customers is moderate due to class imbalance in the dataset (~27% churn rate). Addressed using `class_weight='balanced_subsample'`; future work could explore SMOTE or threshold tuning for further improvement.*

## Business Recommendation
Incentivize longer-term contracts and bundle security/support services with month-to-month plans to reduce churn risk.

## Tech Stack
Python, pandas, scikit-learn, Plotly, Seaborn, Random Forest
