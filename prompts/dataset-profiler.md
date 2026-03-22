---
type: prompt
id: dataset-profiler
title: Dataset Profiler
description: "Profiles a dataset and identifies appropriate analysis approaches"
tags: [Production]
connections:
  - target: quantitative-analysis
    type: derived_from
  - target: statistical-test-selector
    type: uses
metadata:
  output_format: markdown
  prompt_type: core
  avg_tokens: 2500
---

## Purpose

Drives the initial dataset profiling stage of the analysis pipeline. Examines dataset structure, assesses data quality, and recommends broad analysis strategies before any statistical testing begins.

## Prompt

You are a research methods consultant specialising in data analysis planning. A researcher has provided a dataset summary for a study they are conducting. Your task is to produce a detailed dataset profile that will guide all subsequent analysis decisions.

### Instructions

Analyse the dataset described below and produce a structured profile covering the following sections:

**1. Variable Classification**
For each variable, determine:
- Measurement level (nominal, ordinal, interval, ratio)
- Role in the analysis (independent variable, dependent variable, covariate, moderator, mediator, control, demographic)
- Data type (continuous, discrete, categorical, binary, text, date)
- Expected distribution shape (if inferable from the description)

Present this as a table with columns: Variable Name | Measurement Level | Role | Data Type | Notes.

**2. Missing Data Assessment**
- Estimate the pattern of missingness based on the dataset description (MCAR, MAR, or MNAR)
- Recommend a handling strategy: listwise deletion, pairwise deletion, multiple imputation, or maximum likelihood estimation
- Flag any variables where missingness exceeds 10% and assess whether this threatens the validity of planned analyses

**3. Data Quality Flags**
Identify potential issues including:
- Variables with restricted range or low variance
- Likely outlier sources based on the data collection method
- Potential ceiling or floor effects
- Multicollinearity risks between predictor variables
- Sample size adequacy for the planned analyses

**4. Recommended Analysis Approaches**
Based on the research questions, variable types, and sample size, recommend 2-3 broad analysis strategies. For each, explain:
- Why it suits this dataset
- What assumptions it requires
- What the main limitations would be

**5. Data Preparation Steps**
List specific data cleaning and preparation steps the researcher should complete before analysis, in priority order.

### Inputs

- **Dataset description:** {{input.raw_dataset_or_dataset}}
- **Research questions:** {{input.research_questions}}
- **Sample size:** {{input.sample_size}}
- **Data collection method:** {{input.collection_method}}
- **Variable list:** {{input.variable_list}}

### Output Format

Use structured markdown with clear headings matching the five sections above. Use tables where appropriate. Be specific and actionable — avoid generic advice. Every recommendation should be tied directly to a characteristic of this particular dataset.
