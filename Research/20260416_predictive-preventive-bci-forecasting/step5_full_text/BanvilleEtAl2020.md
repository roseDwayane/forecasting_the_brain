---
citation_key: "BanvilleEtAl2020"
paper_id: "paper_312"
title: "Uncovering the structure of clinical EEG signals with self-supervised learning"
authors: "Hubert Banville; Omar Chehab; Aapo Hyvärinen; Denis-Alexander Engemann; Alexandre Gramfort"
year: 2020
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2007.16104"
tier: 3
composite: 4.0
---

# Uncovering the structure of clinical EEG signals with self-supervised learning

**Citation:** `BanvilleEtAl2020` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2007.16104](https://arxiv.org/abs/2007.16104)
- **URL**: [http://arxiv.org/abs/2007.16104v1](http://arxiv.org/abs/2007.16104v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Objective. Supervised learning paradigms are often limited by the amount of labeled data that is available. This phenomenon is particularly problematic in clinically-relevant data, such as electroencephalography (EEG), where labeling can be costly in terms of specialized expertise and human processing time. Consequently, deep learning architectures designed to learn on EEG data have yielded relatively shallow models and performances at best similar to those of traditional feature-based approaches. However, in most situations, unlabeled data is available in abundance. By extracting information from this unlabeled data, it might be possible to reach competitive performance with deep neural networks despite limited access to labels. Approach. We investigated self-supervised learning (SSL), a promising technique for discovering structure in unlabeled data, to learn representations of EEG signals. Specifically, we explored two tasks based on temporal context prediction as well as contrastive predictive coding on two clinically-relevant problems: EEG-based sleep staging and pathology detection. We conducted experiments on two large public datasets with thousands of recordings and performed baseline comparisons with purely supervised and hand-engineered approaches. Main results. Linear classifiers trained on SSL-learned features consistently outperformed purely supervised deep neural networks in low-labeled data regimes while reaching competitive performance when all labels were available. Additionally, the embeddings learned with each method revealed clear latent structures related to physiological and clinical phenomena, such as age effects. Significance. We demonstrate the benefit of self-supervised learning approaches on EEG data. Our results suggest that SSL may pave the way to a wider use of deep learning models on EEG data.
