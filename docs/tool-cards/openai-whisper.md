---
tool_id: TOOL-177
slug: openai-whisper
name: OpenAI Whisper
maintainer: OpenAI
type: non-detector
outline_cells:
 - {id: "2A.1", role: primary, density_role: primary}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: MIT
languages_ui: [en]
languages_content: [id, ms, fil, tha, sin, tam, lao]
access: cli
cost: freemium
documented_country_use: [ID, PH, TH]
tags: [transcription, translation, asr, whisper, sea-language-nlp, productivity, open-source]
---

# OpenAI Whisper

**Vendor:** [openai.com/whisper](https://openai.com/research/whisper) | **Type:** Non-detector | **Cost:** Freemium

!!! abstract "TL;DR"
    The MIT-licensed open-source automatic speech recognition model
    that fact-checkers reach for first when a Tagalog livestream, a
    Thai parliamentary clip, or a Bahasa voice memo lands in the
    queue. Quality is operational for Indonesian, Thai, and
    Filipino; limited for Sinhala and Lao; not a substitute for the
    cell-level honest-gap on either language.

## What it does

Whisper is an encoder-decoder speech recognition model released by
OpenAI under the MIT licence. It accepts audio or video input,
returns time-aligned transcription in the source language, and can
optionally translate the transcription to English in a single pass.
The model was trained on roughly 680,000 hours of multilingual
supervised audio and ships in multiple sizes (tiny, base, small,
medium, large) so a fact-checker can trade off accuracy against
hardware. The CLI, Python library, Hugging Face integration, and
official OpenAI API all expose the same model family; local
inference on a GPU is free, the API costs roughly USD 0.006 per
audio minute.

For toolkit work the value is upstream: Whisper turns audio into
text that downstream tools can search, cluster, translate, or
match against a claim database. It does not produce a detection
signal; it produces transcripts that other tools then process.
A Bahasa political clip becomes searchable text for Yudistira; a Thai parliamentary recording becomes a transcript that
Pinpoint can entity-extract; a Filipino livestream becomes
text a journalist can scan in minutes rather than hours.

## When to use it

- A long-form audio or video source in Indonesian, Thai, Malay, or
 Filipino has arrived and the fact-checker needs a working
 transcript before any claim extraction.
- A source-identifying recording must stay on the user's machine
 for surveillance-environment reasons (Sri Lanka, Laos) and only
 the local-inference path is acceptable.
- A regional newsroom is building a transcription pipeline that
 will feed into Meedan Check or Yudistira and
 needs an open-source, MIT-licensed component rather than a
 commercial ASR vendor.
- A research lab is bootstrapping an SEA-language voice-clone
 detection pipeline and Whisper's encoder is the most plausible
 base (see piotrkawa/deepfake-whisper-features ).

## Limitations

!!! info "Limitations"
    - Hallucination risk is documented and operational: Whisper
    will invent plausible-sounding text on unclear, silent, or
    noisy audio segments, including text that never appears in
    the source. Human review is mandatory before any claim is
    drawn from the transcript.
    - Quality is uneven across the six focus languages. Indonesian,
    Thai, Malay, and Filipino are well-supported in Whisper's
    training mix; Sinhala and Lao are supported but with
    documented accuracy drops at the limits of low-resource
    performance.
    - Lao remains within the structural cell-level honest-gap
    (G-035). Whisper does transcribe Lao audio, but the output
    is unreliable enough that the operational recommendation is
    to pair Whisper Lao output with Google Cloud
    Translation as the only documented Lao text path and with
    diaspora-review or partner-mediated verification (see the
    [Laos country page](../countries/laos.md)).
    - Asymmetric Sinhala/Tamil situation per LIRNEasia research: Whisper Sinhala
    output can be cross-checked against SinLlama-adjacent and
    University of Moratuwa Sinhala-stack resources locally
    (MisinformationCorpusSinhala, SLTK tokenizer, the large
    Sinhala ASR dataset). Sri Lankan Tamil Whisper output runs
    against predominantly pan-Tamil tooling (AnaadiAI's
    TamilTokenizer, Mozilla Common Voice Tamil 425 hours) that
    does not capture Sri Lankan political named entities,
    communal narratives, or island-specific phrasing —
    partner-mediated validation through Watchdog or Hashtag
    Generation is the operational path.
    - Punctuation, speaker diarisation, and code-switching (Tagalog
    with English; Bahasa with English; Sinhala with English) are
    handled unevenly across model sizes; large-v3 is materially
    better than smaller variants but requires more GPU.

## Privacy and threat model

The local-inference path is the privacy-friendly one: the audio
file never leaves the user's machine. Run the model with the
Python library or the CLI on a workstation with a sufficient GPU
and the only data flow is internal. The OpenAI API path is
different; audio is uploaded to OpenAI's servers under that
vendor's retention policy; for source-identifying material this is
the wrong choice unless the source has explicitly consented to
that data flow.

For Sri Lanka and Laos surveillance-environment work, the
local-inference path is mandatory when the audio identifies a
source. The operational reading per Decision 7 is that Whisper's
content-language coverage is the binding selection criterion for
this NLP-class tool, and the privacy posture is set by which
deployment path the user runs.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Routing source-identifying audio through the OpenAI hosted API
    transmits the file to a US-jurisdiction vendor under that
    vendor's retention policy. Mitigation steps:

    1. Classify the audio as public, sensitive, or source-
    identifying before any transcription.
    2. For source-identifying material, run Whisper locally
    (Python library, CLI, or whisper.cpp) on a trusted machine.
    Do not invoke the OpenAI API for the same file.
    3. For Sri Lanka and Lao surveillance work the local path is
    mandatory; for Sinhala, Tamil, and Lao the local path also
    happens to be the right accuracy choice given Whisper's
    documented language coverage.
    4. If the hosted API is the only option and the source has
    consented to the data flow, redact identifying content
    (background, room tone, named references) before the upload.

## Country and platform applicability

- **Indonesia:** primary working language well-supported;
 pairs with Yudistira (MAFINDO Bahasa claim database)
 and Kalimasada in the standard MAFINDO/CekFakta
 workflow.
- **Laos:** transcribes but unreliable. Honest gap pinned
 at cell level (G-035 / G-042). Operational pairing is with
 Google Cloud Translation and with diaspora-review or
 regional partner relays per the Laos country-page entry
.
- **Malaysia:** Bahasa Malaysia coverage carries from the
 Bahasa Indonesia training base; Malay-first work that needs
 Malaysian-specific phrasing should pair with MaLLaM
 for downstream summarisation.
- **Philippines:** Filipino/Tagalog well-supported; standard
 for VERA Files and Rappler livestream transcription work.
- **Sri Lanka:** asymmetric per LIRNEasia research. Sinhala output is
 validatable against the local stack; Sri Lankan Tamil output
 needs partner-mediated validation. Watchdog and Hashtag
 Generation are the documented partners.
- **Thailand:** well-supported; standard component in
 parliamentary-clip and livestream workflows at Thai PBS, SONP
 newsrooms, and AFP Fact Check Thailand.

Platform applicability: any audio or video source the user can
download or record, relevant across Facebook, Facebook Groups, TikTok, YouTube,
LINE, WhatsApp, Telegram. The transcription operates on the file, not
the platform.

## How to access

Open-source under MIT licence at openai/whisper on GitHub. Install
via pip (`pip install openai-whisper`) for the Python CLI, or use
the Hugging Face Transformers integration. The official OpenAI
API path is an alternative when local GPU is not available;
sign-up and API key are required for that route. No account is
required for local inference; the model weights download from
Hugging Face on first run.

## Cost (current as of 2026-05)

Free for local inference. The MIT licence imposes no fee. Hardware
cost is the practical floor: large-v3 needs around 10 GB of VRAM
for comfortable real-time inference on long files, smaller models
run on more modest GPUs. The OpenAI API path is roughly USD 0.006
per audio minute (verify at the OpenAI pricing page before
budgeting). For a regional newsroom processing tens of hours of
audio per month, local inference on a single workstation
typically costs less than the equivalent API spend after the first
month.

## Quickstart

1. Install with `pip install openai-whisper` on a workstation
 with a GPU (CPU inference is possible but slow).
2. Confirm `ffmpeg` is installed; Whisper relies on it for audio
 extraction.
3. From the command line: `whisper input.mp3 --language Indonesian
 --model large-v3 --output_format txt`.
4. For Lao or Sinhala work, expect lower accuracy and treat the
 transcript as a draft requiring human review against the
 audio, not a finished record.
5. For source-identifying audio in Sri Lanka or Laos contexts,
 confirm you are running locally (no `--api` flag, no API key
 set) and not via the OpenAI API path.
6. Pipe the resulting transcript into Pinpoint, Yudistira, Meedan Check, or SEA-LION as the
 downstream step.
7. Always read at least a sample of the transcript against the
 audio before treating any extracted claim as verified; the
 hallucination caveat is binding.

## In the toolkit's workflow

Source-history pillar non-detector productivity tool per
Architectural Anchor 1. Sits in 2A.1 as the primary entry: the
open-source MIT-licensed transcription path that handles four of
the six focus-country languages well. Cell-level honest-gap is
named at section level and inherits per-language quality
disclaimers above.

Standard combinations:

- With **Google Cloud Translation** at 2A.1 when the
 source language is Lao or when cross-language work is needed
 beyond Whisper's translate-to-English mode.
- With **Pinpoint** at 2A.1 / 2B.3 when the transcript
 feeds into multi-document journalist-pipeline analysis.
- With **Yudistira** at 2B.2 when the Bahasa transcript
 needs claim extraction against MAFINDO's database.
- With **Meedan Check** at 2B.1 when the transcript is
 an intake source for a tipline workflow.
- With **SEA-LION** at 2B.3 for downstream
 summarisation, claim flagging, or LLM-assisted verification on
 the transcribed material.

Decision-tree references: [T3 audio triage](../decision-trees/t3-audio-triage.md)
reaches Whisper at T3.3 (accurate transcript) and T3.11 (unsafe
upload: on-device transcription). [T2 video triage](../decision-trees/t2-video-triage.md)
routes audio components through Whisper at T2.9 (transcript matches
caption) before any audio-detector tab is invoked.

This card carries no detector signal class: Whisper produces
transcripts, not signals. Per Anchor 1 the transcript is an input
for downstream signal classes (claim-database matches, named-
entity searches, translation cross-checks); per Anchor 2 a
transcript by itself is not publishable evidence.

## Override notes

!!! note "Override notes"
    - **Indonesian, Thai, Tagalog coverage (b2-pass-Indonesian-
    Thai-Tagalog):** Whisper's training mix includes substantial
    Indonesian, Thai, and Tagalog data; quality is operational
    for routine fact-check work in those three languages plus
    Malay (which inherits from the Bahasa Indonesian base).
    - **Sinhala/Lao limited coverage (b2-disclaimer-pass-Sinhala-
    Lao-limited):** Whisper supports Sinhala and Lao in name but
    accuracy degrades materially at the low-resource end. Lao
    remains within the cell-level honest-gap; Sinhala output is
    validatable against the local stack per LIRNEasia research; Sri Lankan
    Tamil output is asymmetrically thinner than Sinhala for the
    Sri Lanka-specific use case.
    - **Hallucination risk (hallucination-risk-binding-pointer):**
    Whisper invents plausible text on unclear or silent audio.
    Human review against the audio is mandatory before any
    claim is drawn from the transcript; this caveat is binding
    and rendered above in Limitations.

## Sources

- OpenAI. *Whisper — automatic speech recognition system*. OpenAI, 2022–2024 (MIT licence). [github.com/openai/whisper](https://github.com/openai/whisper).
- Radford, A. et al. *Robust Speech Recognition via Large-Scale Weak Supervision*. arXiv:2212.04356, 2022. [arxiv.org/abs/2212.04356](https://arxiv.org/abs/2212.04356).
