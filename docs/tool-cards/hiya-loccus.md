---
tool_id: TOOL-033
slug: hiya-loccus
name: Hiya / Loccus
maintainer: Hiya (formerly Loccus, acquired July 2024)
type: detector
outline_cells:
 - {id: "1B.3", role: primary, density_role: primary}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: proprietary-hosted
languages_ui: [en]
languages_content: [multilingual-claimed-unreliable]
access: api | browser-ext (via TOOL-022)
cost: paid
documented_country_use: []
tags: [audio, voice-clone, invid-integrated, dw-audit-4-of-10]
---

# Hiya / Loccus

**Vendor:** [hiya.com](https://hiya.com) | **Type:** Detector | **Cost:** Paid

!!! abstract "TL;DR"
    The only press-button voice-clone detector currently accessible to
    SEA newsrooms via the InVID-WeVerify voice-clone tab. Documented
    by DW Innovation (November 2025) as 4-of-10 correct on a
    multilingual audit set with 3-of-10 misidentified and 3-of-10
    inconclusive. Use only as one weak signal; never as standalone
    evidence.

## What it does

Hiya (formerly Loccus, acquired July 2024) is a hosted voice-clone
detection service. Its operational surface in the toolkit's workflow
is the InVID-WeVerify voice-clone tab, the only press-button audio
detector available to SEA newsrooms without enterprise procurement.
Audio uploads from the InVID tab go to Hiya's US-jurisdiction servers
for analysis; the service returns a voice-clone score and a
confidence indicator inside the InVID interface.

The toolkit ships Hiya as the primary entry in 1B.3 because it is
the only deployable press-button SEA-accessible option, not because
the audio detector class is reliable. The DW Innovation Nov 2025
audit conclusion ("none of Hiya / Deepfake Total / DeepFake-O-Meter
reliably identify AI voices across languages") is binding on the
card. The card carries the 4-of-10 finding verbatim and the
detector-as-weak-signal sentence in the workflow section.

## When to use it

- A WhatsApp or LINE voice memo has reached a fact-checker for a
 thirty-minute desk pass and you want a press-button voice-clone
 signal as one input among several non-detector signals.
- A regional case is in InVID's existing workflow and you want to
 use the integrated voice-clone tab without installing a
 separate audio detector.
- A workshop demonstrates how the audio detector class behaves
 across SEA languages; running the same Lao or Sinhala clip
 through Hiya and reading the verdict against the DW audit
 conclusion is the cleanest demonstration of the structural gap.
- An institutional partner is auditing the toolkit's audio coverage
 and needs documentation of why no SEA-language audio detector is
 recommended as standalone evidence.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** Hiya's marketing, quoted in the DW Innovation
    audit, promised "free, real-time detection, multi-language...
    detects voices created by all popular voice synthesis tools" but
    did not guarantee complete accuracy.

    **Independent finding:** DW Innovation, *Synthetic Audio
    Detectors Put to the Test* (November 2025; the audit referenced
    as DW Innovation audio detection audit). On a 10-sample multilingual dataset with fully
    synthetic, partially synthetic, and natural audio, multiple
    languages, male and female voices, varying lengths and formats,
    Hiya correctly identified 4 of 10 cases, misidentified 3 of 10,
    and returned 3 of 10 inconclusive. The audit also noted
    contradictory visualisations within the interface.

    **No independent SEA-specific benchmark identified as of May
    2026.** The DW audit's 10-sample dataset covered multiple
    languages but published no per-language, Asian-language, or
    tonal-language breakdown.

## Limitations

!!! info "Limitations"
    - DW Innovation Nov 2025 audit conclusion: tools tested do not
    "reliably identify AI voices across languages".
    - Closed-source hosted service; uploads to Hiya's US-vendor
    servers carry political risk for Lao and Sri Lanka surveillance
    environments.
    - Vendor multilingual claim contradicted by independent audit.
    - SEA-language voice-clone benchmark gap is structural; the
    cell-level honest gap names lao-real-gap-audio,
    sinhala-tamil-asymmetric-gap, and whatsapp-line-codec-untested
    explicitly.

## Privacy and threat model

The InVID voice-clone tab uploads audio to Hiya's US-jurisdiction
servers under Hiya's retention and disclosure policy. For routine
triage on already-public audio (a TikTok clip already widely
circulated, a public broadcast), the upload is low-risk because the
content is already public.

For source-identifying audio, the upload itself is the risk
regardless of the verdict. In Lao and Sri Lanka work, this is the
operationally critical concern.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying audio to the InVID voice-clone tab
    routes the file to Hiya's US-vendor infrastructure. Mitigation
    steps:

    1. Classify the audio file as public, sensitive, or
    source-identifying before any upload.
    2. For source-identifying material, do not use the voice-clone
    tab. Route the case to a regional partner outside the
    surveillance jurisdiction or to manual verification (caller
    verification, platform-of-origin check, voice-comparison
    interview).
    3. If a Hiya verdict is operationally necessary, redact
    identifying context (background noise, identifying speech
    content) on the local machine before uploading the redacted
    version.
    4. Document the upload in your case record and disclose to the
    source as part of source-protection practice.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    Hiya operates from US jurisdiction; voice-clone uploads via the
    InVID tab cross into the US data-protection regime regardless
    of analyst location. Mitigation steps:

    1. Check organisational policy on US-vendor audio uploads
    before invoking the voice-clone tab.
    2. Note that the audio passes through CERTH for the InVID-side
    routing before reaching Hiya; both retention windows apply
    to the upload.
    3. For Sri Lanka, Lao, and Thailand state-linked audio, prefer
    on-device transcription (Whisper local) and human
    listening comparison before any Hiya call.

## Country and platform applicability

- **Indonesia:** language-claimed coverage; not independently
 verified for Bahasa Indonesia voice-clone detection.
- **Laos:** Lao voice-clone detection unverified; the DW
 audit gives no Lao-language breakdown. Lao remains a structural
 honest-gap.
- **Malaysia:** language-claimed coverage; not independently
 verified for Malay.
- **Philippines:** language-claimed coverage; not
 independently verified for Filipino / Tagalog.
- **Sri Lanka:** Sinhala and Tamil voice-clone detection
 unverified; the DW audit gives no Sinhala or Tamil breakdown. The
 Sri Lankan asymmetric Sinhala-vs-Tamil framing per regional research applies;
 no SL-specific resources address this gap.
- **Thailand:** Thai (tonal language) voice-clone detection
 unverified; tonal-language performance is the explicit "no
 evidence" gap regional research names.

Platform applicability: works on any audio file regardless of source
platform; WhatsApp and LINE codec compression carry
the additional honest-gap caveat (G-017); the DW audit did not
test platform-codec-compressed audio specifically.

## How to access

Hiya is integrated into the InVID-WeVerify voice-clone tab. Install
the InVID-WeVerify extension (see [InVID-WeVerify Verification Plugin](invid-weverify.md))
and reach Hiya through the Audio analysis tab. Direct API access is
through Hiya's commercial channels.

## Cost (current as of 2026-05)

The InVID-WeVerify voice-clone tab provides free press-button access
to Hiya through the vera.ai-funded integration. Direct API access is
commercial; pricing on request from Hiya. Verify directly before any
institutional integration.

## Quickstart

1. Install the InVID-WeVerify browser extension from the Chrome Web
 Store, Microsoft Edge Add-ons, or Opera (see [InVID-WeVerify Verification Plugin](invid-weverify.md)).
2. Classify the audio file's sensitivity per the danger admonition
 above.
3. For source-identifying material, stop here and route to the
 alternatives named above.
4. For non-source-identifying material, right-click the audio source
 on a webpage and choose the InVID-WeVerify Audio analysis tab,
 or upload the file through the InVID interface.
5. Read the voice-clone score; treat the result as one weak signal
 class per Anchor 1.
6. Pair with non-detector verification: caller verification,
 platform-of-origin check, voice-comparison interview, or
 metadata extraction via [ExifTool](exiftool.md). Per
 Anchor 2 the toolkit's editorial position is that two
 non-detector signals are required before any strong public claim.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits as
primary at 1B.3 audio deepfake forensics. Primary by virtue of
being the only press-button SEA-accessible option, not by virtue of
class reliability.

Standard combinations:

- With **InVID-WeVerify** at 1A.2 / 1B.1 – Hiya is reached
 through the InVID voice-clone tab; the integration is the
 toolkit's only operational path to a press-button SEA voice-clone
 detector.
- With **TOOL-STUB-DEEPFAKETOTAL** at 1B.3 as the alternative
 audit-leader (DW 7-of-10) – the two together count as one
 detector signal class under Anchor 3, not two.
- With **TrueMedia.org (Georgetown McCourt School)** at
 1B.3 as the institutional escalation when closed-beta access is
 available.
- With **DW Innovation audit** as the institutional
 reference that anchors the editorial frame for the entire 1B.3
 cell.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector signal
class under Anchor 3.

Decision-tree references: [T3 audio triage](../decision-trees/t3-audio-triage.md) – Hiya is the press-button
PV branch invoked at T3.3 (transcript step) and T3.8 (audio detector
step). [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk) –
Hiya is routed through the S1 sub-routine before any upload.

## Conflict resolution behaviour

When Hiya's verdict disagrees with TOOL-STUB-DEEPFAKETOTAL or
TrueMedia, no audio detector carries decisive evidence
weight on its own; the DW audit class-level conclusion is binding.
Hiya specifically carries lower evidence weight than Deepfake Total
on the DW audit set (4-of-10 vs 7-of-10), but the toolkit's
editorial position is that the difference does not justify
publishing a claim from either verdict alone. When Hiya disagrees
with a non-detector signal (caller verification, platform-of-origin
check, manual voice-comparison), the non-detector signal wins
because Anchor 2 mandates two non-detector signals before any strong
public claim.

## Override notes

!!! note "Override notes"
    - **Verbatim DW Innovation Nov 2025 finding
    (c2-verbatim-DW-Innovation-Nov-2025):** the Limitations
    admonition carries the DW audit conclusion verbatim. The card
    does not soften "do not reliably identify AI voices across
    languages" into "limited reliability" or similar.

    - **Vendor wrapping pair (c1-pair-DW-4-of-10):** the vendor
    multi-language claim is paired against the DW 4-of-10 finding
    in the Independent Accuracy admonition.

    - **US-vendor mitigation (d4-mitigation-pass-Hiya-US-vendor):**
    the danger admonition above binds the source-protection
    mitigation steps (classify before upload; for sensitive
    material, route to alternatives; if upload is necessary,
    redact first; document and disclose).

    - **Weak-signal framing (e4-weak-signal-framing-binding-DW-audit):**
    the workflow section above invokes the detector-as-weak-signal
    sentence per P3 sub-routine; never publish a binary claim from
    Hiya alone. The DW audit gives the binding evidence base.

    - **Detector-only caveat:** Hiya
    serves the cautious-detector pillar only. Every output is a
    detector signal; the card frames the workflow accordingly.

## Sources

- Hiya. *Hiya — AI-powered call protection and deepfake voice detection*. Hiya, 2024. [hiya.com](https://hiya.com).
- DW Innovation / EU DisinfoLab. *Deepfake Detectors Put to the Test: An Evaluation of Three AI-Powered Audio Detection Tools*. DW Innovation, November 2025. [innovation.dw.com](https://innovation.dw.com); indexed at [disinfolab.eu/ai-disinfo-hub/](https://disinfolab.eu/ai-disinfo-hub/). (Hiya scored 4/10 — cited in card)
