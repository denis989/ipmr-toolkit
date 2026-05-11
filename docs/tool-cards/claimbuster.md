---
tool_id: TOOL-076
slug: claimbuster
name: ClaimBuster
maintainer: UT Arlington Information Discovery and Information Retrieval Lab (IDIR)
type: non-detector
outline_cells:
 - {id: "2B.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: academic-open-source
languages_ui: [en]
languages_content: [en]
access: web | api | browser-ext | slack
cost: free
documented_country_use: []
tags: [claim-extraction, english-baseline, academic, ut-arlington, duke-tech-and-check, check-worthiness]
---

# ClaimBuster

**Publisher:** [idir.uta.edu](https://idir.uta.edu/claimbuster/) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Long-running academic claim-extraction baseline from UT
    Arlington's IDIR lab that scores English-language sentences
    for fact-check-worthiness, with a free API, browser plugin,
    and Slack integration. The toolkit's English-language
    reference point in 2B.2, useful for regional
    English-language press, diaspora social media, and
    transnational claims; for SEA-language content the
    operational paths sit elsewhere in the cell.

## What it does

ClaimBuster ingests text and returns a check-worthiness score
per sentence: a continuous score that ranks how likely the
sentence is to contain a verifiable factual claim that warrants
fact-checker attention. The model is an academic baseline that
has been maintained over multiple years through the Duke
Reporters' Lab Tech & Check Cooperative, with documented use in
political-debate monitoring (US presidential debates and similar
high-volume English-language transcript processing).

The tool's value to a regional fact-check operation is not
SEA-language coverage (explicitly outside its scope) but the
role it plays as an English-baseline reference point.
Where a fact-checker has English-language input that does not
warrant the heavier integration of a Check-style coalition
deployment (a regional English-language press article, a
diaspora-focused social-media stream, a transnational claim
appearing in English regional news), ClaimBuster is the
maintained academic option. UT Arlington runs the
infrastructure; the Duke Reporters' Lab pairs the tool with
broader fact-check operationalisation.

## When to use it

- An English-language regional press article needs systematic
 check-worthiness scoring before reporter time is allocated
 to verification of specific claims.
- A regional research project needs a free academic baseline
 for English-language claim ranking on transnational content
 appearing in regional English-language outlets.
- A diaspora-social-media monitoring workflow needs lightweight
 English-language claim triage; the Chrome plugin or Slack
 integration is operationally lighter than standing up an
 Alegre or Check deployment.
- A trainer running an English-language fact-check workshop
 wants a free, documented academic tool to demonstrate
 claim-extraction concepts before introducing the
 multilingual paths through Alegre and country-specific
 entries.

## Limitations

!!! info "Limitations"
    - Multilingual claim detection remains uneven. The tool is primarily English; non-English
    content should not be expected to receive the same
    quality of check-worthiness scoring.
    - English-only operational language. Bahasa Indonesia,
    Malay, Filipino / Tagalog, Thai, Sinhala, Tamil, and
    Lao are not covered; for SEA-language content the
    operational paths are Dissect (Sinhala),
    Yudistira (Bahasa), Alegre
    (multilingual XLM-R), and X-CLAIM (Tamil
    pan-Indian).
    - Returns check-worthiness scores, not verified
    fact-checks; a high score is a flag for human attention,
    not evidence the claim is false.
    - Documented use is primarily political-debate monitoring
    in the United States and similar English-speaking
    contexts; SEA-region documented use has not been
    surfaced in the source set. Validation on regional
    English-language content is the operator's
    responsibility.

## Privacy and threat model

ClaimBuster runs as a free API and web service; queries travel
to UT Arlington's infrastructure for processing. The threat
model at the user-facing layer is low for typical use; the
inputs are typically already-published English-language
transcripts or articles, not source-identifying material. The
research-academic operator identity (UT Arlington IDIR, Duke
Tech & Check) is institutionally stable and outside any of the
six focus countries' regulatory environments.

For institutional partners considering Slack or browser-plugin
integration, the same general discipline applies as to other
cloud-hosted tools: classify what is being submitted, do not
route source-identifying material through public APIs, and
prefer the bring-your-own-environment paths (other entries in
2B.2 that are self-hostable) when the threat model warrants.

## Country and platform applicability

Decision 7 framing applies: ClaimBuster is an NLP-class tool,
and content-language coverage is the operational selection
criterion. ClaimBuster is documented as English-only at
operational scale; the b2-disclaimer-pass-English-only flag is
the explicit acknowledgement that this tool enters the
shortlist with a content-language disclaimer rather than
through a SEA-language pass.

- **Indonesia:** not applicable for Bahasa Indonesia
 content. English-language regional press or diaspora
 English-language streams about Indonesian topics may be
 processed; the bilingual context is the validation
 responsibility of the operator.
- **Laos:** not applicable. Lao is not covered; the
 2B.2 Lao gap is structural across all NLP-class entries in
 this cell. The Lao path remains Google Cloud
 Translation routing (2A.1 cross-link) plus partner-mediated
 review.
- **Malaysia:** not applicable for Malay. English-
 language Malaysian regional press may be processed; the
 recommended primary paths for Malaysian content are
 Alegre and the 2B.3 LLM layer (MaLLaM).
- **Philippines:** not applicable for Filipino /
 Tagalog. English-language Philippine press is processable —
 Philippines has substantial English-language press output —
 with the validation caveat above.
- **Sri Lanka:** not applicable for Sinhala or
 Tamil. English-language Sri Lankan press (FactCheck.lk's
 English-facing archive, English-language Sri Lankan news
 outlets) is processable with the validation caveat.
- **Thailand:** not applicable for Thai.
 English-language Thai press is processable with the
 validation caveat.

Platform applicability: not platform-specific. ClaimBuster
operates on text input across web, API, Chrome plugin, and
Slack integrations; the typical use is on transcripts, articles,
or text streams the operator already has in machine-readable
form.

## How to access

Free at idir.uta.edu/claimbuster and via the documented API endpoints.
The Chrome plugin is available from the Chrome Web Store; the
Slack integration is documented on the IDIR / Duke Reporters'
Lab pages. Account creation is required for some API tiers but
not for the basic web-form scoring; institutional partners
considering high-volume programmatic use should review the
IDIR documentation for current rate limits.

## Cost (current as of 2026-05)

Free under the academic-open-source model. The infrastructure
is run by UT Arlington's IDIR lab with Duke Reporters' Lab
Tech & Check Cooperative support; sustainability is on the
maintainers, not on the user.

## Quickstart

1. Open idir.uta.edu/claimbuster or install the Chrome plugin from the
 Chrome Web Store.
2. Submit English-language text (a transcript, an article, a
 social-media post) to the scoring endpoint.
3. Review the per-sentence check-worthiness scores; high-score
 sentences are flagged for fact-checker attention rather
 than auto-classified as false.
4. Carry the priority list into the verification workflow:
 source triangulation, cross-check against existing
 fact-checks via Google Fact Check Explorer (1B.5),
 image / video forensics through 1B tools where applicable.
5. For SEA-language content, do not attempt to use ClaimBuster
 as a primary tool; route to the appropriate 2B.2 entry
 (Dissect, Yudistira, Alegre, X-CLAIM) by content language.
6. For institutional partners considering integration into a
 newsroom workflow, evaluate the Chrome plugin and Slack
 integration against the heavier Alegre / Check pipeline;
 ClaimBuster is operationally lighter but English-only.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.2 AI claim extraction as the English-
baseline reference point alongside the SEA-language
operational primaries: Sri-Lanka-specific Dissect,
multilingual Alegre, Bahasa-specific Yudistira, Tamil pan-Indian X-CLAIM. ClaimBuster's
role in the cell is the maintained academic baseline:
"if the input is English, ClaimBuster is the documented
academic option; for SEA-language content, route through the
language-appropriate entry."

Standard combinations:

- With **Dissect** at 2B.2 – Sri-Lanka-specific
 Sinhala primary versus ClaimBuster's English baseline; the
 two cards illustrate the polarity of the 2B.2 shortlist:
 one locally tuned and language-specific, one academic and
 English-only, with multilingual Alegre between
 them.
- With **Meedan Alegre** at 2B.2 – multilingual
 XLM-R covers SEA languages; ClaimBuster is the English
 reference point. A coalition handling both English regional
 press and multilingual tipline content runs both rather
 than choosing.
- With **Google Fact Check Explorer** at 1B.5 – for
 cross-checking high-score ClaimBuster claims against
 existing fact-checks; English-language ClaimReview-indexed
 output is well covered by Google's Fact Check Explorer.
- With **InVID-WeVerify** at 1B.1 when the
 English-language content includes images or video that need
 forensic verification before the verification proceeds.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
names ClaimBuster at T5.9 (text professional) as the academic
baseline option for English-language text-input claim triage; SEA-
language inputs route to the language-appropriate 2B.2 entry
instead of ClaimBuster.

This card carries no detector signal class: ClaimBuster
produces a non-detector source-history signal (the
check-worthiness score per sentence). Per Anchor 2 the score
is one signal class supporting human triage; the verification
work that follows is the next signal class in the editorial
workflow.

## Override notes

!!! note "Override notes"
    - **English-only disclaimer pass
    (b2-disclaimer-pass-English-only):** ClaimBuster enters
    the 2B.2 shortlist on the explicit understanding that it
    is English-only at operational scale. The card surfaces
    this in the TL;DR (regional English-language press,
    diaspora social media, transnational claims), in the
    Limitations admonition, and in the Country and platform
    applicability section's Decision 7 framing. SEA-language
    content routes to the appropriate language-specific
    entry in 2B.2 rather than to ClaimBuster.

## Sources

- Hassan, N. et al. *ClaimBuster: The First-Ever End-to-End Fact-Checking System*. Proceedings of the VLDB Endowment, 2017. [idir.uta.edu/claimbuster](https://idir.uta.edu/claimbuster).
- UT Arlington IDIR Lab. *ClaimBuster — automated claim detection*. University of Texas at Arlington. [idir.uta.edu/claimbuster](https://idir.uta.edu/claimbuster).
