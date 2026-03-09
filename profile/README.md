<div align="center">

<img src="https://c-elo.com/logo.webp" alt="C-elo Labs" width="160"/>

# C-elo Labs

**Building AI that speaks Africa's languages.**

[![Website](https://img.shields.io/badge/Website-c--elo.com-000?style=for-the-badge&logo=googlechrome&logoColor=white)](https://c-elo.com)
[![X (Twitter)](https://img.shields.io/badge/@c__elolabs-000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/c_elolabs)
[![Linkedin](https://img.shields.io/badge/C--elo-000?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/company/c-elo)
[![Email](https://img.shields.io/badge/hello@c--elo.com-000?style=for-the-badge&logo=gmail&logoColor=white)](mailto:hello@c-elo.com)

---

*Over 200 million East Africans speak languages that AI completely ignores.*
*Try asking ChatGPT Voice, Gemini Live, or Siri something in Kikuyu. Nothing. Zero support.*
*We're changing that.*

</div>

## What We Do

C-elo Labs builds **high-performance AI tools for low-resource African languages**, starting with **Kikuyu** (8M+ speakers in Kenya). We develop production-grade voice and text AI systems, from fine-tuned translation models to real-time speech-to-speech pipelines, and deploy them at [c-elo.com](https://c-elo.com) for anyone to use.

### Live Products

| Product | What It Does | Try It |
|---|---|---|
| 🎙️ **Voice Chat** | Speak Kikuyu, hear AI respond in Kikuyu — real-time streaming voice AI | [c-elo.com/c-elo-ai](https://c-elo.com/c-elo-ai) |
| 🌐 **Translation** | English ↔ Kikuyu neural translation (19.61 BLEU — 758% over baseline) | [c-elo.com/c-elo-ai](https://c-elo.com/c-elo-ai) |
| 🔊 **Text-to-Speech** | Type Kikuyu text, hear it spoken naturally | [c-elo.com/c-elo-ai](https://c-elo.com/c-elo-ai) |

---

## Research

Our research focuses on making state-of-the-art AI work for languages with limited data and tooling. We publish our methods, models, and datasets openly.

### Neural Machine Translation

We fine-tuned Google's **TranslateGemma-12B** for English ↔ Kikuyu using LoRA (r=128) on **30,430 curated sentence pairs**. Our model achieves **19.61 BLEU** — a **758% improvement** over the zero-shot baseline of 2.29 BLEU. We discovered through iterative experimentation that over-regularization degrades translation quality by 2+ BLEU points.

- **Model:** [gateremark/kikuyu-translategemma-12b-merged-V2](https://huggingface.co/gateremark/kikuyu_translategemma_12b_merged_V2) on Hugging Face
- **Training:** Unsloth + LoRA, deployed on Modal (A10G serverless GPU)

### Speech-to-Speech Models

We're building end-to-end voice AI for Kikuyu using a two-stage approach:

- **Stage 1 (Complete):** Adapted Kyutai's **Mimi neural audio codec** for Kikuyu tonal fidelity — 79.3M parameters, 0.071 validation loss, 1.1 Hz pitch error on 750+ hours of Kikuyu audio from the [African Next Voices](https://huggingface.co/datasets/MCAA1-MSU/anv_data_ke) corpus.
- **Stage 2 (In Progress):** Fine-tuning **Moshi** for full-duplex Kikuyu conversation, using 3,400+ hours of real Kikuyu podcast data.

### Real-Time Voice Pipeline

Our streaming voice chatbot uses a **cascaded pipeline**: MMS-1b-all ASR → LLM → MMS-TTS, achieving **sub-2-second end-to-end latency** on serverless GPUs.

### Dataset Engineering

We curate and process multi-source datasets for low-resource language AI:

- **African Next Voices corpus** — 750+ hours of Kikuyu speech audio
- **Google WAXAL TTS dataset** — ~9 hours of studio-quality Kikuyu recordings
- **30,430 English-Kikuyu sentence pairs** — curated for translation fine-tuning
- **3,400+ hours of Kikuyu podcasts** — real conversational data for speech model training

---

## Tech Stack

```
Frontend        Next.js · TypeScript · React
Backend         FastAPI · Python
ML/AI           PyTorch · Transformers · Unsloth · LoRA · vLLM
Models          TranslateGemma-12B · MMS-1b-all · MMS-TTS · Mimi · Moshi · Gemini
Compute         Modal (A10G/A100/H100 GPUs) · Azure
Deployment      Modal Serverless · Vercel
Data            Hugging Face Datasets · yt-dlp · pyannote.audio · Silero VAD
```

---

## Backed By

<div align="center">

| | |
|---|---|
| <img src="https://upload.wikimedia.org/wikipedia/commons/4/44/Microsoft_logo.svg" width="28" align="center"/> **Microsoft for Startups** | $10,000 Azure credits for compute and deployment |
| <img src="./googlecloudsvg.svg" width="24" align="center"/> **Google Cloud** | TRC Support program for AI research |
| <img src="./modalsvg.svg" width="24" align="center"/> **Modal** | Compute partnership for GPU-accelerated training and inference |

</div>

---

## Repositories

We're progressively open-sourcing our work. Here's what's coming:

| Repository | Description | Status |
|---|---|---|
| `translation-models` | Fine-tuned TranslateGemma for Kikuyu with training scripts and datasets | 🔜 Coming soon |
| `voice-pipeline` | Cascaded ASR → LLM → TTS streaming pipeline | 🔜 Coming soon |
| `mimi-kikuyu` | Mimi neural codec adaptation for Kikuyu tonal speech | 🔜 Coming soon |
| `kikuyu-datasets` | Curated sentence pairs, audio preprocessing scripts | 🔜 Coming soon |

> **Want early access?** Reach out at [hello@c-elo.com](mailto:hello@c-elo.com)

---

## Roadmap

- [x] Fine-tune translation model (TranslateGemma-12B for Kikuyu)
- [x] Build and deploy real-time voice chatbot pipeline
- [x] Adapt Mimi neural codec for Kikuyu (Stage 1)
- [x] Deploy live platform at c-elo.com
- [ ] Fine-tune Moshi for full-duplex Kikuyu conversation (Stage 2)
- [ ] Expand to additional African languages (Kamba, Luo, Swahili dialects)
- [ ] Launch public API for developers
- [ ] Publish research papers on low-resource language AI

---

## Contributing

We welcome contributions! Whether you're a linguist, ML engineer, native speaker, or just passionate about language preservation through technology:

1. **Follow us** to show support
2. **Open an issue** to suggest features, report bugs, or discuss ideas
3. **Submit a PR** to any of our open repositories
4. **Share datasets** — native speaker recordings, sentence pairs, or text corpora

---

## Contact

- **Website:** [c-elo.com](https://c-elo.com)
- **Email:** [hello@c-elo.com](mailto:hello@c-elo.com)
- **X (Twitter):** [@c_elolabs](https://x.com/c_elolabs)
- **LinkedIn:** [C-elo](https://linkedin.com/company/c-elo)

---

<div align="center">

**C-elo Labs** · Nairobi, Kenya 🇰🇪

*Bridging the gap with intelligence*

</div>
