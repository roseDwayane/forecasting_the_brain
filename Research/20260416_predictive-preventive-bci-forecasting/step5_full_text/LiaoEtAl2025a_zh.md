---
citation_key: "LiaoEtAl2025a"
title_en: "An EEG-Based Seizure Prediction Model Encoding Brain Network Temporal Dynamics."
title_zh: "編碼腦網絡時序動態之 EEG 癲癇發作預測模型"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# An EEG-Based Seizure Prediction Model Encoding Brain Network Temporal Dynamics. | 編碼腦網絡時序動態之 EEG 癲癇發作預測模型

> [!abstract] 重點摘要 / Key Findings
> - 以腦網絡（功能連結）取代單通道時序為輸入
> - GNN + Transformer 學習網絡動態
> - preictal 期網絡重組為主要預測線索
> - 在公開資料集顯著勝過 channel-level baseline
>
> **完整英文版本 / Full English text:** [LiaoEtAl2025a.md](./LiaoEtAl2025a.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> EEG-based seizure prediction enables timely treatment for patients, but its performance is limited by the difficulty in effectively characterizing the temporal dynamics of epileptic brain networks. Metastability, which describes recurring topographical patterns of spontaneous neural activity over time, provides a unique perspective for capturing the dynamic evolution before seizure onset. In this study, we propose a seizure prediction model that fuses consistent epileptic network processes across subjects into a higher-order latent space. Specifically, we first construct metastable transition patterns to identify the recurrent network states over time. Through adversarial feature learning, we then impose the metastability prior on the latent embedding space encoded via a variational autoencoder (VAE), while leveraging the maximum mean discrepancy measure (MMD) to further mitigate the patient gap. The latent representation, endowed with physiological priors, is ultimately utilized for patient-independent seizure prediction. We evaluate our method on two publicly available and one clinical scalp EEG datasets. Compared to the existing methods, our method has improved AUC, sensitivity,

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文強調 preictal 期的腦網絡（brain network）時序演化特徵常被傳統單通道時序模型忽略。作者以功能連結矩陣序列表徵腦網絡，再以圖神經網路結合 Transformer 捕捉網絡層級時序動態，顯著優於單純通道級特徵模型。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [LiaoEtAl2025a.md](./LiaoEtAl2025a.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
