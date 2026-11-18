# Roat Voca

**Local Visual ADR (lip re-sync) and talking-presenter studio for Windows, macOS and Linux. The companion app to [Roat](https://github.com/angelitojusay/roat).**

Roat Voca re-syncs a speaker's mouth to new dialogue, and turns a talking-head clip into a full-frame presenter or a picture-in-picture bubble that speaks your voiceover. Renders, audio analysis and the AI models all run on your computer. There are no accounts and no telemetry, and nothing is uploaded.

**[⬇ Download the latest release](https://github.com/angelitojusay/roat-voca-releases/releases/latest)** · current version **v1.2.0**

| Platform | Download | |
|---|---|---|
| Windows 10/11 (x64) | [Roat-Voca-1.2.0-win-x64.exe](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-win-x64.exe) | Installer |
| Windows 10/11 (x64) | [Roat-Voca-1.2.0-portable.exe](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-portable.exe) | Portable, no install |
| macOS, Apple Silicon | [Roat-Voca-1.2.0-mac-arm64.dmg](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-mac-arm64.dmg) · [.zip](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-mac-arm64.zip) | |
| macOS, Intel | [Roat-Voca-1.2.0-mac-x64.dmg](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-mac-x64.dmg) · [.zip](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-mac-x64.zip) | Draft engines only (see below) |
| Linux (x64) | [Roat-Voca-1.2.0-linux-x86_64.AppImage](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/Roat-Voca-1.2.0-linux-x86_64.AppImage) | AppImage |

SHA-256 checksums: [SHA256SUMS.txt](https://github.com/angelitojusay/roat-voca-releases/releases/download/v1.2.0/SHA256SUMS.txt). On Windows: `Get-FileHash .\Roat-Voca-1.2.0-win-x64.exe -Algorithm SHA256`.

**Before you start:** Roat Voca uses Roat's engine, chiefly its ffmpeg. Install [Roat](https://github.com/angelitojusay/roat/releases/latest) first (or have ffmpeg on your `PATH`).

## What's new

### v1.2.0
- **Roat's looks, in Roat Voca.** All 36 **Roat Studio Looks** from Roat v1.2.0 are in the Look menu: Clean Contrast, Warm Film, Teal & Amber and Nordic Matte, each for Rec.709 and for the eight camera log spaces. Roat Voca uses Roat's own files, or writes identical ones itself.
- **Roat's LUT Library, shared.** Your **Roat Mimic Looks** and **My Custom LUTs** are listed too: Roat's `luts` folder and the LUT Library folder set in Roat's Settings (for example `F:\_LUTs`), grouped by pack and camera. Everything is read in place and nothing is copied. **Rescan Roat LUT Library** picks up what Roat has added since. A handoff graded with a Studio Look or a Mimic look arrives with that look selected.
- **HD Mouth & Teeth Restore** (Visual ADR, MuseTalk, on by default). On a wide smile, MuseTalk's 256 × 256 face leaves the upper teeth grey and soft. Roat Voca now finds the open mouth between the lips in each frame and restores edge detail and the brightness of the teeth inside it only. Lip colour, the cheeks, the beard and the smile lines of **Native Plate Detail** stay exactly as they were. It is built in, with nothing to download.
- **Roat v1.2.0 parity.** Alloy, Nova, Sky and Isabella join the voices a handoff can name (23 in all), and drop-frame timecode follows Roat's own rules (29.97 and 59.94 only).
- **Video plates only.** Roat Voca now works from real footage alone. A Talking Presenter or PiP bubble is made from a talking-head clip (`.mp4`, `.mov`, `.mxf`, `.mkv`, `.webm`, `.avi`). Still photos and the built-in studio avatar are gone. A dropped still image is refused with "Roat Voca requires a video plate for Visual ADR".
- **Support Roat Voca.** A **Buy Me a Coffee** link sits at the foot of the Dock. It opens Roat's page in your browser. Nothing is gated, counted or tracked.

### v1.1.6
- **Your own LUT arrives with the handoff.** A `.roatlip` from Roat v1.1.5 or later that was graded with your own `.cube` carries a copy of it beside the manifest (`<clip>.roatlip.cube`). Roat Voca now loads that copy on import, checks it, and selects it in the Look menu, marked **(handoff)**. Built-in camera LUTs are selected on import too. An older handoff without the copy still offers **Locate Handoff .cube…**.
- **Presenters who move stay in sync.** For a talking-head clip, **Track the Face** (on by default) follows the head from the box you draw on the first frame, so the new mouth and LivePortrait's crop stay on a presenter who sways or walks across the frame. When the clip is shorter than the voiceover and loops, each loop starts where the clip does. The tracker is built in, with nothing to download.

### v1.1.5
- **Load Custom .cube...** in the Look menu grades with any 3D `.cube` LUT (2 to 65 points). The whole file is checked before it is used. A Roat handoff graded with your own LUT can be pointed at its `.cube` once with **Locate Handoff .cube…**.
- **Talking-head clips as presenters.** `.mp4`, `.mov`, `.webm` and `.mkv` clips play along with the voiceover (and loop when shorter), next to `.png`, `.jpg` and `.webp` stills (stills were removed in v1.2.0: video plates only). LivePortrait reads every frame of the clip and smooths the mouth from frame to frame.

### v1.1.4
- **Eight camera LUTs, the same as Roat's:** ARRI LogC3, RED Log3G10, DJI D-Log and Panasonic V-Log join Sony S-Log3 (S-Gamut3.Cine, S-Gamut3) and Canon C-Log2 / C-Log3, each to Rec.709.
- **Native Plate Detail handles smiles.** When the original take smiles and the new line doesn't, the smile lines beside the nose follow the new mouth, while the nose, eyes and outer cheeks stay untouched.

### v1.1.3
- **Installers for Windows, macOS and Linux**, and the AI model packs hosted publicly here.

### v1.1.2
- **LivePortrait runs fully on the GPU** with DirectML, about three times faster per frame.
- **An Out-point face box.** Draw the face at the In and the Out of a shot and Roat Voca follows a push-in or a move between them.
- **Drop-frame timecode** at 29.97 and 59.94 in the editor timelines.

### v1.1.1
- **Tracked Mouth ROI.** The face box follows the speaker through the shot.
- **Native Plate Detail.** Only the mouth and jaw are replaced; the rest of the face stays the original footage.

## What Roat Voca does

### The Studio
- **One window:**
  - the Dock on the left (five Quick Recipes and four Studio Tools);
  - the Monitor in the middle, with a **Before / After split-wipe**, the face box you drag, and Space to play;
  - the Inspector on the right, with every setting;
  - the drawer below, with the **Batch Queue**, the **Transcript** (the handoff's captions) and your **Deliverables**.
- **Quick Recipes** set up a whole job in one click: **Visual ADR Re-Sync**, **Kokoro Dubbed Lip-Sync**, **Talking Presenter (16:9)**, **Circular PiP Explainer Bubble** and **Transparent PiP Overlay**.

### Visual ADR (lip re-sync)
- **The mouth follows the new line.** You replace a line of dialogue, and the speaker's mouth in the original shot is redrawn to match. The new line can be any audio Roat hands over: a recorded or cleaned take, or a Kokoro voiceover or dub made in Roat.
- **MuseTalk v1.5 on the GPU:**
  - Windows: DirectML, which works with any DirectX 12 graphics card;
  - NVIDIA: CUDA where available;
  - Apple Silicon: Core ML;
  - CPU otherwise.
  - A **Deterministic Draft** engine renders instantly, with no model at all.
- **Tracked face box:**
  - Draw the box once on the In point; it follows the face through the shot.
  - Add an **Out-point box** for push-ins and big moves.
- **Native Plate Detail:** only the mouth and jaw are replaced, and the smile lines blend with the new mouth. The nose, eyes, glasses and outer cheeks stay the original footage.
- **HD Mouth & Teeth Restore:** crisper teeth and inner-lip edges on wide smiles, inside the open mouth only.
- **Speech-gated:** silent frames stay the original picture, and an `.srt` / `.vtt` can limit the change to its spoken lines.

### Talking Presenter and PiP
- **What it animates:** a talking-head clip (`.mp4`, `.mov`, `.mxf`, `.mkv`, `.webm`, `.avi`), speaking the handoff's audio. Roat Voca works from real video only: no still photos and no synthetic avatar.
- **The engine:** **LivePortrait** on DirectML, CUDA or Core ML, or the Deterministic Draft.
- **Clips:** the face is tracked as the head moves, and the clip loops under a longer line.
- **Layouts:**
  - **Full 16:9 presenter**, with an optional burned-in caption track;
  - **PiP bubble**, circle or rounded, with a coloured ring, over the camera clip, a studio backdrop, key green, or a **transparent** background.

### Looks and the Roat handoff
- **Eight built-in camera LUTs**, the same cubes as Roat's: Sony S-Log3 ×2, Canon C-Log2 / C-Log3, ARRI LogC3, RED Log3G10, DJI D-Log and Panasonic V-Log, each to Rec.709.
- **Roat Studio Looks** (36), **Roat Mimic Looks** and **My Custom LUTs** from Roat's LUT library, read in place.
- **Your own `.cube` LUTs.**
- **One-click handoff from Roat:**
  - In Roat, use **Studio → Deliverables → Export .roatlip**.
  - Then drop the `.roatlip.json` on Roat Voca, open it, or click **Import .roatlip from Clipboard**.
  - The audio, captions, camera clip, In / Out, voice and LUT come across. A custom LUT's `.roatlip.cube` is loaded automatically.

### Deliverables and timelines
- **Codecs:**
  - **H.264** `.mp4`;
  - **ProRes 422 HQ** `.mov`;
  - **ProRes 4444 with alpha** `.mov` (a true transparent bubble for V2 over your own V1).
  - ProRes files have 24-bit PCM audio and source timecode, plus an H.264 preview for the monitor.
- **Frame-exact editor timelines** for every deliverable:
  - **FCPXML 1.9** for DaVinci Resolve and Final Cut Pro;
  - **Premiere XML (xmeml v5)** for Adobe Premiere Pro.
  - The original camera clip goes on V1 and the render above it, at the source timecode, with drop-frame at 29.97 and 59.94.
- **Checked in the editors:**
  - **DaVinci Resolve Studio 21.2**: both formats, at 25 fps and 29.97 drop-frame;
  - **Adobe Premiere Pro 27.0**: the Premiere XML, at 25 fps, with no offline clips and the ProRes 4444 alpha read as straight alpha.
  - (Roat itself writes the multi-cam timelines and the CMX 3600 EDL; those were checked in both editors too.)

## What stays on your computer, and when the app goes online

**Offline, always:**
- every render, preview and timeline;
- audio analysis and face tracking;
- LUT grading;
- the AI models.

Your media, handoffs and LUTs never leave your computer. The clipboard is read only when you click **Import .roatlip from Clipboard**.

**Online, only when you click Download Pack.** Roat Voca's single network request is a model pack download that you start in the Inspector's pack card:
- **Source:** this repository's [`voca-models-v1.1`](https://github.com/angelitojusay/roat-voca-releases/releases/tag/voca-models-v1.1) release, over HTTPS.
- **Checks:** every file is verified against the SHA-256 built into the app, and a changed file is refused.
- **After that:** the packs are used offline.

There is no update check, analytics or crash reporting. Links you click (like this page) open in your browser.

## Model packs

| Pack | Engine | Made from | Licence | Size |
|---|---|---|---|---|
| `voca-adr-v1` 1.0.0 | Visual ADR (`onnx-musetalk`) | MuseTalk v1.5, sd-vae-ft-mse, Whisper tiny | MIT / Apache-2.0 | 2.01 GB |
| `voca-presenter-v1` 1.1.0 | Talking Presenter / PiP (`onnx-liveportrait`) | LivePortrait's own modules | MIT | 538 MB |

- **Asset names** are `<pack>__<file>`, for example `voca-adr-v1__unet.onnx`. Each pack's `manifest.json` lists its files, sizes and hashes.
- `SHA256SUMS-models.txt` checks a manual download (`sha256sum -c SHA256SUMS-models.txt`).
- **Only weights licensed for commercial use are included.** Wav2Lip and InsightFace's research-only face models are not, and no face detector ships: Roat Voca works from the box you draw and its own built-in tracker.
- `THIRD-PARTY-NOTICES.txt` holds every licence text for the models and the app.

## First launch
- **Windows:** the builds are not code-signed yet, so SmartScreen asks once (**More info → Run anyway**).
- **macOS:** if macOS calls the unsigned download damaged, run `xattr -cr "/Applications/Roat Voca.app"`.
- **Intel Macs** render with the Deterministic Draft engines; the AI engines need Apple Silicon.
- **Linux:** make the AppImage executable (`chmod +x`).
- **Getting the models:** open the Inspector's engine card and click **Download Pack** (`voca-adr-v1` for Visual ADR, `voca-presenter-v1` for the presenter). Until then, **Auto** renders with the Deterministic Draft.
