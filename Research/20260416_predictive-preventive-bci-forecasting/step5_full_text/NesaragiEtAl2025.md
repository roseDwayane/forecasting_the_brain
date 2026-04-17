---
citation_key: "NesaragiEtAl2025"
paper_id: "paper_166"
title: "Biaxialformer: Leveraging Channel Independence and Inter-Channel Correlations in EEG Signal Decoding for Predicting Neurological Outcomes"
authors: "Naimahmed Nesaragi; Hemin Ali Qadir; Per Steiner Halvorsen; Ilangko Balasingham"
year: 2025
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2507.02879"
tier: 3
composite: 4.0
---

# Biaxialformer: Leveraging Channel Independence and Inter-Channel Correlations in EEG Signal Decoding for Predicting Neurological Outcomes

**Citation:** `NesaragiEtAl2025` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2507.02879](https://arxiv.org/abs/2507.02879)
- **URL**: [http://arxiv.org/abs/2507.02879v1](http://arxiv.org/abs/2507.02879v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Accurate decoding of EEG signals requires comprehensive modeling of both temporal dynamics within individual channels and spatial dependencies across channels. While Transformer-based models utilizing channel-independence (CI) strategies have demonstrated strong performance in various time series tasks, they often overlook the inter-channel correlations that are critical in multivariate EEG signals. This omission can lead to information degradation and reduced prediction accuracy, particularly in complex tasks such as neurological outcome prediction. To address these challenges, we propose Biaxialformer, characterized by a meticulously engineered two-stage attention-based framework. This model independently captures both sequence-specific (temporal) and channel-specific (spatial) EEG information, promoting synergy and mutual reinforcement across channels without sacrificing CI. By employing joint learning of positional encodings, Biaxialformer preserves both temporal and spatial relationships in EEG data, mitigating the interchannel correlation forgetting problem common in traditional CI models. Additionally, a tokenization module with variable receptive fields balance the extraction of fine-grained, localized features and broader temporal dependencies. To enhance spatial feature extraction, we leverage bipolar EEG signals, which capture inter-hemispheric brain interactions, a critical but often overlooked aspect in EEG analysis. Our study broadens the use of Transformer-based models by addressing the challenge of predicting neurological outcomes in comatose patients. Using the multicenter I-CARE data from five hospitals, we validate the robustness and generalizability of Biaxialformer with an average AUC 0.7688, AUPRC 0.8643, and F1 0.6518 in a cross-hospital scenario.
