---
tool_id: TOOL-STUB-DEEPFAKETOTAL
slug: deepfake-total-stub
name: Deepfake Total
maintainer: third-party (vendor) — see vendor docs
type: detector
outline_cells:
 - {id: "1B.3", role: alternative, density_role: alternative}
pillar_service: [cautious-detector]
signal_class: detector
status: stub
last_verified: 2026-05-10
license: see vendor
languages_ui: [en]
languages_content: [multilingual-claimed]
access: see vendor
cost: see vendor
documented_country_use: []
tags: [audio, deepfake, dw-audit-leader, stub]
---

# Deepfake Total

**Vendor:** Status uncertain as of 2026-05 | **Type:** Detector | **Cost:** Contact vendor

!!! abstract "TL;DR"
    A stub card. Deepfake Total emerged from the DW Innovation
    November 2025 audit (DW Innovation audio detection audit) as the strongest of the three
    audited audio detectors at 7-of-10, but the toolkit's research
    base did not produce an independent deployment evaluation
    sufficient for a full tool card. Use as the audit-leader
    reference; route through DW Innovation audio detection audit for the source audit and
    through Hiya for the press-button SEA option via
    InVID-WeVerify.

## Why this is a stub

This card is deliberately short. The toolkit's editorial position is
that an audio-deepfake-detector card requires (a) verbatim
limitations from independent audit evidence, (b) a Country and
platform applicability section grounded in documented SEA
deployment, and (c) a privacy and threat model section that
addresses cross-border data flow specifically. The toolkit's inventory
supplies (a) through DW Innovation audio detection audit (DW Innovation, November 2025) but
does not supply (b) or (c) at the level the toolkit's reference
cards demand. Rather than improvising the missing material, the
toolkit ships this stub and routes the reader explicitly to the
neighbouring tools that ARE sufficiently documented.

This stub framing is a feature: the toolkit acknowledges limited
inventory coverage transparently rather than padding a card with
inferred content.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** see vendor docs; the inventory does not
    record a sharp vendor headline accuracy figure.

    **Independent finding:** DW Innovation, *Synthetic Audio
    Detectors Put to the Test* (September 2025; the November 2025
    audit referenced as DW Innovation audio detection audit ). Deepfake Total
    correctly identified 7 of 10 cases on the audit's 10-sample
    multilingual dataset: the strongest of the three audited audio
    detectors (Hiya: 4 of 10; DeepFake-O-Meter: model-to-model
    contradictions severe enough to undermine operational use). The
    audit's overall finding is that none of the three audited audio
    detectors "reliably identify AI voices across languages."

## Limitations

!!! info "Limitations"
    - DW Innovation Nov 2025 audit conclusion: tools tested do not
    "reliably identify AI voices across languages".
    - 10-sample dataset gives qualitative ranking, not a
    statistically powered benchmark; no per-language or
    Asian-language breakdown was published.
    - Coverage and access conditions on the vendor side not
    independently documented;
    this is the reason the card is a stub rather than a full
    entry. Verify directly before any operational use.

## How to access: route through

For audio-deepfake-detection work in the toolkit's workflow, route
through the documented neighbours rather than relying on this stub:

- **Press-button SEA option:** [Hiya / Loccus](hiya-loccus.md)
 via the [InVID-WeVerify](invid-weverify.md) voice-clone
 tab. Hiya is the only press-button SEA-accessible audio detector
 in the shortlist; carries the DW Innovation 4-of-10 finding
 verbatim.
- **Institutional escalation:** [TrueMedia.org
 (Georgetown McCourt School)](truemedia-georgetown.md), in closed
 beta as of May 2026; ensemble approach with mission-aligned
 radical-transparency framing.
- **Audit-source reference:** [DW Innovation audio detection
 audit](dw-innovation-audit.md) – the institutional reference that
 anchors the editorial frame for the entire 1B.3 cell.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1; sits in
1B.3 audio deepfake forensics as an alternative on the strength of
the DW audit ranking. The cell is structurally constrained: all
three deployable audio detectors carry detector-as-weak-signal
caveats, and the cell-level honest gap names lao-real-gap-audio,
sinhala-tamil-asymmetric-gap, whatsapp-line-codec-untested, and
detector-class-unreliable-cross-language.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector signal
class under Anchor 3 when paired with Hiya or TrueMedia.

Decision-tree references: [T3 audio triage](../decision-trees/t3-audio-triage.md) – Deepfake Total appears
as the audit-leader pointer at T3.2 (speaker-identity check) feeding
into T3.8 (audio detector run); the binding detector-as-weak-signal
caveat applies at every publish-node check.

## Override notes

!!! note "Override notes"
    - **Stub required (stub-required-from-dw-audit-tool-042):** the
    card ships as a stub because the publicly available documentation does not
    supply the documentation depth a full card needs. The stub
    framing is editorially deliberate and directs the reader to
    [Hiya](hiya-loccus.md), [TrueMedia](truemedia-georgetown.md), and [DW
    audit](dw-innovation-audit.md) for the operational and
    reference paths.

    - **Vendor wrapping pair (c1-pair-vendor-docs-vs-dw-7of10):**
    vendor materials are not summarised here in the absence of
    independent verification; the DW Innovation 7-of-10 finding
    is rendered in full in the Independent Accuracy admonition.

    - **DW broken-across-SEA-languages verbatim
    (dw-audit-broken-sea-languages-verbatim):** the DW conclusion
    is carried verbatim in the Limitations admonition rather than
    softened.

    - **Weak-signal framing (e4-weak-signal-framing-binding):** the
    workflow section above invokes the detector-as-weak-signal
    sentence per P3 sub-routine; never publish a binary claim
    from any audio detector alone, including Deepfake Total.

## Sources

- External: [DW Innovation — *Synthetic Audio Detectors Put to the Test*](https://innovation.dw.com) — November 2025 (Deepfake Total scored 7 of 10 on multilingual audit; vendor presence uncertain as of May 2026; referenced for DW Innovation audit context only)
