---
citation_key: "AlkhrijahEtAl2025"
title_en: "Feature fusion ensemble classification approach for epileptic seizure prediction using electroencephalographic bio-signals."
title_zh: "癲癇發作預測之特徵融合集成分類方法"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Feature fusion ensemble classification approach for epileptic seizure prediction using electroencephalographic bio-signals. | 癲癇發作預測之特徵融合集成分類方法

> [!abstract] 重點摘要 / Key Findings
> - 多視角特徵融合（時域／頻域／非線性）
> - 異質集成分類器軟投票
> - 泛化性與魯棒性優於單一模型
> - 為傳統 + 深度方法混合提供基線
>
> **完整英文版本 / Full English text:** [AlkhrijahEtAl2025.md](./AlkhrijahEtAl2025.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epilepsy is a neurological disorder in which patients experience recurrent seizures, with the frequency of occurrence more than twice a day, which highly affects a patient's life. In recent years, multiple researchers have proposed multiple machine learning and deep learning-based methods to predict the onset of seizures using electroencephalogram (EEG) signals before they occur; however, robust preprocessing to mitigate the effect of noise, channel selection to reduce dimensionality, and feature extraction remain challenges in accurate prediction. This study proposes a novel method for accurately predicting epileptic seizures. In the first step, a Butterworth filter is applied, followed by a wavelet and a Fourier transform for the denoising of EEG signals. A non-overlapping window of 15 s is selected to segment the EEG signals, and an optimal spatial filter is applied to reduce the dimensionality. Handcrafted features, including both time and frequency domains, have been extracted and concatenated with the customized one-dimensional convolutional neural network-based features to form a comprehensive feature vector. It is then fed into three classifiers, including support vector ma

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文提出多特徵融合 + 集成分類器（ensemble classifier）策略，結合時域、頻域、非線性特徵，並使用多個異質基分類器（SVM、RF、XGBoost、CNN）之軟投票提升泛化。在標準資料集展示勝過單一模型的 robust 效能。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [AlkhrijahEtAl2025.md](./AlkhrijahEtAl2025.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
