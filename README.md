# Forecasting the Brain

A positional paper project on **Predictive / Preventive Brain–Computer Interfaces (BCI)** — reframing seizure, fall, migraine, sleep, and vigilance forecasting under a single paradigm: **anticipatory neural dynamics**.

本專案為一篇 *positional paper*，旨在將原本各自為政的五大子領域（癲癇、跌倒、偏頭痛、睡眠、警覺度預測）重新收攏於「預期性神經動態」共同框架之下，屬於 **paradigm argument paper**，不是 incremental algorithm 或 domain review。

---

## Contents / 內容

| Path | 說明 |
|---|---|
| [Forecasting the Brain.docx](Forecasting%20the%20Brain.docx) | 主論文草稿 / Main positional paper draft |
| [AI_response.md](AI_response.md) | Research Agent pipeline 逐步輸出與 checkpoint 決策紀錄 |
| [Research/20260416_predictive-preventive-bci-forecasting/](Research/20260416_predictive-preventive-bci-forecasting/) | 完整 9-step 文獻回顧產物 |
| [LICENSE](LICENSE) | 授權條款 |

### Research session artifacts

[Research/20260416_predictive-preventive-bci-forecasting/](Research/20260416_predictive-preventive-bci-forecasting/):

- `step0_session_config.json` — PICO + session metadata
- `step1_search_queries.md` — 5 strategic queries
- `step2_raw_papers.json` / `step2_search_summary.md` — 319 dedup'd papers
- `step3_shortlist.json` / `step3_screening_results.md` — 162 included (T1–T4)
- `step4_references.bib` / `step4_references_apa.md` / `step4_citation_keys.md` — citations
- `step5_full_text/` — 24 full-text PDFs + 138 abstract cards + 24 bilingual reading cards
- `step6_sota_review.md` / `step6_knowledge_graph.canvas` — SOTA synthesis (5 themes, 162→168 nodes)
- `step7_gap_analysis.md` — 3 critical gaps + meta-gap
- `full_pdf/` — 原始 PDF 資料

---

## PICO Framework

| | Scope |
|---|---|
| **P**opulation | Clinical (epilepsy, migraine, sleep-disordered) + fall-risk older adults + healthy vigilance subjects |
| **I**ntervention | Predictive / forecasting BCI with EEG + multimodal (ECG, accelerometry, eye tracking) + ML |
| **C**omparison | Reactive / detection-based BCIs, random baselines, post-event detection |
| **O**utcome | Accuracy, Sensitivity, Specificity, FPR, AUC, Lead time, Uncertainty, Clinical utility |
| Timeframe | 2019–2026 (+ 2002–2018 foundational) |

---

## Three Signatures / 領域三大訊號

1. **Temporal asymmetry / 時間不對稱** — 關鍵不是「當下」而是「未來 5 秒 ~ 數小時」；lead time 是核心度量
2. **Multimodal fusion / 多模態融合** — 純 EEG 不足，需結合 ECG、accelerometry、behavioral context
3. **Closed-loop prevention / 閉環預防介入** — 預測後需可介入（停藥、刺激、警示 caregiver）

---

## Five Themes / 五大主題 (Step 6 SOTA)

| # | Theme | Papers | T1 |
|---|---|---|---|
| 1 | Deep Sequence Models for Seizure Prediction | 60 | 14 |
| 2 | Representation Learning & Transferable EEG Models | 24 | 4 |
| 3 | Cross-Patient Generalization & Privacy | 10 | 1 |
| 4 | Efficient & Deployable Predictive BCIs | 13 | 5 |
| 5 | Cross-Domain Predictive BCIs & Reviews | 55 | 1 |

> **Key asymmetry / 關鍵不對稱：** Seizure : Migraine ≈ 40 : 1 — positional paper 宣稱的「五柱平行」實為「一柱 + 四稀疏衛星」。

---

## Critical Gaps / 三大缺口 (Step 7, Checkpoint 3 pending)

| Rank | Gap | Type | Composite |
|---|---|---|---|
| 1 | **GAP_001** — Preventive Outcome Measurement | Measurement + Integration | **4.40** |
| 2 | GAP_002 — Cross-Domain Methodological Asymmetry | Population + Methodological | 4.00 |
| 3 | GAP_003 — External Validity & Generalization Landscape | Methodological + Temporal | 3.80 |

**Meta-gap：** 162 篇中 137 為 Computational / 0 Experimental — 領域結構性仰賴離線 DL 標竿，缺 RCT 與衛星域世代設計。

---

## Pipeline Status

- [x] Step 0 — Session init
- [x] Step 1 — PICO + queries (Checkpoint 1 ✓)
- [x] Step 2 — Multi-database search (319 papers)
- [x] Step 3 — Screening (162 included, Checkpoint 2 ✓)
- [x] Step 4 — Citation export (APA + BibTeX)
- [x] Step 5 — Full-text retrieval (24 PDFs + bilingual cards)
- [x] Step 6 — SOTA review + Obsidian canvas
- [x] Step 7 — Gap analysis (**Checkpoint 3 awaiting: lock one gap**)
- [ ] Step 8 — Hypothesis specification (`/research-hypothesis`)
- [ ] Step 9 — LaTeX introduction + related work (`/research-write`)

---

## Next Action

Checkpoint 3 — Battlefield Selection：請回覆 `Lock GAP_{N}, drop GAP_{M}, GAP_{K}` 鎖定一個缺口作為 Step 8 假說規格的攻擊目標，其餘正式捨棄為 out of scope。
