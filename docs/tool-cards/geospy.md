---
tool_id: TOOL-066
slug: geospy
name: GeoSpy
maintainer: Graylark Technologies
type: non-detector
outline_cells:
 - {id: "2A.2", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: proprietary
languages_ui: [en]
languages_content: [agnostic]
access: web
cost: freemium
documented_country_use: []
tags: [geolocation, ai-geolocation, image, osint, faktisk, source-history]
---

# GeoSpy

**Vendor:** [geospy.ai](https://geospy.ai) | **Type:** Non-detector | **Cost:** Freemium

!!! abstract "TL;DR"
    An AI photo-geolocation tool that infers a likely city or
    region from visual features in an image. Useful at the
    triage step when a video frame or image needs a starting-
    point geographic hypothesis before manual OSINT corroboration.
    Verified by Faktisk Verifiserbar in Norwegian fact-check
    work; not a substitute for the human chaining that follows.

## What it does

GeoSpy, operated by Graylark Technologies, accepts a still image
and returns a probability-ranked list of likely geographic
locations: typically at the city or region level, occasionally
with finer detail when the image contains identifiable visual
features (signage, distinctive architecture, characteristic
vegetation). The model is trained to extract features not always
obvious to a human viewer (soil colour, sky tone, power-line
geometry, road markings) and match those against learned
geographic priors.

The product line splits between a free tier branded GeoSpy Plus
(open access, city- and region-level accuracy, suitable for
hobbyists and OSINT enthusiasts per the vendor) and a paid Pro
tier restricted to verified law enforcement, government agencies,
journalists, and enterprise users (priority access, finer
location detail, additional reporting features). The product
line is unified under a single GeoSpy platform as of 2025–2026
following an earlier split between GeoSpy Plus and GeoSpy Pro.

For toolkit work, GeoSpy is a starting-point hypothesis
generator. A frame extracted from a video using InVID-WeVerify, an image lifted from a social-media post, or a
photograph attached to a tipline message goes through GeoSpy to
get a candidate region; the user then chains the candidate
against satellite imagery, street-view, time-of-day clues, and
local knowledge in standard Bellingcat-style geolocation work.

## When to use it

- A video frame or photograph of an outdoor scene needs a
 geographic starting-point hypothesis before manual OSINT
 chaining begins.
- A regional fact-check team is processing a high volume of
 user-submitted images and wants a triage layer that
 prioritises which images warrant deeper geolocation work.
- An institutional investigation has access to the Pro tier and
 needs the additional reporting and integration features for
 case documentation.
- A workshop is training participants on AI-assisted geolocation
 workflow and needs a tool that demonstrates the limitations
 of the technique alongside its useful starting-point output.

## Limitations

!!! info "Limitations"
    - Predictions need OSINT corroboration. The
    tool produces a ranked geographic hypothesis, not a
    verified location; treating the top result as ground truth
    is a documented failure mode.
    - Indoor scenes, generic streetscapes, stock-image-quality
    compositions, and AI-generated images degrade prediction
    reliability sharply. The training data favours outdoor
    scenes with distinguishable visual features.
    - The Pro tier's eligibility process restricts access to
    verified law enforcement, government, journalist, and
    enterprise accounts; civil-society organisations and
    non-newsroom NGOs may need explicit verification with
    Graylark before access is granted.
    - Cloud-only product; images uploaded for analysis are
    processed on Graylark servers under that vendor's terms.
    Source-identifying scenes (a recognisable home exterior, a
    photograph that places an informant at a specific
    address) require pre-upload sensitivity classification.
    - AI-generated or stylised images are not reliably handled —
    the model assumes the input is a real photograph; the
    toolkit does not recommend GeoSpy as a synthetic-image
    detection signal.

## Privacy and threat model

GeoSpy is a cloud product. Images uploaded for analysis are
processed on Graylark servers; the company is US-headquartered
and operates under US jurisdiction. For non-source-identifying
public content (a photograph from a public political event, a
frame from a publicly circulated video) the data flow is
acceptable. For source-identifying material (an image that
would let an adversary identify a location associated with a
named source), the upload is the risk, not the verdict.

For Sri Lanka and Laos surveillance-environment work, the
recommended routing matches the Pillar 1 cloud-detector pattern:
classify each image as public, sensitive, or source-identifying
before upload. Sensitive images that need geolocation should
either be cropped to remove source-identifying detail before
upload, or routed through manual chaining (street-view,
satellite imagery, local-knowledge networks) without GeoSpy in
the chain. The tool is a productivity layer, not a mandatory
step.

!!! danger "Source-protection override (S1 — source-identifying upload risk)"
    Uploading an image that would let an adversary identify a
    location associated with a named source (a witness's home, a
    safe-house street view, a meeting venue) exposes the source
    via the Graylark cloud. Mitigation steps:

    1. Classify the image as public, sensitive, or source-
    identifying before any GeoSpy call.
    2. For source-identifying material, do not invoke GeoSpy. Use
    manual chaining (Google Street View, satellite imagery,
    local-knowledge networks) instead; these do not transmit
    the source file.
    3. If a GeoSpy lead is operationally necessary, crop or blur
    the image to remove source-identifying detail on the local
    machine before uploading the redacted version.
    4. Document the upload in your case record and disclose to the
    source as part of source-protection practice.

## Country and platform applicability

- **Indonesia:** language-agnostic; useful for outdoor
 scene geolocation in Indonesian fact-check work, particularly
 for election-period images of political rallies and public
 events. No documented Indonesian-specific deployment cited in
 the inventory.
- **Laos:** language-agnostic; the Lao-content
 geolocation gap is operational rather than tool-specific.
 Field-recorded images from Laos go through the same routing
 thinking as the Lao text path: cloud upload via GeoSpy or
 diaspora/partner-mediated review.
- **Malaysia:** language-agnostic; useful for general
 OSINT work on Malaysian images.
- **Philippines:** language-agnostic; pairs with the
 #FactsFirstPH coalition's image-verification chain.
- **Sri Lanka:** language-agnostic; useful for outdoor
 geolocation on Sinhala-region or Tamil-region content. Pairs
 with Watchdog's OSINT workflow.
- **Thailand:** language-agnostic; useful for AFP Fact
 Check Thailand and Thai PBS image-verification work,
 particularly on regional rural or cross-border content.

Documented use cited  is Faktisk Verifiserbar
(Norway), a non-SEA reference that establishes the tool's
fact-check credibility but does not document SEA deployment
specifically. Platform applicability: works on any image the
user can download; relevant across Facebook, Facebook Groups, TikTok,
YouTube, LINE, WhatsApp, Telegram.

## How to access

Sign up for the free GeoSpy Plus tier at geospy.ai. The Pro tier
requires an eligibility verification process documented at
pro.geospy.ai; verified law enforcement, government, journalist,
and enterprise accounts are accepted. The mobile app
("GeoSpy: AI Location Finder") is available on the Apple App
Store with in-app purchases for premium features. The free tier
is sufficient for most fact-check triage use; the Pro tier is
relevant only for institutional users with case-volume or
reporting requirements that the free tier does not cover.

## Cost (current as of 2026-05)

Freemium. The free GeoSpy Plus tier offers a monthly image quota
(historically 20 images per month at the entry tier) at no cost.
Mid-tier Developer access historically priced around USD
60/month (1,000 images), with Pro tier at around USD 500/month
(10,000 images, premium GPU, priority support) and Enterprise
at custom pricing. Pricing is documented in vendor-side and
third-party reviews (mspoweruser 2024, aimojo 2024) but the
toolkit pins no live figure because Graylark revises tiers; the
verify-before-budgeting pointer applies. Verify the current
pricing page at geospy.ai before committing an institutional
workflow.

## Quickstart

1. Visit geospy.ai and sign up for the free Plus tier.
2. Before uploading, classify the image as public, sensitive, or
 source-identifying: the cloud-upload routing decision sits
 here.
3. For non-source-identifying images, upload via the web
 interface or the mobile app.
4. Read the returned ranked geographic hypothesis as a
 starting-point, not as a verified location.
5. Chain the top candidate against satellite imagery, street-
 view, time-of-day clues, weather records, and local-knowledge
 sources, using standard Bellingcat-style geolocation methodology.
6. Document the chain (intermediate screenshots, data sources,
 reasoning) so the verified location is defensible for the
 eventual fact-check publication.
7. For institutional work that needs the Pro tier's reporting
 features, request access via pro.geospy.ai and provide the
 required verification.

## In the toolkit's workflow

Source-history pillar non-detector productivity tool per
Architectural Anchor 1. Sits in 2A.2 as the AI-geolocation
alternative alongside the cell's primary cross-cell entry
InVID-WeVerify (which carries reverse-image search but
not AI-geolocation), the Amnesty-maintained Citizen
Evidence Lab YouTube Data Viewer (YouTube-specific source-
history), and the Bellingcat archiving infrastructure Auto Archiver.

Standard combinations:

- With **InVID-WeVerify** at 2A.2 / 1B.1 – extract
 keyframes via InVID, then run candidate frames through GeoSpy
 for a geographic hypothesis before manual chaining.
- With **Citizen Evidence Lab YouTube Data Viewer** at
 2A.2 when the image source is a YouTube clip and upload-
 time metadata is needed alongside the visual hypothesis.
- With **Auto Archiver** at 2A.2 to preserve the
 source URL before any analysis; the archiving step matters
 if the geolocation eventually feeds a publishable claim.
- With **Sherloq** at 1B.4 when the image carries
 metadata that should be inspected offline before any
 geolocation upload.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md)
routes to GeoSpy at T1.9 (place / time / light plausibility), and
[T2 video triage](../decision-trees/t2-video-triage.md) routes to
GeoSpy at T2.11 (event plausibility) after keyframe extraction.
[T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk)
routes source-identifying images away from GeoSpy and toward manual
chaining (see [Digital Safety](../digital-safety/source-protection-aggregation.md)).

This card carries no detector signal class: GeoSpy produces a
geographic hypothesis, not a synthetic-content verdict. Per
Anchor 1 the hypothesis is a source-history input that combines
with reverse-image, archived-version, and metadata signals; per
Anchor 2 a GeoSpy hit by itself is not publishable evidence
without manual OSINT corroboration.

## Override notes

!!! note "Override notes"
    - **Non-detector declaration:** GeoSpy
    generates a geographic hypothesis, not a synthetic-content
    verdict. It serves the source-history pillar and is
    framed throughout as a triage layer that requires manual
    OSINT corroboration before publication.

## Sources

- External: [GeoSpy 101 — What Is GeoSpy?](https://geospy.ai/blog/geospy-101-ai-visual-geolocation)
 (current product structure, GeoSpy Plus
 / GeoSpy Pro split, eligibility framing)
- External: [GeoSpy AI Review](https://mspoweruser.com/geospy-ai-review/)
 (historical tier pricing for budget
 context; pre-unification structure)
