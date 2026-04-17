---
citation_key: "ZhouEtAl2026b"
paper_id: "paper_281"
title: "Preventing Data Leakage in EEG-Based Survival Prediction: A Two-Stage Embedding and Transformer Framework"
authors: "Yixin Zhou; Zhixiang Liu; Vladimir I. Zadorozhny; Jonathan Elmer"
year: 2026
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2603.25923"
tier: 3
composite: 4.0
---

# Preventing Data Leakage in EEG-Based Survival Prediction: A Two-Stage Embedding and Transformer Framework

**Citation:** `ZhouEtAl2026b` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2603.25923](https://arxiv.org/abs/2603.25923)
- **URL**: [http://arxiv.org/abs/2603.25923v1](http://arxiv.org/abs/2603.25923v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Deep learning models have shown promise in EEG-based outcome prediction for comatose patients after cardiac arrest, but their reliability is often compromised by subtle forms of data leakage. In particular, when long EEG recordings are segmented into short windows and reused across multiple training stages, models may implicitly encode and propagate label information, leading to overly optimistic validation performance and poor generalization. In this study, we identify a previously overlooked form of data leakage in multi-stage EEG modeling pipelines. We demonstrate that violating strict patient-level separation can significantly inflate validation metrics while causing substantial degradation on independent test data. To address this issue, we propose a leakage-aware two-stage framework. In the first stage, short EEG segments are transformed into embedding representations using a convolutional neural network with an ArcFace objective. In the second stage, a Transformer-based model aggregates these embeddings to produce patient-level predictions, with strict isolation between training cohorts to eliminate leakage pathways. Experiments on a large-scale EEG dataset of post-cardiac-arrest patients show that the proposed framework achieves stable and generalizable performance under clinically relevant constraints, particularly in maintaining high sensitivity at stringent specificity thresholds. These results highlight the importance of rigorous data partitioning and provide a practical solution for reliable EEG-based outcome prediction.
