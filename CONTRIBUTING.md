# Contributing to the IPMR Toolkit

Thank you for considering a contribution. This toolkit is a working
reference for fact-checkers, OSINT investigators, and civil society
staff in Indonesia, Laos, Malaysia, the Philippines, Sri Lanka, and
Thailand. Corrections, additions, and reports from practitioners on the
ground are how it stays accurate.

This guide is for outside contributors. If you are reading the toolkit
to use it, start at the [home page](docs/index.md) instead.

## Reporting an issue

Open a [GitHub issue](https://github.com/denis989/ipmr-toolkit/issues/new)
when you find:

- A factual error in a tool card, decision tree, or country page.
- A broken external link, retired tool, or vendor URL that has moved.
- A safety override (S1–S10) that does not match the toolkit's
  documented framing for the case you encountered.
- A platform behaviour the toolkit describes that has materially
  changed (API closure, takedown policy shift, new tipline endpoint).

Include the page URL, the specific quote or claim you are flagging,
and — where possible — a source or screenshot we can verify.

## Suggesting a new tool

The toolkit's selection criteria are documented in the
[methodology section](docs/methodology/selection-criteria.md).
Read those before opening a tool suggestion. Briefly: a tool needs to be
operationally accessible to the region's fact-checkers, must have a
documented limitation profile, and must fit one of the toolkit's six
pillar–tier cells.

Open an issue with the label `new-tool` and include:

- Tool name and vendor.
- The pillar–tier cell you think it belongs to (or "not sure").
- One paragraph on why a regional newsroom would actually reach for it
  (operational access, language coverage, cost, infrastructure).
- Any independent accuracy or audit reference you are aware of —
  vendor self-reporting alone is not sufficient.

The maintainers will review and either open a card draft, request more
information, or document why the tool was considered but not included.

## Proposing a correction

For changes you are confident about, open a pull request:

1. Fork the repository and create a branch (`fix/tool-card-typo` or
   `update/cofact-thailand-features`).
2. Edit the relevant Markdown file under `docs/`.
3. Keep the change tightly scoped. One correction or one new tool per
   pull request makes review faster.
4. Match the surrounding voice. Tool cards stay practitioner-focused
   and avoid promotional language; decision trees stay operational and
   avoid restating workflow logic in prose.
5. If your change touches a citation or a date-stamped figure (pricing,
   accuracy benchmark, accessed-on dates), update the citation block at
   the bottom of the page.
6. Open the pull request against `main`. The maintainers will review,
   suggest edits, or merge.

For larger structural changes — a new section, a new decision tree, a
new country page — open an issue first to discuss scope before
investing in the draft.

## Style guidance

The toolkit reads as written by a working editor, not a marketing
team. A few conventions:

- Tool cards follow the structure of `docs/tool-cards/_template.md`.
- Limitations come before How-to-access on every tool card — the reader
  must be able to rule a tool out before investing in setup.
- Detector tools never carry a binary "is AI" verdict on their own.
  Independent accuracy framing is mandatory; vendor self-reporting is
  always wrapped with the qualifier the methodology section documents.
- Dates use Month YYYY format for pricing and accessed-on stamps.
- External links live in a Sources block at the bottom of the page,
  not embedded mid-prose, except where the link is itself the
  evidence.

## Code of conduct and licensing

The toolkit content is published under
[Creative Commons Attribution 4.0 International](LICENSE)
(CC BY 4.0). Contributions you submit are accepted under the same
licence — when you open a pull request, you agree that your edits may
be redistributed under CC BY 4.0 with attribution.

When reusing toolkit material outside the repository, attribute as:

> "Triaging and Countering AI-Powered Disinformation and Influence
> Operations" — an IPMR practitioner toolkit, Internews Europe, 2026.
> CC BY 4.0.

## Substantive editorial questions

For questions about the toolkit's editorial scope, regional coverage,
or how to interpret a specific tool card or decision tree, write to:

- **Vino Lucero** — Senior Project Officer-Asia —
  `jlucero@internews.org`

## Maintainer

The toolkit was produced by **Denis Yagodin** under contract with
Internews Europe (IPMR project — Enhancing Indo-Pacific Media
Resilience) with financial support from the European Union.

Repository:
[github.com/denis989/ipmr-toolkit](https://github.com/denis989/ipmr-toolkit)
