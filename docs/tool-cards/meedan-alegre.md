---
tool_id: TOOL-121
slug: meedan-alegre
name: Meedan Alegre
maintainer: Meedan
type: non-detector
outline_cells:
 - {id: "2B.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: Apache-2.0/MIT
languages_ui: [en]
languages_content: [en, id, ms, fil, tha, sin, tam, lao, agnostic]
access: api | self-host
cost: free
documented_country_use: [ID, PH]
tags: [claim-extraction, sea-language-nlp, multilingual, xlm-r, meedan, similarity-matching, docker]
---

# Meedan Alegre

**Operator:** [meedan.com](https://meedan.com) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Open-source text and media similarity service that runs
    multilingual claim-matching using an XLM-R sentence-
    transformer model: the engine that Meedan Check
    runs underneath every tipline. The toolkit's only 2B.2 entry
    that covers all six SEA languages in a single deployable
    model, with a low-resource-language caveat where locally
    tuned tooling exists.

## What it does

Alegre is a Docker-deployable service that accepts text
(and increasingly image and video) inputs and returns
similarity matches against a corpus the operator has indexed.
The matching layer uses xlm_r_bert_base_nli_stsb_mean_tokens (a
multilingual XLM-RoBERTa sentence transformer) together with
indian_sbert for pan-Indian-language coverage and additional
modality-specific models for image and video similarity (the
video-similarity stream was in beta in late 2025). The output
is a similarity score plus the matched item, not a verdict on
truth.

Alegre's structural place in the toolkit is that it is the
claim-matching engine that runs underneath Meedan Check. When a Check tipline receives a forwarded message,
the duplicate detection and claim clustering that lets editorial
staff handle volume is Alegre. Adopting Alegre as a stand-alone
service is the same software in a different deployment posture;
useful when an organisation wants the multilingual similarity
layer without the full Check workspace, or when a research
project needs the matching engine integrated into a custom
pipeline.

## When to use it

- A regional fact-check coalition needs multilingual claim
 matching across Bahasa Indonesia, Filipino, Thai, and other
 SEA languages from a single deployable service rather than a
 per-language tooling stack.
- An institutional research project on cross-language claim
 propagation needs programmatic access to a similarity model
 trained on a multilingual corpus.
- A newsroom partner running its own intake infrastructure
 (not Check) wants to add duplicate detection and clustering
 as a service rather than build the model layer themselves.
- A fact-check operation in a country with a thinner local
 NLP stack (Lao, Sri Lankan Tamil) needs a multilingual
 fallback path while acknowledging the low-resource-language
 performance caveat.

## Limitations

!!! info "Limitations"
    - Issue #11 in the public repo documents work-in-progress
    video similarity; the video-similarity stream was in
    beta in late 2025 and should not be assumed at the same
    production maturity as text similarity.
    - Multilingual XLM-R covers all six SEA languages by
    design, but performance on low-resource languages
    (Lao, Sinhala, Tamil) is structurally weaker than on
    higher-resource languages (Bahasa, Thai, Filipino) and
    should be validated locally before operational use; the
    multilingual fallback is a path, not a guarantee.
    - Indian SBERT covers pan-Indian Tamil rather than
    Sri-Lanka-specific Tamil; the same Sri-Lanka-Tamil
    adaptation gap that applies to X-CLAIM applies
    to Alegre's pan-Indian similarity outputs on Sri Lankan
    Tamil content.
    - Operational deployment requires Docker infrastructure and
    developer integration; not a press-button tool for
    front-line fact-checkers without engineering support.
    - Returns similarity matches, not a verdict on truth; the
    editorial decision (publish, flag, request more
    verification) is a human responsibility downstream.

## Privacy and threat model

Alegre runs as a self-hosted Docker service or as part of a
hosted Check deployment. In the self-hosted case the operator
controls the data flow end-to-end: the corpus the operator
indexes, the queries the operator runs, and the similarity
outputs all sit on the operator's infrastructure. In the
Meedan-hosted case, the data flow is Meedan's standard Check
hosting model; content travels into Meedan-controlled
infrastructure, and the operator's privacy posture sits inside
the Meedan platform's terms.

For surveillance-environment work (Sri Lanka, Lao content
routed via diaspora, Malaysian source handling under the regional research
operating environment), the self-hosted deployment posture is
the operationally appropriate path. Running Alegre on
infrastructure the operator's home jurisdiction allows the
operator to satisfy is part of the same source-protection
discipline that applies to the rest of the 1B.1 tooling
(Sherloq, MetaDataKit).

## Country and platform applicability

Decision 7 framing applies: Alegre is an NLP-class tool, and
content-language coverage is the operational selection
criterion. Alegre's coverage is multilingual via XLM-R: the
single 2B.2 entry that covers all six SEA languages in one
deployable model. The performance asymmetry between
high-resource and low-resource languages is the operational
caveat that goes with that coverage.

- **Indonesia:** documented use as the matching engine
 underneath the CekFakta consortium's Check deployment
 (Meedan Check). Bahasa Indonesia is among XLM-R's stronger
 languages by training-data volume.
- **Laos:** the multilingual XLM-R fallback is the
 operational path for Lao content in 2B.2; Alegre is the
 only entry in this cell that covers Lao at all. The
 performance is low-resource and validation is required
 before trusting the similarity output; the toolkit's Lao
 honest-gap framing applies (G-041) and the supporting Lao
 path remains Google Cloud Translation (2A.1
 cross-link) plus partner-mediated review.
- **Malaysia:** Malay coverage via XLM-R; pairs cleanly
 with MaLLaM (Mesolitica) at 2B.3 for
 Malay-first verification phrasing on Malaysian content.
- **Philippines:** documented use as the matching engine
 underneath the #FactsFirstPH coalition's Check deployment;
 Filipino / Tagalog is supported.
- **Sri Lanka:** Sinhala and Tamil are covered via
 XLM-R as low-resource languages. For Sri-Lanka-specific
 Sinhala work, Dissect with the locally tuned
 LIRNEasia stack is the operational primary; Alegre is the
 multilingual fallback. For Sri Lankan Tamil content,
 Alegre's pan-Indian indian_sbert layer carries the same
 pan-Tamil-vs-Sri-Lanka adaptation gap as X-CLAIM
 (regional research).
- **Thailand:** Thai coverage via XLM-R; pairs with
 Cofact Thailand at 2B.1 when the LINE tipline
 intake feeds into a Check-coalition-shared claim base.

Platform applicability: not platform-specific; Alegre is a
back-end service. Its outputs feed whichever messaging-platform
intake (WhatsApp, LINE, Messenger, Telegram, Viber) the operator
runs at the front-end, typically through a Check tipline.

## How to access

Open-source Apache-2.0 / MIT mixed licence; the codebase is at
the meedan/alegre repository on GitHub. Deployment is via
Docker; the service is run by the operator on infrastructure
they control or as part of a Check hosted deployment under
Meedan's standard partner arrangements.

For organisations adopting Alegre stand-alone, the GitHub repo
is the operational entry point. For organisations adopting it
through Check, Meedan's Check partner pathway brings Alegre
along automatically; the two are not separately licensed.

## Cost (current as of 2026-05)

Free under the open-source licence. Operational cost is
Docker infrastructure, developer time on integration, and any
GPU compute the operator chooses to run for performance on
larger corpora. For Check deployments, Alegre is included in
the Check operational cost structure rather than separately
billed.

## Quickstart

(Quickstart for an operating organisation; Alegre is not a
front-line fact-checker tool.)

1. Clone the meedan/alegre repository from GitHub.
2. Stand up the service via the documented Docker setup;
 verify the multilingual model loads and that text
 similarity returns expected matches on a small test corpus.
3. Index the operator's claim corpus: typically the
 organisation's debunked-claim database or a coalition-
 shared base.
4. Connect Alegre to the operator's intake layer. For Check
 tiplines this is automatic; for stand-alone deployments
 this is API integration into the operator's queue.
5. Tune the similarity threshold for the operator's tolerance
 for false matches versus missed duplicates; thresholds
 that work on Bahasa or Thai may need adjustment for Lao or
 Sinhala due to the low-resource-language performance
 caveat.
6. Validate on local content before trusting the output for
 editorial decisions, especially in low-resource languages
 and for Sri-Lanka-specific Tamil where the pan-Indian
 similarity layer carries the regional research adaptation gap.
7. Pair the matching output with downstream editorial
 workflow (Check, or the operator's custom pipeline) so
 that similarity matches route into a human review queue
 rather than fire automated public responses.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.2 AI claim extraction as the multilingual
alternative to the language-specific entries: Sinhala-strong
Dissect, Bahasa-specific Yudistira, English
baseline ClaimBuster, Tamil pan-Indian X-CLAIM. Cross-cell into 2B.1 is native: Alegre is the
matching engine that runs underneath Meedan Check,
so the 2B.1 Check card and this card describe the same software
in two views (Check at the workspace layer, Alegre at the
matching-engine layer).

Standard combinations:

- With **Meedan Check** at 2B.1 – same maintainer,
 native integration; Check tiplines run Alegre under the
 hood without separate deployment effort.
- With **Kalimasada** at 2B.1 – Kalimasada is
 MAFINDO's WhatsApp deployment of Check; the matching layer
 running Indonesian forwarded WhatsApp content is Alegre.
- With **Dissect** at 2B.2 – Sri-Lanka-specific
 Sinhala primary versus Alegre's multilingual fallback; the
 two cards together illustrate the difference between
 locally tuned and multilingual approaches to Sinhala claim
 extraction.
- With **Yudistira (MAFINDO)** at 2B.2 – Yudistira is
 the MAFINDO Bahasa debunked-claim database that an
 Alegre-powered Indonesian Check tipline queries.
- With **X-CLAIM** at 2B.2 – Alegre's pan-Indian
 indian_sbert layer and X-CLAIM's pan-Indian Tamil baseline
 share the Sri-Lanka-specific Tamil adaptation gap; both
 cards carry the verbatim caveat.
- With **Google Cloud Translation** at 2A.1 – the
 Lao path through 2B.2 is Alegre's multilingual fallback
 paired with Google Cloud Translation routing for the
 English-language editorial layer.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
carries Alegre as the matching layer underneath any Check tipline
node; the response-format paragraph names Alegre as the source of
the canonical claim and verdict reused across tipline replies;
cross-cell routing into 2B.2 stand-alone use is by direct API
access for research and institutional partners.

This card carries no detector signal class: Alegre produces a
non-detector source-history signal (similarity match against
indexed corpus). Per Anchor 2 a similarity match is one signal
class that combines with detector signals from Pillar 1 and with
behaviour signals from CIB tooling at 1C.1 in standard
multi-signal verification workflows.

## Override notes

!!! note "Override notes"
    - **XLM-R multilingual fallback for Lao pointer
    (xlm-r-multilingual-fallback-for-lao-pointer):** Alegre
    is the toolkit's 2B.2 fallback path for Lao-language
    content, paired with Google Cloud Translation
    and partner-mediated review. The fallback is multilingual
    coverage, not Lao-tuned coverage; the Lao honest-gap
    pin (G-041) applies and validation is required before
    trusting similarity output.

## Sources

- Meedan. *Alegre — multilingual text and media similarity service*. Meedan, 2024 (Apache-2.0 / MIT). [github.com/meedan/alegre](https://github.com/meedan/alegre).
- Meedan. *Meedan — technology for fact-checkers and journalists*. [meedan.com](https://meedan.com).
