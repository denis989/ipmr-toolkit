---
tool_id: TOOL-198
slug: auto-archiver
name: Auto Archiver (Bellingcat)
maintainer: Bellingcat (msramalho, pjrobertson, contributors)
type: non-detector
outline_cells:
 - {id: "2A.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: MIT
languages_ui: [en]
languages_content: [agnostic]
access: cli
cost: free
documented_country_use: []
tags: [archiving, evidence-preservation, wacz, bellingcat, python, docker, source-history]
---

# Auto Archiver (Bellingcat)

**Publisher:** [github.com/bellingcat/auto-archiver](https://github.com/bellingcat/auto-archiver) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    Bellingcat's open-source pipeline for automatically preserving
    social-media URLs as evidence. URLs go in (from a Google
    Sheet, a CSV, or the command line); archived files plus
    metadata hashes come out (to S3, Internet Archive, Google
    Drive, or local storage). The infrastructure layer underneath
    every piece of source-history work where evidence
    preservation matters.

## What it does

Auto Archiver is a Python pipeline that takes URLs from a source
(typically a Google Sheet, but also CSV files or direct command-
line input), archives the content of each URL, and writes the
archived artefact plus a metadata record to a configured
back-end (S3 bucket, Google Drive, Internet Archive, or local
storage). The tool handles social-media posts, videos, images,
and webpages, and produces both the archived file and a
verifiable hash record that supports chain-of-custody work.

A status report can be appended back to the original Google
Sheet, which makes the tool natural to deploy as the archiving
layer underneath a fact-check workflow that uses Sheets for
intake. The pipeline is published on PyPI and as a Docker image
with monthly maintenance; v1.2.6 shipped 7 April 2026, the
project carries 44 releases and active contributor activity.

For toolkit work, Auto Archiver is the rapid-archiving WACZ-
adjacent workflow that the gap analysis
identified as a high-priority gap. A Pillar 2 fact-check
operation that processes user-submitted links can run those
links through Auto Archiver on intake; by the time the editorial
team reaches a verdict, the source content has been preserved
in a form that survives platform takedown, account deletion,
and post-publication editing.

## When to use it

- A regional fact-check operation needs an automated archiving
 layer that runs on Google-Sheets intake and writes to S3 or
 Internet Archive without manual per-URL work.
- An institutional investigation is processing dozens or hundreds
 of social-media URLs and needs each one preserved as evidence
 before any analysis begins.
- A verification workflow is preparing for defamation defence or
 platform appeal and the source URLs must be archived with
 verifiable metadata hashes before any publication.
- A research project is collecting longitudinal evidence (an
 ongoing CIB campaign, a recurring deepfake actor, an election-
 period narrative cluster) and needs continuous archiving over
 weeks or months.

## Limitations

!!! info "Limitations"
    - Requires a Google Cloud Service Account plus JSON
    credentials for the Sheets-driven workflow.
    Setup carries an institutional-IT cost that frontline
    fact-checkers without admin access cannot complete on
    their own.
    - Frequent platform-blocking adaptation needed. The pipeline relies on platform APIs and
    scrapers; when Twitter/X changes its rate limits or
    Facebook tightens scraping protections, the maintainer
    ships a fix, but a self-hosted deployment can lag the
    upstream by weeks if the operator does not redeploy
    promptly.
    - Docker or Python install path; the tool is not a
    one-click product. Operators need command-line comfort
    and a server or workstation to run the pipeline.
    - The archived artefact's evidentiary status depends on the
    back-end's chain-of-custody discipline. Uploading to a
    public S3 bucket without access controls is a different
    evidentiary posture from uploading to a controlled S3
    bucket with documented access logs; the tool ships the
    artefact, the operator owns the chain.

## Privacy and threat model

Auto Archiver is self-hosted. The pipeline runs where the
operator deploys it; the source URLs and archived artefacts pass
through whatever infrastructure the operator chooses. This is
the strongest privacy posture in the 2A.2 cell because the
operator controls the data flow end to end; Bellingcat operates
the upstream code repository but does not host any archive on
behalf of users.

The privacy considerations move to the chosen back-end. An
S3 bucket on AWS sits under US/Amazon jurisdiction; an Internet
Archive submission is public and persistent; Google Drive is
under Google jurisdiction with the operator's account
permissions; local storage stays on the operator's machine. For
Sri Lanka and Laos surveillance-environment work, the operator
chooses the back-end to match the threat model: local or
trusted-jurisdiction storage for source-identifying material,
public Internet Archive for material where preservation is the
goal regardless of who reads it.

!!! danger "Source-protection override (S3 — graphic, sexual, child-safety, or abuse material)"
    Auto Archiver pipelines that ingest conflict footage,
    alleged abuse imagery, or non-consensual intimate content
    place archived copies on whichever back-end is configured —
    and any future reviewer of the archive is exposed to the
    same material. Mitigation steps:

    1. Before archiving any conflict, violence, or abuse content,
    follow newsroom protocol on whether the material may be
    preserved at all; some categories (child sexual abuse
    material) carry legal obligations that override editorial
    preservation interest.
    2. Minimise reviewer exposure: rotate analysts, document
    sensitivity classifications in archive metadata, and
    route the archive away from team-wide shared storage by
    default.
    3. Where preservation is required for legal or evidentiary
    purposes, prefer back-ends with documented access controls
    (encrypted local storage, restricted S3 bucket) over
    public Internet Archive submission.
    4. Apply the staff-safety protocol on repeated viewing for
    any analyst working through a sensitive archive batch.

## Country and platform applicability

- **Indonesia:** language-agnostic; usable as the archiving
 layer underneath the MAFINDO/CekFakta workflow at Kalimasada. No documented Indonesian-specific deployment in
 the inventory but the tool is operationally portable.
- **Laos:** language-agnostic; for regional partners
 archiving Lao-content links, the self-hosted deployment is
 the right architectural fit because the operator controls
 whether any data crosses Lao state-aligned infrastructure.
- **Malaysia:** language-agnostic; useful for Sebenarnya.my
 and partner deployments that need automated archiving of
 user-submitted links.
- **Philippines:** language-agnostic; pairs with
 #FactsFirstPH coalition workflow for evidence preservation
 across coalition members.
- **Sri Lanka:** language-agnostic; useful for
 Watchdog and Hashtag Generation election-period archiving.
 Self-host on local infrastructure for surveillance-aware
 posture.
- **Thailand:** language-agnostic; pairs with Thai PBS,
 SONP, and Cofact archiving needs.

Platform applicability: Facebook, Facebook Groups, TikTok, YouTube, Telegram,
X. Twitter/X support requires the v1.2.3+ drop-in alternative;
LINE-shared content is platform-restricted and not directly
archivable through Auto Archiver.

## How to access

Open-source under MIT licence at github.com/bellingcat/auto-
archiver. Install via Docker (`docker pull
bellingcat/auto-archiver`) or pip (`pip install auto-archiver`).
Documentation lives at auto-archiver.bellingcat.com. The
Bellingcat introductory article on the tool is published at
bellingcat.com. Latest release v1.2.6 (7 April 2026) per the
project's GitHub releases page; the maintainer ships roughly
monthly with bugfix and platform-adaptation releases.

## Cost (current as of 2026-05)

Free under MIT licence. The structural cost is operational —
infrastructure to run the pipeline (a Docker host or Python
environment), the back-end storage (S3, Google Drive, Internet
Archive submission, or local), the institutional setup of a
Google Cloud Service Account if Sheets-driven intake is used,
and the operator time to redeploy when upstream releases ship
platform-adaptation fixes.

## Quickstart

1. Decide the deployment posture: Docker (`docker pull
 bellingcat/auto-archiver`) for production, pip install for
 local development, manual command-line runs for ad-hoc work.
2. For Sheets-driven intake, create a Google Cloud Service
 Account and download the JSON credentials; share the target
 Google Sheet with the service account's email.
3. Configure the orchestration YAML (back-end storage, Sheet
 ID, archiving rules) per the Bellingcat documentation.
4. Run the pipeline: `docker run -it --rm -v secrets:/app/secrets
 bellingcat/auto-archiver --config secrets/orchestration.yaml`.
5. Confirm archived artefacts and metadata hashes appear in the
 chosen back-end.
6. Schedule the pipeline (cron, systemd, or a CI scheduler) for
 continuous archiving on intake.
7. Watch the Bellingcat releases page; redeploy when a release
 ships platform-adaptation fixes (Twitter/X, Facebook, TikTok
 adaptation has been the recurring maintenance pattern).

## In the toolkit's workflow

Source-history pillar non-detector infrastructure layer per
Architectural Anchor 1. Sits in 2A.2 nominally as an "enhanced
reverse-image / geolocation" cell entry but functionally as the
evidentiary preservation layer that runs underneath the cell's
visual-verification work. The cell groups Auto Archiver here
because every reverse-image hit, every GeoSpy hypothesis, every
YouTube Data Viewer extraction is more defensible when the
source URL has been preserved before analysis began. Cross-cell
awareness with the [Digital Safety](../digital-safety/source-protection-aggregation.md) section – Auto
Archiver's archiving-as-evidence pattern is foundational there.

Standard combinations:

- With **InVID-WeVerify** at 2A.2 / 1B.1 – InVID's
 WACZ module captures a single URL on demand; Auto Archiver
 preserves bulk URLs from Sheets as a continuous workflow.
- With **GeoSpy** at 2A.2 – Auto Archiver preserves
 the source URL before GeoSpy's geolocation hypothesis is
 generated, so the eventual fact-check has the original
 context in evidence.
- With **Citizen Evidence Lab YouTube Data Viewer** at
 2A.2 when YouTube content needs both upload-time verification
 and bulk archiving for a longitudinal record.
- With **Meedan Check** at 2B.1 when tipline intake
 generates a continuous stream of URLs that need preservation
 before the editorial workflow processes them.
- With **CIB Mango Tree** at 1C.1 when behaviour-
 pillar analysis needs preserved historical artefacts to
 support the network finding.

Decision-tree references: [T2 Video triage](../decision-trees/t2-video-triage.md) and [T6 Source-protection](../decision-trees/t6-source-protection.md) both route through Auto Archiver as the
preservation step before any analysis. The [Digital Safety](../digital-safety/source-protection-aggregation.md) section references
Auto Archiver as the evidentiary baseline alongside Browsertrix (the WACZ-native alternative kept at the Digital
Safety reference layer rather than promoted into 2A.2; see
[change-log](../methodology/change-log.md)).

This card carries no detector signal class: Auto Archiver
preserves source content as evidence; it does not produce a
content-classification verdict. Per Anchor 1 the preserved
artefact is the substrate for downstream source-history
analysis; per Anchor 2 archiving by itself is not a publishable
claim, but its absence weakens any claim that depends on
content the platform later removed.

## Override notes

!!! note "Override notes"
    - **Rapid archiving WACZ workflow (rapid-archiving-WACZ-
    workflow-G-030-pointer):** the tool implements the
    rapid-archiving WACZ-adjacent workflow named in the
    gap analysis as G-030. Operators preserve
    source content as evidence on intake; the toolkit treats
    archive-on-intake as the recommended pattern for any
    Pillar 2 operation that may need defamation defence,
    platform appeal, or longitudinal-cluster analysis.

## Sources

- External: [bellingcat/auto-archiver releases](https://github.com/bellingcat/auto-archiver/releases)
 (v1.2.6 released 7 April 2026; active
 monthly maintenance pattern)
- External: [bellingcat/auto-archiver repository](https://github.com/bellingcat/auto-archiver)
 (MIT licence, 1062 stars, 44 releases,
 20 contributors)
