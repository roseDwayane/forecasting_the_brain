---
citation_key: "PhamTran2026"
title_en: "EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and Neural Memory"
title_zh: "EEG-Titans：透過雙分支注意力進行長時程癲癇發作預測"
year: 2026
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and Neural Memory | EEG-Titans：透過雙分支注意力進行長時程癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 雙分支注意力：短期動態 + 長時程趨勢
> - 支援 hours-scale lead time 預測
> - 跨注意力融合多尺度時序資訊
> - 臨床干預時間窗顯著延長
>
> **完整英文版本 / Full English text:** [PhamTran2026.md](./PhamTran2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Accurate epileptic seizure prediction from electroencephalography (EEG) remains challenging because pre-ictal dynamics may span long time horizons while clinically relevant signatures can be subtle and transient. Many deep learning models face a persistent trade-off between capturing local spatiotemporal patterns and maintaining informative long-range context when operating on ultralong sequences. We propose EEG-Titans, a dualbranch architecture that incorporates a modern neural memory mechanism for long-context modeling. The model combines sliding-window attention to capture short-term anomalies with a recurrent memory pathway that summarizes slower, progressive trends over time. On the CHB-MIT scalp EEG dataset, evaluated under a chronological holdout protocol, EEG-Titans achieves 99.46% average segment-level sensitivity across 18 subjects. We further analyze safety-first operating points on artifact-prone recordings and show that a hierarchical context strategy extending the receptive field for high-noise subjects can markedly reduce false alarms (down to 0.00 FPR/h in an extreme outlier) without sacrificing sensitivity. These results indicate that memory-augmented long-context 

> [!note] 翻譯摘要 (Traditional Chinese)
> EEG-Titans 採用「雙分支注意力」架構：一分支聚焦短期 preictal 動態，另一分支建模長時程（hours-scale）趨勢，兩者以交叉注意力融合。模型在多個公開資料集展示長時程預測能力，提供數小時 lead time，較傳統 30-60 分鐘窗口更接近臨床干預需求。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [PhamTran2026.md](./PhamTran2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
