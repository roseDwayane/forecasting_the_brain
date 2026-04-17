---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
step: 7
gaps_identified: 3
scoring_weights: "severity=0.40, novelty=0.30, feasibility=0.30"
---

# Gap Analysis / 研究缺口分析

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> 預測性與預防性腦機介面：從神經與生理訊號預測認知狀態與不良健康事件
> Evidence base / 證據基礎: 162 screened papers, 24 Tier 1 full texts, 5 themes synthesised in Step 6
> Date / 日期: 2026-04-16

## Executive Summary / 總覽摘要

Three critical gaps emerge from cross-theme synthesis of the 162-paper shortlist. Each is backed by specific quantitative evidence in the SOTA review, classified under the five-type taxonomy (Methodological / Population / Measurement / Temporal / Integration), and scored on severity, novelty, and feasibility. The gaps are ordered by composite priority score — the highest-scoring gap is structurally the most consequential for the positional paper's central claim (that BCIs can shift from reactive detection toward predictive prevention), while the second and third gaps define flanking problems that any focused study must navigate around.

跨主題綜整 162 篇精選清單後，三個關鍵缺口浮現。每一缺口皆由 SOTA 綜述中具體之定量證據支撐，依五類分類法（方法學／族群／測量／時序／整合）歸類，並於嚴重性、新穎性與可行性三軸上計分。各缺口依綜合優先分數排序——最高分缺口於結構上對 positional paper 核心主張（BCI 可從反應式偵測轉向預測式預防）最具後果，而第二與第三缺口定義任何聚焦研究必須繞行的側翼問題。

---

## GAP_001: Preventive Outcome Measurement Gap / 預防性結果測量缺口

### Description / 描述

The entire Tier 1 evidence base measures *prediction quality* (sensitivity, specificity, FPR, AUC, lead time) but not *prevention outcome* (reduction in seizure count, fall events, migraine attacks, or vigilance-lapse incidents under a closed-loop intervention). The positional paper frames predictive BCIs as the foundation for preventive intervention, yet no Tier 1 paper in this collection operationalises the bridge from "we predicted it" to "because we predicted it, it happened less often." The result is that the literature's strongest empirical claim — that CHB-MIT-trained models reach 99.54% AUC with 0.01/h FPR (`CaoEtAl2026`) — is a claim about detection of pre-ictal states, not about prevention of seizures. The predictive → preventive bridge remains an inferential leap rather than an empirically demonstrated transition.

整個 Tier 1 證據基礎測量的是**預測品質**（敏感度、特異度、FPR、AUC、預測時界），而非**預防結果**（閉環介入下癲癇發作次數、跌倒事件、偏頭痛發作或警覺度下降事件的減少量）。positional paper 將預測式 BCI 框為預防介入的基礎，然此精選清單中沒有任一篇 Tier 1 論文將「我們預測到了」至「因為預測到了，所以發生頻率降低」的橋樑操作化。結果是此領域最強之實證宣稱——CHB-MIT 訓練模型達 99.54% AUC、0.01/h FPR（`CaoEtAl2026`）——是關於預發作狀態之偵測宣稱，而非關於癲癇預防之宣稱。預測至預防之橋樑仍是推論上的跳躍，而非經實證之過渡。

### Gap Type / 缺口類型

**Primary: Measurement gap / 主要：測量缺口** — the outcome variable that would close the predictive-to-preventive loop (prevented event count under intervention) is not measured in any Tier 1 paper.
**Secondary: Integration gap / 次要：整合缺口** — prediction pipelines and intervention protocols (stimulation, alert, behavioural cueing) are not integrated into a single evaluable system.

### Supporting Evidence / 支持證據

- `CaoEtAl2026` — 99.54% AUC, 0.01/h FPR on CHB-MIT; paper's contribution is the knowledge-distilled model, not any downstream outcome trial / 論文貢獻為知識蒸餾模型，無下游結果試驗.
- `PhamTran2026` (EEG-Titans) — 99.46% sensitivity on CHB-MIT; preictal detection only, no closed-loop intervention arm / 僅預發作偵測，無閉環介入組.
- `YedurkarEtAl2025` (SPA-IoT) — 99.5% accuracy / 98.3% sensitivity / 0.045 FPR with full sensor-to-cloud pipeline; the paper stops at alarm generation, not at alarm-triggered intervention outcome / 於警報產生停止，無警報觸發介入之結果.
- `AmiriEtAl2026` (PI-GNN) — 89.3% sensitivity with 90-min horizon; horizon is quantified, prevention impact at that horizon is not / 預測時界已量化，但該時界下之預防影響未量化.
- `MaioraEtAl2024` (fall prediction) — 0.83 accuracy, 0.73 AUC on older-adult IMU; no downstream fall-reduction RCT / 無下游跌倒減量 RCT.
- SOTA review Section *Methodology Legend*: 0 papers tagged "Experimental" and only 2 "Observational" out of 162 — the methodological basis for preventive-outcome evaluation (RCT, stepped-wedge, before-after cohort) is structurally absent / 預防性結果評估的方法學基礎（RCT、階梯楔入、前後世代）結構性缺席.

### Counter-Evidence / 反證

- `WesalEtAl2026` (wearable seizure detection review) discusses clinical utility and false-alarm burden, but as a review it surveys existing empirical literature rather than reporting a preventive-outcome study itself / 作為回顧論文，其檢視既有實證文獻而非報告預防性結果研究.
- The positional paper cites `NasseriEtAl2021` (wrist-worn LSTM ambulatory seizure forecasting) and `Beniczky 2020` (Step 2 hub) as evidence of the preventive trajectory, but both papers likewise report prediction metrics, not prevention metrics / 皆報告預測指標，非預防指標.
- Closed-loop responsive neurostimulation (RNS) systems (NeuroPace etc.) do report seizure-reduction outcomes in the clinical-device literature — but those systems sit outside the "predictive BCI from neural signals + deep learning" frame that this review captures, and none of their recent evaluations are in the Tier 1 set / RNS 閉環響應式神經刺激系統之癲癇減量結果存在於臨床裝置文獻，但位於本綜述框架之外.

### Why It Matters / 為何重要

This gap directly threatens the positional paper's core argument. If the literature only demonstrates prediction quality but never measures prevention, the claim that BCIs are moving "from reactive detection to predictive prevention" is programmatic rather than demonstrated. A focused study that (i) deploys a prediction model in a prospective cohort, (ii) triggers an intervention (alert, stimulation, behavioural cue) on each above-threshold prediction, and (iii) measures event-rate reduction against a pre-intervention baseline would be the first Tier 1 empirical bridge between the two halves of the paradigm. Without such a study, the paradigm remains a methodological aspiration.

此缺口直接威脅 positional paper 之核心論證。若文獻僅展示預測品質而從未測量預防結果，則「BCI 從反應式偵測轉向預測式預防」之宣稱是綱領性的而非經實證的。一個聚焦研究若（i）於前瞻性世代中部署預測模型、（ii）於每一超閾值預測觸發介入（警報、刺激、行為提示）、（iii）相對介入前基線測量事件率減少，將是此典範兩半間首個 Tier 1 實證橋樑。無此研究，典範仍是方法學上的願景。

### Priority Score / 優先分數

| Axis / 軸 | Score | Rationale |
|----------|-------|-----------|
| Severity / 嚴重性 | **5** | Threatens the positional paper's central predictive→preventive claim; 0 T1 papers close this gap / 威脅核心主張，T1 論文完全未覆蓋 |
| Novelty / 新穎性 | **5** | Despite field self-labelling as "preventive", no Tier 1 paper in this collection measures prevention outcomes / 儘管領域自稱「預防性」，本精選清單中無 T1 論文測量預防結果 |
| Feasibility / 可行性 | **3** | A prospective closed-loop trial is well-defined but resource-intensive (multi-month cohort, IRB, intervention protocol design) / 前瞻性閉環試驗定義明確但資源密集 |

**Composite / 綜合分**: 5 × 0.40 + 5 × 0.30 + 3 × 0.30 = 2.00 + 1.50 + 0.90 = **4.40**

---

## GAP_002: Cross-Domain Methodological Asymmetry Gap / 跨域方法學不對稱缺口

### Description / 描述

The positional paper frames five parallel prediction domains — seizure, sleep (SWS), migraine, fall, vigilance/drowsiness — as co-equal foundations of the predictive-BCI paradigm. The 162-paper evidence base does not support this parallel framing. Seizure prediction claims 83 papers and 14 Tier 1 full texts; migraine prediction claims 2 papers and 0 Tier 1 full texts; sleep forecasting claims 7 papers and 0 Tier 1 full texts; vigilance/drowsiness claims 4 papers and 0 Tier 1 full texts; predictive-coding/pre-stimulus claims 3 papers and 0 Tier 1 full texts. The seizure-to-migraine ratio alone is ~40:1. What the positional paper presents as a five-pillar paradigm is, in the evidence base, a one-pillar-plus-four-sparse-satellites structure. The four satellite domains have no agreed benchmark dataset, no consensus architecture, and no Tier 1 primary study in this shortlist.

positional paper 將五個平行預測域——癲癇、睡眠（SWS）、偏頭痛、跌倒、警覺度／嗜睡——框為預測式 BCI 典範之等位基礎。162 篇證據基礎並不支持此平行框架。癲癇預測計 83 篇，14 篇 T1 全文；偏頭痛預測計 2 篇，0 篇 T1 全文；睡眠預測計 7 篇，0 篇 T1 全文；警覺度／嗜睡計 4 篇，0 篇 T1 全文；預測編碼／預刺激計 3 篇，0 篇 T1 全文。僅癲癇對偏頭痛之比例即約 40:1。positional paper 呈現為五柱典範之結構，於證據基礎中實為一柱加四稀疏衛星之結構。四個衛星域皆無共識標竿資料集、無共識架構、於本精選清單中亦無 T1 主要研究。

### Gap Type / 缺口類型

**Primary: Population gap / 主要：族群缺口** — the target populations of the four satellite domains (migraine sufferers, sleep-disordered adults, vigilance-critical workers, perceptual-inference subjects) are structurally under-studied in the BCI-prediction literature.
**Secondary: Methodological gap / 次要：方法學缺口** — no established benchmark, protocol, or architecture consensus in these domains prevents cumulative progress.

### Supporting Evidence / 支持證據

- SOTA review Theme 5 *Key Results*: only `MaioraEtAl2024` provides a T1 full-text anchor (fall prediction, 0.83 accuracy on IMU); no T1 full text for sleep, vigilance, migraine, or predictive coding / 跌倒有 T1 錨點，其餘四域皆無.
- Step 2 cluster counts: `seizure_prediction` 107 papers vs. `migraine_headache` 3 papers vs. `sleep_forecasting` 11 papers vs. `vigilance_drowsiness` 15 papers vs. `predictive_coding` 21 papers (raw cluster counts before Step 3 screening) — the asymmetry is present from the search stage / 不對稱於搜尋階段即存在.
- SOTA review *Theme 5 Debates*: "migraine prediction has no equivalent benchmark and no consensus architecture" / 「偏頭痛預測無對等標竿亦無共識架構」.
- SOTA review *Theme 5 Dominant Methods*: sleep forecasting "most papers treating it as a classification problem rather than a true forecasting problem" — the framing itself is non-predictive / 多數論文將其視為分類問題而非真正預測問題，框架本身即非預測性.
- Methodology distribution: 137/162 = 85% Computational, concentrated in seizure prediction; the non-seizure domains disproportionately contain the review and theoretical papers (Theme 5 contains 12 reviews out of 162 total reviews) / 方法學分佈顯示非癲癇域不成比例地集中於回顧與理論論文.

### Counter-Evidence / 反證

- `MaioraEtAl2024` (fall prediction) demonstrates that the seizure-prediction playbook (BiLSTM + multimodal sensing) transfers to at least one satellite domain, suggesting the satellites are *immature* rather than *unattackable* / 至少一衛星域（跌倒）之遷移已實證，暗示衛星域是「尚未成熟」而非「不可攻擊」.
- `WesalEtAl2026` (wearable seizure detection/prediction review) and `Al-QuraishiEtAl2024` (driver-state monitoring review) explicitly describe adaptable methodology for cross-domain deployment — reviews are present even where primary studies are sparse / 即使主要研究稀疏，可適應之跨域方法學回顧已存在.
- The 3-paper predictive-coding cluster (`BalarKapila2025` and peers) provides a theoretical scaffold (free-energy, active inference) that could, in principle, unify the satellite domains under a common generative model — the gap may be less "no theory" and more "theory not operationalised" / 預測編碼簇提供理論骨架，缺口可能是「理論未操作化」而非「無理論」.

### Why It Matters / 為何重要

This gap determines whether the positional paper's paradigm claim generalises or remains seizure-specific. If only seizure prediction has matured, then the paper is effectively an argument about *one* predictive BCI that happens to have cross-domain rhetorical packaging. A focused study that ports a mature seizure-prediction architecture (Theme 1 CNN-LSTM-attention hybrid, or Theme 2 SSL-pretrained backbone) to one satellite domain — with rigorous benchmark construction, cross-subject validation, and clinical-outcome framing — would concretely test whether the paradigm generalises. Migraine prediction is the highest-leverage target because it is the sparsest (~40:1 asymmetry) and has clear clinical stakes (attack prevention via pre-symptomatic warning).

此缺口決定 positional paper 之典範宣稱能否泛化或仍癲癇特異。若僅癲癇預測已成熟，則此論文實質是關於**一個**預測式 BCI 恰好具跨域修辭包裝的論證。一個聚焦研究若將成熟癲癇預測架構（Theme 1 CNN-LSTM-注意力混合，或 Theme 2 SSL 預訓練主幹）移植至一衛星域——並嚴謹建構標竿、跨主體驗證、臨床結果框架——將具體檢驗典範是否泛化。偏頭痛預測是最高槓桿目標，因其最稀疏（~40:1 不對稱）且具明確臨床利害（預症狀警告之發作預防）。

### Priority Score / 優先分數

| Axis / 軸 | Score | Rationale |
|----------|-------|-----------|
| Severity / 嚴重性 | **4** | Limits paradigm generalisation but does not invalidate the core seizure-prediction evidence / 限制典範泛化但不否定核心證據 |
| Novelty / 新穎性 | **4** | Satellite domains are literally absent from Tier 1; any T1-quality contribution would be a first / 衛星域於 T1 完全缺席，任一 T1 級貢獻皆為首次 |
| Feasibility / 可行性 | **4** | Established seizure-prediction architectures transfer readily; data collection in sleep/migraine/vigilance is well-understood procedurally / 既有癲癇預測架構易遷移，資料收集程序明確 |

**Composite / 綜合分**: 4 × 0.40 + 4 × 0.30 + 4 × 0.30 = 1.60 + 1.20 + 1.20 = **4.00**

---

## GAP_003: External Validity & Generalization-Landscape Gap / 外部效度與泛化景觀缺口

### Description / 描述

Cross-dataset, cross-subject, and channel-reduction evaluations are performed by individual papers in isolation, but no paper systematically quantifies the *joint* generalization landscape — i.e., how prediction performance decays as a function of (dataset shift × patient shift × channel reduction × horizon length). The available point estimates reveal a consistent pattern: CHB-MIT performance saturates near 99%, but cross-dataset evaluation drops 3–5 percentage points (`QiEtAl2025`, `LiEtAl2025b`, `JangEtAl2026`), subject-independent evaluation drops 20+ points (`KoutsouvelisEtAl2024`), and aggressive channel reduction drops another 15 points (`ZhengEtAl2025`). These degradations are reported as isolated one-factor comparisons. The field lacks a systematic empirical characterization of the full degradation surface — a gap that directly affects whether published numbers translate to clinically deployed systems operating under joint ambulatory constraints.

跨資料集、跨主體與通道縮減評估由個別論文各自進行，但沒有任何論文系統性量化**聯合**泛化景觀——即預測效能如何隨（資料集偏移 × 病患偏移 × 通道縮減 × 時界長度）之函數衰減。現有點估計揭示一致模式：CHB-MIT 效能於 99% 附近飽和，但跨資料集評估下降 3–5 個百分點（`QiEtAl2025`、`LiEtAl2025b`、`JangEtAl2026`），主體無關評估下降 20+ 點（`KoutsouvelisEtAl2024`），激進通道縮減再降 15 點（`ZhengEtAl2025`）。此等衰減皆以孤立單因子比較形式報告。此領域缺少完整衰減曲面之系統性實證刻劃——此缺口直接影響已發表數字是否能轉譯至聯合門診限制下運行之臨床部署系統。

### Gap Type / 缺口類型

**Primary: Methodological gap / 主要：方法學缺口** — the experimental protocol needed to map the full generalization surface (factorial evaluation across dataset × subject × channel × horizon) has not been executed.
**Secondary: Temporal gap / 次要：時序缺口** — how horizon length interacts with the other generalization dimensions is particularly sparse (`AmiriEtAl2026` reports a horizon decay curve but only for one dataset and one architecture).

### Supporting Evidence / 支持證據

- `KoutsouvelisEtAl2024` — subject-specific 99.31% sensitivity vs. subject-independent drop approaching 20 points; paper acknowledges the gap but does not decompose by dataset or channel / 論文承認差距但未按資料集或通道分解.
- `JangEtAl2026` — CHB-MIT 97.92% → SNUH 94.93%; FPR rises from 0.092 to 0.130 / FPR 自 0.092 升至 0.130.
- `QiEtAl2025` — CHB-MIT 92.97% → Siena 92.79% (a much smaller drop, contradicting `JangEtAl2026`'s cross-dataset magnitude) / 跨資料集降幅與 `JangEtAl2026` 矛盾.
- `LiEtAl2025b` — CHB-MIT 96.6% → MSSM 94.2% (FPR 0.011 → 0.063, almost 6× rise) / FPR 近六倍上升.
- `ZhengEtAl2025` — channel reduction 18 → 2.8 drops sensitivity to 80.1% / 通道縮減使敏感度降至 80.1%.
- `AmiriEtAl2026` — sensitivity 89.3% at baseline horizon, 68.2% at 90-minute horizon; the only Tier 1 paper reporting a horizon-decay curve / 唯一報告預測時界衰減曲線之 T1 論文.
- SOTA review *Diverging Findings*: "same architecture gives very different numbers on CHB-MIT vs. SNUH vs. MSSM vs. Siena… this divergence is not noise; it reflects genuine dataset structural differences… that the field has not fully characterized" / 「分歧非噪聲；它反映真實之資料集結構差異，此領域尚未充分刻劃」.

### Counter-Evidence / 反證

- Review papers (`WesalEtAl2026`, `WuEtAl2025`, `MalikEtAl2026`, `QamarEtAl2025`) collate cross-study comparisons and implicitly describe the generalization surface at a narrative level / 於敘事層面隱含刻劃泛化景觀.
- `AmiriEtAl2026`'s horizon decay curve and physics-informed architecture represent partial progress on the temporal axis specifically / 於時序軸具部分進展.
- The `StaffordEtAl2026` (one of only 2 Observational-tagged papers in Theme 2) provides cohort-level rather than benchmark-level data, constituting weak evidence on external validity / 提供群組而非標竿數據，為外部效度之弱證據.

### Why It Matters / 為何重要

This gap affects whether Theme 1 benchmark numbers can be trusted as ambulatory-deployment performance predictions. A clinician deciding whether to adopt a "99% AUC on CHB-MIT" system needs to know that under joint realistic constraints (new centre + new patient + fewer channels + longer horizon) the effective performance may fall into the 60–80% range — a regime where false-alarm burden dominates. A focused study that systematically evaluates a single well-specified architecture across the full factorial surface would produce the generalization Rosetta Stone the field currently lacks. This is less conceptually novel than GAP_001 or GAP_002 (the field broadly acknowledges each one-factor degradation), but it is the necessary empirical substrate that both of those gaps will eventually need to rest on.

此缺口影響 Theme 1 標竿數字能否被信任作為門診部署效能預測。臨床醫師決定是否採用「CHB-MIT 99% AUC」系統，需知聯合真實限制下（新中心 + 新病患 + 較少通道 + 較長時界）其實際效能可能落入 60–80% 區間——此區間下假警報負擔主導。一個聚焦研究若於完整因子曲面上系統評估單一明確指定之架構，將產生此領域目前缺乏的泛化羅塞塔石碑。此缺口概念上較 GAP_001 與 GAP_002 新穎度低（此領域廣泛承認各單因子衰減），但它是該二缺口最終需要立足之必要實證基質。

### Priority Score / 優先分數

| Axis / 軸 | Score | Rationale |
|----------|-------|-----------|
| Severity / 嚴重性 | **5** | Directly affects clinical translatability of Theme 1 results; without it, benchmark numbers are misleading / 直接影響 Theme 1 結果之臨床可轉譯性 |
| Novelty / 新穎性 | **3** | Each single-factor degradation is known; the factorial combination is not published but is an incremental extension / 單因子衰減皆已知，因子組合為增量延伸 |
| Feasibility / 可行性 | **3** | Requires coordinated multi-dataset access and disciplined factorial design; achievable within ~12-month project / 需協調多資料集存取與嚴謹因子設計，~12 月內可達 |

**Composite / 綜合分**: 5 × 0.40 + 3 × 0.30 + 3 × 0.30 = 2.00 + 0.90 + 0.90 = **3.80**

---

## Priority Ranking / 優先級排序

| Rank | Gap ID | Title | Type | Sev | Nov | Feas | **Composite** |
|------|--------|-------|------|-----|-----|------|---------------|
| **1** | **GAP_001** | Preventive Outcome Measurement / 預防性結果測量 | Measurement + Integration | 5 | 5 | 3 | **4.40** |
| 2 | GAP_002 | Cross-Domain Methodological Asymmetry / 跨域方法學不對稱 | Population + Methodological | 4 | 4 | 4 | **4.00** |
| 3 | GAP_003 | External Validity & Generalization Landscape / 外部效度與泛化景觀 | Methodological + Temporal | 5 | 3 | 3 | **3.80** |

### Gap Landscape Summary / 缺口景觀摘要

**English.** The three gaps partition the field's weaknesses along distinct axes. GAP_001 is the *vertical* gap — it asks whether the predictive→preventive causal chain is demonstrated or merely asserted, and the evidence says asserted. GAP_002 is the *horizontal* gap — it asks whether the paradigm generalises across the five domains the positional paper claims, and the evidence says seizure prediction has raced ahead while the other four domains remain structurally under-attacked. GAP_003 is the *depth* gap — it asks whether the numbers we do have are trustworthy under joint ambulatory constraints, and the evidence says individual degradation factors are documented but their interaction surface is not. GAP_001 scores highest because it attacks the paradigm's central claim; GAP_002 offers the highest feasibility with meaningful novelty; GAP_003 is the empirical substrate both other gaps need.

**繁體中文。** 三個缺口沿不同軸線分割此領域之弱點。GAP_001 為**垂直缺口**——它詢問預測→預防之因果鏈是已實證或僅被斷言，證據顯示為後者。GAP_002 為**水平缺口**——它詢問典範是否泛化至 positional paper 所宣稱之五域，證據顯示癲癇預測遙遙領先，其餘四域仍結構性未被攻擊。GAP_003 為**深度缺口**——它詢問已有之數字於聯合門診限制下是否可信任，證據顯示個別衰減因子已記錄，但其交互曲面未被刻劃。GAP_001 評分最高因其攻擊典範核心宣稱；GAP_002 提供最高可行性與有意義之新穎性；GAP_003 是另二缺口皆需要立足之實證基質。

### Methodological Monoculture as Meta-Gap / 方法學單一文化之元缺口

Across all three gaps, a common root signal surfaces: 137 out of 162 papers (85%) use Computational methodology, zero use Experimental (RCT), only two use Observational (cohort), and the Engineering and Theoretical bins each hold 2 and 9 respectively. The methodology distribution is not a neutral reporting choice — it structurally shapes which kinds of questions the field can answer. Offline deep-learning benchmarks can characterize prediction surfaces (addressing GAP_003); they cannot measure preventive outcomes (GAP_001) or build the domain-specific benchmarks that satellite areas need (GAP_002). Any focused study that closes even one of these gaps will, by necessity, import methodology (RCT, cohort, prospective observational) that is currently under-represented in the evidence base. This meta-gap — the field's near-total reliance on a single methodological modality — is itself worth flagging to the user as the deepest structural weakness that downstream hypothesis design should reckon with.

三個缺口共同浮現之根源訊號：162 篇中 137 篇（85%）使用計算方法學，零篇使用實驗研究（RCT），僅 2 篇使用觀察研究（世代），工程與理論桶分別有 2 與 9 篇。方法學分佈非中性之報告選擇——它結構性地塑造此領域能回答何種問題。離線深度學習標竿可刻劃預測曲面（處理 GAP_003）；它們無法測量預防結果（GAP_001）或建構衛星域所需之域特異標竿（GAP_002）。任何聚焦研究若閉合此三缺口之任一，必然將引入目前於證據基礎中代表性不足之方法學（RCT、世代、前瞻性觀察）。此元缺口——此領域對單一方法學模態之近乎完全依賴——本身值得向使用者標記為下游假說設計應考量之最深結構性弱點。

---

## Checkpoint 3: 戰場選擇與價值裁定 / Battlefield Selection & Value Adjudication

> **⛳ Checkpoint 3**
>
> **English.** Review the three gaps above. Each gap is a candidate "battlefield" for the focused study that Step 8 (research-hypothesis) will specify. The composite scores are advisory — your judgment overrides them, especially on feasibility (which depends on your access to data, equipment, and collaborators) and on alignment with the positional paper's intended contribution. Select exactly one gap to pursue. The other two will be formally dropped and documented as "out of scope" in Step 8, which clarifies the eventual manuscript's moat.
>
> **繁體中文。** 請審核以上三個缺口。每一缺口是 Step 8（research-hypothesis）將規格化之聚焦研究的候選「戰場」。綜合分數僅供參考——您的判斷凌駕之，特別是於可行性（取決於您取得資料、設備與合作者之能力）與 positional paper 預定貢獻之對齊。請選擇恰好一個缺口作為攻擊目標。其餘二者將於 Step 8 正式捨棄並記錄為「範圍外」，以釐清最終手稿之護城河。
>
> **To proceed, specify: / 繼續請明示：** `Lock GAP_{N}, drop GAP_{M}, GAP_{K}` （例如 `Lock GAP_001, drop GAP_002, GAP_003`）
>
> Or if you want to refactor the gap set (merge two gaps, split one, replace with a different angle), state that instead and I'll regenerate this step. / 若您希望重構缺口組合（合併、拆分、替換），請明示，我將重新生成此步驟。

---

Files / 檔案: `step7_gap_analysis.md`
Next step / 下一步: `/research-hypothesis` (Step 8 — hypothesis specification with **Checkpoint 4: 護城河確認**) — pending Checkpoint 3 resolution / 待 Checkpoint 3 解決後執行
