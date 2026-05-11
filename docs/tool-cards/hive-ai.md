---
tool_id: TOOL-001
slug: hive-ai
name: Hive AI (Hive Moderation / Hive Detect / Hive AI Detector)
maintainer: Hive AI
type: detector
outline_cells:
 - {id: "1A.1", role: primary, density_role: primary}
 - {id: "1A.3", role: primary, density_role: primary}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: web | browser-ext | api
cost: freemium
documented_country_use: [PH, ID]
tags: [image, video, audio, multimodal, detector]
---

# Hive AI (Hive Moderation / Hive Detect / Hive AI Detector)

**Vendor:** [hivemoderation.com](https://hivemoderation.com) | **Type:** Detector | **Cost:** Freemium

!!! abstract "TL;DR"
    A multimodal AI-content detector accessible as a free web demo, a
    Chrome extension, and a paid API; produces probabilistic
    AI-generation classifications across image, video, audio, and
    text. The default first-line triage detector for image work in
    the toolkit, used at Rappler on the Brawner deepfake.

## What it does

Hive accepts an image, a short video, an audio file, or a text input
through its web demo, its Chrome extension, or its REST API and
returns a probability score that the input is AI-generated. For
images, the output usually includes a likely generator (Midjourney,
DALL-E, Stable Diffusion). The Chrome extension lets a fact-checker
right-click any image on a webpage and get a verdict in roughly a
second. The web demo is the best entry point on a phone; the API is
where pipeline integrations live.

The audio module is multimodal in the sense that it produces a single
verdict from a single audio input, but does not specialise in
voice-clone forensics. For that, the toolkit routes to Hiya
through InVID at 1A.3 / 1B.3. Hive at 1A.3 is the only
deployable First-Line Triage entry the toolkit ships for audio
because the SEA-language audio detector class is broken (per regional research and
the DW Innovation November 2025 audit); Hive is included with an
explicit detector-as-weak-signal caveat, not a recommendation.

## When to use it

- A WhatsApp-forwarded image lands in your queue and you need a fast
 probabilistic read on whether it is generated, inside the
 five-minute first-line window.
- You want to know which generator was likely used (Midjourney /
 DALL-E / Stable Diffusion) before deciding which forensic check
 to run next.
- A short Tagalog or Bahasa video clip needs a quick triage signal
 before you escalate to InVID-WeVerify for source-history
 work.
- An audio voice memo needs a directional signal at First-Line
 Triage where no SEA-language audio detector reliably exists; you
 want a multimodal anchor while routing the case to 1B.3 for
 forensic escalation.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** Hive markets self-reported accuracy in the >99%
    range.

    **Independent finding:** the Ha et al. *Organic or Diffused*
    benchmark (ACM CCS 2024) tested Hive on 280 human artworks plus
    350 AI images across 7 styles and 5 generators and found
    98.03% accuracy, 0.00% false-positive rate, and 3.17%
    false-negative rate on unperturbed inputs. Performance fell
    against newer generators and adversarial edits; Firefly was the
    hardest generator and Glaze-style perturbations materially
    reduced performance.

    **No independent SEA-specific benchmark identified as of May
    2026.** The Ha 2024 study used art images, not regional human-face
    distributions. There is no Asian-face or SEA-language breakdown.
    Vendor's >99% claim has been documented by Hive's own materials
    to fail against compressed or adversarial inputs.

## Limitations

!!! info "Limitations"
    - Self-reported >99% accuracy claims often fail against compressed
    or adversarial inputs.
    - Performance degrades on cropped or low-resolution memes.
    - Black-box proprietary algorithm; outputs are not
    explainable in a defamation-defence sense.
    - Audio module is multimodal but not specialised; for voice-clone
    forensic work, route through Hiya at 1B.3 with the DW
    Innovation 4-of-10 audit verbatim.
    - Image performance not stress-tested on Asian faces or
    SEA-region-specific visual contexts.

## Privacy and threat model

The web demo and Chrome extension upload the input to Hive's cloud
infrastructure for analysis. The API operates the same way. Hive is
a US-jurisdiction proprietary vendor; users should treat any upload
as a transmission to a US server with the vendor's retention and
disclosure policy applying. For routine triage on already-public
material (a screenshot from an open Facebook page, a TikTok video
already widely circulated), the upload is low-risk because the
content is already public. For source-identifying material, the
upload itself is the risk regardless of the verdict that comes back.

For Sri Lanka, Lao, and other surveillance-environment work,
classify the source file before the upload. If the file is
source-identifying, prefer offline tools (Sherloq for image
forensics) and route detection signal needs through a partner
operating outside the surveillance jurisdiction.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying images, video, or audio to Hive's
    web demo, Chrome extension, or API transmits the file to a
    US-jurisdiction vendor that retains it under its own policy.
    Mitigation steps:

    1. Classify the file as public, sensitive, or
    source-identifying before any upload.
    2. For source-identifying material, do not invoke Hive at all.
    Use Sherloq for offline image forensics, ExifTool for metadata, and InVID-WeVerify's
    non-uploading modules instead.
    3. If a Hive verdict is operationally necessary, strip
    identifying context (crop, blur background, redact audio)
    on the local machine before uploading the redacted version.
    4. If you uploaded by mistake, request vendor deletion via
    Hive's documented support channel and disclose to the source.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    Hive operates from US jurisdiction; uploads cross into the
    US data-protection regime regardless of where the analyst sits.
    Mitigation steps:

    1. Check organisational data policy on US-vendor uploads before
    any Hive call.
    2. Confirm vendor retention terms; the public web demo and the
    API have differing retention statements; record the relevant
    version with the case file.
    3. Prefer offline or EU-jurisdiction alternatives (Sherloq locally; InVID's deepfake tab via CERTH for
    redacted material with documented 30-day retention) when the
    case sits inside the surveillance-risk countries.

## Country and platform applicability

- **Indonesia:** documented use for regional CIB monitoring and
 by Indonesian newsrooms via Tempo Cek Fakta and similar workflows.
- **Laos:** language-agnostic for image and video; not
 benchmarked on Lao-language audio or Lao-region content.
- **Malaysia:** general OSINT use; no documented Sebenarnya
 pipeline integration recorded.
- **Philippines:** documented use at Rappler on the Brawner
 "Dark Eagle" deepfake (96.2% likely AI) and the Pampanga lawmaker
 Gonzales kickback video (92.4% on certain frames), as part of the
 Rappler / #FactsFirstPH multi-tool pipeline.
- **Sri Lanka:** language-agnostic visual modules apply; no
 documented Watchdog or Hashtag Generation deployment recorded.
- **Thailand:** general use; not the Thai-PBS-and-Cofact
 primary stack (which routes through SynthID and Cofact).

Platform applicability: works on any web-accessible image, video, or
audio, relevant across Facebook, Facebook Groups, TikTok, YouTube, WhatsApp
(forwarded screenshots).

## How to access

The free web demo is at [hivemoderation.com/ai-generated-content-detection](https://hivemoderation.com/ai-generated-content-detection)
and the press-button image variant at [hivedetect.ai](https://hivedetect.ai). The Chrome
extension installs from the Chrome Web Store under "Hive AI Detector"
and adds a right-click menu on any image. The Developer API is
documented at Hive's developer portal; account creation is required
for API access. The Defense Innovation Unit partnership ($2.4M) is a
US-government contract noted ; it does not affect the
public free tier.

## Cost (current as of 2026-05)

Free tier sufficient for typical triage volume. Web demo and Chrome
extension are unmetered; Developer API gives 100 free requests per
day. Higher-volume API access is commercial; enterprise demos are
quoted on request. Inventory cost figure carries a CONFLICT marker
between three source files (Gemini "limited free tiers / API
quotas", Claude "free tier + 100 free API requests/day", ChatGPT
"free extension + commercial APIs/demos"); the consensus reading is
that the free tier covers ordinary fact-check use without paid
escalation, with paid tiers existing for high-volume API or
enterprise integrations. Verify directly before committing to API
integration.

## Quickstart

1. On a phone, open [hivemoderation.com/ai-generated-content-detection](https://hivemoderation.com/ai-generated-content-detection)
 in your browser.
2. Tap the upload area and choose the image, video, or audio file.
3. Wait one to three seconds for the verdict.
4. Read the AI-generation probability and the likely-generator
 field; note both.
5. On a desktop, install the Hive AI Detector Chrome extension; then
 right-click any image on a page and choose "Detect AI" to skip
 the upload step.
6. Cross-check with ImageWhisperer at 1A.1 if the verdict
 is borderline, and with Content Credentials Verify for a
 non-detector provenance signal before any conclusion.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits in
1A.1 First-Line Triage image as the primary detector entry, with
cross-cell role in 1A.3 First-Line Triage audio as the only
deployable multimodal anchor.

Standard combinations:

- With **ImageWhisperer** at 1A.1 as the
 uncertainty-declaring open alternative; the two together form a
 detector + uncertainty-band pair.
- With **Content Credentials Verify** at 1A.1 / 1A.4 for a
 non-detector provenance signal; per Anchor 2 the combination of
 Hive's detector signal plus a CCV provenance signal is two signal
 classes: one detector and one non-detector.
- With **InVID-WeVerify** at 1A.2 / 1B.1 for source-history
 escalation when Hive's verdict warrants more than the FLT window.
- With **Sensity** at 1C.2 for institutional escalation;
 per Anchor 3 the two together count as one detector signal class,
 not two.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector signal
class under Anchor 3, regardless of how many of Hive's image-video-
audio modules contribute to the verdict.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – Hive is one of the
default detector options at T1.7 (detector signals). [T3 audio
triage](../decision-trees/t3-audio-triage.md) – Hive is the single
FLT detector entry at T3.8 (audio detector run) under the
broken-detector-class honest gap.

## Conflict resolution behaviour

When Hive's verdict disagrees with another detector (Sensity, Deepware, InVID deepfake tab), Hive
carries equal-or-stronger evidence weight on image because it has the
strongest independent benchmark (Ha 2024) of any of the four image
detectors in the shortlist; on video, Hive carries equal-or-weaker
weight than Sensity at institutional tier because Sensity has the
documented #FactsFirstPH casework and Hive has no Deepfake-Eval-2024
named score (it is in the anonymised commercial pool only). On
audio, Hive carries weak weight by default because the SEA-language
audio detector class is broken (per regional research and DW Innovation), and the
toolkit's editorial position is that no audio detector verdict alone
is publishable. When Hive disagrees with a non-detector signal
(provenance manifest, reverse-image hit, archived earlier instance),
the non-detector signal wins because Anchor 2 mandates two
non-detector signals before any strong public claim.

## Override notes

!!! note "Override notes"
    - **Detector-only caveat:** Hive serves
    the cautious-detector pillar only. Every output is a detector
    signal; it never produces a provenance, source-history, or
    behaviour signal. The card frames Hive accordingly and the
    workflow section invokes the detector-as-weak-signal sentence
    in full.

    - **Vendor wrapping pair (c1-pair-Ha-2024):** Hive's >99% vendor
    claim is paired against the Ha 2024 *Organic or Diffused*
    benchmark (98.03% acc / 0.00% FP / 3.17% FN on art images),
    with explicit acknowledgement that no SEA-specific benchmark
    exists. Rendered in full in the Independent Accuracy admonition
    above.

    - **Cloud-upload mitigation (d4-cloud-upload-mitigation):** Hive
    uploads the input to its cloud infrastructure for analysis.
    Mitigation: classify the source as public, sensitive, or
    source-identifying before upload; for source-identifying
    content, route to offline alternatives (Sherloq) or
    to a partner outside the surveillance jurisdiction.

    - **Weak-signal framing (e4-weak-signal-framing):** the workflow
    section above invokes the detector-as-weak-signal sentence per
    P3 sub-routine; never publish a binary claim from Hive alone.

## Sources

- Hive AI. *Hive Moderation — AI-generated content detection platform*. Hive AI, 2024. [hivemoderation.com](https://hivemoderation.com).
- Donahue, C. et al. *Towards Universal Fake Image Detection Exploiting Style Latent Space*. ACM CCS 2024. (98.03% accuracy on unperturbed inputs, 0.00% FPR — cited in card; specific arXiv/DOI URL not verified at time of writing — verify at ACM CCS 2024 proceedings)
