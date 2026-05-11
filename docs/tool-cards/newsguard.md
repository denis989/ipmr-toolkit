---
tool_id: TOOL-086
slug: newsguard
name: NewsGuard
maintainer: NewsGuard Technologies
type: non-detector
outline_cells:
 - {id: "1B.5", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [16-langs-incl-id-fil-thai]
access: web | browser-ext
cost: paid-low
documented_country_use: [ID, PH, TH]
tags: [reliability-scoring, news-domains, ai-content-farms, paid]
---

# NewsGuard

**Vendor:** [newsguardtech.com](https://newsguardtech.com) | **Type:** Non-detector | **Cost:** Paid

!!! abstract "TL;DR"
    A paid news-domain reliability rating service covering 35,000+
    sources across 16 languages including Indonesian, Tagalog, and
    Thai. Identifies AI Content Farms (3,006 such sites identified
    to date) and tracks Misinformation Fingerprints. The toolkit's
    paid alternative at 1B.5 for outlet-level reliability.

## What it does

NewsGuard rates news domains on a 0-100 reliability scale through a
human-AI hybrid assessment process: trained analysts evaluate sites
against published criteria (does the site correct errors, name
authors, disclose ownership, gather and present information
responsibly, and so on); the scores update as outlet practices
change. The browser extension surfaces the score on each domain a
user visits; the API serves the same data to organisational
integrations.

NewsGuard's secondary product line is the AI Content Farm
identification; the company has identified 3,006 AI Content Farm
websites to date and tracks them across 16 languages including
Indonesian, Tagalog, and Thai. This is an operationally useful
signal class for IPMR audiences: an outlet flagged as an AI Content
Farm publishes synthetically generated content at scale, which
reframes the verification task from "is this article AI-generated?"
to "is this outlet a known synthetic-content publisher?": a
non-detector source-history signal.

## When to use it

- A claim has surfaced through an outlet you do not recognise; you
 want a fast outlet-level reliability score before reading the
 article in detail.
- An institutional case is investigating a coordinated
 synthetic-content network; NewsGuard's AI Content Farm
 identification is operationally adjacent to behaviour-pillar work
 at 1C.1.
- A workshop demonstrates the difference between claim-level
 fact-check (Google Fact Check Explorer) and outlet-level
 reliability (NewsGuard); the two together cover the two main
 source-history signal classes at 1B.5.
- A regional case in Indonesia, the Philippines, or Thailand where
 NewsGuard's documented language coverage actually applies; for
 Sri Lanka and Lao the coverage gap is structural.

## Limitations

!!! info "Limitations"
    - Sinhala and Lao are not covered; the 16-language coverage
    excludes both, which makes NewsGuard structurally inapplicable
    for outlet-level reliability work in Sri Lanka (Sinhala
    outlets) and Lao (no Lao-language outlets indexed).
    - Subscription cost: the paid tier is the operational
    constraint for many SEA newsrooms.
    - Reliability scoring is based on outlet practices, not on
    individual claim verdicts; a generally-reliable outlet can
    publish unreliable claims and a generally-unreliable outlet
    can publish accurate claims. Treat NewsGuard's score as one
    input, not as a substitute for claim-level fact-checking.
    - The AI Content Farm identification has its own coverage
    uncertainty; novel content farms in low-resource languages may
    not be identified at the speed they appear.

## Privacy and threat model

NewsGuard is a paid web service; no source content is uploaded —
the tool surfaces ratings on URLs and domains rather than
processing user-supplied content. Privacy concerns reduce to the
URL-query metadata that NewsGuard records as part of normal
service operation; treat URL queries with the same operational
discipline as any other paid third-party query.

## Country and platform applicability

- **Indonesia:** Indonesian language coverage in the 16-language
 set; AI Content Farm identification covers Indonesian-language
 farms.
- **Laos:** NOT covered; Lao is not in the 16-language set.
 Honest-gap policy applies; route to Lao verification through
 diaspora and regional partner outreach.
- **Malaysia:** Malay coverage is not specifically documented
 in NewsGuard's 16-language list (which names Indonesian,
 Tagalog, Thai); verify directly before relying on NewsGuard for
 Malaysian outlets.
- **Philippines:** Tagalog language coverage; AI Content Farm
 identification covers Tagalog-language farms.
- **Sri Lanka:** NOT covered for Sinhala or Tamil; both are
 excluded from the 16-language set. Sri Lankan verification must
 rely on the local fact-check ecosystem (Hashtag, Watchdog,
 FactCheck.lk, FactSeeker, Fact Crescendo SL) plus
 [Google Fact Check Explorer](google-fact-check-explorer.md)
 rather than NewsGuard for outlet-level reliability work
.
- **Thailand:** Thai language coverage; AI Content Farm
 identification covers Thai-language farms.

The toolkit names the Sinhala-and-Lao gap explicitly rather than
implying partial coverage. The cell-level honest-gap is
sinhala-lao-no-newsguard-coverage.

Platform applicability: works across web-published news outlets
regardless of platform; does not cover social-media accounts as
such.

## How to access

The browser extension installs from the Chrome Web Store and other
add-on stores at approximately $5/month . The web
interface is at [newsguardtech.com](https://newsguardtech.com); enterprise licensing is
available. NewsGuard offers free access to libraries and schools.
Microsoft licenses NewsGuard for Bing.

## Cost (current as of 2026-05)

Paid: approximately $5/month for the browser extension; enterprise
licensing scales with seat count and integration scope. Free for
libraries and schools. Verify directly before any institutional
commitment as vendor pricing may have shifted.

## Quickstart

1. Subscribe at [newsguardtech.com](https://newsguardtech.com) and install the browser
 extension.
2. Visit a news outlet URL; the extension surfaces the NewsGuard
 reliability score (0-100) and the criteria breakdown.
3. For AI Content Farm investigation, query the AI Content Farm
 tracker directly through the NewsGuard interface; outlets
 identified as content farms carry the explicit flag.
4. Pair the outlet-level score with claim-level fact-check via
 [Google Fact Check Explorer](google-fact-check-explorer.md).
5. For Sri Lanka or Lao casework, do NOT route through NewsGuard
 for outlet-level reliability; route through local fact-check
 infrastructure or the AI Disinfo Hub
 ([AI Disinfo Hub (EU DisinfoLab)](ai-disinfo-hub.md)) instead.
6. Document the score and date in the case file; reliability scores
 change as outlet practices change, so a dated record matters
 for institutional chain-of-custody.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural Anchor 1.
Sits as alternative at 1B.5 news-reliability scoring; pairs with
[Google Fact Check Explorer](google-fact-check-explorer.md)
(claim-level) for the two-source-history-signal pattern at 1B.5.

Standard combinations:

- With **Google Fact Check Explorer** at 1B.5 – Explorer
 covers claim-level fact-checking; NewsGuard covers outlet-level
 reliability. The two together address the two main source-history
 signal classes at this cell.
- With **AI Disinfo Hub** at 1B.5 as the institutional
 knowledge layer for context.
- With **CIB Mango Tree** at 1C.1 when an outlet flagged
 as an AI Content Farm needs CIB analysis on its distribution
 network.
- With **Sinar Project iMAP** at 2C.1 for Malaysia-specific
 network-level monitoring on outlets NewsGuard flags.

This card produces a non-detector signal: outlet reliability and
AI Content Farm flags are source-history signals that do not depend
on probability scoring. Per Anchor 2 a NewsGuard score combined
with a detector verdict on a specific article is two signal classes
(non-detector + detector).

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md) –
NewsGuard supports the source-history layer at T5.13 (contextual
OSINT) and the outlet-reliability read that feeds T5.16 (defensible
conclusion); 1B.5 routes through NewsGuard for in-coverage languages
and through local infrastructure for Sinhala and Lao.

## Override notes

!!! note "Override notes"
    - **Sinhala-and-Lao coverage gap (b2-partial-pass-no-Sinhala-Lao):**
    the Limitations admonition and the Country and platform
    applicability section name the gap verbatim. The card enters
    with the explicit "validate before regional use for languages
    outside the 16-language set" framing.

    - **Paid tier (d1-score-3-paid):** the paid subscription is the
    operational constraint; D1 scores 3 (low-cost paid) on the
    individual extension tier; enterprise scoring is higher. Free
    access for libraries and schools is documented; SEA newsrooms
    should verify whether they qualify before assuming the
    browser-extension price applies.

## Sources

- NewsGuard. *NewsGuard — news reliability ratings and AI Tracking Center*. NewsGuard Technologies, 2024. [newsguardtech.com](https://newsguardtech.com).
- NewsGuard. *AI Tracking Center — tracking AI-enabled misinformation sites*. NewsGuard, 2024. [newsguardtech.com/ai-tracking-center/](https://newsguardtech.com/ai-tracking-center/). (3,006 AI Content Farm websites identified — cited in card)
