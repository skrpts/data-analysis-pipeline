---
type: workflow
id: data-analysis-pipeline
title: Data Analysis Pipeline
description: "End-to-end quantitative and qualitative data analysis workflow for research projects"
tags: [Production, Tested, Academic, Data]
connections:
  - target: quantitative-analysis
    type: uses
  - target: qualitative-coding
    type: uses
  - target: data-visualisation-design
    type: uses
  - target: data-interpretation
    type: uses
  - target: language-polish
    type: uses
  - target: llm-service
    type: runs_on
  - target: research-statistics-reference
    type: references
  - target: data-analysis-checklist
    type: references
  - target: analysis-report-template
    type: uses
  - target: visual-spec-generation
    type: uses
metadata:
  estimated_duration: "60-120 minutes"
  trigger: manual
output_step: "language-polish"
composite_steps:
  - "quantitative-analysis"
  - "qualitative-coding"
  - "data-visualisation-design"
  - "data-interpretation"
  - "analysis-report-template"
  - "visual-spec-generation"
  - "language-polish"
execution:
  - skill: "quantitative-analysis"
    step_type: "synthesis"
    prompt: "dataset-profiler"
  - skill: "qualitative-coding"
    step_type: "synthesis"
  - skill: "data-interpretation"
    step_type: "synthesis"
  - skill: "data-visualisation-design"
    step_type: "synthesis"
  - skill: "visual-spec-generation"
    step_type: "synthesis"
  - skill: "language-polish"
    step_type: "content"
---

## Overview

This workflow orchestrates a complete data analysis cycle for research projects, supporting both quantitative and qualitative approaches. It guides researchers from initial dataset profiling through statistical testing, qualitative coding, synthesis, and final report writing. The pipeline is designed for mixed-methods research but works equally well for purely quantitative or purely qualitative studies — simply skip the irrelevant stages.

## Pipeline Stages

### Stage 1: Dataset Profiling

**Input:** Raw dataset or dataset summary (variable names, types, sample size, collection method), research questions

Invoke the **quantitative-analysis** skill via the **dataset-profiler** prompt. The profiler examines the dataset's structure, identifies variable types (continuous, categorical, ordinal), flags missing data patterns, detects potential outliers, and recommends broad analysis approaches suited to the data characteristics and research questions.

**Output:** Dataset profile report with variable classifications, descriptive statistics summary, missing data assessment, and recommended analysis strategies.

**Checkpoint:** Review the profile before proceeding. If the dataset has significant quality issues (more than 20% missing data on key variables, severe outliers, or unexpected variable types), address data cleaning before continuing.

### Stage 2: Statistical Test Selection

**Input:** Dataset profile from Stage 1, specific research hypotheses or questions

Invoke the **quantitative-analysis** skill via the **statistical-test-selector** prompt. Based on the data characteristics, sample size, variable types, and research questions, recommend appropriate statistical tests with full justification.

**Output:** Recommended statistical tests with rationale, assumption checks required, effect size measures, and sample size adequacy assessment.

**Checkpoint:** Verify that assumption checks pass before running the recommended tests. If assumptions are violated, the prompt provides alternative non-parametric or robust methods.

### Stage 3: Qualitative Coding

**Input:** Qualitative data (interview transcripts, open-ended survey responses, field notes), research questions, theoretical framework (if applicable)

Invoke the **qualitative-coding** skill via the **thematic-coder** prompt. Apply systematic thematic coding following Braun and Clarke's six-phase approach: familiarisation, initial coding, theme searching, theme reviewing, theme defining, and reporting.

**Output:** Codebook with code definitions, themed groupings, illustrative quotations, and a thematic map showing relationships between themes.

**Checkpoint:** Review initial codes for consistency and completeness. Ensure themes are coherent, distinctive, and grounded in the data rather than imposed from theory.

### Stage 4: Findings Synthesis

**Input:** Quantitative results from Stage 2, qualitative themes from Stage 3, research questions

Invoke the **quantitative-analysis** and **qualitative-coding** skills via the **findings-synthesiser** prompt. Synthesise findings across data strands, identifying where quantitative and qualitative findings converge, diverge, or complement each other.

**Output:** Integrated findings narrative with convergence/divergence analysis, triangulation assessment, and key insights.

**Checkpoint:** Ensure the synthesis does not overstate convergence or ignore contradictions. Flag any findings that are supported by only one data strand.

### Stage 5: Analysis Report Writing

**Input:** All outputs from Stages 1-4, the **analysis-report-template** asset

Invoke the **data-visualisation-design** skill and the **analysis-report-writer** prompt. Produce a complete analysis section suitable for a research paper, dissertation chapter, or standalone report. Include recommendations for visualisations to support the narrative.

**Output:** Complete analysis report draft with visualisation specifications.

## Error Handling

- If the dataset profile reveals insufficient data for the planned analysis, recommend minimum sample sizes and suggest alternative approaches that work with smaller samples
- If statistical assumptions are violated and no suitable alternative test exists, document the limitation explicitly rather than proceeding with an inappropriate test
- If qualitative coding produces too many codes (over 80), revisit the coding framework and consolidate at a higher level of abstraction
- If quantitative and qualitative findings directly contradict each other, present both strands transparently and discuss possible explanations rather than privileging one over the other
- If the dataset contains sensitive data (identifiable participants, health records), flag this at the profiling stage and ensure all outputs are appropriately anonymised

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.raw_dataset_or_dataset}}` | Yes | Raw dataset or dataset summary (variable names, types, sample size, collection method) | `Paste the latest metrics, exported data, or summary notes relevant to the workflow.` |
| `{{input.research_questions}}` | Yes | The research questions guiding analysis | `What is the relationship between X and Y?` |
| `{{input.specific_research_hypotheses_or}}` | Yes | Specific research hypotheses or questions for statistical testing | `Students who receive intervention X will score higher on measure Y than controls.` |
| `{{input.qualitative_data}}` | No | Qualitative data (interview transcripts, open-ended responses, field notes) | `Paste the latest metrics, exported data, or summary notes relevant to the workflow.` |
| `{{input.sample_size}}` | No | Total sample size | `150` |
| `{{input.collection_method}}` | No | How the data was collected | `Online survey with convenience sampling` |
| `{{input.variable_list}}` | No | List of variables in the dataset | `age, gender, score_pre, score_post, group` |
| `{{input.study_design}}` | No | The study design used | `Between-subjects experimental design` |
| `{{input.alpha_level}}` | No | Significance level for statistical tests | `0.05` |
| `{{input.coding_approach}}` | No | Qualitative coding approach | `inductive` |
| `{{input.theoretical_framework}}` | No | Theoretical framework for qualitative analysis | `none — inductive analysis` |
| `{{input.participant_context}}` | No | Context about participants for qualitative analysis | `12 secondary school teachers from urban schools` |
| `{{input.integration_approach}}` | No | Mixed-methods integration approach | `convergent` |
| `{{input.discipline}}` | No | Academic discipline for reporting conventions | `Psychology` |
| `{{input.target_format}}` | No | Target journal or report format | `APA journal article` |
| `{{input.reporting_standard}}` | No | Reporting standard to follow | `APA 7th edition` |

## Outputs

| Name | Description |
|------|-------------|
| Dataset profile report | Dataset profile report with variable classifications, descriptive statistics summary, missing data assessment, and recommended analysis strategies |
| Recommended statistical tests | Recommended statistical tests with rationale, assumption checks required, effect size measures, and sample size adequacy assessment |
| Codebook | Codebook with code definitions, themed groupings, illustrative quotations, and a thematic map showing relationships between themes |
| Integrated findings narrative | Integrated findings narrative with convergence/divergence analysis, triangulation assessment, and key insights |
| Complete analysis report draft | Complete analysis report draft with visualisation specifications |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Raw Dataset Or Dataset: "Paste the latest metrics, exported data, or summary notes relevant to the workflow."
Research Questions: "Paste the relevant brief, notes, source material, or dataset here."
Specific Research Hypotheses Or: "Paste the relevant brief, notes, source material, or dataset here."
Qualitative Data: "Paste the latest metrics, exported data, or summary notes relevant to the workflow."
```

