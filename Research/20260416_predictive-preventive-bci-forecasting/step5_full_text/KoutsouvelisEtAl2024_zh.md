---
citation_key: "KoutsouvelisEtAl2024"
title_en: "Preictal period optimization for deep learning-based epileptic seizure prediction"
title_zh: "深度學習型癲癇發作預測之 preictal 期長度最佳化研究"
year: 2024
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Preictal period optimization for deep learning-based epileptic seizure prediction | 深度學習型癲癇發作預測之 preictal 期長度最佳化研究

> [!abstract] 重點摘要 / Key Findings
> - 質疑固定 preictal 長度的普遍假設
> - 資料驅動選擇 patient-specific preictal window
> - CHB-MIT 顯著提升 sensitivity，降低 FPR
> - 對後續個人化預測模型具方法論意義
>
> **完整英文版本 / Full English text:** [KoutsouvelisEtAl2024.md](./KoutsouvelisEtAl2024.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Objective. Accurate seizure prediction could prove critical for improving patient safety and quality of life in drug-resistant epilepsy. While deep learning-based approaches have shown promising performance using scalp electroencephalogram (EEG) signals, the incomplete understanding and variability of the preictal state imposes challenges in identifying the optimal preictal period (OPP) for labeling the EEG segments. This study introduces novel measures to capture model behavior under different preictal definitions and proposes a data-centric deep learning methodology to identify the OPP. Approach. We trained a competent subject-specific CNN-Transformer model to detect preictal EEG segments using the open-access CHB-MIT dataset. To capture the temporal dynamics of the model’s predictions, we fitted a sigmoidal curve to the model outputs obtained from uninterrupted multi-hour EEG recordings prior to seizure onset. From this fitted curve, we derived key performance measures reflecting the timing of predictions, including classifier convergence, average error, output stability, and the transition between interictal and preictal states. These measures were then combined to compute the 

> [!note] 翻譯摘要 (Traditional Chinese)
> 不同患者 preictal（發作前期）長度差異顯著，常見以固定時間窗可能降低預測效能。本文系統性探討以患者特異性 preictal 長度調整深度學習模型訓練之影響，提出資料驅動的 preictal 窗口選擇策略，在 CHB-MIT 上顯著提升敏感度並降低 false prediction rate。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [KoutsouvelisEtAl2024.md](./KoutsouvelisEtAl2024.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
