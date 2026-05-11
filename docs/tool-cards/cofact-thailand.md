---
tool_id: TOOL-115
slug: cofact-thailand
name: Cofact Thailand
maintainer: Cofact Thailand (forked from Cofacts Taiwan)
type: non-detector
outline_cells:
 - {id: "2B.1", role: primary, density_role: alternative}
pillar_service: [source-history, behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [tha, en, ja, ko, zh]
languages_content: [tha, en, ja, ko, zh]
access: line-bot | web
cost: free
documented_country_use: [TH]
tags: [tipline, line, thailand, crowdsourced, cofact]
---

# Cofact Thailand

**Operator:** [cofact.org](https://cofact.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Open-source LINE-native tipline platform forked from Cofacts
    Taiwan; the country-anchored Pillar 2 entry for Thailand
    because LINE is the dominant messaging environment and
    Cofact is the only LINE-native option in the toolkit's
    shortlist.

## What it does

Cofact Thailand operates a LINE chatbot that accepts forwarded
messages from the public, checks them against a crowdsourced
volunteer-curated database of fact-checked claims, and returns
a verdict where one exists. Where no prior verification exists,
the message is queued for the volunteer editorial layer. The
back-end is open-source code forked from Cofacts Taiwan, which
runs the same architecture at much larger scale (2,000+
volunteer editors, 300,000+ chatbot users, 87,000+ articles
debunked at the Taiwan deployment); the Thai fork operates the
same workflow inside the Thai LINE ecosystem.

The tool's value to a Thai fact-check coalition is platform
fit. LINE is the dominant Thai messaging environment, especially
for older users and for political-content circulation, and a
WhatsApp-anchored tipline (Check or Kalimasada-style) reaches
the wrong audience. Cofact is the operational answer to that
mismatch. It is also the routing layer the Thailand 2026 case
study describes: when Thai PBS and SONP newsrooms produced
verified debunks of the Anutin / Mauerberger image cluster
(regional case documentation), Cofact was the channel that pushed
those debunks back into LINE conversations where the original
content had been forwarded.

## When to use it

- A Thai fact-checker or newsroom needs an intake channel that
 reaches LINE users, where most Thai political-content
 circulation happens.
- A regional partner outside Thailand has a Thai-language case
 and wants to point a Thai source toward a verification path
 without standing up their own LINE infrastructure.
- A Thai election or referendum cycle generates a surge of
 forwarded LINE content and the operation needs the
 crowdsourced database to keep volume tractable; Cofact's
 Election Commission and TikTok integration during electoral
 campaigns is the documented precedent.
- A researcher studying LINE-mediated misinformation flow in
 Thailand needs an entry point into the verification ecosystem
 to study response latency, routing, and the dynamics of
 closed-platform circulation.

## Limitations

!!! info "Limitations"
    - Relies on volunteer fact-checkers; throughput and
    response latency depend on volunteer engagement.
    - Slow response cycle for emerging claims; novel content
    reaches the queue before any verified counter-claim
    exists, so the bot can return "no match" on
    fast-moving cases.
    - Only a fraction of debunked cases see the original
    forwarded content removed at platform level; engagement
    with the original misleading content can keep climbing
    even after a debunk lands.
    - LINE-only at the user-facing layer. Thai content also
    circulates on Facebook, TikTok, X, and WhatsApp; reach is
    bounded to the LINE share of the Thai information
    ecosystem.
    - Operational continuity is exposed to LINE platform
    policies and to LINE official-account fee structures;
    Cofact's economics shift when LINE shifts.

## Privacy and threat model

A user forwards a message to the Cofact LINE bot inside LINE's
end-to-end encryption between the user's device and LINE's
servers. From there the message reaches the Cofact backend,
which is run by Cofact Thailand (a Thai civil-society
initiative, forked from Cofacts Taiwan). LINE itself, as the
messaging-platform vendor, sits in the chain; the message
travels through LINE infrastructure under LINE's terms of
service before reaching the bot.

For ordinary citizen reports of suspect forwarded content, this
is operationally adequate: the user is sending content into a
verification workflow, not a private channel. For source
handling involving a journalist's confidential informant, an activist
sending content that could identify them, or a politically
sensitive whistleblower in the Thai legal environment, the right
path is a Thai newsroom (Thai PBS, SONP partner outlet) with explicit
source-protection arrangements. The bot is
for citizen reports.

A specific threat-model note for Thailand: regional research records that
Thailand's Computer Crime Act, lèse-majesté provisions, and
2025 platform-takedown rules create real legal exposure on
content related to the monarchy, national security, and certain
political topics. Cofact is a civil-society operator, not a
state operator, and stands outside that enforcement layer; but
content forwarded to the bot still moves through LINE and still
exists as digital evidence. Thai operators applying Cofact in
politically sensitive cases should reach editorial decisions
about which queued claims to debunk publicly with that legal
environment in mind.

!!! danger "Source-protection override (S2 — state-linked or legally sensitive)"
    Thai content involving the monarchy (Article 112), national
    security, or Computer Crime Act-adjacent topics carries real
    legal exposure on any party in the forwarding chain.
    Mitigation steps:

    1. Consult Digital Safety, legal counsel, or the editor
    before queuing any lèse-majesté-adjacent or national-
    security claim for public debunk via Cofact.
    2. Where the source is identifiable, route to a Thai newsroom
    partner (Thai PBS, SONP outlet) with explicit source-
    protection arrangements rather than directly into the
    public-debunk queue.
    3. Cofact stands outside state enforcement, but the LINE
    forwarding chain does not; assess platform-level exposure
    before forwarding sensitive material.

!!! danger "Source-protection override (S5 — private or encrypted group collection)"
    Cofact intake from private LINE groups requires consented
    submissions only. Mitigation steps:

    1. Use Cofact only for content the user has personally
    forwarded with intent to verify; do not scrape or
    infiltrate closed LINE groups for intake.
    2. Where the case originated in a private Thai LINE group
    and the source is identifiable, route to a Thai newsroom
    partner for source-protected handling before any public
    response.
    3. Record the forwarding chain in the case file as a
    chain-of-custody artefact for editorial review.

## Country and platform applicability

- **Indonesia:** not applicable as a primary intake
 channel. Indonesian content runs through Kalimasada
 (WhatsApp / MAFINDO) and Meedan Check (CekFakta).
- **Laos:** not applicable. No Lao-language Cofact
 deployment is documented; the Lao tipline gap is structural
 (G-041) and runs across all 2B.1 entries in this toolkit.
- **Malaysia:** not applicable as a primary intake
 channel; Malaysian content routes through Sebenarnya AIFA and regional partner relays.
- **Philippines:** not applicable; Philippine content
 routes through #FactsFirstPH on Check (Meedan Check) and
 Viber/Messenger via SEEK / VERA Bot.
- **Sri Lanka:** not applicable; the Sri Lanka tipline
 layer is a patchwork of forms, email, phone, and WhatsApp
 distribution rather than a Cofact-style LINE bot (:** primary deployment. Documented through
 the 2025 election cycle integration with the Thai Election
 Commission and TikTok, and through routing of Thai PBS / SONP
 debunks back into LINE conversations including the Anutin /
 Mauerberger February 2026 case (regional case documentation).

Platform applicability: LINE only. Thai content also
moves through Facebook, TikTok, and X;
Cofact reaches that material only when a recipient forwards it
into LINE.

## How to access

Citizens in Thailand add the Cofact LINE official account to
their LINE contacts and forward suspect messages to the bot.
The account handle is published on Cofact Thailand's website and
on partner newsroom materials. There is no account creation
beyond LINE itself, no install, and no fee at the user side.

For a newsroom or coalition wanting to operate or contribute to
the verification database, contact Cofact Thailand directly via
their website. The open-source Cofacts codebase from the Taiwan
project is on GitHub for organisations considering similar
deployments in other LINE-dominant contexts; Thai-specific
adaptations sit on the Thai fork.

## Cost (current as of 2026-05)

Free for the public user. The underlying infrastructure
(LINE official account fees, Cofact's hosting, volunteer
coordination) sits with Cofact Thailand and partner
organisations. The volunteer-curated model means the dominant
operational cost is volunteer time on editorial review, not
platform costs at the user-facing layer.

## Quickstart

(Quickstart for a citizen user; operational organisations
considering a Cofact-like deployment elsewhere should clone the
Cofacts codebase from the Taiwan project on GitHub and adapt.)

1. Open LINE on your phone.
2. Add the Cofact Thailand LINE official account to your
 contacts; the handle is on the Cofact Thailand website.
3. Forward the suspect message, image, or link to the bot.
4. The bot returns either an existing crowdsourced fact-check
 (where the claim is already in the database) or queues the
 claim for volunteer review.
5. For a queued claim, response latency depends on volunteer
 capacity and may take hours to days; do not treat the bot
 as a real-time detector.
6. Where the bot returns a verified debunk, share the debunk
 with the people who forwarded the original content rather
 than just leaving the verdict inside the bot conversation.

## In the toolkit's workflow

Source-history and behaviour pillar non-detector platform per
Architectural Anchor 1. Sits in 2B.1 Multilingual tiplines as
the Thailand-anchored alternative alongside the global primary
Meedan Check, the Indonesia-anchored Kalimasada, and the government-operated Sebenarnya
AIFA in Malaysia. The four entries together cover the
WhatsApp / Messenger / LINE messaging-platform spread of the
focus countries.

Standard combinations:

- With **Meedan Check** at 2B.1 – Cofact runs on its
 own Cofacts-Taiwan-forked backend rather than Check, so the
 cross-reference is for coalition interoperability rather
 than shared infrastructure. A Thai newsroom that is part of
 a regional Check coalition will run Cofact for LINE intake
 and exchange verified claims with Check-backed coalition
 partners separately.
- With **Kalimasada** at 2B.1 – different platform
 (LINE vs WhatsApp), different country (Thailand vs
 Indonesia), similar workflow pattern (forward, match, queue,
 reply) at the user-facing layer.
- With **Sebenarnya AIFA** at 2B.1 – civil-society
 Thai counterpart to the Malaysian government-operated
 chatbot; the two cards illustrate the structural difference
 between civil-society-operated and state-operated tipline
 infrastructure.
- With **SynthID Detector** at 1A.4 – when a Thai
 case generates SynthID-watermarked debunkable content (the
 Anutin / Mauerberger pattern), Cofact distributes the
 resulting verified debunk back through LINE.
- With **InVID-WeVerify** at 1B.1 – when image or
 video content forwarded to Cofact needs forensic verification
 before the bot's editorial reply goes back.
- With **CIB Mango Tree** at 1C.1 – for institutional
 follow-up CIB analysis on the broader image-distribution
 network behind Thai cases that surface through Cofact volume.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
routes Thai forwarded LINE content to Cofact as the country tipline
of record for the `-thai` `-line` combination. [T1 image triage](../decision-trees/t1-image-triage.md)
and [T2 video triage](../decision-trees/t2-video-triage.md) feed
back into Cofact when the underlying forensic check resolves and
the verified debunk needs to reach LINE recipients.

This card carries no detector signal class: Cofact produces a
non-detector source-history signal (the verified debunk) and a
behaviour signal (the volume and pattern of forwarded reports
on LINE). Per Anchor 2 these combine cleanly with detector
signals from Pillar 1 when both are present in the same case.

## Override notes

!!! note "Override notes"
    - **LINE-platform-only pointer (line-platform-only-pointer):**
    Cofact reaches LINE users only. Thai content circulating
    on Facebook, TikTok, X, or WhatsApp reaches Cofact only
    via re-forwarding into LINE, and the toolkit's Thailand
    country page should foreground that scope rather than
    imply pan-platform coverage.

    - **LINE third-party mitigation (d4-mitigation-pass-LINE-third-party):**
    messages forwarded to the Cofact bot pass through LINE's
    infrastructure before reaching the volunteer-operated
    backend. The mitigation is editorial: source-handling
    cases route through direct newsroom contact rather than
    through the public bot, and operators in politically
    sensitive Thai cases reach publication decisions with
    Thailand's CCA and lèse-majesté legal environment in
    mind.

## Sources

- Cofact Foundation. *Cofact — collaborative fact-checking database and LINE chatbot*. Cofact, 2024. [cofact.org](https://cofact.org).
- Cofact. *Cofact Taiwan open-source codebase (origin of Thailand fork)*. GitHub. [github.com/cofacts/rumors-api](https://github.com/cofacts/rumors-api).
