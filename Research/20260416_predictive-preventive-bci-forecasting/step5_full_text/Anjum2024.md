---
citation_key: "Anjum2024"
paper_id: "paper_242"
title: "LiPCoT: Linear Predictive Coding based Tokenizer for Self-supervised Learning of Time Series Data via Language Models"
authors: "Md Fahim Anjum"
year: 2024
doi: ""
source: "abstract-only (metadata from Step 2 search)"
access_level: "abstract-only"
retrieved_date: "2026-04-16"
arxiv_id: "2408.07292"
tier: 3
composite: 4.0
---

# LiPCoT: Linear Predictive Coding based Tokenizer for Self-supervised Learning of Time Series Data via Language Models

**Citation:** `Anjum2024` · **Tier:** 3 · **Composite:** 4.0

- **arXiv**: [2408.07292](https://arxiv.org/abs/2408.07292)
- **URL**: [http://arxiv.org/abs/2408.07292v1](http://arxiv.org/abs/2408.07292v1)

> **Note / 備註:** Full text not fetched in this pipeline run — only Tier 1 PDFs were provided by the user. Abstract shown below (from Step 2 search metadata). For full text, try institutional access via DOI.
> 本次流程僅處理使用者提供的 Tier 1 PDF。以下為 Step 2 搜尋階段擷取之摘要。如需全文請透過 DOI 嘗試機構存取。

## Abstract

Language models have achieved remarkable success in various natural language processing tasks. However, their application to time series data, a crucial component in many domains, remains limited. This paper proposes LiPCoT (Linear Predictive Coding based Tokenizer for time series), a novel tokenizer that encodes time series data into a sequence of tokens, enabling self-supervised learning of time series using existing Language model architectures such as BERT. Unlike traditional time series tokenizers that rely heavily on CNN encoder for time series feature generation, LiPCoT employs stochastic modeling through linear predictive coding to create a latent space for time series providing a compact yet rich representation of the inherent stochastic nature of the data. Furthermore, LiPCoT is computationally efficient and can effectively handle time series data with varying sampling rates and lengths, overcoming common limitations of existing time series tokenizers. In this proof-of-concept work, we present the effectiveness of LiPCoT in classifying Parkinson's disease (PD) using an EEG dataset from 46 participants. In particular, we utilize LiPCoT to encode EEG data into a small vocabulary of tokens and then use BERT for self-supervised learning and the downstream task of PD classification. We benchmark our approach against several state-of-the-art CNN-based deep learning architectures for PD detection. Our results reveal that BERT models utilizing self-supervised learning outperformed the best-performing existing method by 7.1% in precision, 2.3% in recall, 5.5% in accuracy, 4% in AUC, and 5% in F1-score highlighting the potential for self-supervised learning even on small datasets. Our work will inform future foundational models for time series, particularly for self-supervised learning.
