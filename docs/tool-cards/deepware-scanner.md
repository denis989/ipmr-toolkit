---
tool_id: TOOL-023
slug: deepware-scanner
name: Deepware Scanner
maintainer: Deepware
type: detector
outline_cells:
 - {id: "1A.2", role: primary, density_role: alternative}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: mixed
languages_ui: [en]
languages_content: [agnostic]
access: web | mobile
cost: freemium
documented_country_use: [ID, LK]
tags: [video, deepfake, detector]
---

# Deepware Scanner

**Vendor:** [deepware.ai](https://deepware.ai) | **Type:** Detector | **Cost:** Freemium

!!! abstract "TL;DR"
    A press-button web and mobile video deepfake scanner used by
    Tempo Cek Fakta on the Dr Terawan diabetes-drug deepfake and by
    Fact Crescendo Sri Lanka on the Dhammika Perera deepfake.
    Documented to flip to "no deepfake detected" on a reduced-resolution,
    edited Obama clip. Treat the verdict as one weak signal only.

## What it does

Deepware Scanner accepts a video file or a URL pointing to one and
returns a probability score that the video has been manipulated.
The web interface is at [scanner.deepware.ai](https://scanner.deepware.ai); a mobile companion
extends the same workflow to a phone. Output is a single number
between 0 and 1 with a verdict label ("deepfake detected" / "no
deepfake detected"). The tool is open-source-oriented in that
underlying models and some tooling are public, with commercial APIs
and a low-cost paid tier on top.

The toolkit ships Deepware as the alternative entry in 1A.2
First-Line Triage video alongside InVID-WeVerify (which is
the primary because of its source-history pillar coverage). Deepware
is the press-button option when the user just wants a directional
detector signal in the FLT five-minute window. The video detector
class is structurally constrained: regional research found the best commercial
video detector in the Deepfake-Eval-2024 anonymised pool reaching
only 0.78 accuracy on in-the-wild deepfakes. The Deepware
verdict is treated explicitly as one weak signal under Anchor 1, not
as a verdict.

## When to use it

- A short video clip in your queue needs a fast detector signal
 inside the five-minute first-line window before you decide whether
 to escalate to InVID-WeVerify for a thirty-minute desk
 pass.
- You want a press-button option that requires no install or
 account, accessible on a phone in the field.
- You are running a Tempo or Fact Crescendo SL-style triage workflow
 where the case has already been documented to use Deepware as the
 first detector pass.
- A workshop scenario calls for demonstrating the qualitative
 failure mode (compressed / cropped video flips a deepfake to "no
 deepfake detected") that the WITNESS / Reuters Institute documented
 as a baseline limitation of the video detector class.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** Deepware does not publish a sharp headline
    accuracy figure; inventory records mid-tier accuracy in the
    80-85% range, characterised by Deepware as subject to "constant
    adversarial obsolescence."

    **Independent finding:** WITNESS / Reuters Institute's April 2024
    methodology piece tested public deepfake detectors on known
    examples, including a well-known Obama deepfake. Deepware
    judged a reduced-resolution, edited version of the Obama clip as
    "No Deepfake Detected" – a qualitative robustness failure, not
    a benchmark score. Regional research records this as the principal
    independent observation on Deepware.

    **No independent SEA-specific benchmark identified as of May
    2026.** The WITNESS / Reuters Institute test was an
    example-based audit, not a regional benchmark; no Asian-face or
    SEA-language breakdown is published.

## Limitations

!!! info "Limitations"
    - Mid-tier accuracy in the 80-85% range; detection capabilities
    face constant adversarial obsolescence.
    - Documented to flip to "No Deepfake Detected" on a
    reduced-resolution, edited Obama clip.
    - SEA-platform-compressed-video benchmark missing ;
    WhatsApp, Facebook, and TikTok all transcode video on upload,
    so Deepware verdicts on platform-circulated video carry the
    asymmetric robustness risk.
    - No published per-language or Asian-face breakdown.

## Privacy and threat model

The web scanner uploads the video file to Deepware's cloud
infrastructure for analysis. Deepware is a US-jurisdiction vendor;
treat any upload as a transmission to a US server with the vendor's
retention and disclosure policy applying. For routine triage on
already-public video (a clip already widely circulated on TikTok or
Facebook), the upload is low-risk because the content is already
public.

For source-identifying video, the upload itself is the risk
regardless of the verdict; in surveillance-environment contexts (Sri
Lanka, Lao), classify the source file before any upload. If the file
is source-identifying, route to InVID-WeVerify for
source-history work first (reverse-image, archived versions,
metadata) and skip the detector tab.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying video to Deepware's web scanner
    transmits the file to a US-jurisdiction vendor under that
    vendor's retention policy. Mitigation steps:

    1. Classify the video as public, sensitive, or source-
    identifying before any upload.
    2. For source-identifying material, do not invoke Deepware.
    Use InVID-WeVerify's non-uploading keyframe and
    reverse-image modules for the source-history layer.
    3. If a Deepware verdict is operationally necessary, strip
    identifying context (crop the frame, blur backgrounds,
    remove audio) before uploading the redacted version.
    4. If you uploaded by mistake, request vendor deletion via the
    Deepware support contact and disclose to the source.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    Deepware operates from US jurisdiction; uploads cross into the
    US data-protection regime. Mitigation steps:

    1. Check organisational policy on US-vendor uploads before
    any Deepware call.
    2. Record the vendor's retention statement at the time of
    upload with the case file; vendor terms can change.
    3. Prefer offline or EU-jurisdiction alternatives (InVID's deepfake tab via CERTH for redacted material with
    documented 30-day retention) when the source is in a
    surveillance-risk country.

## Country and platform applicability

- **Indonesia:** documented use by Tempo Cek Fakta on the Dr
 Terawan diabetes-drug deepfake.
- **Laos:** language-agnostic; not benchmarked on Lao-region
 content.
- **Malaysia:** no documented use recorded.
- **Philippines:** no documented Rappler / VERA Files
 deployment recorded; the Philippines pipeline routes through
 Sensity at institutional tier and Hive at
 first-line.
- **Sri Lanka:** documented use by Fact Crescendo Sri Lanka
 on the Dhammika Perera deepfake.
- **Thailand:** no documented use recorded.

Platform applicability: works on any video file regardless of source
platform. The WITNESS / Reuters finding above means the verdict
should be treated as weakly informative for platform-compressed
content (TikTok, Facebook, Facebook Groups, WhatsApp).

## How to access

The web scanner is at [scanner.deepware.ai](https://scanner.deepware.ai). No account is required
for free-tier scanning. A mobile companion extends the same workflow
to a phone. Commercial APIs are documented at the Deepware developer
portal; the paid tier is approximately $8/month .

## Cost (current as of 2026-05)

Free for the public web scanner; commercial APIs available on a paid
basis; the paid tier is roughly $8/month .
Verify directly before any institutional integration as vendor
pricing may have shifted.

## Quickstart

1. Open [scanner.deepware.ai](https://scanner.deepware.ai) in your browser (works on phone or
 desktop).
2. Upload the video file or paste a URL pointing to it.
3. Wait for the analysis; Deepware returns a single probability
 score with a verdict label.
4. Read the score; if the score is high but the file is
 platform-compressed (TikTok, Facebook, WhatsApp), treat the
 verdict as one weak signal and escalate to InVID-WeVerify
 for source-history work.
5. If the score is low and the file is platform-compressed, do NOT
 treat the verdict as exoneration. The WITNESS / Reuters audit
 shows compression flips deepfake verdicts to "no deepfake
 detected" on documented examples.
6. Pair the result with a non-detector signal (reverse-image hit,
 archived earlier instance, provenance manifest) before any
 conclusion.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits in
1A.2 First-Line Triage video as the alternative to InVID-WeVerify. Deepware is the press-button detector option;
InVID-WeVerify is the multi-pillar default.

Standard combinations:

- With **InVID-WeVerify** at 1A.2 / 1B.1 as the
 source-history primary; Deepware gives the detector signal,
 InVID-WeVerify gives the source-history signal. Per Anchor 2 these
 combine as detector + non-detector: two signal classes.
- With **Hive** at 1A.1 cross-cell when the same case has
 both a still image and a video; the two together give parallel
 detector signals counted as one signal class under Anchor 3.
- With **Sensity** at 1C.2 for institutional escalation
 when the case warrants enterprise-grade detection.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector signal
class under Anchor 3 when paired with another detector.

Decision-tree references: [T2 video triage](../decision-trees/t2-video-triage.md) – Deepware is the
press-button branch at T2.10 (video detector run); the WITNESS /
Reuters qualitative failure is documented in the T2 stop-condition
annotations on the same node.

## Conflict resolution behaviour

When Deepware's verdict disagrees with another detector (InVID deepfake tab, Hive on a still frame, Sensity
at institutional tier), Deepware carries lower evidence weight on
platform-compressed video because the WITNESS / Reuters Institute
documented qualitative failure on a known example. On uncompressed
video, Deepware carries roughly equal weight to other detectors at
First-Line Triage tier; the toolkit's editorial position is
that no FLT video detector verdict alone is publishable. When
Deepware disagrees with a non-detector signal (reverse-image hit,
provenance manifest, archived earlier instance), the non-detector
signal wins because Anchor 2 mandates two non-detector signals
before any strong public claim.

## Override notes

!!! note "Override notes"
    - **Weak-signal framing (e4-weak-signal-framing-binding):** the
    workflow section above invokes the detector-as-weak-signal
    sentence per P3 sub-routine; never publish a binary claim from
    Deepware alone. The Limitations admonition carries the WITNESS
    / Reuters qualitative failure verbatim.

    - **Vendor wrapping pair (c1-pair-vendor80-vs-regional research-qualitative-fail):**
    Deepware's 80-85% range vendor figure is paired against the
    WITNESS / Reuters qualitative failure on the reduced-resolution
    Obama clip. Rendered in full in the Independent Accuracy
    admonition above.

    - **Tempo and Fact Crescendo SL deployment (b4-score-2-Tempo-FactCrescendo-SL):**
    regional documented use across Indonesia and Sri Lanka noted in
    the Country and platform applicability section; the deployment
    evidence raises the tool's documented-use score but does not
    override the e4 weak-signal-framing requirement.

## Sources

- Deepware. *Deepware Scanner — deepfake video detection*. Deepware, 2024. [deepware.ai](https://deepware.ai).
- Deepware. *Deepware Scanner — online video scanning tool*. [scanner.deepware.ai](https://scanner.deepware.ai).
- DW Innovation / EU DisinfoLab. *Deepfake Detectors Put to the Test* (methodology review cited in card). DW Innovation, November 2025. [innovation.dw.com](https://innovation.dw.com).
