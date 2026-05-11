---
title: "Operational checklists – action-oriented pre-upload, pre-publication, pre-platform-report, pre-source-contact, post-publication monitoring"
summary: "Five checklists for the operational moments where attention is shortest and the consequences are sharpest. Intended to be lifted into a newsroom's standing-operating-procedure document, adapted to local context, and used as the discipline at the boundary of upload, publication, platform report, source contact, and post-publication monitoring."
---

# Operational checklists

The Digital Safety section's other four pages build the standing posture: the [country-legal-context](country-legal-context.md) layer, the [source-protection aggregation](source-protection-aggregation.md) of the ten S-classes, the [threat-models](threat-models.md) reading of recurring actor patterns, and the [index](index.md) framing. This page carries the action-oriented form of that posture: five checklists for the moments where the rest of the section's framing has to translate into a small set of steps a working desk can run quickly.

Unlike the rest of the toolkit's narrative pages, this page uses bullets and numbered lists where the content is operationally list-shaped. The brief that produced the Digital Safety section is direct: the checklist format here is appropriate because the content is genuinely a sequence of discrete checks, not a flowing argument.

The checklists below are templates. Adapt them to the local newsroom or fact-check operation. The country-page operational-routing sections and the [country-legal-context page](country-legal-context.md) carry the per-jurisdiction sharpening; a checklist run for a Lao political case will have additional steps a checklist run for an Indonesian celebrity-endorsement scam will not need.

## Checklist 1: pre-upload

Run this checklist before any source file is uploaded to a cloud-hosted tool. The checklist exists because the pre-upload moment is the point at which most S1 (source-identifying upload risk) and S9 (cross-border vendor retention) exposure is created, and once a file is uploaded the exposure cannot be reversed.

1. **Classify the file.** Is the file public (already widely circulating, no identifying source attached), sensitive (named subject, identifiable context, but no whistleblower or victim signal), or source-identifying (a face, voice, GPS, private handle, phone number, whistleblower material, victim identity, private group name, or original file from a vulnerable source)? Source-identifying material does not go through the standard cloud-hosted route.
2. **Check the topic for S2 firing.** Does the artefact concern police, military, monarchy, ruling party, cybercrime or fake-news laws, protest movements, red-tagging, national security, or authoritarian-context material? If yes, consult Digital Safety, legal counsel or the editor before the upload step proceeds. The [country-legal-context page](country-legal-context.md) carries the per-jurisdiction reading.
3. **Check the collection method for S5 firing.** Did the artefact come from WhatsApp, LINE, private Telegram, closed Facebook Groups, or private Messenger / Viber chats? If yes, use consented tipline submission only. Do not scrape, infiltrate, or expose group members.
4. **Check the vendor-jurisdiction for S9 firing.** Will the upload route the source file to a US-jurisdiction server (Hive, [Reality Defender](../tool-cards/reality-defender.md), Hiya / Loccus, [Sensity](../tool-cards/sensity.md), Deepware, [TrueMedia](../tool-cards/truemedia-georgetown.md)) or an EU-jurisdiction server (CERTH via InVID's deepfake tab, vera.ai consortium)? If yes, check organisational data policy and vendor retention terms. The [InVID-WeVerify](../tool-cards/invid-weverify.md) deepfake tab carries a 30-day CERTH retention window as the documented reference case.
5. **Apply pre-upload redaction where needed.** If a detector verdict is operationally necessary on source-identifying material, strip identifying context locally first: crop frames to remove location signals, blur faces or text identifying the source, redact audio to remove identifiable voice characteristics where the detector accepts redacted input.
6. **Route through offline alternatives where feasible.** [Sherloq](../tool-cards/sherloq.md) for image-and-metadata work, [ExifTool](../tool-cards/exiftool.md) for command-line metadata extraction, locally-deployable [SEA-LION](../tool-cards/sea-lion.md) for Lao or other SEA-language LLM-assisted analysis. The offline route is the right one when the source file cannot leave the verifier's machine.
7. **Archive before uploading.** Run [auto-archiver](../tool-cards/auto-archiver.md) cross-jurisdiction capture at [2A.3](../pillar-2-counter/2a-workflows.md) before the file goes to a detector. Archive failure after upload is a worse outcome than archive friction before upload.
8. **Document the upload chain.** If a cloud upload is the right call, log the file's pre-upload classification, the vendor, the retention window, and the operational reason for the upload in the verification record.

If a step in this checklist surfaces an issue the verifier cannot resolve alone, escalate to the editor or to the institutional Digital Safety contact before the upload happens. The [T6 source-protection tree](../decision-trees/t6-source-protection.md) routes the in-case decision.

## Checklist 2: pre-publication

Run this checklist before the verification is published. The pre-publication moment is where editorial framing decisions affect both the source-protection layer (S4 doxxing risk on identifying material in the debunk) and the legal-risk layer (publication that triggers takedown pressure, complaint-driven investigations, or cross-border legal intimidation).

1. **Separate verification from legal-risk review.** Verification asks whether the claim is accurate. Legal-risk review asks whether publication creates exposure regardless of accuracy. Content can be accurate and still trigger exposure under defamation, public-order, "harmful content," or anti-terror provisions. Both reviews are mandatory on cases touching named officials, security forces, royal or religious subjects, or community-reporting sensitive material.
2. **Check the publication format for S4 firing.** Does the debunk repeat identifying material that would deepen the original harm? Are slurs or addresses repeated in the verification text? Is the original poster identified in a way that propagates exposure? Redact identifiers in the debunk; consider a quiet response or tipline-only response in place of a public debunk where the public-debunk amplifies harm. The [threat-models page](threat-models.md) communal-memory pattern carries the framing.
3. **Apply the country-specific legal-risk reading.** The [country-legal-context page](country-legal-context.md) carries the per-jurisdiction reading. Indonesian UU ITE on public officials and corporate-or-institutional subjects is post-April-2025 reduced but not absent. Malaysian CMA 233 on 3R-coded material is active. Thai Article 112 on monarchy-adjacent material is binding. Sri Lankan OSA enforcement and PTA legacy bind on north-and-east community reporting. Philippine cyber-libel and anti-terror enforcement bind on security-forces and red-tagging-adjacent cases. Lao Decree 327 binds on political material.
4. **Run vendor-accuracy wrapping on detector claims.** Any detector verdict in the debunk should appear paired: vendor claim and independent finding, or the explicit "no independent SEA-specific benchmark identified" sentence. The Brawner / Hive 79.3% versus vendor 98% pair is the worked example in the toolkit.
5. **Apply two-non-detector-signals discipline.** Per Architectural Anchor 2, the publishable claim requires at least two non-detector signals (provenance, source-history, behaviour) alongside the detector class wrapped as one signal under Anchor 3. Verification that rests on detector-only evidence falls inside S6 and should be reframed as "tool flagged for review" until non-detector signals are surfaced.
6. **Avoid the liar's-dividend trap.** Per S8, do not say "fake" when evidence is insufficient. Say "we cannot verify AI manipulation" and surface the non-detector signals that are available. The framing matters because the language a verifier uses propagates into wider discourse.
7. **Confirm archive chain-of-custody.** Has the artefact been archived to a controlled cross-jurisdiction location? Is the chain-of-custody log retained off the production CMS? On regulator-action environments (Malaysia after the *Malaysiakini* CMS-access pattern, Sri Lanka under OSA), the archive-and-chain question is operational, not precautionary.
8. **Disclose AI use in the verification.** Where AI-assisted translation, transcription, summarisation, or claim-extraction was used in the verification workflow, disclose the use. The Indonesia Press Council Regulation No. 1/2025 framing applies in Indonesia; the wider regional norm is moving in the same direction.

## Checklist 3: pre-platform-report

Run this checklist before reporting content to a platform's trust-and-safety reporting infrastructure. The pre-platform-report moment is where the verifier hands material to a third-party (the platform) whose retention, sharing and enforcement practices are not under the verifier's control. The checklist is the smaller of the five but the consequences are sharp on cases where the platform's response can itself create exposure for the source or the verifier.

1. **Confirm the report is the right route.** Could the case be handled through the [T7 tipline routing tree](../decision-trees/t7-tipline-routing.md) response-gate without involving the platform's enforcement layer? Platform reports can produce takedowns that surface the verifier as the reporting actor in ways the source did not consent to.
2. **Check the source-protection implications of the report.** Will the platform report require submission of material that identifies the source? If yes, run the pre-upload checklist's S1 and S9 steps on the material going to the platform.
3. **Check the country-legal-context implications.** On Thailand, the July 2025 24-hour-takedown rules mean platform reports can cascade quickly into removal pressure. On Malaysia, the ONSA framework includes proactive-monitoring incentives; platform reports operate inside that frame. On Sri Lanka, the OSA centralises state authority over accounts and "online locations"; the platform-report layer can interleave with state enforcement in ways the verifier should anticipate.
4. **Preserve the artefact independently.** Archive the content (cross-jurisdiction route via [auto-archiver](../tool-cards/auto-archiver.md)) before the platform report goes in. Platform-driven removal can make the artefact unavailable for future verification or for partner-mediated routing.
5. **Document the report.** Log the platform, the report category, the date and time, the reporting account, and the operational reason for the report in the verification record. The documentation is not procedural; it is the audit trail that protects the verifier on regulator-action environments where post-publication review may follow.
6. **Anticipate the platform's response timeline.** Platform reports do not produce instant outcomes. On election-cycle work where takedown pressure interleaves with publication timing, the report timeline is part of the editorial calculation, not an external variable.

## Checklist 4: pre-source-contact

Run this checklist before initiating contact with a source. The pre-source-contact moment is where the verifier introduces themselves into the source's exposure surface; the contact itself can be the harmful action on surveillance-environment cases.

1. **Confirm the source's consent posture.** Has the source consented to being contacted? Did the source reach out (via tipline, public posting that invited follow-up), or is the contact verifier-initiated? Verifier-initiated contact on a source who did not invite it carries different consent implications.
2. **Check the source's exposure surface.** Is the source already publicly attached to the material? On the Bee Laos March 2024 case, the source was already on the video and named on the account; any republication propagates exposure the state has acted on. On a deniable-tipline source, the consent boundary is sharper.
3. **Apply the S2 country-specific reading.** On Lao, Thai (Article 112), Philippine (red-tagging), Sri Lankan (OSA and PTA), and Malaysian (3R-coded) sensitive cases, the contact itself can carry legal-risk exposure for both the verifier and the source. Consult Digital Safety or legal counsel before contact on the highest-S2 cases.
4. **Use compartmentalised communications.** On surveillance-environment cases, the channel matters operationally. Signal with disappearing-message defaults; pseudonymous handles where appropriate; reduced-data devices for sensitive contact. On Pegasus-history Thailand and on Predator-infrastructure Philippines, phone-compromise threat-modelling is operational on the highest-risk cases.
5. **Minimise the identifying-material exchange.** Do not request identifying material the verification does not need. Do not retain identifying material the verification does not require. The S1 routing applies in the inbound direction as well as the outbound direction.
6. **Document the contact attempt.** Log the source, the channel, the contact rationale, and the consent posture in the verification record. The documentation protects the source on retrospective reviews and the verifier on regulator-action environments.
7. **Plan the follow-up posture.** Will the verifier need to maintain contact through publication and after? On red-tagging-adjacent cases, the source's exposure surface can change after publication; the contact infrastructure has to support that.

## Checklist 5: post-publication monitoring

Run this checklist after the verification is published. The post-publication moment is where harassment backlash (S10), source-security follow-up (S1 and S5), and regulator-action surface manifest. The checklist exists because the publication itself does not close the source-protection question; the question continues for the lifetime of the publication and sometimes longer.

1. **Monitor harassment backlash on the verifier.** Coordinated-abuse patterns after publication on red-tagging-adjacent cases, on 3R-coded debunks, on Article 112-adjacent Thai work, or on KontraS-style Indonesian researcher work can target the verifier specifically. The Tempo pig's-head and decapitated-rats threats documented by CPJ in March 2025 are the operational anchor. Document threats. Secure accounts and devices. Activate the newsroom safety protocol.
2. **Monitor source security.** Has the source's exposure surface changed post-publication? On surveillance-environment cases, the verifier should maintain a check-in cadence with the source through the immediate post-publication window. The Bao Mor Khaen / Sisay Luangmonda March 2026 case in Laos is the upper-bound reminder.
3. **Monitor regulator action.** Has the publication attracted takedown notice, complaint-driven investigation, or regulator inquiry? On Thailand under the 24-hour-takedown rules, on Malaysia under the ONSA framework, on Sri Lanka under OSA centralised authority, and on Indonesia under post-April-2025-narrowed UU ITE, the regulator-action surface is operational.
4. **Rotate reviewers on trauma-load cases.** Per S10, repeated viewing of harmful content (conflict footage, abuse material, voice-clone violent-threat material) carries trauma exposure for the verifier. Limit exposure. Rotate reviewers. Activate peer-support infrastructure. The standing-operating-procedure document carries the workflow form.
5. **Update the verification record.** Has new evidence surfaced after publication that affects the verification's confidence? Has a related case appeared that the verification should cross-link to? The verification record is a living artefact, not a closed file.
6. **Plan the long-cycle response.** On election-cycle work, on red-tagging-adjacent cases, and on communal-memory politics cases, the post-publication monitoring window extends beyond the immediate. The newsroom's standing-operating-procedure document carries the long-cycle response posture.

## Cross-references

- [T6 source-protection tree](../decision-trees/t6-source-protection.md) – in-case routing for S1, S2, S3, S4, S5, S6, S7, S8, S9, S10
- [Source-protection aggregation](source-protection-aggregation.md) – the ten S-classes as one editorial system
- [Country-specific legal context](country-legal-context.md) – per-jurisdiction sharpening of pre-publication and pre-platform-report checks
- [Threat models](threat-models.md) – actor-pattern framings that route through the checklists
- [T7 tipline routing](../decision-trees/t7-tipline-routing.md) – response-gate routing for pre-platform-report checklist
- Country pages: [Indonesia](../countries/indonesia.md), [Laos](../countries/laos.md), [Malaysia](../countries/malaysia.md), [Philippines](../countries/philippines.md), [Sri Lanka](../countries/sri-lanka.md), [Thailand](../countries/thailand.md)
- Tool cards: [auto-archiver](../tool-cards/auto-archiver.md), [Sherloq](../tool-cards/sherloq.md), [ExifTool](../tool-cards/exiftool.md), [SEA-LION](../tool-cards/sea-lion.md), [InVID-WeVerify](../tool-cards/invid-weverify.md), [Content Credentials Verify](../tool-cards/content-credentials-verify.md), [Meedan Check](../tool-cards/meedan-check.md), [MAFINDO Kalimasada](../tool-cards/mafindo-kalimasada.md)

## Sources

- [T6 source-protection tree](../decision-trees/t6-source-protection.md) (the routing layer the checklists operationalise)
- [Architectural Anchors](../methodology/architectural-anchors.md) – Architectural Anchors 1, 2, 3; vendor-accuracy wrapping and limitation faithfulness
- Electronic Frontier Foundation. *Surveillance Self-Defense.* EFF, 2025. [ssd.eff.org](https://ssd.eff.org/).
- Committee to Protect Journalists. *Digital Safety.* CPJ, 2025. [cpj.org/digital-safety](https://cpj.org/digital-safety/).
- Country pages' operational-routing sections (per-country handles)
