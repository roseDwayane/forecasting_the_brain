---
citation_key: "AlarfajEtAl2025"
paper_id: "paper_184"
title: "Deep learning approaches for diagnosing seizure based on EEG signal analysis."
authors: "Mohammed Alarfaj; Muhammad Ali Zeb; Mosleh Hmoud Al-Adhaileh; Asma Abdulmana Alhamadi; Nadhem Ebrahim"
year: 2025
doi: "10.3389/fnhum.2025.1669919"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 3
composite: 4.0
---

# Deep learning approaches for diagnosing seizure based on EEG signal analysis.

**Citation:** `AlarfajEtAl2025` · **Tier:** 3 · **Composite:** 4.0

- **DOI**: [10.3389/fnhum.2025.1669919](https://doi.org/10.3389/fnhum.2025.1669919)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41311991/](https://pubmed.ncbi.nlm.nih.gov/41311991/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Epilepsy is diagnosed in about 1% of the world's population as a common brain disease. Timely prediction and detection of seizures can significantly improve the lives of epilepsy patients. The study has garnered considerable attention over recent years, particularly in the context of advanced computational methods. However, current seizure detection methods still face several limitations, including high inter-patient variability, noisy and non-stationary EEG signals, and the limited generalization ability of single deep learning (DL) models. This paper presents an Ensemble of Deep Transfer Learning (EDTL) models for personalized seizure detection. The technique combines ResNet and EfficientNet methods along with a customized two-Dimensional Convolutional Neural Network (2DCNN) method for patient-specific seizure detection using EEG data. Raw data from the recordings of seizure patients is transformed into EEG signals. Personalized sliding windows are used to extract and store spectrograms for the patients. Patient-specific features are extracted from individual records. EEG signals are normalized for consistent scaling. Short Time Fourier Transform (STFT) is then applied for continuous window slicing over short time intervals. To address the limitations above, the proposed EDTL framework integrates general-purpose pre trained models with a domain-specific custom 2DCNN to capture complementary features. This design improves robustness against noise, enhances adaptability to patient-specific variability, and achieves better generalization compared to individual models. The transformed data is then passed on to train and optimize the models independently and later combined into EDTL. A comparative evaluation is performed using standard evaluation metrics on two datasets, the CHB-MIT Scalp EEG Database and Turkish Epilepsy EEG Dataset. The proposed EDTL models are evaluated against the individual models on standard performance metrics, with the EDTL achieving the highest performance of 99.23% on the AUC.
