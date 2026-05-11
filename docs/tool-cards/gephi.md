---
tool_id: TOOL-153
slug: gephi
name: Gephi
maintainer: Gephi consortium
type: non-detector
outline_cells:
 - {id: "2C.2", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: desktop
cost: free
documented_country_use: []
tags: [network-visualisation, centrality-metrics, behaviour, free-os, civil-society-alternative, publication-graphics]
---

# Gephi

**Publisher:** [gephi.org](https://gephi.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Free, open-source desktop network-visualisation platform that
    maps complex relationships and computes centrality metrics
    (degree, betweenness, closeness) to identify key nodes in
    coordinated operations. The 2C.2 free open-source alternative
    to Maltego for civil-society partners producing
    publication-grade network graphics, and the standard
    visualisation step downstream of CooRTweet, Mango Tree, and
    Maltego analysis.

## What it does

Gephi is a desktop network-visualisation tool: it ingests network
data (nodes plus edges, with optional weight and attribute
columns), renders interactive layouts, and computes the standard
graph-theoretic centrality metrics that surface which nodes are
structurally central to a network. The platform's distinguishing
operational value sits at the publication-graphics layer:
analyst-grade interactive workspace plus configurable layout
algorithms (ForceAtlas, Fruchterman-Reingold, Yifan Hu) plus
exportable vector graphics make Gephi the standard tool for
turning a CIB-tool's raw output into a published network image
that reads cleanly at print resolution and on screen.

The tool fits 2C.2 as the visualisation step downstream of analysis
work elsewhere in the toolkit. CooRTweet (CooRTweet (with CooRnet predecessor)) produces the
network object; Maltego produces the OSINT enrichment;
Mango Tree (CIB Mango Tree) produces the interactive CIB pattern. Gephi
is what those analysis steps export to when the published
investigation needs a visual that holds up under reader scrutiny.

## When to use it

- A CIB finding has been produced through CooRTweet,
 Mango Tree, or another analysis tool, and the
 investigation needs a publication-grade visual of the resulting
 network.
- A civil-society partner does not have institutional Maltego
 licensing and needs the open-source alternative for both analysis
 and visualisation; Gephi covers the visualisation layer
 competently and partial analysis layers via plug-ins.
- A regional research lab is computing centrality metrics on a
 network to identify broker nodes (the documented Bellingcat
 bot-network broker-node case ) and needs the
 metric-computation plus visual-rendering combination.
- A trained analyst is producing the methodology section of a
 published investigation and needs the layout configuration plus
 metric values as part of the methodological artefact.

## Limitations

!!! info "Limitations"
    - Steep learning curve. Gephi is not a no-code
    tool; layout algorithms, attribute encoding, and metric
    configuration require analyst training.
    - Significant computational resources for large datasets. Networks above a certain node-and-edge count strain
    the desktop client; institutional users running large-scale
    visualisations work on dedicated workstations rather than
    laptops.
    - Visualisation tool, not a primary analysis tool. The metric
    computation is real and useful, but the upstream network
    assembly typically happens elsewhere (CooRTweet, Mango Tree,
    Maltego, custom Python pipelines). For frontline operations
    without that upstream capacity, Gephi alone does not produce
    a CIB finding.
    - The analysis depth depends on the data preparation done
    upstream. A clean network export from CooRTweet produces a
    defensible visualisation in Gephi; a poorly scoped or
    poorly cleaned export produces a misleading visualisation
    regardless of the layout algorithm chosen.

## Privacy and threat model

Gephi runs locally on the analyst's desktop; the network dataset
stays on local infrastructure during analysis and visualisation.
There is no upstream data flow to a cloud service intrinsic to the
tool itself, which makes Gephi appropriate for surveillance-
environment work where keeping the dataset local matters (Sri
Lanka, Laos contexts).

The threat model that matters here is editorial: a published
network visualisation that names accounts has the same publication-
discipline considerations as any other named-actor research output.
Local legal regimes (Indonesia's UU ITE/PDP, Malaysia's CMA Section
233 and 3R speech laws, Thailand's lèse-majesté constraints, Sri
Lanka's OSA framework, the Philippines's COMELEC Resolution 11064
during election periods) each shape what cited network findings
can carry into local publication without secondary legal risk
. The visualisation tool itself is
neutral; the publication discipline around the resulting image is
where the risk concentrates.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant for CekFakta
 partner research-layer work, MAFINDO institutional analysis,
 university OSINT training programmes.
- **Laos:** language-agnostic; appropriate for surveillance-
 environment work because local execution keeps the dataset on
 the analyst's machine. The structural gap for Lao 2C.2 work is
 upstream (IFCN-signatory access to MCL is unavailable, OSINT
 analyst capacity is thin) rather than at the visualisation
 step itself.
- **Malaysia:** language-agnostic; relevant for Sinar Project,
 Bernama, and academic-research uses on Malaysian content.
- **Philippines:** language-agnostic; relevant for
 #FactsFirstPH research-layer work and Rappler / VERA Files
 network-analysis output.
- **Sri Lanka:** language-agnostic; appropriate for
 Watchdog and Hashtag Generation institutional research where
 local-execution privacy properties matter.
- **Thailand:** language-agnostic; relevant for Thai PBS,
 AFP Thailand, and Cofact research-layer use.

Platform applicability: not platform-specific. Gephi visualises any
network the analyst can shape into the node-and-edge schema; data
sources are upstream (Facebook, Telegram, X, news-source corpus,
DNS infrastructure) and the visualisation is platform-agnostic.

## How to access

Free download from gephi.org. The platform runs on Windows, macOS,
and Linux desktop systems; no account creation, no fee, no licence
restriction beyond the open-source licence terms. Plug-ins are
available through the in-application repository for additional
analysis features (layouts, metrics, importers); the core feature
set is sufficient for standard publication-graphics work.

## Cost (current as of 2026-05)

Free. Open-source. The platform is community-maintained with no
commercial-tier model. The structural cost is analyst time —
Gephi's learning curve is real and competent visualisations
require iteration on layout and attribute encoding.

## Quickstart

1. Download Gephi from gephi.org and install on the analyst
 desktop.
2. Prepare the network dataset upstream: nodes and edges in CSV
 format, with optional weight and attribute columns. Standard
 exports from CooRTweet, Mango Tree, and
 Maltego shape cleanly into this schema.
3. Open Gephi and import the dataset; configure the data laboratory
 columns (node attributes, edge weights).
4. Run a layout algorithm; ForceAtlas 2 is the standard starting
 point for amplification-network visualisation; iterate
 parameters until the network's structure reads cleanly.
5. Compute centrality metrics (degree, betweenness, closeness)
 and encode the values as node size or colour to surface broker
 nodes.
6. Apply filters and label the structurally important nodes; iterate
 on the legend and visual encoding for publication readability.
7. Export the visualisation as vector graphic (SVG or PDF) for
 institutional reporting; document the layout algorithm and
 metric configuration in the methodology.
8. Cite Gephi per the platform's standard academic citation in any
 published investigation.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 2C.2 Network analysis as the free open-source civil-society
alternative alongside Maltego (primary OSINT gold
standard) and Meta Content Library (escalation-option
data source for IFCN-signatory institutional partners). Of the
three 2C.2 entries, Gephi is the only free open-source desktop
tool covering the visualisation step end-to-end.

Standard combinations:

- With **Maltego** at 2C.2 – the standard institutional
 workflow runs analysis in Maltego and exports the resulting
 network for visual refinement in Gephi before publication.
- With **CooRTweet** at 1C.1 – the standard academic
 workflow runs CLSB analysis in R via CooRTweet and exports the
 network object for visualisation in Gephi.
- With **CIB Mango Tree** at 1C.1 – interactive CIB
 pattern surfacing in Mango Tree, exported to Gephi for
 publication-grade rendering.
- With **Coordination Network Toolkit** at 1C.1 for the
 framework-level analysis whose network output Gephi visualises.
- With **Information Tracer** at 2C.1 for visualising the
 amplifier-set network surfaced by cross-platform tracing.
- With **ABCDE Framework** at 2C.3 for codifying the
 mapped network in the Distribution and Behaviour axes of
 public-facing analysis.

Decision-tree references: visualisation steps appear at the
[T5 escalation](../decision-trees/t5-escalation.md) terminal nodes
(T5.16 defensible conclusion, T5.17 external expert escalation) and
inside the [T7 tipline routing](../decision-trees/t7-tipline-routing.md)
published-output flow where the case requires a published network
image.

This card carries no detector signal class: Gephi produces no
new signal of its own; it is the visualisation layer for network
signals produced upstream by analysis tools. Per Anchor 2 the
visualised network combines with claim-extraction (2B.2), source-
history (1B.1), or fact-check signals to support a publishable
institutional finding.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** Gephi
    produces no detector signal of its own; it visualises
    networks produced upstream by analysis tools. The card
    states this in the workflow section explicitly.

## Sources

- Gephi Consortium. *Gephi — open-source network analysis and visualisation platform*. Gephi Consortium, 2024 (open-source, LGPL). [gephi.org](https://gephi.org).
