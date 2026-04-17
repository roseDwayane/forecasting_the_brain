---
citation_key: "AbbasiEtAl2025"
title_en: "Edge-Enabled Pre-Ictal Activity Prediction Framework Using Geometric Deep Learning."
title_zh: "邊緣啟用之預發作活動預測框架：幾何深度學習方法"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Edge-Enabled Pre-Ictal Activity Prediction Framework Using Geometric Deep Learning. | 邊緣啟用之預發作活動預測框架：幾何深度學習方法

> [!abstract] 重點摘要 / Key Findings
> - 幾何深度學習（GNN）保留通道空間拓撲
> - 模型壓縮 → 邊緣即時推論
> - 平衡延遲／功耗／預測效能
> - 為穿戴式／植入式癲癇預測鋪路
>
> **完整英文版本 / Full English text:** [AbbasiEtAl2025.md](./AbbasiEtAl2025.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> We present an edge-enabled pre-ictal phase prediction framework for the epileptic seizure geometric deep learning technique. In particular, we utilized the Brain Network Transformer (BNT) for the EEG signals based pre-ictal activity prediction. The model analyzes EEG-based brain connectivity to detect pre-ictal state, offering an interpretable approach compared to traditional deep learning techniques. We present a performance comparative analysis of BNT with various existing techniques. Experimental results prove that BNT outperforms existing techniques. In particular, the BNT was evaluated on the CHB-MIT dataset and achieved an average and median accuracy score of 97.17% and 98.51%, respectively on test data with an average area under the receiver operating curve score of 0.99. Additionally, we benchmark the computational efficiency on an Nvidia Jetson Xavier NX edge device, where it has a mean inference time of 9.978 ms demonstrating suitability for real-time deployment on edge devices. The results highlight the potential of BNT for practical seizure prediction, improving patient outcomes through timely intervention.Clinical relevance- This study presents an efficient, real-time 

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文針對邊緣裝置（edge device）設計 preictal 預測框架，以幾何深度學習（graph-based）建模 EEG 通道之空間拓撲，並壓縮模型供邊緣即時推論。系統兼顧低延遲、低功耗與可接受的預測效能，適合穿戴式／植入式 BCI。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [AbbasiEtAl2025.md](./AbbasiEtAl2025.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
