---
title: "2A – AI-Assisted Workflows"
summary: "The productivity layer of Pillar 2 – transcription, translation, reverse-image and geolocation work, prebunking and media literacy. Tools that turn AI into the fact-checker's assistant, not the subject of the investigation."
---

# 2A – AI-Assisted Workflows

2A is the entry tier of Pillar 2 and a different kind of work from anything in Pillar 1. Where Pillar 1 asks "is this content AI-generated?", Pillar 2 asks "how do we use AI to do counter-disinformation work better?" The 2A cells are the productivity layer – the transcription that turns a Lao voice memo into searchable text, the reverse image search that resolves a still before any detector touches it, the prebunking programme that teaches an audience to recognise manipulation patterns before a viral hit lands. The intended reader is a working fact-checker integrating AI tools into routine practice, a newsroom editor coordinating verification across a shift, a trainer running a media-literacy workshop, or a civil society team setting up archival capacity. What follows is a tour of the four 2A cells, the framing the toolkit applies to each (especially 2A.4, which is included as an adjacent pointer rather than a primary recommendation row), and the forward route to [2B Collaborative Verification](2b-collaborative.md) when 2A work surfaces a verifiable claim worth tipline-grade routing.

## When this tier applies

A Lao-language voice memo from a contested provincial meeting reaches a Lao-diaspora reporter outside the country. The reporter needs the audio transcribed and translated into English for the editor. [2A.1](#2a1-transcription-summarisation-translation) covers the cell: [OpenAI Whisper](../tool-cards/openai-whisper.md) runs locally for routine work, [Google Cloud Translation](../tool-cards/google-cloud-translation.md) handles the Lao path that no comparable open-source tool covers, [Google Pinpoint](../tool-cards/google-pinpoint.md) is the journalist-pipeline option when the case is multi-source and Google-server upload is acceptable for the threat model.

A Facebook Group repost circulates a still showing a politician in front of a building the caption calls a foreign embassy. The desk reporter wants a geolocation pass before any of the rest of the verification work begins. [2A.2](#2a2-reverse-image-geolocation-enhanced) routes the case through [InVID-WeVerify](../tool-cards/invid-weverify.md) for reverse-image fan-out, [GeoSpy](../tool-cards/geospy.md) for AI-assisted geolocation, [Citizen Evidence Lab YouTube Data Viewer](../tool-cards/citizen-evidence-lab-ydv.md) for upload-metadata if the still came from YouTube, and [Auto Archiver](../tool-cards/auto-archiver.md) for the rapid-archive step that preserves the source URL before it changes or disappears.

A regional partner is preparing a pre-election media literacy workshop in Indonesia and wants to ground it in something that has actually been measured for effect. [2A.3](#2a3-prebunking-media-literacy) is one of the few cells in the toolkit where regional gold-standard examples already exist – [Tempo Detektif Deepfake](../tool-cards/tempo-detektif-deepfake.md) (WAN-IFRA Silver April 2026), [IREX Learn to Discern via Gali Fakta](../tool-cards/irex-l2d-gali-fakta.md), [Jigsaw Prebunking](../tool-cards/jigsaw-prebunking.md), [Bad News](../tool-cards/bad-news.md). The cell is rich because the work is rich.

A newsroom editor at Tempo wants a sense of how Indonesian newsrooms have orchestrated AI assistance around verification at the workflow level. [2A.4](#2a4-newsroom-workflow-management) treats the category as an adjacent pointer, with two SEA-grounded examples ([Tempo Assistant](../tool-cards/tempo-assistant.md) and [MAFINDO Satgas Pemilu](../tool-cards/mafindo-satgas-pemilu.md)), without recommending newsroom-AI orchestration as a primary deployment row. The cell is deliberately short.

## How techniques in this tier connect

2A cells are productivity inputs to other cells, not signal generators on their own. A 2A.1 transcript feeds into [2B.2 claim extraction](2b-collaborative.md#2b2-ai-claim-extraction) – the transcript is what the claim-extraction tool actually processes. A 2A.2 reverse-image hit produces a non-detector source-history signal that combines with [1B.1 multi-tool plugin work](../pillar-1-detection/1b-professional-verification.md#1b1-multi-tool-plugins) under Architectural Anchor 2 toward a publishable verification. 2A.3 prebunking is the editorial / strategic layer – the work that does not produce detection signals at all but shapes the audience's capacity to recognise manipulation patterns. 2A.4 sits adjacent: not a detection step, not a routine routing step, a design-pattern reference for newsrooms that want to think about how AI assistance fits their workflow.

The [architectural anchors](../methodology/architectural-anchors.md) apply, but at this tier they read as reminders, not as gates. Anchor 1 says these tools sit on the productivity / source-history / editorial-strategic side of the pillar map, not on the detector side. Anchor 2 still binds when 2A work outputs enter a verification pipeline – a 2A.1 transcript that becomes evidence in a published debunk still needs two non-detector signals supporting any synthetic label, but the labelling work happens downstream in 2B and 1B, not in 2A itself. Anchor 3 is dormant at 2A because the cell does not run detectors.

## What this tier produces

Working artefacts that feed downstream verification: transcripts and translations ready for claim-matching, reverse-image evidence with archived URLs, geolocation reads with plausibility narratives, training materials a regional partner can deploy in a workshop, design-pattern references for editors thinking about newsroom AI integration. None of these are verdicts. All of them are inputs to the verdicts that 2B and Pillar 1 produce.

## When to escalate, when to stop

Move forward to [2B Collaborative Verification](2b-collaborative.md) when 2A work surfaces a verifiable claim worth tipline-grade routing and AI-assisted extraction: a transcript that turns out to contain a fact-checkable claim, a reverse-image hit that turns out to be one of fifty similar reposts across platforms, a translated voice memo that warrants community-level distribution of a debunk. Move sideways into Pillar 1 when 2A productivity work surfaces an artefact that needs verification on its own terms – the Lao voice memo whose authenticity is the question, the still whose AI-generation is the question – which routes back through [1A First-Line Triage](../pillar-1-detection/1a-first-line-triage.md) or [1B Professional Verification](../pillar-1-detection/1b-professional-verification.md) depending on time and harm profile.

Stop when 2A has produced the artefact the next step needs and that next step is not yours – the transcript heads to a colleague handling the claim, the workshop material heads to the trainer running the session, the design-pattern reference heads to the editor planning workflow changes. The [T7 tipline routing tree](../decision-trees/t7-tipline-routing.md) is the operational layer when the artefact lands at a tipline; the [T5 escalation tree](../decision-trees/t5-escalation.md) is the layer when 2A surfaces a case that needs Pillar 1 work.

## The cells in detail

### 2A.1 – Transcription, summarisation, translation

A fact-checker handling a Lao-language voice memo, a Thai parliamentary transcript, or a Tagalog Facebook livestream needs transcription, translation, and summarisation that can keep the source material on the user's machine when sensitivity demands it. The cell ships three tools at three different privacy postures.

[OpenAI Whisper](../tool-cards/openai-whisper.md) is the open-source primary – MIT-licensed, runs locally, supports Indonesian, Thai, and Tagalog well; the disclaimer pass binds on Sinhala and Lao where Whisper's low-resource performance is documented (documented low-resource performance evidence ([DW Innovation](../tool-cards/dw-innovation-audit.md) audit and Deepfake-Eval-2024)). [Google Cloud Translation](../tool-cards/google-cloud-translation.md) is the only documented path for Lao text translation in the toolkit's shortlist – paid API, with the Google-server caveat that binds the S1 source-protection override when the source material is identifying. [Google Pinpoint](../tool-cards/google-pinpoint.md) is the journalist-pipeline option that handles fifteen-language audio, OCR, and entity extraction; it is documented in the toolkit as a cross-cell tool that also serves 2B.3 LLM-driven fact-check work.

All three are non-detector productivity tools under Architectural Anchor 1. The cell-level honest gaps are multipart: Lao automatic speech recognition is genuinely thin (gap G-035), and Whisper's Sinhala and Lao accuracy is documented as low-resource. The toolkit names this. Users arrive at 2A.1 naturally as the first stop in any non-image case; the bridge sideways is to [2A.2](#2a2-reverse-image-geolocation-enhanced) for visual-modality work, and the bridge forward is to [2B.3 LLMs in fact-check workflows](2b-collaborative.md#2b3-llms-in-fact-check-workflows) when the transcript becomes the input to LLM-assisted draft work.

### 2A.2 – Reverse-image / geolocation enhanced

Reverse image search and AI-assisted geolocation are where most non-text claims start to resolve – long before any detector touches the file. The cell pairs the Pillar 1 multi-tool plugin with three specialised AI-assistance tools and an archival companion.

[InVID-WeVerify](../tool-cards/invid-weverify.md) is the default starting point – its plugin handles reverse-image queries to Google, Bing, Yandex, Baidu, and TinEye in one click, plus archived versions and metadata in the same session. [GeoSpy](../tool-cards/geospy.md) augments geolocation when the image is location-specific, with the Faktisk-validated reading the GeoSpy card documents. [Citizen Evidence Lab YouTube Data Viewer](../tool-cards/citizen-evidence-lab-ydv.md) extracts upload metadata for any YouTube-sourced clip – an Amnesty-maintained tool with no upload risk to the source file. [Auto Archiver](../tool-cards/auto-archiver.md) captures the source as evidence per the gap G-030 rapid-archiving requirement, with the WACZ-format capture preserving live state plus metadata for chain of custody.

All four are non-detector source-history signal generators. Per Anchor 2 a reverse-image hit is one non-detector signal that combines with claim-extraction (2B.2) or fact-check-database (1B.5) hits before any public characterisation. The cell carries no major honest gap at the cell level because the tools work language-agnostically, though the [T1 image triage tree](../decision-trees/t1-image-triage.md) and [T2 video triage tree](../decision-trees/t2-video-triage.md) note vendor-side region restrictions on facial-recognition geolocation tools (Lenso.AI excluded via the E5 anti-criterion). The entry from 2A.2 is usually from 2A.1 or directly from [1A.1](../pillar-1-detection/1a-first-line-triage.md#1a1-image) / [1A.2](../pillar-1-detection/1a-first-line-triage.md#1a2-video); the bridge upward is to [1B.1](../pillar-1-detection/1b-professional-verification.md#1b1-multi-tool-plugins) when archival depth is needed.

### 2A.3 – Prebunking / media literacy

Prebunking is one of the few areas where SEA already has gold-standard regional examples, and the cell deliberately runs rich (per Decision 8). Unlike most cells in the toolkit, this is not a detection or verification routine; it is a teaching layer. Trainers use these tools, not on individual artefacts but as the architecture of media-literacy workshops and pre-election information campaigns.

[Tempo Detektif Deepfake](../tool-cards/tempo-detektif-deepfake.md) is the primary – Bahasa Indonesia, WAN-IFRA Silver April 2026 winner, deployed by Tempo as part of the broader CekFakta-coalition prebunking effort. [IREX Learn to Discern via Gali Fakta](../tool-cards/irex-l2d-gali-fakta.md) is the IREX / RAND-tested alternative that documented a 25% improvement in multi-source-checking behaviour among trained participants. [Jigsaw Prebunking](../tool-cards/jigsaw-prebunking.md) is the Google campaign deployed in Indonesia, surfaced via passive video views on YouTube and Facebook. [Bad News](../tool-cards/bad-news.md) is the foundational Cambridge inoculation-game architecture – not deployed directly in SEA outside Indonesia, but the architectural reference any trainer in Thailand, Sri Lanka, Malaysia, or Laos can adapt to local languages because no SEA-localised inoculation game outside the Indonesian deployments yet exists.

The cell-level honest gap is that localised prebunking effectiveness has not been measured outside Indonesia (gap G-051). Thai, Filipino, Sinhala, Tamil, Malay, and Lao localised effectiveness data does not exist in the public literature the toolkit drew on. The cell does not need to be wrapped in non-detector signal pairs because it does not produce detection signals at all under Anchor 1. The bridge sideways is to [2A.1](#2a1-transcription-summarisation-translation) when training material itself needs transcription; the bridge upward is to [2B.1 multilingual tiplines](2b-collaborative.md#2b1-multilingual-tiplines) when prebunking deployment generates community feedback worth processing through a tipline.

### 2A.4 – Newsroom workflow management

This cell asks whether newsroom workflow management belongs in a counter-disinformation toolkit at all, and answers: include as adjacent pointer, not as a primary recommendation row. Two tools fill the cell as SEA-grounded examples of newsroom-AI orchestration; neither is a tool to run on a claim.

[Tempo Assistant](../tool-cards/tempo-assistant.md) is the Indonesia archival-query example – an internal newsroom tool documenting how Tempo organised AI assistance around its own archival material. [MAFINDO Satgas Pemilu](../tool-cards/mafindo-satgas-pemilu.md) is the 2024 Election Task Force as a workflow design pattern – the coordinated-response architecture MAFINDO used during the Prabowo / Sri Mulyani deepfake wave in January and February 2025.

Both cards are short and frame themselves as design-pattern references, not deployable recommendations. The cell-level reality is that the broader landscape (La Silla Vacía, Civio, Impact Intelligence, Reporter Donor Framework, JournalismAI) is dominated by non-deployable Innovation Challenge prototypes outside SEA, and the toolkit does not pretend otherwise. Per Anchor 1, these tools sit at the editorial-orchestration layer adjacent to detection, not inside it. Users do not pass through 2A.4 in routine fact-check work; the bridge from the cell is to [2B.1](2b-collaborative.md#2b1-multilingual-tiplines), where MAFINDO's actual [Kalimasada](../tool-cards/mafindo-kalimasada.md) tipline lives, and to [2A.3](#2a3-prebunking-media-literacy), where Tempo's Detektif Deepfake prebunking work sits.

## Cross-references

- [T1 image triage](../decision-trees/t1-image-triage.md), [T2 video triage](../decision-trees/t2-video-triage.md) – operational entry for 2A.2 reverse-image work
- [T4 provenance triage](../decision-trees/t4-provenance-triage.md) – when 2A material carries provenance
- [T5 escalation](../decision-trees/t5-escalation.md) – tier-pivot routing
- [T7 tipline routing](../decision-trees/t7-tipline-routing.md) – when 2A output lands at a tipline
- [1A First-Line Triage](../pillar-1-detection/1a-first-line-triage.md), [1B Professional Verification](../pillar-1-detection/1b-professional-verification.md) – sideways moves when 2A surfaces a verification-side question
- [2B Collaborative Verification](2b-collaborative.md) – the forward route when 2A surfaces a tipline-grade claim
- Country pages: [Indonesia](../countries/indonesia.md) (Tempo Detektif Deepfake / Satgas Pemilu / Tempo Assistant; MAFINDO Bahasa pipeline), [Thailand](../countries/thailand.md) (AFP Chulalongkorn training)
- [Digital Safety — Source Protection](../digital-safety/source-protection-aggregation.md) – Auto Archiver source-protection context

## Sources

- Tempo. *Detektif Deepfake.* Tempo Media Group, 2025. [cekfakta.tempo.co](https://cekfakta.tempo.co/). (Tempo Detektif Deepfake WAN-IFRA Silver April 2026; MAFINDO Satgas Pemilu 2024 workflow anchor for 2A.3 / 2A.4.)
- VERA Files. *About VERA Files and #FactsFirstPH.* VERA Files, 2025. [verafiles.org](https://verafiles.org/). (VERA Files / Rappler 2A.2 reverse-image and claim-extraction use.)
- OpenAI. *Whisper Technical Documentation.* OpenAI, 2025. [openai.com/research/whisper](https://openai.com/research/whisper). (Whisper Sinhala / Lao low-resource performance; Lao ASR thinness at 2A.1.)
- [Architectural Anchors](../methodology/architectural-anchors.md) — Anchor 1 (workflow-not-detector framing) as operationalised across the 2A cells.
