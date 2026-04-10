---
type: prompt
id: design-visualisation
title: "Design Visualisation"
description: "Designs data visualisation specifications from analytical results"
tags: [Production, Data]
connections:
  - target: data-visualisation-design
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the data visualisation design skill.

## Prompt

You are a data visualisation specialist. Design visualisation specifications for the analytical results below.

### Analysis Results

{{steps.previous.output}}

### Instructions

For each key finding that benefits from a visual representation:

1. **Chart type** — select the most effective type (bar, line, pie, scatter, heatmap, table, etc.)
2. **Title** — clear, descriptive title
3. **Data mapping** — which data maps to which axis or dimension
4. **Axes** — labels, scales, ranges, units
5. **Colours** — what colours represent and why (use accessible palettes)
6. **Annotations** — key data points to highlight, trend lines, benchmarks
7. **Dimensions** — recommended width × height

### Rules

- One message per chart — don't combine unrelated data
- Choose chart types based on the relationship: comparison → bar, trend → line, composition → pie, correlation → scatter
- Every visualisation should answer a specific question
- Specify enough detail that a rendering tool or designer can produce the chart without guesswork

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
