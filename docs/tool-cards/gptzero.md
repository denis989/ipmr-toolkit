---
tool_id: TOOL-043
slug: gptzero
name: GPTZero
maintainer: GPTZero
type: detector
outline_cells:
 - {id: "1B.2", role: primary, density_role: alternative}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [en-optimised]
access: web | browser-ext
cost: freemium
documented_country_use: []
tags: [text, ai-text-detection, esl-bias, cautionary-case]
---

# GPTZero

**Vendor:** [gptzero.me](https://gptzero.me) | **Type:** Detector | **Cost:** Freemium

!!! abstract "TL;DR"
    The most documented AI text detector, and the cautionary case
    the toolkit ships specifically because the failure modes are
    publicly evidenced. Stanford 2023 documented up to 61% false-
    positive rate on non-native English writing; Perkins found 26.4%
    accuracy on non-manipulated AI text and 16.7% on manipulated
    text. Use only as one weak signal; never as standalone
    evidence.

## What it does

GPTZero accepts a text input through a web interface or Chrome
extension and returns an AI-generation probability with sentence-
level highlighting of likely AI passages. The underlying method
evaluates perplexity (how "predictable" the next token is for a
language model) and burstiness (variance in sentence-level
predictability). The tool is one of the most-referenced AI-text
detectors in the journalism and academic literature, and is the
detector with the most published independent evidence, including
evidence that documents its failure modes in detail.

The toolkit's editorial position is explicit. GPTZero ships in 1B.2
as the alternative to Pangram precisely because its
failure modes are publicly documented; using GPTZero in the
toolkit's workflow means using it as a cautionary case, with the
verbatim Stanford and Perkins findings on the card and a binding
weak-signal-framing instruction in the workflow section. A
fact-checker who reaches for GPTZero on a non-native English text
without that framing is, per Anchor 2, taking on a defamation risk
the toolkit considers unacceptable.

## When to use it

- A piece of suspect English text needs a directional read and you
 want the most-documented detector with the most-published
 independent evidence, including the evidence that bounds its
 reliability.
- A workshop demonstrates the cautionary case: GPTZero plus the
 Stanford 61% FPR plus the Perkins 26.4% / 16.7% findings together
 show what the toolkit means by "do not use as standalone
 evidence."
- An academic or research case explicitly wants to test a known
 detector against a controlled input set; GPTZero's documentation
 and benchmark presence make it a defensible test subject.
- A regional case involves text in English; treat any verdict as one
 weak signal class and pair with non-detector verification before
 publication.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** GPTZero markets itself as a "trusted AI
    detector" but does not publish a sharp headline accuracy figure
    that survived the regional research source check.

    **Independent finding (Perkins et al.):** Perkins et al.
    adversarial robustness study found GPTZero extremely weak in
    adversarial settings: 26.4% accuracy on non-manipulated AI
    text and 16.7% on manipulated text. Sample size: 805 detector
    tests / 114 samples.

    **Independent finding (Stanford 2023):** the canonical Stanford
    2023 evidence found up to 61% false positive rate on non-native
    English writing, falsely flagging real human writing by ESL
    authors as AI-generated.

    **Independent finding (2025 essay study):** a 2025 preprint
    found GPTZero usually marked AI essays as highly AI-generated
    but still produced false positives on some human essays (28 AI
    essays + 50 human essays).

    **No robust SEA-language breakdown located** in the regional research search.
    A 2025 summary indicated GPTZero struggled on non-English texts;
    coupled with the Stanford 2023 ESL false-positive finding, the
    SEA-language risk profile is structural.

## Limitations

!!! info "Limitations"
    - 10-20% false positive rate documented for non-native English
    (ESL bias).
    - Stanford 2023 study found up to 61% false positive rate on
    non-native English writing.
    - Limited efficacy on complex Asian languages.
    - Perkins 26.4% accuracy on non-manipulated AI text and 16.7%
    on manipulated text.
    - The text detector class as a whole is unreliable for
    high-stakes use; using GPTZero on a non-native English text
    to support a public claim against a person is, per the
    toolkit's editorial position, a defamation risk.

## Privacy and threat model

GPTZero is a vendor web service; the input text uploads to GPTZero's
cloud infrastructure for analysis. GPTZero is a US-jurisdiction
proprietary vendor; treat any upload as a transmission to a US
server with the vendor's retention and disclosure policy applying.
For text inputs the source-protection risk is lower than for image
or audio (text rarely carries diagnostic background), but
source-identifying language patterns or quoted private communication
should still be considered before upload.

## Country and platform applicability

- **Indonesia:** English-optimised; Bahasa Indonesia
 performance unverified and structurally unreliable per the regional research
 class-level evidence.
- **Laos:** Lao not covered.
- **Malaysia:** English-optimised; Malay performance
 unverified.
- **Philippines:** English-optimised; Filipino performance
 unverified.
- **Sri Lanka:** Sinhala and Tamil not covered.
- **Thailand:** English-optimised; Thai performance
 unverified.

The Stanford 2023 ESL finding has direct regional implications:
much SEA writing in English is by non-native speakers; GPTZero will
falsely flag genuine human writing at materially elevated rates in
all six focus countries when the writer is an ESL author. The
Limitations and Independent accuracy sections name this verbatim.

Platform applicability: works on any text regardless of source
platform.

## How to access

The web interface is at [gptzero.me](https://gptzero.me). Free tier covers 10,000 words
per month; paid tiers from $9.99/month give higher quotas. A Chrome
extension extends the same workflow to any webpage. Account creation
required for higher-volume free-tier or paid use.

## Cost (current as of 2026-05)

Freemium. Free tier: 10,000 words per month. Paid tier from
$9.99/month . Verify pricing directly before any
institutional commitment as vendor pricing may have shifted.

## Quickstart

1. Open [gptzero.me](https://gptzero.me) in your browser.
2. Paste the suspect text into the analysis box, or upload a
 document.
3. Read the AI-generation probability AND the sentence-level
 highlighting; the highlighting is more informative than the
 single-number verdict because it shows where the detector saw
 the strongest signal.
4. If the text is by a non-native English author, treat any
 "AI-generated" verdict as a likely false positive per the
 Stanford 2023 finding; the toolkit's editorial position is that
 you cannot publish from this verdict.
5. Cross-check against Pangram for a second-opinion
 detector signal (counted as one detector signal class with
 GPTZero per Anchor 3, not two).
6. Pair with non-detector verification: ClaimBuster at
 2B.2; Google Fact Check Explorer at 1B.5; the
 productive path for textual cases is the non-detector chain,
 not a second detector pass.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits as
alternative at 1B.2 AI text detection: the most-documented
detector and the clearest cautionary case in the toolkit's text
section.

Standard combinations:

- With **Pangram** at 1B.2 as the primary; the two
 together count as one detector signal class under Anchor 3, not
 two, despite being from different vendors with different design
 philosophies.
- With **ClaimBuster** at 2B.2 – the productive
 non-detector path; if a publishable case exists for the text, it
 comes from the claim-extraction and fact-check-database side,
 not from a stronger detector verdict.
- With **Google Fact Check Explorer** at 1B.5 to look up
 whether the claim has already been fact-checked.
- With **Dissect** at 2B.2 for Sinhala-specific work in
 Sri Lanka where the detector path is structurally inapplicable.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector
signal class under Anchor 3 when paired with another text detector.
The toolkit's editorial position on GPTZero is that the value is
pedagogical: it shows what the AI-text-detector class can and
cannot do, more than it is operational.

The productive cross-reference is to [2B.2 AI claim
extraction](../pillar-2-counter/2b-collaborative.md#2b2-ai-claim-extraction)
as the secondary-signal cell: when a textual case lands and the
question is whether the writing was AI-generated, the publishable
path runs through ClaimBuster, Dissect (Sinhala), Yudistira
(Bahasa), or Alegre (multilingual) alongside the detector reading,
not from the detector reading alone. The 1B.2 verdict travels with
the 2B.2 evidence; on its own it does not carry.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md) –
GPTZero is the alternative cautionary-case AI-text detector option
at T5.9 (text professional), where the framing applies in full: AI-
text detection is only a style flag, never a publishable verdict on
its own. The binding "do not use as standalone evidence" framing
applies at every publish-node check.

## Conflict resolution behaviour

When GPTZero's verdict disagrees with Pangram's verdict on
the same text, GPTZero carries lower evidence weight by default
because Pangram's design philosophy targets false-positive
minimisation while GPTZero has documented high false-positive rates
on non-native English (Stanford 61%); the disagreement is more
likely to indicate a Pangram false negative than a GPTZero true
positive. The toolkit's editorial response is to treat both
verdicts as one detector signal class (Anchor 3), record the
disagreement, and route the case to non-detector verification
(claim extraction, source reliability) before any publication. When
GPTZero disagrees with a non-detector signal (claim already
fact-checked, source confirmed authentic, ESL author identified),
the non-detector signal wins because Anchor 2 mandates two
non-detector signals before any strong public claim.

## Override notes

!!! note "Override notes"
    - **Verbatim Stanford ESL finding (c2-verbatim-Stanford-non-native-FPR):**
    the Limitations admonition carries the Stanford 2023 finding
    verbatim ("up to 61% false positive rate on non-native English
    writing") and the Perkins findings (26.4% accuracy on
    non-manipulated AI text and 16.7% on manipulated text)
    verbatim. The toolkit does not soften these into "performs
    less well on non-native English."

    - **SEA-language disclaimer (b2-disclaimer-pass):** the card
    enters with the "validate before regional use" disclaimer per
    Group B2; SEA-language performance is unverified and the
    Limitations section names the structural risk verbatim.

    - **Weak-signal framing (e4-weak-signal-framing-binding):** the
    workflow section above invokes the detector-as-weak-signal
    sentence per P3 sub-routine; never publish a binary claim
    from GPTZero alone. The Conflict resolution paragraph names
    Pangram as the better-design alternative when both run on the
    same text.

    - **Detector-only caveat:** GPTZero
    serves the cautious-detector pillar only. Every output is a
    detector signal; the card frames the workflow accordingly.

## Sources

- GPTZero. *GPTZero — AI text detection platform*. GPTZero, 2024. [gptzero.me](https://gptzero.me).
- Perkins, M. et al. *Game of Tones: Faculty detection of GPT-4 generated text in university assessments*. Assessment & Evaluation in Higher Education, 2024. [doi.org/10.1080/02602938.2023.2241676](https://doi.org/10.1080/02602938.2023.2241676). (26.4% accuracy on non-manipulated AI text; 16.7% on manipulated text — cited in card)
- Liang, W. et al. *GPT Detectors are Biased Against Non-Native English Writers*. Stanford HAI, 2023. [arxiv.org/abs/2304.02819](https://arxiv.org/abs/2304.02819). (61% false-positive rate on non-native English — cited in card)
