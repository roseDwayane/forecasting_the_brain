---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
---

# Search Queries / 搜尋策略

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> 預測性與預防性腦機介面：從神經與生理訊號預測認知狀態與不良健康事件
> Generated / 產生日期: 2026-04-16

## PICO Framework

| Component | English | 繁體中文 |
|-----------|---------|---------|
| **P** Population | Human subjects monitored via non-invasive / minimally invasive neural-physiological sensors — clinical (epilepsy, migraine, sleep-disordered), older adults at fall risk, and healthy individuals in vigilance / cognitive tasks | 透過非侵入或微侵入神經–生理感測器監測之人類受試者——包含臨床族群（癲癇、偏頭痛、睡眠障礙）、跌倒高風險長者、以及執行警覺度或認知任務之健康受試者 |
| **I** Intervention | Predictive / forecasting BCI systems that anticipate cognitive states, performance decrements, or adverse health events from EEG + multimodal physiological signals (ECG, 加速度計, eye tracking) using ML (CNN, RNN/LSTM, Transformer, probabilistic DL, federated learning) | 以機器學習（CNN、RNN/LSTM、Transformer、機率式深度學習、聯邦學習）結合 EEG（腦電圖）與多模態生理訊號（ECG 心電、加速度、眼動），用於預測認知狀態、表現下降或不良健康事件的預測式 BCI（腦機介面）系統 |
| **C** Comparison | Traditional reactive / detection-based BCIs, random-predictor baselines, post-event detection, standard clinical monitoring, or no prediction | 傳統反應式／事後偵測 BCI、隨機預測基線、事件後偵測系統、常規臨床監測，或無預測介入 |
| **O** Outcome | Prediction accuracy, sensitivity, specificity, false prediction rate, AUC-ROC, lead time (ms → hours), prediction uncertainty, and downstream clinical utility (seizure reduction, fall prevention, sleep quality, vigilance maintenance) | 預測準確率、敏感度、特異度、假預測率、AUC-ROC、提前時間（毫秒至小時）、預測不確定性，以及下游臨床效益（癲癇減少、跌倒預防、睡眠品質、警覺度維持） |
| Setting | Ambulatory / wearable, clinical (EMU, sleep lab), home-based, industrial safety-critical | 行動／可穿戴、臨床（癲癇監測單位、睡眠實驗室）、居家、工業安全關鍵場域 |
| Timeframe | 2019–2026 (+ seminal 2002–2018 for foundational BCI and predictive coding) | 2019–2026（並納入 2002–2018 之 BCI 與預測編碼奠基文獻） |

## Queries

### Q1: Core Terms + Population
**Query:** `("predictive brain-computer interface" OR "forecasting BCI" OR "anticipatory BCI") AND (EEG OR electroencephalography) AND (prediction OR forecasting)`
**Rationale / 策略說明:** Direct hit on predictive BCI as a named paradigm — finds papers explicitly framing BCI as predictive/forecasting rather than reactive. / 直接命中「預測式 BCI」這個正在成形的典範——找出明確將 BCI 框定為預測／預測導向而非反應式的論文。

### Q2: Synonyms + MeSH Terms
**Query:** `("seizure prediction" OR "preictal" OR "pre-ictal") AND (EEG OR "wearable") AND ("deep learning" OR "machine learning" OR LSTM OR transformer)`
**Rationale / 策略說明:** Seizure forecasting is the most mature predictive-BCI subfield; catches the dense literature using preictal/seizure-prediction terminology that Q1 might miss. / 癲癇預測是預測式 BCI 最成熟的子領域；此查詢捕捉以 preictal／seizure prediction 為核心詞彙的大量文獻，避免 Q1 漏網。

### Q3: Mechanism + Theoretical Basis
**Query:** `("predictive coding" OR "active inference" OR "anticipatory neural dynamics" OR "pre-stimulus EEG") AND (attention OR vigilance OR perception OR "cognitive state")`
**Rationale / 策略說明:** Finds the neuroscientific foundation — pre-stimulus oscillations, predictive coding, and anticipatory dynamics that justify why forecasting from neural signals is feasible. / 鎖定神經科學基礎——刺激前振盪、預測編碼、預期性動態等理論，為「神經訊號可前瞻性解碼」提供理論後盾。

### Q4: Methodology + Study Design
**Query:** `(EEG OR physiological) AND ("deep learning" OR "convolutional neural network" OR "recurrent neural network" OR transformer OR "federated learning") AND (forecasting OR prediction) AND (sensitivity OR specificity OR "false prediction rate" OR AUC)`
**Rationale / 策略說明:** Targets rigorous quantitative evaluations — papers reporting standard predictive-performance metrics on real datasets (CHB-MIT, TUSZ, in-home cohorts). / 鎖定量化嚴謹的研究——報告標準預測績效指標並在真實資料集（CHB-MIT、TUSZ、居家世代）上驗證的論文。

### Q5: Cross-Disciplinary
**Query:** `("wearable sensor" OR "multimodal physiological" OR "closed-loop") AND (EEG OR ECG OR accelerometry) AND ("fall prediction" OR "migraine prediction" OR "sleep prediction" OR "vigilance forecasting" OR "drowsiness detection")`
**Rationale / 策略說明:** Broadens to adjacent predictive-health domains (falls, migraine, sleep, driver drowsiness) that share the forecasting paradigm but are rarely framed as BCI — important for a cross-domain positional paper. / 擴展至鄰近預測健康領域（跌倒、偏頭痛、睡眠、駕駛嗜睡），這些領域共用預測典範卻少被歸為 BCI——對跨域立場論文至關重要。

---

> **Checkpoint 1: 初始定向核准**
> Please review the PICO framework and search queries above. / 請檢視上方 PICO 框架與搜尋策略。
> - Are the PICO components accurate? / PICO 各元素是否正確？
> - Any missing keywords or synonyms? / 有遺漏的關鍵字或同義詞嗎？
> - Any off-target dimensions to remove? / 有需要移除的偏離維度嗎？
>
> When ready, greenlight to proceed to `/research-search`.
> 確認後請給予指示，以進入 `/research-search`。
