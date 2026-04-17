---
citation_key: "SuffianEtAl2025"
paper_id: "paper_155"
title: "An Explainable 3D-Deep Learning Model for EEG Decoding in Brain-Computer Interface Applications."
authors: "Muhammad Suffian; Cosimo Ieracitano; Francesco C Morabito; Nadia Mammone"
year: 2025
doi: "10.1142/s012906572550073x"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 4
composite: 3.7
---

# An Explainable 3D-Deep Learning Model for EEG Decoding in Brain-Computer Interface Applications.

**Citation:** `SuffianEtAl2025` · **Tier:** 4 · **Composite:** 3.7

- **DOI**: [10.1142/s012906572550073x](https://doi.org/10.1142/s012906572550073x)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41109958/](https://pubmed.ncbi.nlm.nih.gov/41109958/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Decoding electroencephalographic (EEG) signals is of key importance in the development of brain-computer interface (BCI) systems. However, high inter-subject variability in EEG signals requires user-specific calibration, which can be time-consuming and limit the application of deep learning approaches, due to general need of large amount of data to properly train these models. In this context, this paper proposes a multidimensional and explainable deep learning framework for fast and interpretable EEG decoding. In particular, EEG signals are projected into the spatial-spectral-temporal domain and processed using a custom three-dimensional (3D) Convolutional Neural Network, here referred to as EEGCubeNet. In this work, the method has been validated on EEGs recorded during motor BCI experiments. Namely, hand open (HO) and hand close (HC) movement planning was investigated by discriminating them from the absence of movement preparation (resting state, RE). The proposed method is based on a global- to subject-specific fine-tuning. The model is globally trained on a population of subjects and then fine-tuned on the final user, significantly reducing adaptation time. Experimental results demonstrate that EEGCubeNet achieves state-of-the-art performance (accuracy of [Formula: see text] and [Formula: see text] for HC versus RE and HO versus RE, binary classification tasks, respectively) with reduced framework complexity and with a reduced training time. In addition, to enhance transparency, a 3D occlusion sensitivity analysis-based explainability method (here named 3D xAI-OSA) that generates relevance maps revealing the most significant features to each prediction, was introduced. The data and source code are available at the following link: https://github.com/AI-Lab-UniRC/EEGCubeNet.
