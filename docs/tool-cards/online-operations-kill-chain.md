---
tool_id: TOOL-164
slug: online-operations-kill-chain
name: Online Operations Kill Chain
maintainer: Meta (Nimmo and Hutchins) / Carnegie Endowment for International Peace
type: framework
outline_cells:
 - {id: "2C.3", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: framework
status: reference
last_verified: 2026-05-10
license: open
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [framework, operational-sequencing, kill-chain, meta, carnegie, disruption-planning, complementary]
---

# Online Operations Kill Chain

**Publisher:** [carnegieendowment.org](https://carnegieendowment.org/research/2023/03/online-operations-kill-chain) | **Type:** Framework | **Cost:** Free

!!! abstract "TL;DR"
    A ten-phase framework (Acquire Assets, Disguise, Gather, Coordinate,
    Test, Evade, Indiscriminately Engage, Target Specifically,
    Compromise, Enable Longevity) for sequencing how an influence
    operation moves through its lifecycle and identifying the earliest
    disruptable point. Originated by Meta (Nimmo and Hutchins) and
    published with Carnegie Endowment in March 2023; sits at 2C.3 as
    the operational sequencing complement to ABCDE
    (components) and DISARM (techniques catalogue).

## What it does

The Online Operations Kill Chain is a sequenced framework for
analysing influence operations in operational rather than analytical
terms. Where ABCDE characterises an operation's components and
DISARM catalogues its techniques, the Kill Chain describes the
phases the operation moved through: the order in which the
adversary acquired assets, disguised them, gathered intelligence,
coordinated activity, tested approaches, evaded detection, engaged
audiences indiscriminately, then targeted specifically, then
compromised platforms or processes, then enabled the operation's
longevity past initial disruption.

The framework was developed by Meta researchers Ben Nimmo and Eric
Hutchins (lineage from Lockheed Martin's Cyber Kill Chain), and
published in March 2023 with Carnegie Endowment. Its institutional
value sits in disruption planning: by identifying the earliest
phase where defenders have observable signal, the framework supports
decisions about where intervention is most efficient. Active use
is documented at Meta, OpenAI, and the FIMI-ISAC.

## Why this is a framework reference, not a tool card

The Kill Chain is methodology, not deployable software. Like the
other 2C.3 cards in this batch, it sits in the framework layer of
the toolkit; it is methodology applied to outputs from detection and
characterisation tools rather than a tool deployed in its own right.
The card's structure follows the TRIED Benchmark voice register:
no install path, no UI, no operational quickstart; the value is in
the framework structure being available as a shared reference for
institutional partners working on operation disruption.

The Kill Chain complements rather than competes with ABCDE and
DISARM. ABCDE asks "what are the components of this operation"
(Actor, Behaviour, Content, Distribution, Effect). DISARM asks
"what techniques did the operators use" (TTP catalogue). The Kill
Chain asks "in what phase order did the operation unfold, and where
could it have been disrupted earlier." The three frameworks are
designed to layer rather than substitute.

## When to use it

- An institutional partner is producing a disruption-planning
 analysis and needs the earliest-disruptable-point question
 answered with a structured phase framework.
- A platform-side or coalition-side response to an active operation
 needs to map observable signals to operation phases to triage
 intervention priority.
- A retrospective institutional report on a closed operation
 needs to identify which phases were observable in the available
 evidence and which phases the operation completed without
 detection.
- A regional civil-society partner is contributing to a coalition-
 grade analysis where the Kill Chain is the institutional
 framework expected by the report's primary audience (notably
 partners aligned with Meta or FIMI-ISAC reporting standards).

## Limitations

!!! info "Limitations"
    - Requires platform integrity context. Several
    Kill Chain phases (Acquire Assets, Disguise, Compromise) are
    most observable from the platform's own integrity signals;
    external researchers without privileged platform access may
    have only partial visibility into early-phase activity. This
    shapes which phases SEA civil-society analysts can populate
    with evidence versus which phases require institutional or
    platform-side data.
    - Originated at Meta. The framework's design context is
    platform-side disruption work; adaptation to civil-society
    and frontline-newsroom use cases requires the analyst to be
    explicit about which phases are externally observable and
    which are not in the operation under study.
    - Most operationally useful at institutional-level analysis
. The framework's complexity is operationally
 heavy for first-line triage or rapid public reporting; for
 surface use, ABCDE remains the recommended vocabulary per
 Decision 2.
 - Like DISARM, originated in a context where foreign-state or
 foreign-actor operations were the central reference case.
 For SEA's domestic-buzzer / cybertroop / scam-fraud-hybrid
 economy, the Acquire Assets phase looks different (commercial
 buzzer-network procurement rather than covert asset
 acquisition); the framework remains applicable but the
 analyst should expect to adapt the phase-content
 interpretations for the actor type being studied.

## Country and platform applicability

- **Indonesia:** language-agnostic methodology; relevant for
 CekFakta and Mafindo institutional reporting where disruption
 analysis is the report's framing, particularly for election-cycle
 buzzer-network operations.
- **Laos:** language-agnostic; minimal direct relevance
 given the absence of Lao institutional partners producing
 Kill-Chain-formatted output. Where Lao-relevant analysis is
 produced by outside institutional partners using the framework,
 it serves as reference structure.
- **Malaysia:** language-agnostic; relevant for institutional
 research on Malaysian cybertrooper operations where the
 reporting target is platform integrity teams or coalition
 partners.
- **Philippines:** language-agnostic; relevant for the
 #FactsFirstPH research layer's institutional reporting and for
 AFP / Rappler / VERA Files when analysis is paired with Meta or
 platform-side coordination.
- **Sri Lanka:** language-agnostic; minimal direct
 deployment; consulted as reference
 structure where institutional partners outside Sri Lanka apply
 the framework to Sri Lankan cases.
- **Thailand:** language-agnostic; relevant for
 institutional analysis where the reporting target is platform
 integrity or coalition partners aligned with the framework's
 reference base.

Platform applicability: not platform-specific. The Kill Chain
applies to operations regardless of the primary platform, though
phase observability depends on the platform-integrity-data access
the analyst has.

## How to access

Free open methodology. The framework is documented in the original
Nimmo and Hutchins publication with Carnegie Endowment (March 2023)
and in subsequent application reports from Meta, OpenAI, and
FIMI-ISAC. No licence purchase, no application path; the framework
is methodology for application rather than software for installation.

## Cost (current as of 2026-05)

Free. Open framework. The structural cost is analyst time:
applying the ten-phase structure to an operation requires
methodological judgement and access to the evidence layers needed
to populate each phase.

## Quickstart

(Not applicable in the per-card-tool sense. The framework is
applied to other tools' outputs and to direct observation of
operations rather than executed.)

1. Identify the operation under analysis with the upstream
 evidence already assembled: content-pillar verification,
 network analysis, monitoring, tipline records, partner-mediated
 platform integrity data where available.
2. Read the ten-phase Kill Chain structure (Acquire Assets,
 Disguise, Gather, Coordinate, Test, Evade, Indiscriminately
 Engage, Target Specifically, Compromise, Enable Longevity).
3. For each phase, note whether observable evidence exists in the
 operation under study, what evidence sources support the
 observation, and where evidence is absent or incomplete.
4. Identify the earliest phase with observable evidence; this is
 the earliest defensible disruption point in the analyst's
 reporting.
5. Where the operation completed phases unobserved, name the gap
 honestly rather than assume an unobserved phase was absent.
6. Combine the phase-mapped analysis with ABCDE
 characterisation in the executive summary and DISARM
 TTP attribution in the technical annex; the three frameworks
 layer rather than substitute.
7. Cite the Nimmo and Hutchins / Carnegie Endowment publication
 in the published analysis.

## In the toolkit's workflow

Behaviour-pillar framework reference per Architectural Anchor 1.
Sits in 2C.3 Cross-lingual narrative tracking and DISARM as the
operational sequencing framework alongside ABCDE (primary
surface vocabulary), DISARM (institutional annex
techniques catalogue), and DISARM Navigator + STIX2
(technical tooling escalation-option).

Standard combinations:

- With **ABCDE Framework** at 2C.3 – ABCDE characterises
 components, the Kill Chain sequences phases. Used together for
 analysis that needs both component breakdown and operational
 ordering. Public-facing reports lead with ABCDE; the Kill Chain
 appears in the technical or methodology section.
- With **DISARM Framework** at 2C.3 – DISARM catalogues
 techniques used in each phase; the Kill Chain identifies the
 phase ordering of the techniques. Together they support
 thorough institutional reporting on operation lifecycle and
 technique attribution.
- With **DISARM Navigator + STIX2** at 2C.3 for
 institutional partners deploying the technical tooling layer
 for serialisation across phase mapping.
- With **TRIED Benchmark** at 1C.3 – TRIED for detector
 evaluation; the Kill Chain for operation phase analysis. The
 four 2C.3 frameworks plus TRIED form the framework-not-tool
 layer of the toolkit.
- With detection-layer tools producing phase-relevant signals:
 CIB Mango Tree (Coordinate phase), CooRTweet
 (Coordinate, Engage phases), Information Tracer
 (Engage, Target phases via cross-platform spread), Graphika (Acquire Assets, Disguise phases via named-actor
 analysis), Maltego (Acquire Assets, Compromise phases
 via infrastructure analysis), Meedan Check / Kalimasada (Engage phase via tipline volume signals).

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes through Kill Chain phase analysis at T5.16 (defensible
conclusion) and T5.17 (external expert escalation) when
institutional disruption planning is the publication target.

This card carries no detector signal class: the Kill Chain
produces a phase-mapped sequencing of evidence collected by other
tools, not detection signals.

## Override notes

!!! note "Override notes"
    - **Framework-not-tool declaration
    (g2-framework-not-tool-declaration):** the Kill Chain is
    methodology applied to other tools' outputs, not deployable
    software. The card frames this in the "Why this is a
    framework reference, not a tool card" sub-section and the
    In the toolkit's workflow section.

## Sources

- Nimmo, B. and Hutchins, E. *Online Operations Kill Chain*. Carnegie Endowment for International Peace, March 2023. [carnegieendowment.org/research/2023/03/online-operations-kill-chain](https://carnegieendowment.org/research/2023/03/online-operations-kill-chain).
