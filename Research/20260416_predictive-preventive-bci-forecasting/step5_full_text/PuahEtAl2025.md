---
citation_key: "PuahEtAl2025"
paper_id: "paper_207"
title: "EEGDM: EEG Representation Learning via Generative Diffusion Model"
authors: "Jia Hong Puah; Sim Kuan Goh; Ziwei Zhang; Zixuan Ye; Chow Khuen Chan; Kheng Seang Lim; Si Lei Fong; Kok Sin Woon; Cuntai Guan"
year: 2025
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2508.14086"
tier: 3
composite: 4.0
---

# EEGDM: EEG Representation Learning via Generative Diffusion Model

**Citation:** `PuahEtAl2025` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2508.14086](https://arxiv.org/abs/2508.14086)
- **URL**: [http://arxiv.org/abs/2508.14086v3](http://arxiv.org/abs/2508.14086v3)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

While electroencephalogram (EEG) has been a crucial tool for monitoring the brain and diagnosing neurological disorders (e.g., epilepsy), learning meaningful representations from raw EEG signals remains challenging due to limited annotations and high signal variability. Recently, EEG foundation models (FMs) have shown promising potential by adopting transformer architectures and self-supervised pre-training methods from large language models (e.g., masked prediction) to learn representations from diverse EEG data, followed by fine-tuning on specific EEG tasks. Nonetheless, these large models often incurred high computational costs during both training and inference, with only marginal performance improvements as the model size increases. In this work, we proposed an EEG representation learning framework building upon Generative Diffusion Model (EEGDM). Specifically, we developed a structured state-space model for diffusion pretraining (SSMDP) to better capture the temporal dynamics of EEG signals and trained it using Denoising Diffusion Probabilistic Model (DDPM) framework. Subsequently, the resulting latent EEG representations were then used for downstream classification tasks via our proposed latent fusion transformer (LFT). To evaluate our method, we used multi-event datasets covering both interictal epileptiform discharges (TUEV) and seizure (CHB-MIT) detection, and compared EEGDM with current state-of-the-art approaches, including EEG FMs. Empirical results showed that our method outperformed the existing methods. These findings suggested that EEGDM offered a promising alternative to current FMs. Our source code and checkpoint are available at: https://github.com/jhpuah/EEGDM.
