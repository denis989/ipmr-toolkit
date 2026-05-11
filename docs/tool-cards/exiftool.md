---
tool_id: TOOL-008
slug: exiftool
name: ExifTool
maintainer: Phil Harvey
type: non-detector
outline_cells:
 - {id: "1B.1", role: primary, density_role: alternative}
 - {id: "1B.4", role: primary, density_role: primary}
pillar_service: [source-history, provenance]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source-perl
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [metadata, exif, iptc, xmp, gps, cli, batch]
---

# ExifTool

**Publisher:** [exiftool.org](https://exiftool.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    The command-line standard for reading, writing, and editing
    metadata across 400+ file types. Bellingcat-standard part of any
    OSINT desk; the toolkit's primary 1B.4 metadata-forensics entry
    and an alternative at 1B.1 multi-tool plugins.

## What it does

ExifTool, written and continuously updated by Phil Harvey, is the
canonical command-line utility for media metadata work. It reads
EXIF, IPTC, XMP, GPS, and many proprietary metadata formats from
400+ file types: JPEG, RAW, video containers, PDF, audio formats,
and more. It also writes and edits metadata, supports batch
operations across directories, and produces structured output
(JSON, CSV, tab-delimited) suitable for downstream pipelines.

For a fact-checker, ExifTool is the default first step in any
metadata investigation: extract camera model, capture timestamps,
GPS coordinates if present, embedded thumbnails, software-edit
chain, and any C2PA Content Credentials manifest the file may carry.
Output is text; the user reads it. The discipline of the tool is
that it does not interpret; it surfaces what is there. Spoofability
of metadata is a feature of the format, not a limitation of the
tool, and the card carries that caveat verbatim.

## When to use it

- A still image lands in your queue and you want to read its full
 metadata before deciding on detector or source-history work.
- A batch of media files needs metadata extraction in one pass for
 a coordination-pattern investigation (1C.1) or a source-history
 audit.
- A scripted pipeline needs structured metadata output (JSON / CSV)
 to feed into a downstream verification or archival workflow.
- You are training fact-checkers on the difference between
 reading metadata (ExifTool) and trusting metadata (the spoofable
 caveat below).

## Limitations

!!! info "Limitations"
    - Metadata is easily spoofed; readings require secondary
    corroboration before any inference about the file's history is
    drawn.
    - Metadata is frequently stripped by social media platforms;
    WhatsApp, Facebook, TikTok, Instagram all transcode and strip
    metadata on upload, so most files reaching SEA fact-checkers
    will return thin or empty metadata.
    - Requires CLI proficiency; not a press-button option for
    First-Line Triage volunteers. The tier
    mapping is therefore Professional Verification and
    Institutional, not FLT.

## Privacy and threat model

ExifTool is a local command-line tool; it operates on files on the
user's own machine and does not upload anything to remote servers.
This is its core privacy posture and the reason it is the
preferred metadata reader for surveillance-environment work
(Sri Lanka, Lao). The user retains full control of the source file
throughout the operation; metadata extraction does not trigger any
network call.

The risk surface is the user's own environment: if the machine is
compromised, ExifTool's output is too. For institutional chain-of-
custody work, run ExifTool from a hardened analyst workstation and
hash the source file before and after extraction to demonstrate
non-destructive reading.

## Country and platform applicability

- **Indonesia:** standard OSINT use; not specifically
 documented in the source review but applies across MAFINDO
 / CekFakta verification work.
- **Laos:** offline operation; well-suited to surveillance-
 environment threat model where uploads are themselves a risk.
- **Malaysia:** standard OSINT use; applies in principle.
- **Philippines:** Bellingcat-standard tool; applies across
 Rappler and VERA Files investigative work; not specifically named
 in the source review.
- **Sri Lanka:** offline operation matters here for the
 same surveillance-environment reasons as Laos; pairs with Sherloq for ELA work on the same source files (regional case documentation;
 Sri Lanka, surveillance-environment caveat).
- **Thailand:** standard OSINT use; applies in principle.

Platform applicability: works on any file regardless of source
platform. The "stripped by social media" caveat applies; most
files acquired from Facebook, Facebook Groups, TikTok, WhatsApp will return thin
metadata.

## How to access

Download from [exiftool.org](https://exiftool.org). Phil Harvey maintains binary releases
for Windows, macOS (universal), and Linux source builds. Package
managers carry it: `apt install libimage-exiftool-perl`, `brew install
exiftool`. No account, no licence key.

## Cost (current as of 2026-05)

Free. Open-source under the same licence as Perl. Continuously
updated by Phil Harvey across decades; no paid tier; no quota.

## Quickstart

1. Install ExifTool via `brew install exiftool` (macOS), `apt install
 libimage-exiftool-perl` (Debian/Ubuntu), or the Windows
 installer from [exiftool.org](https://exiftool.org).
2. Open a terminal and navigate to the directory containing the file.
3. Run `exiftool filename.jpg` to dump all metadata fields to the
 terminal.
4. Run `exiftool -G -j filename.jpg > metadata.json` to write
 grouped, JSON-structured output for downstream use.
5. For batch work, run `exiftool -r -ext jpg -j./directory/ >
 metadata.json` to recursively process every JPEG in the
 directory.
6. To check for C2PA Content Credentials, run `exiftool -ContentCredentials
 filename.jpg` (newer ExifTool versions include C2PA-aware
 tags).
7. Hash the source file before and after with `shasum -a 256
 filename.jpg` if chain-of-custody documentation matters.

## In the toolkit's workflow

Source-history and provenance pillar non-detector tool per
Architectural Anchor 1. Sits as alternative at 1B.1 multi-tool
plugins (ExifTool is the CLI standard alongside the
browser-extension primaries) and as primary at 1B.4 metadata / ELA
forensics (where command-line metadata work is the core
methodology).

Standard combinations:

- With **InVID-WeVerify** at 1B.1 – InVID gives the
 browser-extension default; ExifTool gives the CLI batch capability
 for the same metadata layer.
- With **Sherloq** at 1B.1 / 1B.4 – Sherloq provides the
 GUI ELA layer; ExifTool provides the metadata layer; together they
 cover the full local-forensics stack without uploading the source
 file.
- With **MetaDataKit** at 1B.1 – MetaDataKit is the
 browser-WASM alternative for users who do not have CLI
 proficiency.
- With **FotoForensics** at 1B.4 – only when sensitivity
 classification clears web upload; ExifTool runs first locally as
 the no-risk metadata read.
- With **CIB Mango Tree** at 1C.1 – ExifTool's batch
 output feeds Mango Tree's coordination-pattern detection on
 metadata-derived signals (capture timestamps, GPS clusters).

This card produces a non-detector signal: extracted metadata is a
source-history / provenance signal that does not depend on
probability scoring. Per Anchor 2, a metadata reading combined with
a detector verdict is two signal classes (non-detector +
detector); per the toolkit's editorial commitment a publishable
claim usually requires that combination plus one further signal
(typically reverse-image hit at 2A.2 or behaviour pattern at 1C.1 /
2C.1).

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – ExifTool is the
metadata-extract branch at T1.6 (metadata step) when the case
escalates from FLT to PV. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk) –
ExifTool is the no-upload default for sensitive cases (see [Digital Safety](../digital-safety/source-protection-aggregation.md)).

## Override notes

!!! note "Override notes"
    - **Metadata-spoofable caveat (c2-metadata-spoofable-caveat):**
    ExifTool reads metadata as it is; the format is spoofable, so
    the Limitations admonition carries the spoofability caveat
    verbatim. The card frames ExifTool's output as a
    requires-corroboration signal, not as standalone evidence.

    - **Non-detector declaration:** the
    tool's signal class is non-detector (source-history /
    provenance). Every metadata reading is a source-history or
    provenance signal, never a detector signal. The card and the
    workflow section name this classification.

## Sources

- Harvey, P. *ExifTool by Phil Harvey — reading, writing, editing metadata*. Phil Harvey, 2024. [exiftool.org](https://exiftool.org).
