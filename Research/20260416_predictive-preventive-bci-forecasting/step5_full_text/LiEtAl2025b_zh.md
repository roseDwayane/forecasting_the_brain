---
citation_key: "LiEtAl2025b"
title_en: "Spatio-Temporal Attention Network for Epileptic Seizure Prediction"
title_zh: "癲癇發作預測之時空注意力網路"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Spatio-Temporal Attention Network for Epileptic Seizure Prediction | 癲癇發作預測之時空注意力網路

> [!abstract] 重點摘要 / Key Findings
> - 並行空間＋時序雙注意力機制
> - 可解釋性：注意力 heatmap 顯示關鍵通道／時段
> - CHB-MIT 競爭力效能
> - 對臨床醫師的模型可詮釋性具意義
>
> **完整英文版本 / Full English text:** [LiEtAl2025b.md](./LiEtAl2025b.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> In this study, we present a deep learning framework that learns complex spatio-temporal correlation structures of EEG signals through a Spatio-Temporal Attention Network (STAN) for accurate predictions of onset of seizures for Epilepsy patients. Unlike existing methods, which rely on feature engineering and/or assume fixed preictal durations, our approach simultaneously models spatio-temporal correlations through STAN and employs an adversarial discriminator to distinguish preictal from interictal attention patterns, enabling patient-specific learning. Evaluation on CHB-MIT and MSSM datasets demonstrates 96.6\% sensitivity with 0.011/h false detection rate on CHB-MIT, and 94.2% sensitivity with 0.063/h FDR on MSSM, significantly outperforming state-of-the-art methods. The framework reliably detects preictal states at least 15 minutes before an onset, with patient-specific windows extending to 45 minutes, providing sufficient intervention time for clinical applications.

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文設計 Spatio-Temporal Attention Network (STAN)，並行建模 EEG 通道間空間依賴與時序動態。空間注意力學習通道重要性加權，時序注意力捕捉關鍵時間片段。在 CHB-MIT 取得競爭力效能並提供可解釋之注意力 heatmap。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [LiEtAl2025b.md](./LiEtAl2025b.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
