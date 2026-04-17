---
citation_key: "ZhouEtAl2026a"
paper_id: "paper_251"
title: "MuGEP: Multiplex Graph-Based Brain Network Modeling for Epileptic Seizure Prediction Using Intracranial EEG."
authors: "Minyu Zhou; Yajing Wu; Yongqiang Tang; Xiaohu Zhou; Ying Zhang; Runshi Gao; Wang Jia; Wensheng Zhang"
year: 2026
doi: "10.1109/jbhi.2026.3679376"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 3
composite: 4.0
---

# MuGEP: Multiplex Graph-Based Brain Network Modeling for Epileptic Seizure Prediction Using Intracranial EEG.

**Citation:** `ZhouEtAl2026a` · **Tier:** 3 · **Composite:** 4.0

- **DOI**: [10.1109/jbhi.2026.3679376](https://doi.org/10.1109/jbhi.2026.3679376)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41915533/](https://pubmed.ncbi.nlm.nih.gov/41915533/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Accurate seizure prediction in advance is crucial for patients with epilepsy, as it helps prevent harm and improve life quality. Intracranial electroencephalogram (iEEG), enabling precise characterization of epileptogenic and propagation networks from deep brain tissue, is a reliable foundation for epilepsy research. While deep learning models have shown success in automating seizure prediction, existing methods often overlook diverse brain network relationships and the rich information within each channel, thereby failing to fully exploit the advantages of iEEG signals. To address these issues, we propose a Multiplex Graph-based brain network modeling framework for Epileptic seizure Prediction (MuGEP) to represent the diverse and fine-grained relationships in the brain network effectively, involving the relationships between amplitude and phase of different frequency bands. Specifically, a specialized multiplex graph called the Multiplex Brain Graph (MBG) is designed for brain network connectivity, which is inspired by Cross-Frequency Coupling (CFC) in neuroscience. In MBG, nodes represent the frequency bands in each channel, and edges are computed following the idea of three types of CFC, resulting in three distinct subgraphs. Further, a novel MBG learning network is proposed to incorporate intra- and inter-subgraph patterns to obtain the final representation leveraging graph convolution networks and a joint fusion module. A sufficient evaluation is conducted on the Kaggle and the SWEC-ETHZ datasets, and the promising results confirm the advantage of MuGEP for iEEG seizure prediction.
