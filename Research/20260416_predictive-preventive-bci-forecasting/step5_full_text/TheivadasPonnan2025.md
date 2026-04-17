---
citation_key: "TheivadasPonnan2025"
paper_id: "paper_189"
title: "Deep-ATM DL-LSTM: A novel adaptive thresholding model with dual-layer LSTM architecture for real-time driver drowsiness detection using skin conductance signals."
authors: "J Robert Theivadas; Suresh Ponnan"
year: 2025
doi: "10.1016/j.compbiomed.2025.110243"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 4
composite: 3.5
---

# Deep-ATM DL-LSTM: A novel adaptive thresholding model with dual-layer LSTM architecture for real-time driver drowsiness detection using skin conductance signals.

**Citation:** `TheivadasPonnan2025` · **Tier:** 4 · **Composite:** 3.5

- **DOI**: [10.1016/j.compbiomed.2025.110243](https://doi.org/10.1016/j.compbiomed.2025.110243)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/40273820/](https://pubmed.ncbi.nlm.nih.gov/40273820/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Driver drowsiness detection systems are crucial for road safety. However, existing machine learning models struggle to adjust thresholds for Skin Conductance (SC) adaptively signals due to insufficient feature extraction of tonic and phasic responses. These responses, controlled by the sympathetic nervous system, provide valuable insights into drowsiness states but are often distorted by signal noise, reducing detection accuracy. This study proposes a novel Deep learning-based Adaptive Thresholding Model with a Dual-layer Long Short-Term Memory (LSTM) architecture, called Deep-ATM DL-LSTM, to process SC signals and dynamically improve drowsiness detection. The model leverages a two-layer LSTM architecture to compute dynamic thresholds for tonic (baseline) and phasic (rapid fluctuation) responses. The first LSTM layer extracts global and regional SC features, while the second layer processes temporal differences in drowsiness states. A softmax layer classifies drowsiness levels based on feature vector differences. The proposed method effectively addresses inter-individual variability and signal distortions by integrating robust feature extraction and adaptive thresholding, ensuring accurate drowsiness detection. Experimental testing using professional drivers on highways, in urban areas, during the day and night and in rain and frost environments demonstrated a 96.4 % accuracy level and a 0.978 AUC-ROC value that surpassed standard machine learning techniques and standard LSTM models. Existing driving conditions that include rain and frost conditions do not affect model performance (94.2 % in rain, 93.5 % in frost) and the model achieves high F1-scores for drowsiness state identification in all alert states (0.978), mild states (0.954), modest states (0.938), and acute states (0.933). The Deep-ATM DL-LSTM system detects drowsiness early by 7.5 min before dangerous levels and needs minimal wearable sensors. The combination of high accuracy, adaptive features and practical deployment from this approach solves significant problems with existing driver monitoring systems, including Behavioural-based detection PERCLOS [9] and Physiological-based detection EEG and EMG signals [4], before delivering an effective tool to reduce drowsiness-caused road accidents.
