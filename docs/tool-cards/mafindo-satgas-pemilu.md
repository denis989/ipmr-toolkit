---
tool_id: TOOL-208
slug: mafindo-satgas-pemilu
name: MAFINDO Satgas Pemilu (2024 Election Task Force)
maintainer: MAFINDO
type: non-detector
outline_cells:
 - {id: "2A.4", role: primary, density_role: alternative}
pillar_service: [behaviour]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free
languages_ui: [id]
languages_content: [id]
access: web
cost: free
documented_country_use: [ID]
tags: [workflow-design-pattern, election-workflow, mafindo, indonesia, satgas-pemilu, adjacent-pointer]
---

# MAFINDO Satgas Pemilu (2024 Election Task Force)

**Operator:** [mafindo.or.id](https://mafindo.or.id) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    An adjacent pointer, not a verification tool. MAFINDO's
    dedicated 2024 Election Task Force is an organisational
    workflow design pattern (event-specific triage units that
    absorb the spike in election-period hoaxes) included here
    because the design pattern is reusable across Southeast
    Asian election cycles, not because Satgas Pemilu itself is a
    deployable product.

## What it does

Satgas Pemilu was the dedicated coordination structure MAFINDO
operated through Indonesia's 2024 presidential election. The
task force organised volunteer triage capacity, routed
forwarded WhatsApp content into MAFINDO's verification workflow,
and coordinated CekFakta consortium response across the
election period. It is a workflow pattern (event-specific unit,
volunteer mobilisation, intake routing), not a tool with a
download or sign-up.

## When to use it

A regional fact-check organisation is preparing for an election
cycle and wants a documented SEA-grounded design pattern for
event-specific triage capacity. A funder or institutional partner
is reviewing how MAFINDO orchestrated volunteer and partner
capacity around the 2024 election and Satgas Pemilu is the
referenced case.

## Limitations

!!! info "Limitations"
    - Event-specific by design. The 2024
    task-force structure ran during the 2024 election cycle;
    MAFINDO has reactivated similar structures around
    subsequent events but Satgas Pemilu 2024 is a closed
    historical reference rather than a continuously-running
    tool.
    - Volunteer-based capacity is a function of MAFINDO's
    organisational network in Indonesia; replicating the
    design pattern in another country requires the
    equivalent volunteer base, not just the workflow design.

## Privacy and threat model

Operational coordination ran inside MAFINDO's editorial
infrastructure under that organisation's data-handling terms;
the public-facing intake was through Kalimasada and
the CekFakta consortium. No data flow is intrinsic to "the
design pattern" itself.

## Country and platform applicability

Indonesia only as a documented case. The pattern is
adaptable to any election-period context with a comparable
volunteer base and consortium structure; concrete adaptation
would require an organisation in the role MAFINDO holds in
Indonesia.

## How to access

Documented through MAFINDO's published 2024 election
post-mortems and through [change-log](../methodology/change-log.md)
references. There is no install or sign-up path; the case is the
reference, not a product.

## Cost (current as of 2026-05)

Volunteer-based; structural cost is the volunteer-coordinator
time MAFINDO absorbs through its membership network plus
funder-supported staff time at the consortium level.

## In the toolkit's workflow

Adjacent pointer at 2A.4 under the cell's marginal-inclusion framing
([change-log](../methodology/change-log.md)). The card exists to acknowledge that
event-specific workflow orchestration around an election cycle
is a coherent design pattern in Indonesia, not to recommend a
deployable product. The reader's operational route into the
MAFINDO Pillar 2 workflow is through Kalimasada at
2B.1 (the public WhatsApp intake), Yudistira at 2B.2
(the Bahasa claim database), and the regional-case lineage at
regional case documentation.

This card carries no detector signal class. Per the template
(non-detector card), no Independent Accuracy admonition and no
Conflict Resolution Behaviour paragraph apply.

## Override notes

!!! note "Override notes"
    - **Workflow design pattern, not tool (workflow-design-
    pattern-not-tool):** the card frames Satgas Pemilu as an
    organisational design pattern from MAFINDO's 2024 election
    cycle inside the INCLUDE MARGINALLY verdict for 2A.4, not
    as a deployable verification tool.

## Sources

- MAFINDO. *Satgas Pemilu 2024 — election task force post-mortem*. MAFINDO, 2024. [mafindo.or.id](https://mafindo.or.id).
- CekFakta Consortium. *CekFakta — Indonesian fact-checking consortium*. CekFakta, 2024. [cekfakta.com](https://cekfakta.com).
