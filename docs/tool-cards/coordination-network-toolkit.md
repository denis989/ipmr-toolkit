---
tool_id: TOOL-137
slug: coordination-network-toolkit
name: Coordination Network Toolkit
maintainer: QUT Digital Observatory (Queensland University of Technology, Australia)
type: non-detector
outline_cells:
 - {id: "1C.1", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [cib, network-analysis, behaviour, r, python, coordination, qut]
---

# Coordination Network Toolkit

**Publisher:** [github.com/QUT-Digital-Observatory/coordination-network-toolkit](https://github.com/QUT-Digital-Observatory/coordination-network-toolkit) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free, open-source R and Python framework from the QUT Digital
    Observatory for detecting coordinated behaviour through user
    similarity networks across social-media datasets. The academic-
    grade alternative in the institutional CIB ladder, with peer-
    reviewed methodology behind the Copy Pasta Test pattern.

## What it does

The Coordination Network Toolkit takes a social-media dataset and
constructs a user-similarity network: nodes are accounts, edges are
weighted by how similar two accounts' posting behaviour is across
chosen dimensions (text re-use, timing, hashtag overlap, link
sharing). The output is a network graph that an analyst can inspect
for clusters indicative of coordinated amplification. The toolkit's
methodology has been published in academic venues including ICWSM
2025, which gives a fact-check operation a citable foundation when
its findings are challenged in a defamation suit or platform appeal.

The toolkit operates at the same architectural layer as CIB Mango Tree but with two practical differences. First, it is an
R-and-Python framework rather than an interactive Python terminal;
it is designed to be embedded in a research-grade analysis pipeline
rather than run conversationally. Second, it produces network
artefacts (graph objects, edge lists, similarity matrices) suitable
for downstream visualisation in Gephi or Maltego,
where Mango Tree produces account-cluster lists more directly. Both
sit on the behaviour pillar per Architectural Anchor 1.

## When to use it

- A research lab or fact-check operation already has an R / Python
 analysis pipeline and wants to plug a peer-reviewed coordination-
 detection layer into it rather than adopt a separate tool.
- An institutional partner intends to publish a CIB finding and
 needs a methodology with a citable academic publication record
 to withstand legal or platform scrutiny.
- A regional newsroom is collaborating with a university research
 partner, and the partner's preferred environment is R for
 statistical work or Python for ML-pipeline integration.
- A multi-platform investigation needs a similarity construct that
 can take signals from text re-use, timing, hashtag co-occurrence,
 and URL co-sharing in a single combined network rather than as
 separate per-test outputs.

## Limitations

!!! info "Limitations"
    - Requires R and / or Python proficiency, plus network-analysis
    expertise to interpret similarity graphs correctly.
    - Documented use is academic: peer-reviewed papers, not
    newsroom casework. The toolkit is well-reviewed inside its
    research community but has no published SEA newsroom
    deployment.
    - Like every coordination-detection method, similarity networks
    can surface legitimate political-party social-media operations
    and authentic communities of interest. Coordination signatures
    are necessary but not sufficient for an inauthenticity
    finding.
    - Heavy on input-dataset quality. Sparse data over short time
    windows produces noisy similarity scores; a meaningful
    analysis usually wants weeks of post-level data per account.

## Privacy and threat model

The toolkit runs on the analyst's machine or institutional
infrastructure; no data is sent to a vendor cloud as part of the
analysis itself. Privacy considerations therefore concentrate on
the input dataset (where it came from, what permissions cover its
analysis) and on the output (named-account network graphs, which
have the same disclosure-care implications as any other CIB
finding).

For collaborations between SEA newsrooms and Western university
partners, the data-residency question matters. If the dataset
itself sits on a partner's institutional servers, the analysis
result inherits that jurisdiction's data-protection regime and any
research-ethics constraints attached to the original data. Confirm
the chain of custody before publishing a finding generated through
a partner's environment.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant in principle for
 Bahasa-Indonesian buzzer-network analysis, especially as a
 pipeline component in collaborations with academic partners. No
 published Indonesian deployment.
- **Laos:** language-agnostic; the local-execution model is
 privacy-defensible. No Lao-specific deployment.
- **Malaysia:** language-agnostic. No published deployment.
- **Philippines:** language-agnostic; relevant in academic
 partnerships with Filipino universities and the #FactsFirstPH
 research layer. No published deployment.
- **Sri Lanka:** language-agnostic; the LIRNEasia and
 Hashtag Generation research environment maps onto the toolkit's
 intended user profile. No documented deployment yet.
- **Thailand:** language-agnostic; relevant for institutional
 partners following up the Anutin / Mauerberger 2026 case at the
 network-pattern layer.

Platform applicability: works on any platform whose data the analyst
can extract. The toolkit's R-and-Python framing makes Meta Content
Library extracts the natural input where IFCN access is available.

## How to access

Free download from the QUT Digital Observatory's GitHub
distribution. Install per the repository README in either an R or
Python environment. No account creation, no beta gate. The toolkit
is open-source; the maintainer organisation is the QUT Digital
Observatory at Queensland University of Technology, Australia.

## Cost (current as of 2026-05)

Free. Open-source. The toolkit's continued development depends on
QUT Digital Observatory's research funding and on community
contributions; it is not exposed to vendor-side pricing changes.
The cost of running an analysis is the analyst's time, the local
compute for the network construction, and any underlying data-
licence costs (Meta Content Library access is gated to IFCN
signatories rather than priced commercially).

## Quickstart

1. Confirm whether your institutional pipeline is R-based or
 Python-based and install the corresponding distribution from
 the QUT Digital Observatory repository.
2. Install dependencies per the README.
3. Prepare the input dataset (post-level records with account ID,
 timestamp, text, hashtags, URLs as required by the chosen
 similarity test).
4. Decide which similarity dimensions to combine: text re-use,
 timing co-occurrence, hashtag overlap, URL co-sharing.
5. Run the toolkit's similarity-network construction step.
6. Export the resulting graph object (edge list, similarity matrix)
 for visualisation in Gephi or downstream community
 detection.
7. Inspect identified clusters for coordination signatures and
 cross-check against Mango Tree's Copy Pasta Test on the
 same dataset for triangulation.
8. Document parameters (time window, similarity threshold,
 dimensions used) in any published finding so that the analysis
 is reproducible.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 1C.1 Institutional CIB detection as an academic-grade alternative
to CIB Mango Tree. The two are intentionally complementary
rather than competing: Mango Tree's interactive Copy Pasta Test is
the faster path to a single coordination signal, the Coordination
Network Toolkit is the framework where multiple signals combine
into one network construct with peer-reviewed methodology behind
it.

Standard combinations:

- With **CIB Mango Tree** as triangulation: run both on
 the same dataset and compare cluster boundaries; agreement
 strengthens the finding, divergence flags methodology
 sensitivity to parameter choices.
- With **CooRTweet** when the analysis is in R and the
 data source is Meta Content Library; CooRTweet handles MCL data
 natively.
- With **Gephi** at 2C.2 for publication-grade network
 graphics from the toolkit's exported edge lists.
- With **Maltego** at 2C.2 when an entity-graph view is
 more useful than a similarity-network view.
- With **ABCDE Framework** at 2C.3 to codify the
 behavioural pattern in published reporting.

This card carries no detector signal class: the toolkit produces a
non-detector behavioural-pattern signal class. Per Anchor 2, that
signal combines with claim-extraction (2B.2) and source-history
(1B.1) to support a strong public claim; coordination signatures
alone are not enough.

## Sources

- QUT Digital Observatory. *Coordination Network Toolkit — coordinated sharing detection*. Queensland University of Technology. [QUT-Digital-Observatory/coordination-network-toolkit](https://github.com/QUT-Digital-Observatory/coordination-network-toolkit).
- Graham, T. et al. *Detecting Coordination on Social Media*. Proceedings of ICWSM 2025. [ICWSM 2025](https://www.icwsm.org/2025/).
