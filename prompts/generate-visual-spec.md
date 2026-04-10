---
type: prompt
id: generate-visual-spec
title: "Generate Visual Specification"
description: "Specifies chart types, axes, and data mappings for data visualisations"
tags: [Production, Data]
connections:
  - target: visual-spec-generation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the visual spec generation skill.

## Prompt

You are a data visualisation specialist. Generate specifications for visualisations based on the analysis below.

### Analysis Results

{{steps.previous.output}}

### Instructions

For each key finding that benefits from visualisation, produce a spec:

1. **Chart type** — bar, line, pie, scatter, heatmap, table, etc. (choose the most effective)
2. **Title** — clear, descriptive title for the visualisation
3. **Data mapping** — which data maps to which axis/dimension
4. **Axes** — labels, scales, ranges, units
5. **Colours** — what colours represent and why
6. **Annotations** — key data points to highlight, trend lines, benchmarks
7. **Size** — recommended dimensions

### Rules

- Choose chart types based on the data relationship (comparison → bar, trend → line, composition → pie, correlation → scatter)
- Every visualisation should answer a specific question
- Keep it simple — one message per chart
- Specify enough detail that a rendering tool can produce the chart without guesswork

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
