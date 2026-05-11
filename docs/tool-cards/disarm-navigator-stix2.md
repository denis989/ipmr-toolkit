---
tool_id: TOOL-166
slug: disarm-navigator-stix2
name: DISARM Foundation Navigator + STIX2 (with Explorer + Word plug-in)
maintainer: DISARM Foundation
type: framework
outline_cells:
 - {id: "2C.3", role: escalation-option, density_role: escalation-option}
pillar_service: [behaviour]
signal_class: framework
status: reference
last_verified: 2026-05-10
license: CC-BY-SA-4.0
languages_ui: [en]
languages_content: [agnostic]
access: web | cli | desktop
cost: free
documented_country_use: []
tags: [framework-tooling, disarm, stix2, csirt, intelligence-sharing, escalation-option, institutional-only]
---

# DISARM Foundation Navigator + STIX2

**Publisher:** [github.com/disarm-platform](https://github.com/disarm-platform) | **Type:** Framework | **Cost:** Free

!!! abstract "TL;DR"
    The technical tooling layer for the DISARM framework: Navigator
    web app for matrix annotation, STIX2 generator for machine-
    readable serialisation, Explorer for visualisation, and a Word
    plug-in for institutional reporting. STIX2 output integrates
    with intelligence-sharing systems used by institutional CSIRTs
    and government partners. Out of scope for the typical SEA
    newsroom and civil-society organisation; the 2C.3 escalation-
    option for institutional partners deploying DISARM analytically.

## What it does

The DISARM Foundation publishes companion tooling alongside the
DISARM framework documentation (covered in DISARM
Framework). The tooling set includes Navigator (a web application
for annotating an operation analysis against the DISARM TTP
matrix), DISARM-STIX2 (a generator that serialises Navigator
annotations into STIX2 format for ingestion into threat-
intelligence sharing infrastructure), DISARM Explorer (a
visualisation companion for browsing and presenting matrix
annotations), and DISARMWordPlugIn (a plug-in for embedding
DISARM-formatted analysis directly into institutional reports
authored in Microsoft Word).

The institutional value of this tooling sits in machine-readable
interoperability: institutional CSIRTs and government partners
working in the European and NATO-aligned threat-intel ecosystem
expect STIX2 input, and DISARM-STIX2 is the standard path for
producing it from a DISARM analysis. Documented institutional use
includes NATO StratCom COE, CISA, and EU DisinfoLab.

## Why this is a framework reference, not a tool card

The Navigator and the STIX2 generator are software, but the
deployment audience is institutional CSIRTs and government partners
rather than the toolkit's typical SEA frontline newsroom or
civil-society organisation. For the toolkit's primary audience, the
realistic path is not direct deployment but reading institutional
research that uses DISARM-formatted output and citing the partner-
produced analysis as an external source.

The card sits in the framework-not-tool layer because the
operational role is "technical tooling layer for an institutional
framework", and the access path for the toolkit's audience is
through institutional partners who deploy DISARM analytically.
Where TRIED is the institutional reference for detector evaluation
and ABCDE is the surface vocabulary for public-facing analysis,
DISARM Navigator + STIX2 is the institutional technical tooling
for inter-org intelligence sharing.

## When to use it

- An institutional partner with CSIRT or government threat-intel
 infrastructure is producing a DISARM analysis and needs the
 Navigator for matrix annotation plus the STIX2 generator for
 machine-readable serialisation into shared infrastructure.
- A coalition partner is integrating DISARM-formatted analysis
 into a Word-document institutional report and needs the Word
 plug-in for embedded TTP attribution.
- A research lab is presenting DISARM analysis findings and needs
 the Explorer for visualisation companion to the matrix
 annotations.
- The typical SEA newsroom is *not* the audience: the realistic
 path for frontline civil-society and newsroom operations is to
 read DISARM-formatted output produced by institutional partners
 and cite the partner-produced analysis rather than to deploy the
 tooling directly.

## Limitations

!!! info "Limitations"
    - CC-BY-SA share-alike on derivatives.
    Institutional users producing derivative analyses need to
    manage the share-alike obligation in their institutional
    data-handling regime.
    - Institutional CSIRT and threat-intel deployment context.
    The Navigator, STIX2 generator, and Explorer are designed
    for analyst workflows that interoperate with broader
    threat-intel infrastructure (STIX2 ingestion endpoints,
    DISARM-aware coalition partners). For a SEA frontline
    newsroom without that surrounding infrastructure, the
    tooling is operationally over-scoped.
    - Out of scope for the typical SEA newsroom and civil-society
    organisation. The toolkit's 2C.3 cell records this as the
    structural rationale for the escalation-option role —
    institutional partners deploying DISARM analytically have
    the operational context that makes the tooling valuable;
    frontline operations do not.
    - Like the DISARM framework itself, the tooling's reference
    base is European and NATO-aligned. SEA-region adaptation of
    the DISARM-aware ecosystem (FIMI-ISAC participation, EEAS-
    style threat-intel sharing) is institutional partner work
    rather than frontline newsroom work.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant for CekFakta
 partner research labs producing institutional reporting that
 interfaces with European or NATO-aligned threat-intel
 infrastructure. Direct frontline newsroom use is not the
 expected pattern.
- **Laos:** language-agnostic; minimal direct relevance
 given the absence of Lao institutional partners deploying
 DISARM-aware infrastructure.
- **Malaysia:** language-agnostic; relevant for institutional
 research partners; not for typical Malaysian newsroom or
 civil-society deployment.
- **Philippines:** language-agnostic; relevant for the
 #FactsFirstPH research-layer when institutional reporting
 interfaces with coalition threat-intel infrastructure.
- **Sri Lanka:** language-agnostic; minimal direct
 deployment.
- **Thailand:** language-agnostic; relevant for Thai PBS
 / AFP institutional research where threat-intel infrastructure
 alignment is the reporting target.

Platform applicability: not platform-specific; the tooling
serialises DISARM-formatted analysis regardless of the platforms
the original operation occurred on.

## How to access

Free download of Navigator, DISARM-STIX2 generator, Explorer, and
the Word plug-in from the DISARM Foundation GitHub repositories.
CC-BY-SA 4.0 licence; the framework documentation (DISARM Framework (Disinformation Analysis and Risk Management)) is
the parent reference. The repositories are actively maintained
under DISARM 2.0 (May 2026 update). Institutional deployment
requires both the analyst capacity to apply DISARM analytically
(which is the primary cost) and the surrounding threat-intel
infrastructure that makes STIX2 output operationally useful.

## Cost (current as of 2026-05)

Free. CC-BY-SA 4.0 licence on the tooling repositories. The
structural cost is institutional analyst time plus the cost of the
surrounding threat-intel infrastructure (STIX2 ingestion endpoints,
shared analyst tooling, coalition partnerships) that makes the
tooling operationally valuable. For institutions outside that
infrastructure context, the tooling is free but functionally
over-scoped.

## Quickstart

(Not applicable to typical SEA frontline use. The realistic path
for the toolkit's primary audience is not "deploy DISARM Navigator
+ STIX2" but "read DISARM-formatted institutional research output
and cite the partner-produced analysis as an external source.")

1. If your institution has CSIRT or government threat-intel
 infrastructure: install Navigator from the DISARM Foundation
 GitHub repository; configure to your institutional analyst
 workflow.
2. Annotate the operation analysis in Navigator against the DISARM
 2.0 matrix (refer to DISARM Framework for the matrix
 structure and TTP application guidance).
3. Generate STIX2-formatted output via the DISARM-STIX2 tool;
 ingest into institutional threat-intel sharing infrastructure
 per the surrounding ecosystem's protocol.
4. For Word-document institutional reports, deploy the
 DISARMWordPlugIn for embedded TTP attribution; for visualisation
 companion to the matrix annotations, use Explorer.
5. For the typical SEA newsroom or civil-society partner *not*
 running this institutional infrastructure: the operational path
 is to identify institutional research partners producing
 DISARM-formatted output on relevant operations, read the
 partner-produced analysis with appropriate scrutiny, and cite
 the partner-produced research as an external source in your
 own published work; the same redirect pattern applies to
 Graphika and Meta Content Library elsewhere
 in the toolkit.
6. Cite the DISARM Foundation tooling and version in any
 published analysis that uses the Navigator or STIX2 output.

## In the toolkit's workflow

Behaviour-pillar framework reference per Architectural Anchor 1.
Sits in 2C.3 Cross-lingual narrative tracking and DISARM as the
escalation-option technical tooling layer alongside ABCDE
(primary surface vocabulary), DISARM (alternative
institutional annex framework), and Online Operations
Kill Chain (alternative operational sequencing).

Standard combinations (when institutionally deployed):

- With **DISARM Framework** at 2C.3 – Navigator + STIX2
 is the technical tooling layer for the DISARM framework.
 Direct dependency: the framework provides the matrix and
 methodology; the tooling provides the analyst workspace and
 serialisation path.
- With **ABCDE Framework** at 2C.3 – institutional
 reports using DISARM Navigator output for the technical annex
 pair with ABCDE characterisation in the executive summary
 per Decision 2.
- With **Online Operations Kill Chain** at 2C.3 – phase
 analysis from the Kill Chain pairs with TTP attribution from
 DISARM Navigator for operational disruption analyses delivered
 to threat-intel infrastructure.
- With **Graphika** at 1C.1 – Graphika and DISARM
 Navigator + STIX2 are both institutional-tier tools whose
 realistic access path for the toolkit's audience is partner-
 mediated. The framing parallel applies: cite institutional
 research output rather than plan direct deployment.
- With **Meta Content Library** at 2C.2 – MCL data
 flowing through institutional analysis sometimes terminates in
 DISARM-Navigator-formatted output for coalition partners. Same
 cite-as-external-source pattern for the toolkit's frontline
 audience.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
terminal nodes T5.17 (external forensic / expert escalation) and
T5.18 (regional partner routing) for institutional CSIRT-grade
reporting.

This card carries no detector signal class: the tooling produces
serialised DISARM-formatted analysis from evidence collected by
other tools, not detection signals.

## Override notes

!!! note "Override notes"
    - **Escalation-option, institutional tooling companion to
    DISARM (e5-institutional-tooling-companion):** the tooling
    is the technical layer of DISARM and the deployment
    audience is institutional CSIRTs and government partners.
    The Cost, How to access, Country and platform applicability,
    and Quickstart sections together carry the
    institutional-only framing. For the toolkit's typical SEA
    audience, the realistic path is to cite institutional
    research output that uses DISARM Navigator rather than to
    deploy the tooling directly; the same redirect pattern applies,
    applied to Graphika and Meta Content
    Library.

## Sources

- DISARM Foundation. *DISARM Navigator, STIX2, Explorer, and Word plug-in repositories*. DISARM Foundation (CC-BY-SA 4.0). [github.com/disarm-platform](https://github.com/disarm-platform).
