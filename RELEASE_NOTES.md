# Release Notes

## v1.1.30
GH#1100/GH#1045 (displaced-producer repair) — this pipeline documents five stages and ran three of them. `findings-synthesiser` was sitting in Stage 3's `qualitative-coding` slot, so it read `{{steps.Qualitative Coding.output}}` while running AS that step — a reference whose only possible target was its own not-yet-existing output (`step_reads_own_output`) — while `thematic-coder`, the prompt documented for Stage 3, and `statistical-test-selector`, documented for Stage 2, both shipped uninvoked (`node_never_invoked`). One defect, three findings: a displaced prompt, and the two stages it displaced.

Repaired to the stage order the workflow's own prose specifies. Added `statistical-test-selection` and `findings-synthesis` backing skills — a second entry on an existing skill slug shares its title, so every `from_step` naming it resolves to one of them silently. Stage 2 inserted (bound `dataset_profile` ← Quantitative Analysis), Stage 3 restored to `thematic-coder` (inputs only, no binding needed), Stage 4 inserted (bound `quantitative_findings` ← Statistical Test Selection and `qualitative_findings` ← Qualitative Coding, which is what "synthesise across data strands" requires).

Two consequential fixes the scanner did not flag. `interpret-data` bound `from_step: "Qualitative Coding"`, which under the old wiring meant the synthesis — rebound to Findings Synthesis to preserve the intent rather than the string. And `analysis-report-writer` declared FOUR labelled inputs of which three were the same positional `{{steps.previous.output}}`, so the report writer received one step's text three times under three headings; each is now a declared slot bound to the stage that produces it. Wiring Stage 3 then surfaced a finding the canonical scan does not raise: `thematic-coder` referenced no upstream output, because it is the ENTRY POINT for the qualitative strand — it takes raw transcripts from the user, exactly as its own documented stage input says. The flow check exempts only step 1, so a mixed-methods pipeline with two entry points cannot satisfy it positionally. Declared rather than worked around: the workflow now declares a `qualitative_data` input and `thematic-coder` binds it as a `context_param` via `from_input`, the same shape GH#1124's fix used for its position-1 step. Nothing was bound that the step does not genuinely consume. Outputs renamed to what they now hold (dataset_profile, thematic_coding). Skills 3→5, total 12→14.

## v1.1.29
GH#1100 consumer wave (batch 2) — declare the data flow this workflow was resolving positionally.

Each stage below now receives its input through a declared `bindings:` entry instead of `default_from_previous`, which K-073 revoked. **The value is unchanged**: every binding names the step that immediately precedes it, which is exactly what the positional default resolved to. What changes is that the dependency is stated rather than inferred from position, so a reorder can no longer silently feed a stage the wrong artefact.

Bindings added:
  `interpret-data` ← `from_step: "Qualitative Coding"` (step 3)
  `generate-visual-spec` ← `from_step: "Data Visualisation Design"` (step 5)
  `polish-language` ← `from_step: "Visual Spec Generation"` (step 6)

Dependency pins moved to the published versions that declare these slots:
  `design-visualisation` 1.0.3 → 1.0.4
  `generate-visual-spec` 1.0.3 → 1.0.4
  `interpret-data` 1.0.3 → 1.0.4
  `polish-language` 1.0.1 → 1.0.7
  `visual-spec-generation` 1.0.1 → 1.0.2

## v1.1.28
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.27
GH#745 — declare per-step `output: {name, type}` on every execution step (quantitative_analysis/text, qualitative_findings/text, interpretation/text, analysis_report/text, visual_spec/text, polished_report/text). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.26
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 8 inline shared-content files and declare 8 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.25
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.24
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.23
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.22
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.21
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
