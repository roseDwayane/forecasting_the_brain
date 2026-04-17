---
citation_key: "JangEtAl2026"
title_en: "Single-channel EEG-based seizure prediction using deep learning."
title_zh: "單通道 EEG 深度學習癲癇發作預測"
year: 2026
tier: 1
composite: 4.5
bilingual_scope: "abstract + key findings summary (not paragraph-level translation)"
---

# Single-channel EEG-based seizure prediction using deep learning. | 單通道 EEG 深度學習癲癇發作預測

> [!abstract] 重點摘要 / Key Findings
> - 單通道 EEG 即可達臨床可用預測效能
> - 極簡穿戴式硬體設計可行性
> - 降低部署成本與使用者負擔
> - 為「極簡 BCI」理念提供實證
>
> **完整英文版本 / Full English text:** [JangEtAl2026.md](./JangEtAl2026.md)

---

## Abstract | 摘要

> [!quote] Original (English)
> Reliable seizure prediction can improve patient safety by enabling timely protective actions, yet most high-performing approaches depend on multichannel EEG, limiting feasibility in wearable and low-power environments. This study developed an ultralight deep learning model for seizure prediction using only single-channel EEG and evaluated its clinical applicability under predefined, clinically actionable criteria: a seizure prediction horizon (SPH) of 2 minutes and a seizure occurrence period (SOP) of 30 minutes. A 37,985-parameter MobileNet-derived architecture was designed to process STFT spectrograms and validated using patient-specific leave-one-out cross-validation on the SNUH and CHB-MIT datasets. Performance was assessed using segment-based accuracy and false positive rate (FPR), along with event-based sensitivity computed under SPH-SOP constraints. The model demonstrated strong and consistent performance across both datasets. In the SNUH cohort, it achieved 85.97% accuracy, an FPR of 0.130, and 94.93% sensitivity, successfully predicting 95.08% of seizures within the SOP window. In the CHB-MIT dataset, it reached 90.72% accuracy, an FPR of 0.092, and 97.92% sensitivity. The

> [!note] 翻譯摘要 (Traditional Chinese)
> 標準臨床 EEG 通常使用 19+ 通道，限制穿戴式場景。本文驗證僅用單一 EEG 通道配合深度學習即可達到臨床可用的預測效能，大幅簡化硬體需求，為極簡穿戴式 BCI 提供技術可行性證據。

---

## Reading Notes / 閱讀筆記

**Position in the positional paper taxonomy / 於 positional paper 之位置：**

本文屬於預測性／預防性 BCI 框架下的「癲癇預測」研究群。Composite score = 4.5 (Tier 1 核心命中)；完整英文全文請參見同名 `.md` 檔案；若需段落級完整中英對照翻譯，請指定此 citation key 並告知我。

---

> **備註 / Note:** 本雙語筆記僅含 abstract + key findings 摘要翻譯，非逐段對照。完整全文見 [JangEtAl2026.md](./JangEtAl2026.md)。如需特定論文之完整段落翻譯，請直接告知 citation key。
