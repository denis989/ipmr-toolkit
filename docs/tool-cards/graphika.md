---
tool_id: TOOL-127
slug: graphika
name: Graphika
maintainer: Graphika
type: non-detector
outline_cells:
 - {id: "1C.1", role: escalation-option, density_role: escalation-option}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: api
cost: enterprise
documented_country_use: []
tags: [cib, network-analysis, behaviour, enterprise, influence-operations, graphika]
---

# Graphika

**Vendor:** [graphika.com](https://graphika.com) | **Type:** Non-detector | **Cost:** Enterprise

!!! abstract "TL;DR"
    A proprietary, enterprise-grade social-network analysis platform
    that maps online communities and tracks coordinated influence
    operations, with documented investigations into Myanmar military
    disinformation and 2024 Taiwan election interference. Listed
    here as escalation-option only; the price barrier puts it
    effectively out of reach for ordinary SEA frontline newsrooms.

## What it does

Graphika ingests social-media data across multiple platforms and
produces community maps, narrative-spread tracking, bot-detection
output, and structured assessments of influence operations. The
platform's published work names actor groups and traces their
activity across platform boundaries, which is the form of finding
that is most operationally useful for institutional research and
government-side intelligence work but least accessible to a
fact-check newsroom under deadline. Graphika has presented findings
to the US Senate Intelligence Committee and is among the named
analytical sources behind public reporting on the Russian Internet
Research Agency, Chinese Spamouflage, Myanmar military information
operations, and 2024 Taiwan election interference.

The tool serves the behaviour pillar per Architectural Anchor 1 by
producing non-detector signals (community maps, named-actor
trajectories) at a scale and depth that open-source tools in the
same cell (CIB Mango Tree, Coordination Network
Toolkit, CooRTweet) generally do not match for
multi-platform breadth, even where the open-source tools match
Graphika's methodological rigour at single-platform depth.

## When to use it

- An institutional research partner (academic centre, government
 CSIRT, regional civil-society lead) has budget access to Graphika
 and is producing analysis that an SEA newsroom can cite.
- A regional civil-society coalition is funded specifically for a
 multi-month influence-operation investigation across multiple
 platforms and Graphika's coverage breadth justifies the licence
 cost.
- A frontline newsroom benefits indirectly: a published Graphika
 report on a named operation becomes a citable source rather than
 an in-house tool.
- A fact-check operation needs to corroborate an open-source
 CooRTweet or Mango Tree finding through an institutional partner
 who runs Graphika; the partner's run is what the newsroom cites.

## Limitations

!!! info "Limitations"
    - Enterprise pricing places the tool out of reach for ordinary
    SEA newsrooms. The toolkit's editorial
    position is to list Graphika as escalation-option only and
    route frontline users to CIB Mango Tree, Coordination Network Toolkit, and CooRTweet (with CooRnet predecessor) as
    open-source primary, alternative, and alternative entries.
    - Requires trained analysts to avoid false attribution. Network-analysis output without methodological
    experience supports overconfident conclusions; the tool
    surfaces patterns, not intent.
    - Documented regional cases include Myanmar military and 2024
    Taiwan but no published deployment in the toolkit's six focus
    countries' frontline fact-check operations. Regional case
    strength sits at the institutional research-partner layer.
    - Black-box proprietary platform: methodology and model details
    are not openly documented at the level of the peer-reviewed
    open-source alternatives. Reproducibility of findings depends
    on Graphika's own documentation discipline rather than on
    published methodology.

## Privacy and threat model

Graphika is a hosted enterprise platform; data flows that an analyst
ingests into the platform travel to and reside on Graphika
infrastructure under the licence agreement's terms. For institutional
partners with the budget access, the standard institutional
data-handling regime (data-protection officer review, access logs,
retention policy review) applies to the contracted use.

For a newsroom that cites a Graphika-derived finding without itself
operating the platform, the privacy chain runs through the publishing
partner. Verify that the partner has obtained the data through
mechanisms compatible with your jurisdiction's legal regime; Sri
Lanka's OSA framework, Indonesia's UU ITE / PDP, and Thai
lèse-majesté concerns each shape what cited findings can carry into
local publication without secondary legal risk.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant via institutional
 partner research output rather than newsroom access.
- **Laos:** no documented Lao-specific Graphika investigation;
 no IFCN signatory means even partner-mediated MCL data is
 generally unavailable. Honest gap: frontline newsrooms have no
 realistic access path to Graphika or its data sources.
- **Malaysia:** language-agnostic; relevant in principle for
 the King / Anwar Ramadan-aid 2026 cluster where institutional research output may exist or be
 commissioned.
- **Philippines:** language-agnostic; the #FactsFirstPH
 research layer can cite institutional partners' Graphika work
 rather than running it directly.
- **Sri Lanka:** language-agnostic; Hashtag Generation and
 Watchdog operate at the research layer where partner Graphika
 output is occasionally cited; direct access is not present in the
 toolkit's inventory.
- **Thailand:** language-agnostic; documented relevance via
 AFP regional partnerships; Thai newsroom direct access not
 documented.

Frontline-no-access disclaimer applies across all six countries:
the listing here is for awareness of what institutional research
partners with budget access can produce. Frontline SEA newsrooms
should treat Graphika output as a citable source from a partner,
not as an in-house tool to deploy.

Platform applicability: cross-platform; Graphika's distinguishing
feature is multi-platform coverage where the open-source alternatives
in 1C.1 are usually single-platform per run.

## How to access

Enterprise sales contact via the Graphika website. The platform is
not available in a free or self-service tier; access requires a
commercial agreement and onboarding through Graphika's enterprise
sales process. Trained analyst capacity is part of the deployment
profile; Graphika is not a tool an untrained user can run
defensibly.

## Cost (current as of 2026-05)

Enterprise pricing in the **$50,000 to $200,000-plus per year** range
. This figure is from the
toolkit's inventory and may move with the vendor; verify
directly through Graphika's sales process before committing to a
procurement. The bracket is included for editorial honesty about why
Graphika is escalation-option in this cell rather than primary or
alternative: at this cost, the tool is structurally inaccessible to
the typical frontline SEA newsroom and is included for awareness of
what institutional research partners can produce.

## Quickstart

(Not applicable to typical SEA frontline use. The realistic path is
not "run Graphika" but "cite a Graphika-derived institutional
research finding as an external source.")

1. If your operation has institutional access via a partner,
 contact the partner directly for the methodology, time period,
 and dataset behind a relevant Graphika report.
2. Confirm the data-licence terms under which the partner conducted
 the analysis before citing in published work.
3. For institutional partners with direct Graphika access:
 onboarding is conducted through Graphika's commercial process;
 analyst training is part of the deployment profile.
4. For frontline newsrooms: invest the Graphika-equivalent budget
 into open-source 1C.1 work (CIB Mango Tree, Coordination Network Toolkit, CooRTweet (with CooRnet predecessor)) plus
 visualisation (Gephi) and codification frameworks
 (ABCDE, DISARM); the open-source ladder
 covers most operational SEA needs at zero software cost, even
 if it sometimes requires more analyst time.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 1C.1 Institutional CIB detection as escalation-option only,
deliberately placed below the open-source ladder (CIB Mango Tree,
Coordination Network Toolkit, CooRTweet (with CooRnet predecessor)) on accessibility grounds. The toolkit's editorial
position is that frontline users should reach Graphika output
indirectly, through institutional research partners' published work,
rather than directly through Graphika as a tool to deploy.

Standard combinations (when partner-mediated):

- With **CIB Mango Tree** as open-source corroboration of
 partner-published Graphika findings on the same dataset, where
 data access permits.
- With **Meta Content Library** at 2C.2 as one of the data
 sources that an institutional Graphika user might draw from for
 the SEA region.
- With **ABCDE Framework** at 2C.3 for codifying the
 Graphika-published behavioural pattern in inter-org reporting.

This card carries no detector signal class: Graphika produces a
non-detector behavioural-pattern signal class. Per Anchor 2, that
signal combines with claim-extraction (2B.2), provenance (1A.4), or
source-history (1B.1) to support a publishable institutional
finding.

## Override notes

!!! note "Override notes"
    - **Escalation-option only (e5-escalation-option-only):**
    Graphika was triggered by E5 (better alternatives exist for
    the toolkit's frontline audience) and rescued as escalation-
    option rather than excluded. The Cost section above renders
    the price barrier concretely. The card frames Graphika as
    awareness for what institutional research partners can
    produce, not as a tool for frontline SEA newsrooms.

    - **Frontline-no-access disclaimer (frontline-no-access-
    disclaimer):** the Country and platform applicability section
    states explicitly that frontline SEA newsrooms generally
    cannot reach Graphika directly across all six focus countries.
    Where Graphika-derived findings reach a frontline operation,
    they reach it through institutional partners' published work.

    - **Enterprise pricing (d1-score-1-enterprise):** D1 framework
    score of 1 (enterprise) is rendered concretely in Cost as the
    $50K-$200K+ per year range. This is the structural reason
    Graphika sits as escalation-option rather than primary or
    alternative in this cell.

## Sources

- Graphika. *Graphika — network analysis and influence operation research platform*. Graphika, 2024. [graphika.com](https://graphika.com).
