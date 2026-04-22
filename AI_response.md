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

# Experimental / 實驗研究 為0，是什麼意思？


這裡的 **Experimental = 0** 是在講 162 篇納入文獻的 **研究方法學（methodology）分類結果**，沿用循證醫學常見的五類分法：

|Methodology|中文|特徵|你這批文獻的計數|
|---|---|---|---|
|**Computational**|計算研究|離線資料集 + 模型訓練／benchmark|**137 / 162（85%）**|
|**Experimental**|實驗研究|**RCT、前瞻介入試驗**——隨機分組、操弄自變項、量測臨床結果|**0**|
|**Observational**|觀察研究|世代／病例對照，不介入，只長期追蹤|2|
|**Theoretical**|理論研究|概念／數學／回顧論證|9|
|**Engineering**|工程研究|硬體／系統 deployment|2|

所以「Experimental 為 0」精確的意思是：

> **在這 162 篇裡，沒有任何一篇做過 RCT 或前瞻性介入試驗來驗證「預測 BCI 真的能預防壞事發生」**。

**為什麼這件事重要（也是為什麼它被標成 meta-gap）：**

1. **預防性主張無法以離線 benchmark 驗證。** AUC = 0.95 只證明模型「能在歷史資料上分類 preictal vs interictal」；它**不能**證明「警示病人後，真的少發作一次癲癇／少跌倒一次」。後者需要隨機對照設計。
2. **整個領域的證據金字塔缺底層。** 臨床證據階層的頂端（RCT → cohort → case-control → case series → expert opinion）最上面那一格是空的，卻有 137 篇擠在「computational benchmark」這一層，而這層在 evidence-based medicine 裡甚至不算臨床證據。
3. **這直接放大 GAP_001（Preventive Outcome Measurement）的嚴重性。** 整個 positional paper 主張「從 detective → predictive → preventive」的 paradigm shift，但 preventive 這一端連一篇 RCT 都沒有 — 主張本身缺乏方法學支撐。
4. **對 positional paper 的戰略意涵：** 這不是壞消息，反而是**論文的槓桿點**。你可以把「Experimental = 0」寫成 call to action：宣告這個領域若要從「能預測」走到「能預防」，下一個十年必須補上前瞻性試驗這一條軸。

所以 email 裡那句 "137 are computational and 0 are experimental" 就是在濃縮這個發現 — **領域結構性地只做離線模型 benchmark，從未用臨床試驗驗證預防效益**。

要我幫你在 email 裡把這句話擴寫成兩三句、讓讀者（特別是非這個子領域的老師）一眼看懂嚴重性嗎？

# RCT 與前瞻介入試驗：完整解釋

這是**循證醫學（Evidence-Based Medicine, EBM）**的核心概念。我分三層講：**什麼是**、**為什麼這樣設計**、**在 BCI 語境下長什麼樣**。

---

## 一、RCT 是什麼？

**RCT = Randomized Controlled Trial（隨機對照試驗）**

它是**臨床證據金字塔頂端**的研究設計，目的是回答一個**因果問題**：

> 「介入 X 是否**導致**結果 Y 的改變？」

注意關鍵字是**導致（cause）**，不是**關聯（correlate）**。這是 RCT 和其他設計最根本的差別。

RCT 有三個不可分割的要素：

|要素|英文|核心動作|
|---|---|---|
|**R**andomized|隨機分組|用亂數把受試者分到不同組|
|**C**ontrolled|有對照組|至少一組不接受真正的介入（或接受標準治療）|
|**T**rial|前瞻性試驗|先設計、再招募、再介入、再追蹤 — 時間順序是「未來式」|

---

## 二、你問的三件事逐一拆解

### 2.1 隨機分組（Randomization）

**做什麼：** 用電腦亂數產生器（或信封抽籤），把每一位受試者**隨機**分配到「介入組」或「對照組」。

**例子：** 招募 200 位癲癇病人，丟銅板：

- 正面 → 戴預測 BCI（介入組，n≈100）
- 反面 → 戴外觀相同但不預測的假裝置（對照組，n≈100）

**為什麼一定要隨機？**

這是 RCT 最關鍵、最反直覺的一步。隨機的目的**不是**讓兩組「看起來公平」，而是要解決一個叫 **confounding（干擾因子）** 的問題：

> 假如你讓醫師「挑」病人進介入組，他可能（無意地）把病情較輕、配合度高、住得近的病人分到介入組。那麼試驗結束後，就算介入組表現比較好，你也**無法分辨**是 BCI 有效、還是這些病人本來就比較容易好。

隨機分組的數學保證是：**當樣本夠大時，所有已知與未知的干擾因子（年齡、病程、基因、社經地位、順從性……）在兩組之間會趨近平均分佈。** 這樣如果最後兩組有差異，這差異就只能歸因於「介入」本身。

> 這就是 RCT 被稱為「**因果推論的黃金標準**」的唯一理由 — 隨機化切斷了介入與結果之間所有潛在的共變項。

---

### 2.2 操弄自變項（Manipulating the Independent Variable）

**做什麼：** 研究者**主動**決定每組受試者接受什麼介入，而**不是**觀察他們自己選擇了什麼。

**自變項（Independent Variable, IV）** = 你操弄的那個東西。 **依變項（Dependent Variable, DV）** = 你量測的結果。

**例子：**

- IV（操弄）：是否使用癲癇預測 BCI（Yes / No）
- DV（量測）：未來 6 個月癲癇發作次數

**「操弄」vs「觀察」的對比：**

|設計|研究者角色|能說什麼|
|---|---|---|
|**實驗（RCT）**|我**指派**誰戴 BCI|「BCI **導致** 發作減少」|
|**觀察（Cohort）**|我**看** 誰自己戴了 BCI|「戴 BCI 的人**比較常**發作少」（但可能是因為戴 BCI 的人本來就更認真服藥）|

**為什麼要操弄？**

因為「自己選擇戴 BCI 的人」和「不戴的人」在幾十個未測變項上本來就不一樣（有錢、有科技素養、有照護者支援……）。唯有研究者**強制分派**，才能讓兩組的差異只剩下「是否戴 BCI」這一項。

這就是為什麼你的 162 篇裡 137 篇 Computational 都**不能**回答「BCI 是否有效」—— 他們用的是歷史資料，病人早就已經經歷了所有事情，研究者沒有介入任何變項，所以根本沒有「操弄」這一步。

---

### 2.3 量測臨床結果（Measuring Clinical Outcomes）

這是最容易被忽略、但**對你的 positional paper 最致命**的一點。

**臨床結果（clinical outcome）** 指的是**對病人真實生活有意義**的終點。它**不是**模型的準確率。

#### 術語對照表

|類別|中文|例子|對病人的意義|
|---|---|---|---|
|**Technical metric**|技術指標|AUC、Sensitivity、FPR|零 — 病人不在乎 AUC|
|**Surrogate endpoint**|替代終點|Preictal 偵測率、警示準時率|間接 — 理論上有用|
|**Clinical outcome**|**臨床結果**|**發作次數減少、跌倒受傷率、住院天數、生活品質（QoL）、死亡率**|**直接 — 病人真正在乎的**|

#### 臨床結果的標準分類

1. **Hard outcomes（硬終點）**：客觀可計數、不可狡辯
    - 死亡、住院、骨折、送急診
2. **Soft outcomes（軟終點）**：主觀但重要
    - 生活品質量表分數（SF-36、QOLIE-31）、焦慮分數、自主活動時間
3. **Composite outcomes（複合終點）**：多個綁在一起看
    - 「死亡 + 住院 + 重大事件」任一發生即計數

#### 為什麼這對你的論文是核心爭點？

你的 meta-gap 那句「137 computational / 0 experimental」的**真正含義**是：

> 「這個領域花了十年，把 AUC 從 0.85 推到 0.95。但**沒有任何一篇論文**證明這個進步讓任何一個真實病人**少發作一次、少跌倒一次、多活一天、或過得比較好**。」

AUC 再高都不是臨床結果 —— 它只是「在歷史資料集上分類 preictal 和 interictal 的能力」。這就是你 GAP_001 的核心 —— **預防性結果測量（Preventive Outcome Measurement）完全缺席**。

---

## 三、前瞻（Prospective）vs 回溯（Retrospective）

「前瞻介入試驗」的**前瞻**兩字也很關鍵：

||前瞻 Prospective|回溯 Retrospective|
|---|---|---|
|時間順序|先設計 → 再招募 → 再量測|翻舊資料、回去看已經發生的事|
|結果變項|**未來**才會發生|早就發生完了|
|偏誤|可控|很難控（selection bias、記憶偏差、資料缺漏）|
|BCI 領域對應|**RCT、Prospective cohort**|137 篇 Computational 幾乎全在這格 — 拿 CHB-MIT 等歷史資料做 benchmark|

「回溯性預測」其實是個邏輯弔詭 —— 你在 2024 年用 2010 年的資料「預測」2010 年的癲癇，那個發作早就結束了，沒有任何東西真的被「預測」或「預防」。

---

## 四、完整 RCT 範例（BCI 版）

假設你要做一個 RCT 驗證 GAP_001 —— 癲癇預測 BCI 的預防效益：

```
研究問題：穿戴式癲癇預測 BCI + 即時警示 + 病人備用藥物，
          是否能減少抗藥性癲癇病人 6 個月內的發作次數？

設計：    雙盲隨機對照試驗（Double-blind RCT）

受試者：  200 位抗藥性局灶性癲癇成人（focal drug-resistant epilepsy），
         基線每月發作 ≥ 4 次

隨機分組：1:1 隨機分派
         - 介入組（n=100）：真實預測 BCI + 警示 app + 備用 diazepam
         - 對照組（n=100）：假裝置（sham）+ 相同 app 但警示為隨機觸發 + 相同備用藥

自變項（操弄）：是否收到「基於腦波的真實預測警示」

主要臨床結果（Primary outcome）：
         6 個月發作總次數（日記 + 穿戴式驗證，intention-to-treat 分析）

次要臨床結果（Secondary outcomes）：
         - 急診就診次數
         - 與癲癇相關之住院天數
         - QOLIE-31 生活品質量表變化
         - 嚴重不良事件（SUDEP、受傷）

盲化：    病人盲（裝置外觀相同）+ 評估者盲（分析者不知分組）

統計：    預先註冊於 ClinicalTrials.gov；混合效應 Poisson 迴歸；
         α = 0.05；檢定力 80% 偵測 30% 發作減少

追蹤：    12 個月（6 個月介入 + 6 個月延續觀察）
```

你目前這 162 篇裡，**0 篇**長這樣。這就是 Experimental = 0 的完整含義。

---

## 五、為什麼你應該把這件事寫進 positional paper 的 thesis

這不只是「統計盤點」而已 —— 它是**你論文的論證武器**：

1. **證據層次的結構性失衡**可以作為 paradigm shift 的主要論據 —— 目前的領域還停在 Phase 2（technical feasibility），根本沒進 Phase 3（clinical efficacy）。
2. **它替你合理化 positional paper 的存在** —— 如果領域已經有成熟 RCT，就輪不到 positional paper 來呼籲典範轉移；正因為 RCT 全空，你的 call to action 才有正當性。
3. **它給下一代研究者一個明確的攻擊目標** —— 不是「再提升 AUC 0.01」，而是「**設計並執行第一個預防性 BCI 的 RCT**」。