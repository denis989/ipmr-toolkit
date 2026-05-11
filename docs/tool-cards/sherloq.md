---
tool_id: TOOL-009
slug: sherloq
name: Sherloq
maintainer: GuidoBartoli
type: non-detector
outline_cells:
 - {id: "1B.1", role: primary, density_role: alternative}
 - {id: "1B.4", role: primary, density_role: alternative}
pillar_service: [source-history]
signal_class: non-detector
status: active
last_verified: 2026-05-10
license: mit-permissive
languages_ui: [en]
languages_content: [agnostic]
access: desktop
cost: free
documented_country_use: [LK, LA]
tags: [image-forensics, ela, jpeg-ghosts, prnu, noiseprint, offline, surveillance-environment]
---

# Sherloq

**Publisher:** [github.com/GuidoBartoli/sherloq](https://github.com/GuidoBartoli/sherloq) | **Type:** Non-detector | **Cost:** Free

!!! abstract "TL;DR"
    A free open-source PySide2/Qt desktop application implementing
    JPEG ghosts, ELA, noise analysis, PRNU/Noiseprint, and an EXIF
    reader, all running entirely offline. The toolkit's mandatory
    mitigation for Sri Lanka and Lao surveillance-environment work
    where uploading the source image is itself a risk.

## What it does

Sherloq is a desktop image-forensics application by Guido Bartoli
that bundles the standard image-forensics methods into a single GUI:
JPEG ghost analysis (recompression-pattern detection), Error Level
Analysis (ELA), noise-pattern visualisation, PRNU and Noiseprint
sensor-pattern checks, and an EXIF metadata reader. All operations
run on the user's own machine. No file leaves the desktop unless the
user explicitly shares the output.

The tool's value to the toolkit is twofold. As a forensics toolkit,
it covers the pixel-level analysis layer that pairs with ExifTool's metadata layer. As a privacy posture, it is the offline
alternative to FotoForensics: same ELA methodology,
fundamentally different threat model. For surveillance-environment
work where uploading a sensitive frame to a cloud forensics service
exposes the source, Sherloq is the right tool. The toolkit binds
this as a mandatory mitigation in the country-applicability section.

## When to use it

- A Sri Lankan or Lao source has shared a sensitive image and you
 need ELA / JPEG-ghost analysis without sending the file to a
 cloud forensics service.
- A working session involves multiple consecutive forensic
 operations on the same file; Sherloq keeps everything in one GUI
 rather than chaining web tools.
- A defamation-defence case requires documented forensic methodology
 on a desktop with chain-of-custody control over the file.
- A workshop in a surveillance-aware country (Sri Lanka, Lao) calls
 for demonstrating offline-by-default forensics rather than
 cloud-by-default.

## Limitations

!!! info "Limitations"
    - One-developer project; while actively maintained, the bus
    factor is one.
    - GUI installation has the friction of any desktop forensics
    tool; not a press-button option for First-Line Triage.
    - The forensic methods themselves (ELA, JPEG ghosts, PRNU) have
    well-known limitations in low-resolution or heavily
    transcoded inputs; Sherloq exposes these methods cleanly but
    does not solve their underlying constraints.

## Privacy and threat model

Sherloq runs entirely locally. No file is uploaded; no network call
is made for the forensic operations. This is the operationally
critical privacy property for the toolkit's surveillance-environment
work in Sri Lanka and Lao. The risk surface reduces to the user's
own machine: a hardened analyst workstation running Sherloq exposes
no file material to any external party.

Pair Sherloq with full-disk encryption on the workstation, with
hashing of the source file (`shasum -a 256`) before and after
analysis, and with documented operational security practices around
the workstation itself. This is the source-protection mitigation the
toolkit recommends as the default for any sensitive case in
Sri Lanka or Lao.

## Country and platform applicability

- **Indonesia:** applies in principle for any case warranting
 offline forensics; not the dominant deployment context.
- **Laos:** mandatory mitigation. The Lao information
 environment makes cloud forensics services a structural risk;
 Sherloq is the toolkit's recommended desktop default for Lao work
 where forensic analysis is needed.
- **Malaysia:** applies in principle.
- **Philippines:** applies in principle; Rappler and VERA
 Files have access to broader detector and forensics platforms but
 Sherloq remains relevant for sensitive cases.
- **Sri Lanka:** mandatory mitigation. The Sri Lankan
 surveillance environment under OSA / PTA carries documented
 source-exposure risk for cloud-uploaded sensitive material;
 Sherloq is the toolkit's recommended desktop default for Sri
 Lankan work where forensic analysis is needed.
- **Thailand:** applies in principle, especially given the
 lèse-majesté legal context where source exposure risk also
 matters; pairs with ExifTool for metadata work on the
 same files.

Platform applicability: works on any image regardless of source
platform.

## How to access

Source and releases at GitHub: [github.com/GuidoBartoli/sherloq](https://github.com/GuidoBartoli/sherloq).
Installation requires Python and PySide2/Qt; binary releases are
published for Windows and macOS. No account, no licence key.

## Cost (current as of 2026-05)

Free. MIT-style permissive licence. Open-source single-developer
project; sustainability depends on the maintainer's continued
activity, with the inventory recording active maintenance.

## Quickstart

1. Visit [github.com/GuidoBartoli/sherloq](https://github.com/GuidoBartoli/sherloq) and download the latest
 release for your operating system.
2. Install via the OS-specific installer (Windows.exe, macOS.dmg)
 or via `pip install -r requirements.txt && python sherloq.py`
 from source.
3. Launch the GUI; open the source image with File → Open.
4. Run the modules you need: ELA, JPEG ghosts, noise analysis,
 PRNU/Noiseprint, EXIF reader. Each appears as a tab in the
 Sherloq interface.
5. Save the analytical outputs locally; do NOT use cloud sync
 services that would route the source file off the machine.
6. Hash the source file before and after with `shasum -a 256` if
 chain-of-custody documentation matters.

## In the toolkit's workflow

Source-history pillar non-detector tool per Architectural Anchor 1.
Sits as alternative at 1B.1 multi-tool plugins (Sherloq is the
offline-desktop option) and as alternative at 1B.4 metadata / ELA
forensics (where the GUI ELA layer is its core contribution).

Standard combinations:

- With **ExifTool** for metadata extraction on the same
 source file in the same offline session; both run locally, both
 cover complementary forensic layers.
- With **InVID-WeVerify** at 1B.1 only when the case is
 not source-sensitive; for sensitive cases, Sherloq replaces the
 InVID workflow rather than supplementing it.
- With **FotoForensics** at 1B.4 – explicitly NOT in the
 same case; Sherloq is the offline alternative to FotoForensics's
 cloud ELA. Choose based on sensitivity classification.
- With **MetaDataKit** at 1B.1 – both are local-by-design;
 MetaDataKit covers browser-WASM metadata work; Sherloq covers
 desktop forensics work.

This card produces a non-detector signal: forensic readouts are
source-history signals (recompression patterns, sensor-pattern
matches, metadata) that do not depend on probability scoring. Per
Anchor 2, a Sherloq output combined with a detector verdict is two
signal classes (non-detector + detector); per the toolkit's
editorial commitment a publishable claim usually requires that
combination plus one further signal.

Decision-tree references: [T1 image triage](../decision-trees/t1-image-triage.md) – Sherloq is the
sensitivity-cleared escalation for surveillance-environment work
at T1.6 (metadata) for the Sri Lanka and Laos regional routing
described in T1.15. [T6 source-protection](../decision-trees/t6-source-protection.md#s1-source-identifying-upload-risk) –
Sherloq is the recommended forensic path for sensitive material
(see [Digital Safety](../digital-safety/source-protection-aggregation.md)).

## Override notes

!!! note "Override notes"
    - **Offline operation (d4-pass-offline):** the tool runs entirely
    locally; no file is uploaded; no network call is made for
    forensic operations. This is its core privacy posture and is
    named in the Privacy and threat model section as the operational
    property that makes Sherloq the surveillance-environment
    default.

    - **Sri Lanka and Lao surveillance mitigation
    (sri-lanka-laos-surveillance-mitigation-binding):** Sherloq is
    the toolkit's mandatory mitigation for Sri Lankan and Lao
    forensic work where cloud upload of sensitive material is a
    structural risk. Bound into the Country and platform
    applicability section above and into the T6 Source-protection
    decision tree.

## Sources

- Bartoli, G. *Sherloq — open-source digital image forensic toolset (GUI)*. GitHub (MIT-style licence). [github.com/GuidoBartoli/sherloq](https://github.com/GuidoBartoli/sherloq).
