---
tool_id: TOOL-007
slug: fotoforensics
name: FotoForensics
maintainer: Hacker Factor
type: non-detector
outline_cells:
 - {id: "1B.4", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free-service
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [image-forensics, ela, exif, clone-detection, noise, web]
---

# FotoForensics

**Publisher:** [fotoforensics.com](https://fotoforensics.com) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    The long-standing web-based image forensics service from Hacker
    Factor: Error Level Analysis, EXIF, clone detection, noise
    inconsistency. Globally used in newsroom verification toolkits.
    Carries an explicit cloud-upload caveat for surveillance-risk
    countries: where source identity matters, route to Sherloq instead.

## What it does

FotoForensics accepts an image upload through its web interface and
returns a multi-method forensic readout: Error Level Analysis (ELA),
EXIF / IPTC metadata extraction, clone detection (areas of the image
that appear duplicated), and noise inconsistency analysis (regions
with mismatched noise patterns suggesting compositing). Outputs are
visual (heatmaps and overlays) alongside raw metadata.

The toolkit ships FotoForensics as the alternative at 1B.4 metadata
/ ELA forensics for cloud-acceptable cases. It is included in
virtually every media verification toolkit recommendation globally,
which gives it strong recognition among trained fact-checkers.
What the toolkit changes is the framing: FotoForensics is not the
default for sensitive material, because the upload exposes the
source file to a public web service. For sensitive cases, route to
[Sherloq](sherloq.md) (offline desktop) or to [MetaDataKit](metadatakit.md) (browser-WASM, no upload).

## When to use it

- An image has been classified as public or non-source-identifying
 and you want a fast web-based ELA / clone-detection / noise read
 without installing a desktop forensics application.
- A workshop setting calls for a familiar tool that participants
 will already recognise from prior training; FotoForensics is the
 most-cited image forensics tool in the global toolkits.
- The case requires an ELA visualisation that participants can
 scrutinise inline; FotoForensics's heatmap overlays are
 pedagogically clearer than CLI output.
- The newsroom has confirmed sensitivity classification and a
 partner agreement that the upload is acceptable per the threat
 model.

## Limitations

!!! info "Limitations"
    - Requires interpretive skill; ELA outputs are not
    self-explanatory; readers should know the limits of ELA
    before drawing conclusions.
    - Not specifically AI detection; the methods (ELA, clone, noise)
    pre-date generative AI and detect classical manipulation
    better than they detect contemporary diffusion-model output.
    - Uploads to a public service; this is the operationally
    critical caveat for surveillance-risk material. Hacker
    Factor's terms of service make uploads searchable and
    potentially public.

## Privacy and threat model

FotoForensics uploads the source image to a public web service. The
upload itself is the risk; the service's policy permits public
indexing of uploaded material in some configurations. For
non-source-identifying content already widely circulated, the upload
is low-risk because the content is already public. For
source-identifying content, the upload is a source-exposure vector
regardless of the verdict.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying images to FotoForensics exposes the
    file to a public web service. Mitigation steps:

    1. Classify the image as public, sensitive, or
    source-identifying before any upload.
    2. For source-identifying material, do not use FotoForensics.
    Use [Sherloq](sherloq.md) (offline desktop) or
    [MetaDataKit](metadatakit.md) (browser-WASM, no
    upload) instead.
    3. If a FotoForensics analysis is operationally necessary on
    sensitive material, redact identifying context (crop, blur,
    redact metadata) on the local machine before uploading the
    redacted version.
    4. Document the upload in your case record per
    source-protection practice.

## Country and platform applicability

- **Indonesia:** standard newsroom verification use; not
 specifically documented in the source review.
- **Laos:** the cloud-upload caveat is binding given the
 surveillance environment; route to Sherloq instead for any Lao
 source-sensitive material.
- **Malaysia:** standard verification use applies in
 principle.
- **Philippines:** included in #FactsFirstPH-adjacent
 verification training; not the dominant pipeline tool.
- **Sri Lanka:** the cloud-upload caveat is binding given
 the OSA / PTA surveillance environment; route to Sherloq instead
 for any Sri Lankan source-sensitive material.
- **Thailand:** applies in principle for non-sensitive
 material; given the lèse-majesté legal context, sensitivity
 classification matters before upload.

Platform applicability: works on any image regardless of source
platform.

## How to access

The web interface is at [fotoforensics.com](https://fotoforensics.com). No account is required
for basic analysis. Hacker Factor maintains the service as a free
public resource; usage limits apply to free-tier upload volume.

## Cost (current as of 2026-05)

Free. Hacker Factor sustains the service through donations and
related professional services; no quota that affects ordinary
fact-check use.

## Quickstart

1. Classify the image's sensitivity per the danger admonition above.
2. For source-identifying material, stop here and route to
 [Sherloq](sherloq.md) or [MetaDataKit](metadatakit.md).
3. For non-sensitive material, open [fotoforensics.com](https://fotoforensics.com) in your
 browser.
4. Upload the image (or paste a URL pointing to it).
5. Review the ELA heatmap, EXIF metadata, clone detection, and
 noise analysis in turn; the heatmap overlays are the most
 immediately readable outputs.
6. Cross-check ELA-flagged regions against [ExifTool](exiftool.md) metadata, [InVID-WeVerify](invid-weverify.md) reverse-image search, and
 any provenance manifest the file may carry.
7. Pair the forensic readout with at least one non-detector signal
 from a different signal class (provenance, reverse-image hit, or
 behaviour pattern) before any publication.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural Anchor 1.
Sits as alternative at 1B.4 metadata / ELA forensics; pairs with
[ExifTool](exiftool.md) (CLI metadata) and [Sherloq](sherloq.md) (offline alternative).

Standard combinations:

- With **ExifTool** for parallel CLI metadata extraction –
 ExifTool runs locally, FotoForensics runs in the cloud; the two
 together cover metadata reading at both privacy postures.
- With **Sherloq** as the offline alternative for sensitive
 cases – explicitly NOT in the same case; the two are alternatives
 selected by sensitivity classification, not complements.
- With **InVID-WeVerify** at 1B.1 for source-history
 escalation when FotoForensics surfaces ELA anomalies that warrant
 reverse-image cross-check.
- With **XAI-Deepfakes** at 1C.3 for institutional
 escalation when ELA evidence needs explainable-AI defence.

This card produces a non-detector signal: forensic readouts are
source-history signals (recompression patterns, clone regions,
metadata) that do not depend on probability scoring. Per Anchor 2 a
FotoForensics output combined with a detector verdict is two signal
classes (non-detector + detector).

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md) –
FotoForensics is one of the Professional Verification options at
T5.6 (image professional). [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk) –
explicitly NOT recommended for sensitive material; the routing
diverts to Sherloq (see [Digital Safety](../digital-safety/source-protection-aggregation.md)).

## Override notes

!!! note "Override notes"
    - **Cloud-upload source-exposure caveat
    (c4-cloud-upload-source-exposure-caveat):** the Limitations
    and Privacy admonitions both name the cloud-upload risk
    verbatim; the danger admonition binds the source-protection
    mitigation steps.

    - **Sensitivity classification S1 mitigation
    (d4-mitigation-pass-sensitivity-classification-S1):** the
    mitigation pathway under D4 is the sensitivity-classification
    step in the danger admonition above. For source-sensitive
    material, the mitigation is to NOT use FotoForensics; route
    to Sherloq instead.

## Sources

- Hacker Factor Solutions. *FotoForensics — digital image forensics*. Hacker Factor, 2024. [fotoforensics.com](https://fotoforensics.com).
