# SUVs and Pedestrian Deaths

## Overview

This project explores the rise in pedestrian fatalities in the United States between 2010 and 2019 and investigates potential contributing factors — particularly the increasing number of SUVs and cell phone subscriptions. Using two structured datasets (by year and by state), we conducted extensive data analysis and statistical testing to uncover correlations and trends. The project uses Python for data manipulation, visualization, and regression modeling.

## Objectives

- Identify statistical trends in pedestrian fatalities over time.
- Examine the potential relationship between SUV sales, mobile phone usage, and pedestrian death rates.
- Determine the impact of handheld device and texting bans at the state level.
- Evaluate predictive power of key variables using linear regression.

## Data Sources

- **pedestriandeathsbystate.xlsx**: State-level data from 2010–2019, including fatality rates and policy indicators.
- **pedestriandeathsbyyear.xlsx**: National-level data for the same period, including vehicle types and cell subscriptions.

## Technologies Used

- Python (Pandas, NumPy, Matplotlib, Seaborn, SciPy, StatsModels, Scikit-Learn)
- ThinkStats2 (for PMF/CDF analysis)
- Jupyter/Google Colab

## Key Analyses

### Descriptive Statistics

- Fatality rates by year and state
- Mean, standard deviation, variance, min, and max across all numeric variables

### Histograms & PMFs

- Distribution of deaths by state and year
- Differences in states with handheld/texting bans
- Vehicle type and cell phone adoption over time

### Correlation & Hypothesis Testing

- Pearson correlations:
  - Light Trucks and Fatality Rate: **0.97**
  - Cell Subscriptions and Fatality Rate: **0.95**
- Welch’s t-test: Significant difference between means of SUV/light truck sales and fatality rate

### Regression Modeling

- Simple and multiple linear regression using:
  - Light Truck sales
  - Cell subscriptions
- Best model performance:
  - **R² = 0.935** (Light Trucks only)
  - Coefficient (slope): ~9e-5 per unit of SUV sale

## Insights

- SUV/light truck growth strongly correlates with pedestrian death rates.
- Cell phone subscriptions may contribute, though significance is lower in multivariate models.
- State texting bans were nearly universal by 2019, making them hard to assess statistically.
- Light truck sales are a strong predictor and raise serious concerns for pedestrian safety.

## Limitations

- Small sample size (10 years)
- Correlation ≠ causation
- Lack of real-time or driver-level behavior data
- Limited geographic detail on policy impact

## Future Work

- Add more granular data (county/city level)
- Include weather, traffic, and population density variables
- Investigate causal inference techniques (e.g., difference-in-differences)
- Explore lag effects of policy changes on safety outcomes

## Repository Structure

