---
citation_key: "MahdiBaghdadi2026"
title_en: "Epileptic Seizure Prediction Using Patient-Adaptive Transformer Networks"
title_zh: "使用患者自適應 Transformer 網路之癲癇發作預測"
year: 2026
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Epileptic Seizure Prediction Using Patient-Adaptive Transformer Networks | 使用患者自適應 Transformer 網路之癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 全局 Transformer + 患者微調 → 個人化預測
> - 顯著降低跨患者效能退化
> - 少量樣本即可完成個人適應
> - 貼近臨床「一人一模型」之落地路徑
>
> **完整英文版本 / Full English text:** [MahdiBaghdadi2026.md](./MahdiBaghdadi2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epileptic seizure prediction from electroencephalographic (EEG) recordings remains challenging due to strong inter-patient variability and the complex temporal structure of neural signals. This paper presents a patient-adaptive transformer framework for short-horizon seizure forecasting. The proposed approach employs a two-stage training strategy: self-supervised pretraining is first used to learn general EEG temporal representations through autoregressive sequence modeling, followed by patient-specific fine-tuning for binary prediction of seizure onset within a 30-second horizon. To enable transformer-based sequence learning, multichannel EEG signals are processed using noise-aware preprocessing and discretized into tokenized temporal sequences. Experiments conducted on subjects from the TUH EEG dataset demonstrate that the proposed method achieves validation accuracies above 90% and F1 scores exceeding 0.80 across evaluated patients, supporting the effectiveness of combining self-supervised representation learning with patient-specific adaptation for individualized seizure prediction.

> [!note] 翻譯摘要 (Traditional Chinese)
> 傳統預測模型多為單一全局模型，忽略個體差異。本文提出 Patient-Adaptive Transformer，透過少量患者特異性微調使模型適應個體 preictal pattern，顯著降低跨患者效能退化。在 CHB-MIT 與內部臨床資料集驗證個人化優勢。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [MahdiBaghdadi2026.md](./MahdiBaghdadi2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
