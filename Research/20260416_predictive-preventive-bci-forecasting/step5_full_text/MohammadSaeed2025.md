---
citation_key: "MohammadSaeed2025"
paper_id: "paper_246"
title: "MLSPred-bench: Transforming electroencephalography (EEG) datasets into machine learning-ready epileptic seizure prediction benchmarks"
authors: "Umair Mohammad; Fahad Saeed"
year: 2025
doi: "10.1016/j.mex.2025.103574"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 2
composite: 4.2
---

# MLSPred-bench: Transforming electroencephalography (EEG) datasets into machine learning-ready epileptic seizure prediction benchmarks

**Citation:** `MohammadSaeed2025` · **Tier:** 2 · **Composite:** 4.2

- **DOI**: [10.1016/j.mex.2025.103574](https://doi.org/10.1016/j.mex.2025.103574)
- **URL**: [https://www.semanticscholar.org/paper/a32c824b087b480248fe84e278defb6d1ca77513](https://www.semanticscholar.org/paper/a32c824b087b480248fe84e278defb6d1ca77513)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Predicting epileptic seizures is a significantly more challenging task compared to seizure detection. However, most publicly available electroencephalography (EEG) datasets are geared towards detection because the ictal phase (main symptomatic period) is annotated. In contrast, prediction requires the availability of annotated preictal and interictal phases. To this end, we designed and developed a method called MLSPred-Bench that can be used for converting any EEG big data annotated for detection into ML-ready data suitable for prediction. We apply our methods to the existing EEG data corpus to generate 12 ML-ready benchmarks comprising data for training, validating, and testing seizure prediction models. Our strategy uses different variations of seizure prediction horizon (SPH) and the seizure occurrence period (SOP) to produce >150GB of ML-ready data. To illustrate the usefulness of the generated data, we technically validate all the benchmarks using multiple machine learning (ML) and deep learning (DL) models. We hope that the generated benchmarking data will be utilized by various computational groups for their seizure prediction model development. The work can be summarized as follows:1. Extract short preictal and interictal segments from long-duration annotated EEG montages.2. Generate a comprehensive list of ML-ready benchmarks with varying SPH and SOP.3. Technically validate the generated data with multiple ML and DL models with up-to 88.73 % validation accuracy4. Opensource code and related materials are available at https://github.com/pcdslab/MLSPred-Bench.
