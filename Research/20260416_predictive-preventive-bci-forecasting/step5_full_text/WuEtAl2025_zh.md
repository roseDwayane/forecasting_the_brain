---
citation_key: "WuEtAl2025"
title_en: "A Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction"
title_zh: "EEG 癲癇發作預測之機器與深度學習趨勢綜述"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# A Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction | EEG 癲癇發作預測之機器與深度學習趨勢綜述

> [!abstract] 重點摘要 / Key Findings
> - 綜述傳統 ML → 深度學習之方法演進
> - 整合 CHB-MIT、TUSZ、Kaggle 等主要資料集效能
> - 辨識跨患者泛化與校準漂移為臨床轉譯瓶頸
> - 提供後續研究框架與評估指標建議
>
> **完整英文版本 / Full English text:** [WuEtAl2025.md](./WuEtAl2025.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epileptic seizures impair patients’ health and quality of life, and electroencephalography (EEG)-based prediction enables timely intervention. Early work on epileptic seizure prediction employed linear models, whereas recent studies employ more advanced machine learning and deep learning models. We review 149 studies (2018—May 2025), summarizing trends and gaps across the full pipeline in EEG-based epileptic seizure prediction. We find that four persistent challenges related to this domain remain. First, severe dataset imbalance, with overreliance on Children’s Hospital Boston–Massachusetts Institute of Technology EEG dataset (CHB-MIT), minimal use of intracranial electroencephalography (iEEG) datasets, and infrequent integration of public and private datasets. Second, preprocessing practices remain rigid, often involving segmentation into windows of 10 s or less, fixed preictal horizons of 30 to 60 min, basic filtering and undersampling procedures. Third, limited model diversity, as most studies use convolutional neural networks (CNNs), with scant exploration of Transformers or graph neural networks (GNNs), dimensionality reduction is predominantly implicit and few linear baseline

> [!note] 翻譯摘要 (Traditional Chinese)
> 本綜述系統性回顧近年 EEG 癲癇發作預測文獻，涵蓋傳統特徵工程（頻譜、非線性動力學）到深度學習（CNN、RNN、Transformer）之方法演進。歸納各代表性資料集（CHB-MIT、TUSZ、Kaggle）效能，並剖析臨床轉譯之挑戰如跨患者泛化、校準漂移、false alarm rate 等。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [WuEtAl2025.md](./WuEtAl2025.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
