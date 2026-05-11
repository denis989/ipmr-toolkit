---
tool_id: TOOL-010
slug: trufor
name: TruFor
maintainer: GRIP-UNINA (vera.ai partner; DARPA-backed under agreement FA8750-20-2-1004)
type: mixed-with-declaration
outline_cells:
 - {id: "1C.3", role: primary, density_role: alternative}
pillar_service: [cautious-detector, source-history]
signal_class: mixed-with-declaration
status: active
last_verified: 2026-05-10
license: research
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [image-forensics, manipulation-localisation, pixel-map, integrity-score, reliability-map, cvpr-2023, vera-ai, darpa]
---

# TruFor

**Publisher:** [github.com/GRIP-UNINA/TruFor](https://github.com/GRIP-UNINA/TruFor) | **Type:** Detector + non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free image-forgery localisation framework from GRIP-UNINA
    (vera.ai partner, DARPA-backed) that produces a pixel-level
    manipulation map plus an integrity score plus a reliability
    map quantifying confidence in the map itself. CVPR 2023.
    Alternative 1C.3 entry, where the reliability-map output is the
    distinguishing feature for fact-checker UI and evidence-grade
    work.

## What it does

TruFor takes an image as input and produces three coordinated
outputs. The pixel map highlights regions of the image flagged as
manipulated. The integrity score is a single overall probability
that the image as a whole has been manipulated. The reliability
map is the distinguishing output: it visualises how confident the
system is in its own per-pixel verdict, region by region. Where a
classical localisation tool produces "this region is fake" with
no uncertainty bound, TruFor produces "this region is fake AND we
are or are not confident in that verdict here," which is the form
of output a working fact-checker can actually publish next to a
debunk.

The toolkit treats TruFor as mixed-with-declaration per
Architectural Anchor 1: the integrity score is a cautious-detector
signal that combines under Anchor 3 with other detector classes,
while the reliability map is a non-detector source-history signal
that quantifies how trustworthy the localisation is. The
explicit-declaration framing (g2-reliability-map-non-detector-
declaration) means a fact-checker can cite the reliability map as
one non-detector signal under Anchor 2's two-non-detector-signal
floor, separate from the underlying detection probability.

The framework was introduced at CVPR 2023 and remains the academic
reference for image-forgery localisation in 2025-2026. The
maintainer is GRIP-UNINA (Image Processing Research Group at the
University of Naples Federico II), a partner in the vera.ai
consortium that also maintains the InVID-WeVerify plugin (InVID-WeVerify Verification Plugin),
which gives TruFor structural alignment with the toolkit's existing
1B.1 multi-tool plugin lineage.

## When to use it

- A defamation-defence file requires per-pixel localisation of
 manipulated regions, with a confidence map showing where the
 localisation itself is trustworthy.
- A regional fact-check is investigating cheapfake screenshots (the
 dominant SEA manipulation form ) and needs
 to localise inserted or edited regions, not detect a
 generative-AI verdict.
- A research-grade publication needs the academic state of the art
 in image-forgery localisation with reproducible methodology
 (CVPR 2023 paper).
- A fact-checker UI is being designed and the reliability-map
 output is being incorporated as a visualisation primitive (the
 inventory's killer-feature framing).

## Independent accuracy

!!! warning "Vendor claim vs independent assessment"
    **Vendor positioning:** TruFor is positioned as an academic
    image-forgery localisation framework with peer-reviewed
    methodology (CVPR 2023). The maintainer does not market a
    single headline accuracy figure; the reported metrics in the
    paper are per-dataset (FaceForensics++, COVERAGE, MFC) rather
    than a single overall claim. The framework's distinguishing
    contribution is the reliability map quantifying confidence in
    the localisation, not a higher headline accuracy than other
    forgery-localisation methods.

    **No independent SEA-specific benchmark identified as of May
    2026.** TruFor inherits the the Deepfake-Eval-2024 cross-category gap: per-region
    or Asian-face score breakdowns are not publicly available for
    image-forgery localisation methodology of this generation. The
    framework's editorial value sits in the reliability-map output
    and the academic provenance, not in a vendor-style headline
    accuracy claim.

## Limitations

!!! info "Limitations"
    - Detects manipulation, not generation. TruFor
    is engineered for localising image edits (the cheapfake
    modality dominant in SEA), not for binary "is this
    AI-generated?" verdicts. The toolkit's editorial framing is
    that this is a feature, not a limitation, but a user
    expecting an AI-generation probability score will be
    disappointed.
    - Training set is restricted: training code is partner-only
    under the DARPA agreement (FA8750-20-2-1004), which means
    external organisations cannot retrain the model on SEA-
    relevant data without partner-mediated arrangements
.
 - Test code is released; only the test container path is
 open to general use.
 - Reliability map output requires careful interpretation: a
 low-reliability region is not the same as a non-manipulated
 region. The output trains operator judgement; it does not
 replace it.
 - No SEA-language documentation; English academic-paper
 framing only.

## Privacy and threat model

TruFor's test container runs locally inside the analyst's Docker
environment. The suspect image stays under the analyst's control;
no upload to a vendor cloud is required for the localisation step.
This is the right privacy posture for surveillance-environment
work in Sri Lanka and Laos, and for defamation-defence work
generally where the suspect file may be sub judice.

The DARPA-restricted training code path matters for the threat
model in a different way: external organisations cannot retrain
TruFor on SEA-specific data without working through the consortium
or the DARPA partner channel. For institutional partners
considering an SEA-adapted version of TruFor, the path runs
through vera.ai consortium membership, not through an open-source fork.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    TruFor's intended use is local; any public web demo or shared
    server deployment changes the threat model. Mitigation steps:

    1. Classify the suspect file as public, sensitive, or source-
    identifying before invoking TruFor.
    2. For source-identifying material, run only the local Docker
    container on a trusted machine; do not use any shared or
    public web demo for the same file.
    3. Preserve the original file on the analyst's machine with
    documented chain of custody; do not move it to cloud
    collaboration tools that would constitute an indirect
    upload to a vendor server.
    4. If the case requires institutional escalation, route through
    vera.ai consortium membership, not by emailing the file to an
    external lab.

## Country and platform applicability

- **Indonesia:** language-agnostic for visual modules;
 available in principle to Indonesian academic and newsroom-
 technical partners with Docker capability.
- **Laos:** language-agnostic; the local-execution model is
 privacy-defensible. No documented Lao-specific deployment.
- **Malaysia:** language-agnostic; available to MIMOS,
 Mesolitica, or university partners.
- **Philippines:** language-agnostic; available to UP / DLSU /
 Ateneo and to Rappler's technical layer; particularly relevant
 for cheapfake-screenshot cases that the toolkit's SEA inventory
 notes as the dominant manipulation form (SEA-
 relevance entry).
- **Sri Lanka:** language-agnostic for visual modules;
 LIRNEasia and Watchdog technical capacity can run TruFor inside
 their research environment; the reliability-map output is
 particularly valuable under Sri Lanka's OSA framework where
 evidentiary defence matters.
- **Thailand:** language-agnostic; available to Thai
 university partners; cheapfake-screenshot cases dominate Thai
 political content per inventory framing.

Platform applicability: not platform-specific. Operates on any
image file the analyst can supply.

## How to access

Free download of the test container from the GRIP-UNINA TruFor
repository on GitHub. Pull the Docker image per the README and
run inference on the analyst's input. Training code remains
partner-only under the DARPA agreement; only the test path is
publicly accessible. No account creation is required for the
test path.

## Cost (current as of 2026-05)

Free in software terms for the test container path. The structural
cost is hardware and analyst time: a CUDA-capable GPU is
recommended for usable inference speeds, and producing publication-
ready forensic-report artefacts is an analyst's time investment
measured in hours rather than minutes per image. For institutional
partners with university or research-lab GPU access, this is a non-
issue; for a frontline newsroom without GPU infrastructure, the
path is partner-mediated rather than direct.

## Quickstart

1. Confirm a host environment with Docker and a CUDA-capable GPU.
2. Pull the GRIP-UNINA TruFor test container from GitHub per the
 repository README.
3. Place the suspect image in the input directory.
4. Run inference; inspect the three outputs: pixel manipulation
 map, integrity score, reliability map.
5. Read the reliability map first: regions where reliability is
 low are regions where the pixel manipulation map should not
 carry decisive evidentiary weight.
6. For a publishable finding, attach all three outputs (pixel map,
 integrity score, reliability map) to the published debunk
 rather than the integrity score alone.
7. Cross-check with XAI-Deepfakes for parallel
 explainability output and with Sherloq for offline
 ELA on the same image.

## In the toolkit's workflow

Mixed-with-declaration per Architectural Anchor 1. Sits in 1C.3
Institutional explainable AI forensics as alternative behind
XAI-Deepfakes (primary, GradCAM / SHAP / LIME on a
deepfake classifier) and ahead of TRIED Benchmark
(institutional reference framework, not a deployable tool). The
role distinction matters: XAI-Deepfakes is detector-with-
explanation, TruFor is localisation-with-reliability-of-localisation.
The two cover complementary evidence-grade use cases.

Standard combinations:

- With **XAI-Deepfakes** at 1C.3 for parallel forensic
 output on the same suspect image; XAI-Deepfakes explains
 classifier output, TruFor localises manipulation. The two
 together cover the "is it AI?" and "where is it edited?"
 questions in one institutional-tier analysis.
- With **Sherloq** at 1B.1 / 1B.4 for offline ELA on
 the same image when the suspect file cannot leave the analyst's
 machine.
- With **InVID-WeVerify** at 1B.1 – TruFor and InVID
 share vera.ai consortium provenance, which means findings
 derived from the two together carry consistent maintenance and
 evidentiary lineage.
- With **TRIED Benchmark** at 1C.3 for sociotechnical
 evaluation of TruFor's reliability-map output against six-
 pillar Global South criteria before any publishable finding.

This card carries a mixed signal class. The integrity score is one
detector signal class per Anchor 1; the reliability map is a non-
detector source-history signal that quantifies how trustworthy the
localisation is. Per Anchor 2, the reliability map combines
cleanly with reverse-image hits, provenance manifests, archived
earlier instances, or tipline-database matches as one of the two
non-detector signal classes required for any strong public claim.

Decision-tree references: [T5 escalation](../decision-trees/t5-escalation.md)
routes here at T5.6 (image professional) when the case warrants
institutional-tier localisation analysis. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes through TruFor's local-execution model when the suspect file
cannot leave the analyst's machine.

## Conflict resolution behaviour

When TruFor's integrity score disagrees with another detector
(Sensity, Hive, InVID's deepfake tab),
TruFor carries weaker headline-accuracy weight than the enterprise
platforms because the framework is engineered for localisation
rather than for AI-generation classification. It carries stronger
weight than enterprise platforms in cheapfake-screenshot cases (the
dominant SEA manipulation form) because TruFor is
architecturally aligned with manipulation-detection rather than
generation-detection. The reliability map is a separate non-
detector signal class that does not enter the detector-versus-
detector arbitration; it is a confidence quantifier on TruFor's
own localisation. When TruFor disagrees with a non-detector signal
(provenance manifest, reverse-image hit, archived earlier instance),
the non-detector signal wins because Anchor 2 mandates two non-
detector signals before any strong public claim, and TruFor's own
reliability map is itself one of the two if it confirms the
non-detector signal.

## Override notes

!!! note "Override notes"
    - **Reliability-map non-detector declaration (g2-reliability-
    map-non-detector-declaration):** TruFor's signal_class is
    mixed-with-declaration. The integrity score is one detector
    signal class per Anchor 1; the reliability map is a non-
    detector source-history signal that combines under Anchor 2
    as one of the two non-detector signals required for a strong
    public claim. The workflow section invokes this declaration
    explicitly.

    - **Local Docker test container (d4-pass-Docker-test-
    container):** the test path runs inside Docker on the
    analyst's machine and does not upload the suspect file to a
    vendor cloud. Privacy section frames the local-execution
    model as the privacy-defensible posture for surveillance-
    environment work.

## Sources

- Guillaro, F. et al. *TruFor: Leveraging All-Round Information for Image Forgery Detection and Localization*. CVPR 2023. [arxiv.org/abs/2212.10957](https://arxiv.org/abs/2212.10957).
- GRIP-UNINA. *TruFor repository*. GitHub. [github.com/GRIP-UNINA/TruFor](https://github.com/GRIP-UNINA/TruFor).
- vera.ai consortium. *vera.ai — verification tools and research*. EU Horizon project. [invid-project.eu](https://invid-project.eu).
