## Checkpoint 1 — 初始定向核准 / Initial Orientation Approval

### PICO Framework

||English|繁體中文|
|---|---|---|
|**P**|Clinical (epilepsy, migraine, sleep-disordered) + older adults at fall risk + healthy vigilance/cognitive task subjects, monitored via non-invasive/minimally invasive neural-physiological sensors|臨床族群（癲癇、偏頭痛、睡眠障礙）＋跌倒高風險長者＋警覺度任務健康受試者，以非侵入／微侵入感測器監測|
|**I**|Predictive/forecasting BCI with EEG + multimodal (ECG, 加速度, eye tracking) + ML (CNN/RNN/LSTM/Transformer/probabilistic DL/federated)|預測式 BCI，結合 EEG＋多模態生理訊號＋ML|
|**C**|Reactive/detection-based BCIs, random baselines, post-event detection|反應式 BCI、隨機基線、事後偵測|
|**O**|Accuracy/Sensitivity/Specificity/FPR/AUC/Lead time/Uncertainty/Clinical utility|準確率／敏感度／特異度／FPR／AUC／提前時間／不確定性／臨床效益|
|Setting|Ambulatory, clinical (EMU/sleep lab), home, industrial safety-critical|行動、臨床、居家、工業安全關鍵|
|Timeframe|2019–2026 (+ 2002–2018 foundational)|2019–2026（含奠基文獻）|

### 5 Queries（摘要）

|#|Strategy|核心字串|
|---|---|---|
|**Q1**|Core + Population|`"predictive BCI" OR "forecasting BCI" OR "anticipatory BCI"` + EEG|
|**Q2**|Synonyms + MeSH|`"seizure prediction" OR preictal` + DL|
|**Q3**|Mechanism|`"predictive coding" OR "pre-stimulus EEG"` + attention/vigilance|
|**Q4**|Methodology|EEG + DL/Transformer/Federated + sensitivity/AUC/FPR|
|**Q5**|Cross-disciplinary|wearable/multimodal + 跌倒／偏頭痛／睡眠／嗜睡|

---

### 請回覆其中一項 / Please respond:

1. **Approved / 通過** → 立刻跑 Step 2（research-search）
2. **Add keywords** → 告訴我要加什麼（例如「加 SSVEP forecasting、fNIRS、active inference」）
3. **Modify PICO** → 例如想縮小到只限 seizure、或排除 industrial vigilance
4. **Remove Q#** → 例如「移除 Q5，太分散」


---

## Search Summary / 搜尋摘要

|Query|Strategy|Unique|
|---|---|---|
|Q1|Core + Population|62|
|Q2|Synonyms + MeSH (seizure prediction)|83|
|Q3|Mechanism (predictive coding)|57|
|Q4|Methodology (DL + metrics)|66|
|Q5|Cross-disciplinary (fall/migraine/drowsiness)|51|
|Snowball|—|0 (主查詢已飽和)|
|**Total**||**319** (raw 579 → dedup 319)|

**DOI coverage:** 275/319 (86.2%) ✓ **Sources:** PubMed 138 · OpenAlex 111 · arXiv 51 · Semantic Scholar 25 (Q2 only，其他 Q 因持續 429 受阻，但其餘三源已補足)

## Hub Papers / 核心文獻

|ID|Paper|In-deg|
|---|---|---|
|**paper_031**|Nasseri et al. 2021 — Ambulatory seizure forecasting w/ wrist-worn LSTM|4|
|paper_021|Beniczky et al. 2020 — ML & wearable devices of the future|3|
|paper_018|Cinel et al. 2019 — Neurotechnologies for Cognitive Augmentation|3|
|paper_004|Wang et al. 2019 — Symbiotic HRI assembly|3|

## Citation Clusters / 引用聚類

|Cluster|N|Theme|
|---|---|---|
|seizure_prediction|**107**|癲癇預測（最成熟子領域）|
|deep_learning_eeg|44|EEG 深度學習方法|
|bci_methods|31|核心 BCI 方法|
|fall_prediction|22|跌倒預測|
|predictive_coding|21|預測編碼與預期性動態|
|vigilance_drowsiness|15|警覺度／嗜睡|
|sleep_forecasting|11|睡眠預測|
|wearable_multimodal|10|穿戴多模態|
|migraine_headache|**3**|偏頭痛預測（訊號最稀疏 → 可能 gap）|
|other|55|邊緣（Step 3 會篩除）|

**Key signal / 關鍵訊號:** Migraine prediction 只有 3 篇 — 這本身暗示 positional paper 的五大域中，偏頭痛預測可能是最未開發、潛在 gap 最大的方向。

Files saved to `Research/20260416_predictive-preventive-bci-forecasting/`:

- `step2_raw_papers.json` (319 papers + citation network)
- `step2_search_summary.md`

**Next step:** `/research-screen` — Step 3 會做相關性＋品質雙軸評分，刪除 "other" 叢集邊緣文獻，並在 composite 3.0–3.4 區間觸發 Checkpoint 2（邊緣打撈）讓你決定是否救回。

要直接 `/research-screen` 嗎？

---

## Screening Criteria / 篩選標準

**Inclusion / 納入**

- Predictive/forecasting BCI or EEG-based prediction of cognitive states or adverse events (seizure, fall, sleep, migraine, vigilance, drowsiness)
- Empirical studies reporting prediction metrics (sensitivity, specificity, FPR, AUC, lead time) OR systematic reviews in this area
- Mechanistic/theoretical work on predictive coding, pre-stimulus dynamics, anticipatory neural activity relevant to forecasting
- Wearable/multimodal physiological sensing methods directly applicable to forecasting

**Exclusion / 排除**

- General AI-in-healthcare reviews without predictive-BCI focus
- Post-event detection (not forecasting) systems
- Animal-only studies, invasive-only chronic implant hardware papers
- Editorials/commentaries lacking data
- Off-topic engineering (industrial robotics, smart grid, blockchain, etc.)

---

## Step 3 Results / 篩選結果

|Category|Count|%|
|---|---|---|
|**Included / 納入**|**162**|50.8%|
|├── T1 Core hits (≥4.5)|25|7.8%|
|├── T2 Strong supporting (4.2–4.4)|32|10.0%|
|├── T3 Robust relevance (3.8–4.1)|47|14.7%|
|└── T4 Contextual (3.5–3.7)|58|18.2%|
|Borderline / 邊緣 (3.0–3.4)|54|16.9%|
|Excluded / 排除 (<3.0)|103|32.3%|
|**Total**|**319**|100%|

**Top T1 picks / 核心命中前五:**

- paper_211 [4.8] Multi-Teacher Knowledge Distillation RGF seizure prediction (2026)
- paper_231 [4.8] HCFT: Hierarchical Convolutional Fusion Transformer for EEG
- paper_250 [4.8] Generalized motor seizure detection and prediction review

**Hub paper audit:** paper_031 Nasseri 2021 (wrist-worn LSTM) → Included T3 ✓ | paper_021 Beniczky 2020 → **Borderline 3.4** ⚠️ | paper_018 Cinel 2019 → **Borderline 3.2** ⚠️ | paper_004 Wang HRI → Excluded (correct, off-topic).

---

## ⛳ Checkpoint 2: 邊緣打撈 / Borderline Rescue

54 papers scored 3.0–3.4 — may contain cross-disciplinary work missed by keyword-based scoring. **Two hub papers are in this range — strongly recommended for manual inclusion:**

- **paper_021** — Beniczky et al. 2020, "Machine learning and wearable devices of the future" (cluster=seizure_prediction, in_degree=3, 152 citations) — **foundational wearable-prediction review**
- **paper_018** — Cinel et al. 2019, "Neurotechnologies for Human Cognitive Augmentation" (in_degree=3, 166 citations) — **foundational BCI review**

Other noteworthy 3.4-scored candidates worth considering: paper_070 SzCORE framework, paper_107 scoping review on seizure prediction, paper_160 EEG implicit intent detection, paper_172 ChatBCI word prediction, paper_205 patient-tailored seizure prediction, paper_217 EEG-ML uncertainty evaluation.

Full list of all 54 borderline papers in `step3_screening_results.md` under "Borderline Papers".

**請審核 / Please review:**

- 最推薦：`include paper_021 paper_018`（兩篇核心引用論文）
- 其他欲納入論文請回覆論文 ID（可多個）
- 無需變更 → 回覆「proceed」直接進入 Step 4 `/research-export`

---

## Step 4 Results / 匯出結果

**Files written / 已產生檔案:**

- `step4_references_apa.md` — 162 APA 7 references (42 KB)
- `step4_citation_keys.md` — Citation key lookup table (20 KB)
- `step4_references.bib` — BibTeX for LaTeX compilation (70 KB)

**Breakdown / 類型分佈:**

|Type|Count|
|---|---|
|Journal articles|114|
|Conference papers|12|
|Preprints (arXiv)|36|
|**DOI coverage**|**130/162 (80.2%)**|

**Validation / 驗證全部通過:**

- ✓ Counts match (APA=162, BibTeX=162, Keys=162)
- ✓ All multi-author APA entries have `&` before last author
- ✓ Alphabetical order verified (Abbasi → Zhang)
- ✓ Disambiguation complete: 10 pairs with `a/b` suffixes + 1 triple with `a/b/c` (no lone suffixes)
- ✓ All 162 keys present in `.bib`

**Key examples / 引用鍵範例:**

- `NasseriEtAl2021` → (Nasseri et al., 2021) — wrist-worn LSTM seizure forecasting (hub paper)
- `XiaZhang2024` pattern for two-author papers
- `Zhang2024a/b/c` disambiguated when multiple Zhang 2024 papers exist

**Spot-check APA entry:**

> Abbasi, H. F., Hamayat, F., Ahmad, R. F., & Anwar, S. M. (2025). Edge-enabled pre-ictal activity prediction framework using geometric deep learning. In _Annual International Conference of the IEEE Engineering in Medicine and Biology Society..._. [https://doi.org/10.1109/embc58623.2025.11253214](https://doi.org/10.1109/embc58623.2025.11253214)

Session advanced to `current_step: 4`. Next step is `/research-fulltext` (Step 5 — attempt full-text retrieval for 162 papers via DOI/URL). This is the most token-intensive step in the pipeline (many web fetches + long markdown outputs).

**Proceed to Step 5 `/research-fulltext`?** / 是否繼續 Step 5？ 回覆「continue」以執行。

---

## Step 5 Results / 全文取得結果

**Files written / 已產生檔案 (187 total in `step5_full_text/`):**

- 24 × `{key}.md` — **full text** from user-provided PDFs (avg 955 lines each, via `pdftotext -layout`)
- 138 × `{key}.md` — **abstract-only** for Tiers 2–4 (using Step 2 metadata)
- 24 × `{key}_zh.md` — **bilingual reading cards** for Tier 1 (Chinese title + abstract summary + key-findings bullets)
- `_access_log.md` — full access provenance + action-required list

**Summary / 取得率:**

|Level|Count|%|
|---|---|---|
|full-text-pdf|24|**14.8%**|
|abstract-only|138|85.2%|

**Tier 1 PDF coverage:** 24/25 (missing `WangEtAl2026b` — Jie Wang "Explainable End-to-End Seizure Prediction")

**PDF→citation-key mapping (24):** `Bary2024→BaryMacq2024`, `Cao2026→CaoEtAl2026`, `Chenqi2022→LiEtAl2022`, `Dabin2026→JangEtAl2026`, `Dhanalekshmi2025→YedurkarEtAl2025`, `Dianli2025→WangEtAl2025c`, `Guo2023→GuoEtAl2023`, `Humza2025→AbbasiEtAl2025`, `Izza2026→AhmadEtAl2026`, `Jiahui2025→LiaoEtAl2025a`, `Koutsouvelis2024→KoutsouvelisEtAl2024`, `Longfei2025→QiEtAl2025`, `Maiora2024→MaioraEtAl2024`, `Masoud2026→AmiriEtAl2026`, `Mohamed2026→MahdiBaghdadi2026`, `Ruifeng2025→ZhengEtAl2025`, `Sunkara2023→SunkaraRajakumari2023`, `Tien2026→PhamTran2026`, `Wesal2026→WesalEtAl2026`, `YITONG2025→WuEtAl2025`, `Yazeed2025→AlkhrijahEtAl2025`, `Yimin2026→QuEtAl2026`, `Zan2025→LiEtAl2025b`, `Zhang2026→ZhangEtAl2026`.

**Scope note / 範圍說明:** Bilingual cards contain Chinese title + Chinese abstract summary + key-findings bullets (not paragraph-level full translation — the 24×full-paper translation would far exceed practical context limits). For a specific paper needing full paragraph-by-paragraph bilingual version, request it by citation key.

**Proceed to Step 6 `/research-sota` / 繼續 Step 6 — SOTA review + knowledge graph synthesis?** This step uses the 24 T1 full texts as primary evidence, T2-T4 abstracts as supporting context. Token-intensive — will generate a structured literature synthesis and Obsidian canvas file.

---

## 三大訊號特徵 / Three Signatures that Define This Field

1. **時間不對稱** — 研究關鍵不是「此刻腦在想什麼」，而是「未來 5 秒 ~ 數小時會發生什麼」（lead time 是核心度量）
2. **多模態融合** — 純 EEG 已不夠，必須結合 ECG、accelerometry、behavioral context（Saeizadeh 2024、Aldahr 2023 都是多模態）
3. **閉環預防介入** — 預測出來後要能「做事」：停藥調整、刺激介入、環境調整、警示 caregiver（這區分了「forecasting science」與「preventive engineering」）

---

## 最接近的既有領域標籤 / Closest Existing Field Labels

若要投稿或定位：

- **主標籤**：_Predictive Brain-Computer Interfaces_ / _Anticipatory Neurotechnology_（新興，尚未完全體制化）
- **次標籤**：_Seizure Forecasting_（最成熟子領域，已有 Nature/Frontiers 專刊）、_Passive BCI_、_Digital Biomarkers_、_Closed-loop Neuromodulation_
- **會議歸屬**：IEEE EMBC、IEEE BIBM、NeurIPS ML4H、BCI Society Meeting
- **期刊歸屬**：_Journal of Neural Engineering_、_Nature Biomedical Engineering_、_Sensors_、_Frontiers in Neurology_、_Neural Computation_

---

## 這篇 positional paper 的獨特切入點 / Novel Angle

它不是在做 **一個新演算法**，也不是 **一個 domain 的綜述**。它在做 **跨 5 個子領域的證據統合**，把原本各自為政的「seizure prediction」「fall prediction」「migraine prediction」「SSVEP prediction」「vigilance forecasting」全部重新收攏在一個共同框架之下 — **anticipatory neural dynamics**。

這種論述結構在學術上稱為 **"paradigm argument paper"**，目的不是 incremental science，而是 **重新框定研究議程**（re-framing the research agenda）。這也是為什麼它叫 _positional paper_ — 作者在宣稱一個立場，而非報告一個實驗。

---

是否繼續 Step 6 `/research-sota`？或你想先針對這個領域解析追問（例如：想深挖 5 大子領域中哪個、想看 paradigm argument 與一般 review 的差異、想討論如何把這個架構落地到具體實驗）？

---

## Step 6 — SOTA Review / 文獻綜述已完成

### 📄 輸出檔案 / Output Files

- **`step6_sota_review.md`** — 49,501 chars, 198 lines, 五主題雙語綜整
- **`step6_knowledge_graph.canvas`** — 50,305 bytes, 168 nodes (162 paper + 5 theme groups + 1 overview), 27 edges

### 🎯 五大主題分佈 / Theme Distribution

|#|Theme / 主題|Papers|T1 Anchors|
|---|---|---|---|
|1|**Deep Sequence Models for Seizure Prediction** / 深度序列模型於癲癇預測|60|14|
|2|**Representation Learning & Transferable EEG Models** / 表徵學習與可遷移 EEG 模型|24|4|
|3|**Cross-Patient Generalization & Privacy** / 跨病患泛化、個人化與隱私|10|1|
|4|**Efficient & Deployable Predictive BCIs** / 高效可部署預測式 BCI|13|5|
|5|**Cross-Domain Predictive BCIs & Reviews** / 跨域預測式 BCI 與回顧|55|1|

### 🎨 方法學分佈 / Methodology Distribution

🟠 Computational (137) · 🟡 Review (12) · 🟣 Theoretical (9) · 🟢 Observational (2) · 🔵 Engineering (2)

### 💡 三個跨主題亮點 / Cross-Theme Highlights

1. **CHB-MIT 已飽和** — 至少 7 篇 2025–2026 T1 論文報告 ≥96% 敏感度 / FPR ≤ 0.05/h。CHB-MIT 作為標竿已無區分力，但跨資料集（Siena、MSSM、SNUH）效能差 3–5 個百分點——真正的泛化爭議在這裡。
    
2. **時間弧線清晰**：CNN（2019–21）→ CNN+LSTM（2022–23）→ Transformer 主導（2024–26）→ SSL 預訓練 + 邊緣部署（新興）。所有 2025–26 T1 癲癇論文都用了 attention。
    
3. **五域極度不對稱** — Seizure:Migraine ≈ 40:1。positional paper 將五域視為平行的定位**未被實際研究量支持**——這是 Step 7 缺口分析的最強訊號。
    

### 🔗 Canvas 結構 / Canvas Structure

T1 與 T5（最大）在上排，T2/T3/T4 在下排。每個 paper node 按方法學著色、可於 Obsidian 中點擊進入全文。27 條關係邊標記了架構血緣、跨主題橋樑、回顧包含關係。

---

## Next Step / 下一步

**/research-gaps** (Step 7 — gap analysis with **Checkpoint 3: 戰場選擇**) 會根據這五主題的爭議與分歧，生成 3–5 個優先級打分的研究缺口，並請你「鎖定一個缺口」作為 Step 8 假說規格的起點。

要繼續 `/research-gaps` 嗎？

---

## Step 7 完成 / Step 7 Complete — 缺口分析

產出檔案 / Output: [step7_gap_analysis.md](vscode-webview://0duskootcbr36krvvlpdl3bao4oc24005hkujj4b490uefkktirb/Research/20260416_predictive-preventive-bci-forecasting/step7_gap_analysis.md)

### 三個關鍵缺口（依綜合優先分排序）/ Three Critical Gaps (ranked by composite priority)

|Rank|Gap ID|Title|Type|Sev|Nov|Feas|**Composite**|
|---|---|---|---|---|---|---|---|
|**1**|**GAP_001**|Preventive Outcome Measurement / 預防性結果測量|Measurement + Integration|5|5|3|**4.40**|
|2|GAP_002|Cross-Domain Methodological Asymmetry / 跨域方法學不對稱|Population + Methodological|4|4|4|**4.00**|
|3|GAP_003|External Validity & Generalization Landscape / 外部效度與泛化景觀|Methodological + Temporal|5|3|3|**3.80**|

### 三缺口分工 / How the three gaps partition the field

- **GAP_001（垂直）** — 預測→預防之因果鏈於 Tier 1 完全未被測量。`CaoEtAl2026`、`PhamTran2026`、`YedurkarEtAl2025` 皆止於警報，無下游事件率減量。positional paper 自稱「predictive → preventive」之核心宣稱因此仍是推論而非實證。
- **GAP_002（水平）** — 癲癇 83 篇、偏頭痛 2 篇（~40:1 不對稱）；睡眠、警覺度、預測編碼三域於 T1 皆無全文錨點。五柱典範實為「一柱 + 四稀疏衛星」結構。
- **GAP_003（深度）** — 資料集偏移 3–5pp、主體偏移 20pp、通道縮減 15pp、時界衰減（89.3%→68.2% @90min）皆以單因子孤立報告；完整因子曲面無人刻劃。

### 元缺口 / Meta-gap

**方法學單一文化**：162 篇中 🟠137 Computational / 🔴0 Experimental / 🟢2 Observational — 此領域結構性仰賴離線 DL 標竿，無法回答 GAP_001 所需之 RCT 與 GAP_002 所需之衛星域世代設計。

### Checkpoint 3: 戰場選擇 / Battlefield Selection

請從三缺口中**鎖定一個**作為 Step 8 假說規格之攻擊目標，其餘二者將被正式捨棄為「out of scope」。

**格式 / Format:** `Lock GAP_{N}, drop GAP_{M}, GAP_{K}` （例如 `Lock GAP_001, drop GAP_002, GAP_003`）

Session config 已更新至 `current_step: 7`。等待您的裁定後進入 `/research-hypothesis`。