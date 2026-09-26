# CHURNGUARD AI — Customer Churn Prediction & Retention Intelligence System

MainCrafts Technology · 2-Day Skill Certification Program · Artificial Intelligence & Machine Learning

## Contents

```
CHURNGUARD AI/
├── README.md
├── CHURNGUARD_AI_Venky.ipynb        # source notebook (Steps 1–15 + Day 2 challenges, already run)
├── CHURNGUARD_AI_Project_Report.pdf # project report (required submission doc)
├── ChurnGuard_AI_Live_Demo.html     # client-side logistic-regression demo
├── customer_churn.csv               # dataset used
├── churnguard_rf_model.joblib       # trained, tuned model
└── images/                          # exported EDA + evaluation charts
```

## How to run

1. Open `CHURNGUARD_AI_Venky.ipynb` in Google Colab or Jupyter.
2. Upload `customer_churn.csv` to the same folder as the notebook.
3. Run all cells top to bottom.

To open the interactive demo, open `ChurnGuard_AI_Live_Demo.html` in a browser. It runs locally
without a server and uses the exported logistic-regression coefficients. Enter the customer's
cumulative `TotalCharges` value along with the other profile fields; the saved Random Forest is
the selected model in the notebook, so its predictions and the demo's logistic-regression scores
will not be identical.

## Note on the dataset

No internet access was available while building this in the assistant's sandbox, so the official IBM Telco
Customer Churn CSV could not be downloaded. `customer_churn.csv` is a synthetic dataset built to match the
same columns, size (~7,000 rows) and realistic churn drivers (contract type, tenure, internet service,
payment method, etc.) as the real Telco dataset, so the entire notebook, metrics and conclusions are
genuine, reproducible outputs — not hand-typed numbers. **If MainCrafts supplies an official dataset**,
swap it in as `customer_churn.csv` (same expected columns) and re-run the notebook; everything downstream
is generic and will recompute against the real data automatically.

## Results summary

| Model | Accuracy | Precision | Recall | F1 |
|---|---|---|---|---|
| Logistic Regression | 0.826 | 0.649 | 0.370 | 0.471 |
| Random Forest (baseline) | 0.825 | 0.652 | 0.356 | 0.461 |
| Random Forest (tuned, selected) | 0.781 | 0.484 | 0.719 | **0.578** |

Random Forest was tuned with `class_weight="balanced"` to reduce false negatives (missed churners), the
costliest error for a retention business — see the Project Report for full reasoning.
