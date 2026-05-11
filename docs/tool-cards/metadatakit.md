---
tool_id: TOOL-200
slug: metadatakit
name: MetaDataKit
maintainer: Independent (Journalist's Toolbox)
type: non-detector
outline_cells:
 - {id: "1B.1", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: public
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [metadata, browser-wasm, local-processing, source-protection]
---

# MetaDataKit

**Publisher:** [metadatakit.com](https://metadatakit.com) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A WebAssembly-driven browser tool for analysing, editing, and
    removing metadata locally; the file never leaves the browser
    sandbox. Bridges the gap between the CLI rigour of ExifTool and the press-button friction-free experience users
    expect on the web.

## What it does

MetaDataKit accepts a media file dropped into a webpage and runs the
metadata read, edit, or strip operation entirely inside the browser
through WebAssembly. The file does not upload to a remote server;
the JavaScript / WASM runtime handles parsing on the user's own
machine, then surfaces the metadata fields, allows edits or strips,
and offers the modified file back to the user as a download.

For source-protection workflows this is operationally important: the
tool delivers the user-experience benefits of a web tool (no install,
no CLI, no account) without the privacy cost of a cloud upload. The
toolkit ships MetaDataKit as the alternative at 1B.1 specifically for
users who need to read or strip metadata on a sensitive file but
cannot or will not learn ExifTool's CLI.

## When to use it

- A sensitive image needs metadata stripped before publication or
 before being shared with a partner; the user wants to do this in
 the browser rather than installing CLI tools.
- A workshop demonstrates the difference between cloud-by-default
 (upload) and local-by-default (WASM) metadata reading; MetaDataKit
 is the cleanest demonstration of the WASM-local approach.
- A fact-check team without CLI proficiency needs metadata extraction
 on routine images and chooses MetaDataKit over installing ExifTool
 on every workstation.
- Source-protection work in any of the surveillance-aware focus
 countries calls for a no-upload metadata path that is faster to
 use than Sherloq's full desktop GUI.

## Limitations

!!! info "Limitations"
    - Requires uncompressed file; if the input is heavily compressed
    or has had its metadata already stripped along the distribution
    chain, the tool returns thin output.
    - Browser-WASM operation depends on the user keeping the
    browser-tab session open; long-running batch operations are
    not its strength (use ExifTool for batch).
    - Single-purpose; for ELA, JPEG-ghost, or PRNU forensics, route
    to Sherloq (offline desktop) or FotoForensics
    (cloud, sensitivity-cleared only).
    - Documented case base is thin (B4 score 1); the tool's
    inclusion rests on its privacy posture, not on regional
    deployment evidence.

## Privacy and threat model

MetaDataKit's WebAssembly runtime processes the file inside the
browser's own sandbox. No HTTP upload of the file content occurs;
verify this in the browser's network panel before trusting the
operation in a sensitive case. The tool therefore behaves much like
Sherloq in terms of data flow: the source file does not
leave the user's machine. The difference is that the runtime is
the browser rather than a desktop application.

For maximally sensitive cases (named informant material, content
identifying a source's location), Sherloq remains the more
defensible choice because the offline desktop reduces the attack
surface further (no browser-side scripts, no third-party dependencies
loaded at page render). MetaDataKit is the right tool when the user
needs the no-upload property without the install friction of Sherloq.

## Country and platform applicability

- **Indonesia:** applies in principle; no documented
 newsroom-pipeline integration recorded.
- **Laos:** the no-upload property aligns with the
 surveillance-environment threat model; usable wherever browser
 access is workable.
- **Malaysia:** applies in principle.
- **Philippines:** no documented Rappler / VERA Files
 deployment recorded.
- **Sri Lanka:** the no-upload property aligns with the
 surveillance-environment threat model; alternative to Sherloq for users who prefer browser to desktop application.
- **Thailand:** applies in principle.

Platform applicability: works on any media file regardless of source
platform.

## How to access

The MetaDataKit web interface is published through the Journalist's
Toolbox catalogue. Search [journaliststoolbox.org](https://www.journaliststoolbox.org) for "MetaDataKit"
to locate the current URL; verify before use. The tool is published as a free
public resource. No account; no install.

## Cost (current as of 2026-05)

Free. Public licence; no paid tier.

## Quickstart

1. Open the MetaDataKit web page in your browser.
2. Verify in the browser's network panel that no upload of the file
 content occurs when you drop the file in (this is the operational
 guarantee that makes the tool source-protection-safe).
3. Drag the media file into the upload area.
4. Read the metadata fields in the resulting display.
5. To strip metadata before sharing, choose the strip operation
 and download the cleaned file.
6. To verify the strip worked, run the cleaned file through the tool
 a second time, or through ExifTool, and confirm the
 metadata is empty.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural Anchor 1.
Sits as alternative at 1B.1 multi-tool plugins, specifically chosen
for users who need the no-upload property without the install
friction of Sherloq.

Standard combinations:

- With **ExifTool** as the CLI alternative – same
 no-upload guarantee, more powerful for batch and scripting work,
 but with CLI friction.
- With **Sherloq** as the desktop alternative – same
 no-upload guarantee with extended ELA / JPEG-ghost / PRNU
 forensics, but with desktop install friction.
- With **InVID-WeVerify** at 1B.1 / 2A.2 only when the case
 is not source-sensitive; for sensitive cases, MetaDataKit replaces
 the InVID metadata layer, not supplements it.
- With **Content Credentials Verify** at 1A.4 – both are
 browser-based provenance / metadata tools; CCV reads C2PA
 manifests, MetaDataKit reads classical EXIF / IPTC / XMP.

This card produces a non-detector signal: extracted metadata is a
source-history signal that does not depend on probability scoring.
Per Anchor 2 the same combinatorics apply as for ExifTool.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – MetaDataKit is the
no-CLI metadata branch at T1.6 (metadata step) for sensitive cases.

## Override notes

!!! note "Override notes"
    - **Local WASM operation (d4-pass-local-WASM):** the tool runs
    entirely in the browser's WebAssembly sandbox; no upload of
    file content occurs. This is its core privacy posture and is
    named in the Privacy and threat model section as the
    operational property that makes MetaDataKit the no-CLI
    no-upload option.

## Sources

- External: [MetaDataKit](https://metadatakit.com) (browser-WASM tool published via Journalist's Toolbox catalogue; local-processing, no upload)
