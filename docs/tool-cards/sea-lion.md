---
tool_id: TOOL-174
slug: sea-lion
name: SEA-LION
maintainer: AI Singapore
type: non-detector
outline_cells:
 - {id: "2B.3", role: primary, density_role: primary}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [id, ms, fil, tha, tam, lao, my, km, vi, en, zh]
access: api | self-host | hugging-face
cost: free
documented_country_use: []
tags: [llm, sea-language-nlp, ai-singapore, multilingual, multimodal, hugging-face, foundation-model]
---

# SEA-LION

**Publisher:** [aisingapore.org](https://aisingapore.org/aiproducts/sea-lion/) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Open-source multilingual and multimodal foundation model
    family from AI Singapore, with v4 (March 2026) covering
    Bahasa Indonesia, Burmese, Khmer, Lao, Malay, Mandarin,
    Tagalog, Tamil, Thai, Vietnamese, and English. The toolkit's
    primary 2B.3 entry because it is the regional LLM IPMR
    newsrooms can plausibly run in their own infrastructure,
    and the only LLM in the shortlist with explicit Lao
    coverage.

## What it does

SEA-LION is a family of foundation models (text and, with the
v4 release, multimodal text-plus-image) published by AI
Singapore under open-source licences and distributed through
Hugging Face. The v4 release in March 2026 added multimodal
input, expanded the language coverage, and brought the family
to a size profile that runs on workstation hardware rather than
exclusively on cloud GPU clusters; the Gemma-SEA-LION-v4-27B-IT
variant on Hugging Face is the most-deployed checkpoint in the
v4 family.

For a fact-check workflow the operational role is LLM-mediated
review: drafting a structured summary of a long Bahasa or Thai
press article before reporter time goes into verification,
generating candidate questions to ask a Tamil-language source,
producing an English-language briefing of a Lao-language clip
that was passed through a transcription tool first. The
multilingual coverage is what makes SEA-LION useful in places
where a global LLM either lacks the language or routes
sensitive content to a US or European cloud provider.

The structural difference between SEA-LION and Pinpoint at 2B.3 is the deployment posture. SEA-LION is the
regional foundation model that an institutional partner can
plausibly run in their own infrastructure: open weights on
Hugging Face, runs on workstation hardware in the v4 size band,
SEA-language coverage built in. Pinpoint is the cloud-LLM
journalist-pipeline path on Google's infrastructure with the
mitigation-pass caveat. Both belong in 2B.3; they answer
different operational questions.

## When to use it

- A regional newsroom or research lab needs an LLM-mediated
 drafting layer in Bahasa Indonesia, Filipino, Thai, Malay,
 Tamil, Khmer, or Lao without routing the content through a
 US or European cloud provider.
- An institutional partner is building a fact-check workflow
 with hallucination-mitigated drafting at the front end and
 needs a foundation model they can run locally with auditable
 prompts and outputs.
- A research project on regional information environments needs
 a multilingual summarisation, translation-assist, or
 question-generation layer that covers SEA languages with
 documented training-data curation.
- A partner working on Lao content needs the only LLM in the
 toolkit's 2B.3 shortlist that covers Lao explicitly; the
 alternative paths for Lao (Google Cloud Translation
 for translation, partner-mediated review for editorial
 judgement) do not provide LLM-mediated drafting.

## Limitations

!!! info "Limitations"
    - Requires advanced developer integration.
    SEA-LION is not a press-button web tool; deployment
    requires Python infrastructure, Hugging Face transformers
    stack, and either workstation-class hardware or cloud
    GPU. Front-line fact-checkers will reach SEA-LION through
    institutional partner deployments rather than direct use.
    - LLM hallucination caveat is binding. Like every LLM,
    SEA-LION can produce confident-sounding output that is
    factually wrong: fabricated sources, invented dates,
    misattributed quotations. Output is suggestive at best;
    every claim drafted by the model must be verified
    against an independent source before publication.
    - Sinhala is absent from the SEA-LION language list.
    Sri-Lanka-Sinhala work in the 2B.3 layer reaches outside
    this card to the SinLlama lineage documented in LIRNEasia research
    (University of Moratuwa Sinhala-specific LLM,
    continually pre-trained on a cleaned ten-million-sentence
    Sinhala corpus); SEA-LION is not the right tool for
    Sinhala content.
    - Multilingual coverage is explicit but performance varies
    across languages. High-resource SEA languages (Bahasa,
    Thai, Vietnamese) have stronger documented behaviour
    than low-resource languages (Lao, Khmer); validation on
    local content before trusting the output is the
    operator's responsibility.
    - Multimodal v4 release is recent (March 2026); operational
    maturity on the multimodal pathway is younger than on the
    text-only pathway. Institutional partners adopting the
    multimodal capabilities should treat the deployment as
    early-stage rather than production-stable.

## Privacy and threat model

The deployment posture is the privacy-defining choice. Run
SEA-LION on infrastructure the operator controls (a
workstation, an on-premise GPU server, or a cloud instance the
operator has provisioned in a jurisdiction they can satisfy)
and the data flow is fully under the operator's control. No
input passes to AI Singapore or any third party at inference
time; the open weights are downloaded once and run locally.

That posture matters for surveillance-environment work and for
source handling. Sri Lankan content under the Online Safety
Act 2024 environment, Lao content from inside the country, Thai
content under the Computer Crime Act / lèse-majesté
context, Malaysian content under the CMA Section 233 / Online
Safety Act 2025 environment all benefit from the
locally-deployable LLM path. Institutional partners running
SEA-LION on their own infrastructure can integrate it into
fact-check workflows without inheriting the threat-model
implications of third-party cloud LLMs.

For lay-user-facing deployments (pointing a citizen to an
LLM-mediated tool), SEA-LION itself is not the front-end; the
operator builds an interface on top. The same source-protection
discipline that applies to other parts of the toolkit applies:
classify the input, route source-identifying material away from
public-facing LLM interfaces, and prefer human-mediated review
where the threat model warrants.

## Country and platform applicability

Decision 7 framing applies: SEA-LION is an NLP-class tool, and
content-language coverage is the operational selection
criterion. SEA-LION v4 covers Bahasa Indonesia, Burmese,
Khmer, Lao, Malay, Mandarin, Tagalog, Tamil, Thai, Vietnamese,
and English (verified via SEA-LION v4 release documentation,
March 2026). Sinhala is not covered and the SinLlama lineage
documented in LIRNEasia research is the cross-reference pointer.

- **Indonesia:** Bahasa Indonesia coverage; the
 high-resource SEA-LION language by training-data volume.
 Pairs cleanly with Yudistira at 2B.2 for matching
 against the MAFINDO debunked-claim corpus and with
 Kalimasada at 2B.1 as the LLM-mediated drafting
 layer behind the tipline editorial workflow.
- **Laos:** SEA-LION v4 covers Lao explicitly. This is
 the only LLM in the toolkit's 2B.3 shortlist with
 documented Lao support, which makes SEA-LION the
 operational answer to the Lao 2B.3 question; it is one of three
 cells in 2B where Lao would otherwise be a structural gap.
 The other two 2B Lao gaps remain real: 2B.1 has no
 Lao-language tipline (G-041) and 2B.2 has no Lao-language
 claim-extraction tool, with the supporting path running
 through Google Cloud Translation. SEA-LION's Lao
 coverage closes the 2B.3 hole partially; institutional
 partners running SEA-LION locally can do LLM-mediated
 Lao-language drafting, with the broader Lao operational
 workflow (diaspora review, partner-mediated editorial,
 Sherloq for any image work at 1B.1) still required around it.
- **Malaysia:** Malay coverage; pairs with MaLLaM at 2B.3 as the escalation-option for Malay-first
 verification phrasing in deeply Malaysian content. SEA-LION
 is the broader-regional default; MaLLaM is the
 Malaysia-specific deeper option.
- **Philippines:** Tagalog / Filipino coverage; pairs
 with Meedan Check at 2B.1 (#FactsFirstPH coalition)
 as the LLM-mediated drafting layer behind Philippine
 tipline editorial workflows.
- **Sri Lanka:** Tamil coverage; Sinhala absent. For
 Sri-Lanka-Tamil fact-check work SEA-LION is operationally
 available with the same pan-multilingual caveat that
 applies to Alegre and X-CLAIM (Sri-Lanka-
 specific named entities and communal-memory politics may
 not be captured in the training data). For Sri-Lanka-
 Sinhala work the SinLlama lineage (University of Moratuwa)
 is the cross-reference per LIRNEasia research; SEA-LION does not cover
 Sinhala.
- **Thailand:** Thai coverage; the high-resource SEA-
 LION language alongside Bahasa and Vietnamese. Pairs with
 Cofact Thailand at 2B.1 as the LLM-mediated
 drafting layer behind Thai LINE-tipline editorial work.

Platform applicability: not platform-specific; SEA-LION is a
foundation model. Its outputs feed whichever editorial workflow
the operator runs at the front-end.

## How to access

Open-source weights are published on Hugging Face. The
aisingapore/sealion repository on GitHub is the canonical
upstream source; the Gemma-SEA-LION-v4-27B-IT variant is the
most-documented v4 checkpoint. Deployment is via Hugging Face
transformers, Ollama, or other standard LLM serving
infrastructure on the operator's hardware.

For institutional partners considering integration, the
SEA-LION documentation site (docs.sea-lion.ai) and the AI
Singapore SEALD (SEA Languages in One Network Data) materials
are the operational references. AI Singapore also runs hosted
endpoints; institutional partners with sensitivity about cloud
deployment should plan for self-hosted from the outset.

## Cost (current as of 2026-05)

Free under the open-source licence. Operational cost is the
operator's compute infrastructure: workstation-class hardware
for the smaller variants, GPU server for the 27B variant in
production, and developer time on integration. Compared with
cloud-LLM API costs at sustained fact-check workflow volume,
self-hosted SEA-LION is typically cheaper per token at the
institutional scale, though the up-front infrastructure
investment is real.

Verify current Hugging Face availability and any change in
licence terms via the aisingapore/sealion repository directly
before integrating; LLM release terms on Hugging Face evolve.

## Quickstart

(Quickstart for an institutional or developer deployment.
Front-line fact-checkers will reach SEA-LION through their
institutional partner's deployment rather than through this
quickstart.)

1. Confirm the use case is editorial drafting, summarisation,
 or question generation, and not detection or verification;
 SEA-LION is a productivity tool per Anchor 1, not a
 detection signal.
2. Select the SEA-LION variant. Gemma-SEA-LION-v4-27B-IT is
 the documented multimodal-capable v4 model; smaller text-
 only variants in the v4 family run on workstation hardware
 if the multimodal capability is not needed.
3. Pull the weights from Hugging Face into the operator's
 serving infrastructure (Hugging Face transformers, Ollama,
 vLLM, or other supported runners).
4. Build a prompt template for the specific editorial task:
 summarisation of a Bahasa article, Tamil-language question
 generation, Lao-language transcription review.
5. Validate output on local content before integrating into
 the live editorial workflow; LLM hallucination is binding,
 and validation reveals where the model produces confident-
 sounding fabrications.
6. Pair the SEA-LION drafting output with an explicit human
 verification step. Every claim the model surfaces is
 suggestive, not evidence; the verification step is
 mandatory before publication.
7. For high-volume integration, build logging that captures
 prompts and outputs so the editorial team can audit the
 LLM behaviour against published outputs over time.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.3 LLMs in fact-check workflows as the
primary entry: the regional foundation model that
institutional partners can run locally, with the broadest
SEA-language coverage in the cell. Cross-cell into 2B.2 is via
the LLM-mediated drafting layer that takes 2B.2 claim-
extraction outputs and produces editor-readable summaries.

Standard combinations:

- With **Google Pinpoint** at 2B.3 – the cloud-LLM
 journalist-pipeline alternative; SEA-LION is the locally-
 deployable counterpart. Operators choose by deployment
 posture: SEA-LION when the threat model requires self-host;
 Pinpoint when Google-server upload is acceptable per S1
 sensitivity classification.
- With **AI Fact Checker App** at 2B.3 – mobile
 lay-user front-end alternative; the two cards together span
 the institutional-self-host (SEA-LION) and lay-mobile
 (AI Fact Checker App) ends of the 2B.3 shortlist.
- With **MaLLaM (Mesolitica)** at 2B.3 – Malay-
 specific escalation-option; SEA-LION is the broader-regional
 default, MaLLaM is the deeper-Malay option for Malaysian
 work where Malay-first phrasing matters.
- With **Meedan Alegre** at 2B.2 – Alegre is the
 multilingual matching engine; SEA-LION is the
 multilingual drafting layer. A coalition-tipline pipeline
 routes Alegre's similarity output through SEA-LION's
 drafting for editorial review.
- With **Yudistira (MAFINDO)** at 2B.2 – Yudistira
 is the Indonesian Bahasa debunked-claim corpus; SEA-LION
 drafts Bahasa-language editorial responses against
 Yudistira matches.
- With **Dissect** at 2B.2 for Sinhala-language
 cross-reference – SEA-LION does not cover Sinhala; for
 Sinhala drafting the cross-reference is the SinLlama
 lineage documented in LIRNEasia research.
- With **Google Cloud Translation** at 2A.1 – for
 Lao-content workflows where SEA-LION provides the LLM-
 mediated drafting and Google Cloud Translation covers the
 English-language-route translation layer.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
references SEA-LION at T5.9 (text professional) as the locally-
deployable primary for SEA-language LLM-mediated editorial
drafting; cross-cell escalation into Pinpoint is the
cloud-LLM path with mitigation-pass caveat.

This card carries no detector signal class: SEA-LION produces
non-detector source-history signals (drafted summaries,
candidate questions, translation-assist outputs supporting
human verification). Per Anchor 2 LLM output is suggestive at
best; every claim must be verified against an independent
source before publication, and the verification step is the
binding rule rather than the LLM output itself.

## Override notes

!!! note "Override notes"
    - **LLM hallucination binding required
    (llm-hallucination-binding-required):** SEA-LION output is
    suggestive, not evidence. The card's TL;DR, Limitations
    admonition, Privacy and threat model section, and
    In the toolkit's workflow section all carry the
    hallucination-mitigation framing: every model-drafted
    claim is verified against an independent source before
    publication, and the verification step is mandatory
    rather than discretionary.

    - **Sinhala-absent cross-reference pointer
    (sinhala-absent-cross-reference-pointer):** SEA-LION
    does not cover Sinhala. The card's Country applicability
    section names the gap explicitly and routes the
    cross-reference to the SinLlama lineage (University of
    Moratuwa, ten-million-sentence Sinhala corpus) recorded
    in LIRNEasia research, which sits outside the 2B.3 cell as a
    Sri-Lanka-specific Sinhala LLM rather than a regional
    one.

## Sources

- [SEA-LION v4 release documentation](https://sea-lion.ai/blog/sea-lion-v4-multimodal/) (Bahasa, Burmese, Khmer, Lao, Malay,
 Mandarin, Tagalog, Tamil, Thai, Vietnamese, English language
 coverage; multimodal release; Gemma-SEA-LION-v4-27B-IT
 variant)
- [Gemma-SEA-LION-v4-27B-IT model card](https://ollama.com/aisingapore/Gemma-SEA-LION-v4-27B-IT)
