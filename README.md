# The Impact of Daily Notifications on Mental Recovery Across Age Groups

DSA 210 — Introduction to Data Science (Spring 2026) term project.

📄 **Read the full results: [FINAL_REPORT.pdf](FINAL_REPORT.pdf)**

## Headline Finding

The original hypothesis — that daily notifications harm mental recovery and that younger users are more affected — is **not supported**.
What this dataset actually shows is that **total daily screen time** (not the count of notifications) is the dominant predictor of mental recovery, with a Pearson correlation of **r ≈ −0.80** with the Mental Recovery Index (MRI). Machine-learning models reach **R² ≈ 0.70 / accuracy ≈ 85%** for predicting MRI from behavioral features — and ≈ 84% of that predictive power comes from `daily_screen_time_hours` alone. The notification count itself contributes almost nothing.

## Dataset

[Sleep, Screen Time, and Stress Analysis](https://www.kaggle.com/code/lukhilaksh/sleep-screen-time-and-stress-analysis/input) from Kaggle — 15,000 individuals, 13 variables.

| Variable | Description |
|---|---|
| `age` | Age (18–59) |
| `gender` | Female / Male / Other |
| `occupation` | 8 categories |
| `daily_screen_time_hours` | Total screen time (1.0–10.0) |
| `phone_usage_before_sleep_minutes` | Pre-sleep phone use (0–119) |
| `sleep_duration_hours` | Sleep length (4.0–9.0) |
| `sleep_quality_score` | 1–10 |
| `stress_level` | 1–10 |
| `caffeine_intake_cups` | 0–4 |
| `physical_activity_minutes` | 0–119 |
| `notifications_received_per_day` | 20–299 |
| `mental_fatigue_score` | 1–10 |

## Feature Engineering

- **Mental Recovery Index (MRI)** — composite score combining sleep quality, sleep duration, mental fatigue, and stress level. Four variants are compared (additive min-max, multiplicative, z-score, weighted) to check whether the choice of formula or the way normalization handles outliers affects conclusions — results are robust across all four.
- **Age groups** — 10-20, 20-35, 35-50, 50-70
- **Notification groups** — Low / Medium / High (quantile-based)

## Project Structure

```
├── README.md                       # This file
├── FINAL_REPORT.pdf                # Final report (motivation, methods, findings, limitations)
├── proposal.pdf                    # Original proposal
├── requirements.txt                # Python dependencies
├── .gitignore
├── data/
│   ├── raw/                        # Original Kaggle dataset
│   └── processed/                  # Cleaned dataset with engineered features
└── notebooks/
    ├── eda_hypothesis_tests.ipynb  # EDA, feature engineering, hypothesis testing
    └── ml_models.ipynb             # Regression + classification ML models
```

## Hypothesis Tests (α = 0.05)

| Test | Statistic | p-value | Decision |
|---|---|---|---|
| Pearson: notifications vs MRI | r = 0.006 | 0.495 | Fail to reject H0 |
| ANOVA: MRI across age groups | F = 0.34 | 0.799 | Fail to reject H0 |
| t-test: Low vs High notifications | t = −0.62 | 0.535 | Fail to reject H0 |

## ML Models

| Task | Best model | Metric |
|---|---|---|
| MRI regression | Gradient Boosting | **R² ≈ 0.70** |
| MRI classification (high vs low) | Logistic Regression | **Accuracy ≈ 0.85, AUC ≈ 0.93** |
| Top predictor | — | `daily_screen_time_hours` (84% importance) |

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/eda_hypothesis_tests.ipynb   # cleaning, EDA, hypothesis tests
jupyter notebook notebooks/ml_models.ipynb              # ML models, feature importance
```

## Tools and Libraries

Python 3 · pandas · numpy · matplotlib · seaborn · scipy · scikit-learn · jupyter
