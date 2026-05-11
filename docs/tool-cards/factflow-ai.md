---
tool_id: TOOL-148
slug: factflow-ai
name: FactFlow AI (Newtral)
maintainer: Newtral / Animal Político
type: non-detector
outline_cells:
 - {id: "2C.1", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: api
cost: paid-mid
documented_country_use: []
tags: [telegram, claim-monitoring, pattern-extraction, telegram-specific, animal-politico, qwen]
---

# FactFlow AI (Newtral)

**Vendor:** [newtral.es](https://newtral.es/factflow-ai/) | **Type:** Non-detector | **Cost:** Paid

!!! abstract "TL;DR"
    Telegram-focused AI tool from Newtral / Animal Político that
    extracts and maps misinformation patterns across text, audio,
    and video Telegram messages, with documented processing of 10
    million Telegram messages by Animal Político that compressed
    detection time from 45 minutes to one. The Telegram-specialist
    entry in 2C.1 for institutional partners with deep Telegram
    monitoring requirements.

## What it does

FactFlow AI ingests Telegram channel and group data and produces
pattern-extraction output across text, audio, and video, surfacing
recurring claim formulations, amplification clusters, and content
copy across channels. The underlying model layer wraps Qwen-class
multilingual capability for content recognition and extraction, and
the operational headline finding is the Animal Político deployment
that processed 10 million Telegram messages and reduced detection
time on misinformation patterns from approximately 45 minutes to
approximately one minute.

The tool fits 2C.1 because in several focus countries Telegram is a
distinct disinformation surface that does not appear cleanly on the
broader cross-platform tools. Where Information Tracer covers
multiple platforms with breadth, FactFlow AI covers Telegram with
depth. For institutional partners running election-cycle monitoring
or sustained influence-operation investigations on Telegram-heavy
information environments, the depth advantage is the operational
case for the tool.

## When to use it

- An institutional partner is monitoring Telegram channel networks
 during an election cycle and needs the depth of pattern-extraction
 across text, audio, and video that broader cross-platform tools
 do not match for Telegram specifically.
- A regional civil-society lab is building a sustained
 misinformation-pattern dataset on Telegram-mediated narratives
 and needs an automated pipeline rather than manual channel-by-
 channel review.
- A research partner is replicating the Animal Político 10M-message
 workflow on a regional dataset and needs an open-source extension
 built specifically for Telegram-volume processing.
- A frontline newsroom is not the target audience; Telegram is a niche surface in
 most of the toolkit's focus countries, and for breadth-first
 monitoring Information Tracer or Media Cloud
 is the right entry.

## Limitations

!!! info "Limitations"
    - Telegram-specific. The tool's design focus is
    Telegram channel and group data; for Facebook, X, TikTok, or
    LINE-mediated narratives this is not the right entry point.
    Cross-link to Information Tracer for cross-platform
    breadth, to Media Cloud for news-side coverage, and
    to Sinar Project iMAP for SEA-specific network
    monitoring.
    - English-language interface; the model layer is multilingual
    (Qwen-based) so SEA-language Telegram content can be processed,
    but no SEA-specific deployment case is recorded in the
    toolkit's inventory; the documented Animal Político
    deployment is Spanish-language Mexican content.
    - Telegram's role as a primary disinformation surface is
    uneven across the six focus countries. Indonesia, Philippines,
    Thailand: secondary surface. Malaysia, Sri Lanka, Laos: lower
    penetration. The cost-benefit for adopting FactFlow AI shifts
    with that distribution; for a frontline newsroom outside
    Telegram-heavy work, the tool is a niche fit.
    - Pattern-extraction output is behavioural signal, not a verdict
    on claim truth. Per Anchor 2 the pattern signal combines with
    a claim-extraction or fact-check signal from 2B before any
    publishable assertion about the operation.

## Privacy and threat model

FactFlow AI ingests Telegram channel and group data; the privacy
concentration depends on how the analyst obtained the data. Public
channel data is open by Telegram's design; private group data
requires either manual joining of the group or access through
Telegram's data export, with all the source-protection
considerations that pattern carries (identification of the analyst
inside the group; risk to any source already inside the group whose
behaviour shifts on observation). For institutional partners the
standard data-handling regime should govern Telegram-data
collection and downstream processing; the tool itself sits at the
processing layer and does not change the upstream collection
threat model.

For surveillance-environment work in Sri Lanka or Laos, an analyst
joining a Telegram group from a personal device or attributable
account can itself be a flagged action. Operational tradecraft
(separate device, dedicated account, documented purpose) belongs
upstream of the FactFlow AI processing step, not at the tool layer.

## Country and platform applicability

- **Indonesia:** Telegram is a secondary surface in the
 Indonesian information environment. Where institutional partners
 are monitoring specific Telegram channel networks, the tool
 applies; for breadth-first Indonesian monitoring it is not the
 primary 2C.1 entry.
- **Laos:** Telegram penetration is lower than Facebook in
 Laos; the tool's relevance in Lao operational contexts is
 correspondingly limited.
- **Malaysia:** Telegram is a secondary surface; for
 Malaysian work the operational pairing is more likely to involve
 Sinar Project iMAP and Sebenarnya AIFA on the
 network and tipline layers.
- **Philippines:** Telegram is a secondary surface; primary
 monitoring runs through Facebook and Messenger. The tool applies
 for institutional partners covering Telegram-specific channel
 networks.
- **Sri Lanka:** Telegram penetration is lower in Sri
 Lanka; the tool's relevance is limited to specific operational
 cases.
- **Thailand:** Telegram is a secondary surface in
 Thailand; LINE is the dominant private-channel surface, which
 this tool does not address. For LINE-specific work Cofact Thailand is the LINE-native intake; for Telegram-specific
 work FactFlow AI applies where the case warrants.

Platform applicability: Telegram only. Other
platforms route through the breadth-first entries elsewhere in
2C.1.

## How to access

Open-source extension; access through the Newtral / Animal Político
open-source repository. Institutional deployment requires the
analyst infrastructure to ingest Telegram data at scale; the
Animal Político 10M-message pipeline is the documented reference
deployment scale. Smaller-scale use is possible on the same code
base; setup is documented through the project's repository.

## Cost (current as of 2026-05)

Open-source extension framing . Source code is freely available; the practical cost for
institutional deployment sits with the analyst infrastructure and
ongoing operational time rather than with the software licence.
The toolkit lists the tool at the paid-mid tier in its broader
2C.1 cost banding because Telegram-monitoring at meaningful scale
is operationally institutional-tier work even when the underlying
software is free; smaller-scale academic use is closer to the
free-academic banding of Media Cloud.

## Quickstart

1. Clone the FactFlow AI open-source repository per the project's
 documentation.
2. Configure the Telegram data-ingest layer: which channels and
 groups, with what authentication and access, with what
 rate-limit handling.
3. Run the pattern-extraction pipeline against the ingested
 dataset; expect compute scaling to grow with the data volume per
 the Animal Político 10M-message reference scale.
4. Inspect the extracted pattern output; cluster by recurring
 formulations, amplification cadences, and content-copy
 relationships across channels.
5. Combine the FactFlow AI output with a claim-extraction or
 fact-check signal from 2B before any publishable assertion
 about the operation.
6. For institutional reporting, codify the pattern signature under
 ABCDE (Distribution axis) or DISARM (TTP
 catalogue) per the operation's institutional reporting target.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.1 Automated claim monitoring as the Telegram-specialist
alternative alongside Information Tracer (paid mid-tier
cross-platform tracer), Media Cloud (free academic
news-source corpus), and Sinar Project iMAP (free
open-source SEA-specific network-monitoring). Of the four 2C.1
entries, FactFlow AI is the platform-specialist for Telegram
specifically.

Standard combinations:

- With **Information Tracer** at 2C.1 for the breadth
 layer that pairs with FactFlow AI's Telegram depth.
- With **CooRTweet** at 1C.1 for IFCN-signatory partners
 running coordinated-link-sharing analysis on Telegram exports
 alongside the FactFlow AI pattern-extraction pass.
- With **CIB Mango Tree** at 1C.1 for the interactive
 CIB-detection layer on Telegram networks.
- With **Gephi** at 2C.2 for publication-grade
 visualisation of FactFlow AI's amplification-cluster output.
- With **ABCDE Framework** and **DISARM** at
 2C.3 for codifying the pattern signature in respectively
 public-facing and institutional reporting.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes through FactFlow AI at T5.13 (contextual OSINT) when the
operation is Telegram-mediated at scale; the same 2C.1 platform-
specialist depth feeds back into [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
when a Telegram-heavy case warrants public response.

This card carries no detector signal class: FactFlow AI produces
a non-detector pattern-extraction behavioural signal on Telegram
data. Per Anchor 2 that signal combines with claim-extraction
(2B.2), CIB analysis (1C.1), or source-history (1B.1) to support
a publishable institutional finding.

## Override notes

!!! note "Override notes"
    - **Telegram platform-specific pointer
    (telegram-platform-specific-pointer):** the tool is a
    Telegram specialist; readers needing breadth-first
    cross-platform monitoring should reach for Information Tracer instead. The Limitations admonition,
    Country and platform applicability section, and In the
    toolkit's workflow section together carry this pointer
    consistently.

## Sources

- Newtral / Animal Político. *FactFlow AI — Telegram monitoring and claim-extraction extension*. Newtral, 2026 (open-source). [github.com/newtral-tech](https://github.com/newtral-tech)
- Animal Político. *Animal Político — investigative journalism outlet (documented FactFlow AI deployment)*. [animalpolitico.com](https://animalpolitico.com).
