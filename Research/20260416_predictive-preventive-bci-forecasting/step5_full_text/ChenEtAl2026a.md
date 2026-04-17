---
citation_key: "ChenEtAl2026a"
paper_id: "paper_132"
title: "A Unified SPD Token Transformer Framework for EEG Classification: Systematic Comparison of Geometric Embeddings"
authors: "Chi-Sheng Chen; En-Jui Kuo; Guan-Ying Chen; Xinyu Zhang; Fan Zhang"
year: 2026
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2601.21521"
tier: 4
composite: 3.7
---

# A Unified SPD Token Transformer Framework for EEG Classification: Systematic Comparison of Geometric Embeddings

**Citation:** `ChenEtAl2026a` · **Tier:** 4 · **Composite:** 3.7

- **arXiv**: [2601.21521](https://arxiv.org/abs/2601.21521)
- **URL**: [http://arxiv.org/abs/2601.21521v1](http://arxiv.org/abs/2601.21521v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Spatial covariance matrices of EEG signals are Symmetric Positive Definite (SPD) and lie on a Riemannian manifold, yet the theoretical connection between embedding geometry and optimization dynamics remains unexplored. We provide a formal analysis linking embedding choice to gradient conditioning and numerical stability for SPD manifolds, establishing three theoretical results: (1) BWSPD's $\sqrtκ$ gradient conditioning (vs $κ$ for Log-Euclidean) via Daleckii-Kreĭn matrices provides better gradient conditioning on high-dimensional inputs ($d \geq 22$), with this advantage reducing on low-dimensional inputs ($d \leq 8$) where eigendecomposition overhead dominates; (2) Embedding-Space Batch Normalization (BN-Embed) approximates Riemannian normalization up to $O(\varepsilon^2)$ error, yielding $+26\%$ accuracy on 56-channel ERP data but negligible effect on 8-channel SSVEP data, matching the channel-count-dependent prediction; (3) bi-Lipschitz bounds prove BWSPD tokens preserve manifold distances with distortion governed solely by the condition ratio $κ$. We validate these predictions via a unified Transformer framework comparing BWSPD, Log-Euclidean, and Euclidean embeddings within identical architecture across 1,500+ runs on three EEG paradigms (motor imagery, ERP, SSVEP; 36 subjects). Our Log-Euclidean Transformer achieves state-of-the-art performance on all datasets, substantially outperforming classical Riemannian classifiers and recent SPD baselines, while BWSPD offers competitive accuracy with similar training time.
