---
tool_id: TOOL-011
slug: xai-deepfakes
name: XAI-Deepfakes
maintainer: IDT-ITI (Information Technologies Institute, Centre for Research and Technology Hellas)
type: detector
outline_cells:
 - {id: "1C.3", role: primary, density_role: primary}
pillar_service: [cautious-detector]
signal_class: detector
status: active
last_verified: 2026-05-10
license: open-source
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [explainable-ai, deepfake, video, image, gradcam, shap, lime, efficient-net, defamation-defence]
---

# XAI-Deepfakes

**Publisher:** [github.com/IDT-ITI/XAI-Deepfakes](https://github.com/IDT-ITI/XAI-Deepfakes) | **Type:** Detector | **Cost:** Free

!!! abstract "TL;DR"
    A free, open-source academic toolkit from CERTH IDT-ITI that
    runs Explainable AI methods (GradCAM, SHAP, LIME) on an
    EfficientNet deepfake classifier to produce visual heatmaps
    showing which pixels drove the verdict. The primary 1C.3 entry
    for evidence-grade reporting where a probability score is not
    enough.

## What it does

XAI-Deepfakes wraps three Explainable AI methods around an
EfficientNet-based deepfake classifier. GradCAM produces gradient-
weighted class-activation heatmaps that visualise which regions of
the image most contributed to the deepfake verdict; SHAP produces
Shapley-value attributions that quantify each pixel's marginal
contribution to the classification; LIME produces locally
interpretable model-agnostic explanations that approximate the
classifier's behaviour on perturbed inputs. The output is a
combination of the underlying classifier's verdict plus the three
explanation visualisations, which together form an evidence
artefact a fact-checker can publish alongside a detection finding
and a defamation-defence file can attach to legal pleadings.

The toolkit's institutional value sits in defamation-defence
contexts. Where Sensity and Reality Defender produce probabilistic
scores plus vendor-defined "explainable indicators" inside a
black-box pipeline, XAI-Deepfakes produces the academic state-of-
the-art explainability output with reproducible methods. For a
court or platform-appeal process that asks "what made the system
decide this was AI?", XAI-Deepfakes can answer the question with
visualisations that are scientifically grounded rather than
vendor-defined.

## When to use it

- A defamation defence file requires evidence-grade detection
 output: not just a probability score but a visual map of which
 pixels drove the verdict, attached to the published debunk as
 legal-defensibility material.
- A research-grade fact-check needs to show that a Sensity or
 Reality Defender verdict is corroborated by an academic
 classifier with explainability output, not only by a black-box
 vendor pipeline.
- A regional academic partner is producing a forensic report and
 the methodology must be reproducible by another lab from the
 published code.
- A graduate-school or partner-university context teaches
 detector explainability and the GradCAM / SHAP / LIME triad is
 the methodologically appropriate teaching environment.

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor positioning:** XAI-Deepfakes is positioned as a
    methodology toolkit for explainable deepfake forensics rather
    than as a headline-accuracy classifier. The underlying
    EfficientNet classifier is a standard academic baseline; the
    three Explainable AI methods (GradCAM, SHAP, LIME) are
    canonical in the explainability literature. The maintainer
    does not market a single headline accuracy figure.

    **No independent SEA-specific benchmark identified as of May
    2026.** XAI-Deepfakes is academic tooling and has not been
    independently audited for SEA-specific performance. The
    underlying EfficientNet classifier inherits the Deepfake-Eval-2024 benchmark cross-
    category gap: no Asian-face or SEA-language breakdown is
    publicly available for image / video detection methodology of
    this generation. The toolkit's editorial framing is that
    XAI-Deepfakes' value sits in the explainability output rather
    than in the underlying classifier's headline accuracy; the
    classifier should be treated as one weak signal class per
    Anchor 1, with the explainability output supporting the
    interpretation work that makes the signal usable in an
    evidence-grade report.

## Limitations

!!! info "Limitations"
    - Requires Python proficiency, an Ubuntu environment, and a
    GPU for practical performance.
    - Academic tooling, not production. Maintenance follows the
    research lab's grant cycle rather than a vendor SLA, and
    operationalising it for a working newsroom requires the
    newsroom's own technical staff.
    - The underlying EfficientNet classifier inherits the same
    Asian-face / SEA-language benchmark gap that affects every
    detector in the toolkit (the Deepfake-Eval-2024 cross-category note).
    - GradCAM / SHAP / LIME outputs are interpretable but not
    objective: an explanation map shows what the classifier
    attended to, not what is true about the image. Treat
    explanations as evidentiary aids, not as ground truth.
    - No Lao-language, Sinhala, or Tamil documentation; the toolkit
    is English-only academic material.

## Privacy and threat model

XAI-Deepfakes runs locally on the analyst's GPU machine. The
suspect file stays under the analyst's control during analysis;
no upload to a vendor cloud is required. This makes the toolkit
the right privacy posture for surveillance-environment work in
Sri Lanka and Laos (where shipping a suspect file to a vendor
cloud would itself constitute a disclosure event) and for
defamation-defence work generally, where the suspect file may be
sub judice and must remain within the analyst's controlled
environment.

The threat model that matters here is downstream: an explanation
artefact published alongside a debunk is published research output
that adversaries can study. Adversarial deepfake research routinely
optimises against published explainability methods to produce
content that GradCAM / SHAP / LIME visualise as "real" even when
the underlying classifier scores it as fake. Treat explanation
outputs as evidence in the published analysis rather than as a
permanent solution to detection.

## Country and platform applicability

- **Indonesia:** language-agnostic for visual modules;
 available in principle to Indonesian academic and newsroom-
 technical partners with GPU infrastructure.
- **Laos:** language-agnostic; the local-execution model is
 privacy-defensible. No documented Lao-specific deployment.
- **Malaysia:** language-agnostic; available to MIMOS,
 Mesolitica, or university partners with GPU access.
- **Philippines:** language-agnostic; available to UP / DLSU /
 Ateneo and to Rappler's technical layer; particularly relevant
 for defamation-defence work tied to Rappler / #FactsFirstPH
 published debunks.
- **Sri Lanka:** language-agnostic for visual modules;
 LIRNEasia and Watchdog technical capacity can run XAI-Deepfakes
 inside their research environment; explainability output is
 particularly valuable under Sri Lanka's OSA framework where
 evidentiary defence matters.
- **Thailand:** language-agnostic; available to Thai
 university partners; relevant under the Thai lèse-majesté and
 CCA evidentiary regime where explainable detection output
 reduces legal exposure.

Platform applicability: not platform-specific. Operates on any
image or video file the analyst can supply.

## How to access

Free download from the IDT-ITI XAI-Deepfakes GitHub repository.
Clone the repo, install Python dependencies, configure CUDA for
GPU support per the README. No account creation, no beta gate.
The toolkit is open-source academic code with a permissive
research licence.

## Cost (current as of 2026-05)

Free in software terms. The structural cost is hardware: a GPU
(Ubuntu host), at least 16 GB GPU memory recommended for
EfficientNet inference plus SHAP attribution at usable speeds.
For institutional partners with university or research-lab GPU
access, this is a non-issue; for a frontline newsroom without GPU
infrastructure, the path is partner-mediated rather than direct.

## Quickstart

1. Confirm an Ubuntu (or Linux compatible) host with a CUDA-
 capable GPU and at least 16 GB GPU memory.
2. Clone the IDT-ITI XAI-Deepfakes repository from GitHub.
3. Install Python dependencies and configure CUDA per the README.
4. Place the suspect image or video frames in the input directory.
5. Run the GradCAM analysis to produce a class-activation heatmap.
6. Run the SHAP analysis to produce per-pixel attribution scores
 (this is the slowest of the three but the most quantitatively
 defensible).
7. Run the LIME analysis to produce a locally interpretable
 approximation of the classifier's behaviour on the input.
8. Combine the three explanation visualisations alongside the
 underlying EfficientNet score in a single forensic-report
 artefact for publication or legal use.

## In the toolkit's workflow

Cautious-detector pillar tool with explanation output per
Architectural Anchor 1. Sits in 1C.3 Institutional explainable AI
forensics as primary, ahead of TruFor (alternative,
non-detector reliability map) and TRIED Benchmark
(institutional reference framework, not a deployable tool).

Standard combinations:

- With **Sensity** at 1C.2 for institutional-pipeline
 corroboration: Sensity provides the production-grade verdict,
 XAI-Deepfakes provides the academic explanation artefact that
 defamation defence can attach.
- With **TruFor** at 1C.3 for parallel non-detector
 reliability-map output on the same suspect image; the two
 together give per-pixel explanation (XAI-Deepfakes) plus
 reliability-of-the-reliability-map (TruFor).
- With **DeepfakeBench** at 1C.2 inside a research-
 evaluation context where XAI-Deepfakes' EfficientNet baseline
 is being compared against the harness's 36 detectors.
- With **TRIED Benchmark** at 1C.3 as the sociotechnical
 evaluation framework that complements XAI-Deepfakes' technical
 explanation output.

This tool's verdict is one weak signal class per Anchor 1; never
publish a binary claim from it alone. The explanation visualisation
adds evidentiary weight to a published claim but does not by
itself constitute a non-detector signal under Anchor 2's
two-non-detector-signal floor.

Decision-tree references: [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes through XAI-Deepfakes' local-execution model when the
suspect file cannot leave the analyst's machine. [T5 escalation](../decision-trees/t5-escalation.md)
references the explanation artefact at T5.15 (method note) when
the published debunk needs a defamation-defence layer.

## Conflict resolution behaviour

When XAI-Deepfakes' verdict disagrees with another detector
(Sensity, Reality Defender, Hive),
XAI-Deepfakes carries weaker headline-accuracy weight than the
enterprise platforms because its underlying EfficientNet
classifier is an academic baseline rather than a Sensity-grade
ensemble. It carries stronger evidentiary weight than the
enterprise platforms in defamation-defence contexts because the
explanation output is reproducible and methodologically grounded,
where vendor "explainable indicators" are vendor-defined and not
openly reproducible. When XAI-Deepfakes disagrees with a
non-detector signal (provenance manifest, reverse-image hit,
archived earlier instance), the non-detector signal wins because
Anchor 2 mandates two non-detector signals before any strong
public claim. The explanation artefact is most useful when it
visualises why the underlying detector and a non-detector signal
agree, not when it tries to substitute for the non-detector
signal.

## Override notes

!!! note "Override notes"
    - **Cautious-detector with explanation (g1-cautious-detector-
    with-explanation):** XAI-Deepfakes serves the cautious-
    detector pillar with an explanation-output supplement. The
    detector verdict is one weak signal class per Anchor 1; the
    explanation output supports interpretation rather than
    adding an independent signal.

    - **Defamation-defence pointer (defamation-defence-use-case-
    pointer):** the toolkit's published-output use case targets
    defamation defence and platform-appeal evidentiary work.
    Country and platform applicability section above names the
    Sri Lanka OSA, Thai lèse-majesté and CCA, and Philippine
    COMELEC contexts where explainability output materially
    reduces legal exposure on a published debunk (regional legal-context research).

## Sources

- IDT-ITI, Centre for Research and Technology Hellas. *XAI-Deepfakes — explainable deepfake detection*. GitHub repository (open-source, CUDA/Ubuntu). [github.com/IDT-ITI/XAI-Deepfakes](https://github.com/IDT-ITI/XAI-Deepfakes).
