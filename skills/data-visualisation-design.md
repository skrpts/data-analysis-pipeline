---
type: skill
id: data-visualisation-design
title: Data Visualisation Design
description: "Designs effective data visualisations to communicate research findings clearly"
tags: [Production, Tested, analysis:data, data:quantitative, data:visualisation]
connections:
  - target: llm-service
    type: runs_on
  - target: research-statistics-reference
    type: references
metadata:
  estimated_duration: "15-30 minutes"
  avg_tokens: 2500
---

## Capability

Designs data visualisations that effectively communicate research findings to academic and professional audiences. This skill recommends appropriate chart types, specifies design parameters, and provides implementation guidance for common tools (R ggplot2, Python matplotlib/seaborn, Excel). It focuses on clarity, accuracy, and adherence to publication standards rather than decorative aesthetics.

## When to Use

- Selecting the right chart type for a given data relationship
- Designing figures for a research paper, thesis, or conference presentation
- Creating visualisations that meet journal submission guidelines
- Presenting complex statistical results in an accessible format
- Designing qualitative data displays (thematic maps, code frequency charts)

## Inputs

- Data summary: variables to visualise, their types, and the relationship to display
- Target audience: academic journal, conference presentation, dissertation, general audience
- Publication requirements: colour restrictions (greyscale vs. colour), size constraints, accessibility standards
- Statistical results to represent: test outcomes, effect sizes, confidence intervals
- Preferred tools: R, Python, Excel, or tool-agnostic specifications

## Process

1. **Identify the message** — determine what the visualisation needs to communicate. Every figure should answer a specific question or illustrate a specific finding
2. **Select chart type** — match the data relationship to the most appropriate visual encoding:
   - Comparisons between groups: bar charts, box plots, violin plots
   - Distributions: histograms, density plots, Q-Q plots
   - Relationships between variables: scatter plots, bubble charts, heatmaps
   - Changes over time: line charts, area charts, slope graphs
   - Compositions: stacked bar charts, pie charts (used sparingly), treemaps
   - Qualitative themes: thematic maps, word clouds, code frequency charts
3. **Specify design parameters** — axis labels, scales, colour palettes, legends, annotations, error bars, confidence intervals
4. **Check accessibility** — ensure the visualisation works in greyscale, uses colourblind-friendly palettes, and has sufficient contrast
5. **Provide implementation** — supply code snippets or step-by-step instructions for the researcher's preferred tool

## Outputs

- Visualisation specification: chart type, data mappings, design parameters
- Implementation code or instructions for the target tool
- Accessibility notes and alternative representations
- Caption text suitable for publication

## Constraints

- Never use 3D charts, dual y-axes, or truncated axes unless explicitly justified
- Always include error bars, confidence intervals, or other measures of uncertainty where applicable
- Default to colourblind-friendly palettes (e.g., viridis, Color Universal Design)
- Respect the data-ink ratio principle — remove chartjunk and unnecessary visual elements
- Recommend individual data points alongside summary statistics where sample sizes are small (n < 30)
- Ensure all text in figures is legible at the intended reproduction size
