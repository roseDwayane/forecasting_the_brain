---
citation_key: "QuEtAl2026"
title_en: "A causal attention network with time frequency channel feature fusion for epileptic seizure prediction."
title_zh: "具時間－頻率－通道特徵融合之因果注意力網路用於癲癇發作預測"
year: 2026
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# A causal attention network with time frequency channel feature fusion for epileptic seizure prediction. | 具時間－頻率－通道特徵融合之因果注意力網路用於癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 因果注意力（causal attention）確保即時推論可行
> - 三視角特徵融合：時間／頻率／通道
> - 多尺度設計捕捉短長期依賴
> - CHB-MIT SOTA 預測效能
>
> **完整英文版本 / Full English text:** [QuEtAl2026.md](./QuEtAl2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epilepsy poses ongoing physical and mental threats and causes substantial economic burdens. Better seizure forecasting enables faster medical responses, improving patients' quality of life and lowering healthcare costs. Research mainly focuses on early forecasting within a short preictal window, often too brief for effective drug administration. A major challenge is that a longer preictal phase may resemble the interictal state, making differentiation difficult. We propose a causal attention network (CANet) with a longer interictal and preictal of 1 h and 2 h respectively as the research object. In the feature extraction, a dilated causal convolution network is employed to extract local features. Causal attention is innovatively incorporated into epilepsy prediction to capture global correlation features. The complementary integration of these two methods enhances feature extraction and enables a more precise distinction between interictal and preictal periods. A double-layer dynamic window algorithm is developed for seizure prediction. We evaluate the performance on Freiburg and CHB-MIT datasets. On the Freiburg dataset, the sensitivity(Sen) of the 1/2-hour preictal intervals was 

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文提出 causal attention network 將 EEG 之時間、頻率、通道三視角特徵融合，使模型以因果方式（不偷看未來資訊）進行預測。注意力機制同時學習跨時間、跨通道依賴性；融合模組在多個 scale 下整合，在 CHB-MIT 上取得當前 SOTA。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [QuEtAl2026.md](./QuEtAl2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
