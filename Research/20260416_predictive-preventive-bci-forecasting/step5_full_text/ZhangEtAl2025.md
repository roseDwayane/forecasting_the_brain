---
citation_key: "ZhangEtAl2025"
paper_id: "paper_174"
title: "Constraint-Driven Causal Representation Learning for Vigilance Robust Estimation in Brain-Computer Interface."
authors: "Xuan Zhang; Wang Zheng; Zhigang Li; Yi Yang; Weijia Liu; Hongxin Cai; Junru Zhu; Jingyu Liu; Bin Hu; Qunxi Dong"
year: 2025
doi: "10.1109/tnnls.2025.3594434"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 3
composite: 3.9
---

# Constraint-Driven Causal Representation Learning for Vigilance Robust Estimation in Brain-Computer Interface.

**Citation:** `ZhangEtAl2025` · **Tier:** 3 · **Composite:** 3.9

- **DOI**: [10.1109/tnnls.2025.3594434](https://doi.org/10.1109/tnnls.2025.3594434)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/40811166/](https://pubmed.ncbi.nlm.nih.gov/40811166/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Vigilance estimation is a critical task within the field of brain-computer interfaces, extensively applied in monitoring and optimizing user states during human-machine interaction using electroencephalography (EEG). However, most existing vigilance prediction frameworks are prone to spurious correlations stemming from inherent biases in collected data. These biases involve relevant but vigilance-independent information, which may lack robustness when applied to different data distributions, i.e., out-of-distribution (OOD) scenarios. The core idea of this study is to learn constraints that capture causal information from the input based on the assumed underlying data generating process. Leveraging the disentanglement and invariance principles behind the assumptions, we propose a constraint-driven causal representation learning (CCRL) to identify and separate spurious latent variables from biased training data for generalized vigilance estimation. The CCRL training process consists of two phases: self-supervised pretraining and constraint-driven causal information disentanglement. In the first phase, based on the masked autoencoder (MAE) architecture, unlabeled training data are used for reconstructing pretext tasks to capture the comprehensive and intrinsic contextual information from EEG data, which provides a powerful input for downstream disentanglement learning. In the second phase, we propose a novel disentanglement strategy to learn spurious-free latent representations causally related to the vigilance state driven by adversarial and invariance constraints. Comprehensive validation experiments conducted on two well-known public datasets demonstrate the effectiveness and superiority of the proposed framework. In general, this work has promising implications for addressing OOD challenges in vigilance estimation.
