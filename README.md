A/B Testing and Conversion Analysis for Ad Effectiveness


Overview

This project analyzes the effectiveness of an advertising treatment using A/B testing and regression modeling. The goal is to evaluate whether showing ads increases user conversion, and to understand how exposure intensity and timing affect user behavior.


Dataset

The dataset contains user-level data with the following fields:

user id — unique identifier
test group — treatment (ad) or control (psa)
converted — whether the user converted (1 or 0)
total ads — total number of ads shown
most ads day — day with highest ad exposure
most ads hour — hour with highest ad exposure


Methodology

1. A/B Test

We perform a one-sided two-proportion z-test:
H0: conversion rates are the same
H1: ad group has higher conversion

Result:
z-statistic: 7.37
p-value: 8.5e-14

Conclusion:
The p-value is far below 0.05, so we reject H0.
This provides strong evidence that the ad treatment increases conversion.

2. Sample Size & Power

Assuming:
significance level = 0.05
power = 0.9

The required sample size depends on the expected effect size. 
Detecting a 50% relative increase in conversion requires ~9,285 users
Since the dataset is larger than this threshold, the experiment is sufficiently powered.

3. Regression Analysis

We fit a logistic regression model to analyze conversion drivers using:
total ads (exposure intensity)
most ads day (timing)
most ads hour (timing)

Key findings:
Total ads: Positive coefficient (~0.45)
More ads lead to higher conversion odds (~57% increase per unit)
Day effect
Higher conversion on early weekdays (Mon–Wed)
Hour effect
Best performance: afternoon to evening (2pm–9pm)
Worst performance: late night / early morning (1am–7am)

4. Controlled Treatment Effect

To account for confounding factors, we include test group in the regression.

Result:
Coefficient (ad): 0.366
Odds ratio ≈ 1.44

Interpretation:
After controlling for exposure and timing:
Users in the ad group have ~44% higher odds of conversion
The effect is not solely driven by exposure differences
This suggests a true positive treatment effect.


Business Impact

The results can be translated into practical insights:
Ads significantly increase conversion
Increasing exposure improves outcomes
Timing matters:
Afternoon/evening ads perform best
Late-night ads are less effective


Implication:
Ad performance can be improved by:
optimizing ad frequency
focusing delivery on high-performing time windows


Tech Stack

Python
Pandas
Statsmodels
Scikit-learn


Author

Yunxuan Yi
Ph.D. in Applied Mathematics
Focus: optimization, data analysis, and statistical modeling
