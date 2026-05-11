---
tool_id: TOOL-085
slug: information-tracer
name: Information Tracer (Rolli)
maintainer: Rolli / Information Tracer
type: non-detector
outline_cells:
 - {id: "2C.1", role: primary, density_role: primary}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: freemium
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: paid-mid
documented_country_use: []
tags: [claim-monitoring, cross-platform, narrative-tracking, behaviour, rolli, breaking-news]
---

# Information Tracer (Rolli)

**Vendor:** [informationtracer.com](https://informationtracer.com) | **Type:** Non-detector | **Cost:** Paid

!!! abstract "TL;DR"
    Cross-platform claim and narrative tracer used by newsrooms during
    breaking news to follow where a circulating claim came from and
    how it spread across Facebook, X, TikTok, Telegram, and other
    public surfaces. The primary 2C.1 entry for institutional-tier
    cross-platform monitoring; pairs with Media Cloud as the
    free academic alternative for partners outside the paid budget.

## What it does

Information Tracer ingests a claim or narrative (a short text, a URL,
a hashtag) and returns a cross-platform timeline of where the same
content (or near-duplicates) has appeared, how the appearances relate
in time, and which accounts amplified the early waves. The tool's
operational value is collapsing what would otherwise be five separate
platform searches plus manual reconciliation into a single dashboard
suitable for a newsroom on deadline. The output is provenance and
spread evidence about the claim, not a verdict on its truth.

The tool fits Pillar 2's institutional tier because the question it
answers ("where did this come from and how is it moving") is
qualitatively different from per-message verification at the tipline
layer (2B). When a verified false claim has already escaped into the
information ecosystem, what an institutional partner needs is the
spread footprint and the early-amplifier set, not another debunk of
the claim itself. Information Tracer produces that footprint as a
non-detector behavioural signal.

## When to use it

- A breaking-news desk needs to know within the first hour whether a
 circulating claim is appearing on multiple platforms simultaneously
 (synthetic amplification signature) or surfacing on one platform and
 trickling outward (organic spread signature).
- An election-cycle monitoring operation in Indonesia or the
 Philippines is tracking a narrative cluster across Facebook,
 TikTok, and Telegram and needs the cross-platform timeline as a
 single-pane view rather than five separate platform tabs.
- A regional fact-check coalition is preparing a published
 cross-platform investigation and needs documentation of the
 earliest appearances and the amplification path for the
 methodology section.
- An institutional research partner is corroborating an open-source
 CIB finding (CIB Mango Tree, CooRTweet) with a
 parallel cross-platform spread trace before publishing.

## Limitations

!!! info "Limitations"
    - Cross-platform correlation can be inaccurate when user behaviour
    differs across networks. The same actor posting
    different framings of a claim on Facebook versus X may register
    as separate origins on the timeline; analyst review of the
    output is part of the method.
    - English-language interface; documented use is in international
    newsroom contexts. SEA-language content works language-agnostically
    (the tool is matching content tokens, not parsing language) but
    no SEA-specific deployment case is recorded in the toolkit's
    inventory.
    - Paid-mid tier sits above the budget of typical individual SEA
    newsrooms outside institutional grant access. The toolkit lists
    Media Cloud as the free academic alternative for
    partners on a research budget, with the trade-off that Media
    Cloud's news-source coverage is structurally thinner for SEA
    languages.
    - Output is provenance and spread evidence about a claim, not a
    verdict on the claim's truth. Per Anchor 2 the spread signal
    combines with a claim-extraction or fact-check signal from
    Pillar 2B before any publishable assertion about the operation.

## Privacy and threat model

Information Tracer is a hosted service; queries an analyst submits
travel to the tool's infrastructure and the spread-trace results are
returned through that channel. For institutional users the standard
data-handling regime (vendor terms review, access logs, retention
policy review) applies to the contracted use.

The threat model that matters here is operational rather than
data-flow. A spread trace that names accounts is research output;
local legal regimes shape what can be published. Indonesia's UU ITE
/ PDP, the Philippines's COMELEC Resolution 11064 election-period
content rules, Thailand's lèse-majesté constraints, Sri Lanka's OSA
framework, and Malaysia's Section 233 plus 3R speech laws each carry
implications for what cited findings can carry into local
publication without secondary legal risk.
The tool itself is not the surveillance vector; the publication
discipline around findings is.

!!! danger "Source-protection override (S2 — state-linked or legally sensitive)"
    Spread traces that touch police, military, ruling-party, or
    state-linked accounts can become enforcement evidence against
    the analyst's publisher in Thailand, Sri Lanka, Indonesia,
    Malaysia, and the Philippines. Mitigation steps:

    1. Consult Digital Safety, legal counsel, or the editor before
    publishing any Information Tracer output that names state-
    linked actors.
    2. Treat the spread trace as research evidence first and
    published artefact second; named-account network images
    are themselves attribution claims under local speech laws.
    3. Use the country-page operational guidance (Article 112,
    OSA, UU ITE, CMA Section 233, Decree 327) to decide which
    findings can be cited publicly versus held for internal
    editorial use.

!!! danger "Source-protection override (S4 — doxxing or vulnerable-community targeting)"
    A spread trace can identify activists, journalists, or
    minority-community members caught up in the network alongside
    inauthentic accounts. Mitigation steps:

    1. Before publishing, audit the named accounts for activists,
    journalists, ethnic or religious minorities, LGBTQ+
    individuals, migrants, witnesses, or alleged criminals.
    2. Redact identifiers in any published network visualisation;
    consider a quiet response or tipline-only response in place
    of a public debunk if retaliation risk is non-trivial.
    3. Assess retaliation risk per the country page's documented
    harassment-and-doxxing patterns before any publication.

## Country and platform applicability

- **Indonesia:** language-agnostic; documented institutional
 use across Indonesian and Philippine newsroom contexts per the
 inventory. Pairs with CooRTweet for IFCN-signatory
 partners running R-based corroboration on the same dataset.
- **Laos:** language-agnostic; the tool can run on Lao-language
 claim tokens, but the Lao information environment is heavily
 Facebook-centric and the IFCN signatory gap (no Lao signatory)
 means Meta Content Library data is also generally unavailable.
 Honest gap: Lao operations will see thinner cross-platform output
 than Indonesia or the Philippines simply because fewer platforms
 carry meaningful Lao content.
- **Malaysia:** language-agnostic; relevant for tracking
 Malaysian content across Facebook, TikTok, and Telegram. The
 Malaysian information environment also requires the network-
 monitoring layer covered by Sinar Project iMAP for
 censorship and blocking events that affect what content reaches
 users in the first place.
- **Philippines:** language-agnostic; documented institutional
 use in the Philippine context . Pairs with
 the #FactsFirstPH coalition's Meedan Check workflow.
- **Sri Lanka:** language-agnostic; applicable to Sinhala
 and Tamil claim tracing in principle. No Sri Lanka-specific
 deployment case is recorded in publicly available documentation; the structural
 thinness of Sri Lankan platform monitoring infrastructure (no
 Meedan-style tipline backend, no IFCN signatory) is a wider
 context than this tool alone.
- **Thailand:** language-agnostic; relevant for Thai claim
 tracing across LINE-, Facebook-, and TikTok-mediated narratives.

Platform applicability: cross-platform; the tool's distinguishing
feature. Facebook and Facebook Groups, X, TikTok, Telegram
, YouTube are the standard surfaces.

## How to access

Web-based via the Information Tracer / Rolli portal. Account creation
plus institutional billing onboarding through the vendor's commercial
process. The tool is not self-service free; access requires an active
subscription. For institutional partners considering procurement, the
vendor's sales process documents tier features and onboarding.

## Cost (current as of 2026-05)

Paid mid-tier per the source review. Concrete pricing varies by deployment scale and is not
fixed; verify directly through the
vendor's commercial process before procurement. The framing for cost
is that Information Tracer sits at the institutional-tier price band
where Media Cloud (free academic) and Sinar Project
iMAP (free open-source SEA-specific) are the civil-society
alternatives for partners without the budget.

## Quickstart

1. Open the Information Tracer / Rolli portal and authenticate with
 your institutional account.
2. Submit the claim text, URL, or hashtag you want to trace.
3. Review the cross-platform timeline; note the earliest appearance
 on each platform and the time gaps between platforms.
4. Inspect the early-amplifier set on each platform: which accounts
 carried the claim during the first wave.
5. Export the timeline and amplifier set for the published
 investigation's methodology section.
6. Cross-check against an open-source CIB finding (CIB Mango Tree,
 CooRTweet (with CooRnet predecessor)) where the operation suggests coordinated amplification
 beyond organic spread.
7. Combine the spread trace with a claim-extraction or fact-check
 signal from Pillar 2B before publishing any binary assertion
 about the operation per Anchor 2.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.1 Automated claim monitoring as the primary cross-platform
tracer alongside Media Cloud (free academic alternative,
news-source-corpus focus), Sinar Project iMAP (free
open-source SEA-specific network-monitoring), and FactFlow
AI (paid Telegram-specific alternative).

Standard combinations:

- With **Media Cloud** at 2C.1 as the news-source-corpus
 complement – Information Tracer covers social-platform spread,
 Media Cloud covers news-source publication patterns; together
 they triangulate operations that move between earned media and
 social amplification.
- With **CooRTweet** at 1C.1 for IFCN-signatory partners
 running coordinated-link-sharing analysis on the same operation;
 CooRTweet's MCL-data-source path complements Information Tracer's
 cross-platform timeline.
- With **CIB Mango Tree** at 1C.1 as the interactive
 CIB-detection complement; Mango Tree surfaces coordination
 patterns inside a single dataset, Information Tracer surfaces
 cross-platform spread of a specific claim.
- With **Gephi** at 2C.2 for publication-grade network
 visualisation of the amplifier set Information Tracer surfaces.
- With **ABCDE Framework** at 2C.3 for codifying the
 spread-and-amplification signature in public-facing analysis;
 Information Tracer's output maps directly to the Distribution
 axis of ABCDE.

Decision-tree references: [T2 video triage](../decision-trees/t2-video-triage.md)
names Information Tracer at T2.13 (cross-platform identical reuse)
for spread-footprint mapping. [T5 escalation](../decision-trees/t5-escalation.md)
routes through Information Tracer at T5.13 (contextual OSINT) when
an operation shows cross-platform characteristics that single-
platform CIB tools cannot resolve.

This card carries no detector signal class: Information Tracer
produces a non-detector behavioural-pattern signal. Per Anchor 2 that
signal combines with claim-extraction (2B.2), CIB analysis (1C.1),
or source-history (1B.1) to support a publishable institutional
finding.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** Information
    Tracer produces a non-detector behavioural-pattern signal
    (cross-platform spread provenance), not a verdict on content
    authenticity. The card states the signal class explicitly in
    the workflow section.

    - **Cross-platform correlation mitigation
    (d4-mitigation-pass-cross-platform-correlation):** the
    Limitations admonition records the cross-platform correlation
    caveat from inventory verbatim; analyst review of the timeline
    output is part of the method, particularly where the same
    actor uses different framings on different platforms.

## Sources

- Information Tracer / Rolli. *Information Tracer — cross-platform claim and narrative tracking*. Information Tracer, 2026. [informationtracer.com](https://informationtracer.com).
