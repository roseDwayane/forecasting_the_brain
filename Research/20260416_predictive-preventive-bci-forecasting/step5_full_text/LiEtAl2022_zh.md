---
citation_key: "LiEtAl2022"
title_en: "Seizure Detection and Prediction by Parallel Memristive Convolutional Neural Networks"
title_zh: "基於平行憶阻器卷積神經網路之癲癇發作偵測與預測"
year: 2022
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Seizure Detection and Prediction by Parallel Memristive Convolutional Neural Networks | 基於平行憶阻器卷積神經網路之癲癇發作偵測與預測

> [!abstract] 重點摘要 / Key Findings
> - Memristor in-memory computing → 超低功耗
> - 平行 CNN 架構同時偵測與預測
> - 邊緣／植入式部署之硬體協同設計
> - 為神經形態 BCI 硬體示範案例
>
> **完整英文版本 / Full English text:** [LiEtAl2022.md](./LiEtAl2022.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> During the past two decades, epileptic seizure detection and prediction algorithms have evolved rapidly. However, despite significant performance improvements, their hardware implementation using conventional technologies, such as Complementary Metal-Oxide-Semiconductor (CMOS), in power and area-constrained settings remains a challenging task; especially when many recording channels are used. In this paper, we propose a novel low-latency parallel Convolutional Neural Network (CNN) architecture that has between 2-2,800x fewer network parameters compared to State-Of-The-Art (SOTA) CNN architectures and achieves 5-fold cross validation accuracy of 99.84% for epileptic seizure detection, and 99.01% and 97.54% for epileptic seizure prediction, when evaluated using the University of Bonn Electroencephalogram (EEG), CHB-MIT and SWEC-ETHZ seizure datasets, respectively. We subsequently implement our network onto analog crossbar arrays comprising Resistive Random-Access Memory (RRAM) devices, and provide a comprehensive benchmark by simulating, laying out, and determining hardware requirements of the CNN component of our system. We parallelize the execution of convolution layer kernels on s

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文展示以憶阻器（memristor）平行 CNN 架構同時執行癲癇偵測與預測，將運算嵌入記憶體內，顯著降低功耗與延遲。憶阻器的 in-memory computing 特性使大量平行卷積可在同一晶片完成，適合未來植入式／穿戴式腦機介面系統。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [LiEtAl2022.md](./LiEtAl2022.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
