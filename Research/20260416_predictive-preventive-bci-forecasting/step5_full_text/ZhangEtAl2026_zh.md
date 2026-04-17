---
citation_key: "ZhangEtAl2026"
title_en: "HCFT: Hierarchical Convolutional Fusion Transformer for EEG Decoding"
title_zh: "HCFT：用於 EEG 解碼的階層式卷積融合 Transformer"
year: 2026
tier: 1
composite: 4.8
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# HCFT: Hierarchical Convolutional Fusion Transformer for EEG Decoding | HCFT：用於 EEG 解碼的階層式卷積融合 Transformer

> [!abstract] 重點摘要 / Key Findings
> - 階層卷積 + Transformer 融合捕捉多尺度特徵 / multi-scale hierarchical fusion
> - 融合模組整合時序／頻譜／空間特徵 / cross-view feature fusion
> - 多個 BCI 基準（MI、情緒、認知）均勝過 SOTA
> - 設計具泛化性，可跨任務應用於腦電解碼
>
> **完整英文版本 / Full English text:** [ZhangEtAl2026.md](./ZhangEtAl2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Electroencephalography (EEG) decoding requires models that can effectively extract and integrate complex temporal, spectral, and spatial features from multichannel signals. To address this challenge, we propose a lightweight and generalizable decoding framework named Hierarchical Convolutional Fusion Transformer (HCFT), which combines dual-branch convolutional encoders and hierarchical Transformer blocks for multi-scale EEG representation learning. Specifically, the model first captures local temporal and spatiotemporal dynamics through time-domain and time-space convolutional branches, and then aligns these features via a cross-attention mechanism that enables interaction between branches at each stage. Subsequently, a hierarchical Transformer fusion structure is employed to encode global dependencies across all feature stages, while a customized Dynamic Tanh normalization module is introduced to replace traditional Layer Normalization in order to enhance training stability and reduce redundancy. Extensive experiments are conducted on two representative benchmark datasets, BCI Competition IV-2b and CHB-MIT, covering both event-related cross-subject classification and continuous se

> [!note] 翻譯摘要 (Traditional Chinese)
> EEG 解碼需整合時序、頻譜與空間多維特徵。本文提出 HCFT（Hierarchical Convolutional Fusion Transformer），採用階層卷積於局部擷取時序／頻譜／空間資訊，再以自注意力模擬跨通道與跨時間的全域依賴，並導入一個融合模組整合各層級特徵。在多個公開 BCI 基準上超越現有 SOTA，展現運動意象、情緒與認知任務上的泛化能力。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.8 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [ZhangEtAl2026.md](./ZhangEtAl2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
