---
citation_key: "LiEtAl2025a"
paper_id: "paper_249"
title: "Memory-Efficient Intrinsic Gating Adaptation for Enhanced On-Device Epilepsy Diagnosis."
authors: "Shanjin Li; Di Wu; Shiqi Zhao; Jie Yang; Mohamad Sawan"
year: 2025
doi: "10.1109/jbhi.2025.3643602"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 3
composite: 4.0
---

# Memory-Efficient Intrinsic Gating Adaptation for Enhanced On-Device Epilepsy Diagnosis.

**Citation:** `LiEtAl2025a` · **Tier:** 3 · **Composite:** 4.0

- **DOI**: [10.1109/jbhi.2025.3643602](https://doi.org/10.1109/jbhi.2025.3643602)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41396749/](https://pubmed.ncbi.nlm.nih.gov/41396749/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Recently, advances in neuroscience and the rise of artificial intelligence have significantly enhanced the capabilities of epilepsy diagnosis. While EEG-based diagnosis offer a promising avenue for detecting and predicting seizure activity, practical implementation in real-world scenarios remains hindered by the heterogeneity of epilepsy and the variability of patient-specific biomarkers over time. Conventional deep learning models, trained on historical EEG, often fail to adapt to such biomarker variations, leading to degraded performance. Moreover, the computational and memory constraints of edge devices further exacerbate the challenge of on-device learning. To address these challenges, we introduce a novel framework, Memory-Efficient Intrinsic Gating Adaptation (MEIGA), designed to enhance real-world epilepsy diagnosis on resource-constrained edge devices. Our approach pre-trains a model using historical EEG data and employs lightweight adapter networks for efficient on-device tuning across new sessions, addressing session-to-session variability. By leveraging Direct Feedback Alignment (DFA), MEIGA reduces memory usage and computational overhead while maintaining high classification accuracy. Extensive experiments on the CHB-MIT epilepsy dataset demonstrate that MEIGA outperforms the pretrained-only Vision Transformer baseline, raising seizure prediction accuracy from 47.88% to 86.77% with only 3,908 tunable parameters (5.05% of the backbone). For seizure detection, MEIGA improves accuracy from 85.06% to 96.29% by adapting 2,008 parameters (17.40% of the base architecture). Further experiments on the AES dataset demonstrate that MEIGA consistently delivers strong performance across subjects and scales effectively to larger networks.
