---
type: document
id: data-analysis-checklist
title: Data Analysis Checklist
description: "Pre-analysis and post-analysis quality checklist for research data analysis"
tags: [Production, Customer-Facing]
connections:
  - target: quantitative-analysis
    type: references
  - target: qualitative-coding
    type: references
metadata:
  document_type: checklist
  last_updated: "2026-03-01"
---

## Data Analysis Quality Checklist

Use this checklist at two points: before beginning your analysis (pre-analysis) and after completing it (post-analysis). Completing both sections helps ensure methodological rigour and reproducibility.

---

### Pre-Analysis Checklist

#### Data Preparation
- [ ] Raw data has been backed up before any cleaning or transformation
- [ ] A data dictionary exists documenting every variable (name, type, coding scheme, permissible values)
- [ ] Missing data has been assessed: percentage missing per variable and pattern of missingness (MCAR/MAR/MNAR)
- [ ] Missing data handling strategy has been selected and justified (listwise deletion, multiple imputation, maximum likelihood)
- [ ] Outliers have been identified using appropriate methods (z-scores, IQR rule, Mahalanobis distance) and a decision has been documented for each (retain, transform, winsorise, or exclude with justification)
- [ ] Variable distributions have been inspected visually (histograms, Q-Q plots) and with formal tests where necessary
- [ ] Any required data transformations (log, square root, z-score standardisation) have been applied and documented
- [ ] Categorical variables have been coded correctly (dummy coding, effect coding) with a clear reference category
- [ ] The dataset has been checked for duplicate records
- [ ] Anonymisation has been verified — no participant-identifying information remains in the analysis dataset

#### Analysis Planning
- [ ] Research questions or hypotheses are stated clearly and specifically before analysis begins
- [ ] For confirmatory analyses: hypotheses and analysis plan were pre-registered or specified before data collection
- [ ] For exploratory analyses: the exploratory nature is explicitly acknowledged
- [ ] Statistical tests have been selected based on data characteristics, not results
- [ ] Assumptions for each planned test have been identified and checks are planned
- [ ] The significance level (alpha) has been set and justified (typically 0.05)
- [ ] Multiple comparison corrections have been planned if conducting multiple tests (Bonferroni, Holm, FDR)
- [ ] Power analysis has been conducted (post-hoc if sample already collected; a priori if still recruiting)
- [ ] Effect size measures have been selected for each test
- [ ] The analysis script or syntax has been reviewed for errors before running

#### Qualitative Analysis (if applicable)
- [ ] Coding approach has been specified (inductive, deductive, or hybrid) with justification
- [ ] Theoretical framework guiding the analysis has been stated (or its absence justified)
- [ ] Anonymisation of transcripts is complete
- [ ] A reflexivity statement has been prepared acknowledging the researcher's positionality
- [ ] If multi-coder: inter-rater reliability procedure has been planned

---

### Post-Analysis Checklist

#### Quantitative Results
- [ ] All assumption checks have been reported (normality, homogeneity of variance, linearity, sphericity, multicollinearity)
- [ ] Where assumptions are violated, the consequence has been assessed and an appropriate remedy applied (robust test, non-parametric alternative, transformation)
- [ ] All statistical results include: test statistic, degrees of freedom, exact p-value, and effect size with confidence interval
- [ ] Results are reported in APA 7th edition format (or the target journal's required format)
- [ ] Non-significant results are reported as fully as significant results — no selective reporting
- [ ] Multiple comparisons have been corrected where applicable
- [ ] Descriptive statistics (means, SDs, frequencies) are reported for all key variables
- [ ] Tables and figures are clearly labelled with informative captions
- [ ] Figures use colourblind-friendly palettes and work in greyscale
- [ ] Individual data points are shown alongside summary statistics where sample sizes are small (n < 30)

#### Qualitative Results
- [ ] All themes are supported by multiple data extracts from multiple participants
- [ ] Quotations are attributed to anonymised participant identifiers
- [ ] The codebook is complete with code definitions and example extracts
- [ ] Analytical decisions (merging codes, splitting themes, discarding themes) are documented
- [ ] Deviant or contradictory cases have been actively sought and discussed
- [ ] If multi-coder: inter-rater reliability has been calculated and reported

#### Integration (if mixed methods)
- [ ] The integration strategy is explicitly stated (convergent, explanatory, exploratory, embedded)
- [ ] Convergences and divergences between strands are discussed transparently
- [ ] Neither strand is privileged over the other without methodological justification
- [ ] The integrated findings address the original research questions

#### Reproducibility
- [ ] All analysis steps are documented in sufficient detail for replication
- [ ] Analysis scripts or syntax are saved and version-controlled
- [ ] Software versions and package versions are recorded
- [ ] Random seeds are set and documented for any procedures involving randomisation
- [ ] The analysis pipeline can be re-run from raw data to final results without manual intervention
- [ ] All data files, scripts, and outputs are organised in a clear, logical directory structure
