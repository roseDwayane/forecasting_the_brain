---
citation_key: "WangEtAl2025b"
paper_id: "paper_219"
title: "Explainable End-to-End Seizure Prediction via Stationary Wavelet Transform-Driven Dynamic Multiscale Fuzzy Clustering."
authors: "Jie Wang; Yingchao Wang; Weiwei Nie; Qi Yuan"
year: 2025
doi: "10.1109/jbhi.2025.3633739"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 4
composite: 3.7
---

# Explainable End-to-End Seizure Prediction via Stationary Wavelet Transform-Driven Dynamic Multiscale Fuzzy Clustering.

**Citation:** `WangEtAl2025b` · **Tier:** 4 · **Composite:** 3.7

- **DOI**: [10.1109/jbhi.2025.3633739](https://doi.org/10.1109/jbhi.2025.3633739)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41259173/](https://pubmed.ncbi.nlm.nih.gov/41259173/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Epileptic seizure prediction holds critical clinical significance for enhancing the quality of life in patients. Despite technological advances, existing approaches face persistent challenges arising from inter-subject variability in electroencephalogram (EEG) dynamics and the complex spatiotemporal coupling associated with ictal transitions. These issues compromise both feature discriminability and model explainability. To address these dual limitations, we propose a novel stationary wavelet transform (SWT)-driven dynamic multiscale fuzzy clustering (SD-MFC) framework, an explainable prediction pipeline that integrates EEG signal analysis with transparent clinical decision-making. Methodologically, the spectral-temporal decomposition of EEG signals via SWT is combined with a geometric attention mechanism to model cross-channel dependencies. To capture the dynamic nature of EEG signals, we develop a Riemannian manifold-based fuzzy clustering algorithm through covariance matrix optimization and time-variant manifold metrics. Hierarchical feature fusion is achieved through multiscale convolutional kernels within a three-layer convolutional network. Model training incorporates contrastive learning with a hybrid supervised/self-supervised strategy to enhance robustness. Notably, two explainability methods: a joint feature visualization strategy and an efficient feature ablation study, are proposed to bridge the adaptation gap between the "black-box" nature of deep learning models and the requirements of clinical diagnostic. Experimental results on both intracranial and extracranial datasets demonstrate that SD-MFC framework not only exhibits superior predictive performance but also maintains a low FPR, offering a feasible scheme for clinical application of EEG-based seizure prediction. The code has been available at https://github.com/JW-Image/SD-MFC.
