---
tool_id: TOOL-138
slug: coortweet
name: CooRTweet (with CooRnet predecessor)
maintainer: Nicola Righetti and Fabio Giglietto
type: non-detector
outline_cells:
 - {id: "1C.1", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [cib, network-analysis, behaviour, r, coordinated-link-sharing, meta-content-library]
---

# CooRTweet (with CooRnet predecessor)

**Publisher:** [github.com/nicolarighetti/CooRTweet](https://github.com/nicolarighetti/CooRTweet) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free, open-source R package by Righetti and Giglietto that
    detects coordinated link-sharing and behavioural networks across
    social-media datasets, with native support for Meta Content
    Library data. The R-native alternative in the institutional CIB
    ladder for analysts already inside the IFCN-signatory MCL gate.

## What it does

CooRTweet is the generalised successor to the CooRnet R package and
implements the coordinated-link-sharing-behaviour (CLSB) methodology
originally developed for Twitter analysis. It takes a social-media
dataset (most cleanly Meta Content Library extracts, but flexible
across platforms) and identifies clusters of accounts that share
the same URLs (or other content tokens) within tight time windows,
which is the canonical signature of an amplification operation. The
package was published with peer review in Computational Communication
Research 7(1) 2025 and is the most cited CIB methodology in
academic communication research.

The "with CooRnet predecessor" framing matters operationally.
CooRnet was the original R package, but its data ingest depended on
CrowdTangle, which Meta deprecated in August 2024. CooRTweet was
written as the generalised successor that decouples the methodology
from any single data source: it works on any post-level dataset the
analyst can shape into the package's expected schema. For SEA
newsrooms with IFCN signatory status (Mafindo, Rappler, VERA Files,
selected partners), Meta Content Library is the natural data source
for CooRTweet runs because the IFCN gate is also the access path to
Meta historical data; for newsrooms outside that gate, the package
runs against any post-level extract the analyst can assemble.

## When to use it

- Your operation is an IFCN-signatory partner with Meta Content
 Library access and you want to run coordinated-link-sharing
 analysis on Facebook or Instagram historical data.
- You are working in an R environment and need a peer-reviewed
 CLSB methodology that is the academic-community standard for
 publication-grade CIB findings.
- An election-cycle investigation in Indonesia or the Philippines
 needs coordinated-amplification analysis on a multi-month dataset
 where temporal clustering of URL or content shares is the
 primary signal.
- You are training researchers in a regional university partnership
 and want a tool whose underlying methodology is the most-cited
 reference in the academic CIB literature.

## Limitations

!!! info "Limitations"
    - Requires R proficiency. The package is not a no-code tool; an
    analyst unfamiliar with R will spend significant ramp-up time
    before producing usable output.
    - Meta Content Library access is gated to IFCN-signatory
    research and fact-checking organisations. Mafindo, Rappler,
    and VERA Files have access; Laos has no IFCN signatory and
    therefore no MCL access path. Other SEA newsrooms vary.
    - CooRnet (the predecessor) depended on CrowdTangle, which Meta
    deprecated in August 2024. Older tutorials referencing CooRnet
    may assume CrowdTangle data flows that no longer exist;
    transition to CooRTweet was explicitly designed to remove this
    dependency.
    - Coordinated-link-sharing analysis surfaces necessary but not
    sufficient evidence of inauthenticity. Authentic political
    communities also share the same links in tight time windows;
    the analyst's interpretation is part of the method.

## Privacy and threat model

CooRTweet runs locally on the analyst's machine within an R
environment. The dataset stays on local infrastructure during
analysis. The privacy concentration shifts to the input data source:
Meta Content Library has its own data-handling and disclosure
constraints attached to the IFCN access agreement, and any analysis
output that names accounts is bound by those constraints.

For surveillance-environment work in Sri Lanka or Laos, the local-
execution model is appropriate but the IFCN gate often blocks the
underlying MCL data source. Where MCL access is unavailable, an
analyst can substitute any post-level dataset they can assemble
through other means (Telegram exports, custom scrapes for fringe
platforms, archived Twitter API data where still accessible) at the
cost of losing MCL's coverage of the largest SEA-region commercial
platforms.

## Country and platform applicability

- **Indonesia:** language-agnostic; Mafindo's IFCN signatory
 status gives access to the MCL data path that CooRTweet handles
 natively. Relevant for buzzer-network and election-cycle analysis.
- **Laos:** no IFCN signatory; no MCL access path; the
 package can run on any other post-level dataset the analyst
 assembles, at the cost of losing the dominant Lao-relevant
 Facebook data source. Honest gap.
- **Malaysia:** Bernama MyCheck.My / Sebenarnya researchers
 with IFCN-equivalent access can run CooRTweet on MCL data.
- **Philippines:** Rappler and VERA Files have IFCN signatory
 status; the package is operationally available to the
 #FactsFirstPH research layer.
- **Sri Lanka:** FactCheck.lk's IFCN status was reported
 expired (regional case documentation
 Lanka); MCL access status should be reverified before relying on
 CooRTweet for SL work. Where MCL is unavailable, the package
 still runs on Telegram and other non-Meta extracts.
- **Thailand:** AFP Fact Check Thailand's regional access
 via the AFP Medialab partnership may include MCL data flows;
 verify before relying on the path.

Platform applicability: native fit with Meta Content Library data
(Facebook, Facebook Groups). Works on Telegram, historical Twitter
extracts (X where still accessible), and any other post-level
extract the analyst can shape to the package's schema.

## How to access

Free download from the CRAN R repository or the package's GitHub
mirror. Install via `install.packages("CooRTweet")` inside an R
session, or from source via `devtools::install_github()` per the
README. Meta Content Library access is the data-source gate, not
the package itself; the IFCN signatory application path is a
separate Meta workflow that institutional partners apply for
independently.

## Cost (current as of 2026-05)

Free. Open-source. The package itself imposes no cost. The Meta
Content Library access path that the package handles natively is
also free for IFCN-signatory partners but is gated by IFCN status
rather than priced. The package is free in software terms but the
most useful data source behind it is free-but-gated; for SEA
newsrooms outside the IFCN
gate (notably anywhere in Laos), the package's cost is functionally
the cost of substitute data assembly.

## Quickstart

1. Install R 4.x and an IDE such as RStudio.
2. Install the package: `install.packages("CooRTweet")`.
3. If Meta Content Library access is available, follow the
 package documentation to ingest MCL post-level data; otherwise,
 prepare a post-level extract from your alternative source
 following the package's expected schema.
4. Choose the coordination construct: shared-URL coordinated link
 sharing is the canonical CooRTweet test, but the package
 supports other behavioural similarity constructs.
5. Set the time window (typical: 60 seconds for very tight
 coordination, several minutes for amplification networks).
6. Run the coordination-detection function and inspect the output
 network object.
7. Export the network for visualisation in Gephi or for
 further analysis in Coordination Network Toolkit's
 similarity construct.
8. Document the methodology and parameters in any published
 finding; cite the Righetti and Giglietto Computational
 Communication Research 7(1) 2025 paper for the underlying
 methodology.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 1C.1 Institutional CIB detection as the R-native alternative
alongside CIB Mango Tree (Python interactive) and Coordination Network Toolkit (R or Python framework). The three
together form a complementary open-source ladder; CooRTweet is the
preferred path when the analyst is in R and the data is MCL.

Standard combinations:

- With **Meta Content Library** at 2C.2 as the IFCN-gated
 data source.
- With **CIB Mango Tree** for triangulation on the same
 dataset.
- With **Gephi** at 2C.2 for publication-grade
 visualisation of CooRTweet network outputs.
- With **Yudistira (MAFINDO)** at 2B.2 for Bahasa-specific
 claim extraction on the posts within identified clusters.
- With **ABCDE Framework** and **DISARM** at
 2C.3 for codifying the behavioural pattern in respectively
 public and institutional reporting.

This card carries no detector signal class: CooRTweet produces a
non-detector behavioural-pattern signal class. Per Anchor 2, that
signal combines with claim-extraction (2B.2) or source-history
(1B.1) to support a publishable institutional finding.

## Override notes

!!! note "Override notes"
    - **Meta Content Library gating pointer (meta-content-library-
    gating-pointer):** the package's most useful data path is
    gated to IFCN-signatory partners. For SEA newsrooms outside
    the gate (notably any Lao operation), the package is still
    usable on alternative datasets, but the bulk of Facebook-side
    coordination evidence is functionally inaccessible. Cost
    section above states this concretely.

## Sources

- Righetti, N. and Giglietto, F. *CooRTweet: Coordinated Retweeting Detection in R*. Computational Communication Research, 7(1), 2025. [github.com/nicolarighetti/CooRTweet](https://github.com/nicolarighetti/CooRTweet).
- Righetti, N. and Giglietto, F. *CooRTweet R package*. CRAN. [cran.r-project.org/package=CooRTweet](https://cran.r-project.org/package=CooRTweet).
