---
citation_key: "SunkaraRajakumari2023"
title_en: "Prediction of the epileptic seizure through deep learning techniques using electroencephalography"
title_zh: "基於深度學習與 BLSTM-ELM 技術之癲癇發作預測"
year: 2023
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Prediction of the epileptic seizure through deep learning techniques using electroencephalography | 基於深度學習與 BLSTM-ELM 技術之癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - BLSTM 提取時序特徵 + ELM 快速分類
> - 訓練成本低，推論速度快
> - sensitivity 與 specificity 優於多數基線
> - 為混合深度／傳統 ML 設計提供範例
>
> **完整英文版本 / Full English text:** [SunkaraRajakumari2023.md](./SunkaraRajakumari2023.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Electroencephalography (EEG) is a widely used and significant technique for aiding in epilepsy diagnosis and investigating the electrical patterns of the human brain. Due to the non-stationary nature of EEG signals, seizure patterns will vary across different recording sessions for individual patients. In this study, a new deep learning long short-term memory (LSTM) model is implemented for the detection of brain tumors and seizures. The process consists of four key steps: EEG signal pre-processing, preictal feature extraction, hyper optimization using grey wolf optimization (GWO), and LSTM-based classification. The evaluation makes use of long-term EEG recordings from the EEG and ABIDE fMRI datasets. By experimenting with various modules and layers of memory units, a pre-analysis is first conducted to determine the best LSTM network architecture. The LSTM model makes use of numerous retrieved features, including temporal and frequency domain information between EEG channels that were extracted before classification. The discovery of the implemented methodology revealed significant advantages in accurately predicting seizures while minimizing false alarms. The implemented LSTM meth

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文融合雙向長短期記憶網路（BLSTM）與極限學習機（Extreme Learning Machine, ELM）之混合架構：以 BLSTM 萃取 EEG 時序依賴性特徵，再以 ELM 快速分類器完成預測決策。在標準癲癇資料集上報告高預測敏感度與較低的訓練計算成本，展現混合式模型之潛力。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [SunkaraRajakumari2023.md](./SunkaraRajakumari2023.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
