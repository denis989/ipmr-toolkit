---
tool_id: TOOL-149
slug: sinar-project-imap
name: Sinar Project iMAP (Internet Monitoring Action Project)
maintainer: Sinar Project (Malaysia)
type: non-detector
outline_cells:
 - {id: "2C.1", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: [MY]
tags: [network-monitoring, censorship, blocking-detection, ooni, malaysia, civil-society, sea-specific]
---

# Sinar Project iMAP (Internet Monitoring Action Project)

**Publisher:** [sinarproject.org](https://sinarproject.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Free, open civil-society network-monitoring platform run by Sinar
    Project, built on the OONI infrastructure to detect censorship,
    blocking, and structural network interference across ten South
    and Southeast Asian countries. Documented detection of MCMC
    blocking against MalaysiaNow and Malaysia-Today; the SEA-specific
    civil-society alternative in 2C.1 where claim-monitoring
    intersects with state-imposed access restrictions.

## What it does

iMAP runs OONI-based network probes from volunteer measurement points
across ten South and Southeast Asian countries and produces
structured censorship and blocking reports: which sites and services
appear blocked, from which network vantage points, when, and
through which mechanism (DNS injection, TCP reset, TLS interference,
HTTP redirection). The outputs are network-level findings, not
content-level; iMAP is not a tool for verifying whether a circulating
claim is true, but for measuring whether a competing fact-check
outlet has been blocked or whether a platform's accessibility has
been degraded for users in a specific network.

The tool fits 2C.1 because in several focus countries (Malaysia
most prominently) monitoring the disinformation environment is
inseparable from monitoring the access environment. When competing
news outlets are blocked at the network layer, the user's question
"is this what's circulating" requires an answer to "what can the
user actually reach" first. iMAP is purpose-built for that
intersection, and unlike the other 2C.1 entries it is grounded in
SEA civil society's own infrastructure rather than imported from
broader academic or commercial monitoring stacks.

## When to use it

- A Malaysian fact-checker is preparing an analysis on what
 alternative-media coverage of a story is reaching the public and
 needs evidence of whether competing outlets have been blocked at
 the network layer (the documented MalaysiaNow / Malaysia-Today
 case).
- A regional civil-society partner is producing a pre-election
 monitoring report and needs the network-access layer alongside the
 content-monitoring layer; what reaches users in each country, not
 only what is being said.
- A researcher in Indonesia, Sri Lanka, Thailand, or another iMAP
 measurement-coverage country needs a measurement record of whether
 a fact-check outlet's URL is currently reachable from local
 networks.
- An institutional partner working with frontline civil-society
 organisations in surveillance-environment contexts needs the OONI-
 grounded measurement record to corroborate complaints of platform
 or outlet blocking.

## Limitations

!!! info "Limitations"
    - Network-level monitoring, not content monitoring.
    iMAP reports on whether a site or service is reachable from a
    probe location, not on what is being said within reachable
    services. For content-monitoring, pair with Information Tracer (cross-platform spread) or Media
    Cloud (news-source corpus).
    - Coverage depends on volunteer-run measurement nodes. Dense
    coverage in countries with active civil-society network
    partners (Malaysia in particular) is not matched in countries
    with thinner volunteer infrastructure; readers of iMAP reports
    should check the measurement-density notes that accompany
    each finding.
    - English-language interface; reports are multilingual where
    country contributors translate them. The platform's
    operational language for analyst work is English.
    - Network monitoring intersects with surveillance-environment
    threat models. Running OONI probes from a personal device in
    a network where blocking is being measured can itself be a
    flagged action depending on local enforcement; institutional
    partners run probes through hardened infrastructure rather
    than personal devices.

## Privacy and threat model

iMAP probes are network-side measurements run from configured
measurement nodes; the volunteer-or-institutional-run probe is the
party generating the measurement traffic, not a remote target. For
the operator of a probe, the threat model is local: in some
jurisdictions running censorship-measurement traffic from a personal
device may itself draw enforcement attention, and institutional
partners operate the probes through hardened infrastructure with
appropriate operational security.

For a researcher reading iMAP data without running probes, the
data path is open and public; the measurement record is published
on the iMAP and OONI explorers for any user to query. The threat
model that matters here is editorial: cited findings about state
blocking activity in jurisdictions with active enforcement
practices (Malaysia's MCMC, Thailand's MDES, Sri Lanka's Online
Safety Act regime) carry implications for what cited
findings can be republished locally without secondary legal risk.

!!! danger "Source-protection override (S4 — doxxing or vulnerable-community targeting)"
    iMAP findings that name independent media, activist sites, or
    minority-community resources as blocked can themselves
    identify the operators and audiences of those resources to
    adversaries. Mitigation steps:

    1. Before publishing iMAP findings that name specific blocked
    sites, audit the operator-and-audience side of those
    sites for activists, journalists, ethnic or religious
    minorities, LGBTQ+ groups, or other vulnerable
    communities.
    2. Use blocking-pattern aggregates rather than per-site
    call-outs where the per-site call-out would expose the
    operator's identity beyond what is already public.
    3. Coordinate with Sinar Project or the OONI partner before
    publishing operator-identifying findings in surveillance-
    risk jurisdictions; the measurement coalition has
    documented disclosure protocols.

## Country and platform applicability

- **Indonesia:** iMAP measurement coverage exists in Indonesia
 through OONI volunteer infrastructure; relevant for monitoring
 blocking events on alternative-media outlets where they occur.
- **Laos:** OONI measurement coverage in Laos is structurally
 thinner than in Malaysia or Indonesia; Lao civil-society
 measurement-volunteer infrastructure is the coverage gap. Where
 iMAP / OONI measurements are present, they remain useful;
 density-of-evidence is the operational caveat.
- **Malaysia:** primary deployment country (Sinar Project is
 Malaysia-based). Documented detection of MCMC blocking against
 MalaysiaNow and Malaysia-Today. Most operationally useful for the
 toolkit's six-country audience in this country.
- **Philippines:** OONI measurement coverage exists; relevant
 for monitoring access conditions on independent outlets where
 blocking events occur.
- **Sri Lanka:** OONI measurement coverage exists;
 particularly relevant under the Online Safety Act regime where
 network-level blocking of fact-check or critical outlets is a
 live concern.
- **Thailand:** OONI measurement coverage exists; relevant
 for monitoring lèse-majesté-related and political-content blocking
 events.

Platform applicability: not platform-specific in the social-media
sense. iMAP operates at the network layer, not the platform layer.
Where a Facebook, X, TikTok, or Telegram URL is blocked, iMAP can
detect the blocking; what is happening on those platforms when
reachable is the work of the other 2C.1 and 1C.1 entries.

## How to access

Free public access to the iMAP explorer at the Sinar Project iMAP
website. The platform publishes country dashboards, blocking-event
reports, and the underlying OONI measurement records for query.
Researchers and civil-society partners can also volunteer to run
measurement nodes through the OONI Probe app (mobile and desktop)
or through dedicated measurement infrastructure for institutional
deployment. Volunteering as a probe operator is documented through
the OONI partner-onboarding process and Sinar Project's own
volunteer channels.

## Cost (current as of 2026-05)

Free. Open-source. The platform is grant-funded through Sinar
Project's funding stack and is not user-priced. The structural
cost is volunteer time for probe operators and analyst time for
researchers reading the data; for institutional deployment the
cost shifts to the institution running the dedicated measurement
node infrastructure.

## Quickstart

1. Open the Sinar Project iMAP website and navigate to the country
 dashboard for the focus country.
2. Review the recent blocking-event reports: which sites have been
 measured as blocked, from which networks, in what time window.
3. For a specific URL of interest (a competing fact-check outlet,
 a platform endpoint), search the OONI explorer for that URL's
 measurement record.
4. Cross-reference the iMAP finding with content-side monitoring
 from Information Tracer or Media Cloud where
 the question is what reached users on currently-reachable
 surfaces.
5. For institutional partners deploying their own measurement
 infrastructure: follow the OONI Probe and Sinar Project partner
 onboarding documentation; route measurement traffic through
 dedicated infrastructure rather than personal devices.
6. Document the iMAP-measured access conditions in any published
 investigation alongside the content findings; cite the Sinar
 Project iMAP and OONI Explorer URLs and measurement
 identifiers for reproducibility.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.1 Automated claim monitoring as the SEA-specific civil-
society alternative alongside Information Tracer (paid
mid-tier cross-platform tracer), Media Cloud (free academic
news-source corpus), and FactFlow AI (paid Telegram-
specific alternative). Of the four 2C.1 entries, iMAP is the only
SEA-grounded civil-society platform and the only one purpose-built
for the network-access layer.

Standard combinations:

- With **Sebenarnya AIFA** at 2B.1 as the
 independent-monitoring counterweight in the Malaysian information
 environment. AIFA is government-operated; iMAP is independent
 civil-society. Used together, they cover the Malaysian
 information environment at both layers: what the state has said
 about a claim (AIFA) and what alternative outlets are or are not
 reaching the public (iMAP).
- With **Information Tracer** or **Media Cloud**
 at 2C.1 for the content layer that complements iMAP's network
 layer.
- With **CIB Mango Tree** at 1C.1 for the platform-side
 CIB analysis that complements iMAP's network-side blocking
 analysis.
- With **Gephi** at 2C.2 for visualisation of network-
 level findings where appropriate.
- With **ABCDE Framework** at 2C.3 – iMAP's network-access
 findings codify under the Distribution axis where state blocking
 affects what reaches the audience, and under the Effect axis
 where the effect is measured at the access layer rather than at
 the engagement layer.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes through iMAP at T5.13 (contextual OSINT) when an operation
involves suspected state blocking of competing coverage in Malaysia
or Sri Lanka, and feeds the 2C.1 access-layer view that single-
platform CIB tools cannot resolve.

This card carries no detector signal class: iMAP produces a
non-detector network-access behavioural signal. Per Anchor 2 that
signal combines with content-layer signals from the other 2C.1
entries or from 1C.1 CIB tools to support a publishable
institutional finding.

## Override notes

!!! note "Override notes"
    - **Malaysia documented use
    (b4-score-3-Malaysia-MalaysiaNow-blocking):** the documented
    detection of MCMC blocking against MalaysiaNow and Malaysia-
    Today is the operational anchor case for this card. Country
    and platform applicability records this case under Malaysia
    with cross-link to Sebenarnya AIFA's framing of
    iMAP as the independent-monitoring counterweight.

## Sources

- Sinar Project. *iMAP — Internet Monitoring Action Project*. Sinar Project, 2024. [imap.sinarproject.org](https://imap.sinarproject.org).
- Open Observatory of Network Interference (OONI). *OONI Explorer — network interference measurement data*. OONI, 2024. [explorer.ooni.org](https://explorer.ooni.org).
