---
tool_id: TOOL-082
slug: ai-fact-checker-app
name: AI Fact Checker App
maintainer: Independent (regional app store publisher)
type: non-detector
outline_cells:
 - {id: "2B.3", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [en, agnostic-via-LLM-routing]
access: mobile
cost: proprietary-app-store
documented_country_use: [LA, MY, PH, TH]
tags: [llm, mobile, fact-check, regional-app-stores, laos, malaysia, philippines, thailand]
---

# AI Fact Checker App

**Distribution:** Regional app stores | **Type:** Non-detector | **Cost:** App store

!!! abstract "TL;DR"
    Mobile fact-check application explicitly localised across
    Laos, Malaysia, Philippines, and Thailand regional app
    stores; the toolkit's lay-mobile entry in 2B.3, paired with
    a binding LLM hallucination caveat. Useful as a
    point-of-first-contact triage for citizens but not as
    primary evidence in any institutional verification.

## What it does

AI Fact Checker App is a mobile application that accepts news
headlines, social-media posts, and viral-media URLs from a
phone's interface and returns an LLM-mediated factuality and
bias assessment. The app sits at the lay-user end of the
spectrum: a citizen forwards a forwarded WhatsApp message or
takes a screenshot of a TikTok caption, drops it into the app,
and gets a structured response framed as a factuality reading.

The app's documented role in the toolkit is regional reach.
Inventory records explicit localisation across Laos, Malaysia,
Philippines, and Thailand app stores, which makes the tool one
of the few documented mobile-fact-check products with cross-
country SEA presence. For a fact-checker pointing a non-
technical relative or community member toward a triage option
that runs on a phone (without requiring browser plugin
installation or knowledge of where to find a tipline number)
this is one of the available paths. The structural caveat is
that the LLM behind the assessment can hallucinate, the
operator-identity is documented as an independent app-store
publisher rather than a fact-check institution, and the output
should be read as suggestive triage rather than authoritative
verification.

## When to use it

- A community trainer pointing non-technical users toward a
 phone-based first-pass fact-check option with a familiar
 app-store install path.
- A regional outreach coalition pointing community members in
 Laos, Malaysia, Philippines, or Thailand toward a fact-check
 triage tool localised through their country's app store.
- A workshop demonstration of how mobile-LLM-based fact-check
 triage works at the lay user layer, paired with the
 mandatory caveat about hallucination and the institutional-
 workflow alternatives (Kalimasada, Cofact,
 Sebenarnya AIFA at 2B.1) for serious cases.
- A research project on lay-user fact-check tool adoption
 needs the documented regional mobile reference point.

## Limitations

!!! info "Limitations"
    - Limitations not stated in research. The
    app's specific operational limitations were not surfaced
    in the source set; institutional partners considering
    pointing users toward the app should review current
    app-store listings, terms of service, and the underlying
    LLM behaviour before broad recommendation.
    - LLM hallucination caveat is binding. The app's output is
    LLM-mediated, which means it can produce confident-
    sounding factuality verdicts on claims the model has no
    reliable basis to evaluate. Lay users will not by
    default treat the output as suggestive rather than
    authoritative; trainers and intermediaries pointing
    users to the app must surface this caveat explicitly.
    - Operator identity is "independent (Apple App Store
    publisher)" ; the app is not maintained
    by a documented fact-check institution (MAFINDO, Cofact,
    Rappler, Watchdog), which means the editorial-trust
    framing that applies to those institutions does not
    transfer.
    - Mobile-only at the user-facing layer; institutional
    integration into a coalition workflow would require API
    or programmatic access that the app does not document
    publicly.
    - Available in regional app stores; specific store-by-store
    version availability and feature parity across the four
    country deployments is not documented in the source set
    and may diverge.

## Privacy and threat model

The app is mobile-published under a proprietary licence. Inputs
typed or pasted into the app travel from the user's phone to
the app's backend infrastructure for LLM-mediated processing
and return as a factuality reading. The data flow is
third-party-hosted; the operator-identity is not a documented
fact-check institution.

For ordinary citizen triage of public claims circulating on
social media this is operationally adequate at the threat-
model level; the input is typically already-public content,
not source-identifying material. For source handling the app
is not the right channel; direct contact with a regional
fact-check institution (MAFINDO, Cofact, Rappler, Watchdog,
Hashtag Generation) with explicit source-protection
arrangements is the right path. The app is for first-pass
citizen triage on circulating claims.

For institutional or coalition use, the same general discipline
applies: classify the input, do not route source-identifying
material through the app, and prefer the institutional-tipline
or self-hosted-LLM paths (Meedan Check, Kalimasada, SEA-LION) for any case the threat model
warrants.

## Country and platform applicability

Decision 7 framing applies: the app is an NLP-class tool, and
content-language coverage is the operational selection
criterion. The inventory records the app as available in
regional app stores across Laos, Malaysia, Philippines, and
Thailand; the underlying LLM is not documented in the source
set as language-specific, so content-language coverage is
inferred from the LLM's underlying multilingual capability
rather than from a documented per-language benchmark.

- **Indonesia:** not in the documented localisation set;
 Indonesian content routes to Kalimasada at 2B.1
 and Yudistira at 2B.2 as the institutional paths.
- **Laos:** localised in the Laos app store. Among the
 toolkit's 2B Lao paths, AI Fact Checker App is one of two
 documented operational tools (alongside AI Fact Checker App itself
 appearing in the Laos regional case documentation gap acknowledgement
 and Google Cloud Translation). The Lao gap pin
 applies; the app's mobile-LLM path is supplementary to
 the structural Lao gap rather than a closure of it.
- **Malaysia:** localised in the Malaysian app store;
 pairs with Sebenarnya AIFA at 2B.1 as the
 Malaysian institutional reference and with MaLLaM
 at 2B.3 as the Malay-specific LLM escalation-option.
- **Philippines:** localised in the Philippine app store;
 pairs with Meedan Check / #FactsFirstPH coalition
 at 2B.1 and with SEEK / VERA Bot as the documented
 Viber / Messenger institutional channel.
- **Sri Lanka:** not in the documented localisation
 set; Sri Lankan content routes to Dissect (Sinhala),
 X-CLAIM (Tamil), and the Hashtag Generation /
 Watchdog / Fact Crescendo SL / FactSeeker ecosystem
 recorded in regional case documentation Lanka.
- **Thailand:** localised in the Thai app store; pairs
 with Cofact Thailand at 2B.1 as the Thai
 institutional reference.

Platform applicability: mobile (-mobile). The app is iOS per
inventory; Android availability via regional Google Play
deployments is not separately documented in the source set and
should be verified per country.

## How to access

Free download from the regional Apple App Store (and any
documented Google Play presence per country). The app is a
proprietary product, not an open-source release; reverse-
engineering or institutional integration is not in scope.

For institutional partners considering pointing users to the
app, the app-store listing in the relevant country is the
operational entry point. Pair the recommendation with explicit
training-context framing about the LLM hallucination caveat
and the institutional-workflow alternatives.

## Cost (current as of 2026-05)

Per inventory, "Proprietary" cost framing; the specific pricing
model is not documented in the source set. App-store apps
typically run free with optional in-app purchases or
subscription tiers; institutional partners pointing users to the
app should check the current app-store listing for any pricing
that has changed since the inventory was last reviewed.

## Quickstart

(Quickstart for a citizen user; institutional partners adapt
the framing for community-training contexts.)

1. Open the regional app store on your phone (Laos, Malaysia,
 Philippines, or Thailand store as relevant).
2. Search for "AI Fact Checker" or follow the trainer-supplied
 link to the listing.
3. Install the app; review the app-store listing and the
 in-app terms of service before submitting any content.
4. Submit the suspect headline, social-media post, or media
 URL to the app's input field.
5. Read the factuality and bias assessment as suggestive
 triage, not as final verification; the app's LLM can
 hallucinate, and the verdict is one signal class supporting
 the user's broader judgement, not evidence in itself.
6. For serious cases (anything that would be published, used
 in a community discussion at scale, or treated as
 authoritative), route to the institutional path appropriate
 to the country (Cofact for Thailand, Sebenarnya AIFA for
 Malaysia with the independence caveat, the regional
 #FactsFirstPH / Rappler chain for the Philippines, the
 Google Cloud Translation plus partner-mediated
 review path for Laos).

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2B.3 LLMs in fact-check workflows as the
mobile lay-user alternative alongside the institutional
SEA-LION primary, the cloud-LLM Pinpoint
journalist-pipeline alternative (cross-cell from 2A.1), and
the Malay-specific MaLLaM escalation-option. The
four entries together span the institutional-self-host /
cloud-LLM-journalist / lay-mobile / language-specific axis of
the 2B.3 shortlist.

Standard combinations:

- With **SEA-LION** at 2B.3 – institutional self-host
 primary; AI Fact Checker App is the lay-mobile alternative.
 The two cards illustrate the spectrum of LLM-deployment
 postures: open-weights regional foundation model on
 operator infrastructure versus proprietary mobile app at
 the citizen layer.
- With **Kalimasada (MAFINDO)** at 2B.1 – Indonesian
 alternative for users not in the AI Fact Checker App's
 documented localisation set.
- With **Cofact Thailand** at 2B.1 – Thai
 institutional reference alongside the AI Fact Checker App's
 Thai localisation.
- With **Sebenarnya AIFA** at 2B.1 – Malaysian
 institutional reference (with the documented independence
 caveat) alongside the AI Fact Checker App's Malaysian
 localisation.
- With **Google Cloud Translation** at 2A.1 – for
 Lao users pairing the app's mobile triage with the
 English-route translation layer for cross-checking.

Decision-tree references: [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
names AI Fact Checker App as the Philippines lay-user surface
alongside VERA Files / X-CLAIM; serious or institutional cases
route through the 2B.1 country-specific institutional paths and
back into [T5 escalation](../decision-trees/t5-escalation.md) at
T5.9 (text professional) where appropriate.

This card carries no detector signal class: AI Fact Checker
App produces a non-detector source-history signal (the LLM-
mediated factuality reading). Per Anchor 2 the reading is one
signal class supporting lay-user judgement; for any
publishable claim or institutional decision, additional
non-detector signals from 2B.1 (tipline-matched debunks),
2B.2 (claim-extraction matches), and 1B.5 (source-reliability
scoring) are mandatory.

## Override notes

!!! note "Override notes"
    - **LLM hallucination binding required
    (llm-hallucination-binding-required):** the app's LLM-
    mediated output can produce confident-sounding factuality
    verdicts on claims the model has no reliable basis to
    evaluate. The card surfaces this in the TL;DR, the
    Limitations admonition, the Privacy and threat model
    section, and the Quickstart's reading instruction. Lay
    users by default will not treat the output as suggestive;
    trainers and intermediaries pointing users to the app
    must surface this caveat explicitly.

    - **Multi-country regional app-store deployment
    (b4-score-2-LA-MY-PH-TH-app-stores):** the app is
    explicitly localised across Laos, Malaysia, Philippines,
    and Thailand regional app stores. The cross-country
    regional reach is the documented basis for inclusion;
    the per-country feature parity and version availability
    should be verified at adoption time.

## Sources

- Note: AI Fact Checker App is distributed through regional app stores (Google Play / Apple App Store). Canonical web URL unavailable as of 2026-05-11. Verify via direct app store search.
