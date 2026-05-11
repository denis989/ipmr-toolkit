# Triaging and Countering AI-Powered Disinformation and Influence Operations

A practitioner toolkit for fact-checkers, OSINT investigators, and
civil society staff working on AI-powered disinformation in
**Indonesia, Laos, Malaysia, the Philippines, Sri Lanka, and Thailand**.

**Live site:** [denis989.github.io/ipmr-toolkit](https://denis989.github.io/ipmr-toolkit/)

## What this is

A regionally-anchored reference for triaging suspected AI-generated
content — images, video, audio, text, and coordinated operations —
and for using AI responsibly inside fact-checking and counter-
disinformation work. The toolkit is intended to be used at the
desk during a working case, not read end-to-end.

It covers:

- **65 tool cards** with operational profiles, regional access
  notes, independent accuracy framing, and source-protection caveats.
- **7 decision trees** for first-line triage of images, video, audio,
  and provenance, plus escalation, source-protection, and tipline
  routing.
- **Pillar narratives** for Detect & Triage (Pillar 1) and Counter
  (Pillar 2), at three tiers each: First-Line Triage, Professional
  Verification, and Institutional-Level Analysis.
- **Six country pages** with per-jurisdiction operational guidance
  and legal context for state-linked or legally sensitive cases.
- **Digital safety** layer with the S1–S10 source-protection overrides
  that gate every tool upload and third-party contact.
- **Platform pages** for WhatsApp, LINE, TikTok, Facebook, Telegram,
  YouTube, and X.
- **Methodology** documenting how the toolkit's tools were chosen,
  the selection criteria, the architectural anchors that constrain
  publication, and a change log of the structural decisions that
  shaped the current form.

## For whom

Fact-checkers on deadline who need a defensible position in five to
thirty minutes. OSINT investigators preserving evidence under
surveillance-risk conditions. Civil society staff handling tiplines,
training newsroom staff, or designing counter-disinformation responses
inside a regional newsroom or coalition.

The toolkit assumes the reader is comfortable with the basic
vocabulary of fact-checking and investigative verification. It is
not an introduction to the field.

## How to read

The fastest path:

1. Read the [home page](https://denis989.github.io/ipmr-toolkit/) for
   the toolkit's framing and the three architectural anchors that
   constrain every tool card.
2. Pick the [decision tree](https://denis989.github.io/ipmr-toolkit/decision-trees/)
   that matches your case — image, video, audio, provenance, or
   escalation — and follow the linear chain.
3. Click any block in the tree to jump to the Node detail row that
   names tools, time budgets, and exact wording for the step.
4. Cross-link to a [tool card](https://denis989.github.io/ipmr-toolkit/tool-cards/)
   when the tree references a specific tool — every card carries a
   Limitations section before How-to-access, so you can rule a tool
   out without reading the full card.
5. If the case touches a vulnerable source, an authoritarian context,
   or hosted-tool data retention, read the matching
   [S-override](https://denis989.github.io/ipmr-toolkit/decision-trees/t6-source-protection/)
   before any third-party upload or contact.

A print-friendly PDF is generated from the same Markdown source on
tagged release; both formats are treated as the deliverable, with the
PDF intended for offline use in Laos and other contexts where stable
internet access cannot be assumed.

## Running locally

If you want to render the toolkit locally:

```bash
git clone https://github.com/denis989/ipmr-toolkit.git
cd ipmr-toolkit
python3 -m venv .venv
source .venv/bin/activate
pip install mkdocs mkdocs-material mkdocs-mermaid2-plugin pymdown-extensions
mkdocs serve
```

The site renders at `http://127.0.0.1:8000/ipmr-toolkit/`.

## Status

The toolkit is in active review following the close of the
content-drafting phase on 11 May 2026. Substantive editorial review
is ongoing with the project content lead; minor corrections, broken
links, and tool-availability updates are tracked through the issue
tracker on this repository.

## Project context

A deliverable of the **IPMR project (Enhancing Indo-Pacific Media
Resilience)**, implemented by [Internews Europe](https://internews.eu)
with financial support from the European Union.

Toolkit produced by **Denis Yagodin** under contract with Internews
Europe (contract reference TH23EED-172, period 25 March – 31 May 2026).
Content lead: **Vino Lucero**, Senior Project Officer-Asia —
`jlucero@internews.org`.

*This publication was produced with the financial support of the
European Union. Its contents are the sole responsibility of Internews
Europe and do not necessarily reflect the views of the European Union.*

## Contributing

Corrections and additions are welcome. See
[`CONTRIBUTING.md`](CONTRIBUTING.md) for how to report an issue,
suggest a new tool, or propose a content correction.

## Licence

Toolkit content released under the
[Creative Commons Attribution 4.0 International](LICENSE) licence
(CC BY 4.0).

Attribute as:

> "Triaging and Countering AI-Powered Disinformation and Influence
> Operations" — an IPMR practitioner toolkit, Internews Europe, 2026.
> CC BY 4.0.
