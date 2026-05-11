---
tool_id: TOOL-165
slug: disarm-framework
name: DISARM Framework (Disinformation Analysis and Risk Management)
maintainer: DISARM Foundation (lineage AMITT → SP!CE → DISARM)
type: framework
outline_cells:
 - {id: "2C.3", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: framework
status: reference
last_verified: 2026-05-10
license: CC-BY-SA-4.0
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [framework, ttp-catalogue, institutional-annex, fimi, stix2, decision-2, european-origin]
---

# DISARM Framework

**Publisher:** [github.com/DISARMFoundation/DISARMframeworks](https://github.com/DISARMFoundation/DISARMframeworks) | **Type:** Framework | **Cost:** Free

!!! abstract "TL;DR"
    The institutional annex framework: DISARM is what institutional
    partners, coalition-grade research teams, and government /
    inter-governmental bodies use for technical attribution and
    behavioural-pattern cataloguing. DISARM is the institutional annex
    while [ABCDE](abcde-framework.md) is the surface analytical vocabulary; for the
    typical SEA newsroom, DISARM is a reference structure to consult
    when institutional partners publish DISARM-formatted analysis.

## What it does

DISARM (Disinformation Analysis and Risk Management) is a structured
TTP (Tactics, Techniques, Procedures) catalogue for influence
operations, modelled on cybersecurity's MITRE ATT&CK approach. The
framework's lineage runs through AMITT → SP!CE → DISARM with the
DISARM Foundation as current steward; DISARM 2.0 was published with
updates through May 2026. The catalogue lists tactics at the
strategic level, techniques at the operational level, and
procedures at the tactical level, allowing analysts to characterise
an operation through structured TTP attribution. STIX2 compatibility
makes DISARM-formatted output suitable for institutional intelligence-
sharing systems.

The institutional value of DISARM sits in inter-organisational
machine-readable structure: when EEAS, ENISA, NATO, or a regional
CSIRT publishes a DISARM-formatted analysis, partners across
organisations and jurisdictions can ingest the TTP attribution
into shared workflow tools. The framework is endorsed by NATO and
EU Hybrid CoE, ENISA, and EEAS, and is cited in EEAS FIMI Threat
Reports 1-4 (2023-2025).

## Why this is a framework reference, not a tool card

DISARM is methodology, not deployable software for the toolkit's
typical SEA frontline audience. The framework documentation lives
on GitHub (CC-BY-SA 4.0); DISARM Navigator and STIX2 generator
tooling exists but sits at the institutional CSIRT / government-
partner deployment layer (covered separately in DISARM
Navigator + STIX2 as escalation-option). For the typical SEA
newsroom and civil-society organisation, DISARM is consulted as a
reference structure when institutional partners publish DISARM-
formatted analysis on a relevant operation, not deployed as the
analyst's primary characterisation framework.

The TRIED-pattern voice register is canonical for this card:
methodology applied to other tools' outputs, with the deployment
recommendation routing through institutional partners rather than
through frontline newsroom adoption.

## When to use it

- Institutional partners (academic research labs, regional
 coalitions, government CSIRTs) are producing structured
 technical reporting on an influence operation and need a
 shared TTP vocabulary that interoperates with European and
 NATO-aligned reference outputs.
- A coalition-grade investigation requires machine-readable
 output (STIX2) for intelligence-sharing infrastructure that
 expects DISARM-formatted analysis.
- A published institutional report leads with ABCDE
 characterisation in the executive summary and supplements with
 DISARM TTPs in the technical annex, per the toolkit's
 recommended pattern per Decision 2.
- A SEA fact-check or civil-society partner is reading
 institutional research that uses DISARM TTP IDs and needs the
 framework as a reference for unpacking the cited attribution.

## Limitations

!!! info "Limitations"
    - Too granular for first-line triage. DISARM
    operates at sub-component depth that is operationally
    excessive for fact-check reporting on deadline; the toolkit's
    recommendation per Decision 2 is to lead public-facing
    analysis with ABCDE and reach for DISARM only when
    institutional reporting requires technique-level depth.
    - Better for retrospective analysis. The
    framework's TTP catalogue depth supports thorough
    after-the-fact characterisation; for live-operation
    monitoring and rapid public communication, the
    characterisation overhead is operationally heavy.
    - Retains FIMI vocabulary; less natural fit for SEA domestic
    operators. DISARM was
    built around European and NATO-aligned cases where the
    central frame is foreign-information-manipulation-and-
    interference. SEA's domestic-buzzer, cybertroop, paid-
    influence, and scam-fraud-hybrid operations sit awkwardly
    in vocabulary built around foreign state interference; the
    toolkit's editorial position is to use ABCDE for surface analysis and reserve
    DISARM for institutional annexes where the European-
    reference-base interoperability matters more than vocabulary
    fit to local actors.
    - Documentation is English-language; SEA-language adaptations
    would require translation and regional-context revision
    rather than direct application.

## Country and platform applicability

- **Indonesia:** language-agnostic methodology; relevant for
 CekFakta partner research output and Mafindo institutional
 reporting where the audience is regional or international
 research bodies. For domestic-Indonesian public-facing
 reporting, ABCDE remains the surface vocabulary.
- **Laos:** language-agnostic; minimal direct relevance
 given the absence of Lao institutional partners producing
 DISARM-formatted output. Where Lao-relevant analysis is
 produced by outside institutional partners using DISARM, the
 framework is consulted as reference structure.
- **Malaysia:** language-agnostic; relevant for any
 Malaysian institutional research that interfaces with
 international coalition reporting. Domestic public-facing
 Malaysian reporting defaults to ABCDE per Decision 2.
- **Philippines:** language-agnostic; relevant for
 #FactsFirstPH research-layer output that interfaces with
 international coalitions. Domestic public-facing Philippine
 reporting defaults to ABCDE.
- **Sri Lanka:** language-agnostic; minimal direct
 deployment in Sri Lankan civil-society research per the
 toolkit's inventory; consulted as reference structure where
 outside institutional partners produce DISARM-formatted Sri
 Lankan analysis.
- **Thailand:** language-agnostic; relevant for Thai PBS
 and AFP Bangkok institutional research that interfaces with
 international coalitions.

Platform applicability: not platform-specific. DISARM applies to
operations regardless of platform; coverage of platform-specific
techniques is part of the catalogue's structure.

## How to access

Free download of DISARM 2.0 from the DISARM Foundation GitHub
repository (CC-BY-SA 4.0). The framework documentation includes
the TTP matrix, Navigator-style annotation tooling, and STIX2
generator (covered separately in DISARM Navigator +
STIX2). The repository was updated through May 2026 with
approximately 49 forks recorded. Navigator and Word-plugin
companion tooling (DISARM Foundation Navigator + STIX2 (with Explorer + Word plug-in)) is also open and free.

## Cost (current as of 2026-05)

Free. CC-BY-SA 4.0 licence. The structural cost is analyst time —
DISARM TTP attribution is interpretive work and the catalogue
depth requires either prior training or thorough self-study before
analyst output reaches institutional standard.

## Quickstart

(Not applicable in the per-card-tool sense. The framework is
applied to other tools' outputs and to direct observation of
operations rather than executed.)

1. Identify the operation under analysis with the upstream evidence
 already assembled: content-pillar verification, network
 analysis, monitoring outputs, tipline records.
2. Open the DISARM 2.0 matrix (DISARM Foundation GitHub) and
 navigate the catalogue structure (tactics → techniques →
 procedures).
3. For each component characterised under ABCDE in the
 public-facing summary, identify the corresponding DISARM TTPs
 that catalogue the technical detail of the component.
4. Apply the TTP attribution with interpretive judgement; where
 evidence supports multiple TTPs at different depths, attribute
 at the deepest defensible technique level rather than at the
 most general tactic.
5. Surface the DISARM-formatted attribution in the technical annex
 of the published report; the executive summary remains in
 ABCDE per Decision 2.
6. For machine-readable output suitable for intelligence-sharing
 infrastructure, route through DISARM Navigator + STIX2
 for STIX2-formatted serialisation.
7. Cite the DISARM Foundation framework in the published analysis;
 reference the framework version (DISARM 2.0) and any specific
 TTP IDs cited.

## In the toolkit's workflow

Behaviour-pillar framework reference per Architectural Anchor 1.
Sits in 2C.3 Cross-lingual narrative tracking and DISARM as the
institutional annex framework alongside ABCDE (primary
surface vocabulary), Online Operations Kill Chain
(operational sequencing complement), and DISARM Navigator
+ STIX2 (technical tooling escalation-option).

Standard combinations:

- With **ABCDE Framework** at 2C.3 – the toolkit's
 canonical pairing per Decision 2. ABCDE leads the public-facing
 summary with five-component characterisation; DISARM follows in
 the technical annex with TTP-level detail. Institutional reports
 use both in this layered structure.
- With **DISARM Navigator + STIX2** at 2C.3 – Navigator
 is the institutional tooling layer for DISARM annotation and
 STIX2 serialisation; deployed by institutional partners with
 CSIRT or threat-intel infrastructure.
- With **Online Operations Kill Chain** at 2C.3 – DISARM
 catalogues techniques; the Kill Chain describes the phase
 sequence. Used together for analysis that needs both technique-
 level cataloguing and phase-mapped operational sequencing
 (notably for disruption planning).
- With **TRIED Benchmark** at 1C.3 – TRIED for detector
 evaluation; DISARM for institutional operation characterisation.
 Together with ABCDE and the Kill Chain, the four frameworks
 cover the toolkit's framework-not-tool layer.
- With detection-layer tools producing TTP-relevant output:
 CooRTweet (coordinated link sharing → Behaviour
 TTPs), CIB Mango Tree (CIB pattern → Behaviour TTPs),
 Graphika (named-actor analysis → Actor + Behaviour
 TTPs), Information Tracer (cross-platform spread →
 Distribution TTPs).

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes through DISARM codification at T5.15 (method note) and
T5.16 (defensible conclusion) when institutional reporting is the
publication target.

This card carries no detector signal class: DISARM produces a
structured TTP attribution of evidence collected by other tools,
not detection signals.

## Override notes

!!! note "Override notes"
    - **Framework-not-tool declaration
    (g2-framework-not-tool-declaration via institutional-annex-
    framing):** DISARM is methodology applied to other tools'
    outputs, not deployable software for the toolkit's typical
    frontline audience. The card frames this in the "Why this
    is a framework reference, not a tool card" sub-section and
    the In the toolkit's workflow section.

    - **FIMI vocabulary verbatim caveat
    (c2-verbatim-FIMI-vocabulary-caveat):** the inventory's
    verbatim caveat (DISARM "retains FIMI vocabulary; less
    natural fit for SEA domestic operators") is preserved in
    Limitations without softening. The toolkit's editorial
    position is to use ABCDE for the surface and reserve DISARM for institutional
    annexes where European-reference-base interoperability
    matters.

    - **Institutional annex only per Decision 2
    (institutional-annex-only-per-Decision-2):** The toolkit's editorial position designates DISARM as institutional
    annex and ABCDE as the surface analytical
    vocabulary. The TL;DR, the framework-reference sub-section,
    and the workflow section all carry this framing
    consistently.

## Sources

- DISARM Foundation. *DISARM Framework 2.0 — Disinformation Analysis and Risk Management*. DISARM Foundation, 2026 (CC-BY-SA 4.0). [github.com/DISARMFoundation/DISARMframeworks](https://github.com/DISARMFoundation/DISARMframeworks).
- DISARM Foundation. *DISARM platform GitHub organisation*. [github.com/disarm-platform](https://github.com/disarm-platform).
