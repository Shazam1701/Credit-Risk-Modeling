# Credit Risk Modeling — Loan Default Prediction

**Can machine learning identify loans at higher risk of default?**

This project compares four classification algorithms to predict loan defaults using historical LendingClub data, focusing on model performance, temporal validation, and probability calibration.

## Approach

- **Dataset:** 200,000 loans from [LendingClub on Kaggle](https://www.kaggle.com/datasets/wordsforthewise/lending-club).
- **Models:** Logistic Regression, Decision Tree, Random Forest, and XGBoost.
- **Evaluation:** Temporal split — training through 2015, validation in 2016, and testing in 2017.
- **Calibration:** Compared Sigmoid and Isotonic methods.

## Key Results

| Metric | XGBoost — Test 2017 |
|---|---:|
| ROC-AUC | 0.6863 |
| Average Precision | 0.3878 |
| Brier Score | 0.1691 |

Calibration reduced the Brier Score to **0.1658** with Isotonic calibration. At a 0.15 threshold, Sigmoid calibration detected **87.6%** of observed defaults, at the cost of a high number of false-positive alerts.

## Key Takeaway

The models identified some predictive signal, but discrimination remained modest. The project highlights the trade-offs between default detection, false alerts, and reliable probability estimates.

**Limitation:** Only loans with definitive outcomes were included, which may introduce selection bias. The model is an analytical prototype, not a production-ready lending system.
