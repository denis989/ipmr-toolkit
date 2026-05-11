---
tool_id: TOOL-117
slug: mafindo-kalimasada
name: Kalimasada (MAFINDO)
maintainer: MAFINDO (Masyarakat Anti Fitnah Indonesia)
type: non-detector
outline_cells:
 - {id: "2B.1", role: primary, density_role: alternative}
pillar_service: [source-history, behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free
languages_ui: [id]
languages_content: [id]
access: mobile
cost: free
documented_country_use: [ID]
tags: [tipline, whatsapp, indonesia, bahasa, hoax-buster, meedan-check]
---

# Kalimasada (MAFINDO)

**Operator:** [mafindo.or.id](https://mafindo.or.id) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    MAFINDO's Indonesia-facing WhatsApp Hoax Buster bot, built on
    Meedan Check infrastructure, where the public forwards suspect
    content in Bahasa Indonesia and gets routed to MAFINDO's
    verification workflow. The country-anchored Pillar 2 entry for
    Indonesia.

## What it does

Kalimasada is a WhatsApp bot operated by MAFINDO that accepts
forwarded messages, images, and links from members of the public,
matches them against MAFINDO's verification database, and returns a
fact-check response in Bahasa Indonesia. Where no prior verification
exists, the message is queued into MAFINDO's editorial workflow. The
bot is the citizen-facing channel of the broader CekFakta consortium
of 18+ Indonesian newsrooms and runs on the Meedan Check tipline
backend (Meedan Check), which gives MAFINDO consortium-grade duplicate
detection, claim clustering, and editorial workflow.

The tool's value to fact-checkers is twofold. As an intake channel,
it scales public verification requests beyond any one newsroom's
direct contact. As a signal source, the volume and pattern of
forwarded messages tells MAFINDO and CekFakta partners which claims
are spreading on WhatsApp before those claims surface on platforms
with stronger moderation visibility.

## When to use it

- A fact-checker working in Indonesia needs an intake channel that
 reaches Bahasa-Indonesian speakers on the platform where political
 content circulates fastest.
- A regional newsroom partner outside Indonesia wants to point an
 Indonesian source toward a verification path without routing
 through their own intake.
- An election cycle generates a surge of forwarded WhatsApp content
 and the operation needs the Meedan-Check duplicate-detection
 backend to keep volume tractable.
- A researcher is studying WhatsApp-mediated disinformation flow in
 Indonesia and needs an entry point into the MAFINDO and CekFakta
 workflow to understand response latency and routing.

## Limitations

!!! info "Limitations"
    - Dependent on WhatsApp's API and Meta's policies; operational
    continuity is exposed to platform policy changes.
    - Single-language: Bahasa Indonesia only. Lao, Sinhala, Tamil,
    Filipino/Tagalog, Thai, and Malay speakers are not served.
    - As a tipline, the response cycle is editorial; turn-around is
    not real-time. A user expecting a synthetic-content verdict in
    seconds will be disappointed; the bot's output is a verified
    fact-check, not a detector score.
    - Bot is built on the Meedan Check infrastructure;
    throughput and feature evolution are coupled to Meedan's
    upstream development.

## Privacy and threat model

The bot operates inside WhatsApp, which means messages travel via
WhatsApp's end-to-end encryption between the user's device and
MAFINDO's backend. Once a message is received by Kalimasada, the
content enters MAFINDO's editorial workflow on the Meedan Check
backend, where MAFINDO staff and CekFakta partners may review it for
verification. Users should treat Kalimasada as a fact-check intake,
not a private channel: anything forwarded becomes part of an
editorial workflow that may inform published debunks.

For sources who are themselves at risk (a whistleblower forwarding a
sensitive document, an activist sending a clip that identifies them),
the bot is not the right channel. Direct contact with a MAFINDO
journalist, with explicit consent and source-protection arrangements,
is the right path. The bot is for citizen reports, not source
handling.

!!! danger "Source-protection override (S5 — private or encrypted group collection)"
    Kalimasada is for consented citizen forwards only; importing
    scraped or infiltrated private-group content is outside its
    operational model. Mitigation steps:

    1. Use Kalimasada only with messages the user has personally
    forwarded with intent to verify; never import data from
    scraped Indonesian WhatsApp groups, even when the original
    claim is public.
    2. For source-identifying material, route the case to a
    MAFINDO journalist or CekFakta partner directly with
    explicit consent and source-protection arrangements,
    bypassing the public bot.
    3. Treat the forwarding chain as chain-of-custody evidence
    for any case that later requires editorial review.

## Country and platform applicability

- **Indonesia:** primary deployment. Used through and after the
 2024 presidential election and again during the January-February
 2025 deepfake cluster involving Prabowo Subianto and Sri Mulyani
 Indrawati impersonations (regional case documentation).
- **Laos:** not applicable; no Lao-language coverage.
- **Malaysia:** not applicable as a primary intake channel;
 Malaysia uses Sebenarnya AIFA and partner regional
 routing.
- **Philippines:** not applicable; the Philippines runs through
 the #FactsFirstPH coalition via Meedan Check directly,
 with SEEK / VERA Bot as the documented Viber/Messenger
 channel.
- **Sri Lanka:** not applicable; Sri Lanka has no
 Meedan-style tipline backend (regional case documentation Lanka).
- **Thailand:** not applicable; Thailand uses Cofact Thailand (LINE-native).

Platform applicability: WhatsApp only. Indonesian audiences also
move through Facebook and TikTok; those flows reach
Kalimasada only when a recipient forwards the content into WhatsApp.

## How to access

Citizens in Indonesia add the Kalimasada WhatsApp number to their
contacts and forward messages to the bot. The number is published on
MAFINDO's website and on CekFakta consortium materials. There is no
account creation, no install beyond WhatsApp itself, and no fee.

For fact-checkers and researchers wanting to study or partner with
the workflow, contact MAFINDO directly. The Meedan Check backend that
Kalimasada runs on (Meedan Check) is separately documented for
organisations considering similar deployments.

## Cost (current as of 2026-05)

Free for the public user. The underlying infrastructure (Meedan
Check backend, MAFINDO operational costs) is grant-funded through
MAFINDO's own funding stack and consortium contributions; cost
sustainability is on the operating organisation, not on the user.

## Quickstart

1. Open WhatsApp on your phone.
2. Save the Kalimasada bot number from MAFINDO's website to your
 contacts.
3. Forward the suspect message, image, or link to the bot.
4. Wait for the bot's response: if MAFINDO has previously verified
 the claim, the response returns the existing fact-check; if not,
 the claim is queued for editorial review.
5. For a queued claim, the response cycle depends on MAFINDO's
 workflow and may take hours to days; users should not treat the
 bot as a real-time detector.

## In the toolkit's workflow

Source-history and behaviour pillar non-detector platform per
Architectural Anchor 1. Sits in 2B.1 Multilingual tiplines as the
country-anchored Indonesia entry alongside the global primary
Meedan Check, the LINE-native Cofact Thailand, and
the government-operated Sebenarnya AIFA in Malaysia.

Standard combinations:

- With **Meedan Check** as the underlying backend; Kalimasada
 is functionally MAFINDO's WhatsApp face on Meedan Check
 infrastructure.
- With **Yudistira (MAFINDO)** at 2B.2 for Bahasa-specific
 claim extraction on the queue's volume.
- With **MAFINDO Satgas Pemilu** at 2A.4 for the workflow
 design pattern that orchestrates Kalimasada intake during election
 cycles.
- With **InVID-WeVerify** at 1B.1 when image or video
 content forwarded to Kalimasada needs forensic verification before
 the fact-check response goes back.
- With **Hive AI** at 1A.1 for AI-generated image triage on
 visual claims that arrive through the bot during a deepfake surge.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
routes Indonesian forwarded WhatsApp content to Kalimasada as the
country tipline of record for the `-id` `-wa` combination. [T1
image triage](../decision-trees/t1-image-triage.md) and
[T2 video triage](../decision-trees/t2-video-triage.md) feed back
into Kalimasada when the underlying forensic check resolves.

This card carries no detector signal class: Kalimasada produces a
non-detector source-history signal (the verified fact-check) and a
behaviour signal (the volume and pattern of forwarded reports). Per
Anchor 2 these combine cleanly with detector signals from Pillar 1
when both are present in the same case.

## Override notes

!!! note "Override notes"
    - **Built on Meedan Check (built-on-Meedan-Check-cross-reference):**
    Kalimasada is functionally MAFINDO's WhatsApp deployment of
    Meedan Check. Operational continuity, throughput, and
    feature evolution are coupled to that upstream backend; this
    card cross-references Meedan Check for backend-level details rather
    than re-stating them.

## Sources

- MAFINDO. *Kalimasada — WhatsApp hoax-checker bot*. MAFINDO (Masyarakat Anti Fitnah Indonesia), 2024. [mafindo.or.id](https://mafindo.or.id).
- MAFINDO. *TurnBackHoax.id — Anti-Hoax Search Engine*. MAFINDO, 2024. [turnbackhoax.id](https://turnbackhoax.id).
