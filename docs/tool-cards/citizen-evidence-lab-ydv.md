---
tool_id: TOOL-069
slug: citizen-evidence-lab-ydv
name: Citizen Evidence Lab YouTube Data Viewer
maintainer: Amnesty International (Citizen Evidence Lab)
type: non-detector
outline_cells:
 - {id: "2A.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: free
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: free
documented_country_use: []
tags: [youtube, reverse-image, source-history, amnesty, citizen-evidence-lab, archiving]
---

# Citizen Evidence Lab YouTube Data Viewer

**Publisher:** [citizenevidence.org](https://citizenevidence.org) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free web tool from Amnesty International's Citizen Evidence
    Lab. Paste a YouTube URL and the tool returns the exact
    upload time and every video thumbnail: the two anchors that
    let a fact-checker establish how old a clip really is and
    cross-check whether earlier copies of it exist elsewhere.
    Narrow scope, high reliability, no upload of source files.

## What it does

The YouTube Data Viewer takes a YouTube video URL and returns
two outputs: the precise upload timestamp (down to the second,
not just the date YouTube displays publicly) and the full set
of video thumbnails YouTube generates for the clip. The
thumbnails matter operationally because they can be reverse-
image-searched to locate earlier instances of the video; a
clip claimed as freshly recorded that surfaces a 2019 thumbnail
match has been re-uploaded, not filmed.

The tool runs entirely against YouTube's metadata; nothing about
the source video is uploaded to Amnesty servers. The user
provides a URL, the tool queries YouTube, the user receives the
metadata. Operational simplicity is the point: the tool does
one thing, does it reliably, and pairs cleanly with reverse-
image search elsewhere in the workflow.

## When to use it

- A YouTube clip is being claimed as fresh footage from a
 current event, and the fact-checker needs to verify the
 upload timestamp against the claimed event time.
- A video has been re-uploaded under a misleading title or
 caption, and the thumbnail set needs reverse-image-searching
 to locate the original posting.
- An archival pipeline (Auto Archiver, InVID-WeVerify's WACZ module) needs the precise upload
 timestamp recorded as evidence metadata before the source
 URL is preserved.
- A workshop is teaching the Pillar 2 source-history pillar in
 practice and needs a tool that demonstrates metadata-driven
 verification without requiring file uploads or paid access.

## Limitations

!!! info "Limitations"
    - YouTube-only. The tool does not work on
    Facebook video, TikTok, Twitter/X video, Telegram-hosted
    video, LINE-shared content, or any other platform; for
    non-YouTube video the user must reach for InVID-WeVerify's keyframe extraction or the platform's
    own metadata if available.
    - Dependent on YouTube's metadata API behaviour. If YouTube
    changes how upload timestamps are exposed or restricts
    thumbnail access, the tool's output changes accordingly.
    - Returns metadata, not verification; the upload time and
    thumbnails are inputs to a manual chain (reverse-image
    search, cross-platform comparison, claim-database
    lookup), not a finished verdict.
    - English-language interface only; the tool itself is
    language-agnostic on input because YouTube URLs are not
    language-bound.

## Privacy and threat model

The tool's privacy posture is unusually clean: no source file is
uploaded, only a YouTube URL is submitted. The query goes to
YouTube via Amnesty's web tool; no analysis of the video itself
takes place on Citizen Evidence Lab servers. For surveillance-
environment work this is the operationally safe path; using the
YouTube Data Viewer does not expose the source video to a
third-party analysis pipeline because no such analysis happens.

The downstream reverse-image-search step that uses the returned
thumbnails does involve querying third-party search engines
(Google, Bing, Yandex, Baidu, TinEye), which carries the usual
search-engine query-logging considerations. The thumbnails
themselves are public YouTube assets so the privacy delta is
minimal compared to a normal browser session.

## Country and platform applicability

- **Indonesia:** language-agnostic; useful for verifying
 YouTube re-uploads of political clips during election
 cycles. Pairs with the MAFINDO/CekFakta workflow at Kalimasada.
- **Laos:** language-agnostic; YouTube content from or
 about Laos is a marginal use case (YouTube reach in Laos is
 limited compared to Facebook), but the tool works on any
 YouTube URL regardless of upload origin.
- **Malaysia:** language-agnostic; useful for
 Sebenarnya.my and Bernama MyCheck verification of Malaysia-
 facing YouTube content.
- **Philippines:** language-agnostic; documented heavy
 use across YouTube-uploaded political clips in the
 #FactsFirstPH workflow context, particularly for re-upload
 detection.
- **Sri Lanka:** language-agnostic; useful for
 Watchdog and Hashtag Generation verification of YouTube clips
 during election cycles.
- **Thailand:** language-agnostic; pairs with Thai PBS
 and SONP verification work on YouTube-uploaded political
 content. LINE is the dominant Thai messaging platform but
 YouTube is still the primary long-form video host.

Platform applicability: YouTube only. The tool's narrow scope
is its design.

## How to access

Free web tool at citizenevidence.amnestyusa.org or the Citizen
Evidence Lab project page. No account creation, no install, no
paid tier. The tool has been online and stable since the early
2010s as part of the Citizen Evidence Lab's broader
verification-resources hub.

## Cost (current as of 2026-05)

Free. No paid tier exists; the tool is part of Amnesty
International's public-good verification infrastructure.

## Quickstart

1. Copy the YouTube URL of the video you want to verify.
2. Paste it into the YouTube Data Viewer at
 citizenevidence.amnestyusa.org.
3. Read the returned upload timestamp: the precise time the
 video was uploaded to YouTube, not the rounded date YouTube
 displays publicly.
4. Compare the timestamp against the claimed event time; an
 upload that predates the claimed event is one strong
 non-detector signal that the clip is misattributed.
5. Take each returned thumbnail and reverse-image-search it
 (InVID-WeVerify's reverse-image module is the
 standard pairing) to locate earlier instances of the video.
6. Document upload time and reverse-image-search hits as
 evidence in the fact-check workflow.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural
Anchor 1. Sits in 2A.2 as the YouTube-specific source-history
alternative alongside the cross-cell primary InVID-WeVerify (broader reverse-image and keyframe pipeline),
the AI-geolocation alternative GeoSpy, and the
archiving infrastructure Auto Archiver.

Standard combinations:

- With **InVID-WeVerify** at 2A.2 / 1B.1 – Citizen
 Evidence Lab YDV returns the upload timestamp and thumbnails;
 InVID's reverse-image module then searches the thumbnails
 across multiple engines in one step.
- With **Auto Archiver** at 2A.2 to preserve the
 source URL plus the verified upload timestamp as a single
 evidence record before the YouTube clip can be removed or
 edited.
- With **GeoSpy** at 2A.2 when a thumbnail or extracted
 frame from the YouTube clip needs a geographic-hypothesis
 starting point.
- With **Meedan Check** at 2B.1 when the verified
 YouTube clip enters a tipline workflow and the upload
 timestamp is part of the fact-check response back to the
 community.

Decision-tree references: [T2 video triage](../decision-trees/t2-video-triage.md)
routes YouTube-sourced video through Citizen Evidence Lab YDV at
T2.2 (platform preservation) and T2.4 (keyframe extraction).
[T1 image triage](../decision-trees/t1-image-triage.md) routes any
extracted thumbnail through reverse-image search via the standard
InVID pairing.

This card carries no detector signal class: the tool produces
metadata (upload time, thumbnails), not a synthetic-content
verdict. Per Anchor 1 the metadata feeds the source-history
pillar; per Anchor 2 an upload-time mismatch by itself is one
non-detector signal that combines with reverse-image hits and
archived-version checks to support a publishable claim.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** the tool
    returns YouTube metadata, not a content-classification
    verdict. It serves the source-history pillar; the
    analytical work (cross-checking timestamps and
    reverse-image-searching thumbnails) is the user's, not
    the tool's.

## Sources

- Amnesty International. *YouTube Data Viewer*. Citizen Evidence Lab, Amnesty International. [Amnesty Tech — Citizen Evidence Lab](https://www.amnesty.org/en/tech/).
