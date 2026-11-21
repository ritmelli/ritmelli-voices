# Ritmelli Voices

Voice models of the Ritmelli sisters, for real-time voice conversion in the voice changer pedal of [Ritmelli](https://github.com/ritmelli/ritmelli).

| Voice | Who | Current release |
|---|---|---|
| **Mina** | the older sister, the lower voice | `mina-v0.2` (model `m3_50e`) |
| **Lira** | the younger sister, the higher voice | `lira-v0.2` (model `l3_50e`) |

Both characters are adults.

## Releases

The files live in the Releases, not in the git tree.

- **`engine-vX.Y`**: files shared by every voice. Contains `contentvec_n22080_fp16.onnx` (content encoder), `fcpe_fp16.onnx` (pitch detector), `ref.npz` (resampling and mel constants) and `meta.json` (engine parameters).
- **`mina-vX.Y`**, **`lira-vX.Y`**: one voice each. Contains the weights (`.pth`, 32 kHz), the real-time export (`*_encp_q334_fp16.onnx` and `*_dec_q32_fp16.onnx`), `config.json`, `model_info.json`, `voz.json` and the `LICENSE.md` that applies to that release. `voz.json` holds the pitch the voice sounds right at (`tom_hz`, in Hz, set by ear): Ritmelli shifts each speaker's own median pitch to it, so a new voice ships its own.

A voice needs the engine release to run.

## License

- **Voices:** the Ritmelli Voices License, in [LICENSE.md](LICENSE.md). Portuguese is the binding text; English is a translation. Each voice release states which version applies to it. The voice weights are fine-tuned from the RVC v2 pretrained model (MIT, RVC-Project/Retrieval-based-Voice-Conversion-WebUI); its license ships in each voice release as `LICENSE-rvc.txt`.
- **Engine:** third-party components under their own licenses: ContentVec (MIT, auspicious3000/contentvec) and FCPE (MIT, CNChTu/FCPE). Their licenses ship in the engine release as `LICENSE-contentvec.txt` and `LICENSE-fcpe.txt`.

Credit when publishing content made with a voice: "voice: Mina (Ritmelli)" or "voice: Lira (Ritmelli)".
