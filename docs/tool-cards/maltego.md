---
tool_id: TOOL-128
slug: maltego
name: Maltego
maintainer: Maltego Technologies
type: non-detector
outline_cells:
 - {id: "2C.2", role: primary, density_role: primary}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: desktop
cost: freemium
documented_country_use: [MY, TH]
tags: [osint, link-analysis, network-mapping, behaviour, gold-standard, freemium, cross-tier]
---

# Maltego

**Vendor:** [maltego.com](https://maltego.com) | **Type:** Non-detector | **Cost:** Freemium

!!! abstract "TL;DR"
    Link-analysis platform integrating with social networks, DNS
    records, and public databases for relationship mapping; the
    OSINT gold standard for institutional CIB and influence-
    operation work, available with a free Community Edition for
    individual practitioners and paid Professional and Enterprise
    tiers for institutional deployment. The 2C.2 primary entry,
    pairs with Gephi as the free open-source visualisation
    alternative.

## What it does

Maltego ingests entities (domains, accounts, IPs, email addresses,
hashes, phone numbers) and runs configurable transforms that pull
related data from public databases, social-network endpoints, DNS
records, and commercial intelligence sources, then renders the
resulting relationships as a visual link graph. The graph is
interactive: an analyst expands nodes, applies filters, clusters
related sub-graphs, and exports the result for institutional
reporting. Maltego's distinguishing operational value sits in the
transforms ecosystem: hundreds of integrations across OSINT data
sources are pre-built, which compresses what would otherwise be
many separate API queries plus manual reconciliation into a single
analyst session.

The tool fits 2C.2 because mapping a network of related accounts,
domains, or infrastructure is the next operational step after a
2C.1 monitoring run or a 1C.1 CIB analysis surfaces the network's
existence. Maltego is the standard institutional tool for that
mapping step; the toolkit lists it as primary because the OSINT
training base in the six focus countries documents Maltego use
where competing free alternatives (Gephi for
visualisation; bespoke Python pipelines elsewhere) require
significantly more analyst time to reach the same finding.

## When to use it

- An institutional partner is mapping a coordinated-amplification
 network surfaced by 1C.1 CIB tools (CIB Mango Tree, CooRTweet (with CooRnet predecessor)) and needs
 the breadth of pre-built transforms across DNS, WHOIS, social,
 and infrastructure data sources.
- An OSINT investigation is connecting actors and infrastructure
 across a multi-month timeline and needs an interactive workspace
 that supports analyst back-and-forth between data ingestion and
 graph-shape iteration.
- A cybersecurity-grounded influence-operation investigation is
 layering domain-and-infrastructure analysis on top of social-
 account analysis; Maltego's transforms cover both dimensions in
 one workspace.
- A trained analyst is producing a published institutional report
 and needs a visual link graph as a methodological artefact rather
 than a final-publication graphic; for publication-grade
 graphics, the standard pairing is Maltego for analysis plus
 Gephi for the final visual.

## Limitations

!!! info "Limitations"
    - Outputs become "hairballs" without strict filtering. The interactive graph workspace is unforgiving of
    expansive transforms run without scoped filtering; analyst
    discipline on what to ingest is part of the method.
    - Steep learning curve. Maltego is not a
    no-code tool; an analyst unfamiliar with OSINT methodology
    and transform configuration will spend significant ramp-up
    time before producing usable output. The OSINT training base
    in the six focus countries varies in depth; institutional
    partners with formal OSINT training programs are the natural
    deployment fit.
    - Free Community Edition has feature and dataset limits that
    shape what an individual practitioner can do without
    institutional licensing. Beyond Community Edition, the
    Professional and Enterprise tiers are paid commercial
    products at price points that put institutional deployment
    typically out of reach for individual newsrooms; the toolkit
    lists Gephi as the free open-source visualisation
    alternative for partners on a research budget.
    - Output is link-graph behavioural signal, not a verdict on
    claim truth or content authenticity. Per Anchor 2 the network
    map combines with claim-extraction (2B.2), source-history
    (1B.1), or fact-check signals before any publishable
    assertion.

## Privacy and threat model

Maltego runs on a desktop client; analyst queries travel out from
the analyst's machine to the various transform endpoints (DNS
servers, public databases, commercial-intelligence APIs, social
endpoints) under those endpoints' respective terms. The analyst's
own query record sits with the Maltego desktop application and any
configured commercial-data-source vendors; institutional users
should review the data-handling regime on the commercial transforms
they enable.

For surveillance-environment work in Sri Lanka, Laos, or other
contexts where running attributable OSINT queries on local
infrastructure is itself a flagged action, the operational
tradecraft (separate device, dedicated analyst account, network
egress through institutional infrastructure) belongs upstream of
the Maltego workspace. The tool itself does not change the upstream
collection threat model; institutional OSINT discipline applies
unchanged.

!!! danger "Source-protection override (S2 — state-linked or legally sensitive)"
    Maltego graphs that traverse police, military, ruling-party,
    or state-linked infrastructure can themselves become evidence
    against the analyst's publisher. Mitigation steps:

    1. Consult Digital Safety, legal counsel, or the editor before
    publishing any Maltego graph that names state-linked
    accounts or infrastructure.
    2. Operate Maltego in surveillance-risk contexts through
    institutional egress (separate device, dedicated account,
    VPN or institutional network) so the query itself is not
    attributable to the analyst's personal infrastructure.
    3. Treat the graph as research evidence first; named-actor
    network images are attribution claims under Article 112,
    OSA, UU ITE, CMA Section 233, and Decree 327.

!!! danger "Source-protection override (S4 — doxxing or vulnerable-community targeting)"
    Maltego graphs can identify activists, journalists, minority-
    community members, or witnesses caught up in the network
    alongside inauthentic accounts. Mitigation steps:

    1. Before publishing any Maltego graph, audit the named
    entities for vulnerable individuals; redact or pseudonymise
    identifiers.
    2. Consider a quiet response or institutional partner alert
    in place of a public debunk where retaliation risk is
    non-trivial.
    3. Assess retaliation risk per country-page documented
    harassment patterns before any publication of the network
    image.

## Country and platform applicability

- **Indonesia:** language-agnostic; institutional OSINT
 training base is present (CekFakta partner research labs;
 university OSINT programs). Documented use as part of the
 general institutional CIB stack rather than as a country-
 specific deployment.
- **Laos:** language-agnostic; institutional OSINT capacity
 in Laos is the structural gap rather than the tool itself. Where
 an institutional partner has analyst capacity, Maltego applies;
 honest gap is on the analyst-capacity side.
- **Malaysia:** language-agnostic; documented use in the
 toolkit's inventory as a general OSINT tool relevant for
 Malaysian work.
- **Philippines:** language-agnostic; relevant for
 #FactsFirstPH research-layer work and for the broader Rappler
 / VERA Files OSINT base.
- **Sri Lanka:** language-agnostic; relevant for
 Watchdog and Hashtag Generation institutional research where
 analyst capacity is present.
- **Thailand:** language-agnostic; documented use in
 Thai OSINT institutional contexts .

Frontline-mediated-access framing applies across the six countries:
Maltego's institutional-tier deployment is most realistic through
research-lab or partner-institution access rather than direct
individual-newsroom procurement. For frontline newsroom OSINT
training that includes Maltego, the Community Edition is the
realistic entry point; institutional partners cover the
Professional and Enterprise tier work.

Platform applicability: not platform-specific in the
social-platform sense. Maltego works across all platforms via
configured transforms; coverage depth shifts with which
commercial transform packs an institutional licence enables.

## How to access

Free download of the Community Edition from maltego.com; account
creation required. Professional and Enterprise tiers are
commercial products; access through Maltego Technologies' sales
process. Trained analyst capacity is part of the deployment
profile; Maltego is not a tool an untrained user runs defensibly.

## Cost (current as of 2026-05)

Freemium. Community Edition is free; Professional and Enterprise
tiers are paid commercial products. The toolkit's inventory records the freemium framing without specific
2026 figures for the Professional and Enterprise tiers. Vendor
pricing on commercial OSINT tools moves; verify current pricing
directly through Maltego Technologies' sales process before
procurement.

Community Edition is operationally adequate for individual
frontline newsroom use within its feature limits, and the toolkit
lists Maltego as primary on that accessibility ground rather than
on the Enterprise pricing tier.
For institutional deployments of Professional or Enterprise scope,
the cost banding is institutional-tier and partner-mediated access
(through a research lab, university OSINT programme, or
fact-check coalition's institutional licence) is the realistic
path for typical SEA newsroom users.

## Quickstart

1. Download Maltego Community Edition from maltego.com and create a
 free account.
2. Install on the analyst desktop and configure the data hub with
 the free transforms relevant to the investigation type.
3. Begin with a scoped entity: a known suspect domain, a single
 account at the centre of a CIB finding, a known infrastructure
 address.
4. Run an initial transform pass; review the returned related
 entities; apply filters before expanding further (the
 "hairball" caveat in Limitations is real).
5. Iterate node expansion with discipline; cluster related
 sub-graphs as the network's structure becomes visible.
6. Export the workspace for institutional reporting; for
 publication-grade graphics, export to Gephi for visual
 refinement.
7. Document the methodology, transform configuration, and time
 window in any published finding; cite the data sources behind
 each transform pack used.
8. For institutional deployment beyond Community Edition,
 coordinate the licence through the institutional partner's
 procurement channel rather than as an individual newsroom
 purchase.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.2 Network analysis as the primary OSINT-gold-standard tool
alongside Gephi (free open-source visualisation
alternative) and Meta Content Library (escalation-option
data source for IFCN-signatory institutional partners).

Standard combinations:

- With **Gephi** at 2C.2 – Maltego is the analysis
 workspace, Gephi is the publication-grade visualisation. The
 standard institutional workflow runs analysis in Maltego and
 exports the resulting network for visual refinement in Gephi
 before publication.
- With **CIB Mango Tree**, **Coordination
 Network Toolkit**, and **CooRTweet** at 1C.1 – these
 tools surface the existence and structure of coordination
 patterns; Maltego adds the OSINT-side infrastructure-and-actor
 enrichment around the surfaced patterns.
- With **Information Tracer** at 2C.1 – Information
 Tracer surfaces cross-platform spread of a claim; Maltego maps
 the actor and infrastructure network behind the spread.
- With **Meta Content Library** at 2C.2 as a
 partner-mediated data source where IFCN-signatory institutional
 partners contribute Meta historical data into a Maltego
 workspace for cross-source mapping.
- With **ABCDE Framework** at 2C.3 for codifying the
 mapped network in public-facing analysis (Actor and Behaviour
 axes) and with **DISARM** for institutional-tier TTP
 cataloguing.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes through Maltego at T5.13 (contextual OSINT) when the case
requires multi-source actor-and-infrastructure mapping; the same
2C.2 network-structure question feeds back into [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
when the network attribution is part of the public response.

This card carries no detector signal class: Maltego produces a
non-detector relationship-mapping behavioural signal. Per Anchor 2
that signal combines with claim-extraction (2B.2), source-history
(1B.1), or content-pillar fact-check signals to support a
publishable institutional finding.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** Maltego
    produces a non-detector relationship-mapping behavioural
    signal (visual link graph), not a verdict on content
    authenticity or claim truth. The card states the signal
    class explicitly in the workflow section.

## Sources

- Maltego. *Maltego — link analysis and OSINT investigation platform*. Maltego Technologies, 2024. [maltego.com](https://maltego.com).
