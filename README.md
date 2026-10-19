# Bank Customer Churn Analysis & Dashboard

End-to-end churn project: data cleaning, EDA, predictive modelling, and an interactive glassmorphism dashboard.

**Dataset:** Kaggle *Bank Customer Churn Modelling* (`Churn_Modelling.csv`, 10,000 customers). The raw file is not included; download it from Kaggle and place it next to the notebook (check the dataset's licence on its Kaggle page).
**Live dashboard:** https://raihat-singh.github.io/Bank_Churn_Analysis/dashboard/
## Results

| Model | CV ROC-AUC | Test ROC-AUC | Test accuracy |
|---|---|---|---|
| Logistic Regression | 0.843 | 0.848 | 76.4% |
| Gradient Boosting | 0.862 | 0.870 | 86.9% |

- Overall churn rate: **20.4%**
- Tuned threshold (~0.16, favouring recall): **82% of churners caught**, ~46% precision
- Top drivers: number of products, activity status, age, Germany, 3+ products
- Risk tiers (actual churn rate): Low ~9%, Medium ~46%, High ~88%

Scores are produced on all customers including the training split, so tier rates are slightly optimistic.

## Project structure
```
notebooks/bank_churn_analysis.ipynb   cleaning, EDA, features, models, importance, export
dashboard/index.html                  standalone interactive dashboard (open in a browser)
data/Cleaned_bank_churn.csv           all customers + ChurnProbability + RiskTier
data/top500_at_risk.csv               500 highest-risk customers
requirements.txt
```

## Run it
```bash
pip install -r requirements.txt
# put Churn_Modelling.csv in notebooks/, then:
jupyter notebook notebooks/bank_churn_analysis.ipynb
```
Open `dashboard/index.html` directly to view the results

## Skills demonstrated
Data cleaning, EDA, feature engineering, leakage-aware preprocessing, model comparison with cross-validation, threshold tuning, permutation importance, and dashboard design.
