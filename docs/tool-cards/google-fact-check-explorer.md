---
tool_id: TOOL-078
slug: google-fact-check-explorer
name: Google Fact Check Explorer
maintainer: Google
type: non-detector
outline_cells:
 - {id: "1B.5", role: primary, density_role: primary}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free-service
languages_ui: [en]
languages_content: [multilingual-incl-bahasa]
access: web
cost: free
documented_country_use: [ID, PH]
tags: [fact-check, claim-database, claimreview, multilingual, ifcn]
---

# Google Fact Check Explorer

**Vendor:** [toolbox.google.com/factcheck](https://toolbox.google.com/factcheck/explorer) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free aggregated search across fact-checks published by IFCN
    member organisations worldwide, surfaced through ClaimReview
    structured-data markup. Multilingual including Bahasa Indonesia.
    The toolkit's primary 1B.5 entry: the first stop when the
    question is "has this claim already been fact-checked?".

## What it does

Google Fact Check Explorer accepts a search query and returns a
ranked list of fact-checks published by participating organisations
worldwide, drawing on the ClaimReview structured-data schema that
publishers embed in their fact-check articles. Each result names the
claim, the verdict, the publishing organisation, and a link to the
underlying fact-check. Coverage extends across IFCN signatories and
beyond; universal IFCN adoption means the database includes work
from CekFakta, Rappler, Boom Live, AFP Fact Check, and many other
SEA-region newsrooms.

For a fact-checker, this is the first stop on any new claim. If the
claim has already been verified by a peer organisation, the existing
fact-check is the strongest source-history signal available: a
peer-published, dated, cited verdict resolves the case more cleanly
than any detector pass would. The tool does not generate new
analysis; it surfaces existing analysis. That is its design and its
value.

## When to use it

- A new claim has reached your queue and you want to check whether a
 peer organisation has already verified it before doing original
 work.
- A regional case may have parallels in earlier work by AFP Fact
 Check, Rappler, MAFINDO, or Tempo Cek Fakta; the Explorer is the
 fastest path to those parallels.
- A workshop demonstrates the IFCN ecosystem and the ClaimReview
 schema; the Explorer is the canonical demonstration.
- An institutional partner is auditing the claim-coverage map across
 six focus countries; per-country queries against the Explorer
 give a fast snapshot of where existing fact-checks concentrate.

## Limitations

!!! info "Limitations"
    - Only surfaces already-verified claims; novel claims that no
    peer has yet checked will return empty.
    - Constrained by speed of human fact-checkers; fast-moving
    claims (deepfake during a breaking event) often outrun the
    Explorer's indexing window.
    - Coverage depth varies by country: Indonesia, the Philippines,
    and Thailand are well-represented through CekFakta, Rappler,
    and AFP Thailand; Sri Lanka and Lao coverage is structurally
    thinner because fewer local IFCN signatories publish to the
    ClaimReview schema.
    - Indexing depends on publishers using ClaimReview correctly;
    misformatted markup or absent schema data means even a
    published fact-check may not surface.

## Privacy and threat model

The Explorer is a search interface; no source content is uploaded.
The privacy concern is search-query metadata; Google records the
queries run against the Explorer per its standard search policy. For
sensitive case work where the claim text itself reveals the source
or subject, treat queries with the same operational discipline as
any other Google search.

## Country and platform applicability

- **Indonesia:** strong coverage through CekFakta consortium
 publishers and AFP Fact Check Indonesia. Bahasa Indonesia search
 is well-supported.
- **Laos:** structurally thin coverage; no IFCN signatory in
 Laos and no Lao-language ClaimReview-publishing organisation.
 Honest-gap policy applies: Lao queries should be paired with
 diaspora and regional partner outreach (regional case documentation).
- **Malaysia:** moderate coverage through Sebenarnya.my and
 partner organisations.
- **Philippines:** strong coverage through Rappler, VERA Files,
 AFP Fact Check Philippines, and #FactsFirstPH coalition members
 (regional case documentation).
- **Sri Lanka:** thin to moderate coverage through
 FactCheck.lk (Verité Research, IFCN status currently expired),
 Fact Crescendo Sri Lanka, FactSeeker, Hashtag Generation, and
 Watchdog. Sinhala and Tamil ClaimReview publishing exists but is
 uneven (regional case documentation Lanka).
- **Thailand:** moderate to strong coverage through Cofact
 Thailand, AFP Fact Check Thailand, and SONP member outlets
 (regional case documentation).

Platform applicability: language-agnostic search across web-published
fact-checks regardless of source platform.

## How to access

The Explorer is at [toolbox.google.com/factcheck/explorer](https://toolbox.google.com/factcheck/explorer). A Google
account is recommended for higher search volume but not required for
basic use. The ClaimReview schema documentation for publishers is at
the same Google Toolbox.

## Cost (current as of 2026-05)

Free. Google maintains the Explorer as part of the Journalist
Toolbox; no quota that affects ordinary fact-check use.

## Quickstart

1. Open [toolbox.google.com/factcheck/explorer](https://toolbox.google.com/factcheck/explorer) in your browser.
2. Enter the claim text or a key phrase from the suspect content
 (Bahasa Indonesia, Filipino, Thai, Sinhala, Tamil, English, and
 other languages all work).
3. Filter by language, date range, or publisher if the result set
 is broad.
4. For each hit, read the publishing organisation, verdict, and date;
 open the underlying fact-check link to read the full analysis.
5. If the claim has been verified by a peer organisation, that
 pre-existing verdict is your strongest source-history signal —
 record it in the case file and decide whether to amplify the
 peer organisation's work or to add new evidence.
6. If no hit returns, route to [NewsGuard](newsguard.md)
 for outlet-level reliability scoring and to [ClaimBuster](claimbuster.md) at 2B.2 for AI-assisted claim
 extraction on the original content.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural Anchor 1.
Sits as primary at 1B.5 news-reliability scoring as the
multilingual claim-already-fact-checked entry; pairs naturally with
[NewsGuard](newsguard.md) (outlet reliability) and the
2B.2 claim-extraction tools.

Standard combinations:

- With **NewsGuard** at 1B.5 – Explorer surfaces existing
 fact-checks of specific claims; NewsGuard scores the publishing
 outlet's overall reliability. The two together cover claim-level
 and source-level reputation.
- With **ClaimBuster** at 2B.2 when the claim has not been
 fact-checked yet and AI-assisted extraction is the productive
 next step.
- With **Dissect** at 2B.2 specifically for Sinhala-claim
 work in Sri Lanka where the Explorer's Sinhala coverage is
 uneven.
- With **AI Disinfo Hub** at 1B.5 when an institutional
 partner needs the EU DisinfoLab knowledge layer for context that
 the Explorer's individual fact-checks do not provide.

This card produces a non-detector signal: a fact-check hit is a
source-history signal that does not depend on probability scoring.
Per Anchor 2 a peer-organisation fact-check combined with a
detector verdict is two signal classes; per the toolkit's editorial
commitment, when a peer fact-check exists it usually carries
sufficient evidentiary weight for the case without further detector
work.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md),
[T2 video triage](../decision-trees/t2-video-triage.md), and
[T3 audio triage](../decision-trees/t3-audio-triage.md) route through
the Explorer at the "already fact-checked" node (T1.4, T2.3 caption-
matching, T3.7 spoken-claim verification) before any detector node.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:**
    the tool's signal class is non-detector (source-history). Every
    fact-check hit is a source-history signal, never a detector
    signal. The card and the workflow section name this
    classification.

## Sources

- Google. *Fact Check Explorer*. Google Toolbox, 2024. [toolbox.google.com/factcheck/explorer](https://toolbox.google.com/factcheck/explorer).
- Google Developers. *ClaimReview structured data documentation*. Google Search Central. [developers.google.com/search/docs/appearance/structured-data/factcheck](https://developers.google.com/search/docs/appearance/structured-data/factcheck).
