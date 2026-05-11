---
tool_id: TOOL-080
slug: google-pinpoint
name: Google Pinpoint / Journalist Studio
maintainer: Google
type: non-detector
outline_cells:
 - {id: "2A.1", role: primary, density_role: alternative}
 - {id: "2B.3", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [en, id, ms, fil, tha, sin, tam, lao]
access: web
cost: free
documented_country_use: [PH, ID, TH]
tags: [document-search, transcription, ocr, entity-extraction, journalist-studio, productivity, google]
---

# Google Pinpoint / Journalist Studio

**Vendor:** [journaliststudio.google.com](https://journaliststudio.google.com/pinpoint/about) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Google's free document-investigation web tool. A fact-checker
    drops a bundle of PDFs, audio recordings, images, or
    transcripts into a Pinpoint collection, and the tool returns
    OCR, fifteen-language audio transcription, named-entity
    extraction, cross-document search, and beta structured-data
    extraction. The productivity surface that turns a 600-page
    leak or a hundred-clip audio archive into a searchable file
    in a working session.

## What it does

Pinpoint is the document-research module of Google's Journalist
Studio. A user uploads a collection (PDFs, Word documents,
images, audio files, transcripts) and the tool processes the
collection in the background, returning OCR for image and PDF
text, audio transcription in roughly fifteen languages,
named-entity extraction across people, organisations, and
locations, and a free-text search that runs across the entire
collection at once. A beta structured-data extraction feature
returns table-shaped data from documents that contain it.
Pinpoint also includes a "labels" mechanism for tagging entities
across documents and exporting findings.

For toolkit work the value is the workflow surface: instead of
reading a hundred PDFs sequentially or transcribing twenty audio
files one at a time, the user front-loads the bulk processing
and then iterates against a searchable collection. A regional
investigation with mixed-language sources (Bahasa documents,
Filipino audio, English background reports) lands in a single
Pinpoint collection where the named-entity extraction and search
do most of the routing work that a manual pass would otherwise
require.

## When to use it

- A document leak or large records request needs OCR, entity
 extraction, and search before any sustained reading begins.
- A journalist is processing a hundred audio clips (interviews,
 livestream rips, parliamentary recordings) in a Southeast
 Asian language and wants the transcripts stitched into a
 searchable collection rather than handled file-by-file.
- A multi-source investigation spans Bahasa, Filipino, Thai, and
 English material and needs a uniform search surface across
 the four languages.
- An election-period workflow needs to cross-reference candidate
 names, party affiliations, and locations across hundreds of
 campaign documents in a working session.

## Limitations

!!! info "Limitations"
    - Generative-AI features (the beta structured-data
    extraction, summary generation) may be inaccurate. Treat any AI-extracted summary or table as a
    draft requiring verification against the source document
    before any claim is published.
    - Files are processed on Google servers; sensitive material
    caution applies. For source-identifying
    content this is a binding pre-upload classification
    decision, not a soft preference.
    - Validation required for low-resource scripts. OCR and transcription quality varies for
    Sinhala, Tamil, and Lao scripts in particular; the
    asymmetric Sri Lanka pattern from regional research applies; Sinhala
    output is validatable against the local stack, Sri Lankan
    Tamil output runs against pan-Tamil resources that miss
    island-specific named entities.
    - Eligibility process for collection ingestion: Pinpoint
    gates large or sensitive collections through a Google-
    operated approval flow (the "Journalist Studio" eligibility
    process). The toolkit cannot guarantee turnaround for any
    specific collection.
    - Audio transcription covers roughly fifteen languages; not
    every SEA language is in that set with equal quality, and
    the precise list shifts as Google updates the product.
    Verify language coverage at the Pinpoint collection-create
    step before committing a workflow.

## Privacy and threat model

Pinpoint is a cloud product. Files uploaded to a Pinpoint
collection are processed and stored on Google servers under that
vendor's retention and access terms. The Journalist Studio
positioning frames the product as journalist-focused; the data
flow is nonetheless to Google. The d4 mitigation-pass that the
framework records here (override flag
`d4-mitigation-pass-Google-servers-sensitive-content`) means the
routing is acceptable for non-source-identifying content but
requires pre-upload classification for material that identifies
a source.

For Sri Lanka and Laos surveillance-environment work, the
recommended routing is: classify each document or audio file as
public, sensitive, or source-identifying before upload. Public
political documents are acceptable; source-identifying material
should be redacted, paraphrased, or routed via Sherloq
(offline) or MetaDataKit (browser-WASM local) for
metadata work that does not require Pinpoint's collection-level
search. The routing thinking is the same as for Hive at
1A.1 / 1A.3: the upload itself, not the verdict that comes
back, is the risk.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying documents (leaked memos that
    name informants, recordings that identify a speaker, contracts
    that expose a whistleblower) to a Pinpoint collection
    transmits the file to Google servers under the vendor's
    retention regime. Mitigation steps:

    1. Classify each file as public, sensitive, or source-
    identifying before any upload to a Pinpoint collection.
    2. For source-identifying material, do not upload to Pinpoint.
    Use Sherloq for offline metadata work or read the
    documents on the analyst's local machine without indexing.
    3. If Pinpoint's collection-level search is operationally
    necessary, redact identifying content (names, addresses,
    reference numbers) on the local machine before upload.
    4. Document the upload and any redactions in the case record;
    disclose the data flow to the source where consent is part
    of the editorial agreement.

## Country and platform applicability

- **Indonesia:** documented adoption in regional newsroom
 document-research workflows; pairs cleanly with Yudistira when extracted entities or claims need MAFINDO
 database matching.
- **Laos:** language coverage is marginal at best on Lao
 audio transcription; the toolkit treats Pinpoint as
 non-primary for Lao. Pair with Google Cloud
 Translation as the explicit Lao text path.
- **Malaysia:** Malay coverage operational; useful for
 multi-document investigation drawing on Bernama, Sebenarnya,
 or court-record sources.
- **Philippines:** documented use in journalist tool
 catalogues including the Philippine investigative-journalism
 community; pairs with #FactsFirstPH workflow on
 document-research cases.
- **Sri Lanka:** asymmetric per regional research context
 transcription is validatable against the local stack;
 Sri Lankan Tamil OCR is thinner. Watchdog and Hashtag
 Generation are the documented partners for validation work.
- **Thailand:** Thai language coverage operational;
 documented use through SONP and Thai PBS document-research
 workflows.

Platform applicability: not platform-specific. Pinpoint operates
on uploaded files regardless of where they originated.

## How to access

Sign in with a Google account at journaliststudio.google.com/
pinpoint and create a collection. Upload documents, audio,
images, or transcripts to the collection through the web
interface. Larger collections or organisational deployments
trigger the Journalist Studio eligibility flow; Google-side
review and approval are required before the collection is fully
operational. No paid tier exists for the core Pinpoint product
as of May 2026; access is gated by the eligibility process
rather than by price.

## Cost (current as of 2026-05)

Free. The Pinpoint product carries no per-collection or
per-character fee for the documented use cases. The structural
cost is the eligibility process (Google's review of the
collection's purpose and source) and the data-flow cost of
processing on Google servers (the d4 mitigation-pass routing
thinking above).

## Quickstart

1. Sign in at journaliststudio.google.com/pinpoint with a Google
 account.
2. Create a new collection and name it; select the language(s)
 relevant to the source material.
3. Before uploading, classify each file as public, sensitive, or
 source-identifying: the d4 routing decision sits here.
4. Upload the bundle: PDFs, images, audio, transcripts. Pinpoint
 runs OCR, transcription, and entity extraction in the
 background.
5. Use the search field to query across the entire collection at
 once; click any entity to see every document that mentions it.
6. For low-resource scripts (Sinhala, Tamil, Lao), spot-check
 transcription and OCR quality before treating extracted
 entities as reliable.
7. Export findings or labels as needed; treat any beta
 structured-data extraction as a draft requiring verification
 against the source document.

## In the toolkit's workflow

Source-history pillar non-detector productivity tool per
Architectural Anchor 1. Sits in 2A.1 as the journalist-pipeline
alternative entry alongside Whisper (open-source
transcription) and Google Cloud Translation (paid
cross-language path for Lao). Cross-cell role at 2B.3 as an
LLM-pipeline alternative; Pinpoint's beta structured-data
extraction sits inside the LLM-in-fact-check-workflows landscape
alongside SEA-LION, AI Fact Checker App, and
MaLLaM.

Standard combinations:

- With **Whisper** at 2A.1 when raw audio needs to
 reach a Pinpoint collection; Whisper transcribes locally,
 the resulting transcripts are uploaded to Pinpoint for
 collection-level search.
- With **Google Cloud Translation** at 2A.1 when
 multi-language content needs uniform translation before
 cross-document search.
- With **Yudistira** at 2B.2 when extracted Bahasa
 entities need claim-database matching against MAFINDO's stack.
- With **Meedan Check** at 2B.1 when document-research
 findings feed into a tipline workflow.
- With **Sherloq** or **MetaDataKit** at 1B.1
 when source-identifying material would otherwise have to
 upload to Pinpoint; those two tools handle metadata work
 without the cloud upload.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
reaches Pinpoint at T5.9 (text professional) when an institutional
document-research escalation is the right tier. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes any source-identifying material away from Pinpoint and
toward offline alternatives (see [Digital Safety](../digital-safety/source-protection-aggregation.md)).

This card carries no detector signal class: Pinpoint produces
search, OCR, transcription, and entity-extraction outputs, not
detection signals. Per Anchor 1 these outputs are inputs for
downstream signal classes; per Anchor 2 a Pinpoint extraction by
itself is not publishable evidence and must be verified against
the underlying source documents.

## Override notes

!!! note "Override notes"
    - **Google-server data flow with sensitive-content caveat
    (d4-mitigation-pass-Google-servers-sensitive-content):** the
    tool processes files on Google servers under that vendor's
    retention policy. For source-identifying content, classify
    before upload and route sensitive material through the
    offline alternatives at 1B.1. Routing thinking matches
    Hive at 1A.1 / 1A.3.
    - **Low-resource script validation (b2-partial-pass-low-
    resource-script-validation):** OCR and transcription quality
    degrades on Sinhala, Tamil, and Lao scripts. Spot-check
    output before treating extracted entities as reliable;
    pair with the regional research local-stack resources for Sinhala and
    with partner-mediated review for Sri Lankan Tamil and
    Lao content.

## Sources

- Google Journalist Studio. *Pinpoint — document and audio collection analysis for journalists*. Google, 2024. [journaliststudio.google.com/pinpoint](https://journaliststudio.google.com/pinpoint).
