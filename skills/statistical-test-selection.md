---
type: skill
id: statistical-test-selection
title: Statistical Test Selection
description: "Selects appropriate statistical tests from data characteristics and research questions"
tags: [Research, Analysis]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Matches research hypotheses to statistical tests given variable types, sample size, and distributional assumptions. States the assumption checks each test requires, and the non-parametric or robust alternative to use when they fail.

## When to Use

- Choosing tests once a dataset has been profiled
- Checking whether a planned test's assumptions hold for the data in hand
- Finding a defensible alternative when those assumptions are violated

## Inputs

Dataset profile, research hypotheses, alpha level

## Outputs

Recommended tests with rationale, the assumption checks each requires, effect size measures, and a sample size adequacy assessment
