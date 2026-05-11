---
tool_id: TOOL-029
slug: deepfakebench
name: DeepfakeBench
maintainer: SCLBD (Shenzhen Big Data Research Lab and academic collaborators)
type: framework
outline_cells:
 - {id: "1C.2", role: primary, density_role: alternative}
pillar_service: [cautious-detector]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: research
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [benchmark, evaluation-harness, deepfake, academic, docker, icml-2025]
---

# DeepfakeBench

**Publisher:** [github.com/SCLBD/DeepfakeBench](https://github.com/SCLBD/DeepfakeBench) | **Type:** Framework | **Cost:** Free

!!! abstract "TL;DR"
    A free, academic, open-source benchmark and evaluation harness
    bundling 36 deepfake detectors (including an ICML 2025 spotlight
    face-and-non-face detector) with a Docker image and pre-trained
    weights. Listed in 1C.2 as the institutional research-lab path
    for evaluating candidate detectors, not as a deployable
    in-the-loop tool for fact-check workflows.

## What it does

DeepfakeBench packages 36 deepfake detectors and their pre-trained
weights into a single Docker image with a conda environment plus a
64 GB shared-memory configuration. The harness lets a research lab
run multiple detectors over the same dataset, compare per-detector
outputs, and reproduce the ICML 2025 spotlight detector's reported
results on standard benchmarks. The output is per-detector scoring
across the included models, useful for evaluating which detector
is currently strongest on a given dataset, and for reproducibility
of academic findings, but not useful as an in-the-loop production
detector inside a fact-check pipeline.

The toolkit lists DeepfakeBench in 1C.2 alongside Sensity
and Reality Defender to make the cell's institutional
character explicit: an institutional partner with technical staff
or research-lab affiliation can use DeepfakeBench to evaluate
whether a candidate detector merits inclusion in a downstream
production pipeline, while the production pipeline itself runs
Sensity or Reality Defender. Per Architectural Anchor 1, the
benchmark itself is non-detector: it is infrastructure for
evaluating detectors, not a detector that produces signals.

## When to use it

- A research lab or institutional fact-check partner is evaluating
 whether a candidate open-source detector matches the academic
 state of the art on a specific deepfake style and wants to
 reproduce ICML 2025 results before adopting it.
- A regional civil-society research project is producing a
 technical report on detector reliability for SEA-relevant
 content and needs an evaluation harness with academic provenance.
- A graduate-school or partner-university project is teaching
 detector evaluation methodology and DeepfakeBench's harness is
 the right pedagogical environment.
- An organisation considering procurement of an enterprise platform
 (Sensity, Reality Defender) wants an academic baseline against
 which to read the platform's vendor headlines.

## Limitations

!!! info "Limitations"
    - Heavy install: Docker image plus conda environment plus 64 GB
    shared memory; not suitable for casual or laptop-grade use.
    - For evaluation, not deployment: DeepfakeBench is a benchmark
    harness for testing detectors against datasets; it is not a
    production detector to integrate into a fact-check pipeline.
    - No SEA-specific dataset is bundled. The harness works on any
    dataset the analyst supplies; producing SEA-relevant
    evaluation results means the analyst must also supply the
    SEA-relevant dataset, which is itself the gap that regional research's
    "no Asian-face or SEA-language breakdown" finding describes.
    - Academic-licence research code; production-grade adoption
    requires the analyst to handle dependency management and
    hardware provisioning rather than relying on a vendor.

## Privacy and threat model

DeepfakeBench runs locally inside the analyst's Docker environment.
The dataset stays under the analyst's control; no upload to a
vendor cloud is required for the evaluation step itself. This is
the right privacy posture for institutional research work in
surveillance-environment contexts (Sri Lanka, Laos), where the
input dataset itself may be sensitive.

The threat model that matters here is downstream: an evaluation
finding that names which detector performed best on which dataset
is published research output, and the publication itself can shape
adversaries' adversarial-edit choices. Treat the evaluation
publication discipline with the same care that academic adversarial
ML literature applies: the Anchor 1 commitment to detector
skepticism includes acknowledging that publishing detector
evaluations gives adversaries information.

## Country and platform applicability

- **Indonesia:** language-agnostic; available to Indonesian
 research partners with technical-staff capacity (universities,
 CekFakta consortium technical layer).
- **Laos:** language-agnostic; available in principle to any
 research partner reaching into Laos through diaspora or regional
 collaboration; the 64 GB shared-memory hardware requirement is
 the realistic constraint.
- **Malaysia:** language-agnostic; available to MIMOS,
 Mesolitica (which maintains MaLLaM), or university
 partners.
- **Philippines:** language-agnostic; available to UP / DLSU
 / Ateneo research labs and to Rappler's technical layer; useful
 for evaluating candidate detectors before Rappler / #FactsFirstPH
 pipeline integration.
- **Sri Lanka:** language-agnostic; LIRNEasia and Watchdog
 technical capacity can run DeepfakeBench inside their research
 environment.
- **Thailand:** language-agnostic; available to Thai
 university research partners and to the AFP Medialab regional
 collaboration layer.

Platform applicability: not platform-specific. The harness operates
on whatever video and image data the research partner can supply,
under whatever licence terms cover that data.

## How to access

Free download from the SCLBD DeepfakeBench GitHub repository. Pull
the Docker image per the README, ensure a host environment with at
least 64 GB shared memory, and start the harness. No account
creation, no beta gate. Pre-trained weights are bundled or linked
from the repository.

## Cost (current as of 2026-05)

Free in software terms. The structural cost is hardware and
analyst time: the Docker image with 64 GB shared memory typically
runs on a workstation or server-grade environment rather than on a
laptop, and producing meaningful evaluation results is a
researcher's time investment measured in days rather than hours.
For institutional partners with university or research-lab access
to GPU compute, this is a non-issue; for a frontline newsroom
without that infrastructure, DeepfakeBench is structurally not the
right tier.

## Quickstart

1. Confirm a host environment with adequate compute (GPU
 recommended) and at least 64 GB shared memory.
2. Install Docker and pull the DeepfakeBench image per the
 repository README.
3. Start the conda environment inside the container.
4. Prepare or acquire an evaluation dataset relevant to the
 research question (FaceForensics++, Celeb-DF, or a regionally
 assembled dataset for SEA-specific evaluation).
5. Run the harness against the chosen dataset; inspect per-
 detector output across the 36 included models.
6. Document parameters and dataset provenance for any published
 evaluation finding; cite the ICML 2025 spotlight paper for the
 bundled spotlight detector's underlying methodology.
7. Use the evaluation result as input to a downstream procurement
 or research decision; do not use DeepfakeBench output as an in-
 the-loop production detector signal.

## In the toolkit's workflow

Non-detector evaluation framework per Architectural Anchor 1. Sits
in 1C.2 Institutional deepfake platforms as the academic / research-
lab alternative alongside Sensity (production primary) and
Reality Defender (broadcaster-grade alternative). The role
distinction matters: DeepfakeBench produces evaluation output about
detectors, where Sensity and Reality Defender produce detection
output about content.

Standard combinations:

- With **Sensity** and **Reality Defender** as
 evaluation context: institutional partners can use
 DeepfakeBench's per-detector results as a baseline against which
 to read enterprise-platform vendor headlines.
- With **TRIED Benchmark** at 1C.3 as the sociotechnical
 evaluation framework that complements DeepfakeBench's technical
 evaluation harness; TRIED provides the six-pillar Global South
 framing that DeepfakeBench's purely technical metrics do not.
- With **XAI-Deepfakes** at 1C.3 when the evaluation
 question is not "which detector scores highest" but "what does
 the detector see when it scores high": the explainability
 layer adjacent to DeepfakeBench's quantitative layer.

This card carries no detector signal class: DeepfakeBench produces
evaluation output about detectors, not detection signals per se.
Per Anchor 2, evaluation output supports procurement and research
decisions but does not by itself constitute a publishable claim
about any specific piece of suspect content.

## Override notes

!!! note "Override notes"
    - **Benchmark not deployable (g2-benchmark-not-deployable-
    declaration):** the YAML signal_class is non-detector and the
    framing throughout this card is "evaluation harness, not
    in-the-loop detector." Frontline users should not treat
    DeepfakeBench as a tool to run on suspect content during a
    fact-check; institutional partners should use it only inside
    a research-evaluation context.

## Sources

- SCLBD. *DeepfakeBench — unified benchmark for deepfake detection*. GitHub repository. [SCLBD/DeepfakeBench](https://github.com/SCLBD/DeepfakeBench).
- SCLBD. *DeepfakeBench: A Comprehensive Benchmark in Deepfake Detection*. ICML 2025 (spotlight). [arxiv.org/abs/2307.01426](https://arxiv.org/abs/2307.01426).
