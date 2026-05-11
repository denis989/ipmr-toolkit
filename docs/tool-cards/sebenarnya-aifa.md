---
tool_id: TOOL-099
slug: sebenarnya-aifa
name: Sebenarnya.my (with AIFA chatbot)
maintainer: MCMC (Malaysian Communications and Multimedia Commission)
type: non-detector
outline_cells:
 - {id: "2B.1", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: government
languages_ui: [ms, en, zh, tam]
languages_content: [ms, en, zh, tam]
access: web | chatbot
cost: free
documented_country_use: [MY]
tags: [tipline, malaysia, government-run, multilingual, tamil, malay, mandarin, b1-exception-pass]
---

# Sebenarnya.my (with AIFA chatbot)

**Operator:** [sebenarnya.my](https://sebenarnya.my) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Government-run multilingual fact-check chatbot (MCMC); read
    with independence caveat. AIFA is Southeast Asia's only
    state-operated multilingual fact-check chatbot, covering
    Malay, English, Mandarin, and Tamil with documented reach of
    70 million-plus views; the toolkit lists it as an alternative
    in 2B.1 because the Malaysian information environment cannot
    be described without it, but the toolkit's deployment
    recommendations sit with civil-society and newsroom partners,
    not with the operator.

## What it does

Sebenarnya.my is a fact-check website operated by the Malaysian
Communications and Multimedia Commission (MCMC) since 2017, with
the AIFA chatbot launched under the AI untuk Rakyat initiative
in April 2024. The chatbot accepts public queries about
circulating claims, returns MCMC-validated fact-checks where they
exist, and routes the lay public to the broader Sebenarnya.my
archive. AIFA covers four languages (Malay, English, Mandarin,
and Tamil), making it the only government-run multilingual
fact-check chatbot in Southeast Asia and one of very few
state-operated multilingual fact-check products globally that
covers Tamil at all.

The platform's reach is the operational fact that puts it in the
shortlist. Inventory records 70 million-plus views since the 2024
AIFA launch, which is the largest documented public-facing
fact-check audience in any of the six focus countries. For a
fact-checker working on Malaysian content, AIFA outputs are part
of the documentary record of what the Malaysian state has said
about a given claim: useful evidence in either direction
(matching corroboration or noted divergence) when stitching a
verified position together. The platform does not itself produce
synthetic-content forensics; image, audio, and video work routes
to 1A / 1B tools.

## When to use it

- A fact-checker working on Malaysian content needs to check
 whether MCMC has already issued a state-validated debunk on
 a circulating claim, as documentary evidence about the
 Malaysian government's published position.
- A regional newsroom partner wants to surface what Malaysian
 Tamil, Mandarin, and Malay-language audiences are receiving
 through the official channel, in order to compare against
 independent civil-society debunks.
- An institutional research project on regional information
 environments needs the AIFA outputs as one of several data
 points on what state-operated fact-check infrastructure
 reaches the public in each country.
- A fact-check coalition is producing a comparative piece on
 how state-operated and civil-society-operated fact-check
 channels handled the same claim cluster; the March 2026
 Ramadan-aid King and Anwar deepfake cluster is the documented
 example.

## Limitations

!!! info "Limitations"
    - Government-operated raises independence concerns. MCMC is the same body that holds enforcement
    powers under the CMA and the Online Safety Act 2025
    ; AIFA outputs sit inside that
    institutional context.
    - The chatbot returns MCMC-validated fact-checks; the
    universe of claims AIFA addresses is shaped by MCMC's
    priorities, which may not align with what civil-society
    fact-checkers prioritise on the same content.
    - As a tipline-style intake, the response cycle is editorial
    and not real-time; users expecting a synthetic-content
    verdict in seconds will be disappointed.
    - Operational continuity is exposed to MCMC budget and
    policy decisions; the platform's architecture and reach
    can change with state direction in ways civil-society
    tiplines do not face.
    - Lao, Sinhala, Filipino, and Thai speakers are not served;
    AIFA's multilingual scope is Malaysia-internal (Malay,
    English, Mandarin, Tamil).

## Privacy and threat model

The threat model that matters here is operator identity. AIFA is
operated by MCMC, a Malaysian government body. A user forwarding
or querying content through AIFA is sending content into a
government channel, not a private channel and not a
civil-society editorial workflow. That has real consequences in
the Malaysian legal environment: Section 233
of the Communications and Multimedia Act remained a live
enforcement tool through 2025–2026, the Online Safety Act 2025
came into force on 1 January 2026 with broad "harmful content"
categories, and 3R (race, religion, royalty) enforcement
continued to be applied to online speech. Content the user
sends to AIFA is documentary evidence in that environment; the
user should not assume it is operationally separate from the
broader MCMC enforcement context.

For ordinary citizen queries on already-circulating public
claims this is operationally adequate, and AIFA's 70 million-
plus views suggest most use sits in that band. For source
handling (a journalist's confidential informant, an activist
sending content that could identify them, a politically
sensitive whistleblower in the Malaysian legal environment),
AIFA is not the right channel. Direct contact with an
independent civil-society fact-checker, a non-Malaysian
newsroom partner, or a regional fact-check coalition with
explicit source-protection arrangements is the right path. The
*Malaysiakini* January 2025 device-seizure and CMS-access
incident documented in the Malaysia country page is the operational warning
case for how MCMC and adjacent regulators can interact with
journalistic systems in Malaysia.

The toolkit's editorial position, drawn from the broader scope
of work, is that independent fact-checkers and civil society
read AIFA outputs with the same scrutiny they would apply to
any government source-of-record claim: useful documentary
evidence, not authoritative verdict. Cross-verification through
independent civil-society or newsroom channels precedes
publication.

!!! danger "Source-protection override (S2 — state-linked or legally sensitive)"
    AIFA is operated by MCMC; any submission enters a Malaysian
    government channel that the CMA Section 233 and Online Safety
    Act 2025 enforcement regime can read. Mitigation steps:

    1. Consult Digital Safety, legal counsel, or the editor before
    submitting any politically sensitive content to AIFA,
    especially material concerning royalty, race, religion (3R),
    or named state actors.
    2. Do not route source-identifying material through AIFA at
    all; use the independent civil-society / regional coalition
    paths instead.
    3. If AIFA is needed as documentary evidence of a counter-
    claim or as a citable government readout, query a public
    claim only; never private or unpublished source material.

!!! danger "Source-protection override (S5 — private or encrypted group collection)"
    A user forwarding WhatsApp content into AIFA's intake exposes
    the forwarding chain to the operator. Mitigation steps:

    1. Use AIFA only for consented submissions or for claims
    already in public circulation; never for scraped or
    infiltrated private-group content.
    2. Where the case originates in a private WhatsApp or
    Telegram group, route through independent tipline
    partners (Indonesian Kalimasada, Thai Cofact, or a
    Malaysian civil-society contact) instead of AIFA.
    3. Treat any submission to AIFA as a disclosure event; record
    the chain of custody in the case file.

## Country and platform applicability

- **Indonesia:** not applicable as a primary intake
 channel. Indonesian content runs through Kalimasada
 and Meedan Check.
- **Laos:** not applicable. AIFA does not cover Lao;
 the 2B.1 Lao tipline gap (G-041) is structural across all
 entries in this cell.
- **Malaysia:** primary deployment. Documented through
 the AI untuk Rakyat April 2024 launch; the March 2026
 Ramadan-aid King and Anwar Ibrahim deepfake cluster was
 among the documented cases the chatbot processed alongside
 MCMC's broader debunk workflow.
- **Philippines:** not applicable; Philippine content
 routes through #FactsFirstPH on Check (Meedan Check) and
 Viber/Messenger via SEEK / VERA Bot.
- **Sri Lanka:** not applicable as an intake channel,
 but the Tamil-language scope of AIFA is the documented
 contrast point for the Sri Lanka 2B.2 Tamil tooling
 conversation. AIFA's Tamil UI is government-operated Malaysian
 Tamil; Sri Lankan Tamil fact-checking still leans on
 pan-Tamil tooling (X-CLAIM) with the Sri-Lanka-
 specific adaptation gap documented in LIRNEasia research.
- **Thailand:** not applicable; Thai content routes
 through Cofact Thailand on LINE.

Platform applicability: AIFA is web-based and chatbot-style
rather than tied to a specific messaging-app integration in the
WhatsApp / LINE / Messenger sense; the user reaches it via the
Sebenarnya.my web interface or the AIFA chatbot endpoint
documented on MCMC channels.

A specific Decision 7 note: AIFA enters the shortlist via the
B1 exception-pass framing recorded in the Selection Criteria.
For most tools, English UI is operationally sufficient for the
toolkit's audience of trained fact-checkers, and local UI is a
bonus signal rather than a requirement. AIFA is the explicit
exception: the audience is the Malaysian lay public, not
trained fact-checkers, and Tamil, Malay, Mandarin, and English
UI is operationally critical for that audience. The chatbot
would not reach Malaysia's actual demographic mix without it.
That makes AIFA the rare 2B.1 case where local UI is a
selection criterion in its own right, not just a bonus.

## How to access

Free public access. Citizens reach AIFA via the Sebenarnya.my
website or the AIFA chatbot endpoint on MCMC's communications
channels; the chatbot conversation is in any of Malay, English,
Mandarin, or Tamil at the user's choice. There is no account
creation, no install beyond the web interface, and no fee.

For a research partner or regional newsroom wanting to compare
AIFA outputs against civil-society debunks, the Sebenarnya.my
public archive is the documentary record. MCMC publishes
methodology and operational details on its own channels; an
independent assessment of those materials is part of the
documentary research a comparison piece would draw on.

## Cost (current as of 2026-05)

Free for the user. The platform is funded through MCMC
operational budgets and the AI untuk Rakyat initiative. The
hidden cost from the user's side is the operator-identity
consideration recorded in the Privacy and threat model section,
not a monetary cost.

## Quickstart

(Quickstart for a citizen user; institutional partners
considering a comparative-analysis workflow on AIFA outputs
should adapt step 5 accordingly.)

1. Open the Sebenarnya.my website or the AIFA chatbot
 endpoint published on MCMC channels.
2. Choose the conversation language: Malay, English, Mandarin,
 or Tamil.
3. Submit the suspect claim or query; text-based works most
 reliably; the platform is web/chatbot rather than
 messaging-app-native.
4. Read AIFA's response as documentary evidence about MCMC's
 published position on the claim, not as a final
 independent verdict.
5. For institutional or research use: cross-verify the AIFA
 output against an independent civil-society fact-check
 (Meedan Check coalitions; regional partners) before
 citing it in a publication; treat the AIFA reply as a
 documentary data point in a multi-source verification
 workflow rather than as a stand-alone authoritative source.
6. For source handling, route through a civil-society
 fact-checker, a regional newsroom partner, or a coalition
 with explicit source-protection arrangements rather than
 through AIFA.

## In the toolkit's workflow

Source-history pillar non-detector platform per Architectural
Anchor 1. Sits in 2B.1 Multilingual tiplines as the
Malaysia-anchored alternative alongside the global primary
Meedan Check, the LINE-native Cofact Thailand,
and the Indonesia-anchored Kalimasada. Of the four
2B.1 entries, AIFA is the only government-operated platform.

The toolkit documents AIFA because the Malaysian information
environment cannot be described without it; 70
million-plus views and Tamil-language coverage are operational
realities a Malaysia-relevant fact-check workflow has to
account for. The toolkit's deployment recommendations, however,
sit with civil-society and newsroom partners. What civil
society and independent fact-checkers do with AIFA is observe
its outputs as documentary evidence about the Malaysian
information environment; what the toolkit recommends they
deploy for their own intake is the civil-society alternatives
elsewhere in 2B.1.

Standard combinations:

- With **Meedan Check** at 2B.1 – the civil-society
 alternative; coalitions running Check-backed tiplines are
 what the toolkit recommends operators deploy.
- With **Kalimasada** at 2B.1 – country-anchored
 civil-society contrast; same regional category, opposite
 operator type.
- With **Cofact Thailand** at 2B.1 – civil-society
 contrast in a different focus country; volunteer-curated
 rather than state-run.
- With **MaLLaM (Mesolitica)** at 2B.3 – Malay-specific
 open-source LLM; complementary for Malay-first verification
 phrasing on Malaysian content where civil-society Malay LLM
 output augments the cross-checking layer.
- With **Sinar Project iMAP** at 2C.1 – independent
 network-monitoring layer; documented use includes detection
 of MCMC blocking events on competing outlets, and the iMAP card's framing belongs alongside
 AIFA as the independent-monitoring counterweight.
- With **Bernama MyCheck.My** as a media-side
 Malaysian cross-check pointer (referenced in).

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
addresses Malaysian content with a primary node into AIFA at the
documentary layer (the `-ms` row of the country and platform
availability table) and a parallel routing into independent civil-
society intake for source-handling and editorial work.

This card carries no detector signal class: AIFA produces a
non-detector source-history signal (the MCMC-validated
fact-check). Per Anchor 2 it combines with detector signals
from Pillar 1 when both are present in the same case, but the
operator-identity caveat above applies to how independent
civil society reads the AIFA signal in any combined workflow.

## Override notes

!!! note "Override notes"
    - **Government-operated independence caveat
    (government-operated-independence-caveat):** AIFA is
    operated by MCMC. The card carries this caveat in the
    TL;DR opening line, in the Limitations admonition, in the
    Privacy and threat model section, and in the In the
    toolkit's workflow section. Independent fact-checkers
    and civil society read AIFA outputs with the same
    scrutiny they would apply to any government source-of-
    record claim; the toolkit lists AIFA as documentary
    evidence about the Malaysian information environment
    rather than as a deployment recommendation for
    civil-society or newsroom partners.

    - **B1 exception-pass for public-facing Tamil/Malay/
    Mandarin/English UI (b1-exception-pass-Tamil-Malay-
    Mandarin-public-facing):** AIFA enters the shortlist
    because its audience is the Malaysian lay public, where
    local UI is operationally critical rather than a bonus
    signal. The Tamil-language scope is the rare SEA
    government-run chatbot case to cover Tamil at all and is
    a documented contrast point for the Sri Lanka 2B.2 Tamil
    tooling conversation.

## Sources

- MCMC (Malaysian Communications and Multimedia Commission). *Sebenarnya.my — fact-check portal and AIFA chatbot*. MCMC, 2024. [sebenarnya.my](https://sebenarnya.my).
