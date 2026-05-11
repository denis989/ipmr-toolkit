---
tool_id: TOOL-024
slug: truemedia-georgetown
name: TrueMedia.org (Georgetown McCourt School)
maintainer: Georgetown University McCourt School of Public Policy (Massive Data Institute, Tech & Public Policy program)
type: mixed-with-declaration
outline_cells:
 - {id: "1B.3", role: escalation-option, density_role: alternative}
pillar_service: [cautious-detector, source-history]
signal_class: mixed-with-declaration
status: beta
last_verified: 2026-05-10
license: mit (when active)
languages_ui: [en]
languages_content: [unverified-multilingual-claimed]
access: web (closed-beta)
cost: free
documented_country_use: []
tags: [audio, video, image, deepfake, ensemble, georgetown, closed-beta, radical-transparency]
---

# TrueMedia.org (Georgetown McCourt School)

**Vendor:** [truemedia.org](https://truemedia.org) | **Type:** Detector + non-detector | **Cost:** Free

!!! abstract "TL;DR"
    The revived TrueMedia.org, now hosted at Georgetown University's
    McCourt School of Public Policy, is a non-partisan ensemble
    deepfake detector with a mission of radical transparency about
    detection accuracy and uncertainty. Currently in closed beta;
    request access at [truemedia.org](https://truemedia.org). The toolkit's escalation
    option for institutional partners on audio, video, and image
    deepfake casework.

## What it does

TrueMedia accepts uploaded social-media content (image, audio, video;
text veracity to come) and runs the input through an ensemble of
AI detectors and human verification, returning a deepfake-probability
verdict alongside transparent reporting of accuracy metrics,
uncertainty levels, and known limitations. The original TrueMedia,
founded by Dr Oren Etzioni, shut down in January 2025; Georgetown's
McCourt School of Public Policy revived it in April 2025 through the
Massive Data Institute and the Tech & Public Policy program, where
Dr Lisa Singh and Michelle De Mooy oversee the initiative.

The toolkit ships TrueMedia as the escalation-option entry in 1B.3
audio deepfake forensics for two reasons. First, the ensemble
approach (multiple AI detectors plus human verification) is closer
to the toolkit's own architectural anchors than any single-model
detector: every decision determined by a model is checked by a
human, and the platform reports uncertainty, not a single
binary verdict. Second, the mission framing of radical transparency
(no claim of perfect accuracy; reliability measured, documented, and
continuously evaluated) matches the toolkit's own
detector-as-weak-signal commitments and its honesty about
SEA-language audio detection limits.

The closed-beta access status is the operational constraint. Until
beta access is granted, TrueMedia is a referenceable institutional
option, not a deployable tool for SEA newsrooms.

## When to use it

- An institutional partner with closed-beta access has a high-stakes
 deepfake case (audio, image, video) and wants ensemble verdict
 plus documented uncertainty, not a single-vendor score.
- A research collaboration with Georgetown's MDI / TPP needs a
 deepfake-detection backbone that ships with transparent methodology
 for academic citation.
- A regional partner with IFCN signatory status or formal academic
 affiliation can credibly request beta access for a documented case
 pipeline.
- A workshop demonstrates the difference between vendor-style
 closed-source detector products (Sensity, Reality Defender) and a
 mission-driven open-methodology platform. TrueMedia is the
 cleanest demonstration available.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** TrueMedia explicitly does not claim perfect
    accuracy ("No detection system achieves perfect accuracy. We do
    not claim otherwise.") and frames itself as reporting
    performance metrics, uncertainty levels, and known limitations,
    not headline numbers.

    **No independent SEA-specific benchmark identified as of May
    2026.** The closed-beta status limits public independent
    evaluation; TrueMedia's own self-reporting commits to publishing
    performance and uncertainty metrics, but no third-party SEA-
    language audit has been published in the toolkit's research
    base. Verify directly when beta access is granted.

## Limitations

!!! info "Limitations"
    - Currently in closed beta (May 2026); not deployable for SEA
    newsrooms without granted access. Verify access status before
    relying on this tool in any case (see [truemedia.org](https://truemedia.org)).
    - Ensemble approach inherits the limitations of its constituent
    detectors; per Anchor 3, multi-detector wrappers count as one
    detector signal class regardless of how many internal models
    contribute to the verdict.
    - SEA-language coverage and SEA-specific audio performance are
    not independently documented; the platform's
    radical-transparency commitment is to publish metrics, but
    the disclosed metrics base is not yet SEA-specific.
    - Original TrueMedia shut down in January 2025; the Georgetown
    revival relies on continued institutional commitment from the
    McCourt School. Bus-factor risk is institutional, not
    single-developer, but it is real.

## Privacy and threat model

The detection portal at [detect.truemedia.org](https://detect.truemedia.org) and the public site
at [truemedia.org](https://truemedia.org) operate on Georgetown University infrastructure
([truemedia.georgetown.edu](https://truemedia.georgetown.edu) per the privacy policy). Uploads route
through Georgetown's data-handling practices. Verify the current
data-flow practices in the privacy policy at the time of access; the
policy was last updated 11 March 2026.

For source-identifying material, the upload itself is the risk
regardless of the verdict. In Lao and Sri Lanka surveillance work,
classify the source file before any upload and document the
disclosure.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Submitting source-identifying frames, audio, or video to the
    TrueMedia portal routes the file to Georgetown University
    infrastructure under the published privacy policy. Mitigation
    steps:

    1. Classify the suspect file as public, sensitive, or source-
    identifying before any submission.
    2. For source-identifying material, do not invoke TrueMedia
    directly. Route the case through an institutional partner
    outside the surveillance jurisdiction, or use the source-
    history modules of InVID-WeVerify first.
    3. If a TrueMedia verdict is operationally necessary, strip
    identifying context (crop, blur, redact audio) on the local
    machine before submission of the redacted version.
    4. Document the submission in the case record per the closed-
    beta access conditions.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    TrueMedia operates from US jurisdiction on Georgetown University
    infrastructure. Mitigation steps:

    1. Check the active privacy policy at time of access (last
    updated 11 March 2026); record the version with the case
    file because policy text drifts.
    2. Confirm organisational policy permits the upload under US
    university data-handling terms.
    3. Prefer EU-jurisdiction alternatives (InVID's deepfake
    tab via CERTH for redacted material with documented 30-day
    retention) when the source is in a surveillance-risk country.

## Country and platform applicability

- **Indonesia:** no documented Indonesian newsroom deployment
 recorded; tool applies in principle if beta access is granted to
 a partner like CekFakta or MAFINDO.
- **Laos:** no documented use; ensemble approach
 language-claimed but not Lao-tested.
- **Malaysia:** no documented use; ensemble approach
 language-claimed.
- **Philippines:** no documented Rappler / VERA Files
 deployment recorded; the closed-beta status is the operational
 constraint.
- **Sri Lanka:** no documented use; ensemble approach
 language-claimed but not Sinhala or Tamil tested.
- **Thailand:** no documented use; tonal-language
 performance is the explicit "no evidence" gap from the same Deepfake-Eval-2024
 framing as Hiya.

The closed-beta status means SEA documented use will accumulate
only after beta access is widely granted to regional partners.

Platform applicability: works on social-media content regardless of
source platform; the platform-specific compression caveats from the
DW audio audit apply equally here.

## How to access

The public site at [truemedia.org](https://truemedia.org) carries the "Request Beta Access"
call-to-action; the detection endpoint at [detect.truemedia.org](https://detect.truemedia.org)
requires a beta password. Request access through the form on the
public site; the For Teams page describes API access, organisation
accounts, and team management features that ship with the platform
when beta access is granted.

!!! note "Access status as of 2026-05-10"
    Web-fetch verification (Exa search, 2026-05-10) confirms:
    revival under Georgetown McCourt School (April 2025
    announcement); current site at [truemedia.org](https://truemedia.org); detection
    endpoint at [detect.truemedia.org](https://detect.truemedia.org) behind a sign-in; closed-beta
    "Request Beta Access" CTA active. Privacy policy at
    [truemedia.org/privacy-policy](https://truemedia.org/privacy-policy) updated 11 March 2026; published
    domain references include [truemedia.georgetown.edu](https://truemedia.georgetown.edu). Verify
    again before institutional reliance.

## Cost (current as of 2026-05)

Free (when beta access is active). Non-profit, non-partisan;
Georgetown McCourt School institutional commitment underwrites
operational costs.

## Quickstart

1. Visit [truemedia.org](https://truemedia.org) and click "Request Beta Access".
2. Submit the access request with your organisational affiliation
 and case-pipeline description.
3. After access is granted, sign in at [detect.truemedia.org](https://detect.truemedia.org).
4. Upload the suspect image, audio, or video file.
5. Read the ensemble verdict alongside the disclosed uncertainty
 metrics; the platform's radical-transparency commitment means
 the uncertainty band is the operationally important field, not
 the single-number probability.
6. Pair with non-detector signals: provenance check via [Content Credentials Verify](content-credentials-verify.md) or
 [SynthID Detector](synthid-detector.md); source-history
 work via [InVID-WeVerify](invid-weverify.md). Per Anchor
 2 the toolkit's editorial position is unchanged: two non-detector
 signals are required before any strong public claim, regardless
 of how transparent the detector platform is.

## In the toolkit's workflow

Cautious-detector and source-history pillar mixed-with-declaration
tool per Architectural Anchor 1. TrueMedia's ensemble approach
combines model verdicts (cautious-detector signal) with human
verification (source-history-style signal). Sits as escalation-option
at 1B.3 audio deepfake forensics; usable across image, audio, and
video casework when access is granted.

Standard combinations:

- With **Hiya** at 1B.3 – Hiya is the press-button
 deployable option; TrueMedia is the institutional escalation when
 beta access is available. Per Anchor 3 both count as one detector
 signal class.
- With **TOOL-STUB-DEEPFAKETOTAL** at 1B.3 – Deepfake Total is the
 audit-leader (DW 7-of-10); TrueMedia is the
 ensemble-with-transparency alternative. Same Anchor 3 framing.
- With **Content Credentials Verify** and **SynthID Detector** at 1A.4 for non-detector provenance pairing.
- With **Sensity** at 1C.2 for institutional contrast. Both
 are enterprise-tier; Sensity is closed-source vendor; TrueMedia is
 open-methodology academic.

This card declares signal-class per output: when the verdict comes
from the ensemble of model detectors, the signal class is detector
(one weak signal under Anchor 1, one signal class under Anchor 3
regardless of internal model count). When the verdict incorporates
human verification, the signal carries weight closer to a
source-history signal; the card and the user must declare
which part of the verdict they are reading from for any given case.

Decision-tree references: [T3 audio triage](../decision-trees/t3-audio-triage.md) – TrueMedia is the
institutional escalation branch at T3.8 (audio detector run) behind
beta gating. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk) –
same upload-classification discipline as Hiya.

## Conflict resolution behaviour

When TrueMedia's ensemble verdict disagrees with Hiya or
TOOL-STUB-DEEPFAKETOTAL on the same input, TrueMedia carries
slightly stronger evidence weight by virtue of the human-in-the-loop
verification layer (the platform commits that "every decision
determined by a model is checked by a human"). The toolkit's
editorial position is that no audio detector verdict alone is
publishable, including TrueMedia's; per Anchor 2 a non-detector
signal (caller verification, platform-of-origin check, manual
voice-comparison) must independently corroborate before any
publication. When TrueMedia disagrees with a non-detector signal,
the non-detector signal wins.

## Override notes

!!! note "Override notes"
    - **Revival confirmed but beta-gated
    (e2-revival-confirmed-but-beta-gated):** the E2 anti-criterion
    (abandoned) was triggered when TrueMedia shut down in January
    2025 but is overridden by the Georgetown McCourt School
    revival in April 2025, web-fetch-verified May 2026. The card
    enters at 1B.3 as escalation-option (D3 fail at First-Line
    Triage acceptable at Professional Verification per the E2
    revival override).

    - **Closed-beta disclaimer (closed-beta-disclaimer-required):**
    "Currently in closed beta; request access via
    [truemedia.org](https://truemedia.org)." Rendered as the leading sentence in the
    How to access section above; the access-status note records
    the May 2026 verification.

    - **Cautious-detector with multi-pillar framing
    (g1-cautious-detector-with-multi-pillar-framing):** the
    ensemble + human verification design genuinely serves both
    cautious-detector and source-history pillars; the workflow
    section names this declaratively.

    - **Anchor-aligned mission radical transparency
    (anchor-aligned-mission-radical-transparency):** TrueMedia's
    mission framing aligns with the toolkit's Architectural
    Anchor 1 (workflow over directory, transparency over headline
    accuracy) and Anchor 2 (no strong claim from detector signal
    alone). The Limitations and Independent Accuracy admonitions
    reference this alignment in framing; the caveats stand regardless.

## Sources

- web-fetch — [TrueMedia.org](https://www.truemedia.org/) — accessed
 2026-05-10
- web-fetch — [TrueMedia finds new home at Georgetown's McCourt
 School](https://mccourt.georgetown.edu/news/truemedia-finds-new-home-at-georgetowns-mccourt-school/)

- web-fetch — [TrueMedia privacy policy](https://www.truemedia.org/privacy-policy)
 — updated 2026-03-11
