---
citation_key: "TruongDelorme2025"
paper_id: "paper_181"
title: "Data Normalization Strategies for EEG Deep Learning"
authors: "Dung Truong; Arnaud Delorme"
year: 2025
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2506.22455"
tier: 4
composite: 3.7
---

# Data Normalization Strategies for EEG Deep Learning

**Citation:** `TruongDelorme2025` · **Tier:** 4 · **Composite:** 3.7

- **arXiv**: [2506.22455](https://arxiv.org/abs/2506.22455)
- **URL**: [http://arxiv.org/abs/2506.22455v1](http://arxiv.org/abs/2506.22455v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Normalization is a critical yet often overlooked component in the preprocessing pipeline for EEG deep learning applications. The rise of large-scale pretraining paradigms such as self-supervised learning (SSL) introduces a new set of tasks whose nature is substantially different from supervised training common in EEG deep learning applications. This raises new questions about optimal normalization strategies for the applicable task. In this study, we systematically evaluate the impact of normalization granularity (recording vs. window level) and scope (cross-channel vs. within-channel) on both supervised (age and gender prediction) and self-supervised (Contrastive Predictive Coding) tasks. Using high-density resting-state EEG from 2,836 subjects in the Healthy Brain Network dataset, we show that optimal normalization strategies differ significantly between training paradigms. Window-level within-channel normalization yields the best performance in supervised tasks, while minimal or cross-channel normalization at the window level is more effective for SSL. These results underscore the necessity of task-specific normalization choices and challenge the assumption that a universal normalization strategy can generalize across learning settings. Our findings provide practical insights for developing robust EEG deep learning pipelines as the field shifts toward large-scale, foundation model training.
