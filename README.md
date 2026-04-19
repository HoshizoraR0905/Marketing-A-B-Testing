# A/B Testing and Ad Effectiveness Analysis

## Overview
This project evaluates the causal impact of advertising on user conversion using a randomized A/B test, and extends the analysis to heterogeneity and predictive targeting. 

## Problem Statement
Given user-level exposure data, determine whether ads increase conversion and how user behavior relates to conversion outcomes. 

## Methods
Randomized A/B test (two-proportion z-test)
Confidence intervals and power/MDE analysis
Heterogeneous treatment effect analysis (by day and hour)
Logistic regression for conversion propensity modeling
Quantile-based ranking for targeting

## Results
### A/B test:
Conversion lift: +0.77% (absolute), +43% (relative)
95% CI: (0.60%, 0.94%)

z-statistic: 7.37
p-value: 8.5e-14
Strong evidence that ads increase conversion

### Heterogeneity
Effects are positive across most days, with moderate variation
Limited evidence of strong heterogeneity across hours due to noise in small segments

### Predictive Model
Logistic regression achieves ROC-AUC ≈ 0.81
Higher predicted scores correspond to higher observed conversion

## Targeting Insight
Users are segmented by predicted conversion propensity.
Top ~15% of users achieve significantly higher conversion rates (~5%–18%), suggesting a simple and effective targeting strategy.

## Key Takeaway
Ads have a clear positive causal effect on conversion
Effects are broadly consistent across segments
Predictive modeling enables efficient targeting based on user propensity

## Tech Stack
Python, Pandas, statsmodels, scikit-learn, Jupyter

## Files
main.ipynb: main analysis
