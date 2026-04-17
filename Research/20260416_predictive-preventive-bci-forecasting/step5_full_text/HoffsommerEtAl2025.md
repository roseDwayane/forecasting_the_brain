---
citation_key: "HoffsommerEtAl2025"
paper_id: "paper_180"
title: "DEAP DIVE: Dataset Investigation with Vision transformers for EEG evaluation"
authors: "Annemarie Hoffsommer; Helen Schneider; Svetlana Pavlitska; J. Marius Zöllner"
year: 2025
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2510.00725"
tier: 3
composite: 4.0
---

# DEAP DIVE: Dataset Investigation with Vision transformers for EEG evaluation

**Citation:** `HoffsommerEtAl2025` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2510.00725](https://arxiv.org/abs/2510.00725)
- **URL**: [http://arxiv.org/abs/2510.00725v1](http://arxiv.org/abs/2510.00725v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Accurately predicting emotions from brain signals has the potential to achieve goals such as improving mental health, human-computer interaction, and affective computing. Emotion prediction through neural signals offers a promising alternative to traditional methods, such as self-assessment and facial expression analysis, which can be subjective or ambiguous. Measurements of the brain activity via electroencephalogram (EEG) provides a more direct and unbiased data source. However, conducting a full EEG is a complex, resource-intensive process, leading to the rise of low-cost EEG devices with simplified measurement capabilities. This work examines how subsets of EEG channels from the DEAP dataset can be used for sufficiently accurate emotion prediction with low-cost EEG devices, rather than fully equipped EEG-measurements. Using Continuous Wavelet Transformation to convert EEG data into scaleograms, we trained a vision transformer (ViT) model for emotion classification. The model achieved over 91,57% accuracy in predicting 4 quadrants (high/low per arousal and valence) with only 12 measuring points (also referred to as channels). Our work shows clearly, that a significant reduction of input channels yields high results compared to state-of-the-art results of 96,9% with 32 channels. Training scripts to reproduce our code can be found here: https://gitlab.kit.edu/kit/aifb/ATKS/public/AutoSMiLeS/DEAP-DIVE.
