---
tool_id: TOOL-042
slug: dw-innovation-audit
name: DW Innovation audio detection audit
maintainer: DW Innovation (Deutsche Welle), with EU DisinfoLab
type: reference
outline_cells:
 - {id: "1B.3", role: secondary, density_role: alternative}
pillar_service: [cautious-detector]
signal_class: non-detector
status: reference
last_verified: 2026-05-10
license: public
languages_ui: [en]
languages_content: [methodology-agnostic]
access: web
cost: free
documented_country_use: []
tags: [audit, audio-detection-evidence, institutional-reference, eu-disinfolab]
---

# DW Innovation audio detection audit

**Publisher:** [innovation.dw.com](https://innovation.dw.com) | **Type:** Reference framework | **Cost:** Free

!!! abstract "TL;DR"
    The November 2025 DW Innovation audit testing Hiya, Deepfake
    Total, and DeepFake-O-Meter, published in collaboration with EU
    DisinfoLab. Anchors the editorial frame for the toolkit's entire
    1B.3 cell. The conclusion: none of the three reliably identify
    AI voices across languages.

## Why this is a reference card, not a tool card

This is an institutional reference, not a deployable tool. The audit
is the binding evidence base for the toolkit's framing of the audio
detector class: every claim the toolkit makes about audio detector
unreliability across SEA languages traces back to this audit. The
card exists to give the audit an addressable citation point inside
the toolkit so that other tool cards (Hiya,
TOOL-STUB-DEEPFAKETOTAL, TrueMedia) can refer to it
unambiguously and so that decision trees (T3 Audio triage) can cite
it as the editorial anchor.

## What the audit found

The DW Innovation audit, published September / November 2025 with EU
DisinfoLab, tested three publicly accessible audio deepfake detectors
on a 10-sample multilingual dataset built from fully synthetic,
partially synthetic, and natural audio across multiple languages,
male and female voices, and varying lengths and formats. Headline
findings:

- **Deepfake Total:** 7 of 10 cases correctly identified;
 strongest of the three.
- **Hiya:** 4 of 10 correctly identified, 3 of 10 misidentified, 3
 of 10 inconclusive; the audit also noted contradictory
 visualisations within the Hiya interface.
- **DeepFake-O-Meter:** model-to-model contradictions severe enough
 to undermine operational use.

The overall conclusion: none of the three audited audio detectors
"reliably identify AI voices across languages."

The audit's 10-sample dataset is multilingual but does not publish a
per-language, Asian-language, or tonal-language breakdown. There is
still essentially no public independent evidence on tonal-language
performance, including the kinds of audio environments relevant to
Southeast Asia.

## How the toolkit uses the audit

The audit is the binding citation source for:

- The TL;DR framing on every audio detector card in 1B.3: the
 detector-as-weak-signal sentence is anchored in the DW conclusion.
- The C1 wrapping pair on [Hiya](hiya-loccus.md) (4-of-10
 finding) and on [TOOL-STUB-DEEPFAKETOTAL Deepfake Total](deepfake-total-stub.md) (7-of-10 finding).
- The C2 verbatim limitation on every audio detector card: "do not
 reliably identify AI voices across languages."
- The cell-level honest-gap statements at 1A.3 First-Line Triage
 audio and 1B.3 Professional Verification audio: lao-real-gap-audio
 (G-042), sinhala-tamil-asymmetric-gap (regional research),
 whatsapp-line-codec-untested (G-017), detector-class-unreliable-
 cross-language.
- The [T3 audio triage](../decision-trees/t3-audio-triage.md)
 stop-condition that prevents publication of any binary AI-audio
 claim from a single detector verdict.

## Limitations of the audit itself

!!! info "Limitations"
    - 10-sample dataset gives qualitative ranking, not a
    statistically powered benchmark.
    - Multilingual coverage but no per-language or Asian-language
    breakdown published; tonal-language performance specifically
    remains untested in any public independent evaluation.
    - Audit, not a deployable detector; the card is reference-only
    and does not enter operational workflow as a tool.

## How to access

The DW Innovation report is published at the DW Innovation site;
EU DisinfoLab also indexes the audit through its AI Disinfo Hub
(see [AI Disinfo Hub (EU DisinfoLab)](ai-disinfo-hub.md)).

## Cost (current as of 2026-05)

Free. Public report. EU DisinfoLab and DW Innovation are non-profit
institutional publishers.

## In the toolkit's workflow

Reference, not tool. Sits at 1B.3 audio deepfake forensics as the
secondary entry that anchors the cell's editorial frame. Every
deployable audio detector card in the cell ([Hiya / Loccus](hiya-loccus.md),
[TOOL-STUB-DEEPFAKETOTAL](deepfake-total-stub.md),
[TrueMedia.org (Georgetown McCourt School)](truemedia-georgetown.md)) cross-references this card for
the binding audit evidence.

Decision-tree references: [T3 audio triage](../decision-trees/t3-audio-triage.md) – DW audit is the
stop-condition citation at every publish-node check, named in the
T3.8 (audio detector run) framing.

## Override notes

!!! note "Override notes"
    - **Reference-not-tool declaration:**
    this card is a reference, not a deployable tool. The Sources
    section and the cross-references above route the reader to the
    operational neighbours.

## Sources

- DW Innovation / EU DisinfoLab. *Deepfake Detectors Put to the Test: An Evaluation of Three AI-Powered Audio Detection Tools*. DW Innovation, November 2025. [innovation.dw.com](https://innovation.dw.com); indexed at [disinfolab.eu/ai-disinfo-hub/](https://disinfolab.eu/ai-disinfo-hub/).
- [AI Disinfo Hub](ai-disinfo-hub.md) (EU DisinfoLab indexer)
