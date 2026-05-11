---
tool_id: TOOL-074
slug: dissect-watchdog-lirneasia
name: Dissect (Watchdog Sri Lanka / LIRNEasia)
maintainer: LIRNEasia in partnership with Watchdog (Appendix)
type: non-detector
outline_cells:
 - {id: "2B.2", role: primary, density_role: primary}
pillar_service: [source-history]
signal_class: non-detector
status: beta
last_verified: 2026-05-10
license: open-source-collective-licence-not-stated-on-repo
languages_ui: [en]
languages_content: [sin]
access: web
cost: free
documented_country_use: [LK]
tags: [claim-extraction, sea-language-nlp, sinhala, sri-lanka, lirneasia, watchdog, asia-foundation]
---

# Dissect (Watchdog Sri Lanka / LIRNEasia)

**Operator:** [watchdog.team](https://watchdog.team) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Sri Lanka-specific AI-assisted claim-extraction tool from
    LIRNEasia and Watchdog (Appendix) that ingests news article
    URLs and decomposes them into claims, assumptions, sources,
    and named entities, with explicit Sinhala operational
    coverage. The only Sri Lanka-specific Sinhala NLP tool in
    the toolkit's 2B.2 shortlist; the closest analogue to a
    locally adapted claim-extraction stack for the country.

## What it does

Dissect is a beta-stage web tool that accepts the URL of a news
article and returns a structured decomposition: a list of
extractable claims, the assumptions behind each claim, the
named sources cited, and the named entities mentioned. It does
not return a truth verdict; the output is structural support
for a human fact-checker, not a finished debunk. A journalist
or fact-checker reviews the extracted decomposition, prioritises
the claims that warrant verification, and proceeds to the
verification work itself with the structural analysis in hand.

The tool's value to the Sri Lanka fact-check ecosystem is that
it is built on and tuned to the local NLP stack, not a
multilingual model retrofitted for the region. The 2025
LIRNEasia / Appendix prototype phase emphasised usability and
scalability refinement before public launch, and regional research records
that the design intent is newsroom-assist or investigator-
assist rather than a consumer-facing tipline. Dissect sits
upstream of the editorial decision rather than at the public
intake layer.

## When to use it

- A Sri Lankan newsroom or fact-check team has a Sinhala-
 language news article that needs to be triaged for
 check-worthy claims before investing reporter time on
 verification.
- A regional research project on Sri Lankan information flows
 needs structured claim and entity extraction from local
 Sinhala news content as input to monitoring or analysis.
- A journalist preparing election-cycle coverage wants
 systematic decomposition of statements by senior officials
 and party communications, building from the FactCheck.lk and
 Citizen Fact Check pattern of monitoring high-level public
 speech.
- An institutional partner is evaluating Sinhala-language NLP
 tooling for adoption in a fact-check workflow and Dissect is
 the documented Sri-Lanka-specific reference point.

## Limitations

!!! info "Limitations"
    - Does not verify truth (extractor only).
    The output is structural, not evaluative; a human
    journalist completes the fact-checking work after
    extraction.
    - Requires human journalist for final fact-checking.
    - Beta status (Late 2025 / 2026): the public-launch phase
    is the productisation of an earlier prototype, and
    operational throughput and uptime are not at production-
    grade SLAs.
    - Sinhala is the documented operational language; Tamil
    and Bengali are listed as in-development and should not
    be assumed available in the same operational state as
    Sinhala. For Tamil-language Sri Lankan content the
    toolkit's available path is X-CLAIM with the
    Sri-Lanka-specific adaptation gap recorded on that card.
    - Repository licence is recorded as "open-source collective"
    in the source set, but the underlying repo licence
    (MIT, Apache, AGPL, or other) is not surfaced in
    research; institutional partners considering operational
    reuse should verify the licence on the repository
    directly before integration.

## Privacy and threat model

The data flow is article-level rather than source-level. A
user submits a news article URL, and Dissect retrieves and
processes the public article text on its own infrastructure.
The user does not upload private documents, source-identifying
material, or interview content; the input is already-published
news text in the public domain.

For Sri Lanka, the threat-model dimension that matters is the
broader operating environment for the maintainers rather than
data flow at the user-facing layer. regional research records that Sri
Lanka's Online Safety Act 2024 establishes broad state powers
over "prohibited statements," online accounts, and "online
locations"; LIRNEasia and Appendix/Watchdog operate inside
that environment. The toolkit's Sri Lanka country page and
1B.1 source-protection guidance (Sherloq for offline
forensics) carry the broader Sri Lanka surveillance-environment
framing that institutional partners should pair with any
tooling decision in the country.

## Country and platform applicability

Decision 7 framing applies: Dissect is an NLP-class tool, and
content-language coverage is the operational selection
criterion.

- **Indonesia:** not applicable as a primary tool.
 Indonesian Bahasa content routes through Yudistira
 (MAFINDO) and Meedan Alegre.
- **Laos:** not applicable. Lao-language claim
 extraction is not covered by Dissect; the Lao gap at 2B.2 is
 structural across all entries in this cell. The Lao path
 remains Google Cloud Translation routing (2A.1
 cross-link) plus partner-mediated review.
- **Malaysia:** not applicable as a primary tool. Malay
 content routes through Alegre and the 2B.3 LLM
 layer (MaLLaM).
- **Philippines:** not applicable as a primary tool.
 Filipino / Tagalog content routes through Alegre.
- **Sri Lanka:** primary deployment for Sinhala
 content. Dissect is the only Sri-Lanka-specific Sinhala NLP
 claim-extraction tool in the toolkit's 2B.2 shortlist, and
 it sits inside a wider Sri-Lanka-specific Sinhala stack —
 LIRNEasia's MisinformationCorpusSinhala (3,576 Sinhala
 documents annotated CREDIBLE / FALSE / PARTIAL / UNCERTAIN),
 the University of Moratuwa's SinLlama model (the first
 open-source LLM built specifically for Sinhala, continually
 pre-trained on a cleaned ten-million-sentence Sinhala
 corpus), and the SLTK PyPI tokenizer (v1.0.0 released
 25 March 2025), which supports the asymmetric Sinhala-strong
 framing recorded in regional research. Tested by FactCheck.lk and Citizen
 Fact Check.

 For Sri Lankan Tamil content, Dissect is not the right tool;
 the available path is X-CLAIM, and the
 pan-Tamil-vs-Sri-Lanka-specific adaptation gap recorded on
 that card applies. The asymmetric framing (Sinhala-strong on Dissect, Tamil
 pan-Indian on X-CLAIM) is the toolkit's
 honest closure of the Decision 7 Sinhala-Tamil parity
 question per regional research.
- **Thailand:** not applicable. Thai content routes
 through Alegre.

Platform applicability: not platform-specific. Dissect operates
on news article URLs across whichever publication the article
appears on; the typical use is articles published on Sri Lankan
news outlets and accessed via standard web URLs.

## How to access

Web access in beta. Dissect is reachable through the Watchdog
(Appendix) and LIRNEasia public communications channels; the
beta is grant-funded under Asia Foundation South Asia Grants and
runs on LIRNEasia infrastructure. Account requirements depend
on the current beta access policy; institutional partners
considering integration should reach LIRNEasia or Watchdog
directly to confirm current access conditions and any
operational constraints on automated or high-volume use.

The repository is open-source-collective per inventory; the
specific licence on the underlying code is not surfaced in
research, and reuse beyond the public web tool requires direct
verification on the repo (see Limitations).

## Cost (current as of 2026-05)

Free at the public-tool layer. Underlying operational costs
sit with LIRNEasia and Watchdog and are funded through Asia
Foundation South Asia Grants and the maintainers' broader
funding stack. Cost sustainability is on the operating
organisations, not on the user.

## Quickstart

1. Open the Dissect web tool (URL published through Watchdog /
 LIRNEasia channels at the current beta).
2. Submit the URL of the Sinhala-language news article you
 want decomposed.
3. Wait for the structured output: extracted claims,
 assumptions, sources, and named entities.
4. Review the decomposition. Prioritise the claims that warrant
 reporter time for verification: typically the
 highest-stakes statements by senior officials, the most
 verifiable factual assertions, and any claim that resembles
 prior debunked content from FactCheck.lk, Hashtag
 Generation, or Watchdog archives.
5. Carry the priority list into your verification workflow:
 source triangulation, expert consultation, image / video
 verification through 1B tools where the article includes
 visual content, archive lookup against existing fact-checks
 (1B.5 Google Fact Check Explorer).
6. For Tamil-language Sri Lankan content, do not run Dissect;
 route to X-CLAIM with the Sri-Lanka-specific
 adaptation caveat applied.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.2 AI claim extraction as the primary entry
because it is the only Sri-Lanka-specific Sinhala NLP claim
tool in the shortlist; the cell's other four entries are
multilingual XLM-R (Meedan Alegre), Bahasa-specific (Yudistira (MAFINDO)),
English baseline (ClaimBuster), and Tamil pan-Indian (X-CLAIM).

Standard combinations:

- With **X-CLAIM** at 2B.2 – the Tamil counterpart for
 Sri Lankan content. Together Dissect and X-CLAIM close the
 Sinhala / Tamil shortlist for Sri Lankan claim extraction
 with the asymmetric framing recorded above.
- With **Google Cloud Translation** at 2A.1 – when
 Sinhala content needs translation into English for a
 cross-country audience, or when partner-mediated review of
 English versions of decomposed claims is the editorial
 path; Sinhala is supported on Google Cloud Translation as
 one of the documented SEA-language paths.
- With **Google Fact Check Explorer** at 1B.5 – for
 cross-checking decomposed claims against existing
 fact-checks, including ClaimReview-indexed Sri Lankan
 fact-checker output.
- With **Sherloq** at 1B.1 – when the article under
 decomposition includes images that need offline forensic
 review in the Sri Lankan surveillance-environment threat
 model recorded in regional case documentation Lanka.
- With **Meedan Alegre** at 2B.2 – Alegre's
 multilingual XLM-R covers Sinhala via the multilingual model
 but with the low-resource caveat that LIRNEasia's
 Sri-Lanka-specific tooling is built to address. The two
 cards together illustrate the difference between
 multilingual-fallback and locally-tuned approaches to
 Sinhala claim extraction.

Decision-tree references: T-tree node for Sri Lankan
Sinhala-language claim triage routes through Dissect at the
2B.2 entry; cross-cell routing into 2B.1 tipline-style
structures is bounded because Sri Lanka has no
Meedan-style purpose-built tipline backend (regional case documentation
Lanka; regional research context.

This card carries no detector signal class: Dissect produces a
non-detector source-history signal (the structural decomposition
of the article and the entity extraction). Per Anchor 2 the
decomposition is one signal class supporting human verification
work; the verified fact-check that follows is itself the next
signal class in the editorial workflow.

## Override notes

!!! note "Override notes"
    - **Sinhala asymmetric-gap acknowledgement
    (sinhala-asymmetric-gap-acknowledgement):** Sri Lanka's
    Sinhala stack is the more locally coherent side of the
    Sinhala / Tamil pair recorded in regional research context
    MisinformationCorpusSinhala, the University of
    Moratuwa's SinLlama, the SLTK tokenizer, and Dissect
    itself sit alongside FactCheck.lk and Hashtag
    Generation's Sinhala fact-check output as a coherent
    operational layer. Tamil tooling for Sri Lanka leans
    heavily on pan-Indian resources, including X-CLAIM. The toolkit's 2B.2 cell pairs Dissect with
    X-CLAIM precisely to make this asymmetry visible rather
    than mask it under a single multilingual entry.

    - **Non-detector declaration:** Dissect
    produces structural decomposition (claims, assumptions,
    sources, entities); a human journalist completes the
    fact-check.

## Sources

- Watchdog Sri Lanka / Appendix. *Dissect — Sinhala-language news article decomposition tool*. Watchdog Sri Lanka, 2025–2026 (beta). [watchdog.team](https://watchdog.team).
- LIRNEasia. *LIRNEasia — technology research think tank, South and Southeast Asia*. [lirneasia.net](https://lirneasia.net).
