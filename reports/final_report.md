# Customer Churn Prediction — Final Report

## Objective
The objective of this project is to predict customer churn and identify the key factors associated with customer attrition. The goal is not only to build an accurate model, but also to provide actionable insights that can support customer retention strategies.

---

## Data Overview
The dataset contains customer demographic information, service subscriptions, contract details, and billing behavior. The target variable indicates whether a customer churned.

Key characteristics:
- Binary churn outcome
- Moderate class imbalance (approximately 25–30% churn)
- Mix of numeric and categorical features

---

## Modeling Approach
Two model families were evaluated:

- **Logistic Regression**  
  Used as an interpretable baseline model. Feature scaling and multicollinearity handling were applied.

- **Random Forest**  
  Used to capture non-linear relationships and feature interactions. This model is robust to correlated features and does not require scaling.

Both models were evaluated using ROC-AUC and Precision–Recall AUC. Threshold tuning was performed to align predictions with a churn-prevention objective.

---

## Results Summary

| Model | ROC-AUC | PR-AUC | Churn Recall | Churn Precision |
|------|--------|--------|-------------|-----------------|
| Logistic Regression (tuned) | ~0.84 | ~0.63 | ~0.75 | ~0.53 |
| Random Forest (tuned) | ~0.84 | ~0.65 | ~0.80 | ~0.51 |

The Random Forest model achieved the strongest overall performance, particularly in terms of recall for churned customers.

---

## Key Insights
- **Customer tenure** and **contract length** are the strongest predictors of churn.
- Customers on **month-to-month contracts** are significantly more likely to churn.
- **Higher monthly charges** and **fiber optic internet service** are associated with increased churn risk.
- Customers using **automatic payment methods** and subscribing to **support or security services** tend to be more stable.
- Demographic features play a relatively minor role compared to behavioral and contractual factors.

---

## Final Model Selection
The **Random Forest model**, tuned with a classification threshold of **0.35**, was selected as the final model. This threshold prioritizes recall, identifying approximately 80% of churned customers, which is appropriate for customer retention use cases where missing an at-risk customer is costly.

Logistic Regression remains valuable as a complementary model for interpretability and insight generation.

---

## Business Recommendation
Retention efforts should focus on:
- Customers with short tenure
- Month-to-month contracts
- High monthly charges
- Non-automatic payment methods

Encouraging longer-term contracts, bundled services, and automatic payments may reduce churn risk.
