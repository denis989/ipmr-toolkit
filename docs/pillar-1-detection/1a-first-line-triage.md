---
title: "1A – First-Line Triage"
summary: "Five-minute, phone-friendly pass that disqualifies obviously synthetic or obviously authentic content before the case ever reaches a desk. Carries image, video, audio, and provenance checks as four parallel modalities."
---

# 1A – First-Line Triage

First-Line Triage is the work a fact-checker does in the first five minutes after content lands in a queue, usually on a phone, often while still moving between tasks. It runs on browser extensions and one-click checkers and produces a defensible "keep working on this" or "move on" judgment without account creation, install, or institutional approval. The intended reader is anyone in a regional newsroom or civil society team who routes incoming material before it reaches a desk-based verification pass – staff on a tipline shift, a duty editor at a CekFakta partner, a Watchdog OSINT operator looking at a Telegram drop. This section sorts the four 1A modalities, names the tool to reach for first in each, and is honest about the moment to climb to [1B Professional Verification](1b-professional-verification.md) versus the moment to stop and let ordinary fact-check work do its job.

## When this tier applies

A meme of a Filipino senator endorsing an obscure crypto scheme arrives in a Viber group at 8 a.m. The fact-checker on shift has fifteen minutes before the morning editorial call. The question is not "is this the deepfake of the year" – it is "do I have to file this for the team to look at, or has the same image already been debunked by AFP Fact Check Philippines last week." That is the work [1A.1](#1a1-image) is designed to handle, in five minutes, on a phone, with two or three browser checks.

A TikTok clip of someone resembling Anutin Charnvirakul making policy claims circulates through LINE chats in Bangkok. The clip is six seconds long and heavily compressed. The duty editor wants to know whether the file carries even a baseline detector signal before forwarding to a desk reporter for a thirty-minute pass. The honest answer the toolkit gives in [1A.2](#1a2-video) is that detector class confidence on a six-second SEA-platform-compressed clip is structurally low; the productive five-minute move is non-detector – source-history through reverse keyframe search and platform-of-origin checks via [InVID-WeVerify](../tool-cards/invid-weverify.md).

A WhatsApp voice memo, alleged to be the Prime Minister of Laos approving a road contract, lands with a Lao diaspora reporter outside the country. The memo is 19 seconds, in Lao, codec-compressed through WhatsApp's voice format. [1A.3](#1a3-audio) tells the user up front: no first-line audio detector handles this case well. The five-minute pass produces an honest "escalate or stop" decision, not a verdict.

A still photograph forwarded across Facebook Groups in Jakarta claims to show a minister at a meeting with foreign businessmen. The image carries Content Credentials in its header. [1A.4](#1a4-provenance-watermark) reads the manifest in seconds and resolves the question without invoking any detector – the provenance pillar in its purest form. The same path resolves the [Thai PBS Anutin / Mauerberger February 2026 case](../countries/thailand.md) through SynthID instead of a detector probability.

These four scenarios are 1A: image, video, audio, provenance. Each runs on the same five-minute budget but with very different reliability profiles, and the section keeps them separate because conflating them is how a fact-checker on deadline ends up publishing a detector verdict as if it were a forensic conclusion.

## How techniques in this tier connect

The four cells work as parallel modalities, not as a sequential ladder. A case usually enters through one modality – the file you receive is an image, or a video, or an audio clip – but [1A.4](#1a4-provenance-watermark) sits across all three because any of the others can carry an embedded watermark or C2PA manifest. The discipline is to check provenance first whenever a clean original file is in hand; a watermark-bound verdict is a non-detector signal that outranks any probability score under Architectural Anchor 1.

Where a case crosses modalities mid-triage – the still came from a video, the audio is a soundtrack lifted from a clip on TikTok – move between cells without leaving the tier. A still extracted from a TikTok video reaches [1A.1](#1a1-image) for reverse search and detector triage; the original video reaches [1A.2](#1a2-video) for keyframe and reverse-image work; if either carries provenance, both fall back to [1A.4](#1a4-provenance-watermark) before the detector tabs run. The decision trees codify this routing: [T1 image triage](../decision-trees/t1-image-triage.md), [T2 video triage](../decision-trees/t2-video-triage.md), [T3 audio triage](../decision-trees/t3-audio-triage.md), and [T4 provenance triage](../decision-trees/t4-provenance-triage.md) are the operational entry points for the four cells in this section.

Two of the [architectural anchors](../methodology/architectural-anchors.md) operate inside every 1A pass. Multi-detector consensus counts as one signal class, not three, so running an image through Hive plus [ImageWhisperer](../tool-cards/imagewhisperer.md) plus a third option is still one signal under Anchor 3. And no strong public claim follows from a detector signal alone – Anchor 2 requires at least one non-detector signal before a synthetic label, which is why reverse-image work and provenance checks share the same tier as the detectors and not a step below.

## What this tier produces

A defensible first-line judgment that can be acted on within the five-to-thirty-minute window: file the case for desk work, route to the tipline coalition, return to source for context, or stop. The output is not a verdict on whether the content is AI-generated. It is a decision on whether the case warrants further time at all, paired with the non-detector evidence collected along the way – the reverse-image hits, the C2PA manifest read, the absence of metadata as a signal in itself – which the desk reporter at [1B](1b-professional-verification.md) inherits without having to re-derive it.

## When to escalate, when to stop

Escalate to [1B Professional Verification](1b-professional-verification.md) when the harm profile of the case justifies thirty minutes of desk work and 1A has not closed the question – the image survived reverse search, no provenance manifest was found, detector signals were inconclusive, the claim is consequential. Climb directly to [1C Institutional-Level Analysis](1c-institutional-analysis.md) only if 1A surfaces evidence that the case needs partner-mediated tooling immediately – an enterprise-grade deepfake platform for broadcaster-level certification, for example – which is uncommon at the triage tier.

Stop when 1A produces no first-line AI evidence AND the broader claim is verifiable through ordinary fact-check work that does not need synthesis judgment. The [T5 escalation tree](../decision-trees/t5-escalation.md) calls this out explicitly: a meme that is plausibly authentic but mis-captioned does not need a deepfake pipeline, it needs a reverse search and a fact-check database lookup. Rabbit-holing into detector tabs on a case that does not warrant them is the most common waste of newsroom time in this tier, and the tree is the operational discipline against it.

## The cells in detail

### 1A.1 – Image

A still image is the most common 1A input – a screenshot from a Telegram channel, a poster shared in a Facebook Group, an AI-looking portrait circulating on Instagram. The cell ships three tools that cover the productive five-minute moves on a phone or a laptop browser: a multimodal commercial detector for the probability read, an uncertainty-declaring open alternative for the borderline cases, and a non-detector provenance check that often resolves the question before any detector runs.

For the routine pass on public-content, run [Hive AI](../tool-cards/hive-ai.md) first. It is fast, multimodal, and documented in the Brawner casework at 79.3%; the vendor's 99% claim is paired against the Ha 2024 University-of-Chicago benchmark at 98.03% inside the tool card. When the image is compressed, low-resolution, or already AI-suspicious enough that a single probability score will not earn confidence, switch to [Imagewhisperer](../tool-cards/imagewhisperer.md), which is designed to admit "I don't know" instead of forcing a binary call. For any image where the original file is in hand and might carry C2PA Content Credentials – a Reuters-bylined photo, a press release image, a Google-product output – check [Content Credentials Verify](../tool-cards/content-credentials-verify.md) first; a manifest answers the question without invoking either detector. Per Anchor 3 the two detectors together count as one signal class, so running both does not produce two independent reads.

Honest gap: independent benchmarks on Asian faces and SEA-region content remain thin. The Ha 2024 figures are derived from a Western dataset, and no SEA-specific test exists for any of the three tools in this cell. The [T1 image triage tree](../decision-trees/t1-image-triage.md) carries the routing logic; for a clean case, expect to spend three minutes on Content Credentials, two minutes on reverse image, and reach for a detector only if the first two surface nothing.

### 1A.2 – Video

A first-line video pass is harder than the image equivalent. The best commercial video detectors in the Deepfake-Eval-2024 anonymised pool reached 0.78 accuracy on 2,036 in-the-wild clips, per independent benchmark evidence, and there is no public benchmark for SEA-platform-compressed footage. The cell deliberately runs thin and refuses to inflate density with vendor-only entries that would imply false confidence under Anchor 3.

Two tools cover the cell. [InVID-WeVerify](../tool-cards/invid-weverify.md) is the workhorse – its reverse-image, archived-version, and keyframe extraction modules produce non-detector source-history signals that often resolve the question before the user ever reaches the deepfake tab. [Deepware Scanner](../tool-cards/deepware-scanner.md) is the press-button option when a single quick detector signal is wanted alongside the InVID-derived non-detector evidence. Per Anchor 3 the InVID deepfake tab and Deepware together count as one detector class.

The cell carries two honest gaps that bind on every card – SEA-platform-compressed video has no independent benchmark (gap G-031), and detector class confidence is structurally low for short clips. The [T2 video triage tree](../decision-trees/t2-video-triage.md) routes the work: keyframes first, reverse search second, detector only after non-detector signals have been exhausted. When the case needs pixel-level scrutiny or broadcaster-grade certification, the escalation is to [1C.2 enterprise platforms](1c-institutional-analysis.md#1c2-enterprise-open-source-deepfake-platforms), not to another 1A tool.

### 1A.3 – Audio

A WhatsApp voice memo or a LINE forwarded clip in Lao, Sinhala, Tamil, or Thai is the worst case for first-line audio detection. The [DW Innovation](../tool-cards/dw-innovation-audit.md) civil-society audit (Synthetic Audio Detectors Put to the Test, September 2025) tested the major audio detectors against a ten-sample multilingual dataset and confirmed that the class is broken across SEA languages, codec compressions, and tonal phonetics. There is no press-button option at this tier that handles WhatsApp-codec audio reliably.

The section ships one tool by design. [Hive AI](../tool-cards/hive-ai.md) is the multimodal entry for a quick language-agnostic read on glaring waveform anomalies, with the binding instruction that no binary verdict ever follows from a 1A audio scan. The honest gaps the cell carries are non-trivial: no Lao-language audio detector exists at the FLT tier (gap G-042), the Sinhala/Tamil asymmetry from LIRNEasia research means Tamil leans on pan-Tamil resources while Sinhala has neither a tool nor a corpus at this layer, and WhatsApp and LINE codec compressions are not independently tested in any public audit (gap G-017).

The [T3 audio triage tree](../decision-trees/t3-audio-triage.md) puts transcription and human listening before any detector run for exactly this reason: most cases at 1A close on the transcript, on a reverse search of the speaker's recent public statements, or on a same-day human listening pass with a colleague who speaks the source language. Escalation is to [1B.3 audio deepfake forensics](1b-professional-verification.md#1b3-audio-deepfake-forensics) when the case warrants thirty minutes of desk work, or laterally to [1A.4](#1a4-provenance-watermark) if the audio came with a watermark.

### 1A.4 – Provenance / watermark

This is the only Pillar 1 tier where non-detector signals are the primary mode. When an image, a video, or an audio file carries C2PA Content Credentials, a SynthID watermark, or a creator-attestation manifest, the question shifts from "is this AI-generated" to "what does the provenance metadata say about who made this and how." A clean watermark read at 1A.4 outranks any probability score the rest of 1A could produce – the same move that resolved the Thai PBS Anutin / Mauerberger February 2026 case through [SynthID Detector](../tool-cards/synthid-detector.md) without a detector tab firing.

The cell ships a verifier-first triad. [Content Credentials Verify](../tool-cards/content-credentials-verify.md) is the first stop for any C2PA-bearing file – the manifest reads in seconds and resolves the question without further work. [SynthID Detector](../tool-cards/synthid-detector.md) is the right tool when the suspect content was generated through a Google product (Imagen, Veo, Lyria); it returns a watermark-confirmed synthesis verdict the user can cite as a non-detector signal. [C2PA Conformance Explorer](../tool-cards/c2pa-conformance-explorer.md) is the forensic inspection layer for when the manifest itself is under question – chain integrity, signer validation, manifest-type identification – usually a handover to a desk-tier pass at [1B.1](1b-professional-verification.md#1b1-multi-tool-plugins) when the suspicion is technical.

Honest gap: manifest survival across the SEA hardware and platform stack is not independently documented. Whether C2PA metadata survives a forward through WhatsApp, a re-upload to Facebook, a TikTok ingest, or a Realme / Vivo / Oppo / Xiaomi / Transsion handset's camera pipeline is not publicly benchmarked (gap G-019). When provenance is absent or stripped, the cell hands off downward to [1B.4 metadata / ELA forensics](1b-professional-verification.md#1b4-metadata-ela-forensics); when provenance is present and clean, the case usually closes here. The [T4 provenance triage tree](../decision-trees/t4-provenance-triage.md) is the routing layer.

## Cross-references

- [T1 image triage](../decision-trees/t1-image-triage.md) – cell 1A.1 operational entry
- [T2 video triage](../decision-trees/t2-video-triage.md) – cell 1A.2 operational entry
- [T3 audio triage](../decision-trees/t3-audio-triage.md) – cell 1A.3 operational entry
- [T4 provenance triage](../decision-trees/t4-provenance-triage.md) – cell 1A.4 operational entry
- [T5 escalation](../decision-trees/t5-escalation.md) – stop-vs-escalate decision when 1A is inconclusive
- [T6 source-protection](../decision-trees/t6-source-protection.md) – read alongside 1A whenever the source file is identifying or sensitive
- [1B Professional Verification](1b-professional-verification.md) – the desk-tier escalation
- Country pages: [Thailand](../countries/thailand.md) (SynthID / Anutin), [Philippines](../countries/philippines.md) (Doc Willie Ong cross-tier), [Indonesia](../countries/indonesia.md) (CekFakta tipline routing into 1A)
- Platform pages: [WhatsApp](../platforms/whatsapp.md), [LINE](../platforms/line.md), [TikTok](../platforms/tiktok.md), [Facebook](../platforms/facebook.md)

## Sources

- Ha, B. et al. *Organic or Diffused: Can We Distinguish Human Art from AI-generated Images?* ACM CCS 2024. (Image detector robustness under adversarial edits; baseline for 1A.1 detector-as-weak-signal framing.)
- Lyu, S. et al. *Deepfake-Eval-2024: A Real-World Benchmark for Deepfake Detection.* 2025. [arxiv.org/abs/2503.02857](https://arxiv.org/abs/2503.02857). (Anonymised commercial pool; category-level ceiling for video detectors; SEA-platform-compressed video context.)
- DW Innovation. *Synthetic Audio Detectors Put to the Test.* Deutsche Welle, 29 September 2025. [innovation.dw.com/articles/synthetic-audio-detectors-tested](https://innovation.dw.com/articles/synthetic-audio-detectors-tested). (Audio detector failure modes; Lao audio gap; WhatsApp / LINE codec failure at 1A.3.)
- Coalition for Content Provenance and Authenticity (C2PA). *C2PA Technical Specification 2.x.* [c2pa.org](https://c2pa.org/specifications/). (C2PA SEA hardware survival constraints; provenance-first framing at 1A.4.)
- Country pages: [Thailand](../countries/thailand.md) (Anutin / SynthID provenance-first case), [Philippines](../countries/philippines.md) (Doc Willie Ong cross-tier reference).
- [Architectural Anchors](../methodology/architectural-anchors.md) — Anchors 1–3 as operationalised across the 1A cells.
