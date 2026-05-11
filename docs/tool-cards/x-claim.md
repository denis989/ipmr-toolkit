---
tool_id: TOOL-113
slug: x-claim
name: X-CLAIM
maintainer: MBZUAI NLP (academic)
type: non-detector
outline_cells:
 - {id: "2B.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: academic
languages_ui: [en]
languages_content: [en, hi, pa, tam, te, bn]
access: api | python
cost: free
documented_country_use: []
tags: [claim-extraction, sea-language-nlp, tamil, pan-indian, mbzuai, emnlp, sri-lanka-adaptation-gap]
---

# X-CLAIM

**Operator:** [github.com/mbzuai-nlp/X-CLAIM](https://github.com/mbzuai-nlp/X-CLAIM) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Academic 7,000-claim multilingual dataset and baseline
    models (mBERT / mDeBERTa / XLM-R) for claim-span
    identification across English, Hindi, Punjabi, Tamil,
    Telugu, and Bengali: the toolkit's available Tamil entry
    in 2B.2. Pan-Indian by training-data composition; for Sri
    Lankan Tamil content the tool is operationally usable but
    the training data does not cover Sri-Lanka-specific named
    entities or communal-memory politics, and that adaptation
    gap is the binding caveat.

## What it does

X-CLAIM is the dataset and accompanying baseline models from
MBZUAI's NLP group, published at EMNLP 2023 main conference.
The dataset contains 7,000 real-world claims across six
languages (English, Hindi, Punjabi, Tamil, Telugu, Bengali),
annotated for claim-span identification (which spans of a
sentence are factual claims that warrant fact-check
attention). The baseline models (multilingual BERT, mDeBERTa,
XLM-R) provide a starting point for downstream Tamil-language
claim-extraction work.

The tool's structural place in the toolkit is the Tamil-
language entry point in 2B.2. The cell needs Tamil coverage
because Sri Lanka is a focus country and Tamil is one of its
two main local languages. X-CLAIM is the most documented
Tamil-capable academic baseline ; it is not a
Sri-Lanka-specific tool. The claim-span identification task
the dataset trains is exactly the structural decomposition
work a fact-checker needs at the front end of a verification
workflow on Tamil content.

## When to use it

- A Sri Lankan fact-check team or a regional partner needs
 Tamil-language claim-span extraction as a baseline starting
 point and accepts that local adaptation will be required
 for Sri-Lanka-specific content.
- A research group is building Tamil-language fact-check NLP
 capacity and needs a documented EMNLP-published dataset and
 baseline models as the academic substrate for their work.
- A pan-South-Asian project is processing Tamil content from
 multiple jurisdictions and X-CLAIM's pan-Indian-plus-Sri-
 Lanka-applicability framing fits the input distribution.
- A trainer is teaching Tamil-language claim-extraction concepts
 in a workshop setting and needs an academic reference point
 with a published dataset.

## Limitations

!!! info "Limitations"
    - Indian-language-centred. The 7,000-claim
    dataset is built from pan-Indian sources rather than Sri
    Lanka-specific Tamil discourse; the baseline models
    reflect that training data.
    - Sri Lanka-specific Tamil adaptation gap. LIRNEasia research records that
    most Tamil-specific resources useful for Sri Lankan
    monitoring come from Indian or pan-Tamil ecosystems
    rather than Sri Lanka-specific ones, including the
    training data X-CLAIM is built on. Pan-Indian Tamil
    training data does not cover Sri Lankan named entities,
    Sri Lankan political actors, or Sri Lankan communal-
    memory politics with the depth a Sri-Lanka-specific
    tool would. Sri Lankan Tamil workflows therefore need
    more human review, more source-list curation, and more
    care with named entities, dialectal nuance, and
    communal memory politics than the bare X-CLAIM output
    provides (Synthesis section C).
    - Academic baseline rather than productionised tool.
    Operational deployment requires Python NLP capacity and
    developer integration; X-CLAIM is not a press-button
    web tool for front-line fact-checkers.
    - No Sri Lankan deployment of X-CLAIM is documented in the
    source set; institutional adoption would be the operator's
    first documented use rather than building on a documented
    Sri Lankan precedent.
    - Languages outside the EMNLP six (Bahasa Indonesia, Malay,
    Filipino / Tagalog, Thai, Sinhala, Lao) are not covered.

## Privacy and threat model

X-CLAIM is an academic dataset and baseline-model release.
Operational use means downloading the dataset and code and
running it on the operator's own infrastructure, typically
Python with the Hugging Face transformers stack. There is no
hosted service to which a user submits claims; the data flow
is fully under the operator's control.

For Sri Lanka deployment the threat-model dimension that
matters is the broader operating environment documented in the [Sri Lanka country page](../countries/sri-lanka.md).
Sri Lanka's Online Safety Act 2024 establishes broad state
powers; institutional partners running Tamil-language NLP work
on politically sensitive content should pair the technical
deployment with the same source-protection discipline that
applies elsewhere in the toolkit (Sherloq for offline
forensics at 1B.1, the Sri Lanka country page's surveillance-
environment framing). For research-publication outputs that
identify or characterise specific Tamil discourse patterns,
standard institutional research-publication ethics apply —
named-entity exposure in published research can have
operational consequences in a tense communal-political
environment.

## Country and platform applicability

Decision 7 framing applies: X-CLAIM is an NLP-class tool, and
content-language coverage is the operational selection
criterion. Tamil is the documented operational language; the
b2-pass-Tamil-pan-Tamil-not-SL-adapted flag is the explicit
acknowledgement that this tool enters the shortlist with the
pan-Indian-not-Sri-Lanka-adapted caveat.

- **Indonesia:** not applicable. Bahasa Indonesia is not
 among X-CLAIM's six languages; Indonesian content routes
 through Yudistira and Alegre.
- **Laos:** not applicable. Lao is not covered; the
 2B.2 Lao gap is structural across all NLP-class entries in
 this cell. The Lao path remains Google Cloud
 Translation routing (2A.1 cross-link) plus partner-mediated
 review.
- **Malaysia:** not applicable as a primary tool. Malay
 is not in the X-CLAIM language set; Malaysian Tamil content
 in principle could route to X-CLAIM, but the documented use
 is pan-Indian Tamil rather than Malaysian Tamil, so the same
 adaptation-gap framing applies. Malaysian content routes
 through Alegre and MaLLaM.
- **Philippines:** not applicable; Filipino / Tagalog is
 not covered.
- **Sri Lanka:** the available Tamil tool, with the
 pan-Indian adaptation gap as the binding caveat. For Sri
 Lankan Tamil content X-CLAIM is the documented option in
 the 2B.2 shortlist, but its training data is pan-Indian;
 Sri-Lanka-specific named entities, Sri Lankan political
 actors, and Sri Lankan communal-memory politics may not be
 captured. The pairing of X-CLAIM's pan-Indian framing with
 Dissect's Sinhala asymmetric-strong framing (Dissect (Watchdog Sri Lanka / LIRNEasia)) is
 the toolkit's honest closure of the Decision 7 Sinhala-Tamil
 parity question per LIRNEasia research: Sri Lanka's Sinhala stack is more
 locally coherent (LIRNEasia MisinformationCorpusSinhala,
 University of Moratuwa SinLlama, SLTK tokenizer) while Sri
 Lankan Tamil tooling leans on pan-Indian resources with
 the adaptation gap visible.
- **Thailand:** not applicable; Thai is not covered.

Platform applicability: not platform-specific; X-CLAIM is a
dataset and baseline-model release, deployable as Python NLP
infrastructure. Its outputs feed whichever editorial workflow
the operator runs at the front-end.

## How to access

Free under the academic licence; the dataset and baseline
models are distributed through standard academic NLP channels
(MBZUAI NLP, Hugging Face, the EMNLP 2023 publication's
documented release path). Operational use requires Python
infrastructure and the Hugging Face transformers stack;
institutional partners considering integration should clone the
public release and follow the documented training and
inference scripts. There is no hosted X-CLAIM service.

## Cost (current as of 2026-05)

Free under the academic open licence. Operational cost is
infrastructure (the operator's compute for inference, GPU if
fine-tuning) and developer time on integration. For Sri-Lanka-
specific adaptation, the cost is primarily the human work of
curating Sri Lankan Tamil training data (the locally specific
material the pan-Indian X-CLAIM corpus does not carry) and
fine-tuning the baseline on that material.

## Quickstart

(Quickstart for an institutional research or developer
deployment; X-CLAIM is not a press-button tool.)

1. Confirm the content is Tamil and that the Sri-Lanka-specific
 adaptation gap is acceptable for the use case, or that
 adaptation work is in scope.
2. Clone the X-CLAIM dataset and baseline-model release through
 MBZUAI NLP / Hugging Face channels.
3. Stand up a Python environment with the Hugging Face
 transformers stack; load the chosen baseline (mBERT,
 mDeBERTa, or XLM-R) and the dataset.
4. For research-baseline use, run the published evaluation
 scripts on Tamil to reproduce the EMNLP results before
 trusting the tool on new content.
5. For Sri-Lanka-specific adaptation, curate Sri Lankan Tamil
 training material (Hashtag Generation, Watchdog, Fact
 Crescendo SL, FactSeeker Tamil archives are the candidate
 sources) and fine-tune the baseline on the local data.
6. Integrate the inference layer into the operator's editorial
 workflow with explicit human review on every output: a
 high-confidence claim-span flag is a starting point for
 verification, not evidence the claim is suspect.
7. Pair the deployment with Sherloq at 1B.1 for any
 image / video material accompanying the Tamil-language text
 (the Sri Lankan surveillance-environment threat model
 documented in the Sri Lanka country page).

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.2 AI claim extraction as the Tamil entry
alongside the Sri-Lanka-specific Dissect (Sinhala),
the multilingual Alegre, the Bahasa-specific Yudistira, and the English baseline ClaimBuster. The
asymmetric framing (Dissect Sinhala-strong via the LIRNEasia
stack, X-CLAIM Tamil pan-Indian with adaptation gap) is the
honest account of Sri Lanka's Sinhala / Tamil tooling
asymmetry per LIRNEasia research rather than a single multilingual entry that
would mask the gap.

Standard combinations:

- With **Dissect** at 2B.2 – Sinhala primary; Tamil
 alternative. The two cards together close the Sri Lankan
 Sinhala / Tamil shortlist with the asymmetry visible.
- With **Meedan Alegre** at 2B.2 – Alegre's
 indian_sbert layer carries the same pan-Indian-Tamil training
 inheritance as X-CLAIM; both cards carry the verbatim
 Sri-Lanka-Tamil adaptation caveat. Operationally, Alegre is
 the multilingual back-end of a tipline; X-CLAIM is the
 research-baseline dataset and model. They are complementary
 rather than substitutable.
- With **Sherloq** at 1B.1 – for offline image /
 video forensics on Tamil-language content in the Sri Lankan
 surveillance-environment threat model.
- With **AI Disinfo Hub** at 1B.5 – institutional
 knowledge layer including the EU DisinfoLab "King of slop"
 Sri Lanka coverage; a cross-reference for the broader
 research environment X-CLAIM-based work fits inside.
- With **Google Cloud Translation** at 2A.1 – for
 routing Tamil-language outputs into English-language
 editorial layers and for partner-mediated cross-country
 review.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
names X-CLAIM as the Philippines `-ph` tipline tool of record
(VERA Files / X-CLAIM coalition); [T5 escalation](../decision-trees/t5-escalation.md)
at T5.9 (text professional) routes Sri Lankan Tamil-language claim
triage to X-CLAIM with the verbatim adaptation-gap caveat applied,
and cross-cell escalation into 1B.5 source-reliability scoring and
2C.1 automated claim monitoring is the standard pipeline for
institutional Tamil-language work.

This card carries no detector signal class: X-CLAIM produces a
non-detector source-history signal (claim-span identification
on the input text). Per Anchor 2 the claim-span output is one
signal class supporting human verification; the verification
work that follows is the next signal class in the editorial
workflow.

## Override notes

!!! note "Override notes"
    - **Tamil real-gap Sri-Lanka-specific
    (tamil-real-gap-sri-lanka-specific):** the verbatim caveat
    from LIRNEasia research, surfaced in the Limitations admonition and the
    Country and platform applicability section: pan-Indian
    Tamil training data does not cover Sri Lankan named
    entities, Sri Lankan political actors, or Sri Lankan
    communal-memory politics with the depth a Sri-Lanka-
    specific tool would. The card does not soften this; the
    pairing with Dissect is the toolkit's honest
    closure of the Sinhala / Tamil parity question.

    - **Pan-Tamil pass with not-SL-adapted disclaimer
    (b2-pass-Tamil-pan-Tamil-not-SL-adapted):** X-CLAIM
    enters the 2B.2 shortlist on Tamil-language coverage
    with the pan-Indian-not-Sri-Lanka-adapted disclaimer
    explicit in the card text. The disclaimer is part of
    the selection record, not a footnote.

## Sources

- MBZUAI NLP Group. *X-CLAIM — multilingual claim extraction model*. Mohamed bin Zayed University of AI, 2023 (EMNLP 2023 main; academic licence). [github.com/mbzuai-nlp/X-CLAIM](https://github.com/mbzuai-nlp/X-CLAIM).
- Guo, M. et al. *X-CLAIM: Automated Check-worthy Claim Detection across Languages*. EMNLP 2023. [aclanthology.org/2023.emnlp-main.1028](https://aclanthology.org/2023.emnlp-main.1028).
