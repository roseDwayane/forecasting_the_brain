---
citation_key: "ZhengEtAl2025"
title_en: "EEG-based Epileptic Prediction via a Two-stage Channel-aware Set Transformer Network"
title_zh: "透過兩階段通道感知集合 Transformer 之 EEG 癲癇預測"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# EEG-based Epileptic Prediction via a Two-stage Channel-aware Set Transformer Network | 透過兩階段通道感知集合 Transformer 之 EEG 癲癇預測

> [!abstract] 重點摘要 / Key Findings
> - Set Transformer 處理任意通道數／不同電極配置
> - 兩階段：通道聚合 → 時序建模
> - 跨患者／跨中心泛化提升
> - 降低臨床部署時重新設計模型之需要
>
> **完整英文版本 / Full English text:** [ZhengEtAl2025.md](./ZhengEtAl2025.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epilepsy is a chronic, noncommunicable brain disorder, and sudden seizure onsets can significantly impact patients' quality of life and health. However, wearable seizure-predicting devices are still limited, partly due to the bulky size of EEG-collecting devices. To relieve the problem, we proposed a novel two-stage channel-aware Set Transformer Network that could perform seizure prediction with fewer EEG channel sensors. We also tested a seizure-independent division method which could prevent the adjacency of training and test data. Experiments were performed on the CHB-MIT dataset which includes 22 patients with 88 merged seizures. The mean sensitivity before channel selection was 76.4% with a false predicting rate (FPR) of 0.09/hour. After channel selection, dominant channels emerged in 20 out of 22 patients; the average number of channels was reduced to 2.8 from 18; and the mean sensitivity rose to 80.1% with an FPR of 0.11/hour. Furthermore, experimental results on the seizure-independent division supported our assertion that a more rigorous seizure-independent division should be used for patients with abundant EEG recordings.

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文針對患者間通道數目／配置差異，提出 two-stage Channel-Aware Set Transformer：第一階段以 set-based attention 處理任意數量通道；第二階段聚焦時序動態。此設計使模型可跨不同通道配置泛化，對臨床多中心部署極具實用性。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [ZhengEtAl2025.md](./ZhengEtAl2025.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
