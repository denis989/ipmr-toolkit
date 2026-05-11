---
tool_id: TOOL-225
slug: tried-benchmark
name: TRIED Benchmark (Truly Innovative and Effective AI Detection)
maintainer: WITNESS
type: reference
outline_cells:
 - {id: "1C.3", role: secondary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: reference
last_verified: 2026-05-10
license: open
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: [PH, LK]
tags: [benchmark, evaluation-framework, sociotechnical, witness, global-south, fairness, reference]
---

# TRIED Benchmark (Truly Innovative and Effective AI Detection)

**Publisher:** [witness.org](https://witness.org/resources/?cat=deepfakes) | **Type:** Reference framework | **Cost:** Free

!!! abstract "TL;DR"
    A free, open sociotechnical evaluation framework released by
    WITNESS in July 2025 that tests AI detection tools on real-
    world Global South effectiveness across six pillars including
    fairness and representation. Listed in 1C.3 as the
    institutional reference for evaluating any 1A / 1B / 1C
    detector card in this toolkit before adoption; the third
    reference card in the toolkit alongside InVID-WeVerify
    (multi-cell deployable tool exemplar) and Kalimasada
    (single-country tipline exemplar).

## What it does

TRIED is not a tool. It is a structured methodology for evaluating
whether an AI-detection tool is fit for Global South use, organised
around six pillars: technical performance, robustness, fairness,
explainability, accessibility, and accountability. WITNESS released
the framework in July 2025 to address the gap between vendor
headline-accuracy claims and operational reality in the contexts
where WITNESS's Deepfake Rapid Response Force (DRRF) actually
operates, including documented Philippines and Sri Lanka
consultations alongside other Global South cases.

The framework's institutional value sits in two adjacent uses.
First, an SEA fact-check coalition or research lab evaluating
whether to adopt Sensity, Reality Defender, Hive, or any other
detector in the toolkit's shortlist can apply TRIED's six pillars
as a structured procurement test rather than relying on vendor
materials. Second, a published debunk that cites a detector verdict
can attach a TRIED-style assessment of the detector's
appropriateness for the case's specific Global South context, which
materially strengthens defamation defence and platform-appeal work.
TRIED does not produce detection signals; it produces
defensibility about how detection signals were generated.

## When to use it

- A regional fact-check coalition is evaluating procurement of
 Sensity or Reality Defender and needs a
 structured Global-South-grounded framework rather than vendor
 marketing for the assessment.
- A research-grade publication is auditing how AI detection tools
 perform on SEA-region content and TRIED's six pillars are the
 appropriate evaluation structure.
- A defamation-defence or platform-appeal file requires
 documentation of why the chosen detector was appropriate for the
 specific case context (Asian face, SEA language, codec-
 compressed input).
- An institutional partner is producing a regional advocacy report
 on detector accountability and TRIED's accountability pillar
 provides the structured framing.

## Limitations

!!! info "Limitations"
    - Methodology, not deployable software. TRIED
    cannot be installed or run; it is applied as an evaluation
    structure to the detectors listed elsewhere in this toolkit.
    - The six pillars require interpretive judgement to score; two
    analysts applying TRIED to the same detector may produce
    different findings on fairness and explainability where the
    detector's documentation is thin.
    - Released July 2025; the framework is recent and has not yet
    accumulated a large corpus of published applications outside
    WITNESS's own DRRF cases.
    - English-language framework documentation; SEA-language
    adaptations would require translation and regional-context
    revision rather than direct application.

## Privacy and threat model

TRIED is methodology applied to existing detector outputs and
documentation; no data flow is intrinsic to the framework itself.
Privacy considerations apply to the detectors being evaluated
(see Sensity, Reality Defender, Hive,
XAI-Deepfakes, TruFor for the per-detector
privacy and threat models that TRIED's accountability pillar
asks the evaluator to surface).

The threat model that matters here is institutional rather than
data-flow: a TRIED evaluation that names a detector as failing on
a specific pillar is published research output that vendor
relationships may complicate. Apply standard institutional
research-publication discipline; the framework's accountability
pillar specifically asks evaluators to consider these dynamics.

## Country and platform applicability

- **Indonesia:** language-agnostic methodology; applicable to
 any detector evaluation an Indonesian fact-check coalition wishes
 to conduct on Bahasa-relevant content.
- **Laos:** language-agnostic; applicable in principle but
 the detector evaluations the framework structures will surface
 the Lao-specific gap that is already pinned at cell level in 1A.3
 and 1B.3.
- **Malaysia:** language-agnostic; applicable to detector
 evaluations on Malay, English, Mandarin, or Tamil content.
- **Philippines:** documented use through WITNESS PH
 workshops as part of the Doc Willie Ong / Brawner case context
. The framework is the reference
 layer alongside the Rappler / #FactsFirstPH detector pipeline.
- **Sri Lanka:** documented relevance via WITNESS DRRF
 Global South consultations covering Sri Lanka ; applicable to evaluations of Sinhala and Tamil
 content detection.
- **Thailand:** language-agnostic methodology; applicable
 to evaluations of Thai-content detection by Thai PBS, SONP, or
 Cofact-affiliated research.

Platform applicability: not platform-specific. The framework
applies to evaluation of any detector regardless of which
platform's content the detector processes.

## How to access

Free download of the TRIED framework documentation from the
WITNESS website. The framework is open and documented as
methodology rather than as software: an evaluator reads the six-
pillar structure, applies it to a detector under evaluation, and
produces the assessment as a research artefact. WITNESS conducts
periodic workshops applying the framework in DRRF and partner-
country contexts.

## Cost (current as of 2026-05)

Free. Open framework. The structural cost is the evaluator's time
to apply the six pillars to a detector under evaluation, plus any
data costs incurred in producing the empirical inputs (test
datasets, robustness probes, fairness audits) that the framework
asks the evaluator to surface.

## Quickstart

(Not applicable in the per-card-tool sense. The framework is
applied to other tools rather than executed.)

1. Select the detector under evaluation (for example, Sensity for an institutional procurement decision; Hive for a workflow integration choice).
2. Read the TRIED six-pillar structure on the WITNESS website.
3. For each pillar (technical performance, robustness, fairness,
 explainability, accessibility, accountability), assemble the
 evidence available about the detector: vendor materials,
 independent benchmarks, published deployments, case observations.
4. Score or characterise the detector against each pillar, naming
 gaps explicitly.
5. Surface the scoring as an evaluation artefact attached to the
 procurement, deployment, or publication decision.
6. Cite the WITNESS framework in the published artefact so the
 methodology is traceable and reproducible.

## In the toolkit's workflow

Source-history non-detector reference per Architectural Anchor 1.
Sits in 1C.3 Institutional explainable AI forensics as the
institutional reference framework alongside XAI-Deepfakes
(primary deployable detector with explanation output) and TruFor (alternative deployable framework with reliability map).
Cross-cell role: TRIED is applied during evaluation of any detector
in the toolkit's shortlist: Hive, ImageWhisperer,
Sensity, Reality Defender, Deepware,
Hiya, TrueMedia, Pangram, GPTZero, DeepfakeBench, XAI-Deepfakes, TruFor.

Standard combinations:

- With **Sensity** and **Reality Defender** at
 1C.2 as the procurement-evaluation framework before adoption.
- With **DeepfakeBench** at 1C.2 as the sociotechnical
 complement to DeepfakeBench's purely technical evaluation
 harness; TRIED's fairness and accountability pillars
 complement DeepfakeBench's per-detector metrics.
- With **XAI-Deepfakes** and **TruFor** at 1C.3
 as the sociotechnical evaluation layer that wraps the technical
 explainability output.
- With **ABCDE Framework** and **DISARM** at
 2C.3 – TRIED, ABCDE, and DISARM together form the
 framework-not-tool layer of the toolkit, with TRIED covering
 detector evaluation, ABCDE covering public-facing operation
 characterisation, and DISARM covering institutional reporting.

This card carries no detector signal class: TRIED produces
evaluation artefacts about detectors, not detection signals. Per
Anchor 2, an evaluation artefact supports procurement, deployment,
and publication decisions but does not by itself constitute a
publishable claim about any specific piece of suspect content.

## Override notes

!!! note "Override notes"
    - **Evaluation framework not tool (g2-evaluation-framework-
    not-tool-declaration):** the YAML signal_class is non-detector
    and the framing throughout this card is "methodology applied
    to other tools, not deployable software." Frontline users
    should not expect to install or run TRIED; institutional
    partners should apply it as a structured evaluation layer
    around the detectors they are considering or already use.

## Sources

- WITNESS. *TRIED Benchmark — Truly Innovative and Effective AI Detection*. WITNESS, July 2025. [witness.org/resources/?cat=deepfakes](https://witness.org/resources/?cat=deepfakes).
