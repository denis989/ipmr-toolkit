---
tool_id: TOOL-176
slug: mallam-mesolitica
name: MaLLaM (Mesolitica)
maintainer: Mesolitica (Malaysia)
type: non-detector
outline_cells:
 - {id: "2B.3", role: escalation-option, density_role: escalation-option}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [ms]
access: hugging-face | api | self-host
cost: free
documented_country_use: [MY]
tags: [llm, sea-language-nlp, malay, malaysia, mesolitica, hugging-face, foundation-model]
---

# MaLLaM (Mesolitica)

**Vendor:** [mesolitica.com](https://mesolitica.com) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Mesolitica's open-source Malay-specific foundation model
    family, pre-trained from scratch on 90 billion Malaysian-
    context tokens, distributed through Hugging Face under the
    Mistral architecture in 1.1B and 5B parameter sizes. The
    toolkit's escalation-option in 2B.3 for Malaysian work
    where Malay-first verification phrasing matters more than
    broader regional coverage.

## What it does

MaLLaM is a family of open-weight Malay-language foundation
models pre-trained from scratch on a 90-billion-token corpus
of Malaysian text. The current Hugging Face checkpoints are
mallam-1.1B-4096 (1.1 billion parameters, 4096 context length,
most recently updated 2 March 2026) and mallam-5B-4096
(5 billion parameters, updated 28 June 2025), with
instruction-tuned variants for chat-style use. The deliberate
design choice that distinguishes MaLLaM from broader regional
LLMs is "pre-trained from scratch" rather than fine-tuned on
Malay data: the model's representations are tuned to Malaysian
linguistic idiosyncrasies from the ground up rather than
inheriting English-language priors with Malay overlay.

For a fact-check workflow on Malaysian content, the operational
role is Malay-first drafting and reasoning where phrasing,
register, and Malaysian-context fluency matter to the editorial
output. Where SEA-LION is the broader regional default
covering 11 SEA languages including Malay, MaLLaM is the
deeper Malay-specific option. The two are not substitutes;
MaLLaM enters the toolkit as an escalation-option for cases
where the Malay-language quality of the output is itself the
selection criterion.

## When to use it

- A Malaysian newsroom or research lab needs Malay-language
 drafting, summarisation, or reasoning where Malay-first
 fluency matters more than the multi-language coverage
 SEA-LION provides.
- An institutional partner is building a Malaysia-specific
 fact-check pipeline that requires a deeply Malay foundation
 model and acceptable infrastructure overhead for self-host.
- A research project on Malay-language information environments
 needs a documented Malaysian-context-trained foundation
 model with auditable training-data provenance.
- A regional partner pairing a Malaysian deployment with the
 broader-regional SEA-LION primary needs the Malay-specific
 deep option for the cases where SEA-LION's broader-regional
 default does not produce acceptable Malay output.

## Limitations

!!! info "Limitations"
    - Local. MaLLaM is built on Malaysian
    contexts; it is not designed for cross-country regional
    deployment beyond Malay-language work. For
    Bahasa Indonesia (close but distinct linguistic
    environment), Filipino, Thai, Tamil, Sinhala, or Lao
    content the operational paths are SEA-LION
    (regional) and the country-specific 2B.2 entries.
    - LLM hallucination caveat is binding. Like every LLM,
    MaLLaM can produce confident-sounding output that is
    factually wrong. Output is suggestive at best; every
    claim must be verified against an independent source
    before publication.
    - Model size is modest by 2026 LLM standards (1.1B and 5B
    checkpoints). Performance on complex reasoning tasks may
    be more limited than the 27B-parameter SEA-LION v4
    checkpoint; institutional partners should validate
    against their specific use case before broad adoption.
    - Sinhala, Tamil, Lao, Thai, Filipino are not covered;
    MaLLaM is single-language by design.
    - Operational deployment requires Hugging Face
    transformers infrastructure and developer integration;
    not a press-button tool for front-line fact-checkers
    without engineering support.

## Privacy and threat model

The deployment posture is the privacy-defining choice, the
same as for SEA-LION. Run MaLLaM on infrastructure the
operator controls (workstation, on-premise GPU, or operator-
provisioned cloud instance) and the data flow is fully under
the operator's control. No input passes to Mesolitica or any
third party at inference time; the open weights are downloaded
once and run locally.

For Malaysian fact-check work in the regional research operating environment
(CMA Section 233, Online Safety Act 2025 in force from 1
January 2026, 3R speech laws, the *Malaysiakini* January 2025
device-seizure precedent), the locally-deployable LLM path
matters operationally. Institutional partners running MaLLaM on
their own infrastructure can integrate Malay-language drafting
into fact-check workflows without inheriting third-party cloud
LLM threat-model implications.

For Malaysian source handling, the same general discipline
applies: classify the input, route source-identifying material
through human-mediated workflows rather than LLM-mediated
ones, and prefer the institutional civil-society paths
(Meedan Check, regional partner relays) over public-
facing LLM interfaces for sensitive cases.

## Country and platform applicability

Decision 7 framing applies: MaLLaM is an NLP-class tool, and
content-language coverage is the operational selection
criterion. Malay is the documented operational language; the
malay-only-escalation-option flag is the explicit
acknowledgement that this tool covers Malay only and enters
the shortlist as an escalation-option rather than a primary.

- **Indonesia:** not applicable. Bahasa Indonesia is
 linguistically adjacent to Malay but the corpus and tuning
 are Malaysian-context-specific; Indonesian content routes
 through Yudistira (MAFINDO Bahasa-specific) and
 SEA-LION (regional Bahasa support).
- **Laos:** not applicable. Lao is not covered; the
 Lao path in 2B.3 is SEA-LION (which covers Lao
 explicitly per its v4 release documentation).
- **Malaysia:** primary deployment context. Pairs with
 Sebenarnya AIFA at 2B.1 (the Malaysian
 institutional reference, with the documented government-
 operated independence caveat) and with SEA-LION
 at 2B.3 (broader-regional default; MaLLaM is the
 Malaysia-specific escalation-option for Malay-first
 phrasing). Documented use is Malaysian NLP per inventory.
- **Philippines:** not applicable; Filipino / Tagalog
 is not covered.
- **Sri Lanka:** not applicable; Sinhala and Tamil
 are not covered.
- **Thailand:** not applicable; Thai is not covered.

Platform applicability: not platform-specific; MaLLaM is a
foundation model. Its outputs feed whichever editorial workflow
the operator runs at the front-end.

## How to access

Open-source weights on Hugging Face under the Mesolitica
organisation. The current checkpoints are mallam-1.1B-4096
(updated 2 March 2026) and mallam-5B-4096 (updated 28 June
2025), with instruction-tuned variants
(mallam-1.1b-20k-instructions, mallam-1.1b-20k-instructions-v2)
for chat-style use. Mesolitica also publishes a Malay LLM
Leaderboard space on Hugging Face for cross-model comparison
within the Malay-language category.

Deployment is via Hugging Face transformers, Ollama, or other
standard LLM serving infrastructure. For institutional
partners, the GitHub MaLLaM wiki under the malaysia-ai/malaya
project documents architecture and training details; the
Mesolitica organisation page on Hugging Face is the canonical
distribution channel.

## Cost (current as of 2026-05)

Free under the open-source licence. Operational cost is the
operator's compute infrastructure: workstation-class hardware
for the 1.1B variant, more substantial GPU for the 5B variant
in production, plus developer time on integration. The 1.1B
size profile is operationally lighter than SEA-LION's 27B
multimodal variant at the cost of capability; the trade-off
is Malay-specific tuning at smaller model size versus broader
regional coverage at larger scale.

Verify current Hugging Face availability and any change in
licence terms via the Mesolitica organisation page on Hugging
Face directly before integrating.

## Quickstart

(Quickstart for an institutional or developer deployment;
front-line fact-checkers reach MaLLaM through their
institutional partner's deployment.)

1. Confirm the use case is Malay-language editorial drafting
 or reasoning where Malay-first phrasing matters; for
 broader-regional or non-Malay cases route to SEA-LION.
2. Select the MaLLaM variant: mallam-1.1B-4096 for lighter
 deployments, mallam-5B-4096 for cases where the additional
 parameter count justifies the infrastructure overhead, or
 one of the instruction-tuned checkpoints for chat-style
 prompting.
3. Pull the weights from Hugging Face into the operator's
 serving infrastructure (Hugging Face transformers, Ollama,
 vLLM, or other supported runners).
4. Build prompt templates for the specific Malay-language
 editorial tasks: summarisation of Malaysian press, drafting
 of Malay-language clarification questions for a source,
 reasoning over Malaysian-context terminology that broader
 regional models stumble on.
5. Validate output on local Malaysian content before
 integrating into the live editorial workflow; LLM
 hallucination is binding and Malaysian-context-specific
 validation surfaces where the smaller model produces
 confident fabrications.
6. Pair the MaLLaM drafting output with an explicit human
 verification step, the same as for any LLM-mediated tool
 in 2B.3. Every model-drafted claim is verified against an
 independent source before publication.
7. For comparative deployment alongside SEA-LION (institutional
 workflows running both models), build the routing logic so
 Malay-first cases default to MaLLaM and broader-regional or
 non-Malay cases default to SEA-LION, with the operator
 reviewing output quality before settling the routing.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.3 LLMs in fact-check workflows as the
escalation-option for Malay-specific work alongside the
institutional SEA-LION primary, the cloud-LLM
Pinpoint alternative (cross-cell from 2A.1), and the
mobile lay-user AI Fact Checker App alternative.
MaLLaM's place in the cell is depth rather than breadth: when
Malay-language quality matters more than coverage, MaLLaM
escalates from SEA-LION.

Standard combinations:

- With **SEA-LION** at 2B.3 – broader-regional
 default; MaLLaM is the Malay-specific deep option. The two
 cards together illustrate the depth-vs-breadth axis of
 SEA-region LLM choice.
- With **Sebenarnya AIFA** at 2B.1 – Malaysian
 institutional reference (with the documented independence
 caveat). Civil-society and newsroom partners running
 Check-coalition workflows on Malaysian content can deploy
 MaLLaM as the LLM-mediated drafting layer alongside
 observation of AIFA outputs as documentary evidence about
 the Malaysian information environment.
- With **Sinar Project iMAP** at 2C.1 – independent
 network-monitoring layer for Malaysian content, including
 detection of MCMC blocking events on competing outlets per
 regional case documentation. iMAP and MaLLaM are
 complementary parts of the civil-society-operated
 alternative to the government-operated AIFA.
- With **Meedan Alegre** at 2B.2 – multilingual
 matching engine including Malay; pairs with MaLLaM for
 Malay-content tipline workflows where Alegre handles
 duplicate detection and MaLLaM handles editorial drafting.
- With **AI Fact Checker App** at 2B.3 – Malaysian
 app-store localisation at the lay-mobile layer; MaLLaM is
 the institutional self-host alternative for cases where
 the LLM-mediated drafting output is part of a published
 workflow rather than lay triage.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
references MaLLaM at T5.9 (text professional) for Malay-language
LLM-mediated editorial drafting where Malay-first phrasing matters;
broader-regional or cross-language cases default to SEA-LION.

This card carries no detector signal class: MaLLaM produces
non-detector source-history signals (drafted summaries,
candidate questions, translation-assist outputs supporting
human verification). Per Anchor 2 LLM output is suggestive at
best; every claim must be verified against an independent
source before publication, and the verification step is
mandatory rather than discretionary.

## Override notes

!!! note "Override notes"
    - **Malay-only escalation-option
    (malay-only-escalation-option):** MaLLaM enters the 2B.3
    shortlist as the Malay-specific escalation-option rather
    than a regional primary. The card surfaces this in the
    TL;DR, the Limitations admonition, and the Country and
    platform applicability section's Decision 7 framing.
    Cross-country deployment beyond Malay-language work is
    not the design intent and is not the operational use
    the toolkit recommends.

## Sources

- [Mesolitica MaLLaM Hugging Face collection](https://huggingface.co/collections/mesolitica/mallam) (mallam-1.1B-4096 updated 2 March 2026; mallam-5B-4096
 updated 28 June 2025; instruction-tuned variants;
 pre-trained from scratch on 90B Malaysian-context tokens;
 Mistral architecture; 4096 context length)
- [MaLLaM arXiv paper](https://arxiv.org/html/2401.14680v2) (architecture and training details)
