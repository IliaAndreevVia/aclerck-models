# AClerck model packages

Downloadable model resources for AClerck offline speech recognition and language identification.
Weights are distributed only as GitHub Release assets; they are not stored in Git history.

**Prerelease 2026.11.06.1:** [release](https://github.com/IliaAndreevVia/aclerck-models/releases/tag/models-2026.11.06.1), [delivery manifest](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/model_delivery_manifest.json), [SHA256SUMS.txt](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/SHA256SUMS.txt).

**Not production-ready.** The application downloader and installation through a production APK have not been validated. The minimum compatible application version is unconfirmed (`minimum_app_version: null`, `production_ready: false`). Download verification does not change this status.

LID is the required shared delivery package and is installed once. Select any of the four independent ASR language packages; no ASR package needs the weights of another language. A manually selected ASR can technically run without LID, but the delivery policy requires LID. Automatic language selection can identify a language whose ASR is absent; the application must handle that condition.

| Package | Purpose | Required | ZIP bytes | Installed file bytes |
| --- | --- | --- | ---: | ---: |
| [lid](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/aclerck-models-lid-2026.11.06.1.zip) | Language identification: English, Russian, Arabic, Hebrew | Yes | 79947135 | 85379454 |
| [english](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/aclerck-models-english-2026.11.06.1.zip) | English recognition | Selectable | 74524693 | 81813143 |
| [russian](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/aclerck-models-russian-2026.11.06.1.zip) | Russian recognition | Selectable | 474621611 | 780242994 |
| [hebrew](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/aclerck-models-hebrew-2026.11.06.1.zip) | Hebrew recognition | Selectable | 820635472 | 885827330 |
| [arabic](https://github.com/IliaAndreevVia/aclerck-models/releases/download/models-2026.11.06.1/aclerck-models-arabic-2026.11.06.1.zip) | Arabic recognition | Selectable | 250465599 | 264514819 |

Every package has version **2026.11.06.1**. Total ZIP download: **1700194510 bytes**. Combined installed files: **2097774708 bytes**, counting the identical root configuration once. Installed sizes include model resources, configuration and accompanying legal materials.

ZIP/DEFLATE, without ZIP64; each asset is below 2 GiB. Extract into a common model root, preserving the package directories. All ZIPs contain an identical `native_deployment.json`: it maps supported directories and is not an installed-module inventory. Allow a common path only when its bytes match. Do not mix this set with other versions without compatibility validation.

The manifest records archive and per-file SHA-256, exact byte lengths, model formats and `model_interface_version: aclerck-native-v1`. ONNX uses IR 8 / opset 17 with embedded tensors; Whisper uses the pinned AClerck GGML Q8_0 interface. The interface label is a packaging contract; the existing application does not enforce it. See the manifest for the tested runtime requirements.

Packages were verified through the native CLI on Linux and Android (Samsung SM-A356E, API 36). Each ASR alone, LID plus each ASR, and the complete set were checked. Results are stable across those installation layouts on each platform. Arabic output differs between the two platforms. These checks do not validate the application downloader or production APK integration.

## Component licences

There is **no single licence for this repository or all model files**. Use the applicable component licences and notices:

- English Whisper and embedded OpenAI resources: OpenAI MIT; the retained Hugging Face card also declares Apache-2.0. Both texts/declarations accompany the package.
- Arabic fine-tune: publisher-declared Apache-2.0; OpenAI base/processor resources retain their MIT and source-card materials.
- Russian GigaAM-v3 and Hebrew fast-hebrew-asr: MIT; source cards and required attribution are retained.
- LID SpeechBrain encoder: declared Apache-2.0. **Ilia Andreev's custom classification head is permitted for use as part of AClerck under [its limited terms](licenses/ACLERCK_LID_TERMS.txt).** Those conditions apply only to his head, not to the complete ONNX file; all third-party parts retain their own rights and conditions.

See [third-party materials and sources](THIRD_PARTY_NOTICES.md). Each ZIP contains original licence texts, publisher cards, attribution and a model modification notice in its `licenses/` directory. These terms impose no conditions on user recordings or transcripts.
