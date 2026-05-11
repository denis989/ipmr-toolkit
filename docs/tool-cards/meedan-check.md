---
tool_id: TOOL-073
slug: meedan-check
name: Meedan Check
maintainer: Meedan
type: non-detector
outline_cells:
 - {id: "2B.1", role: primary, density_role: primary}
pillar_service: [source-history, behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: AGPL/MIT mixed
languages_ui: [en, id, fil, ar, es, pt, fr, hi, ur, bn, ta, th, zh, plus]
languages_content: [en, id, fil, ms, tha, sin, tam, agnostic]
access: web | api | self-host
cost: freemium
documented_country_use: [ID, PH]
tags: [tipline, claim-clustering, whatsapp, messenger, telegram, viber, line, indonesia, philippines, meedan]
---

# Meedan Check

**Operator:** [meedan.com](https://meedan.com) | **Type:** Non-detector | **Cost:** Freemium

!!! abstract "TL;DR"
    Open-source collaborative tipline workspace from Meedan that
    powers multilingual fact-check intake on WhatsApp, Messenger,
    Telegram, Viber, and LINE for 140,000+ users globally. The
    back-end engine of CekFakta in Indonesia, #FactsFirstPH in the
    Philippines, MAFINDO Kalimasada, and many of the region's
    front-line tiplines.

## What it does

Check is a tipline-platform-of-platforms. A newsroom or coalition
operates a public-facing bot on a messaging app (a WhatsApp number,
a Messenger page, a Telegram channel, a LINE official account) and
Check sits behind it as the workspace where forwarded text, images,
audio, and video land for triage, clustering, claim-matching, and
editorial review. It accepts intake in 34+ languages including
Bahasa Indonesia (via CekFakta), Filipino (via Rappler and the
#FactsFirstPH coalition), Thai, Tamil, and many others; the
multilingual claim-matching engine that runs underneath is Meedan
Alegre (Meedan Alegre), so the same XLM-R-driven similarity layer
serves every Check tipline.

The platform's value to fact-checkers is twofold. As a workspace,
it gives a coalition shared queues, claim clusters, and editorial
status across multiple newsrooms; CekFakta routes through a single
Check instance for 18+ Indonesian outlets. As a back-end, it lets
country-specific tipline brands (Kalimasada in Indonesia, SEEK /
VERA Bot in the Philippines, the Mafindo and Rappler bots) share
infrastructure rather than each rebuilding it. The trade-off is
that Check is heavy: a multi-service Docker stack with around an
hour of first-build time, sustained operational engagement, and
volunteer or staff time on the editorial side. It is not a tool a
solo fact-checker spins up over coffee.

## When to use it

- A national or regional fact-check coalition needs a shared
 workspace for tipline intake across multiple newsrooms with
 consistent claim-clustering and editorial status.
- A country-specific tipline (WhatsApp number, LINE official
 account) needs a back-end for queue management, similarity
 matching, and audit trail rather than a per-message human
 inbox.
- An election cycle generates forwarded-content volume that
 exceeds what a single editorial team can triage manually,
 and the operation needs duplicate detection plus claim
 clustering to keep the queue tractable.
- A research partnership with a fact-check coalition wants
 programmatic access to the claim database for monitoring and
 pattern analysis on what is spreading on closed messaging
 platforms.

## Limitations

!!! info "Limitations"
    - Heavy install: multi-service Docker stack, around an hour
    for a first build, sustained operational engagement
    required.
    - The AI triage layer struggles with heavy regional slang,
    which means a Bahasa or Filipino tipline still needs
    editorial human review on the borderline cases.
    - Requires sustained community engagement: a Check tipline
    is only as good as the editorial workflow behind it. An
    under-resourced operation produces a slow response cycle
    that erodes user trust.
    - Operational continuity depends on the messaging platform's
    Business API or bot terms; WhatsApp rate-limit changes and
    LINE official-account fee changes pass through to Check
    tipline economics.
    - Does not in itself produce a synthetic-content verdict.
    Check is a workflow platform; image, audio, or video
    forensics still routes through 1A / 1B tools.

## Privacy and threat model

The data flow is layered. A user's forwarded message travels
inside the messaging platform's encryption (WhatsApp end-to-end,
LINE channel-level) to a Meedan-Check-operated bot endpoint.
From there it enters the Check workspace controlled by the
operating organisation (MAFINDO, Rappler, CekFakta, or whichever
deployment is in question). The operating organisation's editorial
team can read the message, cluster it with similar messages, and
respond. For a self-hosted Check deployment, all of this happens
on infrastructure the operator controls; for a Meedan-hosted
deployment, Meedan as the platform vendor sits in the chain.

The reader-facing privacy framing is that a user forwarding
content to a Check-backed tipline is sending it into an editorial
workflow, not a private channel. That is the right framing for
ordinary citizen reports of suspect WhatsApp content. It is the
wrong framing for source handling: a whistleblower forwarding
sensitive material, an activist sending a clip that could
identify them, or a survivor reporting harassment should reach
the operating newsroom directly with explicit source-protection
arrangements rather than through the public bot.

For surveillance-environment work (Sri Lanka, Lao content
routed via diaspora), operators should classify the threat
model of their deployment region before launching a public
intake. Self-hosting on jurisdictionally appropriate
infrastructure becomes more important as the threat model
hardens.

!!! danger "Source-protection override (S5 — private or encrypted group collection)"
    A Check-backed tipline must only ingest content forwarded by
    the user with intent to verify; scraping, infiltrating, or
    importing closed-group content into Check's claim database
    breaks the source-protection model the tipline depends on.
    Mitigation steps:

    1. Use Check only with consented submissions from the user
    who received the content; never import data from scraped
    WhatsApp, LINE, Telegram, or Facebook private groups.
    2. For source-identifying material, route the case to the
    operating organisation's direct source-protection channel
    rather than through the public bot.
    3. Apply the operating organisation's documented retention
    policy to forwarded messages; default to minimum retention
    consistent with the verification workflow.

## Country and platform applicability

- **Indonesia:** the back-end of MAFINDO Kalimasada
 (Kalimasada (MAFINDO)) and the CekFakta consortium of 18+ newsrooms
 (regional case documentation). The most-deployed Check
 installation in Southeast Asia.
- **Laos:** no Lao-language tipline running on Check is
 documented . The Lao path is structurally
 absent at 2B.1; partner-mediated review and Google
 Cloud Translation routing remain the workaround per the
 honest-gap policy (G-041 — Lao tipline real-gap).
- **Malaysia:** no documented MAFINDO-style Check
 deployment for Malaysia; the Malaysian information environment
 routes through Sebenarnya AIFA (government-run, with
 independence caveat) plus regional Check tiplines reachable to
 Malaysian users.
- **Philippines:** the back-end of #FactsFirstPH coalition
 workflows including the Rappler tipline pipeline. Documented as the routing layer behind the
 Doc Willie Ong / Brawner deepfake-cluster response.
- **Sri Lanka:** no Sri Lanka-based Check deployment.
 The Sri Lanka tipline layer is a patchwork of forms, email,
 phone, and WhatsApp distribution rather than a Meedan-style
 backend (regional case documentation Lanka; regional research context.
 Newschecker Sri Lanka and Fact Crescendo SL operate intake
 channels, but neither is documented as Check-backed.
- **Thailand:** Thailand's primary tipline Cofact Thailand uses its own Cofacts-Taiwan-forked backend on
 LINE rather than Check. Thai partners can interoperate with
 Check via cross-coalition routing.

Platform applicability: WhatsApp, Messenger, Telegram, Viber,
LINE. Each Check tipline is configured to one or more of these
platforms; cross-platform deployments are common for coalitions
operating in multiple messaging environments.

## How to access

Meedan publishes Check at meedan.com/check with three deployment
paths. Self-hosted via the Docker stack at the
meedan/check-api GitHub repository (open-source, AGPL/MIT
mixed licence, around one hour first-build time). Cloud-hosted
business plan around USD 400 per month for organisations that
want Meedan to operate the infrastructure. Non-profit partner
arrangements for fact-check coalitions, negotiated case by case
(MAFINDO Kalimasada, #FactsFirstPH, CekFakta operate via
partner arrangements rather than the standard business plan).

A new fact-check coalition considering Check should reach
Meedan directly to discuss the partner path before standing up
a self-hosted instance, because partner arrangements typically
include training, onboarding, and shared-claim-database
integration that a fresh self-host does not.

## Cost (current as of 2026-05)

Self-hosted Docker deployment: free under the AGPL/MIT
licence; infrastructure costs (servers, messaging-platform API
fees, staff time) are on the operator. Cloud-hosted business
plan: USD 400 per month at the entry tier 
record; verify current pricing with Meedan directly because
SaaS tiers shift. Non-profit partner arrangements: case by case;
typically grant-funded on the operator's side rather than billed.
The dominant cost in any deployment is editorial staff time
behind the bot, not the platform itself.

## Quickstart

(Quickstart for an operating organisation, not for a citizen
user. Citizens forward messages to whichever tipline number
their country's operator publishes; see Kalimasada,
#FactsFirstPH, Cofact, AIFA cards for the country-specific
front-end paths.)

1. Decide deployment path: self-hosted Docker, Meedan-hosted
 business plan, or partner arrangement.
2. For self-host: clone meedan/check-api from GitHub, follow
 the multi-service Docker setup, and budget around one hour
 for the first build.
3. Connect at least one messaging-platform integration:
 WhatsApp Business API, Messenger, Telegram, Viber, or LINE;
 configure intake routing.
4. Define claim-clustering rules and editorial workflow states
 (received, in review, debunked, awaiting source, published).
5. Train editorial staff on the queue interface and
 claim-similarity affordances; the AI triage handles broad
 matching but borderline regional-slang cases need humans.
6. Publish the front-end tipline number or handle through your
 organisation's communications channels and link it back to
 any consortium-shared claim database.
7. Operate the editorial cycle continuously; tipline trust
 degrades when the response cycle drifts from hours to days.

## In the toolkit's workflow

Source-history and behaviour pillar non-detector platform per
Architectural Anchor 1. Sits in 2B.1 Multilingual tiplines as
the primary entry: Check is the back-end most other tools in
2B.1 wire into. Cross-cell handoff into 2B.2 (claim
extraction) is native: Check's similarity engine is Meedan
Alegre (Meedan Alegre), so a Check tipline already runs Alegre at
the matching layer; pairing the two cards is the same software
in two views.

Standard combinations:

- With **Kalimasada (MAFINDO)** at 2B.1 – Kalimasada is
 MAFINDO's WhatsApp deployment of Check; the two cards
 describe the front-end and back-end of the same Indonesian
 tipline.
- With **Cofact Thailand** at 2B.1 – Cofact runs on
 its own Cofacts backend rather than Check, so the
 cross-reference is for coalition interoperability rather than
 shared infrastructure.
- With **Sebenarnya AIFA** at 2B.1 – AIFA is a
 government-operated alternative; civil-society and newsroom
 Check deployments stand alongside it rather than integrate
 with it, per the editorial position recorded on the AIFA card.
- With **Meedan Alegre** at 2B.2 – same maintainer,
 native integration; Alegre is the claim-matching engine that
 runs underneath every Check tipline.
- With **Yudistira (MAFINDO)** at 2B.2 – Yudistira is
 MAFINDO's Bahasa-specific debunked-claim database that
 Check-routed Indonesian tiplines query.
- With **InVID-WeVerify** at 1B.1 when image or video
 content lands in the Check queue and needs forensic
 verification before the editorial reply.
- With **MAFINDO Satgas Pemilu** at 2A.4 – Satgas
 Pemilu is the workflow design pattern that orchestrates
 Kalimasada-on-Check intake during election cycles.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
names Meedan Check as the cross-country back-end backbone that
Kalimasada, Cofact, and Sebenarnya AIFA components build on; the
user-facing tipline is always the local-language product, never
Check directly.

This card carries no detector signal class: Check produces a
non-detector source-history signal (the verified fact-check
matched against the claim database) and a behaviour signal (the
volume and clustering pattern of forwarded reports across the
deployment's user base). Per Anchor 2 these combine cleanly with
detector signals from Pillar 1 when a case spans both.

## Override notes

!!! note "Override notes"
    - **Source-history pillar declaration:**
    Check produces non-detector source-history signals
    (matched fact-checks) and behaviour signals (clustering
    patterns), not detector signals. Render in workflow as the
    back-end of the tipline ladder.

    - **Multi-country deployment record (b4-score-3-CekFakta-FactsFirstPH-Pakistan-Brazil):**
    documented use spans CekFakta (Indonesia, 18+ newsrooms),
    #FactsFirstPH (Philippines), Pakistan, Brazil, India
    (Ekta), and the MAFINDO Kalimasada deployment. The card
    surfaces Indonesia and Philippines as the SEA anchors;
    the broader global footprint reinforces the partner
    pathway.

## Sources

- Meedan. *Check — collaborative tipline and claim-matching platform*. Meedan, 2024 (open-source, AGPL/MIT). [meedan.com/check](https://meedan.com/check).
- Meedan. *check-api — Check platform backend*. GitHub. [github.com/meedan/check-api](https://github.com/meedan/check-api).
