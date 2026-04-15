# A/B Testing and Ad Effectiveness Analysis

## Overview
This project evaluates the effectiveness of an advertising treatment using A/B testing and logistic regression. It focuses on understanding both the overall treatment effect and the impact of exposure intensity and timing on user conversion.

## Problem Statement
Given user-level exposure data, determine whether showing ads increases conversion, and quantify how exposure intensity and timing influence conversion outcomes.

## Methods
One-sided two-proportion z-test for A/B testing
Sample size and power analysis
Logistic regression for conversion modeling
Feature engineering for exposure intensity and timing (day and hour)
Controlled analysis including treatment indicator to adjust for confounding

## Results
A/B test:
z-statistic: 7.37
p-value: 8.5e-14
Strong evidence that ads increase conversion
Regression:
Total ads coefficient ≈ 0.45 → higher exposure increases conversion odds
Ad group coefficient ≈ 0.37 → ~44% higher conversion odds after controlling for exposure and timing
Conversion is higher during early weekdays and afternoon/evening hours
Late-night exposure is associated with significantly lower conversion

## Key Insight
While the A/B test shows a strong positive effect of the ad treatment, part of this effect may be influenced by differences in exposure patterns. After controlling for exposure intensity and timing, the treatment effect remains positive, indicating a genuine contribution of the ad itself to conversion.
This highlights the importance of distinguishing between total effect and controlled (direct) effect in experimental analysis.

## Tech Stack
Python, Pandas, statsmodels, scikit-learn, Jupyter

## Files
main.ipynb: main analysis
