---
type: skill
id: qualitative-coding
title: Qualitative Coding
description: "Applies systematic thematic coding to qualitative data using established frameworks"
tags: [Production, Tested, Data, Research]
connections:
  - target: llm-service
    type: runs_on
  - target: research-statistics-reference
    type: references
metadata:
  estimated_duration: "30-60 minutes"
  avg_tokens: 3500
---

## Capability

Performs systematic qualitative data analysis following established methodological frameworks, primarily Braun and Clarke's reflexive thematic analysis. This skill processes interview transcripts, open-ended survey responses, focus group transcripts, field notes, and other textual data to identify patterns, generate codes, develop themes, and produce a coherent thematic narrative grounded in the data.

## When to Use

- Analysing interview or focus group transcripts for a qualitative or mixed-methods study
- Coding open-ended survey responses to identify recurring patterns
- Performing thematic analysis on field notes or observational data
- Developing a codebook for a multi-coder qualitative study
- Reviewing and refining existing qualitative codes for consistency

## Inputs

- Qualitative data: transcripts, text responses, or field notes (anonymised)
- Research questions guiding the analysis
- Theoretical or conceptual framework (if applicable — purely inductive analysis is also supported)
- Coding approach preference: inductive (data-driven), deductive (theory-driven), or hybrid
- Any pre-existing codes or codebook to build upon

## Process

1. **Familiarisation** — read through the data thoroughly, noting initial impressions, recurring ideas, and striking passages
2. **Initial coding** — generate codes systematically across the entire dataset. Each code captures a meaningful unit of data relevant to the research questions. Codes should be concise, descriptive, and consistently applied
3. **Code review** — consolidate overlapping codes, split overly broad codes, and ensure each code has a clear definition
4. **Theme searching** — group related codes into candidate themes. A theme captures something important about the data in relation to the research questions and represents a patterned response or meaning
5. **Theme reviewing** — check that themes work in relation to the coded extracts and the full dataset. Themes should be coherent internally, distinct from each other, and collectively tell a meaningful story
6. **Theme defining** — write a clear definition for each theme, specifying its scope, boundaries, and relationship to other themes. Identify sub-themes where appropriate
7. **Reporting** — produce a narrative account of each theme supported by illustrative quotations from the data

## Outputs

- Codebook: complete list of codes with definitions and example quotations
- Thematic map: visual representation of themes, sub-themes, and their relationships
- Theme definitions: detailed description of each theme with scope and boundaries
- Data extracts: key quotations organised by theme with participant identifiers
- Reflexivity notes: observations about the coding process and analytical decisions made

## Constraints

- Never fabricate quotations or attribute codes to data that does not support them
- Maintain an audit trail of all coding decisions for transparency and reproducibility
- Distinguish between semantic codes (surface meaning) and latent codes (underlying assumptions) — be explicit about which level of analysis is being applied
- Respect participant confidentiality — use anonymised identifiers only
- When using a deductive approach, remain open to codes that do not fit the pre-existing framework rather than forcing data into predetermined categories
- Acknowledge the researcher's positionality and its potential influence on coding decisions
