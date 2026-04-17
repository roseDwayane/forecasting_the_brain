---
citation_key: "RevathyM2025"
paper_id: "paper_179"
title: "Cross-modal privacy-preserving synthesis and mixture-of-experts ensemble for robust ASD prediction."
authors: "J Revathy; Karthiga M"
year: 2025
doi: "10.3389/fninf.2025.1679196"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 3
composite: 4.0
---

# Cross-modal privacy-preserving synthesis and mixture-of-experts ensemble for robust ASD prediction.

**Citation:** `RevathyM2025` · **Tier:** 3 · **Composite:** 4.0

- **DOI**: [10.3389/fninf.2025.1679196](https://doi.org/10.3389/fninf.2025.1679196)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41346493/](https://pubmed.ncbi.nlm.nih.gov/41346493/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Autism Spectrum Disorder (ASD) diagnosis remains complex due to limited access to large-scale multimodal datasets and privacy concerns surrounding clinical data. Traditional methods rely heavily on resource-intensive clinical assessments and are constrained by unimodal or non-adaptive learning models. To address these limitations, this study introduces AutismSynthGen, a privacy-preserving framework for synthesizing multimodal ASD data and enhancing prediction accuracy. The proposed system integrates a Multimodal Autism Data Synthesis Network (MADSN), which employs transformer-based encoders and cross-modal attention within a conditional GAN to generate synthetic data across structural MRI, EEG, behavioral vectors, and severity scores. Differential privacy is enforced via DP-SGD (ε ≤ 1.0). A complementary Adaptive Multimodal Ensemble Learning (AMEL) module, consisting of five heterogeneous experts and a gating network, is trained on both real and synthetic data. Evaluation is conducted on the ABIDE, NDAR, and SSC datasets using metrics such as AUC, F1 score, MMD, KS statistic, and BLEU. Synthetic augmentation improved model performance, yielding validation AUC gains of ≥ 0.04. AMEL achieved an AUC of 0.98 and an F1 score of 0.99 on real data and approached near-perfect internal performance (AUC ≈ 1.00, F1 ≈ 1.00) when synthetic data were included. Distributional metrics (MMD = 0.04; KS = 0.03) and text similarity (BLEU = 0.70) demonstrated high fidelity between the real and synthetic samples. Ablation studies confirmed the importance of cross-modal attention and entropy-regularized expert gating. AutismSynthGen offers a scalable, privacy-compliant solution for augmenting limited multimodal datasets and enhancing ASD prediction. Future directions include semi-supervised learning, explainable AI for clinical trust, and deployment in federated environments to broaden accessibility while maintaining privacy.
