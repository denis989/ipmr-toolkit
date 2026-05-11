---
title: "Decision trees"
summary: "Seven workflow trees a fact-checker runs against viral content. Each tree is a Mermaid flowchart, a node-by-node reference, and a regional / platform routing block."
---

# Decision trees

The decision trees sit between the pillar narratives, which explain why a workflow is shaped the way it is, and the tool cards, which describe the individual instruments. A tree shows what a fact-checker actually does when content lands in their queue: which checks run first, which tools cover which step, when to escalate, and where the workflow stops.

These pages are built to work on paper as well as on the web. In a browser the Mermaid flowchart renders to an SVG; on a printout the node-detail tables and prose reference carry the same logic alongside the diagram. Read the tree from its first node unless the case throws a callout to another tree or to the source-protection layer ([T6](t6-source-protection.md)).

## The seven trees

[**T1 – Image triage.**](t1-image-triage.md) Sixteen-node first-line workflow for viral images, screenshots, and stills. Original-file preservation, provenance, reverse search, existing debunks, visible anomalies, and detector triangulation – in that order. The reference shape for the rest of the modality trees.

[**T2 – Video triage.**](t2-video-triage.md) Seventeen-node workflow for short-form video. Separates URL preservation and keyframe-driven reverse search from synthetic-video detection; calls [T3](t3-audio-triage.md) for audio-central videos.

[**T3 – Audio triage.**](t3-audio-triage.md) Sixteen-node workflow for voice notes, alleged leaked calls, robocalls, and dubbed clips. Treats audio detectors as the most fragile signal class because of cross-language and cross-codec failure modes; transcription and human listening come first.

[**T4 – Provenance triage.**](t4-provenance-triage.md) Twelve-node workflow for any modality where an original file carries C2PA / Content Credentials, a vendor watermark such as [SynthID](../tool-cards/synthid-detector.md), or a creator-attestation manifest. Provenance is the toolkit's most reliable signal class; T4 is the reading layer.

[**T5 – Escalation.**](t5-escalation.md) Eighteen-node workflow for cases that [first-line triage](../pillar-1-detection/1a-first-line-triage.md) cannot close, plus the explicit "tools disagree" entry that resets to Architectural Anchor 2 and 3. Routes by content type into [professional verification](../pillar-1-detection/1b-professional-verification.md), contextual OSINT, subject contact, and external expert escalation.

[**T6 – Source-protection.**](t6-source-protection.md) Routing layer for the ten safety-override classes (S1 to S10). Read T6 alongside the calling tree, not after. The canonical reference for the toolkit's source-protection discipline.

[**T7 – Tipline routing.**](t7-tipline-routing.md) Platform-by-country routing tree for tipline-bound responses. Maps the five priority platforms to the available tipline tool in each of the six focus countries; names the country–platform combinations where no tipline exists.

## How the trees connect

[T1](t1-image-triage.md), T2, T3 are the first-line modality trees, one for image, video, and audio. T4 fires from any modality when an original file carries provenance metadata. T5 is the escalation gate when first-line triage cannot close the case, or when detectors disagree. T6 sits in parallel to all six others as the source-protection layer. T7 takes verified cases through to a tipline-bound response.

Two [architectural anchors](../methodology/architectural-anchors.md) run through every tree, and they operate as gates, not as suggestions. At least two non-detector signal classes are required before any strong public claim, and multi-detector consensus is treated as one signal class.

## Reading the diagrams

- Diamond nodes are decisions. Rectangles are actions or conclusions. Stadium shapes (`(...)`) are hand-offs to other trees or to the safety-override layer.
- Edge labels are short on purpose – four words or fewer. The full condition lives in the node-detail table beneath the diagram.
- Tool names in the node-detail tables link to the relevant tool card. A node that names [InVID-WeVerify](../tool-cards/invid-weverify.md) routes to the InVID card; a node that calls T5.1 routes to the T5 page.
- Time bands per Foundational Decision 1: First-Line Triage in five to thirty minutes; Professional Verification in roughly thirty minutes; Institutional Analysis in two hours or more.

The trees are operational artefacts. If a step in a tree does not match newsroom reality on a specific case, log it – the trees are versioned and revised against documented practice, not against ideal-case design.
