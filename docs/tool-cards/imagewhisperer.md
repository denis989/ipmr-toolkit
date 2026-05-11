---
tool_id: TOOL-002
slug: imagewhisperer
name: ImageWhisperer / Detectai.live
maintainer: Henk van Ess
type: mixed-with-declaration
outline_cells:
 - {id: "1A.1", role: primary, density_role: alternative}
pillar_service: [cautious-detector, source-history]
signal_class: mixed-with-declaration
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [image, uncertainty-band, gijn, deadline-journalism]
---

# ImageWhisperer / Detectai.live

**Vendor:** [detectai.live](https://detectai.live) | **Type:** Detector + non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free open-source image-AI detector explicitly designed to admit
    "I don't know" when the evidence is borderline; combines parallel Google Vision
    queries, LLM analysis, and 41 forensic checks, plus a 100+ entry
    fact-checker debunked-image database. Named in GIJN's Top
    Investigative Tools 2025.

## What it does

ImageWhisperer accepts an image upload through its web interface and
runs three parallel processes: a Google Vision query for object,
landmark, and OCR signals; an LLM analysis pass that reasons over the
image's visual content and metadata; and a battery of 41 forensic
checks (compression artefacts, ELA-style residuals, generator-specific
fingerprints). The output is an AI-generation probability with an
explicit uncertainty band. The tool is designed by Henk van Ess
specifically to refuse a verdict when the evidence is borderline,
where most detector products default to producing false confidence.

The tool also cross-checks the image against a database of 100+
fact-checker-debunked images, which gives it a non-detector
source-history signal alongside its detector signal. That blended
output is why the tool's signal class is mixed-with-declaration: the
card must declare which class the user can extract from a given
verdict.

## When to use it

- An image's classification by another detector (Hive,
 InVID deepfake tab) is borderline and you want a
 second-opinion read from a tool whose design admits ambiguity.
- A meme is compressed or low-resolution to the point that vendor
 detectors (Hive) lose accuracy; the uncertainty-band design is
 more honest about that condition.
- You want to check whether an image has already been debunked by
 another fact-checker before running detector work.
- You are training a fact-checker workshop and want to demonstrate
 why "I don't know" is an acceptable detector output for borderline
 cases.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **No vendor headline accuracy claim located in inventory or
    inventory.** The tool is designed around uncertainty-band
    output, not headline accuracy.

    **No independent SEA-specific benchmark identified as of May
    2026.** Tool is named in GIJN's Top Investigative Tools 2025 as a
    most-cited 2025-26 newcomer for deadline-pressured journalists,
    but no quantitative independent evaluation has been published.

## Limitations

!!! info "Limitations"
    - Acknowledges, in its own design framing, that the
    generator-vs-detector arms race is tilted toward creators.
    - SEA language and SEA-specific image content not specifically
    documented in available sources; treat any output on regional
    content as directional.
    - Tool is relatively new (v1.0 launched February 2026); track
    record on adversarial inputs is shorter than that of
    established detectors.

## Privacy and threat model

ImageWhisperer is a free web tool that uploads the input image to its
cloud infrastructure for the parallel Google Vision and LLM
processing. The Google Vision component routes image data through
Google's servers under Google Cloud's policy; the LLM component runs
through whichever provider the tool currently uses (van Ess's
deployment, which has shifted between providers across versions).
For routine triage on already-public images, the upload is low-risk.
For source-identifying images, the upload chain involves at least
one major US cloud provider; classify accordingly before use.

## Country and platform applicability

- **Indonesia:** no documented Indonesian-newsroom deployment
 recorded ; tool is language-agnostic for image
 analysis and applies in principle.
- **Laos:** no documented use; language-agnostic for image
 analysis.
- **Malaysia:** no documented use; tool is open and free.
- **Philippines:** no documented Rappler / VERA Files
 deployment recorded; tool postdates much of the documented
 pipeline.
- **Sri Lanka:** no documented Watchdog or Hashtag
 deployment recorded.
- **Thailand:** no documented use.

Documented case base remains thin (B4 score 1). The tool's
inclusion rests on its design discipline (uncertainty-band output)
and the GIJN endorsement, not on regional deployment evidence.

Platform applicability: works on any image regardless of source
platform.

## How to access

The web interface is at `detectai.live`. No account is required for
basic image checks. The tool is open-source; the maintainer's
distribution channels are the GIJN ecosystem and the broader
verification community via van Ess's own publications.

## Cost (current as of 2026-05)

Free. The tool is open-source and the public web instance imposes no
fee; if van Ess restricts free-tier volume in future, the
open-source release allows self-hosting.

## Quickstart

1. Open `detectai.live` in your browser (works on phone or desktop).
2. Upload the image you want to check.
3. Wait for the parallel Google Vision, LLM, and forensic-check
 passes to complete.
4. Read the AI-generation probability AND the uncertainty band; if
 the band overlaps zero, treat the verdict as "do not know" rather
 than as a soft positive or negative.
5. Read the debunked-image cross-check result; if the image has
 appeared in a previous fact-check, that source-history signal
 typically resolves the case without further detector work.
6. Pair the output with Hive's verdict at 1A.1 and a
 Content Credentials Verify provenance check before any
 conclusion.

## In the toolkit's workflow

Mixed-with-declaration tool: serves cautious-detector and
source-history pillars per Architectural Anchor 1. Sits in 1A.1
First-Line Triage image as the alternative to Hive,
explicitly chosen for borderline cases where the uncertainty-band
design is more honest than a Hive probability score.

Standard combinations:

- With **Hive** at 1A.1 as a confidence pair – Hive gives a
 probability, ImageWhisperer gives a probability with an
 uncertainty band. Together they tell the user how much to trust
 the verdict.
- With **Content Credentials Verify** for non-detector
 provenance check; per Anchor 2 this combination produces one
 detector signal class plus one provenance signal class.
- With **InVID-WeVerify** at 1B.1 for source-history
 escalation when the debunked-image cross-check returns nothing.

Signal class declaration: when the verdict is the AI-generation
probability, the output is a detector signal under Anchor 1 (one weak
signal; never publishable alone). When the verdict is a hit on the
debunked-image database, the output is a source-history non-detector
signal: the image has appeared in a previous published
fact-check, which is independently citable evidence regardless of
what the detector probability says. The card and the user should
treat these as two distinct signal classes.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – ImageWhisperer is the
borderline-case branch at T1.2 (provenance) feeding into T1.7
(detector signals) when no C2PA manifest is present.

## Override notes

!!! note "Override notes"
    - **Declare uncertainty output:**
    the tool produces both detector and source-history signals; the
    card and the user must declare which one is being read from
    any given verdict. This is why the tool is classified
    mixed-with-declaration, not detector.

    - **No vendor accuracy claim (c1-no-vendor-claim):** the C1
    wrapping pair has no vendor headline number to wrap; the
    Independent Accuracy admonition records this; no number is
    improvised.

## Sources

- van Ess, H. *ImageWhisperer / Detectai.live — AI image detection with uncertainty bands*. Detectai.live, 2026 (open-source). [detectai.live](https://detectai.live).
