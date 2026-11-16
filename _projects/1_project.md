---
layout: page
title: Predicting Employee Attrition (DDSAnalytics / Frito Lay)
description: Identifying the drivers of voluntary turnover and building a classifier to flag at-risk employees — MSDS 6306 Case Study 1
importance: 1
category: work
---

### Overview
DDSAnalytics was engaged by Frito Lay to identify the factors driving voluntary employee attrition and to build a model that flags at-risk employees so HR can intervene before they leave.

### Top 3 drivers of attrition
1. **Overtime** — employees who work overtime leave at 31.7%, more than 3x the rate of those who don't (9.7%).
2. **Monthly income / job level** — the lowest-earning quartile leaves at roughly 3x the rate of the highest-earning quartile; MonthlyIncome and JobLevel are highly correlated (r = 0.95) and represent the same compensation/seniority signal.
3. **Job role** — Sales Representatives leave at 45.3%, far above any other role, pointing to role-specific drivers rather than a company-wide problem.

### Model
A Naive Bayes classifier (18 predictors, log-transformed skewed numerics, validated with 5x repeated 10-fold cross-validation) reaches sensitivity ≈ 72.6% and specificity ≈ 72.0% at a 0.14 classification threshold — comfortably clearing the 60%/60% business requirement. A kNN model was also tested for comparison but had a slightly worse sensitivity/specificity balance.

### Other findings
Employees with no stock options leave at roughly 3x the rate of those who have them, and single employees leave more than twice as often as married employees — both retention levers that don't require a pay raise.

### Business impact
Targeting the model's at-risk list with a $200 retention incentive is estimated to save between $3.8M and $31.2M per year versus doing nothing, depending on assumed replacement-cost %, with an $11.7M midpoint estimate.

[Read the full analysis](CaseStudy1DDS.pdf) · [View the R Markdown source](Chinedu_Okoro_CaseStudy1DDS.Rmd)
