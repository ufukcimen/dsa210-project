# The Impact of Daily Notifications on Mental Recovery Across Age Groups

## Motivation

In today's digital environment, individuals are continuously exposed to smartphone notifications that interrupt attention and may increase cognitive load. These interruptions can negatively affect mental fatigue and sleep quality, which together represent an individual's ability to recover mentally. This project investigates how notification frequency impacts mental recovery and whether these effects differ across age groups.

## Dataset

The project uses a publicly available dataset from Kaggle: [Sleep, Screen Time, and Stress Analysis](https://www.kaggle.com/code/lukhilaksh/sleep-screen-time-and-stress-analysis/input) containing 15,000 observations with the following variables:

| Variable | Description |
|---|---|
| `age` | Age of the individual |
| `gender` | Gender |
| `occupation` | Occupation type |
| `daily_screen_time_hours` | Daily screen time in hours |
| `phone_usage_before_sleep_minutes` | Phone usage before sleep in minutes |
| `sleep_duration_hours` | Sleep duration in hours |
| `sleep_quality_score` | Sleep quality score (1-10) |
| `stress_level` | Stress level (1-10) |
| `caffeine_intake_cups` | Daily caffeine intake in cups |
| `physical_activity_minutes` | Daily physical activity in minutes |
| `notifications_received_per_day` | Number of daily notifications |
| `mental_fatigue_score` | Mental fatigue score (1-10) |

## Feature Engineering

- **Mental Recovery Index (MRI):** A composite score combining sleep quality, sleep duration, mental fatigue, and stress level using min-max normalization. Higher MRI indicates better mental recovery.
- **Age Groups:** 10-20, 20-35, 35-50, 50-70
- **Notification Groups:** Low, Medium, High (based on quantiles)

## Project Structure

```
├── data/
│   ├── raw/                          # Original dataset
│   └── processed/                    # Cleaned dataset with engineered features
├── notebooks/
│   └── eda_hypothesis_tests.ipynb    # EDA and hypothesis testing notebook
├── proposal.md                       # Project proposal
├── proposal.pdf
├── requirements.txt
└── README.md
```

## Findings (Milestone 1: EDA & Hypothesis Testing)

### EDA Highlights
- Distributions of notifications and MRI were examined across the full sample
- Correlation heatmap and scatter plots explored relationships between key variables
- Boxplots compared MRI and notification levels across age groups

### Hypothesis Tests

| Test | Method | Result |
|---|---|---|
| Notifications vs MRI correlation | Pearson correlation | r = 0.006, p = 0.50 — Not significant |
| MRI across age groups | One-way ANOVA | F = 0.34, p = 0.80 — Not significant |
| Low vs High notification groups | Independent t-test | t = -0.62, p = 0.54 — Not significant |

None of the tests showed statistically significant relationships at the 0.05 significance level.

## How to Run

1. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

2. Open and run the notebook:
   ```
   jupyter notebook notebooks/eda_hypothesis_tests.ipynb
   ```

## Tools and Libraries

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scipy
