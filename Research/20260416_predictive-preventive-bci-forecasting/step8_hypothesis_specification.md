---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
step: 8
selected_gap: "GAP_001"
dropped_gaps: ["GAP_002", "GAP_003"]
design_constraint: "Positional-paper context — hypothesis framed as a prospective pilot closed-loop study feasible within a 12–18-month single-centre deployment, not a multi-site RCT"
research_questions: 4
hypotheses: 3
---

# Hypothesis Specification / 假說規格書

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> Selected Gap / 選定缺口: GAP_001 — Preventive Outcome Measurement Gap / 預防性結果測量缺口
> Dropped Gaps / 放棄缺口: GAP_002 (Cross-Domain Methodological Asymmetry / 跨域方法學不對稱), GAP_003 (External Validity & Generalization Landscape / 外部效度與泛化景觀)
> Date / 日期: 2026-04-16

## Executive Summary / 總覽摘要

**English.** The locked research gap — GAP_001 Preventive Outcome Measurement — identifies that the 162-paper evidence base measures *prediction* (sensitivity, specificity, FPR, AUC, lead time) but never *prevention* (reduction in events under a closed-loop intervention), leaving the positional paper's central predictive→preventive bridge as an inferential leap rather than an empirical result. The proposed study closes this gap by deploying a pre-trained, previously-validated predictive BCI model in a single-centre prospective cohort of adults with drug-resistant focal epilepsy, coupling each above-threshold prediction to a pre-specified intervention protocol (user-facing alert + caregiver notification + behavioural safety procedure), and comparing event rate during a 12-week intervention phase against a 4-week individual baseline. This is explicitly a *pilot* study: its contribution is not a new architecture or new benchmark, but the first measurement in this evidence base of whether high-performing offline predictions actually translate into reduced real-world events. A successful result would empirically validate the paradigm the positional paper defends; a null result would sharply constrain the claim that prediction quality is the bottleneck and re-frame the problem as intervention-protocol design.

**繁體中文。** 鎖定之研究缺口——GAP_001 預防性結果測量——指出 162 篇證據基礎測量的是**預測**（敏感度、特異度、FPR、AUC、預測時界），而從未測量**預防**（閉環介入下事件之減量），使 positional paper 核心之「預測→預防」橋樑仍是推論跳躍而非實證結果。本提案研究以將一個預訓練、既有驗證之預測式 BCI 模型部署於一個單中心、針對藥物難治性局灶性癲癇成人之前瞻性世代來閉合此缺口：將每一超閾值預測耦合至預先規定之介入協定（使用者端警報 + 照顧者通知 + 行為安全程序），並將 12 週介入期之事件率與 4 週個體基線期比較。這明確是一個**先導**研究：其貢獻不在於新架構或新標竿，而在於於此證據基礎中**首次**測量高效能離線預測能否實際轉譯為真實世界事件之減量。正向結果將實證 positional paper 所辯護之典範；虛無結果將大幅收緊「預測品質是瓶頸」之宣稱並將問題重新框為介入協定設計。

**Why it matters now / 為何此刻重要.** CHB-MIT 上 96–99% 敏感度 / ≤0.05/h FPR 之飽和區間已持續兩年（`CaoEtAl2026`、`AlkhrijahEtAl2025`、`PhamTran2026`、`WangEtAl2025c`），該領域已具備一個若預防性宣稱有意義則應足以支撐臨床轉譯之效能基質。**在此區間內進一步之標竿競賽在預防性結果被測量之前，幾乎必然是遞減報酬。**

---

## Selected Gap Summary / 選定缺口摘要

**Gap ID:** GAP_001
**Type / 類型:** Measurement + Integration / 測量 + 整合
**Priority Score / 優先分數:** 4.40 (Severity 5 / Novelty 5 / Feasibility 3)

The Tier 1 evidence base reports prediction quality but not prevention outcome; `CaoEtAl2026` reaches 99.54% AUC with 0.01/h FPR, `PhamTran2026` reaches 99.46% sensitivity, `YedurkarEtAl2025` reports end-to-end sensor-to-cloud accuracy of 99.5% — all of which stop at alarm generation, none measures whether those alarms, when linked to interventions, reduce event counts. The methodological distribution (137/162 Computational, 0 Experimental, 2 Observational) reveals the structural reason: the field's default modality cannot, by design, produce preventive-outcome data. Closing this gap therefore requires methodology that is currently under-represented in the literature — prospective, within-subject, intervention-anchored measurement.

Tier 1 證據基礎報告預測品質而非預防結果；`CaoEtAl2026` 達 99.54% AUC 與 0.01/h FPR、`PhamTran2026` 達 99.46% 敏感度、`YedurkarEtAl2025` 報告端對端感測器至雲端準確度 99.5% ——全部止於警報產生，無一測量此等警報連結至介入時能否減少事件數。方法學分佈（137/162 計算、0 實驗、2 觀察）揭示結構性原因：此領域預設之方法學模態無法依設計產生預防性結果資料。因此閉合此缺口需要目前於文獻中代表性不足之方法學——前瞻性、主體內、介入錨定之測量。

---

## Gap Selection Rationale / 缺口選擇理由

| Gap | Status | Composite | Rationale |
|-----|--------|-----------|-----------|
| **GAP_001** | **Locked** | **4.40** | Highest severity × novelty product; attacks the positional paper's central predictive→preventive claim directly. / 嚴重性 × 新穎性乘積最高；直接攻擊 positional paper 核心「預測→預防」宣稱 |
| GAP_002 | Dropped | 4.00 | Cross-domain expansion (migraine, sleep, vigilance) is valuable but presupposes the predictive→preventive bridge is valid in the mature seizure domain first. Deferred as future work once GAP_001 is resolved. / 跨域擴展有價值但預設預測→預防橋樑於成熟癲癇域已成立；俟 GAP_001 解決後作為未來工作延期執行 |
| GAP_003 | Dropped | 3.80 | Generalization-landscape characterization is an empirical substrate problem; it defines how numbers degrade but does not answer the more fundamental prevention question. The prospective cohort in GAP_001 will incidentally produce deployment-regime data as a by-product. / 泛化景觀刻劃是實證基質問題；界定數字衰減方式但未回答更根本之預防問題。GAP_001 之前瞻性世代將附帶產出部署域數據 |

---

## Constraint Adaptation / 約束適應

The original gap is ambitiously framed as a prospective, intervention-anchored measurement study — which in its fullest form would be a multi-site randomized controlled trial. Such a study is out of reach for a positional-paper-anchored pilot. The adapted design is therefore:

原始缺口雄心勃勃地框為前瞻性、介入錨定之測量研究——其完整形式將是多中心隨機對照試驗。此類研究超出以 positional paper 為錨之先導範圍。因此採用以下適應設計：

- **Single-site, within-subject pre/post design** rather than multi-site RCT — each participant serves as own control, allowing causal inference without inter-subject randomization overhead / 單中心、主體內前/後設計取代多中心 RCT——每位受試者自為對照，無需跨主體隨機化開銷.
- **Pre-validated model (no new architecture)** — use a Tier 1 deep-learning architecture (CNN-LSTM-attention hybrid class, e.g., adapted from `CaoEtAl2026` or `AlkhrijahEtAl2025`) that already passes offline benchmark thresholds; the novelty of this study is in *outcome measurement*, not model engineering / 預先驗證模型（無新架構）——採用已通過離線標竿門檻之 Tier 1 深度學習架構（CNN-LSTM-注意力混合類，例如改編自 `CaoEtAl2026` 或 `AlkhrijahEtAl2025`）；本研究新穎性在於**結果測量**而非模型工程.
- **Adults with drug-resistant focal epilepsy** as the target population — the most mature predictive domain in the evidence base, with clinically meaningful event-rate outcomes / 藥物難治性局灶性癲癇成人為目標族群——證據基礎中最成熟之預測域，具臨床意義之事件率結果.
- **16-week total protocol** (4-week baseline, 12-week intervention) feasible within a 12–18 month PhD/positional-paper timeline / 16 週總協定（4 週基線、12 週介入）於 12–18 個月博士／positional paper 時程內可行.

This adaptation does not dilute the gap — it operationalises it. The core measurement (does prediction reduce events?) is preserved; only the scale is constrained to pilot-study magnitudes.

此適應不稀釋缺口——它將缺口操作化。核心測量（預測能否減少事件？）被保留；僅規模被約束至先導研究量級。

---

## Research Questions / 研究問題

### RQ1 (Feasibility/Existence): Can a pre-trained predictive BCI deployed prospectively in ambulatory conditions maintain the per-participant sensitivity and false-prediction-rate envelope established on offline benchmarks? / 預訓練預測式 BCI 於前瞻性門診條件下部署，能否維持離線標竿所建立之個體敏感度與錯誤預測率封包？

**Elaboration.** The first binding constraint on any preventive claim is that the prediction system actually works outside the benchmark dataset. Cross-dataset evidence (`JangEtAl2026` CHB-MIT → SNUH; `LiEtAl2025b` CHB-MIT → MSSM; `KoutsouvelisEtAl2024` subject-specific → subject-independent) shows that 3–20 percentage-point degradations are plausible in the deployment transition. Before any intervention effect can be attributed, RQ1 establishes whether the model is still operational. A positive answer is: per-participant sensitivity ≥ 0.80 and FPR ≤ 0.20/h during the prospective phase, calibrated on each participant's baseline period.

任何預防性宣稱之首個約束條件是：預測系統實際上能於標竿資料集以外運作。跨資料集證據（`JangEtAl2026` CHB-MIT → SNUH；`LiEtAl2025b` CHB-MIT → MSSM；`KoutsouvelisEtAl2024` 主體特異 → 主體無關）顯示部署轉場中 3–20 個百分點衰減是可能的。在任何介入效果被歸因之前，RQ1 確立模型是否仍具運作能力。正向答案為：前瞻期內每位受試者敏感度 ≥ 0.80、FPR ≤ 0.20/h，並在每位受試者基線期上校準。

### RQ2 (Primary Outcome): Does linking above-threshold predictions to a pre-specified intervention protocol reduce the participant-specific event rate during the intervention period compared to a pre-intervention baseline? / 將超閾值預測連結至預先規定之介入協定，能否相較介入前基線，降低介入期間個體特異之事件率？

**Elaboration.** This is the central question of the gap. It operationalises "prevention" as a within-subject rate-ratio (intervention-period events per week ÷ baseline-period events per week). Existing empirical anchors: NeuroPace RNS 2-year clinical registries report 40–70% seizure reduction in drug-resistant focal epilepsy; the positional paper cites this as the invasive-device upper bound. A non-invasive predictive BCI with behaviourally-mediated intervention should plausibly achieve a smaller but non-zero reduction. The directional commitment is that event rate decreases; the magnitude commitment is ≥ 25% median within-subject reduction.

此為此缺口之中心問題。它將「預防」操作化為主體內之率比（介入期每週事件 ÷ 基線期每週事件）。既有實證錨點：NeuroPace RNS 兩年臨床登錄報告於藥物難治性局灶性癲癇中 40–70% 癲癇減量；positional paper 引用此作為侵入性裝置上限。非侵入性預測式 BCI 以行為介導介入應可達較小但非零之減量。方向承諾是事件率下降；幅度承諾是 ≥ 25% 主體內中位數減量。

### RQ3 (Transfer/Secondary): Does the magnitude of within-subject event-rate reduction correlate with (a) predicted-lead-time distribution, (b) per-participant sensitivity, or (c) participant-reported intervention adherence? / 主體內事件率減量之幅度，是否與（a）預測時界分佈、（b）個體敏感度、或（c）受試者回報之介入依從性相關？

**Elaboration.** If RQ2 is confirmed, RQ3 asks what drives the effect. This is a dose-response analysis. Longer lead times allow more complete intervention; higher sensitivity means more events are predicted and preventable; higher adherence means intervention protocols are actually executed. If none of these correlates with reduction magnitude, the effect (if present) is not cleanly attributable to the predictive BCI and an alternative mediator (observation effect, regression to the mean, Hawthorne effect) must be considered.

若 RQ2 獲確認，RQ3 詢問何者驅動此效應。此為劑量-反應分析。較長預測時界允許更完整之介入；較高敏感度意味更多事件被預測及可預防；較高依從性意味介入協定實際執行。若以上皆不與減量幅度相關，則效應（若存在）無法乾淨歸因於預測式 BCI，必須考慮替代中介者（觀察效應、均值回歸、Hawthorne 效應）。

### RQ4 (Mechanism): Which intervention components — behavioural safety procedures, caregiver notification, environmental modification, or rescue medication — mediate the event-rate reduction? / 介入之何種組件——行為安全程序、照顧者通知、環境修改、或救援用藥——中介事件率減量？

**Elaboration.** RQ4 is exploratory. A pilot study is underpowered for clean mediation analysis, but intervention-component logging (which modality was activated on each alert) enables descriptive attribution. This RQ produces hypothesis-generating evidence for a follow-up multi-arm RCT that would test each component independently.

RQ4 為探索性。先導研究無足夠功效進行乾淨之中介分析，但介入組件記錄（各警報時啟動何種模態）允許描述性歸因。此 RQ 產出為後續將獨立測試各組件之多臂 RCT 提供之假說生成性證據。

---

## Hypotheses / 假說

### Primary Hypothesis H1 / 主要假說 H1

**H0 (Null / 虛無假說):**

In adults with drug-resistant focal epilepsy, the within-subject ratio of intervention-period weekly seizure rate to baseline weekly seizure rate is not significantly different from 1 (no reduction).

於藥物難治性局灶性癲癇成人中，介入期每週癲癇率對基線每週癲癇率之主體內比值，與 1 無顯著差異（無減量）。

**H1 (Alternative / 對立假說):**

In adults with drug-resistant focal epilepsy receiving closed-loop predictive-BCI alerts coupled to a pre-specified intervention protocol, the within-subject median ratio of intervention-period weekly seizure rate to baseline weekly seizure rate will be ≤ 0.75 (i.e., a ≥ 25% median within-subject event-rate reduction).

於藥物難治性局灶性癲癇成人且接受連結至預先規定之介入協定之閉環預測式 BCI 警報者，介入期每週癲癇率對基線每週癲癇率之主體內中位數比值將 ≤ 0.75（即 ≥ 25% 主體內中位數事件率減量）。

**Expected Direction & Magnitude / 預期方向與幅度:**

- Direction: decrease (events per week lower in intervention than baseline). Derived from the conceptual predictive→preventive bridge: if predictions are accurate and interventions have non-zero efficacy, event rate must decrease.
- Magnitude anchor ≥ 25%: conservatively derived from the invasive closed-loop neurostimulation literature (NeuroPace RNS registries: 40–70% reduction at 2-year follow-up for a device that responds *after* electrographic seizure onset). A non-invasive predictive system with behavioural intervention should plausibly achieve less than the invasive device floor (40%), but still a clinically meaningful minimum. 25% is the threshold below which clinicians typically treat an intervention as non-clinically-meaningful for drug-resistant epilepsy.
- Cross-reference: `AmiriEtAl2026` reports 68.2% predictive sensitivity at 90-minute horizon — ample lead time for behavioural intervention. `CaoEtAl2026`'s 0.01/h FPR implies ≤ 0.24 false alarms/day, which is below the alarm-habituation threshold documented in `WesalEtAl2026`'s review.

方向：下降（介入期每週事件數低於基線）。源自預測→預防概念橋樑：若預測準確且介入具非零效果，事件率必須下降。
幅度錨定 ≥ 25%：保守源自侵入性閉環神經刺激文獻（NeuroPace RNS 登錄：一於電描記發作**後**反應之裝置於藥物難治性癲癇兩年追蹤減量 40–70%）。非侵入性預測式系統配合行為介入應可達低於侵入性裝置下限（40%）之減量，但仍需達臨床意義之最低值。25% 為藥物難治性癲癇臨床上視為「非臨床意義」之門檻。
交叉參照：`AmiriEtAl2026` 於 90 分鐘時界報告 68.2% 預測敏感度——充足之行為介入時界。`CaoEtAl2026` 之 0.01/h FPR 意味 ≤ 0.24 假警報/日，低於 `WesalEtAl2026` 回顧中記錄之警報習慣化門檻。

**Suggested Statistical Approach / 建議統計方法:**

Primary test: Wilcoxon signed-rank test on within-subject log-rate-ratios (one-sided, α = 0.05), with paired negative-binomial regression as a supporting parametric analysis (accounts for count nature and overdispersion of seizure-count data). Effect size: median rate ratio with 95% bootstrap CI. Pre-registered analysis plan before baseline data collection.

主要檢定：主體內對數率比之 Wilcoxon 符號秩檢定（單尾，α = 0.05），配對負二項式迴歸作為支持性參數分析（考量癲癇計數資料之計數性質與過度離散性）。效果量：中位數率比並附 95% 自助法 CI。於基線資料收集前預先登錄分析計畫。

---

### Secondary Hypothesis H2 / 次要假說 H2

**H0 (Null / 虛無假說):**

Prospective per-participant sensitivity and FPR of the deployed predictive BCI are significantly worse than the offline benchmark envelope — specifically, per-participant sensitivity < 0.80 OR FPR > 0.20/h for ≥ 50% of participants.

所部署預測式 BCI 之前瞻性個體敏感度與 FPR 顯著劣於離線標竿封包——具體為 ≥ 50% 受試者之個體敏感度 < 0.80 或 FPR > 0.20/h。

**H1 (Alternative / 對立假說):**

Per-participant sensitivity ≥ 0.80 AND FPR ≤ 0.20/h will be achieved in ≥ 70% of participants during the 12-week intervention phase, after per-participant baseline calibration.

於經個體基線校準後之 12 週介入期間，≥ 70% 受試者將達成個體敏感度 ≥ 0.80 且 FPR ≤ 0.20/h。

**Expected Direction & Magnitude / 預期方向與幅度:**

- Derived from cross-dataset degradation evidence: `LiEtAl2025b` reports 96.6% → 94.2% (CHB-MIT → MSSM), `JangEtAl2026` reports 97.92% → 94.93% (CHB-MIT → SNUH). A 5–15 percentage-point drop to ambulatory deployment is the realistic band. Target of 0.80 sensitivity preserves clinical utility even at the pessimistic end of this range.
- FPR target 0.20/h derived from `WesalEtAl2026`'s review of alarm-burden tolerance in wearable seizure systems.

源自跨資料集衰減證據：`LiEtAl2025b` 報告 96.6% → 94.2%（CHB-MIT → MSSM），`JangEtAl2026` 報告 97.92% → 94.93%（CHB-MIT → SNUH）。至門診部署之 5–15 個百分點下降為實際區間。0.80 敏感度目標即使於此範圍之悲觀端仍保留臨床效用。
FPR 目標 0.20/h 源自 `WesalEtAl2026` 回顧中穿戴式癲癇系統之警報負擔耐受性。

**Suggested Statistical Approach / 建議統計方法:**

One-sample binomial test on the proportion of participants meeting the joint criterion (sensitivity ≥ 0.80 AND FPR ≤ 0.20/h), tested against the null proportion of 0.50 and the alternative of 0.70.

主體達成聯合準則比例之單樣本二項式檢定（敏感度 ≥ 0.80 且 FPR ≤ 0.20/h），針對 0.50 虛無比例與 0.70 對立比例檢定。

---

### Tertiary Hypothesis H3 / 第三假說 H3

**H0 (Null / 虛無假說):**

The within-subject rate-reduction magnitude (1 − rate-ratio) has no significant correlation with per-participant median predicted lead time, per-participant sensitivity, or per-participant intervention adherence.

主體內率減量幅度（1 − 率比）與個體中位數預測時界、個體敏感度、個體介入依從性皆無顯著相關。

**H1 (Alternative / 對立假說):**

The within-subject rate-reduction magnitude positively correlates (Spearman ρ > 0.30, p < 0.05) with at least one of the three candidate mediators — median predicted lead time, per-participant sensitivity, or intervention adherence — indicating that the reduction effect is driven by the predictive-intervention mechanism rather than non-specific factors.

主體內率減量幅度與三個候選中介者之至少一個——中位數預測時界、個體敏感度、或介入依從性——呈正相關（Spearman ρ > 0.30，p < 0.05），顯示減量效應由預測-介入機制驅動而非非特異性因素。

**Expected Direction & Magnitude / 預期方向與幅度:**

Direction: positive (more lead time / higher sensitivity / higher adherence → greater reduction). Magnitude threshold ρ > 0.30 derived from pilot-study conventions for "meaningful but non-definitive" correlations; `AmiriEtAl2026`'s horizon-decay curve (89.3% → 68.2% across 90 min) suggests lead-time effects are measurable within the horizon range used here.

方向：正向（更長時界／更高敏感度／更高依從性 → 更大減量）。幅度門檻 ρ > 0.30 源自先導研究對「有意義但非決定性」相關之慣例；`AmiriEtAl2026` 之時界衰減曲線（89.3% → 68.2% 跨 90 分鐘）暗示於此處所用時界範圍內時界效應是可測量的。

**Suggested Statistical Approach / 建議統計方法:**

Spearman rank correlation (non-parametric, appropriate for small N and ordinal/ratio mixed predictors), with Bonferroni correction across the three candidate mediators (α_corrected = 0.0167).

Spearman 秩相關（非參數、適合小 N 與順序／比率混合預測因子），三個候選中介者之 Bonferroni 校正（α_corrected = 0.0167）。

---

## Scope Boundaries / 範圍界定

### IN Scope / 範圍內

| Dimension / 維度 | Specification / 規格 |
|-----------------|---------------------|
| **Population / 族群** | Adults aged 18–65 with drug-resistant focal epilepsy (≥ 2 failed anti-seizure medications, ≥ 2 seizures/month average over prior 3 months), medically stable, capable of informed consent. N = 20 participants (pilot scale). / 成年 18–65 歲藥物難治性局灶性癲癇（≥ 2 個抗癲癇藥物失敗、過去 3 個月平均 ≥ 2 次/月癲癇發作）、病況穩定、具知情同意能力。N = 20 位受試者（先導規模）。 |
| **Intervention / Method / 介入/方法** | Wearable or minimal-channel EEG (≤ 8 channels) + pre-trained CNN-LSTM-attention prediction model (architectural class validated in `CaoEtAl2026` / `AlkhrijahEtAl2025`), running on a companion smartphone with pre-specified intervention protocol on above-threshold alert: (a) user-facing audiovisual warning, (b) caregiver SMS notification, (c) behavioural safety checklist, (d) optional pre-prescribed rescue benzodiazepine per participant's neurologist. / 穿戴式或最少通道 EEG（≤ 8 通道）＋ 預訓練 CNN-LSTM-注意力預測模型（架構類別於 `CaoEtAl2026` / `AlkhrijahEtAl2025` 已驗證），於伴隨智慧型手機上執行；超閾值警報時啟動預先規定介入協定：（a）使用者端視聽警告、（b）照顧者簡訊通知、（c）行為安全清單、（d）依受試者神經科醫師處方選用之預先開立救援苯二氮平類藥物。 |
| **Comparison / Control / 對照/控制** | Within-subject pre-intervention baseline: 4 weeks of EEG + seizure diary collection *without* intervention (alerts silenced), followed by 12-week intervention phase. Each participant is their own control; pre/post rate ratios computed per participant. / 主體內介入前基線：4 週 EEG ＋ 癲癇日誌收集，**無**介入（警報靜音），續接 12 週介入期。每位受試者自為對照；每位受試者計算前/後率比。 |
| **Primary Outcome / 主要結果** | Within-subject weekly seizure-rate ratio (intervention weeks / baseline weeks), reported as clinician-adjudicated events from combined EEG + seizure diary + caregiver reports. / 主體內每週癲癇率比（介入週 / 基線週），以結合 EEG ＋ 癲癇日誌 ＋ 照顧者報告之臨床醫師判定事件報告。 |
| **Secondary Outcome / 次要結果** | (i) Per-participant prospective sensitivity and FPR vs. offline calibration; (ii) intervention adherence (protocol-execution rate per alert); (iii) per-participant quality of life (QOLIE-31 at baseline, week 8, week 16); (iv) alert-lead-time distribution. / （i）個體前瞻性敏感度與 FPR 對比離線校準；（ii）介入依從性（每警報協定執行率）；（iii）個體生活品質（QOLIE-31 於基線、週 8、週 16）；（iv）警報預測時界分佈。 |
| **Setting / 場域** | Ambulatory / home-based with weekly remote clinical check-ins via telehealth; enrolment and final assessment on-site at a single epilepsy monitoring unit (EMU). / 門診／家庭為主，每週遠距臨床檢查；收案與最終評估於單一癲癇監測單位（EMU）進行。 |
| **Design / 設計** | Prospective single-centre within-subject pre/post cohort study with embedded closed-loop intervention. Preregistered analysis plan. / 前瞻性單中心主體內前/後世代研究，嵌入閉環介入。分析計畫預先登錄。 |
| **Timeframe / 時間框架** | 4-week baseline + 12-week intervention = 16 weeks per participant. Total enrolment window 6 months, analysis + writeup 6 months — 12 months total. / 每位受試者 4 週基線 ＋ 12 週介入 ＝ 16 週。收案窗期 6 個月，分析與撰寫 6 個月——總計 12 個月。 |

### OUT Scope / 範圍外

| Exclusion / 排除項目 | Rationale / 學術理由 |
|---------------------|---------------------|
| Non-seizure domains (migraine, sleep SWS, falls, vigilance) / 非癲癇域（偏頭痛、睡眠 SWS、跌倒、警覺度） | Seizure prediction is the only domain in the evidence base with sufficient methodological maturity (14 Tier 1 full texts, offline benchmarks at 96–99% sensitivity) to support a feasible closed-loop pilot. Cross-domain extension (GAP_002) is deferred to future work. / 癲癇預測是證據基礎中唯一具足夠方法學成熟度（14 篇 Tier 1 全文、離線標竿 96–99% 敏感度）以支撐可行閉環先導之域。跨域延伸（GAP_002）延期至未來工作。 |
| Generalization-landscape factorial evaluation / 泛化景觀因子評估 | GAP_003 requires coordinated multi-dataset access and exceeds a single-site pilot's scope. The prospective cohort will incidentally generate single-dataset deployment data; full factorial is deferred. / GAP_003 需協調多資料集存取並超出單中心先導範圍。前瞻性世代將附帶產出單資料集部署資料；完整因子組合延期。 |
| New prediction architecture development / 新預測架構開發 | The contribution is preventive-outcome measurement, not model novelty. Using a pre-validated architecture isolates the study's causal contribution (does the intervention loop work?) from confounding model-engineering claims. / 貢獻是預防性結果測量而非模型新穎性。採用已驗證架構將本研究之因果貢獻（介入循環能否運作？）自模型工程宣稱之干擾中分離。 |
| Pediatric populations (< 18 yo) / 小兒族群（< 18 歲） | Seizure semiology, EEG signatures, and intervention ethics differ substantially; separate study required with dedicated IRB protocol. / 癲癇症狀學、EEG 訊號特徵與介入倫理差異顯著；需專屬 IRB 協定之獨立研究。 |
| Invasive closed-loop systems (RNS, DBS) / 侵入性閉環系統（RNS、DBS） | The positional paper's PICO frames non-invasive / minimally invasive BCIs; invasive neuromodulation is a well-developed parallel literature (NeuroPace etc.) with its own regulatory and methodological standards. / positional paper 之 PICO 框定非侵入性／微創 BCI；侵入性神經調控為具其自身監管與方法學標準之獨立發展文獻（NeuroPace 等）。 |
| Long-term (> 12 months) outcome assessment / 長期（> 12 個月）結果評估 | Pilot feasibility scope. Durability of preventive effect requires a follow-on extension trial once feasibility is established. / 先導可行性範圍。預防效應之持久性需於可行性確立後之後續延伸試驗。 |
| Active comparator arm (e.g., sham alert vs. real alert) / 主動對照臂（如假警報對真警報） | A within-subject pre/post design is chosen for pilot feasibility; a sham-controlled two-arm RCT is the logical follow-on if H1 is supported. / 選擇主體內前/後設計為先導可行性；若 H1 獲支持，假警報對照雙臂 RCT 為合邏輯之後續。 |
| Mechanism dissection via single-component intervention arms / 經單組件介入臂之機制分解 | RQ4 is exploratory and underpowered for clean mediation. A four-arm factorial RCT testing each intervention component independently is the follow-on study (pre-specified in the protocol). / RQ4 為探索性且無足夠功效進行乾淨中介分析。獨立測試各介入組件之四臂因子 RCT 為後續研究（於協定中預先規定）。 |

### Scope Rationale / 範圍邏輯

**English.** The scope is deliberately asymmetric: IN scope is tightly specified to a single population, single domain, single model class, single-centre within-subject design — everything needed to produce one clean preventive-outcome measurement. OUT scope is deliberately *expansive* and each exclusion is a *testable future study*. This structure makes the moat defensible: a reviewer asking "why didn't you also do X?" has a ready answer ("X is deferred to follow-on study Y, which depends on the feasibility signal this study produces"). The philosophical commitment is that a single well-measured preventive outcome, even in a narrow slice, is more valuable than a broad study whose methodology cannot support causal prevention inference at all — which is precisely the current state of the literature per the SOTA review.

**繁體中文。** 範圍有意採取不對稱：IN 範圍緊縮規格化於單一族群、單一域、單一模型類別、單中心主體內設計——恰好是產生**一次**乾淨之預防性結果測量所需之全部。OUT 範圍有意**擴張**，每一排除項皆為**可測試之未來研究**。此結構使護城河可辯護：審稿人詢問「為何您未同時做 X？」時有現成答案（「X 延期至後續研究 Y，其依賴本研究產出之可行性訊號」）。哲學承諾是：即使於狹窄切片中，一次充分測量之預防性結果，相較於方法學根本無法支撐因果預防推論之廣泛研究——即 SOTA 綜述所呈現之文獻現況——更具價值。

---

## Conceptual Framework / 概念框架

```
┌─────────────────────────────────────────────────────────────────────────┐
│  PHASE 1: BASELINE (Weeks 1–4, no intervention)                         │
│  ───────────────────────────────────────────────────────────────────    │
│  Participant wears EEG + carries smartphone                             │
│  Seizure diary + caregiver reports logged                               │
│  Prediction model runs silently (alerts suppressed)                     │
│  → Output: individual baseline seizure rate λ_baseline (events/week)    │
│  → Output: per-participant offline-equivalent sensitivity / FPR         │
│  → Output: per-participant threshold calibration                        │
└──────────────────────────────┬──────────────────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────────────────┐
│  PHASE 2: INTERVENTION (Weeks 5–16, closed-loop active)                 │
│  ───────────────────────────────────────────────────────────────────    │
│  EEG stream → Prediction model → Threshold test                         │
│                                        │                                │
│                                        ▼ (if above threshold)           │
│                              ┌──── ALERT TRIGGER ────┐                  │
│                              │                        │                 │
│                  Smartphone UI             Caregiver SMS                │
│                  warning + checklist       (+ geo-location)             │
│                              │                        │                 │
│                              ▼                        ▼                 │
│                  Participant executes:    Caregiver monitors /          │
│                  (a) safety position      assists as protocol           │
│                  (b) environment mod       dictates                     │
│                  (c) rescue meds (optional, per neurologist)            │
│                                        │                                │
│                                        ▼                                │
│                         INTERVENTION LOG + OUTCOME ADJUDICATION         │
│  → Output: intervention-period seizure rate λ_intervention              │
│  → Output: per-alert intervention-component log                         │
│  → Output: prospective sensitivity / FPR                                │
└──────────────────────────────┬──────────────────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────────────────┐
│  PHASE 3: ANALYSIS                                                      │
│  ───────────────────────────────────────────────────────────────────    │
│  H1: Wilcoxon signed-rank on log(λ_intervention / λ_baseline) per N=20  │
│  H2: Binomial test on proportion meeting sensitivity × FPR criteria     │
│  H3: Spearman ρ of (1 − rate ratio) vs. lead time, sensitivity, adher.  │
└─────────────────────────────────────────────────────────────────────────┘
```

**English.** The architecture is deliberately minimal. Every component is either (a) already validated in the Tier 1 evidence base (prediction model, EEG wearable), (b) standard clinical practice (seizure diary, QOLIE-31, caregiver adjudication), or (c) routine smartphone/communication infrastructure. The novelty is entirely in the *closing of the loop* between prediction and intervention, and in the *measurement of the outcome downstream of that loop*. By keeping each component standard, the study isolates the causal contribution of loop-closure itself.

**繁體中文。** 架構有意採取最小化。每一組件皆為：（a）Tier 1 證據基礎中已驗證者（預測模型、EEG 穿戴），（b）標準臨床實作（癲癇日誌、QOLIE-31、照顧者判定），或（c）常規智慧型手機／通訊基礎設施。新穎性完全在於預測與介入之間**閉環**之閉合、以及該閉環下游**結果測量**。藉由保持各組件標準化，本研究將閉環本身之因果貢獻分離。

---

## Risk Assessment / 風險評估

| Risk / 風險 | Likelihood / 可能性 | Impact / 影響 | Mitigation / 緩解策略 |
|------------|-------------------|-------------|---------------------|
| Insufficient recruitment of drug-resistant focal epilepsy cohort / 藥物難治性局灶性癲癇世代招募不足 | Medium | High | Partner with a high-volume EMU; pre-screen from existing registry; extend enrolment window to 9 months if < 15 by month 6 / 與高流量 EMU 合作；自既有登錄預篩；若 6 個月僅招收 < 15 位則延長至 9 個月 |
| Cross-dataset model degradation below H2 thresholds (prospective sensitivity < 0.80 for majority) / 模型跨資料集衰減低於 H2 門檻（多數受試者前瞻敏感度 < 0.80） | Medium-High | High for H1 | Per-participant baseline calibration phase (4 weeks) specifically to adapt thresholds; pre-registered fall-back analysis if H2 fails — report H1 stratified by whether H2 held for each participant / 每位受試者基線校準階段（4 週）專為閾值自適應；若 H2 失敗則預先登錄之退守分析——按 H2 於各受試者是否成立分層報告 H1 |
| Hawthorne effect / observation bias confound (participants change behaviour simply because they know they're being monitored) / Hawthorne 效應（受試者因知道被監測而改變行為） | High | Medium | Baseline phase with identical monitoring but alerts silenced — any Hawthorne effect is present in both phases and subtracts out of the within-subject ratio; explicit debrief assessing behaviour-change awareness / 基線期採用相同監測但警報靜音——任何 Hawthorne 效應於兩階段皆存在並於主體內率比中被抵消；顯性匯報評估行為改變意識 |
| Alert burden / habituation degrading adherence over 12 weeks / 警報負擔導致 12 週中依從性衰減 | Medium | Medium | Pre-registered adherence monitoring in RQ3 / H3; weekly check-in adjusts threshold if per-participant FPR exceeds habituation band (> 0.3/h); documented protocol for threshold reset / 預先登錄之依從性監測於 RQ3 / H3；每週檢查若個體 FPR 超過習慣化帶（> 0.3/h）則調整閾值；閾值重設之記錄協定 |
| Adverse event during seizure (e.g., injury during unpredicted event) / 癲癇期間不良事件（如未預測事件期間受傷） | Low (compared to baseline risk inherent to the condition) | High | Standard epilepsy safety protocols unchanged; 24/7 on-call neurologist; participants retain all standard care pathways; IRB-approved adverse-event reporting chain / 標準癲癇安全協定不變；24/7 值班神經科醫師；受試者保留所有標準照護路徑；IRB 核准之不良事件通報鏈 |
| Insufficient within-subject statistical power with N = 20 / N = 20 之主體內統計功效不足 | Medium | Medium | Pre-registered power calculation assuming Cohen's dz = 0.6 (moderate-to-large effect), N = 20 yields 80% power for Wilcoxon signed-rank at α = 0.05 one-sided. If interim check at N = 15 shows dz < 0.4, document as null / 預先登錄之功效計算假設 Cohen's dz = 0.6（中大效應量），N = 20 於單尾 α = 0.05 之 Wilcoxon 符號秩達 80% 功效。若 N = 15 時中期檢查顯示 dz < 0.4，記錄為虛無 |

---

## Gap-to-Hypothesis Traceability / 缺口到假說追溯

| Element / 元素 | Source / 來源 | Evidence / 證據 |
|---------------|-------------|----------------|
| RQ1 (feasibility) | GAP_003 residual signal within GAP_001 | Cross-dataset degradation: `JangEtAl2026` (CHB-MIT 97.92% → SNUH 94.93%), `LiEtAl2025b` (CHB-MIT 96.6% → MSSM 94.2%), `KoutsouvelisEtAl2024` (subject-specific → subject-independent 20-point drop) |
| RQ2 (primary) | GAP_001 description — no Tier 1 paper measures prevention | Positional paper's predictive → preventive claim; Step 6 SOTA Executive Summary |
| RQ3 (transfer) | GAP_001 + lead-time literature | `AmiriEtAl2026` 89.3% → 68.2% across 90-min horizon; `CaoEtAl2026` 0.01/h FPR |
| RQ4 (mechanism) | GAP_001 Integration sub-type | `WesalEtAl2026` multimodal-intervention review; positional paper's component taxonomy |
| H1 direction | Conceptual predictive → preventive bridge | Any non-zero-efficacy intervention on accurate predictions must reduce events |
| H1 magnitude (≥ 25%) | NeuroPace RNS invasive-device anchor (40–70% at 2 yr); non-invasive should be less | Clinical threshold for drug-resistant focal epilepsy; SOTA review Theme 4 `YedurkarEtAl2025` / `CaoEtAl2026` FPR envelope enables tolerable alarm burden |
| H2 thresholds (sens ≥ 0.80, FPR ≤ 0.20/h) | Cross-dataset degradation band + alarm tolerance | `LiEtAl2025b` 5–15 pp drop band; `WesalEtAl2026` alarm burden review |
| H3 correlation threshold (ρ > 0.30) | Pilot-convention for meaningful correlation | `AmiriEtAl2026` horizon decay curve demonstrates measurable lead-time effect |
| IN: Adults drug-resistant focal epilepsy | GAP_001 feasibility constraint + PICO population | Mature predictive domain (14 Tier 1 seizure papers); clinical registry infrastructure exists |
| IN: Pre-trained CNN-LSTM-attention | Methodological maturity signal | `CaoEtAl2026`, `AlkhrijahEtAl2025`, `LiEtAl2025b` — dominant Tier 1 architecture class |
| OUT: Non-seizure domains | GAP_002 dropped | Deferred to follow-on cross-domain study |
| OUT: Factorial generalization | GAP_003 dropped | Deferred; exceeds single-site pilot scope |
| OUT: New architecture | Scope discipline | Contribution is measurement, not model engineering |
| OUT: Sham-controlled arm | Pilot feasibility (Feasibility = 3) | Follow-on two-arm RCT is the logical continuation |

---

> **Checkpoint 4: 護城河最終確認 / Moat Final Confirmation**
>
> **English.** Review the IN/OUT boundaries above. Verify that:
> 1. Every OUT exclusion has an academically defensible rationale (each row in the OUT table must answer "why didn't you also do X?")
> 2. The scope matches your actual time, budget, and resource constraints — specifically, a 12–18-month timeline with access to an epilepsy monitoring unit and ~20 drug-resistant focal epilepsy participants
> 3. The hypotheses are testable with your available methods and data — the pre-trained model class (CNN-LSTM-attention) is a commodity architecture; the intervention protocol is standard clinical practice; the statistical tests are pre-registrable
> 4. The magnitude commitment in H1 (≥ 25% within-subject median event-rate reduction) is defensible under your reading of the SOTA evidence
>
> **繁體中文。** 請審核上述 IN/OUT 邊界。確認：
> 1. 每個 OUT 排除項目都有可在學術上辯護的理由（OUT 表中每一列必須回答「為何您未同時做 X？」）
> 2. 範圍符合您實際的時間、預算與資源限制——具體為 12–18 個月時程，具癲癇監測單位存取權與 ~20 位藥物難治性局灶性癲癇受試者
> 3. 假說可用您現有方法與資料測試——預訓練模型類別（CNN-LSTM-注意力）為商品化架構；介入協定為標準臨床實作；統計檢定可預先登錄
> 4. H1 中之幅度承諾（≥ 25% 主體內中位數事件率減量）於您對 SOTA 證據之解讀下可辯護
>
> **To proceed, confirm: "Scope approved" — then I'll finalise the journal recommendations and you can move to `/research-write`.**
> **請確認：「範圍核准」——然後我將完成期刊推薦，您可進入 `/research-write` 階段。**
>
> **If you want to revise / 若您希望修訂：**
> - Widen / narrow IN scope (e.g., different population, domain, N) / 擴/縮 IN 範圍（如不同族群、域、N）
> - Revise H1 magnitude threshold (e.g., ≥ 20% or ≥ 30% instead of ≥ 25%) / 修訂 H1 幅度門檻（如 ≥ 20% 或 ≥ 30% 取代 ≥ 25%）
> - Change study design (e.g., observational-only, no intervention; or add sham arm) / 變更研究設計（如純觀察無介入；或加假警報臂）
> - Add or remove an OUT exclusion / 新增或移除 OUT 排除項目
>
> Just tell me the change and I'll regenerate this step. / 告知變更後我將重新生成此步驟。

---

Files / 檔案: `step8_hypothesis_specification.md`, `step8_journal_recommendations.md`
Next step / 下一步: Review journal recommendations, then `/research-write` after Checkpoint 4 approval
