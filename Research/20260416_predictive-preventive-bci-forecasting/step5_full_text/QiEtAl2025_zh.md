---
citation_key: "QiEtAl2025"
title_en: "A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures Using EEG Signals."
title_zh: "基於對比學習強化殘差網路的癲癇發作預測"
year: 2025
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures Using EEG Signals. | 基於對比學習強化殘差網路的癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 自監督對比學習 pre-training 解決標註稀缺
> - ResNet 骨幹支援深層特徵抽取
> - CHB-MIT 高 sensitivity、低 FPR
> - 可延伸至 semi-supervised 臨床場景
>
> **完整英文版本 / Full English text:** [QiEtAl2025.md](./QiEtAl2025.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> The models used to predict epileptic seizures based on electroencephalogram (EEG) signals often encounter substantial challenges due to the requirement for large, labeled datasets and the inherent complexity of EEG data, which hinders their robustness and generalization capability. This study proposes CLResNet, a framework for predicting epileptic seizures, which combines contrastive self-supervised learning with a modified deep residual neural network to address the above challenges. In contrast to traditional models, CLResNet uses unlabeled EEG data for pre-training to extract robust feature representations. It is then fine-tuned on a smaller labeled dataset to significantly reduce its reliance on labeled data while improving its efficiency and predictive accuracy. The contrastive learning (CL) framework enhances the ability of the model to distinguish between preictal and interictal states, thus improving its robustness and generalizability. The architecture of CLResNet contains residual connections that enable it to learn deep features of the data and ensure an efficient gradient flow. The results of the evaluation of the model on the CHB-MIT dataset showed that it outperformed

> [!note] 翻譯摘要 (Traditional Chinese)
> 本文結合對比學習與殘差卷積網路（ResNet），以自監督對比目標 pre-train 編碼器，再微調於 preictal vs. interictal 分類任務。對比學習強化表徵之判別性，殘差結構支援更深層特徵擷取。在 CHB-MIT 上顯著降低 FPR 並提升 sensitivity。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [QiEtAl2025.md](./QiEtAl2025.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
