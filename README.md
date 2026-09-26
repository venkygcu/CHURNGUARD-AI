# CHURNGUARD AI — Customer Churn Prediction & Retention Intelligence System

MainCrafts Technology · 2-Day Skill Certification Program · Artificial Intelligence & Machine Learning

## Project structure

```text
CHURNGUARD-AI/
├── README.md
├── CHURNGUARD_AI_Venky.ipynb       # single project code notebook
├── requirements.txt
├── dataset/
│   └── customer_churn.csv
├── images/                         # EDA and evaluation charts
├── report/
│   └── CHURNGUARD_AI_Project_Report.pdf
├── ChurnGuard_AI_Live_Demo.html
└── churnguard_rf_model.joblib
```

## Install and run

From this project directory, install the notebook dependencies:

```powershell
python -m pip install -r requirements.txt
```

Execute the complete notebook and refresh its outputs, charts, and trained model:

```powershell
python -m jupyter nbconvert --to notebook --execute --inplace CHURNGUARD_AI_Venky.ipynb
```

To run the interactive browser demo locally:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000/ChurnGuard_AI_Live_Demo.html`.

## Dataset note

`dataset/customer_churn.csv` is a synthetic Telco-style churn dataset with 7,058 records and the same general columns and churn drivers as IBM Telco Customer Churn. The project report documents this limitation. If MainCrafts supplies the official dataset, replace this CSV with it and rerun the notebook.

## Results summary

| Model | Accuracy | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.826 | 0.649 | 0.370 | 0.471 |
| Random Forest (baseline) | 0.825 | 0.652 | 0.356 | 0.461 |
| Random Forest (tuned, selected) | 0.781 | 0.484 | 0.719 | **0.578** |

The tuned Random Forest uses class weighting to improve churn recall. See `report/CHURNGUARD_AI_Project_Report.pdf` for methodology, interpretation, and limitations.

## Live demo

The GitHub Pages homepage opens the interactive demo: https://venkygcu.github.io/CHURNGUARD-AI/

The project root page redirects visitors to ChurnGuard_AI_Live_Demo.html; the README and report remain available in the repository.
