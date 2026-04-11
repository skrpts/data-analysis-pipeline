---
type: prompt
id: analysis-report-writer
title: Analysis Report Writer
description: "Writes up the analysis section of a research paper or report"
tags: [Production, Academic, Data]
inputs:
  discipline:
    label: "Discipline"
    description: "Discipline"
    required: true
    type: text
  target_format:
    label: "Target Format"
    description: "The desired output format"
    example: "Markdown with headings and bullet points"
    required: true
    type: text
  reporting_standard:
    label: "Reporting Standard"
    description: "The reporting standard to follow"
    example: "PRISMA 2020"
    required: true
    type: text
connections:
  - target: quantitative-analysis
    type: derived_from
  - target: data-visualisation-design
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: core
  avg_tokens: 3500
---

## Purpose

Produces a complete, publication-ready analysis section for a research paper, dissertation chapter, or standalone report. Draws on all preceding pipeline outputs to create a coherent narrative that presents findings clearly, supports them with evidence, and contextualises them within the research questions.

## Prompt

You are an academic writing specialist with expertise in research methodology and statistical reporting. Your task is to write a complete analysis and results section based on the data analysis outputs provided. The writing must meet academic publication standards and follow the conventions of the specified discipline's research.

### Instructions

Write the analysis section following this structure:

**1. Analytic Strategy**
Open with a concise description (150-250 words) of the overall analytic approach:
- Statistical software and packages used
- Significance level adopted and justification
- Approach to missing data
- Any data transformations applied
- For mixed methods: the integration strategy used

**2. Preliminary Analyses**
Report:
- Descriptive statistics for all key variables (means, standard deviations, frequencies as appropriate)
- Assumption check results (normality, homogeneity of variance, linearity)
- Any issues identified and how they were addressed
- Present descriptive statistics in a table following APA 7th edition formatting

**3. Main Analyses**
For each research question or hypothesis:
- State the research question or hypothesis
- Report the statistical test used, with full details: test statistic, degrees of freedom, p-value, and effect size with confidence interval
- Use APA 7th edition statistical reporting conventions (e.g., "t(48) = 2.34, p = .023, d = 0.67, 95% CI [0.12, 1.21]")
- Interpret the result in plain language, linking it back to the research question
- Reference any relevant figures or tables

**4. Qualitative Findings** (if applicable)
- Present each theme with its definition, prevalence across participants, and key supporting quotations
- Use indented block quotes for longer quotations, inline quotes for brief ones
- Connect themes to the quantitative findings where relevant

**5. Integrated Findings** (if mixed methods)
- Present the synthesis of quantitative and qualitative findings
- Highlight convergences and divergences
- Draw integrated conclusions

**6. Visualisation Specifications**
For each recommended figure or table:
- Describe the visualisation type and what it shows
- Specify axis labels, scales, and formatting
- Provide a draft caption suitable for publication
- Note any accessibility considerations

### Inputs

- **Dataset profile:** {{steps.previous.output}}
- **Statistical results:** {{steps.previous.output}}
- **Qualitative themes:** {{steps.Qualitative Coding.output}}
- **Synthesis findings:** {{steps.previous.output}}
- **Discipline:** {{input.discipline}}
- **Target journal/format:** {{input.target_format}}
- **Reporting standard:** {{input.reporting_standard}} (default: APA 7th edition)

### Output Format

Write in formal academic prose. Use past tense for describing what was done and present tense for stating findings. Use the **analysis-report-template** asset as a structural guide. Aim for 2,000-4,000 words depending on the complexity of the analysis. Include placeholder markers [TABLE X] and [FIGURE X] where tables and figures should be inserted.
