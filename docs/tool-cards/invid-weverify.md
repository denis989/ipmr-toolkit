---
tool_id: TOOL-022
slug: invid-weverify
name: InVID-WeVerify Verification Plugin
maintainer: AFP Medialab; vera.ai consortium (EU Horizon GA 101070093)
type: mixed-with-declaration
outline_cells:
 - {id: "1A.2", role: primary, density_role: primary}
 - {id: "1B.1", role: primary, density_role: primary}
 - {id: "2A.2", role: primary, density_role: primary}
pillar_service: [provenance, source-history, cautious-detector]
signal_class: mixed-with-declaration
status: active
last_verified: 2026-05-10
license: MIT
languages_ui: [en, fr, es, el, ar, it, de, ja, hu]
languages_content: [agnostic]
access: browser-ext
cost: free
documented_country_use: [PH, TH, ID]
tags: [image, video, audio, reverse-image, geolocation, archiving, metadata, deepfake, voice-clone]
---

# InVID-WeVerify Verification Plugin

**Vendor:** [invid-project.eu](https://invid-project.eu) | **Type:** Detector + non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free Chromium browser extension that bundles reverse-image
    search, video keyframe extraction, EXIF metadata, OCR, image
    forensics, deepfake screening, and Hiya-backed voice-clone
    detection into one plugin used by AFP, Bellingcat, VERA Files,
    and trained fact-checkers across Southeast Asia. The hub of
    Pillar 1B.

## What it does

InVID-WeVerify is a single browser extension that turns a fact-checker's
desk session into a multi-tool forensic pipeline. It accepts URLs,
images, and videos, then returns: keyframes pulled at scene-change
boundaries; reverse-image search results across Google, Bing, Yandex,
Baidu, and TinEye; EXIF and metadata extraction; OCR on text inside
images; basic image-forensics outputs (ELA, copy-move detection); a
deepfake-screening tab that uploads frames to CERTH servers for an
"experimental" probability score; and a voice-clone module that wraps
Hiya for audio classification. It also captures WACZ archives of source
URLs for chain-of-custody preservation.

The plugin is the workhorse of Pillar 1B because its non-detector
modules (reverse-image, archived versions, metadata) usually resolve
the question without the user ever invoking the deepfake tab. Where
the case escalates, the deepfake and voice-clone modules give a
cautious-detector signal that combines per Anchor 3 as one signal
class.

## When to use it

- A WhatsApp-forwarded image or video lands in your queue and you need
 to check whether it has appeared elsewhere online before scoring it
 for AI generation.
- A Tagalog or Bahasa video circulating on Facebook needs keyframe
 extraction and reverse-image cross-checking before you decide
 whether to escalate to enterprise detectors.
- You need WACZ-format archival preservation of a source URL before
 it is removed or edited, with the archive capturing live state plus
 metadata.
- You are running a workshop and want one extension that demonstrates
 the full Pillar 1B verification stack without installing five
 separate tools.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim (deepfake tab):** the deepfake-screening tab is
    documented in the plugin as "experimental" with reported accuracy
    in the 70-90% range that degrades on newer generation methods.

    **Vendor claim (voice-clone module / Hiya):** Hiya's marketing,
    quoted in the DW Innovation audit, promised "free, real-time
    detection, multi-language... detects voices created by all
    popular voice synthesis tools" but did not guarantee complete
    accuracy.

    **Independent finding (Hiya audio module):** the DW Innovation
    civil-society audit (Synthetic Audio Detectors Put to the Test,
    September 2025) tested Hiya on a 10-sample multilingual dataset
    and found it correctly identified 4 of 10 cases, misidentified
    3 of 10, and returned 3 of 10 inconclusive. The audit also noted
    contradictory visualisations within the interface.

    **No independent SEA-specific benchmark identified as of May 2026**
    for the deepfake tab on tonal-language video or
    SEA-platform-compressed footage. The audit's 10-sample test
    covered multiple languages but published no per-language or
    Asian-language breakdown.

## Limitations

!!! info "Limitations"
    - Deepfake tab is documented as "experimental"; reported accuracy
    degrades on new generation methods.
    - Frames uploaded to the deepfake tab go to CERTH servers and are
    retained for 30 days; a privacy concern for source-identifying
    content.
    - Twitter/X features have been broken since the API change.
    - UI is English by default; localisation covers French, Spanish,
    Greek, Arabic, Italian, German, Japanese, and Hungarian, but
    none of the seven SEA languages (Bahasa Indonesia, Lao, Malay,
    Filipino/Tagalog, Sinhala, Tamil, Thai). Trained fact-checkers
    treat the English UI as workable; the gap matters for
    semi-trained volunteers.
    - Voice-clone module wraps Hiya; carries the DW Innovation
    cross-language unreliability finding verbatim.

## Privacy and threat model

The plugin's non-detector modules (reverse-image, EXIF, OCR,
archiving) operate without uploading the source file to InVID-controlled
servers; they query third-party search engines or run locally in the
browser. The deepfake tab is the exception: it uploads video frames
to CERTH (Centre for Research and Technology Hellas, the Greek
research partner in the vera.ai consortium) and retains them for 30
days. The voice-clone module routes audio to Hiya, a US vendor,
under that vendor's retention policy.

For Sri Lanka, Lao, and other surveillance-environment work, classify
the source file before invoking the deepfake or voice-clone tabs. If
the file is source-identifying (a frame containing a recognisable
informant, an audio clip with diagnostic background noise), the
upload itself is the risk, not the verdict that comes back.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying frames or audio to the deepfake or
    voice-clone tabs exposes the source to a third-party server with
    a 30-day retention window (CERTH) or a US-vendor jurisdiction
    (Hiya). Mitigation steps:

    1. Classify the file as public, sensitive, or
    source-identifying before any upload.
    2. For source-identifying material, do not use the deepfake or
    voice-clone tabs. Use the reverse-image, EXIF, OCR, and
    archiving modules instead; these do not upload the source
    file to InVID-controlled servers.
    3. If a deepfake-tab verdict is operationally necessary, strip
    identifying context (crop, blur background, redact audio) on
    the local machine before uploading the redacted version.
    4. If you uploaded by mistake, request CERTH deletion via the
    vera.ai contact channel and note the disclosure to the source.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    The deepfake tab routes uploads to CERTH (EU jurisdiction) with
    a documented 30-day retention window; the voice-clone tab
    routes to Hiya (US jurisdiction) under that vendor's terms.
    This is the toolkit's reference case for cross-border vendor
    retention. Mitigation steps:

    1. Treat the 30-day CERTH window and the Hiya US-vendor regime
    as separate compliance facts; both apply when both tabs are
    used on the same case.
    2. Strip identifying context before any deepfake-tab or
    voice-clone-tab upload, then request CERTH or vendor
    deletion at case close via the documented support channel.
    3. The non-deepfake modules (reverse-image, EXIF, OCR, WACZ
    archiving) do not transit the source file to InVID-controlled
    servers; route source-identifying work through these instead.

## Country and platform applicability

- **Indonesia:** documented use through training and Tempo
 workflow; pairs well with Kalimasada at the
 WhatsApp-intake side.
- **Laos:** plugin operates language-agnostically on visual
 modules; UI is English. Honest gap: deepfake and voice-clone tabs
 are not benchmarked on Lao-language audio or on Lao-region content.
- **Malaysia:** general OSINT use; no documented MAFINDO or
 Sebenarnya pipeline integration recorded .
- **Philippines:** documented heavy reliance at VERA Files
 (Nieman Lab quote); standard for AFP Fact Check Philippines and the
 #FactsFirstPH coalition (regional case documentation).
- **Sri Lanka:** language-agnostic visual modules apply;
 Watchdog and Hashtag Generation use the plugin alongside their own
 Sinhala/Tamil OSINT stack. Honest gap: no SL-specific benchmark for
 the deepfake or voice-clone tabs.
- **Thailand:** AFP training at Chulalongkorn University,
 August 2025; standard for Thai PBS workflow alongside SynthID
 Detector (regional case documentation).

Platform applicability: works on any web-accessible image or video,
relevant across Facebook, Facebook Groups, TikTok, YouTube, Telegram. The X/-x
modules are broken since the API change.

## How to access

Free download from the Chrome Web Store, Microsoft Edge Add-ons, or
the Opera add-on store (search "InVID-WeVerify" or "vera.ai
Verification Plugin"). The repository at AFP-Medialab/verification-plugin
on GitHub publishes source and release notes; v0.87 shipped in July
2025; commits continue through April 2026. Account creation is not
required for core modules; some advanced features (Hiya audio analysis,
DBKF queries) require registration.

## Cost (current as of 2026-05)

Free. The plugin is open-source under MIT licence, funded through the
vera.ai consortium under EU Horizon Grant Agreement 101070093. No paid
tier; no quota for ordinary use. Vendor wraps inside the plugin (Hiya
voice-clone module) operate under those vendors' separate cost
structures, but the plugin itself imposes no fee.

## Quickstart

1. Install the extension from your browser's add-on store.
2. Right-click any image or video on a webpage and choose the
 "InVID-WeVerify" submenu.
3. For an image, run "Image search" first; this fans out reverse-image
 queries to Google, Bing, Yandex, Baidu, and TinEye in one click.
4. For a video, choose "Video → Analysis" to extract keyframes, then
 right-click each keyframe to reverse-image-search it.
5. Use the "Image forensics" tab for ELA and copy-move detection
 (browser-local; no upload).
6. For metadata, choose "Image → Metadata"; this reads EXIF in the
 browser without uploading.
7. Only if non-detector modules are exhausted and the case warrants
 it, classify your file per the danger admonition above and then
 try the "Deepfake" or "Audio analysis" tabs; these upload to
 CERTH or Hiya respectively.
8. Capture a WACZ archive of the source URL via "Archive" before the
 page changes.

## In the toolkit's workflow

Multi-pillar tool: serves provenance (metadata module), source-history
(reverse-image, archiving), and cautious-detector (deepfake and
voice-clone tabs) per Architectural Anchor 1. Sits at the centre of
1B.1 Professional Verification, with cross-cell roles in 1A.2
First-Line Triage video and 2A.2 reverse-image / geolocation.

Standard combinations:

- With **ExifTool** for command-line metadata work on the
 same source file when batch processing is needed.
- With **Sherloq** when the source file cannot leave the
 user's machine (Sri Lanka, Lao surveillance contexts).
- With **Hive AI** at 1A.1 / 1A.3 for a parallel detector
 signal, counted as one detector signal class with the InVID
 deepfake tab per Anchor 3.
- With **Auto Archiver** at 2A.2 for evidence preservation
 beyond the WACZ module's capture.
- With **Meedan Check** at 2B.1 when the same content is
 also being processed through a tipline.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md)
routes to InVID at T1.5 (reverse-image search) and T1.6 (metadata)
as the default first PV step. [T2 video triage](../decision-trees/t2-video-triage.md)
routes to InVID's keyframe extraction at T2.4 and reverse search at
T2.5. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes the deepfake tab through the S1 sub-routine before any upload.

## Conflict resolution behaviour

When the deepfake tab's verdict disagrees with another detector
(Hive, Sensity, Deepware), the InVID tab
carries the lower evidence weight in most cases because (a) the
underlying CERTH model is documented as experimental, with vendor
accuracy in the 70-90% range, and (b) it has not been independently
audited at the level of the Deepfake-Eval-2024 benchmark or the DW
Innovation audit. When it disagrees with a non-detector signal
(reverse-image hit, provenance manifest, archived earlier instance),
the non-detector signal wins because Anchor 2 mandates two
non-detector signals before any strong public claim. The InVID
deepfake verdict alone is never sufficient for a publishable claim.

## Override notes

!!! note "Override notes"
    - **Multi-pillar declaration:** the plugin
    serves provenance, source-history, and cautious-detector
    pillars; the deepfake and voice-clone tabs are explicitly framed
    as cautious-detector with a weak-signal caveat.

    - **Deepfake-tab caveat (c4-deepfake-tab-caveat):** the deepfake
    tab is "experimental" and accuracy degrades on new generation
    methods. Use only after non-detector modules are exhausted and
    treat the verdict as one weak signal.

    - **CERTH 30-day retention mitigation (d4-mitigation-CERTH-30day):**
    the deepfake tab uploads to CERTH for 30 days. Mitigation is
    bound into the danger admonition above (S1 source-protection
    sub-routine).

    - **Safety-before-upload binding (p2-safety-before-upload-binding):**
    pre-upload sensitivity classification is required for the
    deepfake and voice-clone tabs. See the danger admonition above.

## Sources

- AFP Medialab / vera.ai consortium. *InVID-WeVerify Verification Plugin*. AFP Medialab (EU Horizon GA 101070093), 2024–2026. [github.com/AFP-Medialab/verification-plugin](https://github.com/AFP-Medialab/verification-plugin).
- vera.ai consortium. *Vera.ai — verification tools and research*. EU Horizon 2020 project. [invid-project.eu](https://invid-project.eu).
