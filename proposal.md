# The Impact of Daily Notifications on Mental Recovery Across Age Groups

## Motivation
In today’s digital environment, individuals are continuously exposed to smartphone notifications that interrupt attention and may increase cognitive load. These interruptions can negatively affect mental fatigue and sleep quality, which together represent an individual’s ability to recover mentally. Understanding how notification frequency impacts mental recovery is important for identifying healthier digital habits. Additionally, individuals may respond differently to digital exposure depending on their age, making it valuable to examine age-based differences in these effects.

## Data Sources
This project uses a publicly available dataset from Kaggle titled *Sleep, Screen Time, and Stress Analysis* (https://www.kaggle.com/code/lukhilaksh/sleep-screen-time-and-stress-analysis/input), which contains 15,000 observations, each representing an individual with behavioral, physiological, and demographic attributes such as age, gender, occupation, daily screen time, phone usage before sleep, number of notifications received per day, sleep duration, sleep quality score, stress level, caffeine intake, physical activity, and mental fatigue score. The dataset will be obtained in CSV format and imported into a Python environment using libraries such as pandas. Since all variables are recorded at the individual level, the dataset enables consistent analysis of relationships between lifestyle factors and mental health indicators.

## Data Enrichment
To enhance the analytical value of the dataset, feature engineering techniques will be applied. A composite metric called the **Mental Recovery Index (MRI)** will be created by combining sleep quality and mental fatigue to represent overall mental recovery. In addition, users will be grouped into age categories (e.g., 10–20, 20–35, 35–50, 50–70) to allow group-based comparisons. 
## Data Characteristics
The dataset consists of both numerical and categorical variables representing digital behavior, lifestyle factors, and mental health indicators. Key variables include notifications received per day, sleep quality, mental fatigue, stress level, and screen time. The dataset size (15,000 observations) allows for statistically meaningful analysis and supports both exploratory and comparative evaluation of relationships between variables.

## Expected Outcome
The project aims to determine whether higher notification exposure is associated with lower mental recovery and whether younger individuals are more sensitive to digital interruptions compared to older individuals. The findings are expected to provide insights into how notification behavior influences mental well-being and highlight age-dependent differences in these effects.
