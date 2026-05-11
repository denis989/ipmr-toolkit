---
tool_id: TOOL-142
slug: media-cloud
name: Media Cloud
maintainer: UMass Amherst, Northeastern, Harvard Berkman Klein Center
type: non-detector
outline_cells:
 - {id: "2C.1", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [en, agnostic]
access: web
cost: free
documented_country_use: []
tags: [news-monitoring, claim-monitoring, attention-analysis, academic, open-source, civil-society-alternative]
---

# Media Cloud

**Publisher:** [mediacloud.org](https://mediacloud.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Free, open-source academic platform indexing 60,000-plus news
    sources and roughly two billion stories across 20-plus languages,
    with attention and network-analysis tools for tracking how
    narratives move through the news ecosystem. The 2C.1 free
    academic alternative for institutional partners and research
    labs that cannot fund Information Tracer.

## What it does

Media Cloud is a research-grade open platform built and maintained
across UMass Amherst, Northeastern, and Harvard's Berkman Klein
Center. It crawls 60,000-plus news sources, indexes the full text
of approximately two billion stories, and provides tools for
attention analysis (how much coverage a claim or actor received,
when, in which outlets), network analysis (which sources cite or
link to which others), and cross-language clustering. The platform
is the most widely used academic infrastructure for studying
narrative flow through news media at scale; available evidence records
167 academic papers using Media Cloud data.

For a 2C.1 monitoring operation, the value is structural: when
Information Tracer is out of budget, Media Cloud is the
nearest free alternative for tracking cross-source narrative spread.
The trade-off sits at the data layer rather than at the methodology
layer; Media Cloud's news-source corpus is structurally thinner for
SEA languages than for English-language coverage, which the toolkit
flags as the cell-level honest-gap on this entry.

## When to use it

- An academic partner or research lab is producing a study on how a
 claim moved through the news ecosystem and needs a queryable
 corpus of multi-year, multi-source full-text coverage.
- An institutional fact-check coalition wants to compare how a
 cluster of false claims was covered across earned media in
 different countries and languages, as the news-side complement to
 social-platform spread analysis.
- A regional civil-society partner is preparing a published
 investigation on a long-tail narrative and needs methodologically
 rigorous attention-curve evidence rather than per-message tipline
 data.
- An institutional research budget cannot fund Information Tracer
 but the operation has the analyst capacity to build the news-side
 monitoring layer on Media Cloud's open infrastructure.

## Limitations

!!! info "Limitations"
    - Limited SEA-language coverage in the news-source corpus. The platform indexes 20-plus languages but coverage
    of Thai, Bahasa Indonesia, Filipino/Tagalog, Sinhala, and Lao
    is structurally thinner than for English. For SEA-native
    monitoring, Sinar Project iMAP is the SEA-specific
    civil-society alternative; Media Cloud is best for cross-
    language and cross-region work where the SEA-side gap is
    acknowledged rather than concealed.
    - News-source-corpus focus rather than social-platform focus.
    Media Cloud surfaces what news outlets published; for what
    moved on Facebook, X, TikTok, or Telegram, the platform is
    not the right entry point; cross-link to Information Tracer (paid mid-tier cross-platform tracer) or
    to 1C.1 CIB tools (CIB Mango Tree, CooRTweet (with CooRnet predecessor)).
    - Quality of analysis depends on the data pipeline the analyst
    builds around the corpus. Media Cloud is academic-grade
    infrastructure rather than a no-code product; an operation
    without research-side analyst time will not get the same
    output quality from it.
    - Output is news-attention behavioural signal, not a verdict on
    claim truth. Per Anchor 2 the attention curve combines with a
    claim-extraction or fact-check signal from 2B before any
    publishable assertion about the underlying claim.

## Privacy and threat model

Media Cloud queries run against a public-news corpus on academic
infrastructure; the privacy concentration sits with the analyst's
own query record on the platform rather than with content uploads
that originated from a source. For institutional users the standard
academic data-handling regime applies.

The threat model that matters here is editorial rather than
data-flow. Attention-curve findings about how news outlets covered
a claim in a specific country are research output that cited
publication shapes; Indonesia's UU ITE/PDP, Malaysia's CMA Section
233 and 3R speech laws, and Thailand's lèse-majesté constraints
each carry implications for what cited findings can be republished
locally without secondary legal risk.
The data path itself is open and academic; the cited use of the
data is where local legal regimes come in.

!!! danger "Source-protection override (S2 — state-linked or legally sensitive)"
    Media Cloud attention curves on coverage of state actors or
    state-linked claims become published evidence whose
    circulation is subject to local speech laws. Mitigation steps:

    1. Consult Digital Safety, legal counsel, or the editor
    before publishing attention-curve findings on coverage of
    monarchy, military, police, ruling party, or named state
    officials in Thailand, Malaysia, Indonesia, Sri Lanka, or
    Laos.
    2. Treat the attention curve as a research artefact first;
    reproducing it in a local-language fact-check carries the
    legal exposure of the underlying coverage it visualises.
    3. Use the country-page operational guidance to decide which
    findings can be published locally versus held for cross-
    border or institutional partner channels.

## Country and platform applicability

- **Indonesia:** SEA-language coverage is thinner than English
 coverage; Bahasa Indonesia news-source coverage is partial. Useful
 for cross-language work pairing English-language coverage of
 Indonesian events with selected Bahasa sources.
- **Laos:** structurally thin Lao-language news-source
 coverage. Honest gap: Lao operations needing 2C.1 monitoring will
 generally see thinner output from Media Cloud than from
 SEA-specific alternatives like Sinar Project iMAP.
- **Malaysia:** partial SEA-language coverage; Malay and
 English Malaysian sources are partially indexed. Pairs with
 Sinar Project iMAP for the network-monitoring layer
 Media Cloud does not address.
- **Philippines:** partial coverage; English-language
 Philippine sources are better-indexed than Filipino-language
 sources. Useful for #FactsFirstPH research-layer work pairing
 English Philippine media coverage with social-platform spread
 analysis.
- **Sri Lanka:** partial coverage; Sinhala-language
 coverage is structurally thin per the broader Sinhala
 low-resource-language pattern (regional research). Tamil coverage is also thin
 on the Sri Lankan side specifically.
- **Thailand:** partial coverage; English-language Thai
 sources are better-indexed than Thai-language sources.

Platform applicability: news-source corpus, not social-platform
corpus. For news-side attention analysis on Facebook / Facebook Groups / TikTok /
Telegram, this is not the right tool; Information Tracer or the
1C.1 CIB stack is.

## How to access

Free registration at mediacloud.org. The platform has a web
interface for query work and a documented API for programmatic
extraction. Account creation requires institutional or research
context; the academic origin of the platform shapes the access
profile, but registration is open and not gated to a closed
researcher network.

## Cost (current as of 2026-05)

Free. Open-source. The platform is funded through the academic
consortium of UMass Amherst, Northeastern, and Harvard's Berkman
Klein Center plus grant support. There is no paid tier for
ordinary use. The structural cost is analyst time to build a query
pipeline against the corpus.

## Quickstart

1. Register a free account at mediacloud.org.
2. Define the query: claim or narrative keywords, time window,
 country / language filter where supported.
3. Run an attention-analysis query to surface the volume curve of
 coverage across the corpus.
4. Drill into the source-list output: which outlets carried the
 coverage, what proportion was original reporting vs syndication.
5. Run a network-analysis query to surface how the sources cite or
 link to each other on the topic.
6. Export the data via the API for further analysis in Gephi (network visualisation) or for combination with
 social-platform spread output from Information Tracer.
7. Document the methodology in the published investigation; cite
 the Media Cloud platform per its standard citation guidance.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.1 Automated claim monitoring as the free-academic civil-
society alternative alongside Information Tracer (paid mid-
tier cross-platform tracer), Sinar Project iMAP (free
open-source SEA-specific network-monitoring), and FactFlow
AI (paid Telegram-specific alternative).

Standard combinations:

- With **Information Tracer** at 2C.1 – Media Cloud
 surfaces news-side attention curves, Information Tracer surfaces
 social-platform spread; together they triangulate operations that
 move between earned media and social amplification.
- With **Sinar Project iMAP** at 2C.1 for SEA-specific
 network-monitoring complementing Media Cloud's news-side coverage,
 particularly where the Lao or Malaysian information environment
 is the focus and the Media Cloud SEA-language gap is binding.
- With **Gephi** at 2C.2 for publication-grade network
 visualisation of Media Cloud's source-network outputs.
- With **CIB Mango Tree** and **CooRTweet** at
 1C.1 for the social-platform CIB layer that Media Cloud does not
 address.
- With **ABCDE Framework** at 2C.3 for codifying news-side
 attention findings under the Distribution axis.

Decision-tree references: [T2 video triage](../decision-trees/t2-video-triage.md)
names Media Cloud at T2.13 (cross-platform identical reuse) for the
news-side attention layer; [T5 escalation](../decision-trees/t5-escalation.md)
routes through Media Cloud when the case is multi-month or multi-
country in scope and the coordinated-operation branch fires.

This card carries no detector signal class: Media Cloud produces a
non-detector news-attention behavioural-pattern signal. Per Anchor 2
that signal combines with claim-extraction (2B.2), source-history
(1B.1), or social-platform CIB (1C.1) to support a publishable
institutional finding.

## Override notes

!!! note "Override notes"
    - **Limited SEA-language coverage disclaimer
    (b2-partial-pass-disclaimer-limited-SEA):** the Limitations
    admonition records the SEA-language coverage gap concretely.
    The Country and platform applicability section names the
    thinness for each focus country. The recommendation is
    Sinar Project iMAP for SEA-native monitoring where
    the Media Cloud gap is binding.

## Sources

- Media Cloud. *Media Cloud — open-source media analysis platform*. UMass Amherst / Northeastern / Harvard Berkman Klein, 2024. [mediacloud.org](https://mediacloud.org).
- Media Cloud. *Media Cloud Search*. [search.mediacloud.org](https://search.mediacloud.org).
