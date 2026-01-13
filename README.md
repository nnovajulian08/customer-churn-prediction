# Customer Churn Prediction

## Project Overview
This project builds a machine learning model to predict customer churn and identify key drivers of customer attrition using a telecom customer dataset.

The project follows an end-to-end data science workflow including exploratory analysis, feature engineering, modeling, evaluation, and interpretation.

---

## Project Structure
```
customer-churn-prediction/
├── data/
│   ├── raw/
│   │   └── telco_churn.csv
│   └── processed/
│       └── churn_processed.csv
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   └── 03_modeling.ipynb
│
├── reports/
│   ├── figures/
│   │   ├── roc_logistic.png
│   │   ├── pr_logistic.png
│   │   ├── roc_random_forest.png
│   │   ├── pr_random_forest.png
│   │   ├── rf_feature_importance.png
│   │   └── logistic_coefficients.png
│   └── final_report.md
│
├── src/
│
├── requirements.txt
└── README.md

```

## Methodology

### Exploratory Data Analysis
- Distribution analysis of key numeric features
- Churn rate comparisons across service and contract categories
- Identification of relationships between customer behavior and churn

### Feature Engineering
- One-hot encoding of categorical variables
- Multicollinearity analysis and feature selection
- Separate feature sets for linear and tree-based models

### Modeling
Two model families were evaluated:
- **Logistic Regression** (interpretable baseline)
- **Random Forest** (non-linear, high-recall model)

Models were evaluated using ROC-AUC, Precision–Recall AUC, and confusion matrices. Threshold tuning was applied to align predictions with churn-prevention objectives.

---

## Results Summary
- Best ROC-AUC: ~0.84
- Best PR-AUC: ~0.65
- Final model: **Random Forest (threshold = 0.35)**

The tuned Random Forest model identifies approximately 80% of churned customers, making it suitable for retention-focused use cases.

Detailed results and interpretations are available in  
📄 **[`reports/final_report.md`](reports/final_report.md)**

---

## Key Insights
- Customer tenure and contract length are the strongest churn predictors
- Month-to-month contracts significantly increase churn risk
- Higher monthly charges and fiber optic service are associated with increased churn
- Automatic payment methods and support services reduce churn likelihood

---

## How to Run
1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Run notebooks in order:

01_eda.ipynb

02_feature_engineering.ipynb

03_modeling.ipynb
