---
type: skill
id: quantitative-analysis
title: Quantitative Analysis
description: "Guides statistical analysis of numerical research data — from descriptive statistics through inferential testing"
tags: [Production, Tested, analysis:data, data:quantitative]
connections:
  - target: llm-service
    type: runs_on
  - target: research-statistics-reference
    type: references
metadata:
  estimated_duration: "20-40 minutes"
  avg_tokens: 3000
---

## Capability

Provides structured guidance for quantitative data analysis in research contexts. This skill covers the full spectrum of statistical analysis: descriptive statistics, assumption checking, inferential testing, effect size calculation, and interpretation. It does not execute statistical code directly but produces detailed, actionable recommendations that researchers can implement in R, Python, SPSS, Stata, or any other statistical software.

## When to Use

- Profiling a new dataset to understand its structure and characteristics before analysis
- Selecting appropriate statistical tests for specific research questions and data types
- Checking whether statistical assumptions hold for a planned analysis
- Interpreting statistical output and translating results into meaningful findings
- Reviewing an existing analysis for methodological soundness

## Inputs

- Dataset summary: variable names, types (continuous, categorical, ordinal, binary), sample size, collection method
- Research questions or hypotheses to be tested
- Study design details: experimental vs. observational, independent vs. repeated measures, number of groups
- Any known constraints: non-normal distributions, small sample sizes, nested data structures
- Theoretical framework guiding the analysis (if applicable)

## Process

1. **Classify variables** — determine the measurement level and role (independent, dependent, covariate, moderator, mediator) of each variable
2. **Assess data quality** — evaluate missing data patterns (MCAR, MAR, MNAR), outlier detection strategies, and data cleaning requirements
3. **Select descriptive statistics** — choose appropriate measures of central tendency and dispersion for each variable type
4. **Match tests to questions** — for each research question, recommend the most appropriate statistical test based on variable types, sample size, number of groups, and study design
5. **Specify assumption checks** — list the assumptions for each recommended test and describe how to check them (e.g., Shapiro-Wilk for normality, Levene's for homogeneity of variance)
6. **Recommend alternatives** — for each test, provide a fallback if assumptions are violated (e.g., Mann-Whitney U instead of independent t-test)
7. **Calculate effect sizes** — recommend appropriate effect size measures (Cohen's d, eta-squared, Cramér's V, odds ratios) alongside significance tests
8. **Guide interpretation** — explain how to interpret results in the context of the research questions, including practical significance beyond statistical significance

## Outputs

- Variable classification table
- Missing data assessment with recommended handling strategy
- Statistical test recommendations with full justification
- Assumption check procedures
- Effect size measures and interpretation guidelines
- Suggested code snippets for R or Python (where helpful)

## Constraints

- Always recommend effect sizes alongside p-values — statistical significance alone is insufficient
- Flag when sample sizes are too small for reliable inference and recommend minimum sample sizes
- Never recommend a test without specifying its assumptions and how to check them
- When multiple valid approaches exist, present options with trade-offs rather than dictating a single choice
- Distinguish between exploratory and confirmatory analyses — pre-registered hypotheses require confirmatory approaches
