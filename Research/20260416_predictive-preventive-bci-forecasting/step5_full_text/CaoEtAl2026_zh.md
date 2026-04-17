---
citation_key: "CaoEtAl2026"
title_en: "Efficient and Accurate Epilepsy Seizure Prediction and Detection Based on Multi-Teacher Knowledge Distillation RGF-Model."
title_zh: "基於多教師知識蒸餾 RGF 模型的高效精準癲癇發作預測與偵測"
year: 2026
tier: 1
composite: 4.8
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Efficient and Accurate Epilepsy Seizure Prediction and Detection Based on Multi-Teacher Knowledge Distillation RGF-Model. | 基於多教師知識蒸餾 RGF 模型的高效精準癲癇發作預測與偵測

> [!abstract] 重點摘要 / Key Findings
> - 單一因果架構統一預測與偵測 / unified causal framework for prediction + detection
> - Ring-GRU + FiLM 達成任務自適應特徵調變 / adaptive task-specific conditioning
> - 多教師知識蒸餾 → 模型輕量化（僅 0.082M 參數）
> - CHB-MIT 99.54% AUC，0.01 FPR/h；可於穿戴裝置即時推論
>
> **完整英文版本 / Full English text:** [CaoEtAl2026.md](./CaoEtAl2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Epileptic seizures are unpredictable, and while existing deep learning models achieve high accuracy, their deployment on wearable devices is constrained by high computational costs and latency. To address this, this work proposes the RGF-Model, a lightweight network that unifies seizure prediction and detection within a single causal framework. By integrating Feature-wise Linear Modulation (FiLM) with a Ring-Buffer Gated Recurrent Unit (Ring-GRU), the model achieves adaptive task-specific feature conditioning while strictly enforcing causal consistency for real-time inference. A multi-teacher knowledge distillation strategy is employed to transfer complementary knowledge from complex teacher ensembles to the lightweight student, significantly reducing complexity without sacrificing accuracy. Evaluations on the CHB-MIT and Siena datasets demonstrate that the RGF-Model outperforms state-of-the-art teacher models in terms of efficiency while maintaining comparable accuracy. Specifically, on CHB-MIT, it achieves 99.54% Area Under the Curve (AUC) and 0.01 False Prediction Rate per hour (FPR/h) for prediction, and 98.78% Accuracy (Acc) for detection, with only 0.082 million parameters. S

> [!note] 翻譯摘要 (Traditional Chinese)
> 針對可穿戴裝置上深度學習癲癇預測模型的高計算成本問題，本文提出 RGF-Model 輕量架構，透過 FiLM 特徵調變與 Ring-GRU（環形緩衝門控循環單元）在單一因果框架中統一「預測」與「偵測」任務，並以多教師知識蒸餾將複雜教師集成的互補知識轉移至輕量學生模型。在 CHB-MIT 與 Siena 資料集上，以僅 0.082M 參數達到 99.54% AUC、0.01 FPR/h、98.78% 偵測準確率，展現實時可部署性。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.8 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [CaoEtAl2026.md](./CaoEtAl2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
