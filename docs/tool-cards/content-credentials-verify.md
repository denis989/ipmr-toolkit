---
tool_id: TOOL-054
slug: content-credentials-verify
name: Content Credentials Verify
maintainer: C2PA / Adobe-led Content Authenticity Initiative (CAI)
type: non-detector
outline_cells:
 - {id: "1A.1", role: primary, density_role: alternative}
 - {id: "1A.4", role: primary, density_role: primary}
pillar_service: [provenance]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-standard
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [provenance, c2pa, watermark, verifier, manifest]
---

# Content Credentials Verify

**Publisher:** [contentcredentials.org/verify](https://contentcredentials.org/verify) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free web portal where you upload a digital asset and inspect its
    embedded C2PA Content Credentials manifest: origin, edit history,
    AI involvement, signer. The toolkit's default first stop for any
    file that might carry provenance metadata.

## What it does

Content Credentials Verify accepts an image, audio file, or video
upload (or a URL pointing to one) and reads the C2PA manifest if the
file carries one. The output is a structured readout of the
manifest: the device or software that created the file, the chain of
edits applied to it, whether AI was involved at creation or in
editing, and the cryptographic signer's identity. When the file
carries a manifest, the verifier returns it cleanly. When the file
does not carry one, the verifier returns a "no Content Credentials
found" result, which is itself a signal, because the file was
either created without C2PA-aware hardware or had its manifest
stripped along the distribution chain.

The portal implements C2PA spec v2.2/v2.3 and is the canonical
end-user verifier for the standard. It is also the toolkit's clearest
worked example of Architectural Anchor 1: the question shifts from
"is this AI-generated?" (a detector frame) to "what does the
provenance metadata say?" (a non-detector frame).

## When to use it

- Any file received that might have been created on Pixel 10, Leica
 M11-P, Sony Alpha, or another C2PA-instrumented device; these
 embed Content Credentials at capture.
- Any file generated through Adobe Firefly, Microsoft Designer, or
 another C2PA-aware tool; these embed Content Credentials at
 generation, including AI-involvement disclosure.
- Before running any detector at 1A.1, run the file through
 Content Credentials Verify first; a hit returns a non-detector
 provenance signal that often resolves the case more cleanly than
 any probability score.
- When training fact-checkers on the difference between detector
 signals and provenance signals; this is the cleanest demo tool.

## Limitations

!!! info "Limitations"
    - Limited adoption globally; nearly zero C2PA-instrumented
    hardware in SEA-popular brands (Realme, Vivo, Oppo, Xiaomi,
    Transsion). Most files reaching SEA fact-checkers will not
    carry Content Credentials at all.
    - Content Credentials are stripped on most SEA distribution
    channels (WhatsApp, Facebook re-uploads, TikTok). Even
    C2PA-instrumented files lose the manifest as they move through
    the platforms most relevant to the toolkit's audience.
    - C2PA encodes creator identity; for source-protection cases the
    creator field of the manifest may itself be a privacy concern.
    - C2PA survival across the SEA hardware base and platform stack is
    not independently documented. The toolkit names this gap explicitly;
    coverage is not implied.

## Privacy and threat model

The portal uploads the file to the C2PA / Adobe-led CAI
infrastructure for manifest reading. The reading process is
non-destructive (the original file is not modified), and the
operation is essentially a metadata query, not a forensic
analysis. For files that already carry Content Credentials, the
manifest content (creator, signer, edit chain) is by design intended
to be readable, so the upload reveals only what the manifest is
designed to expose.

For source-protection cases, the relevant concern is not the upload
itself but whether the manifest's creator field exposes a source's
identity. Strip or pseudonymise creator metadata at the device or
generation step; the verifier is not the mitigation point.

## Country and platform applicability

- **Indonesia:** no documented MAFINDO or CekFakta deployment
 recorded; the value here is per-case rather than per-newsroom
 workflow.
- **Laos:** no documented use; tool is language-agnostic but
 applicable only when files happen to carry C2PA manifests, which
 is rare in the Lao information environment.
- **Malaysia:** no documented use; tool applies in principle.
- **Philippines:** no documented Rappler or VERA Files workflow
 integration recorded; applies per-case.
- **Sri Lanka:** no documented use; tool is
 language-agnostic.
- **Thailand:** Thai PBS used Google Lens for SynthID
 detection on the Anutin Charnvirakul image (Feb 2026), which is a
 parallel provenance path; Content Credentials Verify covers the
 C2PA half of the same provenance pillar.

C2PA-survival-across-SEA-hardware-and-platforms is a documented gap.
The toolkit names this absence explicitly; C2PA coverage across the region is not assumed.

Platform applicability: the tool reads the file regardless of
platform of origin; most SEA distribution platforms (WhatsApp,
Facebook re-upload, TikTok) strip the manifest before the file
reaches the user.

## How to access

The web portal is at [contentcredentials.org/verify](https://contentcredentials.org/verify). No account is
required. The tool is part of the Content Authenticity Initiative's
public verifier infrastructure; the C2PA standard itself is
documented at [c2pa.org](https://c2pa.org).

## Cost (current as of 2026-05)

Free. Open standard governance via the C2PA consortium and the
Adobe-led Content Authenticity Initiative. No paid tier; no quota
for ordinary use.

## Quickstart

1. Open [contentcredentials.org/verify](https://contentcredentials.org/verify) in your browser (works on
 phone or desktop).
2. Drag the file into the upload area, or paste a URL pointing to
 the file.
3. Wait one to three seconds for the manifest read.
4. If the file carries a manifest, read the creator, edit chain, and
 AI-involvement fields; record this as a non-detector provenance
 signal.
5. If the file returns "no Content Credentials found", record that
 absence too; for files that should have carried a manifest
 (generated through a known C2PA-aware tool), the absence may
 itself indicate stripping along the distribution chain.
6. Pair the verifier output with a detector check (Hive)
 for completeness; provenance + detector are two signal classes
 per Anchor 2.

## In the toolkit's workflow

Provenance pillar non-detector tool per Architectural Anchor 1.
Sits as the alternative entry in 1A.1 First-Line Triage image and as
the primary entry in 1A.4 First-Line Triage provenance / watermark.

Standard combinations:

- With **SynthID Detector** at 1A.4 for Google-watermarked
 content; the two together cover the two main provenance ecosystems
 (C2PA across the Adobe / hardware stack; SynthID across the
 Google generation stack).
- With **C2PA Conformance Explorer** at 1A.4 when the
 manifest itself is under question and forensic verification of the
 cryptographic chain is needed.
- With **Hive** or **ImageWhisperer** at 1A.1 as
 the detector half of a detector + provenance pair.
- With **InVID-WeVerify** at 1B.1 when the case escalates
 to a thirty-minute desk pass and the provenance check needs to be
 combined with reverse-image and metadata work.

This card produces a non-detector signal: the manifest readout is a
provenance signal that does not depend on probability scoring. Per
Anchor 2, a manifest hit combined with any detector verdict is two
signal classes; per the toolkit's editorial commitment a publishable
claim usually requires that combination plus one further non-detector
signal (source-history or behaviour).

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – Content Credentials
Verify is the provenance-first branch at T1.2 (C2PA provenance)
before any detector node. [T4 provenance triage](../decision-trees/t4-provenance-triage.md) –
primary entry at T4.2 (manifest type identification).

## Override notes

!!! note "Override notes"
    - **SEA C2PA-survival pointer (sea-c2pa-survival-pointer):** the
    tool's regional value is constrained by the GAP G-019 finding
    that C2PA survival across SEA hardware (Realme, Vivo, Oppo,
    Xiaomi, Transsion) and SEA platforms (WhatsApp, Facebook,
    TikTok) is not independently documented. The Limitations and
    Country and platform applicability sections name this gap
    explicitly rather than implying coverage.

    - **Non-detector declaration:** the
    tool's signal class is non-detector (provenance). Every
    manifest readout is a provenance signal, never a detector
    signal. The card and the workflow section name this
    classification.

## Sources

- Content Authenticity Initiative. *Content Credentials Verify — C2PA manifest inspection tool*. Adobe-led CAI, 2024. [verify.contentauthenticity.org](https://verify.contentauthenticity.org).
- C2PA Technical Working Group. *C2PA Specification v2.2 / v2.3*. Coalition for Content Provenance and Authenticity, 2024–2025. [c2pa.org](https://c2pa.org).
