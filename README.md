# Proactive Churn Prevention: A Data-Driven Retention Strategy 📈

This project implements a data-driven strategy for proactive customer churn prevention in an e-commerce platform. It leverages machine learning to identify at-risk customers, understand churn drivers, and develop targeted retention strategies to ensure sustainable revenue growth and improved marketing efficiency.

## Dataset

The analysis uses a **transactional dataset** of approximately **5,600 customers**, including demographics, behavioral metrics, and transaction history. The overall churn rate is **17%**.

**Data File:** The raw data is in `data.xlsx` in this repo. Use that file to run the code.

## Methodology

The project followed a pipeline involving:

1.  **Data Preparation & Cleaning:** Outlier handling, feature merging, missing value imputation.
2.  **Feature Engineering:** Binning, ratio feature creation, statistical significance testing (Chi-squared, T-test).
3.  **Model Development:** Train-test split, OHE, standardization, imbalance handling, training of multiple models (Logistic Regression, Decision Tree, Random Forest, XGBoost, CatBoost).
4.  **Model Evaluation & Tuning:** Selection of best model based on ROC AUC and accuracy, hyperparameter tuning to improve recall.

## Model Performance

**XGBoost (Tuned)** achieved the best performance among the models evaluated.

| Model                  | ROC AUC | Accuracy | AUC-PR |
| :--------------------- | :------ | :------- | :----- |
| **XGBoost (Tuned)**    | 0.999   | 0.987    | 0.996  |
| XGBoost                | 0.998   | 0.985    | 0.992  |

## Business Insights

Key findings include:

*   **46.7% of low-tenure customers** are in medium-to-high churn risk classes.
*   **Churn Drivers:** Customer complaints, missing tenure data, and city tier.
*   **Retention Drivers:** Absence of complaints, longer tenure.
*   **High-Risk Indicators:** Lower average cashback, very low median tenure (1 month), high complain rate (60.2%), and higher use of Cash on Delivery.

## Targeted Retention Strategies

A segment-based retention strategy is proposed:

1.  **New & At-Risk Onboarding:** For low tenure, complaining customers; focus on early engagement and satisfaction surveys.
2.  **Service Recovery:** For high-tenure, complaining customers; focus on proactive resolution and recovery offers.
3.  **Trust-Sensitive COD Users:** For Cash on Delivery users; offer discounts for first digital payments to build trust.
4.  **Under-Engaged with Loyalty:** For customers with low cashback per order; focus on loyalty program education and gamification.

## How to Run the Code

1.  **Clone the Repository:** `git clone https://github.com/ashley-andrea/churn-prevention.git`
2.  **Install Dependencies:** `pip install pandas numpy scikit-learn xgboost catboost matplotlib seaborn`
3.  **Data:** Ensure `data.xlsx` is in the repository root.
4.  **Execute:** Run the provided notebook to replicate the analysis.
