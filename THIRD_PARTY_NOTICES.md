# AClerck model materials and sources

These notices cover the model packages only. No licence for AClerck application source is granted. No blanket licence is assigned to the repository, combined LID graph or package set.

| Component | Author / publisher | Pinned source |
| --- | --- | --- |
| lid | SpeechBrain team (encoder); Ilia Andreev (custom head) | [speechbrain/lang-id-voxlingua107-ecapa](https://huggingface.co/speechbrain/lang-id-voxlingua107-ecapa/tree/0253049ae131d6a4be1c4f0d8b0ff483a0f8c8e9) |
| english | OpenAI | [openai/whisper-base.en](https://huggingface.co/openai/whisper-base.en/tree/911407f4214e0e1d82085af863093ec0b66f9cd6) |
| russian | GigaChat Team; publisher ai-sage | [ai-sage/GigaAM-v3](https://huggingface.co/ai-sage/GigaAM-v3/tree/ec1dc1f01d0d627ab2c0d3acc1e235702300d95e) |
| hebrew | asfberlin (fine-tune); GigaChat Team (base) | [asfberlin/fast-hebrew-asr](https://huggingface.co/asfberlin/fast-hebrew-asr/tree/f374969f14a6c7b9d5a829f8bfb80de041931f8b) |
| arabic | oddadmix (fine-tune); OpenAI (base and processor) | [oddadmix/whisper-small-arabic-dialectal-v2](https://huggingface.co/oddadmix/whisper-small-arabic-dialectal-v2/tree/1bc3e652fd4c0a4dfc9a94c8629af219ffaddff1) |

The Arabic embedded processor/tokenizer comes from `openai/whisper-small` at `973afd24965f72e36ca33b3055d56a652f456b4d`; its acoustic weights remain the oddadmix fine-tune. Embedded Whisper mel filters originate from OpenAI Whisper 20250625.

Original complete texts: [OpenAI MIT](licenses/OpenAI-Whisper-MIT.txt), [GigaAM MIT](licenses/GigaAM-MIT.txt), [Apache-2.0](licenses/SentencePiece-Apache-2.0.txt), [AClerck custom-head terms](licenses/ACLERCK_LID_TERMS.txt). The Apache filename identifies the retained canonical text; it does not make SentencePiece the licensor of other models.

The Hebrew publisher declares MIT for the weights and credits asfberlin, GigaChat Team, SLPRL-HUJI/HebDB (CC-BY-4.0 per card) and ivrit-ai/crowd-transcribe-v5. The SpeechBrain card credits VoxLingua107. Publisher model cards and their original notices are retained in each ZIP. The upstream language-name reference is not AClerck's four-class classifier.

Per-package `licenses/MODEL_CHANGES.md` identifies the exact distributed files and conversions: Whisper GGML/Q8_0, Russian selective static INT8 ONNX, Hebrew FP32 ONNX, and SpeechBrain FP32 encoder plus the exact custom four-class head. These modification notices are included in the ZIPs, alongside `licenses/INDEX.txt` and the original materials.

Ilia Andreev's own-head permission covers only his classifier weight and bias for use in AClerck. It neither relicenses nor restricts SpeechBrain and other third-party components. Original publisher cards may contain public usage examples; AClerck user recordings and recognition results are not distributed.
