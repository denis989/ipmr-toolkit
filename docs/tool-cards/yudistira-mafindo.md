---
tool_id: TOOL-097
slug: yudistira-mafindo
name: Yudistira (MAFINDO)
maintainer: MAFINDO (Masyarakat Anti Fitnah Indonesia)
type: non-detector
outline_cells:
 - {id: "2B.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free
languages_ui: [id]
languages_content: [id]
access: api | web
cost: free
documented_country_use: [ID]
tags: [claim-extraction, sea-language-nlp, bahasa-indonesia, mafindo, hoax-database, indonesia]
---

# Yudistira (MAFINDO)

**Operator:** [mafindo.or.id](https://mafindo.or.id) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    MAFINDO's centralised Bahasa Indonesia hoax-claim database
    and machine-to-machine API mapping circulating hoaxes
    against debunked claims. The country-anchored Bahasa
    Indonesia entry in 2B.2; the back-end claim-archive that
    Indonesian Check tiplines query when matching incoming
    forwarded content.

## What it does

Yudistira is the structured hoax database MAFINDO maintains as
a public reference and machine-readable API. A claim (typically the text or transcribed text of a forwarded
WhatsApp message, TikTok caption, or Facebook post) queries the
API and returns
matches against MAFINDO's corpus of debunked claims. The output
is "this claim has been debunked here" or "no match," not a
de-novo fact-check. Yudistira sits in the same MAFINDO product
family as ASE (Anti-Hoax Search Engine, the
public-facing search interface) and Kalimasada (the
WhatsApp Hoax Buster bot, the citizen-facing intake on
Meedan Check); Yudistira is the database layer all three
products draw on.

The tool's value to the Indonesian fact-check ecosystem is
specificity: MAFINDO's debunked-claim corpus is curated in
Bahasa Indonesia by Indonesian fact-checkers across the
CekFakta consortium, which means the matching is on the
language and the claim universe Indonesian misinformation
actually occupies, not a multilingual fallback retrofitted to
the country. For a cross-coalition deployment that needs
authoritative Indonesian debunk lookup, Yudistira is the
documented data source.

## When to use it

- An Indonesian fact-checker or newsroom needs to check whether
 a forwarded WhatsApp claim has already been debunked by the
 CekFakta consortium before opening a fresh verification
 cycle.
- A Check-backed tipline operator (Kalimasada, a CekFakta
 partner outlet, a regional Indonesian newsroom) needs the
 MAFINDO database integrated into the matching layer for
 duplicate detection.
- A regional research project on Indonesian information flows
 needs programmatic access to the curated debunk corpus for
 pattern analysis or cross-country comparison.
- A regional partner outside Indonesia is processing
 Bahasa-language content from Indonesian diaspora or
 cross-border discussions and needs the authoritative
 Indonesian debunk reference.

## Limitations

!!! info "Limitations"
    - Highly localised; requires continuous manual updating
. The corpus is editorially curated by
 MAFINDO and CekFakta partners; new claims must be added
 manually as they are debunked.
 - Bahasa Indonesia only. Filipino / Tagalog, Thai, Malay,
 Sinhala, Tamil, and Lao speakers are not served; for
 multilingual content the matching path is Meedan Alegre (XLM-R fallback) or the appropriate
 country-specific entry.
 - As a database, Yudistira returns matches against
 previously debunked claims; novel claims that have not
 yet been processed through MAFINDO's editorial workflow
 return "no match" and require fresh verification rather
 than being flagged as suspicious.
 - The corpus reflects MAFINDO's editorial priorities and
 coverage; claims that fall outside CekFakta's
 operational focus (very local rumours, fast-moving
 content not yet escalated to MAFINDO) may not be
 represented.

## Privacy and threat model

The privacy posture is database-query rather than source-handling.
A user or system queries the API with a claim text; the API
returns matches. The query content travels to MAFINDO's
infrastructure and is processed there. For ordinary
duplicate-detection use this is operationally adequate; the
query is typically the text of an already-circulating
public claim, not source-identifying material.

For source handling (sensitive content from a specific
informant, a clip that could identify someone, a private
document), Yudistira is the wrong path. Direct contact with a
MAFINDO journalist or a CekFakta partner newsroom with
explicit source-protection arrangements is the right path; the
database query layer is for circulating public claims, not for
private source material.

The Indonesia legal environment context applies broadly:
ITE risk is reduced after the April 2025 Constitutional Court
rulings but not removed, and MAFINDO operates inside that
environment. Yudistira itself does not change that framing;
operational source-protection discipline at the editorial layer
is the toolkit's recommendation.

## Country and platform applicability

Decision 7 framing applies: Yudistira is an NLP-class tool, and
content-language coverage is the operational selection
criterion. Bahasa Indonesia is the documented operational
language; the tool does not cover other SEA languages.

- **Indonesia:** primary deployment. Documented use
 through MAFINDO's Global Hoax Database and the ASE
 Anti-Hoax Search Engine; integrated with the CekFakta
 consortium's editorial workflow and queryable from
 Kalimasada-routed Check tipline content. The 2024 election
 cycle and the January-February 2025 Prabowo / Sri Mulyani
 deepfake cluster are the documented case anchors
.
- **Laos:** not applicable. No Lao coverage; the 2B.2
 Lao gap is structural (G-041) and the supporting Lao path
 remains Google Cloud Translation routing (2A.1
 cross-link) plus partner-mediated review.
- **Malaysia:** not applicable as a primary tool. Malay
 content is linguistically adjacent to Bahasa Indonesia but
 the corpus is Indonesian rather than Malaysian; Malaysian
 content routes through Alegre and the 2B.3 LLM
 layer (MaLLaM).
- **Philippines:** not applicable. Filipino / Tagalog
 content routes through Alegre.
- **Sri Lanka:** not applicable; Sinhala content
 routes through Dissect and Tamil content through
 X-CLAIM.
- **Thailand:** not applicable; Thai content routes
 through Alegre.

Platform applicability: not platform-specific; Yudistira is a
back-end database queried via API. Its outputs feed whichever
front-end intake (WhatsApp, Facebook, TikTok, LINE) the operating
organisation runs.

## How to access

Free public access via API and web. The MAFINDO Global Hoax
Database is published on MAFINDO's channels alongside the
TurnBackHoax.id public archive and the ASE Anti-Hoax Search
Engine. Institutional partners considering programmatic
integration should contact MAFINDO directly to confirm current
API access conditions and any operational constraints on
high-volume querying.

## Cost (current as of 2026-05)

Free for the public user. Underlying operational costs sit with
MAFINDO and are funded through MAFINDO's grant stack and
CekFakta consortium contributions; the hidden cost is the
continuous manual editorial work that keeps the corpus current.

## Quickstart

(Quickstart for an institutional partner integrating
Yudistira into a fact-check workflow; lay users typically
reach the corpus via ASE or Kalimasada
front-ends.)

1. Confirm Bahasa Indonesia is the relevant content language
 for the case; if not, route to the appropriate 2B.2 entry.
2. Submit the claim text to the Yudistira API endpoint
 published on MAFINDO's developer channels.
3. Review the API response: matched debunks (with links to
 the verified fact-checks) or no-match.
4. For matched debunks, route the link to the editorial layer
 so the operator's response references the existing MAFINDO
 verification rather than initiating a duplicate cycle.
5. For no-match results, route into the operator's standard
 fresh-verification workflow: Kalimasada queue if the
 intake is WhatsApp; CekFakta partner outlet desk if the
 case warrants newsroom investigation.
6. For high-volume programmatic use, coordinate with MAFINDO
 on rate limits and any usage-attribution requirements
 before sustained integration.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.2 AI claim extraction as the
country-anchored Bahasa Indonesia entry alongside the
Sri-Lanka-specific Dissect, the multilingual
Meedan Alegre, the English baseline ClaimBuster, and the Tamil pan-Indian X-CLAIM. Cross-cell
into 2B.1 is operational: Yudistira is the MAFINDO debunked-claim
corpus that Indonesian Check tiplines (Kalimasada at Kalimasada (MAFINDO))
query underneath the Alegre matching engine.

Standard combinations:

- With **Kalimasada (MAFINDO)** at 2B.1 – same
 maintainer, native integration; Kalimasada-routed forwarded
 WhatsApp content matches against the Yudistira corpus on
 the way through the Check editorial workflow.
- With **Meedan Check** at 2B.1 – Check is the
 workspace; Yudistira is the MAFINDO data source the
 Indonesian Check deployment queries.
- With **Meedan Alegre** at 2B.2 – Alegre is the
 multilingual matching engine; Yudistira is the curated
 Indonesian corpus Alegre matches against in the Indonesian
 deployment. The two cards describe the engine layer and the
 data layer of the same Indonesian back-end.
- With **MAFINDO Satgas Pemilu** at 2A.4 – Satgas
 Pemilu is the workflow design pattern that orchestrates
 Yudistira lookups during election cycles; the MAFINDO 2024
 Election Task Force ran on this combination.
- With **ASE Anti-Hoax Search Engine** as the
 public-facing search interface MAFINDO operates against the
 Yudistira corpus (referenced for completeness; ASE is not in
 the 2B.2 shortlist as a primary tool).
- With **InVID-WeVerify** at 1B.1 – when the matched
 claim involves image or video content needing forensic
 verification before the editorial reply.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
carries Yudistira as the Indonesian debunked-claim corpus underneath
the Kalimasada / Check tipline node; cross-cell routing for direct
institutional research access is via the documented MAFINDO API
channels.

This card carries no detector signal class: Yudistira produces
a non-detector source-history signal (database match against
the curated debunk corpus). Per Anchor 2 a database match is
one signal class supporting the editorial decision; the
matched fact-check itself is the next signal class.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration (g2-non-detector):** Yudistira
    returns database matches, not detector signals. Render
    in workflow as the Indonesian Bahasa-specific corpus
    layer underneath the country's tipline and matching
    infrastructure.

## Sources

- MAFINDO. *Yudistira — Global Hoax Database and Anti-Hoax Search Engine*. MAFINDO, 2024. [mafindo.or.id/yudistira](https://mafindo.or.id/yudistira).
- MAFINDO. *TurnBackHoax.id — Anti-Hoax Search Engine*. MAFINDO, 2024. [turnbackhoax.id](https://turnbackhoax.id).
