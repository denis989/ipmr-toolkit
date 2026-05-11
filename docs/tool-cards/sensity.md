---
tool_id: TOOL-005
slug: sensity
name: Sensity AI
maintainer: Sensity (Amsterdam-based)
type: detector
outline_cells:
 - {id: "1C.2", role: primary, density_role: primary}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: api
cost: enterprise
documented_country_use: [PH]
tags: [image, video, audio, deepfake, detector, enterprise, sensity, rappler]
---

# Sensity AI

**Vendor:** [sensity.ai](https://sensity.ai) | **Type:** Detector | **Cost:** Enterprise

!!! abstract "TL;DR"
    The institutional-grade deepfake detection platform deployed by
    Rappler and the #FactsFirstPH coalition on the Doc Willie Ong
    eye-drop deepfake and the Brawner "Dark Eagle" deepfake; produces
    confidence scores, heatmaps, and forensic reports across video,
    audio, and image. Primary 1C.2 entry, with a documented vendor-
    versus-casework gap of roughly twenty percentage points.

## What it does

Sensity ingests video, audio, and image inputs and produces
multilayer analysis output: pixel-level facial-manipulation scores,
acoustic deepfake probabilities, metadata reconciliation, and a
behavioural component that scores anomalies in motion and lip-sync.
The platform exposes its results as confidence scores plus heatmaps
and as forensic-report artefacts intended for evidentiary use. The
documented Rappler casework returns three separate scores per item
when a deepfake combines facial manipulation, AI-generated objects in
the visual frame, and audio manipulation: for the Doc Willie Ong
eye-drop deepfake, Sensity returned 98% facial-manipulation, 75.5%
AI-object-generation, and 94% audio-manipulation
.

The platform aggregates several internal models in producing those
scores; under Architectural Anchor 3 the toolkit treats the entire
Sensity output for a single item as one detector signal class, not
as multiple independent signals. The same wrapping rule applies when
a fact-checker runs Sensity in parallel with Hive at 1A.1
or with InVID-WeVerify's deepfake tab at 1B.1: the multiple
detectors together still count as one detector signal class for the
purposes of Anchor 2's editorial floor on publishable claims.

## When to use it

- A Rappler-grade investigative pipeline needs to produce forensic-
 quality scores on a public-figure synthetic-content case where
 the case will be publicly debunked under the newsroom's name.
- A defamation-defence file needs a vendor-supplied forensic report
 that a court or platform-appeals process will recognise as
 institutional-grade output.
- A multimodal case (face + AI-generated object + manipulated audio)
 needs separate per-modality scores rather than a single composite
 verdict.
- An institutional partner is funded specifically for the licence
 cost and is producing analysis that a regional fact-check
 coalition can cite.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor claim:** Sensity markets a headline of approximately
    98% accuracy and the Rappler workflow returned 98%
    facial-manipulation, 75.5% AI-object-generation, and 94%
    audio-manipulation on the Doc Willie Ong eye-drop deepfake
.

 **Independent finding:** in the documented Brawner "Dark
 Eagle" deepfake (a separate political-impersonation case from
 the same actor pool covered by Rappler / #FactsFirstPH), the
 same Sensity workflow returned **79.3% AI-generated**,
 roughly twenty percentage points below the headline figure
. The toolkit's
 editorial position is that the Brawner figure is the more
 operationally honest reference point: it is what Sensity
 actually returns on contested SEA political content rather
 than on a vendor-favourable demonstration.

 **No independent SEA-specific benchmark identified as of May
 2026.** Sensity is included in the Deepfake-Eval-2024
 anonymised commercial pool but no provider-level score is
 publicly separable from that benchmark; the best commercial
 video detector in that pool reached only **0.78 accuracy / 0.79
 AUC** on 2,036 in-the-wild 2024 deepfakes, which is a
 category-level upper bound rather than a Sensity-specific number
. The 98%
 headline should therefore be read as the Sensity ceiling on
 favourable inputs and the 79.3% Brawner figure as a documented
 field reading.

## Limitations

!!! info "Limitations"
    - Vendor headline of 98% accuracy is a CONFLICT-marked claim in
    the source review;
    the same operation returned 79.3% on the Brawner case
    (verbatim retention required by C2 limitation faithfulness
    rule).
    - Enterprise-only access; high cost barrier.
    - No independent tool-specific benchmark publicly available;
    Sensity sits in the Deepfake-Eval-2024 anonymised commercial
    pool where only the pool's best score (0.78) is public
.
 - Performance is not stress-tested on the full SEA face
 distribution or on the codec-compressed material common in
 WhatsApp / Facebook / TikTok pipelines.
 - Black-box proprietary platform; the score breakdown is
 vendor-defined and not openly reproducible at the level of
 academic benchmarks.

## Privacy and threat model

Sensity is a hosted enterprise platform: an analyst submits the
suspect file to Sensity's cloud or on-premises deployment for
processing. The analyst's organisation is bound by the contract
terms governing data retention, access logging, and disclosure.
For routine work on already-public material (a viral TikTok clip,
a screenshot from an open Facebook page), the upload is low-risk
because the content is already public and the chain of custody is
documented through the published source.

For source-identifying material (a clip provided by a whistleblower,
audio with diagnostic background, or anything where the suspect file
itself names a source), the upload is the risk regardless of the
verdict that comes back. Decision 7's paired honest-gap policy and
the Architectural Anchor 1 framing apply: in surveillance-environment
contexts (Sri Lanka, Laos), classify the file before the upload, and
where the classification is source-identifying, route to an offline
forensic alternative (Sherloq) and through an institutional
partner outside the surveillance jurisdiction rather than uploading
directly.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading source-identifying frames or audio to Sensity exposes
    the source to a vendor cloud and to the contract-governed
    retention and disclosure regime. Mitigation steps:

    1. Classify the suspect file as public, sensitive, or
    source-identifying before any upload.
    2. For source-identifying material, do not upload to Sensity
    directly. Route the case through an institutional partner
    outside the surveillance jurisdiction, or use offline
    forensics (Sherloq) for the modules that can be
    run locally.
    3. If the case requires Sensity's specific output, strip
    identifying context (crop, blur, redact audio) on the
    analyst's machine before submission of the redacted
    version.
    4. Document the chain of custody for the redacted file in
    case the original is later required for evidentiary
    purposes.

!!! danger "Source-protection override (S9 — cross-border data transfer)"
    Sensity is a vendor-cloud platform with contract-governed
    retention. Uploads cross into the vendor's jurisdiction
    regardless of where the analyst sits. Mitigation steps:

    1. Read the active contract's retention and disclosure terms
    before any Sensity submission; record the version with the
    case file.
    2. Confirm that organisational data policy permits the upload
    under the contract terms; some newsroom and partner
    agreements restrict cross-border transfer of sensitive
    material.
    3. For surveillance-risk countries, prefer the institutional-
    partner submission path so the analyst is not the named
    account holder on the platform.

## Country and platform applicability

- **Indonesia:** language-agnostic; relevant in principle for
 the Prabowo / Sri Mulyani 2025 deepfake cluster where institutional-grade detection would have
 applied; no documented Indonesian newsroom direct deployment.
- **Laos:** language-agnostic for image and video; the
 cloud-upload privacy posture is wrong for a Lao surveillance-
 environment workflow without partner-mediated routing.
- **Malaysia:** language-agnostic; relevant for the King /
 Anwar Ramadan-aid 2026 cluster context if institutional access
 is available.
- **Philippines:** primary documented use. Rappler /
 #FactsFirstPH workhorse on the Doc Willie Ong eye-drop deepfake
 (98% / 75.5% / 94%) and Brawner "Dark Eagle" (79.3%); part of
 the Rappler / #FactsFirstPH multi-tool pipeline alongside
 Hive AI and InVID-WeVerify
.
- **Sri Lanka:** language-agnostic for visual modules;
 surveillance-environment routing through institutional partners
 is the right path; direct Sri Lankan newsroom use not documented.
- **Thailand:** language-agnostic; AFP regional partnership
 may include institutional access; Thai PBS uses SynthID
 Detector as the documented provenance-first path on the
 Anutin / Mauerberger case rather than Sensity.

Platform applicability: works on any video, audio, or image file the
user can submit; relevant across Facebook, Facebook Groups, TikTok, YouTube, WhatsApp
(forwarded clips). Documented Rappler use covered Facebook-
distributed political-impersonation content.

## How to access

Enterprise sales contact via the Sensity website. The platform is
not available in a free or self-service tier; access requires a
commercial agreement. Cloud deployment and on-premises options
exist; the on-premises route is the path used by national-security
or law-enforcement institutional partners with strict
data-residency requirements.

## Cost (current as of 2026-05)

Enterprise pricing in the **$50,000 to $200,000-plus per year**
range . Specific numbers
move with the vendor's pricing; verify through Sensity's sales
process before committing to a procurement. The bracket is included
to make the structural reason for Sensity's institutional-tier
placement concrete: at this cost, the tool is realistic for
broadcaster-grade or coalition-grade operations (Rappler /
#FactsFirstPH, AFP regional partnerships) and out of reach for the
typical individual SEA newsroom unless the budget arrives through a
specific institutional grant.

## Quickstart

1. Confirm institutional access. The realistic path for a frontline
 SEA newsroom is partner-mediated rather than direct.
2. Classify the suspect file per the danger admonition above before
 any upload.
3. Submit the file through Sensity's API or web interface as the
 licence agreement specifies.
4. Inspect the per-modality scores: facial-manipulation,
 AI-object-generation, audio-manipulation, plus the heatmap
 visualisation.
5. Treat the multiple modality scores as one detector signal class
 per Anchor 3, not as multiple independent confirmations.
6. Pair the Sensity output with at least one non-detector signal
 class (a reverse-image hit, a provenance manifest, an
 archived-version search, a tipline-database match) before
 any publishable claim, per Anchor 2.
7. Retain the forensic report artefact for chain-of-custody if the
 case may face a defamation defence or a platform appeal.

## In the toolkit's workflow

Cautious-detector pillar tool per Architectural Anchor 1. Sits in
1C.2 Institutional deepfake platforms as primary, ahead of Reality Defender (alternative for broadcaster-grade deployments)
and DeepfakeBench (academic evaluation harness, not a
deployable detector).

Standard combinations:

- With **Hive AI** at 1A.1 / 1A.3 as the documented
 Rappler / #FactsFirstPH pipeline; the two detectors together
 count as one detector signal class under Anchor 3, not as two.
- With **InVID-WeVerify** at 1A.2 / 1B.1 for source-
 history work alongside Sensity's detector pass.
- With **Meedan Check** at 2B.1 for the #FactsFirstPH
 coalition's claim-database backbone.
- With **TRIED Benchmark** at 1C.3 for sociotechnical
 evaluation of Sensity's output on the same case before the
 finding is published.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. Counted as one detector
signal class under Anchor 3, regardless of how many of Sensity's
internal modality scores contribute to the verdict.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
escalates to Sensity at T5.6 (image professional) and T5.7 (video
professional) when the case warrants forensic-grade scoring.
[T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes the upload through the S1 sub-routine before any submission.

## Conflict resolution behaviour

When Sensity's verdict disagrees with another detector
(Hive, Deepware, InVID deepfake tab),
Sensity carries equal-or-stronger evidence weight at the
institutional tier on documented Rappler casework but **no stronger
weight than its own field reading**: the 79.3% Brawner figure is
what Sensity actually returns on contested SEA political content
and is the operational reference point. When the Sensity verdict
disagrees with a non-detector signal (provenance manifest, reverse-
image hit, archived earlier instance, or a tipline-database match),
the non-detector signal wins because Anchor 2 mandates two
non-detector signals before any strong public claim. Inside an
institutional pipeline, Sensity's forensic-report artefact carries
chain-of-custody weight that Hive's free-tier output does not, but
that weight applies to the report's evidentiary status, not to the
underlying probability.

## Override notes

!!! note "Override notes"
    - **Multi-detector wrapped as one class (g3-multi-detector-
    wrapped-as-one-class):** Sensity's internal modality scores
    (face, object, audio) and any parallel detector run (Hive,
    InVID's tab) together count as one detector signal class
    under Anchor 3. Workflow section above invokes this rule
    explicitly.

    - **Vendor wrapping pair (c1-pair-vendor98-vs-Brawner79.3):**
    the 98% headline against the Brawner 79.3% field reading is
    rendered in full in the Independent accuracy admonition above,
    with the Deepfake-Eval-2024 anonymised-pool framing surfaced for context.

    - **Verbatim Brawner counter-example (c2-verbatim-Brawner-
    counter-example):** the Brawner 79.3% figure is preserved
    verbatim in Limitations rather than softened or merged into
    the headline figure.

    - **Enterprise pricing (d1-score-1-enterprise):** D1 score of 1
    rendered concretely in Cost as the $50K-$200K+ per year
    range; this is the structural reason the tool sits at
    institutional tier rather than at PV or FLT.

    - **Cloud-upload mitigation (d4-mitigation-pass-cloud-upload-
    S1):** the S1 source-protection sub-routine is bound into the
    danger admonition above, with concrete pre-upload mitigation
    steps for surveillance-environment work.

## Sources

- Sensity. *Sensity AI — forensic deepfake detection platform*. Sensity (Amsterdam), 2024. [sensity.ai](https://sensity.ai).
- Sensity. *Sensity Platform — detection product page*. [sensity.ai/platform](https://sensity.ai/platform).
