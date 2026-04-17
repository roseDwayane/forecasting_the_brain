---
citation_key: "BaryMacq2024"
title_en: "Designing Pre-training Datasets from Unlabeled Data for EEG Classification with Transformers"
title_zh: "從未標記資料設計 EEG 分類 Transformer 之預訓練資料集"
year: 2024
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Designing Pre-training Datasets from Unlabeled Data for EEG Classification with Transformers | 從未標記資料設計 EEG 分類 Transformer 之預訓練資料集

> [!abstract] 重點摘要 / Key Findings
> - 三種可解釋自監督 pretext tasks 從未標記 EEG 建立資料集
> - MViT 於 TUSZ 癲癇預測
> - 微調時間縮短 >50%，accuracy +1.23%、AUC +0.0054
> - 為 EEG 大模型 pre-training 提供資料驅動方法論
>
> **完整英文版本 / Full English text:** [BaryMacq2024.md](./BaryMacq2024.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Transformer neural networks require a large amount of labeled data to train effectively. Such data is often scarce in electroencephalography, as annotations made by medical experts are costly. This is why self-supervised training, using unlabeled data, has to be performed beforehand. In this paper, we present a way to design several labeled datasets from unlabeled electroencephalogram (EEG) data. These can then be used to pre-train transformers to learn representations of EEG signals. We tested this method on an epileptic seizure forecasting task on the Temple University Seizure Detection Corpus using a Multi-channel Vision Transformer. Our results suggest that 1) Models pre-trained using our approach demonstrate significantly faster training times, reducing fine-tuning duration by more than 50% for the specific task, and 2) Pre-trained models exhibit improved accuracy, with an increase from 90.93% to 92.16%, as well as a higher AUC, rising from 0.9648 to 0.9702 when compared to non-pre-trained models.

> [!note] 翻譯摘要 (Traditional Chinese)
> Transformer 需大量標註資料；EEG 標註稀缺。本文提出三種直覺且可解釋的 pretext 任務（自監督目標）從未標記 EEG 設計「自標」預訓練資料集，接著以 Multi-channel Vision Transformer (MViT) 在 TUSZ 做癲癇預測。預訓練使微調時間縮短 50% 以上，準確率從 90.93% 提升至 92.16%、AUC 從 0.9648 至 0.9702。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [BaryMacq2024.md](./BaryMacq2024.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
