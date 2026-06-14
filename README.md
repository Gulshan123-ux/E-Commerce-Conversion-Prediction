# 🛒 E-Commerce Conversion Prediction — Summer Analytics 2026

## Project Structure
```
hacker/
├── data/
│   ├── train.csv           ← place here
│   └── private_test.csv    ← place here
├── notebook.ipynb          ← full ML pipeline
├── submission.csv          ← generated after running notebook
├── methodology_report.pdf  ← generated in last cell
└── README.md
```

## Quick Start
1. Place `train.csv` and `private_test.csv` in the `data/` folder
2. Run all cells: `jupyter nbconvert --to notebook --execute notebook.ipynb`
3. Collect `submission.csv` and `methodology_report.pdf`

## Pipeline Overview
| Step | Detail |
|------|--------|
| Feature Engineering | 8 new features (engagement score, loyalty proxy, rate features, bands) |
| Models | XGBoost · LightGBM · Random Forest |
| Validation | 5-Fold Stratified CV |
| Ensemble | Weighted-average OOF probabilities |
| Threshold | Swept 0.30–0.70, maximise F1 on OOF |
| Imbalance | scale_pos_weight (XGB), class_weight=barulanced (LGB/RF) |

## Deliverables
- `submission.csv` — `User_ID, Converted` predictions for private test set
- `notebook.ipynb` — reproducible end-to-end notebook
- `methodology_report.pdf` — one-page PDF report (auto-generated in Cell 10)
