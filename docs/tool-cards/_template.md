---
tool_id: TOOL-XXX
slug: tool-slug-here
name: Full Tool Name
maintainer: Maintainer org or vendor
type: detector | non-detector | mixed-with-declaration | framework | reference
outline_cells:
  - {id: "X.X", role: primary | alternative | escalation-option, density_role: primary | alternative}
pillar_service: [provenance | source-history | behaviour | cautious-detector]
signal_class: detector | non-detector | mixed-with-declaration | framework | reference
status: active | beta | inactive | reference
last_verified: 2026-05-10
license: MIT | proprietary | freemium | research | other
languages_ui: [en, ...]
languages_content: [en, id, ms, fil, tha, sin, tam, lao, agnostic]
access: web | browser-ext | desktop | api | cli | mobile
cost: free | freemium | paid-low | paid-mid | enterprise | grant-funded
documented_country_use: [ID, MY, PH, TH, LK, LA]
tags: [image, video, audio, text, provenance, tipline, claim-extraction, ...]
---

# Tool Name

!!! abstract "TL;DR"
    One or two sentences: what this tool is and why a fact-checker on
    deadline would reach for it.

## What it does

One or two paragraphs of operational description. Inputs and outputs.
No marketing voice. State the tool's core function in concrete terms.

## When to use it

- Scenario one.
- Scenario two.
- Scenario three.
- Optional fourth or fifth scenario.

## Independent accuracy

(DETECTOR or MIXED cards only — omit on non-detector / framework /
reference cards.)

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** [exact quote or paraphrase that does not soften].

    **Independent finding:** [exact result with sample size and
    citation], [evaluator], [date].

    OR

    **No independent SEA-specific benchmark identified as of May 2026.**
    Vendor's headline claim is recorded for transparency:
    [vendor claim].

## Limitations

!!! info "Limitations"
    - Verbatim caveat one.
    - Verbatim caveat two.
    - SEA-language-specific caveat where applicable.
    - Documented regional content failure where applicable.

## Privacy and threat model

Prose paragraph describing data flows: input source, where the data
goes, retention policy, jurisdictional concerns, and any disclosure
the user should make to a source before running the tool.

If a safety override S1–S10 applies (the tool, used by default, would
expose a source), include the danger admonition below; otherwise
omit it.

!!! danger "Source-protection override (S?)"
    Concrete description of the exposure risk.

    Mitigation steps:

    1. Pre-upload action.
    2. Pre-upload action.
    3. Pre-upload action.

## Country and platform applicability

Per regional suffix scheme. Name the focus countries where the tool is
documented, with cross-links to the country pages.

- Indonesia (-id): documented use, case reference.
- Laos (-lao): coverage status, honest-gap acknowledgement if
  applicable.
- Malaysia (-ms): documented use, case reference.
- Philippines (-ph): documented use, case reference.
- Sri Lanka (-si-ta): coverage for Sinhala and Tamil specifically.
- Thailand (-thai): documented use, case reference.

Platform applicability where relevant (-wa / -line / -tiktok / -fb /
-fbg / -telegram / -youtube / -x).

## How to access

URL, install path, account requirement, beta gate. Be specific. If a
closed-beta-disclaimer flag is set, render the leading sentence:
"Currently in closed beta — request access via [URL]."

## Cost (current as of YYYY-MM)

Date-stamped pricing or licence. Concrete tier figures rather than
"affordable for newsrooms." If pricing has changed since the inventory
was compiled, note the date the figure was verified.

## Quickstart

1. Step one.
2. Step two.
3. Step three.
4. Step four.
5. Step five.

(Mobile-aware where the tool is FLT-tier and a phone is the expected
device.)

## In the toolkit's workflow

Pillar service and tier position. Tool combinations: which other tool
cards typically pair with this one, with cross-links. Decision-tree
node references — cite T-tree node IDs when the routing is known.

State signal-class behaviour explicitly:

- For detector cards: "This tool's verdict is one weak signal class
  per Architectural Anchor 1; never publish a binary claim from it
  alone."
- For multi-detector wrappers: "Counted as one detector signal class
  under Architectural Anchor 3, not as multiple."
- For non-detector cards: name the signal type (provenance,
  source-history, behaviour) the tool generates.

## Conflict resolution behaviour

(DETECTOR or MIXED cards only — omit on non-detector / framework /
reference cards.)

When this tool's verdict disagrees with another tool's verdict, this
tool's evidence weight is X because Y. Concrete, not soft. Implements
Architectural Anchor 1 signal-class hierarchy.

## Override notes

(Only when the tool's `override_flags` in shortlist-data.yaml is
non-empty.)

!!! note "Override notes"
    Render each flag as final published prose per CONTRIBUTING.md
    section 4. One paragraph or sub-list per flag.

## Sources

- External: `[Title](URL)` — accessed YYYY-MM-DD
