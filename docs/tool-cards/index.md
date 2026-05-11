# Tool cards — pivot view

Sixty-five tools across the twenty-two outline subcategories, ordered
by outline cell. Cross-cell tools are listed once per cell with a
single canonical card link. Tier-functional notes follow each cell
heading per the outline structure.

Every cell has cards in `docs/tool-cards/[slug].md`; cross-links
across cells are live and bidirectional. The canonical reference
cards are
[InVID-WeVerify](invid-weverify.md) (multi-cell, multi-pillar
deployable tool exemplar), [MAFINDO Kalimasada](mafindo-kalimasada.md)
(single-country tipline exemplar), and [TRIED Benchmark](tried-benchmark.md)
(institutional-reference exemplar: framework applied to other tools
rather than a deployable tool itself).

---

## Pillar 1 — Detect and triage

### 1A — First-Line Triage

#### 1A.1 — Image

A five-minute phone read on whether a forwarded image carries any
AI signal at all. The cell is for the screenshot-from-WhatsApp
moment when the question is whether to keep working with the file
or set it aside; three tools cover it – a multimodal commercial
detector, an uncertainty-declaring open alternative, and a
non-detector provenance check, so that no single output reads as
a verdict. Cases that warrant a thirty-minute desk pass escalate
into 1B.1.

- [Hive AI](hive-ai.md) — detector — primary
- [ImageWhisperer / Detectai.live](imagewhisperer.md) — mixed-with-declaration —
 alternative
- [Content Credentials Verify](content-credentials-verify.md) — non-detector (provenance) —
 alternative

#### 1A.2 — Video

The same triage band as 1A.1, but for moving image, where detector
class confidence sits structurally lower – independent benchmarking measured best-in-class
at 0.78 accuracy on 2,036 in-the-wild deepfakes, and SEA-platform-
compressed video has no public benchmark. Two tools only, by
deliberate honest-gap policy: a multi-pillar plugin whose
reverse-image and metadata modules often resolve the case before
the deepfake tab is ever opened, plus one press-button detector.
Cell-level discipline is binding here – a detector verdict on its
own never carries a public claim.

- [InVID-WeVerify](invid-weverify.md) — non-detector +
 cautious-detector mixed — primary (cross-cell)
- [Deepware Scanner](deepware-scanner.md) — detector — alternative

#### 1A.3 — Audio (constrained)

A single multimodal entry at first-line tier, by deliberate
honest-gap policy. The audio detector class is broken across SEA
languages per the [DW Innovation](dw-innovation-audit.md) November 2025 audit;
tonal-language phonetics, codec-compressed audio, and low-resource
scripts defeat the press-button options that exist. Use Hive AI (Hive Moderation / Hive Detect / Hive AI Detector)
for a quick lay-read on language-agnostic synthesis artefacts only,
and escalate to 1B.3 the moment the case warrants more than five
minutes.

- [Hive AI](hive-ai.md) — detector — primary (cross-cell from 1A.1)

#### 1A.4 — Provenance / watermark (architecturally important)

The only Pillar 1 first-line band where non-detector signals are
the primary mode. When a file carries C2PA Content Credentials
or a [SynthID](synthid-detector.md) watermark, the question shifts from "is this
AI-generated?" to "what does the manifest say about who made this
and how?" – a path that aligns directly with Anchor 1's
provenance-first framing. The three verifier tools cover end-user
verification, Google-DeepMind-watermarked content, and forensic
inspection of the manifest itself. The cell-level gap is manifest
survival across SEA hardware (Realme, Vivo, Oppo, Xiaomi,
Transsion) and across WhatsApp/Facebook/TikTok strip-on-upload –
not independently documented.

- [Content Credentials Verify](content-credentials-verify.md) — non-detector — primary
 (cross-cell from 1A.1)
- [SynthID Detector](synthid-detector.md) — non-detector (provenance) — alternative
- [C2PA Conformance Explorer](c2pa-conformance-explorer.md) — non-detector — alternative

### 1B — Professional Verification

#### 1B.1 — Multi-tool plugins (workhorse hub)

The desk-hour workhorse of Pillar 1, where a working fact-checker
assembles a verifiable source-history record before any escalation.
Four privacy-postured options let the user match tool to threat
model: a cloud-mitigated default, an offline desktop alternative
for surveillance-risk environments (Sri Lanka, Laos), a
local-WASM browser option for source-protection-binding cases,
and the command-line standard for batch or scripted work. Every
card here carries an S1-mitigation note by cell-level binding.
Entry from 1A FLT escalations; bridges down to 1B.4 for ELA work
and up to 1C.2 for enterprise-grade deepfake platforms.

- [InVID-WeVerify](invid-weverify.md) — non-detector +
 cautious-detector mixed — primary (cross-cell)
- [ExifTool](exiftool.md) — non-detector — alternative
- [Sherloq](sherloq.md) — non-detector — alternative (offline desktop)
- [MetaDataKit](metadatakit.md) — non-detector — alternative (browser-WASM)

#### 1B.2 — AI text detection (contracted)

Contracted on purpose. Users arrive at this cell asking whether
they can prove a piece of text was generated by an LLM; the
toolkit's plain answer is "not reliably, especially in
non-English." Two cards stand here as cautionary cases – one
defensible current vendor, one clearest cautionary tale per
the Stanford 2023 and Perkins 2024 evidence – both under a
binding "do not use as standalone evidence" frame. Productive
work on textual cases routes to 2B.2 claim extraction instead.

- [Pangram AI](pangram-ai.md) — detector — primary
- [GPTZero](gptzero.md) — detector — alternative

#### 1B.3 — Audio deepfake forensics (structural ceiling)

The productive ceiling for audio work in this toolkit. A Lao
political voice clip, a Thai scam call, or a Tagalog
candidate-impersonation audio that warrants a thirty-minute desk
pass lands here. Three viable detectors plus the DW Innovation
editorial reference; under Anchor 3 the three count as one
detector class signal, and under Anchor 2 each case still needs
a non-detector pair – caller verification, platform-of-origin
check, voice-comparison interview – before any public claim.
Cross-language detector unreliability is binding at the
cell level.

- [TOOL-STUB-DEEPFAKETOTAL Deepfake Total](deepfake-total-stub.md) — detector — alternative (stub)
- [Hiya / Loccus](hiya-loccus.md) — detector — primary (only press-button SEA option)
- [TrueMedia.org (Georgetown McCourt School)](truemedia-georgetown.md) — mixed-with-declaration — escalation-option (closed beta)
- [DW Innovation audit](dw-innovation-audit.md) — institutional reference

#### 1B.4 — Metadata / ELA forensics

Where ELA, EXIF, and metadata-spoofing checks happen once a
multi-tool pass has surfaced an image worth deeper inspection.
Three tools by threat-model band: a command-line standard for
non-destructive metadata extraction (no upload, low-risk), an
offline desktop alternative when the source file cannot leave
the machine, and a cloud ELA option for low-sensitivity material
where S1 classification clears web upload. The cell-level
discipline is plain: metadata is spoofable, and most images
encountered on WhatsApp, Facebook, or TikTok have already lost
their EXIF before they reach the user – that absence is itself
a signal to read, not a tool failure.

- [ExifTool](exiftool.md) — non-detector — primary (cross-cell from 1B.1)
- [Sherloq](sherloq.md) — non-detector — alternative (cross-cell from 1B.1)
- [FotoForensics](fotoforensics.md) — non-detector — alternative

#### 1B.5 — News-reliability scoring

When the question stops being "is this content AI-generated?" and
becomes "is the outlet that published this reliable?", users
reach for source-reliability scoring. The cell pairs a
multilingual fact-check claim explorer (the default first stop,
returning existing fact-check work and ClaimReview metadata
across Bahasa Indonesia and more) with a paid reliability service
for the 16 languages it covers (Indonesian, Tagalog, Thai
included) and an EU DisinfoLab knowledge layer for institutional
readers. Sinhala and Lao outlets sit outside [NewsGuard](newsguard.md) coverage,
so Sri Lankan and Lao workflows rely on the local fact-check
ecosystem (Hashtag, Watchdog, FactSeeker) alongside the
Google explorer.

- [Google Fact Check Explorer](google-fact-check-explorer.md) — non-detector — primary
- [NewsGuard](newsguard.md) — non-detector — alternative
- [AI Disinfo Hub (EU DisinfoLab)](ai-disinfo-hub.md) — non-detector — escalation-option

### 1C — Institutional-Level Analysis

#### 1C.1 — CIB detection (largest single landscape)

Entry to Pillar 1's institutional tier, and the single largest
landscape in the inventory at 38 entries. This is where the
question becomes "is there a behavioural pattern across accounts,
posts, and timing?" – the analytical move from organic claim to
coordinated operation, and one that requires Python proficiency
or paid enterprise access. The four-tool ladder runs from
open-source primary (locally on user-supplied data) through two
academic R/Python alternatives to the enterprise escalation
option; the standard institutional pipeline pairs CIB output
with 2B.2 extraction and 2C.1 monitoring. SEA-specific
worked-example casebook absence is the cell's named gap.

- [CIB Mango Tree](cib-mango-tree.md) — non-detector
 (behaviour pillar) — primary
- [Coordination Network Toolkit](coordination-network-toolkit.md)
 — non-detector — alternative
- [CooRTweet](coortweet.md) — non-detector — alternative
- [Graphika](graphika.md) — non-detector — escalation-option

#### 1C.2 — Enterprise / open-source deepfake platforms

The deepfake-detection ceiling of Pillar 1. This is where a
Rappler-grade investigative pipeline lands when it needs to
certify whether a video case is AI-generated – the Doc Willie
Ong eye-drop case (98% / 75.5% / 94%) and the Brawner 79.3%
work are the documented precedents. Three institutional-grade
options cover documented-deployment confidence, broadcaster-grade
alternative, and the academic evaluation harness; under Anchor 3
all three still count as one detector signal class no matter how
many ensemble verdicts they aggregate internally. Vendor accuracy
figures come from anonymised pools where independent scores are
not separable – cell-binding caveat on every card.

- [Sensity AI](sensity.md) — detector — primary (cross-cell
 awareness with 1A.1, 1A.2, 1B.1 escalations)
- [Reality Defender](reality-defender.md) — detector —
 alternative
- [DeepfakeBench](deepfakebench.md) — non-detector +
 reference benchmark — alternative

#### 1C.3 — Explainable AI forensics

Where a probability score stops being enough and the question
becomes whether the verdict can withstand a defamation suit or a
legal challenge – the toolkit's explainability layer for
evidence-grade reporting. The cell carries a GradCAM/SHAP/LIME-on-
EfficientNet primary (heatmaps that can be embedded in a
published forensic report), a reliability-map alternative whose
declared uncertainty band is itself the signal under Anchor 1,
and the WITNESS evaluation framework as institutional reference
for methodology review. Explainability is built and benchmarked
on English-language and Western-face data; Sinhala and Lao
defamation contexts still require manual interpretation alongside
the visualisation.

- [XAI-Deepfakes](xai-deepfakes.md) — detector +
 explanation-output — primary
- [TruFor](trufor.md) — non-detector + reliability-map —
 alternative (mixed-with-declaration)
- [TRIED Benchmark (WITNESS)](tried-benchmark.md) —
 institutional reference (third reference card; institutional-
 reference exemplar)

---

## Pillar 2 — Counter

### 2A — AI-Assisted Workflows

#### 2A.1 — Transcription / summarisation / translation

The pure productivity entry of Pillar 2. The cell is for handling
a Lao voice memo, a Thai parliamentary transcript, or a Tagalog
Facebook livestream when the source has to stay local enough that
S1 sensitivity classification holds. An open-source local primary
covers routine work; paid [Google Cloud Translation](google-cloud-translation.md) is the only
documented Lao path, accepted with the Google-server caveat; the
journalist-pipeline option covers multi-source archival cases
where Google-server upload is acceptable. Whisper's low-resource
performance for Sinhala and Lao is named honestly in the cards;
fallback to multilingual figures would mask the gap.

- [OpenAI Whisper](openai-whisper.md) — non-detector — primary
- [Google Cloud Translation](google-cloud-translation.md) — non-detector — alternative (only Lao path)
- [Google Pinpoint / Journalist Studio](google-pinpoint.md) — non-detector — alternative (cross-cell with 2B.3)

#### 2A.2 — Reverse-image / geolocation enhanced

Where most non-text claims start to resolve, long before any
detector touches the file. A reverse-image hit or an archival
capture is one non-detector source-history signal under Anchor 2,
combining with claim-extraction (2B.2) or fact-check-database
(1B.5) results for any institutional reading. Four tools cover
the standard one-click plugin (cross-cell from 1B.1, handling
reverse-image queries plus archived versions in one move), a
Faktisk-validated AI geolocator, an Amnesty-maintained YouTube
data viewer, and the Bellingcat archiving companion under G-030
rapid-archiving discipline. No cell-level honest-gap of note –
the tools work language-agnostically.

- [InVID-WeVerify](invid-weverify.md) — non-detector — primary (cross-cell from 1A.2 / 1B.1)
- [GeoSpy](geospy.md) — non-detector — alternative
- [Citizen Evidence Lab YouTube Data Viewer](citizen-evidence-lab-ydv.md) — non-detector — alternative
- [Auto Archiver (Bellingcat)](auto-archiver.md) — non-detector + archiving — alternative

#### 2A.3 — Prebunking / media-literacy (rich)

One of the few cells where SEA already has gold-standard examples
in the inventory. Users reach for these tools in training contexts, not on
artefacts in active fact-check work – a workshop
in Indonesia runs [Tempo Detektif Deepfake](tempo-detektif-deepfake.md) directly, and a
trainer in Thailand, Sri Lanka, or Malaysia adapts the Cambridge
inoculation-game architecture because no SEA-localised
inoculation game exists outside Indonesia yet. The IREX/RAND
25% multi-source-checking improvement and the Jigsaw Indonesia
campaign are cited as evidence that prebunking effects are real
and measurable. Localised effectiveness measurement outside
Indonesia is the cell's named gap.

- [Tempo Detektif Deepfake](tempo-detektif-deepfake.md) — non-detector + prebunking — primary
- [IREX L2D / Gali Fakta](irex-l2d-gali-fakta.md) — non-detector + media-literacy — alternative
- [Jigsaw Prebunking](jigsaw-prebunking.md) — non-detector + campaign — alternative
- [Bad News / Harmony Square](bad-news.md) — non-detector + game — alternative

#### 2A.4 — Newsroom workflow management (INCLUDE MARGINALLY)

Included marginally as an editorial choice: an adjacent pointer, not
a primary recommendation row. Two SEA-grounded examples – a Tempo
archival-query assistant for Indonesia and the MAFINDO Satgas
Pemilu 2024 Election Task Force as a workflow design pattern –
show how Indonesian newsrooms have orchestrated AI assistance
around verification work. The cell is deliberately short, because
the inventory outside these two is dominated by non-deployable
Innovation Challenge prototypes; the toolkit does not pretend
that workflow-management AI is yet a deployable category in SEA.
Bridge to 2B.1, where the MAFINDO tipline itself lives.

- [Tempo Assistant](tempo-assistant.md) — non-detector + workflow — primary adjacent pointer
- [MAFINDO Satgas Pemilu](mafindo-satgas-pemilu.md) — non-detector + workflow — primary adjacent pointer

### 2B — Collaborative Verification

#### 2B.1 — Multilingual tiplines (rich)

The heart of Pillar 2 – the place where the claim of durable,
strategic value is anchored, because the user base does the
work and AI helps process the intake. Match platform to country:
WhatsApp + Bahasa points to [Kalimasada](mafindo-kalimasada.md); LINE + Thai points to
Cofact (the only LINE-native option in the inventory); a
multilingual deployment with self-hostability points to Meedan
Check (140K+ users, CekFakta and #FactsFirstPH backbone);
Malaysia's multi-language plus Tamil case points to Sebenarnya
AIFA with the public-facing exception-pass and the
government-operator independence caveat attached. Lao has no
tipline in the toolkit and the cell says so directly; Sri Lanka
remains a form/email/WhatsApp patchwork distribution, not a
Meedan-style backend.

- [Meedan Check](meedan-check.md) — non-detector + tipline-platform — primary
- [Cofact Thailand](cofact-thailand.md) — non-detector + tipline — alternative (LINE-native)
- [Kalimasada (MAFINDO)](mafindo-kalimasada.md) — non-detector + tipline — alternative (Indonesia WhatsApp)
- [Sebenarnya.my AIFA](sebenarnya-aifa.md) — non-detector + tipline — alternative (Malaysia, government-operated with independence caveat; B1 exception-pass)

#### 2B.2 — AI claim extraction (rich)

Where tipline volume scales beyond manual processing and AI
extraction keeps the operation functional. The largest inventory
landscape after CIB (42 entries); five cards cover SEA's language
asymmetry. Sri Lanka work routes to the Sinhala-asymmetric-strong
primary (Watchdog/LIRNEasia Dissect) first, then to the pan-Indian
Tamil tool with the Sri-Lanka adaptation gap noted; Indonesia
work routes to MAFINDO's Bahasa database with the multilingual
XLM-R fallback; cross-country and Lao material routes to Alegre
because XLM-R is the only multilingual non-vendor option that
covers Lao at all (with a low-resource disclaimer pass). Tamil
Sri-Lanka-specific adaptation gap ([X-CLAIM](x-claim.md) is pan-Tamil, not
SL-adapted) and Lao claim-extraction absence are the
cell's binding named gaps.

- [Dissect (Watchdog SL / LIRNEasia)](dissect-watchdog-lirneasia.md) — non-detector — primary (Sinhala asymmetric-strong)
- [Meedan Alegre](meedan-alegre.md) — non-detector — alternative (multilingual XLM-R, Lao fallback path; matching engine of Check)
- [Yudistira (MAFINDO)](yudistira-mafindo.md) — non-detector — alternative (Bahasa Indonesia)
- [ClaimBuster](claimbuster.md) — non-detector — alternative (English baseline, b2-disclaimer-pass)
- [X-CLAIM](x-claim.md) — non-detector — alternative (Tamil pan-Indian; Sri-Lanka-specific adaptation gap binding caveat)

#### 2B.3 — LLMs in fact-check workflows

The LLM-as-tool layer of Pillar 2: useful, hallucinatory, and
moving fast. Journalists handling Bahasa, Filipino, or Thai
material run [SEA-LION](sea-lion.md) locally for hallucination-mitigated draft
outputs, then verify every claim downstream against 2B.2
extraction or 1B.5 reliability scoring before publication; lay
users in Laos, Malaysia, Philippines, and Thailand have the
mobile app option under a binding hallucination caveat;
Malay-first work in Malaysia escalates to [MaLLaM](mallam-mesolitica.md) (Mesolitica) as
the Malay-specific option. SEA-LION v4 (AI Singapore, March
2026) closed the previously-paired Lao real-gap in this cell;
Sinhala remains absent from the major SEA LMs and is handled
outside this category via the Dissect / LIRNEasia stack noted
in 2B.2.

- [SEA-LION](sea-lion.md) — non-detector — primary (regional foundation model; explicit Lao coverage in v4 March 2026; Sinhala absent)
- [AI Fact Checker App](ai-fact-checker-app.md) — non-detector + mobile — alternative (LA / MY / PH / TH app-store localisation)
- [Google Pinpoint](google-pinpoint.md) — non-detector + LLM-pipeline — alternative (cross-cell from 2A.1; cloud-LLM journalist-pipeline mode)
- [MaLLaM (Mesolitica)](mallam-mesolitica.md) — non-detector — escalation-option (Malay-specific, Mesolitica)

### 2C — Large-Scale Intelligence

#### 2C.1 — Automated claim monitoring

Cross-platform monitoring infrastructure across mixed cost tiers,
with civil-society alternatives explicit. The cell demonstrates that
monitoring exists at multiple price bands and that free academic and
SEA-civil-society options are genuine alternatives, not consolation
prizes.

- [Information Tracer (Rolli)](information-tracer.md) — non-detector — primary (paid mid-tier cross-platform tracer)
- [Media Cloud](media-cloud.md) — non-detector — alternative (free academic news-source corpus)
- [Sinar Project iMAP](sinar-project-imap.md) — non-detector — alternative (free open-source SEA-specific network monitoring; MalaysiaNow / Malaysia-Today MCMC blocking documented)
- [FactFlow AI (Newtral)](factflow-ai.md) — non-detector — alternative (Telegram-specific platform specialist; Animal Político 10M-message processing)

#### 2C.2 — Network analysis

The mapping and visualisation layer downstream of CIB analysis (1C.1)
or claim-monitoring (2C.1). [Maltego](maltego.md) is the OSINT gold standard with
a free Community Edition; [Gephi](gephi.md) is the free open-source visualisation
alternative; [Meta Content Library](meta-content-library.md) is the IFCN-gated data source
for institutional partners with the access path.

- [Maltego](maltego.md) — non-detector — primary (OSINT gold standard, freemium with free Community Edition)
- [Gephi](gephi.md) — non-detector — alternative (free open-source desktop visualisation; standard pairing downstream of Maltego, [CooRTweet](coortweet.md), Mango Tree)
- [Meta Content Library](meta-content-library.md) — non-detector — escalation-option (IFCN-signatory only; journalists excluded; combined Sebenarnya operator-identity caveat + Graphika cite-as-external-source quickstart redirect)

#### 2C.3 — Cross-lingual narrative tracking + DISARM

Framework references rather than deployable tools; the
TRIED-pattern voice register applies. ABCDE is the toolkit's surface
analytical vocabulary per Decision 2; DISARM is the institutional
annex; [Online Operations Kill Chain](online-operations-kill-chain.md) is the operational sequencing
complement; [DISARM Navigator](disarm-navigator-stix2.md) + STIX2 is the technical tooling layer
for institutional CSIRT and government-partner deployment.

- [ABC / ABCDE Framework](abcde-framework.md) — framework — primary (toolkit's surface analytical vocabulary per Decision 2)
- [DISARM Framework](disarm-framework.md) — framework — alternative (institutional annex per Decision 2; FIMI vocabulary verbatim caveat)
- [Online Operations Kill Chain](online-operations-kill-chain.md) — framework — alternative (operational sequencing; Meta / Carnegie ten-phase)
- [DISARM Foundation Navigator + STIX2](disarm-navigator-stix2.md) — framework + tooling — escalation-option (institutional CSIRT / government-partner deployment)
