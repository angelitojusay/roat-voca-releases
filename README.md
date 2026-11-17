# Roat Voca releases

Public downloads for **Roat Voca**, the local Visual ADR (lip re-sync) and talking-presenter studio that pairs with [Roat](https://github.com/angelitojusay/roat).

## Model packs

Roat Voca's GPU engines run two ONNX model packs. The app downloads them from the [`voca-models-v1.1`](https://github.com/angelitojusay/roat-voca-releases/releases/tag/voca-models-v1.1) release when you click **Download Pack**. Each file is checked against the SHA-256 pinned inside the app, so a changed file is refused.

| Pack | Engine | Made from | Licence | Size |
|---|---|---|---|---|
| `voca-adr-v1` 1.0.0 | Visual ADR (`onnx-musetalk`) | MuseTalk v1.5, sd-vae-ft-mse, Whisper tiny | MIT / Apache-2.0 | 2.01 GB |
| `voca-presenter-v1` 1.1.0 | Talking Presenter / PiP (`onnx-liveportrait`) | LivePortrait's own modules | MIT | 538 MB |

- **Asset names** are `<pack>__<file>`, for example `voca-adr-v1__unet.onnx`; each pack's `manifest.json` lists its files, sizes and hashes.
- `SHA256SUMS-models.txt` checks a manual download (`sha256sum -c SHA256SUMS-models.txt`).
- `THIRD-PARTY-NOTICES.txt` holds every licence text.
- **No face detector is included.** InsightFace's research-only models are not part of either pack, and Roat Voca crops the face from the box you draw.

The packs are ONNX exports of the models' published weights, made with Roat Voca's model pack exporter from pinned upstream files.
