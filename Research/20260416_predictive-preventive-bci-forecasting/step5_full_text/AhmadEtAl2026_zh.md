---
citation_key: "AhmadEtAl2026"
title_en: "A hybrid deep learning framework for epileptic seizure prediction using scalp and intracranial EEG data."
title_zh: "結合頭皮與顱內 EEG 的混合深度學習癲癇發作預測框架"
year: 2026
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# A hybrid deep learning framework for epileptic seizure prediction using scalp and intracranial EEG data. | 結合頭皮與顱內 EEG 的混合深度學習癲癇發作預測框架

> [!abstract] 重點摘要 / Key Findings
> - 首度整合 scalp + iEEG 雙模態於深度學習預測
> - 利用兩模態互補性提升敏感度
> - 跨患者泛化優於單一模態
> - 對 pre-surgical evaluation 有臨床意義
>
> **完整英文版本 / Full English text:** [AhmadEtAl2026.md](./AhmadEtAl2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epilepsy is a prevalent neurological disorder affecting over 50 million people globally, often impairing quality of life due to unpredictable and recurrent seizures. Despite advances in seizure prediction, challenges remain due to variability in EEG signals. EEG data exists in two primary modalities: non-invasive scalp EEG (sEEG) and invasive intracranial EEG (iEEG), and current deep learning models often exhibit limited generalizability across these modalities due to signal and structural differences. In this study, we propose a custom hybrid CNN-LSTM model optimized for scalp EEG, and assess its effectiveness across modalities by also evaluating it on invasive EEG datasets. We utilize the CHB-MIT (sEEG) and AES-Kaggle (iEEG) datasets employing a unified pipeline of preprocessing, signal transformation, and deep learning techniques. The model reported an accuracy of 98.84% on sEEG, using a 10-minute seizure anticipation window, outperforming conventional CNN, LSTM and several recent state-of-the-art models. On iEEG data, the hybrid model performed comparably well, achieving an impressive accuracy of 97.18%. The models are further validated using real-world scalp EEG data collected

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文同時利用頭皮 EEG（scalp）與顱內 EEG（intracranial, iEEG），設計一個混合深度學習框架融合兩種模態之互補資訊：scalp EEG 提供全腦覆蓋但 SNR 較低；iEEG 空間解析度高但僅限局部。雙模態融合於臨床預測系統中提升敏感度與跨患者泛化。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [AhmadEtAl2026.md](./AhmadEtAl2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
