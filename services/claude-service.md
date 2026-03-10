---
type: service
id: claude-service
title: Claude Service
description: "Anthropic Claude integration for data analysis reasoning, statistical guidance, and qualitative coding"
tags: [Production, Tested]
connections:
  - target: anthropic-claude
    type: runs_on
metadata:
  provider: anthropic
  model: claude-sonnet
---

## Service Description

This skrpt uses Anthropic Claude as the primary reasoning engine for all data analysis tasks. Claude handles statistical method selection, qualitative thematic coding, data profiling interpretation, and narrative synthesis of findings.

## How This Skrpt Uses Claude

### Dataset Profiling
Claude analyses dataset summaries — variable types, distributions, missing data patterns — and recommends appropriate analysis strategies. It does not execute code directly but provides structured guidance that researchers can implement in their preferred statistical software.

### Statistical Reasoning
Claude recommends statistical tests based on research questions, data characteristics, and assumptions. It explains the rationale for each recommendation and flags common pitfalls such as violation of normality assumptions or insufficient sample sizes.

### Qualitative Coding
Claude applies thematic analysis frameworks to qualitative data (interview transcripts, open-ended survey responses, field notes). It generates initial codes, groups them into themes, and provides illustrative quotations for each theme.

### Synthesis and Reporting
Claude synthesises findings across quantitative and qualitative strands, identifies convergences and divergences, and drafts analysis sections following academic conventions.

## Configuration

- **Model:** Claude Sonnet or higher recommended for nuanced statistical reasoning
- **Context window:** Extended context beneficial for processing longer transcripts and datasets
- **Temperature:** 0.3 for statistical recommendations, 0.5 for qualitative coding, 0.4 for synthesis
- **Output format:** Structured markdown with tables, code suggestions, and narrative text
