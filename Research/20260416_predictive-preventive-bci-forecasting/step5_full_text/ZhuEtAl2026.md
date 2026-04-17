---
citation_key: "ZhuEtAl2026"
paper_id: "paper_244"
title: "M3T-attention: a multi-level multi-scale temporal attention transformer for EEG hand movement trajectory decoding."
authors: "Lei Zhu; Peng Jiang; Aiai Huang; Jianhai Zhang; Peng Yuan"
year: 2026
doi: "10.1007/s11571-025-10403-1"
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
tier: 4
composite: 3.7
---

# M3T-attention: a multi-level multi-scale temporal attention transformer for EEG hand movement trajectory decoding.

**Citation:** `ZhuEtAl2026` · **Tier:** 4 · **Composite:** 3.7

- **DOI**: [10.1007/s11571-025-10403-1](https://doi.org/10.1007/s11571-025-10403-1)
- **URL**: [https://pubmed.ncbi.nlm.nih.gov/41647146/](https://pubmed.ncbi.nlm.nih.gov/41647146/)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

In recent years, brain-computer interface (BCI) technology has made significant progress in the fields of neural engineering and human-computer interaction. Among these advances, decoding upper-limb movements from electroencephalography (EEG) signals has become a key research focus. However, most existing studies concentrate on discrete classification tasks (e.g., motor imagery recognition), while the prediction of three-dimensional continuous movement trajectories still faces several major challenges. These include the low signal-to-noise ratio of EEG signals, substantial inter-subject variability that limits generalizability, and the high degrees of freedom in 3D trajectories, which increase decoding complexity. To address these challenges and improve the accuracy of decoding continuous 3D hand movement trajectories from EEG signals, this study proposes a Multi-level Multi-scale Temporal Attention Transformer framework (M3T-Attention). The model is designed to extract temporal features across multiple time scales from EEG signals and integrate them via cross-scale attention mechanisms, enabling a nonlinear mapping from 0.5 to 12 Hz EEG signals to 3D kinematic parameters (position, velocity, and acceleration). The model was trained using EEG and wrist kinematic data from the WAY-EEG-GAL dataset. Experimental results show that the proposed method achieves Pearson correlation coefficients (PCCs) of 0.8816, 0.8841, and 0.8711 on the X, Y, and Z axes, respectively, demonstrating robust prediction performance across all subjects and outperforming existing state-of-the-art approaches. In summary, through comparative experiments, statistical significance analysis, and ablation studies, we have fully verified its ability to capture neural coding patterns. It significantly enhances the decoding performance from EEG signals to movement trajectories, offering new approaches for BCI applications in complex motor control scenarios. We have made the model's source code publicly available on GitHub repository URL: https://github.com/jjspp/M3T_Attention.
