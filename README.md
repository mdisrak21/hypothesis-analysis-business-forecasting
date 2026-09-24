# Statistical Inferential Hypothesis Analysis & Predictive Business Forecaster

## Project Overview

This project was completed as part of the **Progree Data Analytics Internship — Task 4**. It implements formal statistical hypothesis tests and a predictive business forecasting pipeline using the Online Retail II dataset.

## Task Requirements Covered

- A/B-style two-group significance validation using Welch's t-test
- One-way ANOVA across RFM customer segments
- Chi-Square independence evaluation of country group vs RFM segment
- SARIMA time-series forecasting of monthly revenue
- Holdout evaluation using MAE, RMSE and MAPE
- 95% confidence intervals for forecast boundaries
- Future six-month revenue projection

## Dataset

**Online Retail II** — UCI Machine Learning Repository

Source: https://archive.ics.uci.edu/dataset/502/online+retail+ii

DOI: 10.24432/C5CG6D

The dataset contains 1,067,371 transaction records covering 01/12/2009 to 09/12/2011.

## Tools

- Python
- Pandas / NumPy
- SciPy
- Statsmodels
- Matplotlib / Seaborn
- Jupyter Notebook

## Statistical Analysis

### A/B-style two-group validation

UK and non-UK customer monetary values are compared using Welch's two-sample t-test. This is an observational group comparison, not a randomized experiment.

### ANOVA

One-way ANOVA tests whether average monetary value differs across RFM customer segments. Tukey HSD post-hoc results are exported when the omnibus test is significant.

### Chi-Square

A Chi-Square independence test evaluates whether grouped country and RFM segment are statistically associated. The five largest customer countries are retained and all others are grouped as `Other`.

## Forecasting

Monthly revenue is modeled with **SARIMA(1,1,1) × (1,1,1,12)**. The last five observed months are held out for evaluation. The final model is refit on the full history for a six-month forward forecast.

Performance metrics and 95% forecast confidence intervals are exported as CSV files.

## Project Structure

```text
Task-4/
├── Progree_Task_4_Hypothesis_Forecasting.ipynb
├── Progree_Task_4_Final_Report.docx
├── README.md
├── outputs/
│   ├── ab_test_results.csv
│   ├── anova_results.csv
│   ├── anova_tukey_posthoc.csv
│   ├── chi_square_results.csv
│   ├── chi_square_contingency.csv
│   ├── monthly_business_metrics.csv
│   ├── forecast_test_set.csv
│   ├── forecast_model_performance.csv
│   ├── future_revenue_forecast.csv
│   └── task4_summary.csv
└── plots/
    ├── 01_sarima_holdout_forecast.png
    ├── 02_future_revenue_forecast.png
    ├── 03_rfm_segment_monetary.png
    └── 04_rfm_segment_boxplot.png
```

## Reproducibility

Place the authentic `online_retail_II.xlsx` workbook beside the notebook, or allow the notebook to fetch the dataset through `ucimlrepo`. Then run the notebook from top to bottom.

## Important Interpretation Note

Statistical significance does not by itself establish causality. The UK/non-UK comparison is observational, and the forecasting model's holdout error is reported explicitly so that the forecast is not presented as guaranteed.

## Internship

**Program:** Progree Data Analytics Internship  
**Task:** Task 4 — Statistical Inferential Hypothesis Analysis & Predictive Business Forecaster


