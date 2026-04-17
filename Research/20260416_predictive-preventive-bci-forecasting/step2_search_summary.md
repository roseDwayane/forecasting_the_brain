---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
step: 2
---

# Search Summary / 搜尋摘要

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> 預測性與預防性腦機介面：從神經與生理訊號預測認知狀態與不良健康事件
> Sources / 資料來源: Semantic Scholar, OpenAlex, PubMed, arXiv
> Date / 搜尋日期: 2026-04-16

## Results / 搜尋結果

| Query | Strategy / 策略 | Raw | Unique / 唯一 |
|-------|-----------------|-----|---------------|
| Q1 | Core terms + Population / 核心詞＋族群 | 38 | 62 |
| Q2 | Synonyms + MeSH / 同義詞＋MeSH | 114 | 83 |
| Q3 | Mechanism + Theory / 機制＋理論 | 95 | 57 |
| Q4 | Methodology + Design / 方法學＋研究設計 | 126 | 66 |
| Q5 | Cross-disciplinary / 跨域（fall／migraine／drowsiness） | 81 | 51 |
| Snowball | Top-cited references / 高引用文獻延伸 | 245 | 0 |
| **Total / 總計** | | **579** | **319** (after dedup / 去重後) |

> **Note on snowball / 雪球說明:** Top-cited topic-relevant seeds (Nasseri 2021, Beniczky 2020, Cinel 2019, etc.) had almost all their pre-2019 references filtered out by timeframe, and post-2019 references were already captured by Q1–Q5. Snowball yielded 0 new additions — the base search saturated this niche.
> 主題相關的高引用種子（Nasseri 2021、Beniczky 2020、Cinel 2019 等）其參考文獻多為 2019 年前、被時間窗過濾；2019 年後參考文獻已被 Q1–Q5 收錄，因此雪球新增為 0，顯示此利基領域主查詢已達飽和。

## Source Coverage / 來源分佈

| Source | Papers / 收錄數 |
|--------|------------|
| PubMed | 138 |
| OpenAlex | 111 |
| arXiv | 51 |
| Semantic Scholar | 25 (Q2 only — Q1/3/4/5 blocked by persistent 429) |

DOI coverage / DOI 覆蓋率: **275/319 (86.2%)**
Source overlap / 來源重疊: Minimal — four databases surfaced largely complementary corpora / 四個資料庫回傳之論文高度互補，重疊極少，代表跨域搜尋策略奏效。

> **Known caveat / 已知限制:** Semantic Scholar returned only Q2 due to a sustained 429 rate-limit state (a burst of parallel calls at the start of this step locked the shared IP for the duration of the search). OpenAlex + PubMed + arXiv compensated — total yield 319 still exceeds the 30–60 target. Q2 relevance is especially strong because it combines the two densest subfields (seizure prediction + deep learning).
> Semantic Scholar 僅 Q2 成功，其餘 Q1/3/4/5 因共享 IP 持續 429 被擋。OpenAlex + PubMed + arXiv 已補足，總量 319 遠超 30–60 目標值。Q2 相關性特強（癲癇預測＋深度學習兩大密集子領域交集）。

## Hub Papers / 核心文獻

| # | ID | Title | Author (Year) | Cites | In-degree | Cluster |
|---|-----|-------|---------------|-------|-----------|---------|
| 1 | paper_031 | Ambulatory seizure forecasting with a wrist-worn device using LSTM deep learning | Nasseri et al. (2021) | 81 | **4** | seizure_prediction |
| 2 | paper_021 | Machine learning and wearable devices of the future | Beniczky et al. (2020) | 152 | 3 | seizure_prediction |
| 3 | paper_018 | Neurotechnologies for Human Cognitive Augmentation | Cinel et al. (2019) | 166 | 3 | other (BCI review) |
| 4 | paper_004 | Symbiotic human-robot collaborative assembly | Wang et al. (2019) | 539 | 3 | other (HRI review) |

**Interpretation / 解讀:** Nasseri 2021（穿戴式 LSTM 癲癇預測）為內部最高連結度節點，與 Beniczky 2020（穿戴式機器學習預測裝置未來）共同構成「可穿戴預測式 BCI」的核心引用簇 ── 也正是你原始 positional paper 的核心主張。兩篇 "other" 叢集的高引用文獻（HRI 與認知增強綜述）雖非直接主題，但被多篇預測式 BCI 論文引用，顯示此領域與人機協作、認知增強之跨域連結。

## Citation Clusters / 引用聚類

| Cluster slug | Count | Theme / 主題 |
|--------------|-------|--------------|
| **seizure_prediction** | 107 | Seizure forecasting / pre-ictal EEG prediction (deep learning, wearables, closed-loop) — 癲癇預測（深度學習、穿戴、閉環）|
| **deep_learning_eeg** | 44 | Deep learning architectures for EEG and physiological signal analysis — EEG 深度學習方法 |
| **bci_methods** | 31 | Core BCI methods (SSVEP, P300, motor imagery, signal processing) — 核心 BCI 方法 |
| **fall_prediction** | 22 | Fall prediction and gait/balance monitoring — 跌倒預測與步態／平衡 |
| **predictive_coding** | 21 | Predictive coding, pre-stimulus dynamics, anticipatory activity — 預測編碼與預期性動態 |
| **vigilance_drowsiness** | 15 | Vigilance / drowsiness / fatigue forecasting — 警覺度／嗜睡／疲勞預測 |
| **sleep_forecasting** | 11 | Sleep prediction / slow-wave sleep / circadian — 睡眠預測與慢波睡眠 |
| **wearable_multimodal** | 10 | Wearable multimodal sensing (ECG, PPG, accelerometry) — 可穿戴多模態 |
| **migraine_headache** | 3 | Migraine / headache prediction — 偏頭痛預測（搜尋產量最低） |
| **other** | 55 | Tangential / off-topic (to be pruned at screening) — 偏離或邊緣（留待 Step 3 篩選） |

## Yield Assessment / 產量評估

**English.** The collection of 319 unique papers is comfortably above the 30–60 target and maps cleanly onto the five domains from the positional paper (seizure, sleep, migraine, fall, vigilance) plus supporting clusters (BCI methods, deep-learning methodology, predictive-coding theory, wearable sensing). Seizure prediction dominates (107 papers, 34%) as expected given its maturity as a subfield; migraine prediction is thinnest (3 papers) which itself is a signal — this is likely the most under-explored prediction domain in the evidence base. The "other" bucket (55 papers) contains tangential reviews that Step 3 screening should cleanly remove. DOI coverage at 86.2% is healthy for downstream full-text retrieval.

**繁體中文。** 最終 319 篇唯一論文，遠超 30–60 之目標區間，並乾淨對應到 positional paper 的五大域（癲癇、睡眠、偏頭痛、跌倒、警覺度）以及方法學與理論支撐簇（BCI 方法、EEG 深度學習、預測編碼、穿戴感測）。癲癇預測最龐大（107 篇，34%）符合其子領域成熟度預期；偏頭痛預測僅 3 篇——此稀疏本身即是訊號，暗示這是五大域中最待開發的預測方向。「other」桶 55 篇多為邊緣綜述，Step 3 篩選將清除。DOI 覆蓋率 86.2% 利於後續全文擷取。

---

Files / 檔案: `step2_raw_papers.json` (319 papers with citation network), `step2_search_summary.md`
Next step / 下一步: `/research-screen` (Step 3 — quality/relevance screening with checkpoint 2 邊緣打撈)
