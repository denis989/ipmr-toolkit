---
tool_id: TOOL-049
slug: pangram-ai
name: Pangram AI
maintainer: Pangram Labs
type: detector
outline_cells:
 - {id: "1B.2", role: primary, density_role: primary}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [multilingual-20+]
access: web | api
cost: freemium
documented_country_use: []
tags: [text, ai-text-detection, multilingual, low-fpr]
---

# Pangram AI

**Vendor:** [pangram.com](https://pangram.com) | **Type:** Detector | **Cost:** Freemium

!!! abstract "TL;DR"
    A vendor AI text detector that markets fine-grained structural
    sentence analysis aimed at minimising false positives, with
    documented support for 20+ languages including Arabic, Chinese,
    French, and Spanish. The toolkit's primary 1B.2 entry. Every entry in this cell is
    a cautionary case, not a recommendation.

## What it does

Pangram accepts a text input and returns an AI-generation
classification through structural sentence-level analysis. The
vendor's design philosophy (articulated in product materials and
in the V2 2026 release) is strict thresholds intended to keep false
positives low; the trade-off is that humanised AI text is more
likely to slip through as a false negative than to be falsely
flagged as machine-generated. For a fact-checker triaging suspect
text under the toolkit's Anchor 2 (no strong public claim from
detector signals alone), the false-positive minimisation is
operationally important: a false positive on a public figure's
genuine writing is a defamation risk in any of the focus countries.

The toolkit ships Pangram as the primary entry in 1B.2 specifically
because of this design discipline. It does NOT ship it because the
AI-text-detector class is reliable; independent evidence is unanimous that
the class is unreliable for high-stakes use across the board, and
the cell-level honest gap names this in full.

## When to use it

- A piece of suspect text needs a directional read; you want a
 vendor that prioritises false-positive minimisation over
 false-negative minimisation.
- A regional case involves text in one of Pangram's supported
 languages and the multi-lingual coverage matters more than
 GPTZero's English-optimised baseline.
- A workshop demonstrates the difference between a strict-threshold
 vendor (Pangram) and a more permissive vendor (GPTZero) on the
 same input.
- An API integration into a newsroom pipeline needs a detector that
 is engineered against false-positive risk; pair the API output
 with non-detector verification (claim extraction at 2B.2,
 source-reliability at 1B.5) before any publication.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** Pangram publicly markets vendor reports 99%+ accuracy; no independent SEA-specific benchmark identified. Coverage across many languages, including Arabic, Chinese, French, and Spanish.

    **No independent SEA-specific benchmark identified as of May
    2026.** independent assessment searches located no peer-reviewed or
    civil-society audit that tested Pangram on tonal, low-resource,
    or SEA-language inputs. The vendor markets multilingual support;
    no independent validation for SEA languages has been published in
    the higher-priority sources searched.

## Limitations

!!! info "Limitations"
    - Strict thresholds miss humanised AI text; false negatives are
    the documented failure mode of the design philosophy.
    - SEA language performance is vendor-claimed but
    independently-untested; treat the 20+ language coverage as
    vendor-claim until independent benchmarks appear.
    - The text detector class as a whole is unreliable for
    high-stakes use per independent benchmark evidence (Turnitin 0.61, Originality 0.69,
    GPTZero 26.4%/16.7%, Copyleaks 73.9% with 50% FP on small
    human-control). Pangram's design choice may shift the
    false-positive / false-negative balance, but does not change
    the class-level reliability ceiling.

## Privacy and threat model

Pangram is a vendor web service; the input text uploads to Pangram's
cloud infrastructure for analysis. Pangram is a US-jurisdiction
proprietary vendor; treat any upload as a transmission to a US
server with the vendor's retention and disclosure policy applying.
For text inputs the source-protection risk is lower than for image
or audio (text rarely carries diagnostic background), but
source-identifying language patterns or quoted private communication
should still be considered before upload.

## Country and platform applicability

- **Indonesia:** Bahasa Indonesia is plausibly within the 20+
 language coverage; not independently verified for Bahasa.
- **Laos:** Lao is unlikely to be in the supported set; no
 independent verification.
- **Malaysia:** Malay is plausibly within the 20+ language
 coverage; not independently verified for Malay.
- **Philippines:** Filipino / Tagalog is plausibly within the
 20+ language coverage; not independently verified for Filipino.
- **Sri Lanka:** Sinhala and Tamil coverage is unverified;
 no independent benchmark exists.
- **Thailand:** Thai is plausibly within the 20+ language
 coverage; not independently verified for Thai.

The toolkit's editorial position is that the multi-language vendor
claim does not substitute for independent SEA-specific benchmarking;
the Limitations section names this gap explicitly; coverage is not implied.

Platform applicability: works on any text regardless of source
platform.

## How to access

The web interface is at [pangram.com](https://pangram.com) (basic free tier); API access
documented at the developer portal. Account creation required for
API access and for higher-volume free-tier use.

## Cost (current as of 2026-05)

Free basic tier sufficient for low-volume triage; Premium tier paid
on a per-seat or per-volume basis. Verify pricing directly before
any institutional integration as vendor pricing may have shifted
since the inventory was last reviewed.

## Quickstart

1. Open [pangram.com](https://pangram.com) in your browser.
2. Paste the suspect text into the analysis box.
3. Read the AI-generation classification; treat the result as one
 weak signal class per Anchor 1.
4. If the classification is "AI-generated" with high confidence on a
 text in a SEA language, do NOT publish a binary claim from this
 alone; the SEA-language performance is vendor-claimed but
 independently-untested.
5. Cross-check against GPTZero for a second-opinion
 detector signal (counted as one detector signal class with
 Pangram per Anchor 3, not two).
6. Pair with non-detector verification: ClaimBuster or
 Dissect at 2B.2 for claim extraction; Google
 Fact Check Explorer at 1B.5 for source-reliability cross-check.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits as
primary at 1B.2 AI text detection. The cell is structurally thin
because the detector class is unreliable; Pangram's primary slot
reflects design discipline (low FPR), not class reliability.

Standard combinations:

- With **GPTZero** at 1B.2 as the alternative; the two
 together count as one detector signal class under Anchor 3, not
 two.
- With **ClaimBuster** at 2B.2 for non-detector claim
 extraction – the productive pair for textual cases per the cell-
 level bridging note.
- With **Google Fact Check Explorer** at 1B.5 for
 source-reliability and existing-fact-check cross-check.
- With **Dissect** at 2B.2 for Sinhala-specific claim
 extraction when the case is in Sri Lanka.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector signal
class under Anchor 3 when paired with another text detector.

The productive cross-reference is to [2B.2 AI claim
extraction](../pillar-2-counter/2b-collaborative.md#2b2-ai-claim-extraction)
as the secondary-signal cell: when a tipline-routed text claim
reaches the desk, a Pangram verdict sits beside ClaimBuster
extraction, Yudistira (Bahasa) or Dissect (Sinhala) clustering, and
Alegre's multilingual fallback. The detector reading travels with
those non-detector signals, never apart from them.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md) –
Pangram is the primary AI-text detector option at T5.9 (text
professional), where T5.9's framing applies in full: AI-text
detection is only a style flag, never a publishable verdict on its
own. The binding "do not use as standalone evidence" framing
applies at every publish-node check across T1, T2, and T3.

## Conflict resolution behaviour

When Pangram's verdict disagrees with GPTZero's verdict on
the same text, neither carries decisive evidence weight on its own;
the class-level evidence is that the AI-text-detector category
is unreliable for high-stakes use across the board. The toolkit's
editorial response to such disagreements is to treat both verdicts
as one detector signal class (Anchor 3), record the disagreement,
and route the case to non-detector verification (claim extraction,
source reliability, fact-check database hit) before any publication.
When Pangram disagrees with a non-detector signal (claim already
fact-checked elsewhere, source confirmed authentic), the
non-detector signal wins because Anchor 2 mandates two non-detector
signals before any strong public claim.

## Override notes

!!! note "Override notes"
    - **Vendor wrapping pair (c1-pair-vendor99-no-indep):** Pangram's
    99%+ vendor claim is paired against the explicit "no
    independent SEA-specific benchmark identified" sentence in the
    Independent Accuracy admonition. The pair is honest; the
    vendor headline travels with the gap acknowledgement.

    - **SEA-language disclaimer (b2-disclaimer-pass-no-SEA-indep):**
    the Limitations admonition records that 20+ language coverage
    is vendor-claimed and SEA-language performance is
    independently-untested. The card enters with the
    "validate before regional use" disclaimer.

    - **Weak-signal framing (e4-weak-signal-framing-required):** the
    workflow section above invokes the detector-as-weak-signal
    sentence per P3 sub-routine; never publish a binary claim from
    Pangram alone.

    - **Detector-only caveat (g1-detector-only-caveat):** Pangram
    serves the cautious-detector pillar only. Every output is a
    detector signal; the card frames the workflow accordingly.

## Sources

- Pangram Labs. *Pangram AI — AI text detection with low false-positive design*. Pangram Labs, 2026 (V2). [pangram.com](https://pangram.com).
- Note: No independent SEA-language benchmark identified as of May 2026 for Pangram AI. Per editorial discipline, vendor self-claim wrapped with explicit field-context. See [editorial patterns](../methodology/editorial-patterns.md) for vendor wrapping pattern.
