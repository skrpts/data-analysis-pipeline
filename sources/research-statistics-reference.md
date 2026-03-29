---
type: source
id: research-statistics-reference
title: Research Statistics Reference
description: "Reference guide to common statistical methods used in social science and health research"
tags: [Production, Customer-Facing, Data, Research]
connections: []
metadata:
  source_type: reference
  last_updated: "2026-03-01"
---

## Common Statistical Tests Reference Guide

### Tests for Comparing Groups

| Test | Use Case | IV Type | DV Type | Groups | Assumptions |
|------|----------|---------|---------|--------|-------------|
| Independent t-test | Compare means of two independent groups | Categorical (2 levels) | Continuous | 2 independent | Normality, homogeneity of variance, independence |
| Paired t-test | Compare means of two related measurements | Within-subjects (2 levels) | Continuous | 2 related | Normality of differences, independence of pairs |
| One-way ANOVA | Compare means across 3+ independent groups | Categorical (3+ levels) | Continuous | 3+ independent | Normality, homogeneity of variance, independence |
| Repeated measures ANOVA | Compare means across 3+ related measurements | Within-subjects (3+ levels) | Continuous | 3+ related | Normality, sphericity, independence |
| Two-way ANOVA | Examine effects of two factors and their interaction | 2 categorical IVs | Continuous | Varies | Normality, homogeneity of variance, independence |
| ANCOVA | Compare group means while controlling covariates | Categorical + continuous covariate | Continuous | 2+ independent | Normality, homogeneity of variance, homogeneity of regression slopes |
| Mann-Whitney U | Non-parametric alternative to independent t-test | Categorical (2 levels) | Ordinal/continuous | 2 independent | Independence, similar distribution shapes |
| Wilcoxon signed-rank | Non-parametric alternative to paired t-test | Within-subjects (2 levels) | Ordinal/continuous | 2 related | Symmetry of differences |
| Kruskal-Wallis | Non-parametric alternative to one-way ANOVA | Categorical (3+ levels) | Ordinal/continuous | 3+ independent | Independence, similar distribution shapes |
| Friedman test | Non-parametric alternative to repeated measures ANOVA | Within-subjects (3+ levels) | Ordinal/continuous | 3+ related | Independence of groups |

### Tests for Relationships

| Test | Use Case | Variable Types | Assumptions |
|------|----------|---------------|-------------|
| Pearson's r | Linear relationship between two continuous variables | 2 continuous | Normality, linearity, homoscedasticity |
| Spearman's rho | Monotonic relationship between two ranked variables | 2 ordinal/continuous | Monotonic relationship |
| Chi-squared test | Association between two categorical variables | 2 categorical | Expected frequencies >= 5, independence |
| Fisher's exact test | Association when expected frequencies are small | 2 categorical | Independence (no minimum frequency requirement) |
| Simple linear regression | Predict one continuous variable from another | 1 continuous IV, 1 continuous DV | Linearity, normality of residuals, homoscedasticity, independence |
| Multiple regression | Predict one variable from several predictors | Multiple IVs, 1 continuous DV | Linearity, normality of residuals, homoscedasticity, no multicollinearity |
| Logistic regression | Predict a binary outcome from predictors | Multiple IVs, 1 binary DV | Independence, no multicollinearity, linearity of logit |
| Ordinal regression | Predict an ordinal outcome from predictors | Multiple IVs, 1 ordinal DV | Proportional odds assumption |

### Effect Size Measures

| Measure | Test | Small | Medium | Large | Interpretation |
|---------|------|-------|--------|-------|----------------|
| Cohen's d | t-tests | 0.2 | 0.5 | 0.8 | Standardised mean difference |
| Eta-squared (eta sq) | ANOVA | 0.01 | 0.06 | 0.14 | Proportion of variance explained |
| Partial eta-squared | Factorial ANOVA | 0.01 | 0.06 | 0.14 | Proportion of variance explained (controlling other factors) |
| Cohen's f | ANOVA | 0.10 | 0.25 | 0.40 | Root of variance ratio |
| Pearson's r | Correlation | 0.10 | 0.30 | 0.50 | Correlation coefficient |
| R-squared | Regression | 0.02 | 0.13 | 0.26 | Proportion of variance explained |
| Cramér's V | Chi-squared | 0.10 | 0.30 | 0.50 | Association strength for categorical variables |
| Odds ratio | Logistic regression | 1.5 | 2.5 | 4.0 | Odds multiplier (approximate benchmarks) |

### Assumption Checks

| Assumption | Test/Method | Decision Rule |
|------------|-------------|---------------|
| Normality | Shapiro-Wilk test | p > 0.05 suggests normality is not violated |
| Normality (visual) | Q-Q plot | Points should fall approximately on the diagonal line |
| Homogeneity of variance | Levene's test | p > 0.05 suggests equal variances |
| Sphericity | Mauchly's test | p > 0.05 suggests sphericity is met; if violated, use Greenhouse-Geisser correction |
| Linearity | Scatter plot of residuals vs. fitted | No systematic pattern |
| Homoscedasticity | Residuals vs. fitted plot | Constant spread of residuals across fitted values |
| Multicollinearity | VIF (Variance Inflation Factor) | VIF < 5 (conservative: < 3) |
| Independence | Durbin-Watson test | Values near 2 indicate no autocorrelation |

### Sample Size Rules of Thumb

| Analysis | Minimum Recommendation |
|----------|----------------------|
| t-test | 30 per group for adequate power at medium effect size |
| ANOVA (3 groups) | 20-25 per group |
| Correlation | 85 for detecting r = 0.30 at power = 0.80 |
| Multiple regression | 50 + 8 per predictor (Tabachnick & Fidell) or 10-15 per predictor |
| Logistic regression | 10 events per predictor variable |
| Chi-squared | 5 expected frequency per cell minimum |
| Factor analysis | 5-10 participants per variable, minimum 100 total |
| SEM | 200+ recommended; 10 per estimated parameter |
