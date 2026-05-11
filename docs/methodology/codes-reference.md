---
title: "Codes and terms reference"
summary: "Canonical reference for the S-class source-protection codes, T-tree decision trees, Architectural Anchors, Foundational Decisions, and framework acronyms used throughout the toolkit."
---

# Codes and terms reference

The toolkit threads a compact taxonomy through almost every page – S-class source-protection codes, T-tree decision trees, three Architectural Anchors, eight Foundational Decisions, and a handful of framework acronyms. This page is the single place a reader can land to recover what any of those names refer to and where to read on. Two reading modes use this material. In the browser, hovering any acronym surfaces an inline tooltip drawn from `docs/includes/abbreviations.md`; that mode answers the quick "what does S2 mean" question without leaving the page in hand. For PDF readers and for the cases where a hover gloss is insufficient, this page is the long form – each entry carries a one-paragraph definition and a link to the canonical operational source.

## Architectural Anchors

The three anchors run beneath every tool card and every decision tree as embedded operational logic. Full treatment sits at [architectural-anchors.md](architectural-anchors.md); a reader who applies the anchors on a working case walks each in the order below.

### Anchor 1 – The toolkit is not a directory of detectors

Detection is one signal class among four. Provenance, source-history, behaviour, and cautious-detector together form the workflow the toolkit teaches, with the detector pillar positioned as the last resort and not the first move. The anchor surfaces sharpest at 1A.4 (provenance and watermark verification), at 1B.4 (metadata and ELA forensics), and at 2C.1 (automated claim monitoring) – three cells where non-detector tools carry the load that a less disciplined toolkit would route to detectors.

### Anchor 2 – Two non-detector signals required for any strong public claim

Editorial policy, not advisory. Every decision tree's terminal "publish" node enforces a two-non-detector-signals floor before any strong synthetic label leaves the newsroom. The rule is grounded in the field evidence on detector reliability – independent detector benchmarking evidence shows detector class ceilings well below what defamation-grade evidence requires. The anchor surfaces sharpest at 1B.2 (AI text detection, contracted to two cards) and at the S6 detector-only-accusation gate in [T6](../decision-trees/t6-source-protection.md).

### Anchor 3 – Detector plus detector is one signal class

Running an image through three detectors and getting three "AI" verdicts produces one signal class with three rendering surfaces, not three independent signals. The shared training-data overlap, similar architectures, and convergent failure modes across detector products make multi-detector consensus a confidence illusion, not additive evidence. The anchor's operational form is the per-card G3 declaration plus the Anchor-3-reset branch in [T5](../decision-trees/t5-escalation.md); together they make the rule enforceable at the card layer and at the workflow layer.

## Source-protection classes (S1 – S10)

The ten S-classes name editorial overrides that fire when a default workflow step would expose a source, breach legal context, or harm staff. Each class carries a triggering condition and a required action. Canonical routing across all ten lives in the [T6 source-protection tree](../decision-trees/t6-source-protection.md); the tool cards that render an S-class as `!!! danger` admonitions trace their wording back to T6.

### S1 – Source-identifying upload risk

Fires when content contains faces, voices, GPS, metadata, private handles, victim identity, or original files from a vulnerable source. The required action is to stop the tool upload, preserve the original securely, and switch to local or on-device tools – or to expert escalation with minimisation and consent. Currently rendered on thirteen tool cards across hosted detector and translation products. See [T6 S1](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk).

### S2 – State-linked or legally sensitive investigation

Fires when content concerns police, military, monarchy, ruling party, cybercrime or fake-news laws, protest movements, red-tagging, or national security. The required action routes through the digital safety, legal, or editor approval gate before any outreach, publication, platform reporting, or contact with state-linked actors. Country-specific anchors include Thailand Article 112 lèse-majesté, Sri Lanka OSA, Indonesia EIT Law, Malaysia CMA Section 233, and Laos Decree 327. See [T6 S2](../decision-trees/t6-source-protection.md#s2-state-linked-or-legally-sensitive-investigation).

### S3 – Graphic, sexual, child-safety, or abuse material

Fires when content includes sexual imagery, minors, abuse, corpses, graphic violence, torture, or non-consensual intimate imagery. The required action stops the upload to general tools and routes the case through newsroom, legal, or platform protocols, minimising viewing and protecting staff well-being. Rendered as `!!! danger` on the [Auto Archiver](../tool-cards/auto-archiver.md) card and referenced in prose across 1B and 1C image-and-video detector cards. See [T6 S3](../decision-trees/t6-source-protection.md#s3-graphic-sexual-child-safety-or-abuse-material).

### S4 – Doxxing, harassment, or vulnerable-community targeting

Fires when content identifies activists, journalists, ethnic or religious minorities, LGBTQ+ people, migrants, witnesses, or alleged criminals. The required action redacts identifiers, avoids repeating slurs or addresses, assesses retaliation risk, and considers a quiet tipline-only response in place of a public debunk. Rendered on [Information Tracer](../tool-cards/information-tracer.md), [Maltego](../tool-cards/maltego.md), [Sinar Project iMAP](../tool-cards/sinar-project-imap.md), and [CIB Mango Tree](../tool-cards/cib-mango-tree.md). See [T6 S4](../decision-trees/t6-source-protection.md#s4-doxxing-harassment-or-vulnerable-community-targeting).

### S5 – Private or encrypted group collection

Fires when evidence comes from WhatsApp, LINE, private Telegram, closed Facebook Groups, or private Messenger or Viber chats. The required action is to use consented submissions and tiplines only; scraping, infiltrating, or exposing group members without explicit organisational protocol is forbidden. Rendered on tipline cards including [Meedan Check](../tool-cards/meedan-check.md), [Cofact Thailand](../tool-cards/cofact-thailand.md), [MAFINDO Kalimasada](../tool-cards/mafindo-kalimasada.md), and [Sebenarnya AIFA](../tool-cards/sebenarnya-aifa.md). See [T6 S5](../decision-trees/t6-source-protection.md#s5-private-or-encrypted-group-collection).

### S6 – Detector-only accusation

Fires when the only evidence for "AI-generated," "deepfake," "voice clone," "bot," or "coordinated inauthentic behaviour" is one or more automated tool scores. The required action is to stop, reframe as "tool flagged for review," seek independent evidence, or escalate to T5 / coordinated analysis. S6 is the operational expression of Architectural Anchor 2 and Anchor 3; it binds every detector card identically, which is why it lives in T6 as a global gate instead of rendering sixty-five times. See [T6 S6](../decision-trees/t6-source-protection.md#s6-detector-only-accusation).

### S7 – Malware, APK, phishing, payment, or ID-harvesting risk

Fires when content directs users to APKs, payment, "registration," WhatsApp or Telegram forms, aid claims, investment platforms, or credential collection. The required action holds back any click or install on a work or personal device, preserves the link safely, and escalates as scam or impersonation through [T7](../decision-trees/t7-tipline-routing.md) and through technical and security support. Region context covers Indonesian and Malaysian deepfake-aid scams, Thai voice-scam routing, and Philippine impersonation funnels. See [T6 S7](../decision-trees/t6-source-protection.md#s7-malware-apk-phishing-payment-or-id-harvesting-risk).

### S8 – Liar's-dividend risk

Fires when a powerful actor claims real evidence is AI-generated, or when the newsroom is tempted to label something fake without independent proof. The required action verifies source, context, and provenance; the safe formulation is "we cannot verify AI manipulation," not "fake." S8 is the editorial twin of S6 – where S6 prevents over-claiming AI from a detector signal, S8 prevents the political abuse of "could be AI" as a way to dismiss real abuse, corruption, violence, or testimony. See [T6 S8](../decision-trees/t6-source-protection.md#s8-liars-dividend-risk).

### S9 – Cross-border data transfer or vendor retention risk

Fires when hosted tools require upload of sensitive content to proprietary APIs or foreign servers. The required action checks the organisational data policy, vendor retention terms, and source consent before any upload, with a preference for local or on-device tools or trusted expert channels. The [InVID-WeVerify](../tool-cards/invid-weverify.md) thirty-day CERTH window is the reference case for documented vendor retention. Rendered on seven hosted detector cards. See [T6 S9](../decision-trees/t6-source-protection.md#s9-cross-border-data-transfer-or-vendor-retention-risk).

### S10 – Staff safety and trauma risk

Fires when repeated viewing or listening, harassment backlash, threats, graphic content, or coordinated abuse after publication threaten the well-being of newsroom staff. The required action limits exposure, rotates reviewers, documents threats, secures accounts and devices, and activates the newsroom safety protocol. S10 is a workflow-level override; it lives in the [Digital Safety](../digital-safety/index.md) section and not on individual tool cards. See [T6 S10](../decision-trees/t6-source-protection.md#s10-staff-safety-and-trauma-risk).

## Decision trees (T1 – T7)

The seven trees are operational workflows for routing cases by modality plus escalation need. Each tree carries a Mermaid flowchart, a node-detail table, and a prose layer. Full index in [decision-trees/index.md](../decision-trees/index.md).

### T1 – Image triage

Sixteen-node first-line workflow for viral images, screenshots, and stills lifted from short video. Leads with file preservation, provenance, reverse search, and existing debunks; the detector pass arrives only after non-detector signals are exhausted. See [T1](../decision-trees/t1-image-triage.md).

### T2 – Video triage

Seventeen-node first-line workflow for short-form video. Separates URL preservation and keyframe-driven reverse search from synthetic-video detection; routes audio-central videos out to [T3](../decision-trees/t3-audio-triage.md) and rejoins for the final verdict. See [T2](../decision-trees/t2-video-triage.md).

### T3 – Audio triage

Sixteen-node first-line workflow for voice notes, alleged leaked calls, robocalls, dubbed clips, and any video where the voice is the central claim. Treats audio detectors as the most fragile signal class because of cross-language and cross-codec failure modes; transcription and human listening come first. See [T3](../decision-trees/t3-audio-triage.md).

### T4 – Provenance triage

Twelve-node workflow for any modality where an original file carries C2PA / Content Credentials, a vendor watermark such as [SynthID](../tool-cards/synthid-detector.md), or a creator-attestation manifest. Reads what the manifest claims, tests the chain, and returns a non-detector signal class that feeds back into [T1](../decision-trees/t1-image-triage.md), [T2](../decision-trees/t2-video-triage.md), or T3. See [T4](../decision-trees/t4-provenance-triage.md).

### T5 – Escalation

Eighteen-node workflow for cases [first-line triage](../pillar-1-detection/1a-first-line-triage.md) cannot close, plus the explicit "tools disagree" entry that resets to Architectural Anchors 2 and 3. Routes by content type into [professional verification](../pillar-1-detection/1b-professional-verification.md), contextual OSINT, subject contact, and external expert escalation. See [T5](../decision-trees/t5-escalation.md).

### T6 – Source-protection

Routing layer for the ten safety-override classes S1 – S10. Read T6 alongside the calling tree, not after; an S-class often fires on the same case in parallel with the modality tree. The canonical reference for the toolkit's source-protection discipline. See [T6](../decision-trees/t6-source-protection.md).

### T7 – Tipline routing

Platform-by-country routing tree for tipline-bound responses. Maps the five priority platforms to the available 2B.1 tipline tool in each of the six focus countries; names the country-platform combinations where no tipline exists. See [T7](../decision-trees/t7-tipline-routing.md).

## Pillars and tiers

The toolkit's primary content organisation. Two pillars, three tiers per pillar. Tier labels are technique-level, not user-level – a single reader moves across tiers depending on the case in hand. Further context in [change-log.md](change-log.md).

### Pillar 1 – Detection and triage

Pillar 1 covers detecting and triaging AI-powered content. Tactical in character: detectors framed as ad-hoc tools, not solutions. Cells run from 1A.1 through 1C.3, covering image, video, audio, and provenance modalities across three tiers. Entry page at [pillar-1-detection/index.md](../pillar-1-detection/index.md).

### Pillar 2 – Counter-disinformation work

Pillar 2 covers using AI to counter disinformation. Strategic in character: provenance verification, tipline networks, and manual verification carry the durable load. Cells run from 2A.1 through 2C.3, covering [AI-assisted workflows](../pillar-2-counter/2a-workflows.md), [collaborative verification](../pillar-2-counter/2b-collaborative.md), and [large-scale intelligence](../pillar-2-counter/2c-intelligence.md). Entry page at [pillar-2-counter/index.md](../pillar-2-counter/index.md).

### First-Line Triage (1A / 2A)

Five-minute time band per Foundational Decision 1. The tier a fact-checker reaches for on a phone in the field. Tools are scannable, mobile-aware, and built for first-pass disqualification, not for depth.

### Professional Verification (1B / 2B)

Thirty-minute time band. Desk-based work with browser tools and modest infrastructure. The tier where most fact-check publishing decisions land; non-detector signal classes converge here for the two-non-detector-signals floor Anchor 2 requires.

### Institutional-Level Analysis (1C / 2C)

Two hours minimum, often half a day. Coordinated-operation analysis, ABCDE / DISARM codification, and the access-barrier-gated tools at enterprise pricing or IFCN-signatory gating. Most frontline readers reach this tier through partner-mediated paths, not direct deployment.

## Foundational Decisions

Eight structural decisions that govern toolkit shape. Full documentation in [change-log.md](change-log.md).

### Decision 1 – Canonical five / thirty / one-hundred-twenty-minute time-band ladder

First-Line Triage runs in five minutes on a phone. Professional Verification in thirty minutes at desk with browser tools. [Institutional-Level Analysis](../pillar-1-detection/1c-institutional-analysis.md) in two hours minimum, often half a day. Decision-tree node times remain free-form; tree headers cite this ladder.

### Decision 2 – ABCDE / DISARM split

ABCDE is the surface vocabulary for public-facing analysis. DISARM is the institutional annex for inter-organisation reporting and researcher use. Both go in the toolkit, in clearly distinct contexts. The split surfaces in 2C cell tool cards.

### Decision 3 – Inter-tool conflict resolution

Conflict resolution lives in two places: a per-card Conflict-resolution-behaviour field stating evidence weight, and a dedicated T5 node handling "two tools disagree." Not a separate outline subcategory.

### Decision 4 – Regional suffix scheme

Country and platform suffixes adopted as canonical. Countries: `-id`, `-ms`, `-thai`, `-ph`, `-si-ta`, `-lao`. Platforms: `-wa`, `-line`, `-tiktok`, `-fb`, `-fbg`, `-telegram`, `-youtube`, `-x`. Used in decision-tree node IDs, tool-card cross-link anchors, and regional case studies.

### Decision 5 – Gap catalogue as single source

A consolidated gap catalogue serves as the single source for all gap-driven outline additions and drafting priorities, superseding earlier separate gap lists.

### Decision 6 – Detector skepticism

Hard-coded at three levels: architectural (Anchor 1), editorial policy (Anchor 2), and operational safety override (the S-class system that fires regardless of branch logic). Soft positioning rejected: a fact-checker on deadline will use a detector verdict if not told plainly it is insufficient.

### Decision 7 – SEA language coverage applies conditionally

Local-language coverage is not a blanket requirement. UI accessibility is English-sufficient for trained fact-checkers, with [Sebenarnya AIFA](../tool-cards/sebenarnya-aifa.md) as the named lay-public exception. Content-language coverage applies only to NLP-class tools that process natural language. Image, video, provenance, network, and metadata tools are language-agnostic. The honest-gap policy applies to content the reader needs to verify, not to tools' UI.

### Decision 8 – Comprehensive density target

Two to three tools per outline subcategory by default, three to four where the landscape is rich, one to two where the landscape is thin. Resulting target range of sixty-five to eighty-five tools across the twenty-two cells – the shortlist landed at sixty-five. Supersedes any earlier "12-15 tools total" figure.

## Framework acronyms

The toolkit treats these as named external references – frameworks the reader is expected to recognise or reach for, not tools the toolkit deploys directly. Most carry a dedicated tool card; the brief gloss below points the reader to the operational surface.

### ABCDE

Actor, Behaviour, Content, Distribution, Effect. The public-facing surface vocabulary for attribution analysis. Used in fact-check articles and editorial layouts where a clear five-element breakdown of an operation reaches a general audience. See [ABCDE Framework card](../tool-cards/abcde-framework.md) and the 2C narrative at [pillar-2-counter/2c-intelligence.md](../pillar-2-counter/2c-intelligence.md).

### DISARM

Disinformation Analysis and Risk Management framework. The institutional taxonomy for inter-organisation reporting and researcher use. Where ABCDE simplifies for a reader, DISARM specifies for a CSIRT, a coalition, or a researcher. See [DISARM Framework card](../tool-cards/disarm-framework.md) and the [Navigator card](../tool-cards/disarm-navigator-stix2.md).

### C2PA / Content Credentials

Coalition for Content Provenance and Authenticity. A cross-industry standard for cryptographically signed manifests that travel with media files, recording creator identity, edit history, and AI-use disclosure. The toolkit's most reliable signal class when present, though SEA-distributed files usually arrive with the manifest stripped by platform re-encoding. See the [Content Credentials Verify card](../tool-cards/content-credentials-verify.md) and [T4](../decision-trees/t4-provenance-triage.md).

### CIB

Coordinated Inauthentic Behaviour. The Meta-originated category for accounts and pages working together to mislead the platform and its users. Surfaces at 1C.1 in the institutional-tier cells; mapped to behavioural-pillar tools including [CIB Mango Tree](../tool-cards/cib-mango-tree.md), [CooRTweet](../tool-cards/coortweet.md), and [Coordination Network Toolkit](../tool-cards/coordination-network-toolkit.md).

### IFCN

International Fact-Checking Network. The signatory status governs Meta Content Library access and several research-data programmes. In the region, MAFINDO, Rappler, and Vera Files hold signatory status; Sri Lankan and Lao organisations face structural access gaps that the country pages name. See [Meta Content Library card](../tool-cards/meta-content-library.md) for the access-barrier framing.

### OOKC – Online Operations Kill Chain

Meta and Carnegie's chain-stage framework for analysing influence operations from acquisition through to terminal action. The institutional companion to ABCDE at the analytical-depth end. See [Online Operations Kill Chain card](../tool-cards/online-operations-kill-chain.md) and the 2C narrative.

## Platform suffixes

The toolkit uses two-character platform suffixes per Foundational Decision 4 for cross-referencing platform-specific guidance.

| Suffix | Platform | Regional dominance |
|---|---|---|
| `-wa` | WhatsApp | Personal messaging across Indonesia, Malaysia, Sri Lanka, Philippines |
| `-line` | LINE | All-purpose in Thailand |
| `-tiktok` | TikTok | Region-wide, election-cycle video |
| `-fb` | Facebook | Region-wide public discourse |
| `-fbg` | Facebook Groups | Closed-group rumour propagation |
| `-telegram` | Telegram | Scam economy hub region-wide |
| `-youtube` | YouTube | Longer-form video region-wide |
| `-x` | X (formerly Twitter) | Political discourse layer region-wide |

Full per-platform guidance in [platforms/index.md](../platforms/index.md).

## Cell numbering scheme

Tool cards and narrative cells organise by `Pillar.Tier.Cell` codes. The scheme runs across twenty-two outline subcategories.

- **1A.1, 1A.2, 1A.3, 1A.4** – Pillar 1, First-Line Triage: image, video, audio, provenance cells
- **1B.1 – 1B.5** – Pillar 1, Professional Verification: five cells covering archiving, AI text detection, audio professional verification, metadata and ELA forensics, fact-check databases
- **1C.1, 1C.2, 1C.3** – Pillar 1, Institutional-Level Analysis: coordinated-operation detection, institutional deepfake platforms, academic benchmark references
- **2A.1 – 2A.4** – Pillar 2, AI-Assisted Workflows: transcription and translation, geolocation, archiving, prebunking
- **2B.1, 2B.2, 2B.3** – Pillar 2, Collaborative Verification: tiplines, claim extraction, regional LLMs
- **2C.1, 2C.2, 2C.3** – Pillar 2, Large-Scale Intelligence: automated claim monitoring, network analysis, ABCDE / DISARM codification

Full cell-by-cell pivot in [tool-cards/index.md](../tool-cards/index.md).

## Cross-references

- [T6 source-protection tree](../decision-trees/t6-source-protection.md) – operational routing for S1 – S10
- [architectural-anchors.md](architectural-anchors.md) – full Anchor 1 – 3 treatment
- [editorial-patterns.md](editorial-patterns.md) – framework application patterns
- [change-log.md](change-log.md) – Foundational Decisions documented
- [tool-cards/index.md](../tool-cards/index.md) – cell pivot view
- [decision-trees/index.md](../decision-trees/index.md) – tree index
