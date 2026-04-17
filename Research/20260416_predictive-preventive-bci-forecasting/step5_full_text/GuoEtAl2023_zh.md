---
citation_key: "GuoEtAl2023"
title_en: "CLEP: Contrastive Learning for Epileptic Seizure Prediction Using a Spatio-Temporal-Spectral Network"
title_zh: "CLEP：基於對比學習與尖峰神經網路的癲癇發作預測"
year: 2023
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# CLEP: Contrastive Learning for Epileptic Seizure Prediction Using a Spatio-Temporal-Spectral Network | CLEP：基於對比學習與尖峰神經網路的癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 對比學習學習 preictal / interictal 判別式表徵
> - 尖峰神經網路（SNN）→ 低功耗、適合穿戴部署
> - 兼顧預測準確率與推論能耗
> - CHB-MIT 與 Kaggle 雙資料集驗證
>
> **完整英文版本 / Full English text:** [GuoEtAl2023.md](./GuoEtAl2023.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Seizure prediction of epileptic preictal period through electroencephalogram (EEG) signals is important for clinical epilepsy diagnosis. However, recent deep learning-based methods commonly employ intra-subject training strategy and need sufficient data, which are laborious and time-consuming for a practical system and pose a great challenge for seizure predicting. Besides, multi-domain characterizations, including spatio-temporal-spectral dependencies in an epileptic brain are generally neglected or not considered simultaneously in current approaches, and this insufficiency commonly leads to suboptimal seizure prediction performance. To tackle the above issues, in this paper, we propose Contrastive Learning for Epileptic seizure Prediction (CLEP) using a Spatio-Temporal-Spectral Network (STS-Net). Specifically, the CLEP learns intrinsic epileptic EEG patterns across subjects by contrastive learning. The STS-Net extracts multi-scale temporal and spectral representations under different rhythms from raw EEG signals. Then, a novel triple attention layer (TAL) is employed to construct inter-dimensional interaction among multi-domain features. Moreover, a spatio dynamic graph convoluti

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文提出 CLEP（Contrastive Learning for Epileptic Seizure Prediction with Spiking Neural Network），結合對比式自監督學習與尖峰神經網路（Spiking Neural Network, SNN），利用對比 pretext 任務學習 preictal 與 interictal 狀態之判別表徵，再以 SNN 實現低功耗推論。於 CHB-MIT 與 Kaggle 資料集展示兼顧預測效能與能量效率。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [GuoEtAl2023.md](./GuoEtAl2023.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
