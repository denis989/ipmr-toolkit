---
tool_id: TOOL-215
slug: tempo-detektif-deepfake
name: Tempo Detektif Deepfake
maintainer: Tempo Cek Fakta + Tempo Media Lab (with IFCN ENGAGE)
type: non-detector
outline_cells:
 - {id: "2A.3", role: primary, density_role: primary}
pillar_service: [source-history, behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free
languages_ui: [id]
languages_content: [id]
access: web
cost: free
documented_country_use: [ID]
tags: [prebunking, inoculation, media-literacy, deepfake, indonesia, bahasa, tempo, newsgame]
---

# Tempo Detektif Deepfake

**Operator:** [tempo.co](https://tempo.co) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A Bahasa-Indonesian inoculation newsgame from Tempo Cek Fakta
    that walks players through deepfake-recognition scenarios
    using a multiple-choice format. WAN-IFRA Digital Media
    Awards Asia 2026 Silver in Best in Countering
    Disinformation. The fact-checker's deployment tool, not the
    fact-checker's verification tool; its purpose is to inoculate
    audiences before they encounter the synthetic content the
    fact-checker is debunking.

## What it does

Detektif Deepfake is a browser-based newsgame that presents
players with deepfake-recognition scenarios in Bahasa Indonesia,
asking the player to identify manipulation cues (visual
artefacts, audio mismatches, contextual signals) through a
multiple-choice interface. The pedagogical foundation is
inoculation theory: by exposing players to weakened forms of
manipulation techniques in a low-stakes setting, the game
builds recognition skills that transfer to real encounters with
synthetic content in the wild.

The game was developed by Tempo Cek Fakta (Tempo's fact-check
desk) and Tempo Media Lab as part of the IFCN ENGAGE programme
and launched in May 2025. It won the WAN-IFRA Digital Media
Awards Asia 2026 Silver for Best in Countering Disinformation in
Manila on 28 April 2026. The lead author is Inge Klara Safitri.
Two companion games (Vaksin HOX for general hoax inoculation and
Anti Jebakan Batman for phishing) extend the same pedagogical
approach across adjacent disinformation surfaces. Detektif
Deepfake itself recommends Deepware.ai and MIT Media Lab
DetectFakes inside the game's "go further" guidance.

For the fact-checker, the game is something to deploy outward
rather than something to apply inward. The fact-checker who
embeds Detektif Deepfake on the Tempo Cek Fakta page, shares it
through a partner newsroom's social media, or hosts it inside a
school workshop is using the tool the way it is designed to be
used.

## When to use it

- A regional newsroom is preparing audiences for an election
 cycle and wants a Bahasa-Indonesian inoculation surface that
 reaches readers before deepfakes circulate widely.
- A media-literacy programme in Indonesia is training secondary-
 school or university students and needs an interactive,
 Bahasa-native game that teaches deepfake-recognition through
 practice rather than lecture.
- A community-volunteer training session needs a short,
 engaging warm-up that teaches the manipulation cues
 fact-checkers themselves rely on when triaging suspect video.
- A coalition campaign (CekFakta, MAFINDO, Tempo combined) is
 preparing audiences in advance of an anticipated synthetic-
 political-content surge: election season, a foreign-policy
 flashpoint, a known impersonation actor.

## Limitations

!!! info "Limitations"
    - Single-format game. The multiple-choice
    newsgame format is one inoculation surface; effects
    typically require booster sessions to maintain over months
    rather than days.
    - Should be ported to other SEA languages (override flag `should-port-other-SEA-languages-pointer`).
    Bahasa Indonesia coverage only at present; Thai, Filipino,
    Sinhala, Tamil, Malay, and Lao audiences cannot use the
    game in their working language. The toolkit's cell-level
    honest-gap (G-051) names the absence of localised
    prebunking effectiveness measurements outside Indonesia.
    - Inoculation effects measured for prebunking generally
    decay over weeks without reinforcement; the literature
    base for Bad News and Jigsaw Prebunking puts the half-
    life in the order of weeks, and Detektif Deepfake
    inherits that shape rather than overcoming it.
    - The game teaches recognition of manipulation cues that
    newer synthetic-content generators may not produce; the
    game's effectiveness against the most current deepfake
    generation methods is a function of how recently the
    game's scenarios were updated relative to the generator
    landscape.

## Privacy and threat model

The game is a publicly accessible web page. Players load it in
the browser; no account creation is required for casual play.
Tempo's standard web analytics apply to the page; for any
deployment that integrates the game into a newsroom workflow
beyond casual play (curriculum integration, formal training,
community-volunteer programmes) the operator should review
Tempo's data-handling terms before deployment.

The threat model that matters here is the deployment model
rather than the data-flow model; a fact-checker embedding the
game does so for an audience the fact-checker has identified as
worth reaching. The game itself does not handle source-
identifying material because it works on pre-built scenarios,
not on user-submitted content.

## Country and platform applicability

- **Indonesia:** primary deployment. Tempo Cek Fakta uses
 the game in audience-engagement and education programming;
 the WAN-IFRA Silver context establishes regional editorial
 recognition.
- **Laos:** not applicable in the source language; Bahasa
 Indonesia content is not accessible to Lao audiences. The
 cell-level honest-gap on localised prebunking outside
 Indonesia applies.
- **Malaysia:** Bahasa-Malaysia speakers can read the
 Bahasa-Indonesia content with comprehension, but the game is
 not adapted to Malaysian context, references, or named
 entities. Practical reach is limited; the inoculation case
 for Malaysia would benefit from a Malay adaptation.
- **Philippines:** not applicable in the source language;
 the underlying inoculation pattern transfers but a Filipino
 adaptation does not yet exist .
- **Sri Lanka:** not applicable in the source language;
 Sinhala or Tamil adaptations would require local Tempo-
 equivalent partners to lead.
- **Thailand:** not applicable in the source language;
 a Thai adaptation could plausibly be led by Cofact or AFP
 Fact Check Thailand if regional partnership emerged.

Platform applicability: web-deployed; the game can be embedded
or linked from any platform a newsroom or training operator
uses to reach their audience (Facebook, Facebook Groups, TikTok organic posts,
LINE, WhatsApp shareable links).

## How to access

Free public access through the Tempo Cek Fakta website. The
game is one of three companion newsgames Tempo publishes
(alongside Vaksin HOX and Anti Jebakan Batman); Tempo's
fact-check section is the entry point. No account required for
play; institutional integration (embedding into curriculum,
deploying through partner newsroom social media) is a partner
arrangement with Tempo rather than a configuration step.

## Cost (current as of 2026-05)

Free for players and for institutions integrating the game into
audience-engagement work. Tempo's institutional partnership
costs sit outside the player-side product; the game itself is
published under a free editorial licence.

## Quickstart (deployment-side)

(The user reading this card is a fact-checker deploying the
game to audiences, not a player verifying suspect content. The
quickstart reflects that.)

1. Identify the audience moment: an election cycle on the
 horizon, a media-literacy curriculum slot, a community-
 volunteer training session, an anticipated synthetic-content
 surge.
2. Visit the Tempo Cek Fakta page and locate Detektif Deepfake;
 confirm the game's current scenarios are recent enough for
 the audience moment (the multiple-choice scenarios reflect
 the synthetic-content landscape they were built against).
3. For audience deployment through a partner newsroom or NGO,
 share the game's URL through that organisation's social-
 media channels alongside framing copy that names the
 inoculation purpose ("five minutes of practice that makes
 spotting deepfakes easier").
4. For workshop deployment, plan a 15-30 minute session that
 includes the game plus discussion of the manipulation cues
 the player encountered.
5. For curriculum integration, partner with Tempo and adapt the
 game into the broader media-literacy curriculum frame
 alongside Vaksin HOX and Anti Jebakan Batman.
6. After deployment, plan reinforcement: booster sessions,
 follow-up content, or pairing with Bahasa fact-check
 coverage; inoculation effects decay without
 reinforcement.

## In the toolkit's workflow

Source-history and behaviour pillar non-detector audience-
engagement deployment per Architectural Anchor 1. Sits in 2A.3
as the primary entry: the SEA-grounded gold-standard
inoculation game that the toolkit privileges as the default
reference for any prebunking deployment in or about Indonesia.

Standard combinations (deployment combinations):

- With **IREX L2D / Gali Fakta** at 2A.3 – IREX's
 curriculum-style media-literacy training pairs naturally with
 Detektif Deepfake's interactive game format; the two together
 form a complete media-literacy programme for Bahasa
 audiences.
- With **Jigsaw Prebunking** at 2A.3 when a campaign
 needs both a deeper interactive game (Detektif Deepfake) and
 shorter video-ad inoculation surfaces (Jigsaw) reaching
 passive audiences on YouTube, Meta, and TikTok.
- With **Bad News / Harmony Square** at 2A.3 when a
 trainer wants to teach the broader inoculation pattern
 alongside the deepfake-specific game; Bad News covers the
 six general manipulation techniques, Detektif Deepfake covers
 the synthetic-content surface.
- With **Kalimasada** and **Yudistira** at
 2B – the prebunking work happens upstream of the tipline
 intake and downstream feedback (community questions about
 scenarios) can flow back into the MAFINDO/CekFakta workflow.

Decision-tree references: this is not a verification routine;
the decision trees in T1–T7 do not invoke Detektif Deepfake at
runtime. The tool sits in the editorial-strategic layer that
shapes audience preparation rather than per-claim handling.

This card carries no detector signal class: Detektif Deepfake
is an inoculation deployment that builds audience recognition;
it does not produce a synthetic-content verdict on any specific
piece of suspect content.

## Override notes

!!! note "Override notes"
    - **WAN-IFRA Silver April 2026 (wan-ifra-silver-apr-2026-
    pointer):** the game won the WAN-IFRA Digital Media Awards
    Asia 2026 Silver for Best in Countering Disinformation in
    Manila on 28 April 2026. The award context anchors the
    regional editorial recognition that justifies Detektif
    Deepfake's primary status in 2A.3.
    - **Should be ported to other SEA languages (should-port-
    other-SEA-languages-pointer):** Bahasa Indonesia coverage
    only at present. The cell-level honest-gap on localised
    prebunking effectiveness outside Indonesia (G-051) names
    the structural absence of Thai, Filipino, Sinhala, Tamil,
    Malay, and Lao adaptations; partner-led adaptation is the
    operational route to closing the gap.

## Sources

- Safitri, I.K. et al. *Detektif Deepfake — deepfake literacy newsgame*. Tempo Cek Fakta / Tempo Media Lab, May 2025. [tempo.co/tag/detektif-deepfake](https://tempo.co/tag/detektif-deepfake). (WAN-IFRA Digital Media Awards Asia 2026 Silver, 28 April 2026, Manila — cited in card)
