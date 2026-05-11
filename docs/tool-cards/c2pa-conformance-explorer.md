---
tool_id: TOOL-055
slug: c2pa-conformance-explorer
name: C2PA Conformance Explorer
maintainer: Content Authenticity Initiative (CAI) / C2PA
type: non-detector
outline_cells:
 - {id: "1A.4", role: primary, density_role: alternative}
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
tags: [provenance, c2pa, cryptographic-attestation, chain-of-custody]
---

# C2PA Conformance Explorer

**Publisher:** [c2pa.org](https://c2pa.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    The C2PA forensic verifier: checks the cryptographic
    attestations in a Content Credentials manifest to establish an
    unbroken chain of custody. Reach for it when the manifest itself
    is in question, beyond what Content Credentials Verify
    surfaces at the end-user level.

## What it does

The C2PA Conformance Explorer accepts a media file with a Content
Credentials manifest and runs the cryptographic verification chain:
checking that the signer's certificate is valid, that the manifest
hash matches the file content, that each step in the edit chain is
properly signed, and that the chain has not been broken or
re-signed. The output is an attestation verification result with the
specific point of failure named when verification breaks.

This is the forensic complement to Content Credentials
Verify. Content Credentials Verify reads the manifest content (creator, edit chain, AI
involvement) for end-user inspection; the Conformance Explorer
verifies that the manifest is cryptographically intact. Same standard
(C2PA), different layer of question: Content Credentials Verify answers "what does the
manifest say?", the Conformance Explorer answers "is the manifest
trustworthy?".

## When to use it

- A file carries a Content Credentials manifest that Content Credentials Verify
 surfaced, but the manifest claims a chain of edits that look
 inconsistent with the visual content; you need cryptographic
 verification before treating the manifest as authoritative.
- A photojournalism desk is integrating C2PA-bearing assets into a
 publication pipeline and needs forensic verification of the
 provenance chain at the desk-side rather than at the end-user
 reader side.
- A workshop scenario calls for demonstrating the difference
 between manifest-content reading and manifest-cryptographic-
 verification; the Conformance Explorer is the cleanest demo of
 the latter.
- A CSIRT or institutional partner is investigating a possible
 manifest spoof and needs the conformance-level diagnostic.

## Limitations

!!! info "Limitations"
    - Ineffective if the original device or software did not embed
    C2PA in the first place.
    - Vulnerable to screenshot stripping; a screenshot of a
    C2PA-bearing file loses the manifest entirely, and the
    Conformance Explorer has nothing to verify.
    - Limited adoption in SEA; same hardware-and-platform constraints
    apply as for Content Credentials Verify (most files
    reaching SEA fact-checkers will not carry a C2PA manifest at
    all).
    - Verification is binary at the attestation level (pass or fail);
    a fail does not always tell the user why a manifest is broken
    without expert reading of the diagnostic output.

## Privacy and threat model

The Explorer uploads the file to the CAI infrastructure for
verification. Verification is non-destructive; the file is not
modified. The cryptographic chain check exposes only the manifest
metadata that the manifest itself was designed to expose, plus the
diagnostic of where the chain failed if it did.

For source-protection cases the same caveat as for Content Credentials Verify applies:
the manifest's creator field may itself be a privacy concern; strip
or pseudonymise creator metadata at the device or generation step.

## Country and platform applicability

- **Indonesia:** no documented use; tool applies in principle
 for any C2PA-bearing file.
- **Laos:** no documented use.
- **Malaysia:** no documented use.
- **Philippines:** no documented Rappler / VERA Files
 deployment recorded.
- **Sri Lanka:** no documented use.
- **Thailand:** no documented Thai PBS or Cofact deployment
 recorded; SynthID is the regional provenance entry of record.

Same regional-coverage constraint as Content Credentials Verify: the C2PA ecosystem is
embryonic across the focus countries.
The toolkit names this gap explicitly; broader applicability is not implied.

Platform applicability: works on any C2PA-bearing file regardless of
source platform; most SEA distribution channels strip the manifest
before the file reaches the user.

## How to access

The Conformance Explorer is at [opensource.contentauthenticity.org/](https://opensource.contentauthenticity.org)
and linked validator endpoints maintained by the CAI. No account is
required for basic conformance checks. The C2PA standard itself is
documented at [c2pa.org](https://c2pa.org); the open-source verification libraries are
on the Content Authenticity Initiative's GitHub.

## Cost (current as of 2026-05)

Free. Open standard governance via the C2PA consortium and the
Adobe-led Content Authenticity Initiative.

## Quickstart

1. Open the Conformance Explorer at the CAI's open-source verifier
 page.
2. Upload the C2PA-bearing media file.
3. Read the attestation verification result; note pass or fail and
 the specific diagnostic if the chain failed.
4. If verification passes, treat the manifest content surfaced by
 Content Credentials Verify as cryptographically
 trustworthy.
5. If verification fails, the manifest may have been tampered with
 or improperly re-signed; route to Content Credentials Verify for the human-readable
 manifest content and document the failure point in your
 verification record.
6. For institutional integration, the open-source libraries on the
 CAI GitHub allow self-hosted conformance checking inside a
 newsroom pipeline.

## In the toolkit's workflow

Provenance pillar non-detector tool per Architectural Anchor 1. Sits
in 1A.4 First-Line Triage provenance / watermark as the alternative
to Content Credentials Verify and SynthID
Detector. The Conformance Explorer's role is forensic: it is the
escalation when the manifest itself needs verification beyond
end-user reading.

Standard combinations:

- With **Content Credentials Verify** as the human-readable
 manifest reader; the Conformance Explorer adds the cryptographic
 verification layer.
- With **SynthID Detector** when both Google-stack
 provenance (SynthID) and C2PA provenance need to be checked on
 different files in the same case.
- With **ExifTool** at 1B.1 / 1B.4 when classical metadata
 also matters alongside the C2PA manifest.

This card produces a non-detector signal: the cryptographic
verification result is a provenance-trust signal that does not
depend on probability scoring. Per Anchor 2, a Conformance Explorer
pass combined with a Content Credentials Verify manifest readout is one provenance
signal class (the pass strengthens the trust value of the readout,
but they are layers of the same provenance signal, not two distinct
signal classes).

Decision-tree references: [T4 provenance triage](../decision-trees/t4-provenance-triage.md) – Conformance Explorer
is the manifest-chain integrity check at T4.3.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** the
    tool's signal class is non-detector (provenance-trust). Every
    verification result is a provenance signal, never a detector
    signal. The card and the workflow section name this
    classification.

## Sources

- Content Authenticity Initiative. *C2PA Conformance Explorer*. Adobe-led CAI, 2024. [CAI open-source tools](https://opensource.contentauthenticity.org).
- C2PA Technical Working Group. *C2PA Specification v2.2 / v2.3*. Coalition for Content Provenance and Authenticity, 2024–2025. [c2pa.org](https://c2pa.org).
