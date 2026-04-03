---
type: skill
id: visual-spec-generation
title: Visual Spec Generation
description: "Generates specifications for data visualisations, charts, and diagrams from analytical results"
tags: [Production, Data, Reporting]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Takes analytical results, datasets, or report findings and produces specifications for charts, graphs, and diagrams. Specifies chart type, axes, data mapping, labels, colours, and annotations — everything a rendering tool or designer needs to produce the visualisation.

## When to Use

- After a data analysis pipeline produces numerical results that need visual representation
- When writing reports that require charts or figures
- When preparing status updates or dashboards with visual metrics

## What It Produces

For each recommended visualisation:

1. **Chart type** — bar, line, scatter, pie, heatmap, flow diagram, etc.
2. **Data mapping** — which data fields map to which axes or segments
3. **Labels** — axis labels, legend entries, title, subtitle
4. **Annotations** — callouts, trend lines, threshold markers
5. **Colour scheme** — colour assignments for series or categories
6. **Size and layout** — recommended dimensions and placement context
7. **Narrative caption** — a plain-English description of what the visualisation shows

## What It Does NOT Do

- Render the actual image (it produces specs, not pixels)
- Access external data sources (it works with the data provided)

## Inputs

- Analytical results or dataset summary
- Report context (what story the visualisation should tell)
- Optional: style guidelines or colour constraints

## Outputs

One or more visualisation specifications, each with all fields above populated.
