---
tool_id: TOOL-141
slug: meta-content-library
name: Meta Content Library
maintainer: Meta Platforms
type: non-detector
outline_cells:
 - {id: "2C.2", role: escalation-option, density_role: escalation-option}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: web | api
cost: freemium
documented_country_use: [PH, ID]
tags: [meta-platforms, ifcn-gated, journalists-excluded, historical-data, escalation-option, combined-pattern]
---

# Meta Content Library

**Vendor:** [developers.facebook.com/docs/content-library](https://developers.facebook.com/docs/content-library) | **Type:** Non-detector | **Cost:** Freemium

!!! abstract "TL;DR"
    Meta-Platforms-controlled research access to Facebook, Instagram,
    and Threads public archive (IFCN-signatory and vetted-academic
    only; journalists formally excluded). The toolkit documents Meta
    Content Library because the Meta-platform information environment
    is impossible to describe without it; for the typical SEA
    newsroom and civil-society organisation that is not an IFCN
    signatory, the operational path is to cite Meta-Content-Library-
    derived institutional research findings as external sources
    rather than to deploy the tool directly.

## What it does

Meta Content Library is Meta Platforms' research-access product for
queryable archives of public content on Facebook, Instagram, and
Threads. The interface offers near-real-time search and API access
with filters, dashboards, and OCR-on-images, and was launched as
the replacement for CrowdTangle after Meta deprecated CrowdTangle
in August 2024. The platform is the only path to historical Meta-
platform data at meaningful scale; for institutional partners with
access, it covers the largest commercial information surfaces in
several focus countries (Facebook is the dominant social platform
in Indonesia, the Philippines, and across most of the regional
mass-market audience).

The tool fits 2C.2 as the data-source layer underneath downstream
analysis tools; CooRTweet handles MCL data natively,
Maltego can integrate MCL extracts via partner-mediated
flows, Gephi visualises the resulting networks. The card
is listed at escalation-option role rather than primary or
alternative because Meta's access terms structurally exclude most
of the toolkit's audience: ordinary frontline newsrooms, civil-
society organisations not affiliated with an IFCN signatory, and
the entirety of Lao operations (no IFCN signatory exists in Laos).

## When to use it

- Your organisation is an IFCN signatory or vetted-academic
 research partner with active Meta Content Library access and you
 are running historical analysis on Facebook or Instagram public
 data.
- You are an institutional research partner running a
 coordinated-amplification investigation through CooRTweet on MCL data; the package handles MCL extracts natively.
- You are citing a Meta-Content-Library-derived institutional
 research finding in a published investigation as an external
 source; this is the realistic path for the typical SEA newsroom
 outside the IFCN gate.
- You are *not* running the tool directly and are not an IFCN
 signatory: the realistic path is the cite-as-external-source
 redirect described in Quickstart below, not deployment.

## Limitations

!!! info "Limitations"
    - Strictly limited to vetted academic and non-profit researchers. Excludes journalists. Cannot be used for
    surveillance or commercial purposes. Researchers without
    academic or qualifying-non-profit affiliation will be rejected
    at application; this is a formal access-terms exclusion, not
    an informal practitioner-availability question.
    - 500,000-record rolling weekly retrieval cap.
    Even within the access tier, the platform imposes a hard
    ceiling that shapes what queries are feasible; long-tail
    multi-year analyses split across access cycles.
    - SOMAR VDE access tier is paid: $1,000 one-time set-up plus
    $371 per month . This tier is the institutional
    vetted-data-environment path; pricing on Meta research
    products has shifted multiple times since the August 2024
    CrowdTangle deprecation, and partnership terms 2024-2026 are
    subject to ongoing change. Verify current pricing and terms
    directly through Meta Content Library's access process before
    committing to procurement.
    - In the toolkit's six focus countries, IFCN-signatory access
    is uneven: Mafindo (Indonesia), Rappler and VERA Files
    (Philippines) are signatories with documented access; FactCheck.lk's
    Sri Lanka IFCN status was reported expired in the toolkit's
    inventory (regional case documentation for Sri Lanka), and Laos has no
    IFCN signatory at all. The toolkit's editorial position
    records this as the structural gap that shapes who in the
    region can deploy the tool versus who cites its outputs.
    - "1% of the features" of CrowdTangle is the recurring
    independent assessment of MCL's coverage gap relative to its
    predecessor. The CrowdTangle shutdown framing remains the
    operative public-research reading of what was lost in the
    transition.

## Privacy and threat model

The threat model that matters here is operator identity. Meta
Content Library is operated by Meta Platforms, the same operator
whose platforms generate the content under study. Queries an
analyst submits travel to Meta infrastructure and are visible to
Meta under the access agreement's terms. Meta sets the eligibility
criteria, sets the retrieval caps, sets the pricing on the SOMAR
VDE tier, and has shifted partnership terms multiple times since
the August 2024 CrowdTangle deprecation. The access path is not a
neutral data utility; it is a Meta-Platforms-controlled research
channel with terms that have shifted multiple times across
2024–2026 and may continue to change.

For the typical SEA newsroom or civil-society organisation, the
operator-identity consideration combines with the formal exclusion
of journalists from the access terms to make MCL not a tool the
operation deploys. For institutional partners who do qualify,
standard institutional data-handling discipline applies: data-
protection officer review of the access agreement, retention
policy review, controlled access logs, and editorial review of
what cited findings can carry into publication under local legal
regimes (Indonesia's UU ITE/PDP, the Philippines's COMELEC
Resolution 11064 during election periods, Thailand's lèse-majesté
constraints, Sri Lanka's OSA framework, Malaysia's CMA Section 233
and 3R laws per regional research regulatory framing).

The toolkit's editorial position, drawn from the broader scope of
work, is that Meta Content Library is structurally inaccessible to
the bulk of the toolkit's audience and that the realistic path is
to cite MCL-derived institutional research findings as external
sources, with appropriate scrutiny of the originating research's
methodology and access-terms compliance, rather than to plan
direct deployment.

## Country and platform applicability

- **Indonesia:** documented institutional access through
 Mafindo's IFCN signatory status. CekFakta partner research uses
 MCL data through Mafindo where the access path supports the
 investigation.
- **Laos:** no IFCN signatory exists in Laos; no MCL access
 path. Honest gap: the dominant Lao-relevant Facebook information
 environment is structurally unavailable to Lao civil-society or
 newsroom operations through this channel. For Lao 2C.2 work, the
 cited-as-external-source path through institutional partners
 outside Laos is the realistic option.
- **Malaysia:** mixed access; Sebenarnya / Bernama
 researchers with IFCN-equivalent vetted access can run MCL
 queries on Malaysian public data, but no Malaysian IFCN signatory
 is recorded. Verify access status
 before relying on the path.
- **Philippines:** documented institutional access through
 Rappler and VERA Files' IFCN signatory status. The
 #FactsFirstPH research layer uses MCL data through these
 signatories where the access path supports the investigation.
- **Sri Lanka:** FactCheck.lk's IFCN signatory status was
 reported expired. MCL access status should be reverified before
 relying on the path; in the interim, the cited-as-external-source
 path through institutional partners outside Sri Lanka is the
 realistic option.
- **Thailand:** AFP Fact Check Thailand's regional
 partnership through AFP Medialab may include MCL data flows;
 verify access status before relying on the path. No
 Thailand-specific IFCN signatory is recorded in the toolkit's
 toolkit's inventory for direct access.

Frontline-no-access disclaimer applies across all six countries:
the listing here is for awareness of what institutional research
partners with IFCN signatory or vetted-academic access can produce.
Frontline SEA newsrooms generally cannot reach MCL directly and
should treat MCL output as a citable source from a partner, not as
an in-house tool to deploy.

Platform applicability: Facebook and Facebook Groups, Instagram, Threads.
Cross-platform breadth beyond the Meta-platforms set is not part
of this card's coverage; for cross-platform work the entries in
2C.1 (Information Tracer; Sinar Project iMAP)
are the appropriate complements.

## How to access

IFCN-signatory and vetted-academic access through Meta's access
application process, documented at the Meta Content Library access
URL Meta publishes for current researchers. The application
process verifies institutional affiliation, research purpose, and
data-handling commitments; researchers without academic or
qualifying-non-profit affiliation are rejected at this stage.

For the typical SEA newsroom or civil-society organisation that
does not have IFCN-signatory or qualifying-academic affiliation,
the realistic path is partner-mediated: identify an institutional
research partner who has access, work through that partner's
published research output, and cite the partner's MCL-derived
findings as external sources in your own published work.

The SOMAR VDE access tier is documented  at
$1,000 one-time set-up plus $371 per month (January 31 2026
pricing). This tier is for institutional vetted-data-environment
deployment; pricing has shifted across the 2024-2026 period and
should be verified directly with Meta Content Library before
procurement. Partnership terms 2024-2026 have not been
comprehensively documented;
Meta's research-access policies have changed multiple times in this
period and continue to be subject to vendor change.

## Cost (current as of 2026-05)

Free for IFCN-signatory and vetted-academic access at the standard
tier. SOMAR VDE access tier: $1,000 one-time set-up plus $371 per
month  (January 31 2026 pricing).
Verification recommended directly with Meta Content Library before
procurement; pricing on Meta research products has shifted multiple
times since the August 2024 CrowdTangle deprecation and partnership
terms 2024-2026 are subject to ongoing change.

The headline-free tier is gated to a researcher population that
excludes most of the toolkit's audience, and the paid SOMAR VDE
tier is institutional infrastructure pricing rather than
individual-newsroom procurement range. The structural cost for SEA
frontline operations is the access barrier itself, not the dollar
figure.

## Quickstart

(Not applicable to typical SEA frontline use. The realistic path is
not "run Meta Content Library" but "cite a Meta-Content-Library-
derived institutional research finding as an external source.")

1. If your operation is an IFCN signatory or qualifying academic
 partner: apply for Meta Content Library access through Meta's
 published application process; budget the analyst time for
 onboarding, terms-of-service review, and data-handling
 discipline that the access agreement requires.
2. If your operation is *not* IFCN-signatory or qualifying-academic
 (which is the case for the majority of the toolkit's audience),
 identify an institutional research partner who is. For
 Indonesia, Mafindo is the documented signatory; for the
 Philippines, Rappler and VERA Files; for the other four focus
 countries, the access path is partner-mediated through outside
 institutional research labs.
3. When citing an MCL-derived finding, confirm with the originating
 partner the time window, the query parameters, and the data-
 licence terms under which the analysis was conducted. Cite the
 partner's published research and methodology, not "Meta Content
 Library" as if your operation had run it directly.
4. Apply scrutiny to the originating research's methodology; MCL
 has the 500K-record weekly cap and the "1% of CrowdTangle's
 features" critique; published findings carry those structural
 limits whether or not the originating researcher named them
 explicitly.
5. For the Lao and (likely) Sri Lankan cases where no IFCN
 signatory access path exists, route through outside-region
 institutional research partners and treat the resulting MCL-
 derived findings with the same external-source citation
 discipline.
6. For institutional partners considering direct procurement of
 the SOMAR VDE tier: verify current pricing and partnership
 terms with Meta Content Library directly; the inventory figure
 ($1,000 set-up plus $371 per month) is the January 31 2026
 record and may have shifted.

## In the toolkit's workflow

Behaviour-pillar non-detector platform per Architectural Anchor 1.
Sits in 2C.2 Network analysis as escalation-option only; listed
because the Meta-platform information environment in Indonesia,
the Philippines, and the broader regional mass-market audience
cannot be described without it, but with the deployment
recommendation routing through IFCN-signatory institutional
partners rather than to the typical SEA newsroom or civil-society
organisation.

The toolkit documents Meta Content Library because the Meta-
platform information environment cannot be described without it;
deployment recommendations sit with IFCN-signatory
institutional partners. For the typical SEA newsroom and
civil-society organisation that is not IFCN-signatory, the
operational path is to cite Meta-Content-Library-derived
institutional research findings as external sources, not to
deploy the tool directly.

Standard combinations (when partner-mediated or institutional):

- With **CooRTweet** at 1C.1 – CooRTweet handles MCL data
 natively for IFCN-signatory partners running coordinated-link-
 sharing analysis on Facebook or Instagram historical data. This
 is the canonical analysis pairing where MCL access is available;
 CooRTweet's card explicitly cross-references MCL as the IFCN-
 gated data source.
- With **Maltego** at 2C.2 – partner-mediated flow where
 IFCN-signatory institutional partners contribute MCL extracts
 into a Maltego workspace for cross-source actor-and-
 infrastructure mapping.
- With **Gephi** at 2C.2 – visualisation layer for any
 network output downstream of MCL-data analysis.
- With **Graphika** at 1C.1 – Graphika is similarly
 enterprise/access-gated; its MCL integration is one of the data
 sources behind its multi-platform analysis. The toolkit's
 editorial framing on both tools is parallel: cite institutional
 research partners' published work rather than plan direct
 deployment.
- With **ABCDE Framework** and **DISARM** at
 2C.3 for codifying the resulting findings in respectively
 public-facing analysis and institutional reporting.

This card carries no detector signal class: Meta Content Library
provides a non-detector data path through which behavioural
signals (coordinated link sharing, amplification timing, network
structure) are produced by downstream analysis tools. Per Anchor 2
those signals combine with claim-extraction (2B.2), source-history
(1B.1), or fact-check signals to support a publishable
institutional finding.

## Override notes

!!! note "Override notes"
    - **Escalation-option only, IFCN-signatory gate
    (e5-ifcn-signatory-only):** Meta Content Library was
    triggered by E5 (better alternatives exist: partner-mediated
    access for the toolkit's frontline audience) and
    rescued as escalation-option rather than excluded. The Cost,
    How to access, and Country and platform applicability
    sections render the gating concretely; the In the toolkit's
    workflow section frames the editorial-position statement.

    - **Journalists excluded disclaimer (journalists-excluded-
    disclaimer):** Meta's formal access terms exclude journalists
    from MCL. The Limitations admonition states this verbatim
    from inventory; the Quickstart redirect (cite as external
    source rather than deploy) is the operational consequence
    for the toolkit's primary audience of fact-checkers and
    civil-society staff who are not affiliated with a
    qualifying-academic institution.

    - **PH/ID IFCN partners regional relevance score
    (b4-score-3-PH-ID-IFCN-partners):** documented institutional
    access in Indonesia (Mafindo) and the Philippines (Rappler,
    VERA Files). The Country and platform applicability section
    records this concretely; Lao, Malaysian, Sri Lankan, and
    Thai access paths are noted as gaps or requiring direct
    verification.

## Sources

- Meta. *Meta Content Library and API — researcher access to Facebook and Instagram data*. Meta Platforms, 2024. [developers.facebook.com/docs/content-library](https://developers.facebook.com/docs/content-library).
