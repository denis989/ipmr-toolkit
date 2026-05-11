---
tool_id: TOOL-126
slug: cib-mango-tree
name: CIB Mango Tree
maintainer: Civic Tech DC (civictechdc/cib-mango-tree)
type: non-detector
outline_cells:
 - {id: "1C.1", role: primary, density_role: primary}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: MIT
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [cib, network-analysis, behaviour, python, copy-pasta-test, open-source]
---

# CIB Mango Tree

**Publisher:** [github.com/civictechdc/cib-mango-tree](https://github.com/civictechdc/cib-mango-tree) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free, MIT-licensed Python toolkit that runs Coordinated
    Inauthentic Behaviour tests over a fact-checker's own social-media
    dataset, with a "Copy Pasta Test" that surfaces near-identical
    synchronous posts across accounts. The open-source primary entry
    of the institutional CIB ladder.

## What it does

CIB Mango Tree is an interactive Python terminal toolkit that ingests
user-supplied social-media data and runs a sequence of behavioural
tests against it. The most documented test is the Copy Pasta Test,
which clusters near-identical text posts that appear across multiple
accounts within tight time windows: the canonical signal of a
coordinated amplification operation. Outputs are pattern files: lists
of accounts, post clusters, and time windows that meet the test's
similarity and synchrony thresholds. The tool does not pull from a
platform API; the analyst is responsible for assembling the input
dataset, which means the analysis runs against whatever source the
analyst can access (Meta Content Library extracts for IFCN partners,
Twitter API archives where still accessible, Telegram exports, custom
scrapes for fringe platforms).

The toolkit's value sits inside Architectural Anchor 1's behaviour
pillar: Mango Tree produces a non-detector behavioural-pattern
signal that combines with claim-extraction (2B.2) and content
provenance (1A.4) to support an institutional finding. It is not a
detector and never produces an "AI-generated" verdict; it produces a
"these N accounts posted the same string within M minutes" verdict
that a human analyst then interprets in context.

## When to use it

- A regional research lab or fact-check newsroom has assembled a
 dataset of suspect posts (Meta Content Library, Telegram export,
 Twitter archive) and needs to test whether the accounts behind
 those posts show coordination signatures.
- An election-cycle CIB investigation in Indonesia, the Philippines,
 or Thailand needs an open-source analysis layer that runs locally
 on the analyst's machine without sending data to a vendor cloud.
- A research partner is training a regional newsroom in CIB
 methodology and wants a free, MIT-licensed tool that participants
 can install and reuse on their own datasets after the workshop.
- An institutional response to a synthetic-content surge needs to
 test whether the amplification network behind the synthetic content
 shows coordination signatures separable from organic spread.

## Limitations

!!! info "Limitations"
    - Requires Python proficiency; the interactive terminal is not a
    no-code tool.
    - Behavioural focus, not content: Mango Tree analyses posting
    patterns, not whether the underlying content is true, false,
    or AI-generated.
    - Input dataset is the analyst's responsibility. A Mango Tree run
    is only as representative as the data the analyst supplies; no
    Mango Tree result vouches for the completeness of the input.
    - No published SEA-specific deployment is documented in the
    toolkit's source base (gap G-049): the tool is regionally relevant
    in principle but the worked-example casebook for Indonesia, Malaysia,
    the Philippines, Thailand, Sri Lanka, or Laos has not yet been
    published.
    - Coordination signatures alone do not prove inauthenticity. A
    legitimate political party's social-media team can produce
    Copy Pasta Test hits; the tool surfaces patterns, not intent.

## Privacy and threat model

Mango Tree runs locally on the analyst's machine. The dataset stays
under the analyst's control; no upload is required and no vendor
processing occurs. This makes Mango Tree a defensible choice for
surveillance-environment work in Sri Lanka and Laos, where shipping
behavioural data to a third-party cloud would itself constitute a
disclosure event.

The threat model that matters here is downstream: a Mango Tree
output naming specific accounts circulates as institutional research
output, and that naming has consequences for the named accounts and
for any source who supplied the underlying dataset. Treat the output
file with the same care as a list of named informants in any other
investigation; disclose to collaborators only on a need-to-know
basis and apply the same source-protection arrangements that would
apply to a verbatim quote.

!!! danger "Source-protection override (S4 — doxxing or vulnerable-community targeting)"
    A Mango Tree CIB report can name activists, journalists, or
    minority-community accounts caught alongside genuinely
    coordinated inauthentic accounts. The published naming is the
    risk; the analysis itself is local. Mitigation steps:

    1. Audit the candidate-account list for activists, journalists,
    ethnic or religious minorities, LGBTQ+ persons, witnesses,
    and migrants before publishing any naming output.
    2. Redact or pseudonymise identifiers in published network
    visualisations; consider a quiet response or institutional-
    partner alert in place of a public CIB call-out where the
    retaliation risk against the named operators is non-trivial.
    3. Preserve the source dataset under documented chain of
    custody on the analyst's machine; disclose to collaborators
    only on need-to-know basis.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant in principle for
 Bahasa-Indonesian CIB analysis, including the buzzer-network
 context that documented.
 No published Indonesian newsroom deployment.
- **Laos:** language-agnostic; the offline local-machine
 execution is one of the few CIB analysis paths that does not
 require an external service. Honest gap: no Lao-language CIB
 worked example documented.
- **Malaysia:** language-agnostic; relevant for the King /
 Anwar Ramadan-aid 2026 cluster context (regional case documentation)
 if a research partner assembles the underlying dataset.
- **Philippines:** language-agnostic; relevant in principle
 for the #FactsFirstPH coalition's broader CIB work and the
 Brawner / Doc Willie Ong actor pool's amplification network. No
 published Mango Tree deployment in the Rappler / VERA Files
 pipeline so far.
- **Sri Lanka:** language-agnostic visual modules apply;
 the local-machine execution model is the right privacy posture for
 Watchdog and Hashtag Generation's surveillance-environment work.
 No SL-specific deployment documented.
- **Thailand:** language-agnostic; relevant for follow-up
 CIB analysis on the Anutin / Mauerberger image-distribution
 network referenced in the Thai PBS / SynthID case
 (regional case documentation).

Platform applicability: works on any platform whose data the analyst
can extract. Works most cleanly with Meta Content Library extracts
(Facebook, Facebook Groups) for IFCN-signatory partners and Telegram
exports.

## How to access

Free download from the `civictechdc/cib-mango-tree` GitHub repository.
Clone the repo, install Python dependencies per the README, and run
the interactive terminal. No account creation, no beta gate. The
toolkit is licensed MIT.

## Cost (current as of 2026-05)

Free. MIT licensed. No quota, no paid tier. The cost of running
Mango Tree is the analyst's time to assemble the input dataset and
the local compute to run the tests, both of which scale with dataset
size. Civic Tech DC's maintenance is community-driven; the toolkit
does not depend on a vendor business model and is not exposed to
vendor-side pricing changes.

## Quickstart

1. Install Python 3.10+ on the analyst's machine.
2. Clone `civictechdc/cib-mango-tree` from GitHub.
3. Install dependencies via `pip install -r requirements.txt` per
 the repository README.
4. Prepare the input dataset as the README specifies (CSV or JSON
 of post records with account ID, timestamp, text, and platform
 fields).
5. Launch the interactive terminal entry point per the README.
6. Configure the Copy Pasta Test parameters: similarity threshold
 (typical: 0.85+ string similarity), time window (typical: ten
 minutes for tight coordination signals; thirty for looser
 amplification networks).
7. Run the test and inspect the output file (clusters of accounts
 posting near-identical content within the time window).
8. Cross-check the named accounts against Maltego or
 Gephi for visualisation, and against Meta
 Content Library if the IFCN gate is open to your organisation.

## In the toolkit's workflow

Behaviour-pillar non-detector tool per Architectural Anchor 1. Sits
in 1C.1 Institutional CIB detection as the open-source primary
entry, ahead of Coordination Network Toolkit (academic R
or Python alternative) and CooRTweet (R, Meta Content
Library access required), and ahead of Graphika as the
enterprise escalation-option that frontline SEA newsrooms generally
cannot reach.

Standard combinations:

- With **Maltego** at 2C.2 to visualise the named-account
 clusters that Mango Tree surfaces.
- With **Gephi** at 2C.2 for publication-grade network
 graphics on the same clusters.
- With **Meta Content Library** at 2C.2 as the IFCN-gated
 data source for the input dataset, when the analyst's
 organisation is signatory.
- With **Yudistira (MAFINDO)** at 2B.2 when the underlying
 posts need Bahasa-specific claim extraction before behavioural
 clustering.
- With **ABCDE Framework** at 2C.3 for codifying the
 behavioural pattern in inter-org reporting.

This card carries no detector signal class: Mango Tree produces a
non-detector behavioural-pattern signal. Per Anchor 2, that signal
combines cleanly with claim-extraction (2B.2), reverse-image hits
(2A.2), or source-history records (1B.1) to support an institutional
finding. Coordination alone is not enough for a strong public claim;
two non-detector signal classes are.

Decision-tree references: T-tree CIB sub-routine routes here from
1B.1 source-history hits when account-level pattern questions
emerge; the upward bridge is 2C.3 codification under DISARM /
ABCDE.

## Override notes

!!! note "Override notes"
    - **Behaviour-pillar declaration:** Mango
    Tree serves the behaviour pillar only. Every output is a
    behavioural-pattern signal; it never produces a content
    verdict (true / false / AI-generated). The card frames Mango
    Tree accordingly.

    - **No SEA-newsroom deployment yet:** the toolkit's source
    base carries no published Indonesian, Filipino, Thai, Sinhala, Tamil, Malay,
    or Lao newsroom case where Mango Tree was deployed. The tool
    enters as primary on framework merit and open-access
    properties; the regional case for it is to be built rather
    than already available. Country pages flag Mango Tree as the
    recommended open-source path for any SEA research partner
    intending to build a CIB casebook.

## Sources

- Civic Tech DC. *CIB Mango Tree — coordinated inauthentic behaviour detection toolkit*. GitHub repository (MIT licence). [civictechdc/cib-mango-tree](https://github.com/civictechdc/cib-mango-tree).
