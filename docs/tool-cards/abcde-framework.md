---
tool_id: TOOL-167
slug: abcde-framework
name: ABC / ABCDE Framework
maintainer: Camille François (2019); Alaphilippe; Pamment (later extensions)
type: framework
outline_cells:
 - {id: "2C.3", role: primary, density_role: primary}
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
tags: [framework, taxonomy, public-facing, surface-vocabulary, fimi-alternative, decision-2]
---

# ABC / ABCDE Framework

**Publisher:** [disinfolab.eu](https://disinfolab.eu) | **Type:** Framework | **Cost:** Free

!!! abstract "TL;DR"
    The toolkit's primary analytical vocabulary for describing
    influence operations, organised across five components (Actor,
    Behaviour, Content, Distribution, Effect). ABCDE is what fact-
    checkers and civil society use in narrative analysis,
    public-facing reporting, and cross-organisational
    communication; it is the surface vocabulary while [DISARM](disarm-framework.md) is the
    institutional annex for deeper technical reporting.

## What it does

ABCDE is not a tool. It is a structured analytical vocabulary for
characterising influence operations, originally proposed by Camille
François in 2019 as the three-component ABC framework (Actor,
Behaviour, Content) and extended by Alaphilippe and Pamment to
add Distribution and Effect as the fourth and fifth components.
The vocabulary's institutional value sits in its readability for
public-facing audiences while remaining specific enough to support
analyst-to-analyst communication: a Distribution claim about a
buzzer network can be made accurately in ABCDE without requiring
the reader to know any FIMI taxonomy.

The five components partition the analytical question:

- **Actor:** who is conducting the operation. Domestic political
 staff, paid buzzer network, foreign state actor, scam-compound
 operation, AI-content farm, individual amplifier.
- **Behaviour:** how they are conducting it. Coordinated link
 sharing, copy-paste amplification, narrative seeding,
 cross-platform laundering, manufactured-controversy seeding.
- **Content:** what is being distributed. Generated images, voice
 clones, manipulated quotes, decontextualised footage, fabricated
 documents, ordinary partisan content amplified inauthentically.
- **Distribution:** where and how it is propagating. Which
 platforms, which language communities, what timing patterns,
 what amplification cadence.
- **Effect:** what observable impact has been achieved. Reach,
 engagement, downstream behaviour change, secondary news pickup,
 policy or election effect where evidenced.

For SEA's domestic-buzzer, cybertroop, and scam-fraud-hybrid
economies, ABCDE applies cleanly where the European FIMI
vocabulary does not; most operations in the six focus countries
are not foreign-state interference but domestic paid influence
plus commercial scam infrastructure. ABCDE is the toolkit's recommended surface vocabulary
for that reason.

## Why this is a framework reference, not a tool card

ABCDE is methodology, not deployable software. The card's structure
mirrors TRIED Benchmark and the other 2C.3 cards: there
is no install path, no UI, no quickstart in the operational sense.
The card is included because the toolkit's narrative sections
(Pillar 2C tier introduction, Regional Case Studies, decision
trees that lead to public-facing publication) refer to ABCDE
components throughout, and a single canonical reference card lets
those references resolve to one consistent definition.

Where TRIED is the institutional reference for evaluating
detectors, ABCDE is the surface analytical vocabulary for
characterising operations. Both serve the toolkit's framework
layer: methodologies applied to other tools' outputs rather than
tools deployed in their own right.

## When to use it

- A fact-check publication is characterising an operation for a
 public audience and needs vocabulary that reads naturally for
 non-specialist readers while remaining analytically specific.
- A regional civil-society coalition is producing a comparative
 report across multiple operations and needs a five-component
 axis for structured comparison.
- A newsroom is communicating a CIB finding to its editorial
 leadership or to a regulatory body and needs vocabulary that
 separates the actor question from the distribution question
 cleanly.
- A coalition is coordinating cross-organisational reporting on
 the same operation cluster and needs shared component
 definitions to avoid talking past each other.

## Limitations

!!! info "Limitations"
    - Less granular than DISARM. DISARM
    catalogues hundreds of TTPs at sub-component depth; ABCDE
    operates at the component-level abstraction. Where
    institutional reporting requires technique-level specificity,
    DISARM is the appropriate annex; ABCDE remains the surface
    vocabulary the institutional report opens with.
    - The framework requires interpretive judgement to apply.
    Two analysts characterising the same operation may produce
    different ABCDE scorings on Effect specifically (where
    observable impact is harder to attribute) or on Behaviour
    (where coordination signatures admit competing readings).
    - ABCDE was developed in a Western policy context (François
    2019; Alaphilippe and Pamment extensions). The toolkit's SEA
    re-angle treats ABCDE as cleanly portable to the
    domestic-buzzer / cybertroop / scam-fraud-hybrid economy
    typical in the six focus countries; institutional partners
    working on European FIMI cases will find DISARM's vocabulary
    more native to their reference base.
    - Component boundaries are not always crisp on real cases. AI
    content generated by paid buzzer staff sits across Actor and
    Content axes; coordinated amplification on Telegram for paid
    campaigns sits across Behaviour and Distribution. Analysts
    apply judgement on which component carries the operation's
    load-bearing characterisation.

## Country and platform applicability

- **Indonesia:** language-agnostic methodology; recommended
 surface vocabulary for CekFakta partner public-facing reporting,
 Mafindo institutional comms, and academic research output on
 buzzer networks.
- **Laos:** language-agnostic; recommended surface
 vocabulary for any Lao-relevant operation analysis where the
 upstream detection capacity is present (the structural Lao gap
 sits at the detection layer, not at the codification layer).
- **Malaysia:** language-agnostic; recommended for Sebenarnya
 / Bernama and independent civil-society research on Malaysian
 cybertrooper operations.
- **Philippines:** language-agnostic; recommended for
 #FactsFirstPH coalition reporting and for Rappler / VERA Files
 public-facing operation characterisation.
- **Sri Lanka:** language-agnostic; recommended for
 Watchdog and Hashtag Generation institutional research and
 public-facing reporting on Sinhala / Tamil operations.
- **Thailand:** language-agnostic; recommended for Thai
 PBS, Cofact Thailand, and AFP Bangkok public-facing operation
 characterisation.

Platform applicability: not platform-specific. ABCDE applies to
operations regardless of which platform's content the analysis
draws from.

## How to access

Free open methodology. The framework is documented in the original
François 2019 paper (Algorithms and Amplifiers: The ABCs of
Disinformation) and in subsequent extensions by Alaphilippe and
Pamment. No application path, no licence purchase, no account
creation. The framework is methodology applied to other tools'
outputs rather than software to install.

## Cost (current as of 2026-05)

Free. Open methodology. The structural cost is analyst time to
apply the five components to a specific operation; for trained
fact-checkers and OSINT practitioners this is light overhead on
top of work the analyst is already doing.

## Quickstart

(Not applicable in the per-card-tool sense. The framework is
applied to other tools' outputs and to direct observation of
operations rather than executed.)

1. Identify the operation under analysis (the suspect cluster of
 coordinated content, the named actor group, the platform-
 specific amplification pattern).
2. For each of the five components (Actor, Behaviour, Content,
 Distribution, Effect), assemble the evidence available about
 the operation from upstream tools: tipline records (2B.1), CIB
 analysis (1C.1), claim-extraction (2B.2), forensic verification
 (1B), monitoring (2C.1), network mapping (2C.2).
3. Characterise each component with the available evidence.
 Where evidence is thin (Effect is commonly the thinnest), name
 the gap rather than overclaim.
4. Surface the characterisation as the structuring frame of the
 published analysis: a public-facing investigation typically
 leads with Actor and Behaviour, follows with Content and
 Distribution, and closes with Effect framed honestly about its
 evidentiary weight.
5. Cross-link to the institutional annex (DISARM) when
 the publication is paired with structured technical reporting
 for inter-organisational sharing or regulatory submission.
6. Cite the framework in the published analysis so the
 methodology is traceable; François 2019 plus the Alaphilippe
 and Pamment extensions are the standard citations.

## In the toolkit's workflow

Behaviour-pillar framework reference per Architectural Anchor 1.
Sits in 2C.3 Cross-lingual narrative tracking and DISARM as the
toolkit's primary surface analytical vocabulary, alongside DISARM (institutional annex), Online Operations Kill Chain
(operational sequencing complement), and DISARM Navigator
+ STIX2 (institutional technical tooling). Per Decision 2, ABCDE
is the surface vocabulary; DISARM is the institutional annex.

Standard combinations:

- With **DISARM Framework** at 2C.3 – ABCDE provides
 the public-facing five-component frame; DISARM provides the
 institutional-tier technique-level catalogue. Standard
 institutional reports lead with ABCDE characterisation in the
 executive summary and reach for DISARM TTPs in the technical
 annex.
- With **Online Operations Kill Chain** at 2C.3 –
 ABCDE describes components, the Kill Chain describes the phases
 the operation moved through. Used together for analysis that
 needs both characterisation and operational sequencing.
- With **TRIED Benchmark** at 1C.3 – TRIED covers
 detector evaluation; ABCDE covers operation characterisation.
 The two reference frameworks together cover the
 framework-not-tool layer of the toolkit at the detection and
 the codification layers respectively.
- With detection-layer tools whose outputs codify under ABCDE
 axes:
 - CIB Mango Tree, CooRTweet, Graphika at 1C.1 → Behaviour and Distribution axes
 - Information Tracer at 2C.1 → Distribution axis
 - Maltego at 2C.2 → Actor axis (infrastructure and
 actor enrichment)
 - Gephi at 2C.2 → visualisation of the Distribution
 axis
 - Meedan Check, Kalimasada, Cofact, Sebenarnya AIFA at 2B.1 → Effect axis
 (reach signals from tipline volume)

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
references ABCDE at T5.15 (method note) and T5.16 (defensible
conclusion) for the executive-summary codification step;
[T7 tipline routing](../decision-trees/t7-tipline-routing.md) references
ABCDE characterisation in the published output where the case
warrants a structured presentation.

This card carries no detector signal class: ABCDE produces an
analytical structuring of evidence collected by other tools, not
detection signals. Per Anchor 2 the structured characterisation
combines the multi-tool evidence for the published claim.

## Override notes

!!! note "Override notes"
    - **Framework-not-tool declaration:** ABCDE is methodology
    applied to other tools' outputs, not deployable software.
    The card frames this in the "Why this is a framework
    reference, not a tool card" sub-section and the In the
    toolkit's workflow section.

    - **Public-facing surface vocabulary per Decision 2
    (public-facing-surface-vocabulary-per-Decision-2):** the
    toolkit's editorial position designates ABCDE as the surface vocabulary for
    public-facing analysis and DISARM as the
    institutional annex. The TL;DR, "Why this is a framework
    reference" sub-section, and "In the toolkit's workflow"
    section all carry this framing.

## Sources

- François, C. *Algorithms and Amplifiers: The ABCs of Disinformation*. EU DisinfoLab, 2019. [ABC Framework overview](https://disinfolab.eu).
- Alaphilippe, A. and Pamment, J. Distribution and Effect extensions to the ABCDE framework. EU DisinfoLab. [EU DisinfoLab resources](https://disinfolab.eu).
