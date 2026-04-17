---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
step: 6
total_papers: 162
themes: 5
full_text_papers: 24
abstract_only_papers: 138
---

# State-of-the-Art Review / 研究現況綜述

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> 預測性與預防性腦機介面：從神經與生理訊號預測認知狀態與不良健康事件
> Papers synthesized / 綜整論文數: 162
> Themes identified / 主題數: 5
> Full text available / 可取得全文: 24 (Tier 1) — primary evidence base / 主要證據基礎
> Abstract-only / 僅摘要: 138 (Tier 2–4) — supporting context / 輔助脈絡
> Date / 日期: 2026-04-16

## Executive Summary / 總覽摘要

The literature on predictive and preventive brain-computer interfaces has, within the past five years, crystallized around a single empirical centre of gravity: deep-learning-based seizure forecasting on the CHB-MIT and TUSZ benchmarks. Of the 162 screened papers, 83 (51%) sit in the `seizure_prediction` citation cluster, and of the 24 Tier 1 papers with retrieved full texts, 23 address seizure prediction while only one (MaioraEtAl2024) addresses the other positional-paper domains (falls). This asymmetry is itself the first finding — seizure forecasting has become the methodological lingua franca for *all* predictive BCIs, with architectures developed there (hybrid CNN-LSTM, Transformer-attention variants, contrastive pre-training, graph neural networks) being reused across sleep, vigilance, and migraine sub-literatures.

在過去五年，預測性與預防性腦機介面文獻已在一個經驗中心凝結：以 CHB-MIT 與 TUSZ 為標竿的深度學習癲癇預測。經篩選的 162 篇論文中，83 篇（51%）屬於 `seizure_prediction` 引用簇，而 24 篇已取得全文的 Tier 1 論文中，有 23 篇處理癲癇預測，僅 1 篇（MaioraEtAl2024）處理 positional paper 的其他域（跌倒）。此不對稱本身即是首要發現——癲癇預測已成為**所有**預測式 BCI 的方法學共通語，其發展出的架構（CNN-LSTM 混合、Transformer 注意力變體、對比預訓練、圖神經網路）被跨領域挪用至睡眠、警覺度與偏頭痛子文獻。

Within this centre, performance on CHB-MIT has saturated: at least seven 2025–2026 Tier 1 papers report sensitivity ≥ 96% with false prediction rate (FPR) ≤ 0.05/h — a regime where further numerical gains on the benchmark are clinically irrelevant and increasingly diagnostic of overfitting. The genuinely live debates have therefore migrated outward: (1) **generalization** — can CHB-MIT-trained models transfer to new datasets like Siena, MSSM, SNUH without re-training? (2) **deployment** — can state-of-the-art architectures run on wearable hardware under edge constraints? (3) **personalization vs. privacy** — how do federated / patient-adaptive models resolve the tension between individual fit and data protection? (4) **interpretability** — can preictal biomarkers be named rather than only predicted? Theme-level synthesis below walks through each of these frontiers.

在此核心之內，CHB-MIT 之效能已近飽和：至少七篇 2025–2026 年 Tier 1 論文報告敏感度 ≥ 96%、錯誤預測率（FPR）≤ 0.05/h——此區間內標竿數字的進一步提升已無臨床意義，且日益成為過擬合的診斷指標。真正活躍的爭議因此向外遷移：（1）**泛化性**——CHB-MIT 訓練之模型能否不經重訓即遷移至 Siena、MSSM、SNUH 等新資料集？（2）**部署性**——SOTA 架構能否在邊緣限制下於穿戴硬體上執行？（3）**個人化與隱私之張力**——聯邦式／病患自適應模型如何權衡個體擬合與資料保護？（4）**可解釋性**——能否將預發作生物標記具體命名而非僅能預測？下文主題綜整將逐一展開此四條前線。

Beyond seizure prediction, the review documents a long, thin tail of cross-domain predictive BCIs — fall (14 papers), sleep (7), vigilance (4), migraine (2), pre-stimulus/predictive-coding (3) — where methodological maturity lags seizure work by roughly a decade. The sparsest subdomain, migraine prediction, is arguably the most consequential signal in this review: if 162 papers surface only 2 migraine-prediction studies, the gap is not that the question is answered but that it is structurally under-attacked.

在癲癇預測之外，本綜述記錄了跨域預測式 BCI 的長尾——跌倒（14 篇）、睡眠（7 篇）、警覺度（4 篇）、偏頭痛（2 篇）、預刺激/預測編碼（3 篇）——方法學成熟度相較癲癇研究約落後十年。其中最稀疏的偏頭痛預測子域，或許是本綜述中最具訊號意義的發現：若 162 篇論文中僅浮現 2 篇偏頭痛預測研究，則此缺口並非問題已獲解答，而是結構性未被攻擊。

## Methodology Legend / 方法學圖例

| Color / 顏色 | Methodology / 方法學 | Count / 數量 |
|-------------|---------------------|-------------|
| 🔴 Red | Experimental / 實驗研究 | 0 |
| 🟠 Orange | Computational / 計算方法 | 137 |
| 🟡 Yellow | Review / 文獻回顧 | 12 |
| 🟢 Green | Observational / 觀察研究 | 2 |
| 🔵 Cyan | Engineering / 工程設計 | 2 |
| 🟣 Purple | Theoretical / 理論研究 | 9 |

---

## Theme 1: Deep Sequence Models for Seizure Prediction / 深度序列模型於癲癇預測

**Papers (60) / 論文數:** `WesalEtAl2026`, `KoutsouvelisEtAl2024`, `WuEtAl2025`, `SunkaraRajakumari2023`, `QuEtAl2026`, `AhmadEtAl2026`, `LiaoEtAl2025a`, `PhamTran2026`, `ZhengEtAl2025`, `AbbasiEtAl2025`, `WangEtAl2026b`, `AlkhrijahEtAl2025`, `WangEtAl2025c`, `LiEtAl2025b`, `EsmaeilpourEtAl2024`, … (+45 more)

**Tier 1 anchor papers / T1 錨定論文 (14):** `WesalEtAl2026`, `KoutsouvelisEtAl2024`, `WuEtAl2025`, `SunkaraRajakumari2023`, `QuEtAl2026`, `AhmadEtAl2026`, `LiaoEtAl2025a`, `PhamTran2026`, `ZhengEtAl2025`, `AbbasiEtAl2025`, `WangEtAl2026b`, `AlkhrijahEtAl2025`, `WangEtAl2025c`, `LiEtAl2025b`

### Consensus / 共識

The field has converged on a specific architectural recipe for seizure prediction: a hybrid pipeline that extracts spatiotemporal features from multichannel EEG via convolutional layers, then models temporal dependencies via LSTM, self-attention, or Transformer blocks. At least 11 Tier 1 papers (LiaoEtAl2025a, QuEtAl2026, LiEtAl2025b, PhamTran2026, WangEtAl2025c, AhmadEtAl2026, AlkhrijahEtAl2025, SunkaraRajakumari2023, ZhengEtAl2025, AbbasiEtAl2025, WangEtAl2026b) adopt some form of this pattern, and the non-Tier-1 seizure-prediction literature overwhelmingly extends or benchmarks against it. Performance on CHB-MIT has stabilized at a ceiling: CaoEtAl2026 reports 99.54% AUC with 0.01/h FPR, AlkhrijahEtAl2025 reports 99.34% sensitivity / 98.67% specificity / 0.039/h FPR, WangEtAl2025c reports 98.89% accuracy on CHB-MIT, and PhamTran2026 reports 99.46% sensitivity. The implicit consensus is that on CHB-MIT, accuracy has ceased to be a useful distinguishing metric between models.

此領域已收斂於一個明確的架構配方：以卷積層從多通道 EEG 擷取時空特徵，再以 LSTM、自注意力或 Transformer 區塊建模時序依賴的混合流水線。至少 11 篇 T1 論文（LiaoEtAl2025a、QuEtAl2026、LiEtAl2025b、PhamTran2026、WangEtAl2025c、AhmadEtAl2026、AlkhrijahEtAl2025、SunkaraRajakumari2023、ZhengEtAl2025、AbbasiEtAl2025、WangEtAl2026b）採用此模式的某種形式，非 T1 的癲癇預測文獻則大量延伸或與其對照。CHB-MIT 上的效能已穩定在天花板：CaoEtAl2026 報告 99.54% AUC、0.01/h FPR；AlkhrijahEtAl2025 報告 99.34% 敏感度 / 98.67% 特異度 / 0.039/h FPR；WangEtAl2025c 在 CHB-MIT 上報告 98.89% 準確度；PhamTran2026 報告 99.46% 敏感度。隱含共識是：在 CHB-MIT 上，準確度已不再是區分模型的有意義度量。

### Debates / 爭議

The central debate within Theme 1 is whether the reported performance reflects genuine predictive capability or benchmark-specific overfitting. Three lines of evidence suggest the latter is a serious concern. First, on harder or less-curated datasets, numbers drop substantially: JangEtAl2026 achieves 97.92% sensitivity on CHB-MIT but only 94.93% on SNUH with nearly four-fold higher FPR (0.092 vs 0.130). Second, QiEtAl2025 explicitly cross-validates on both CHB-MIT (92.97% accuracy) and Siena (92.79%), finding comparable but *not identical* performance — the generalizability gap is real even between curated datasets. Third, KoutsouvelisEtAl2024 shows that cross-patient models in a subject-independent setting exhibit sensitivity 20%+ below subject-specific models on the same data. A second debate concerns **preictal window definition**: papers variously define the preictal period as 5, 10, 15, 30, or 60 minutes before seizure onset, and LiEtAl2025b explicitly critiques the field for assuming fixed preictal durations across all patients, proposing adaptive windows in the 15–45 minute range instead.

Theme 1 內的核心爭議在於：所報告之效能反映的是真正的預測能力，還是標竿特異的過擬合？三條證據指向後者是嚴重問題。其一，在較困難或較少整理的資料集上，數字大幅下降：JangEtAl2026 在 CHB-MIT 上敏感度 97.92%，但在 SNUH 上僅 94.93%，FPR 幾乎高四倍（0.092 對 0.130）。其二，QiEtAl2025 明確在 CHB-MIT（92.97% 準確度）與 Siena（92.79%）進行交叉驗證，發現效能相近但**非相同**——即使在已整理的資料集間，泛化差距是真實的。其三，KoutsouvelisEtAl2024 顯示主體無關設定下的跨病患模型，其敏感度比同資料之主體特異模型低 20% 以上。第二個爭議涉及**預發作窗口定義**：論文將預發作期不一地定義為發作前 5、10、15、30 或 60 分鐘，而 LiEtAl2025b 明確批評此領域假設所有病患共享固定預發作時長，並提議 15–45 分鐘範圍內的自適應窗口。

### Dominant Methods / 主流方法

Architectural components: (a) **Convolutional frontend** — 1D or 2D CNNs for per-channel spectro-temporal feature extraction (SunkaraRajakumari2023, AhmadEtAl2026, CaoEtAl2026); (b) **Recurrent backbone** — Bi-LSTM for modeling the pre-ictal trajectory (AlkhrijahEtAl2025's Bi-LSTM `consistently outperformed other recurrent neural networks`); (c) **Attention / Transformer head** — multi-head self-attention for channel-time fusion (LiEtAl2025b, QuEtAl2026, ZhangEtAl2026, WangEtAl2025c's CGTNet, PhamTran2026's EEG-Titans); (d) **Graph neural networks** — GCN/GAT over EEG electrode topology (AbbasiEtAl2025, WangEtAl2026b's dynamic multiscale cross-graph). Dataset dominance: CHB-MIT is evaluated by ≥90% of papers in this theme; Siena, MSSM, TUSZ, SNUH appear as secondary benchmarks. Evaluation convention: patient-specific k-fold or leave-one-seizure-out cross-validation; segment-level accuracy/sensitivity/FPR are standard; event-level sensitivity (fraction of seizures correctly alarmed) is increasingly reported.

架構組件：（a）**卷積前端**——每通道時頻特徵擷取之 1D 或 2D CNN（SunkaraRajakumari2023、AhmadEtAl2026、CaoEtAl2026）；（b）**循環主幹**——Bi-LSTM 建模預發作軌跡（AlkhrijahEtAl2025 之 Bi-LSTM `consistently outperformed other recurrent neural networks`）；（c）**注意力／Transformer 頭**——多頭自注意力於通道－時間融合（LiEtAl2025b、QuEtAl2026、ZhangEtAl2026、WangEtAl2025c 之 CGTNet、PhamTran2026 之 EEG-Titans）；（d）**圖神經網路**——於 EEG 電極拓撲上之 GCN/GAT（AbbasiEtAl2025、WangEtAl2026b 之動態多尺度跨圖）。資料集主導：CHB-MIT 被本主題 ≥90% 的論文評估；Siena、MSSM、TUSZ、SNUH 作為次要標竿出現。評估慣例：病患特異的 k-fold 或留一癲癇發作交叉驗證；片段級準確度／敏感度／FPR 為標準；事件級敏感度（正確警報之癲癇發作比例）日益被報告。

### Key Results / 關鍵發現

| Study | Dataset | Sensitivity | FPR (/h) | Architecture |
|-------|---------|------------|----------|--------------|
| `CaoEtAl2026` | CHB-MIT | 99.54% AUC | 0.01 | Knowledge-distilled CNN-LSTM-Transformer |
| `AlkhrijahEtAl2025` | CHB-MIT | 99.34% | 0.039 | SVM + RF + Bi-LSTM ensemble |
| `WangEtAl2025c` (CGTNet) | CHB-MIT | 98.52% (Acc 98.89%) | — | Convolutional Graph Transformer |
| `PhamTran2026` (EEG-Titans) | CHB-MIT | 99.46% | — | Dual-branch long-horizon Transformer |
| `ZhangEtAl2026` (HCFT) | (not CHB-MIT) | 99.10% | 0.023 | Hierarchical Convolutional Fusion Transformer |
| `AhmadEtAl2026` | sEEG | 98.84% Acc | — | Hybrid CNN-LSTM + attention (10-min window) |
| `AhmadEtAl2026` | iEEG | 97.18% Acc | — | (same architecture) |
| `QuEtAl2026` | (CHB-MIT) | 93.87% | 0.12 (segment) / 0.056 (event) | Causal attention network |
| `QiEtAl2025` | CHB-MIT | 94.18% (Acc 92.97%) | (reported) | Contrastive ResNet |
| `QiEtAl2025` | Siena | 91.47% (Acc 92.79%) | 0.041 | (same) |
| `JangEtAl2026` | CHB-MIT | 97.92% | 0.092 | Single-channel DL |
| `JangEtAl2026` | SNUH | 94.93% (Acc 85.97%) | 0.130 | (same) |
| `LiEtAl2025b` | CHB-MIT | 96.6% | 0.011 | Spatio-Temporal Attention + adaptive preictal window |
| `LiEtAl2025b` | MSSM | 94.2% | 0.063 | (same) |
| `AbbasiEtAl2025` | (CHB-MIT) | 97.1% mean / 98.5% median Acc | — | Edge-deployable GCN |
| `YedurkarEtAl2025` | (multi) | 98.3% | 0.045 | MCSV-CNN IoT pipeline |
| `SunkaraRajakumari2023` | CHB-MIT | 99% recall | — | LSTM (prec 98%, F1 98%) |
| `ZhengEtAl2025` | CHB-MIT (ch.-reduced) | 80.1% | 0.11 | 2-stage channel-aware (2.8 ch from 18) |

The rightmost columns of this table tell a useful story: pure CHB-MIT numbers cluster tightly at 96–99% sensitivity with FPR below 0.1/h — a saturation regime. When the *same* architectures are evaluated on second datasets (SNUH, MSSM, Siena), sensitivity typically drops 3–5 percentage points and FPR often doubles. When channels are reduced to wearable-compatible levels (ZhengEtAl2025), sensitivity drops to 80%. These joint facts are the strongest quantitative signal in Theme 1 that CHB-MIT-only performance should no longer be treated as the field's benchmark of record.

此表最右欄講述一個有用的故事：純 CHB-MIT 數字緊密叢集於 96–99% 敏感度，FPR 低於 0.1/h——飽和區間。當**相同**架構在第二資料集（SNUH、MSSM、Siena）上評估時，敏感度通常下降 3–5 個百分點，FPR 通常加倍。當通道縮減至穿戴相容水準（ZhengEtAl2025），敏感度降至 80%。此等共同事實是 Theme 1 中最強的定量訊號：CHB-MIT 單一資料集之效能不應再被視為此領域的標竿之紀錄。

---

## Theme 2: Representation Learning & Transferable EEG Models / 表徵學習與可遷移 EEG 模型

**Papers (24) / 論文數:** `GuoEtAl2023`, `QiEtAl2025`, `BaryMacq2024`, `MahdiBaghdadi2026`, `YinEtAl2026`, `StaffordEtAl2026`, `LiaoEtAl2024`, `ShiEtAl2025`, `LutesEtAl2022`, `HoffsommerEtAl2025`, `PuahEtAl2025`, `PelentritouEtAl2025`, `Anjum2024`, `KollaEtAl2026`, `ZhouEtAl2026b`, … (+9 more)

**Tier 1 anchor papers / T1 錨定論文 (4):** `GuoEtAl2023`, `QiEtAl2025`, `BaryMacq2024`, `MahdiBaghdadi2026`

### Consensus / 共識

Representation learning — self-supervised pretraining, contrastive learning, and transferable feature extraction on unlabeled EEG — has emerged since 2023 as a distinct methodological wing of predictive BCIs. The consensus across Tier 1 papers is that large-scale unlabeled EEG corpora can be used to learn features that transfer positively to seizure prediction downstream tasks. GuoEtAl2023's CLEP framework explicitly frames seizure prediction as a contrastive learning problem, and QiEtAl2025's `Contrastive Learning-Enhanced Residual Network` extends this idea into a ResNet backbone. BaryMacq2024 focuses on the pre-requisite question of *dataset construction* for SSL pretraining from unlabeled EEG, reporting AUC 0.97 on downstream tasks. AmiriEtAl2026 (primary in Theme 3 but overlapping) cites a reference using over 10,000 hours of EEG for self-supervised pre-training achieving 87.2% sensitivity on CHB-MIT, indicating that the scale-pretraining hypothesis from NLP/vision is being actively imported.

表徵學習——在無標註 EEG 上的自監督預訓練、對比學習與可遷移特徵擷取——自 2023 年起已作為預測式 BCI 的獨立方法學分支浮現。Tier 1 論文間的共識是：大規模無標註 EEG 語料庫可用以學習能正向遷移至下游癲癇預測任務的特徵。GuoEtAl2023 之 CLEP 框架明確將癲癇預測框為對比學習問題，QiEtAl2025 之對比學習增強殘差網路將此想法延伸至 ResNet 主幹。BaryMacq2024 聚焦於 SSL 預訓練自無標註 EEG 之先決問題——**資料集建構**，於下游任務報告 AUC 0.97。AmiriEtAl2026（主要歸屬 Theme 3 但有重疊）引用一篇使用超過 10,000 小時 EEG 進行自監督預訓練、於 CHB-MIT 達 87.2% 敏感度的文獻，顯示來自 NLP/視覺的規模預訓練假說正被積極引入。

### Debates / 爭議

Whether SSL/contrastive pre-training *actually* improves downstream seizure prediction beyond a well-tuned supervised baseline remains unresolved. GuoEtAl2023 reports that CLEP-STS-Net achieves AUC improvement of only `0.004 and 0.005` over non-contrastive baselines — a gain that is statistically detectable but clinically marginal. The contrasting position, advocated by MahdiBaghdadi2026 and AmiriEtAl2026, is that gains become substantial only when combined with patient-adaptive fine-tuning or physics-informed structural priors — i.e., pre-training is necessary but not sufficient. A second debate concerns **tokenization**: Anjum2024's LiPCoT (Linear Predictive Coding-based Tokenizer) imports the NLP tokenizer concept into EEG, but the broader field has not agreed on whether EEG should be tokenized at all, or whether continuous-signal architectures remain preferable.

SSL/對比預訓練是否**確實**改善下游癲癇預測效能（超越調教良好之監督基線）仍未解決。GuoEtAl2023 報告 CLEP-STS-Net 相較非對比基線之 AUC 改善僅 `0.004 and 0.005`——統計上可偵測但臨床上邊緣之增益。相對立場（由 MahdiBaghdadi2026 與 AmiriEtAl2026 倡議）是：只有在結合病患自適應微調或物理知情的結構先驗時，增益才變得顯著——即，預訓練必要但不充分。第二個爭議涉及**分詞**：Anjum2024 之 LiPCoT（基於線性預測編碼的分詞器）將 NLP 分詞器概念引入 EEG，但更廣泛的領域尚未就 EEG 是否應分詞達成共識，或連續訊號架構是否仍較可取。

### Dominant Methods / 主流方法

(a) **Contrastive SSL** — InfoNCE-style loss over temporal EEG augmentations (GuoEtAl2023 CLEP, QiEtAl2025); (b) **Masked reconstruction** — masked-autoencoder variants pretrain on EEG windows (BaryMacq2024, BanvilleEtAl2020); (c) **Tokenization** — discretizing continuous EEG into tokens for Transformer-style consumption (Anjum2024 LiPCoT, PhamTran2026 EEG-Titans); (d) **Foundation model scale** — pretraining on 10,000+ hours of pooled EEG data across patients and centres (as cited by AmiriEtAl2026). Evaluation protocol: pretrain on large pooled unlabeled EEG → freeze or fine-tune → evaluate downstream on CHB-MIT or similar.

（a）**對比式 SSL**——時序 EEG 增強上的 InfoNCE 形式損失（GuoEtAl2023 CLEP、QiEtAl2025）；（b）**遮蔽重建**——於 EEG 窗口上預訓練的遮蔽自編碼器變體（BaryMacq2024、BanvilleEtAl2020）；（c）**分詞**——將連續 EEG 離散化為供 Transformer 式消耗之令牌（Anjum2024 LiPCoT、PhamTran2026 EEG-Titans）；（d）**基礎模型規模**——跨病患與中心彙集之 10,000+ 小時 EEG 資料上預訓練（如 AmiriEtAl2026 所引）。評估協定：於大型彙集無標註 EEG 預訓練 → 凍結或微調 → 於 CHB-MIT 或類似下游評估。

### Key Results / 關鍵發現

Representation-learning approaches currently report AUC and accuracy comparable to best supervised baselines on CHB-MIT (AUC ≈ 0.97; accuracy 92–95%) but have not established a clear performance dominance. The distinctive value proposition is therefore not raw CHB-MIT performance but **sample efficiency** and **transferability to new centres** — claims that the Tier 1 full texts gesture toward but have not yet quantified at scale. The papers with the most rigorous quantitative evidence for this wing (foundation-model-scale pre-training at 10,000+ EEG hours) are citations embedded within the Tier 1 papers rather than the Tier 1 papers themselves, meaning that the strongest evidence for SSL-driven gains lies just outside this shortlist and warrants Step-7 gap analysis.

表徵學習方法目前於 CHB-MIT 上報告之 AUC 與準確度可與最佳監督基線相當（AUC ≈ 0.97；準確度 92–95%），但尚未確立明確的效能主導性。因此其獨特價值主張不在於 CHB-MIT 純效能，而在於**樣本效率**與**向新中心之可遷移性**——Tier 1 全文指向但尚未大規模量化此二主張。此分支最嚴謹定量證據之論文（於 10,000+ EEG 小時規模之基礎模型預訓練）是嵌於 Tier 1 論文內之引用而非 Tier 1 論文本身，意味著 SSL 驅動增益之最強證據恰位於此精選清單之外，並值得於 Step 7 缺口分析中追蹤。

---

## Theme 3: Cross-Patient Generalization, Personalization & Privacy / 跨病患泛化、個人化與隱私

**Papers (10) / 論文數:** `AmiriEtAl2026`, `TariqEtAl2020`, `DaoudBayoumi2019`, `ChoiEtAl2022`, `RevathyM2025`, `LiEtAl2025a`, `KhanEtAl2025`, `JeongEtAl2025`, `JabbarEtAl2025`, `JadduEtAl2024`

**Tier 1 anchor papers / T1 錨定論文 (1):** `AmiriEtAl2026`

### Consensus / 共識

Cross-patient generalization is the field's most widely acknowledged unsolved problem. The consensus across Theme 3 is that (a) subject-specific models dominate subject-independent models by 10–20+ percentage points in sensitivity (KoutsouvelisEtAl2024 shows subject-specific sensitivity 99.31% vs. subject-independent approaching floor), (b) simple transfer-learning from pooled data does not close this gap, and (c) some form of patient-adaptive mechanism is required — whether fine-tuning, meta-learning, federated aggregation with personalization layers, or physics-informed structural bias. AmiriEtAl2026 explicitly positions physics-informed graph neural networks (PI-GNN) as a cross-patient solution, achieving 89.3% sensitivity with 68.2% preserved at 90-minute horizons, and claims a +4.9% accuracy advantage over temporal-GNN baselines. MahdiBaghdadi2026's patient-adaptive Transformer takes a complementary angle, embedding adaptation into the attention mechanism itself.

跨病患泛化是此領域被最廣泛承認的未解問題。Theme 3 共識為：（a）主體特異模型於敏感度上壓倒主體無關模型 10–20+ 個百分點（KoutsouvelisEtAl2024 顯示主體特異敏感度 99.31%，主體無關趨近下限）；（b）自彙集資料的簡單遷移學習無法彌合此差距；（c）需要某種形式的病患自適應機制——無論是微調、元學習、帶個人化層的聯邦聚合，或物理知情的結構偏差。AmiriEtAl2026 明確將物理知情圖神經網路（PI-GNN）定位為跨病患解，達 89.3% 敏感度並於 90 分鐘預測時界保留 68.2%，宣稱相較時間 GNN 基線 +4.9% 準確度優勢。MahdiBaghdadi2026 之病患自適應 Transformer 採取互補角度，將適應性嵌入注意力機制本身。

### Debates / 爭議

Three debates are live. **First**, is federated learning (FL) the right privacy-preserving personalization architecture? Proponents argue FL preserves data locality while enabling aggregated model improvement; skeptics (implicit in KoutsouvelisEtAl2024 and the broader lack of T1 FL seizure papers) note that federated updates can actually *amplify* subject-specific overfitting if not carefully regularized. **Second**, what is the right granularity of personalization — patient, seizure type, or session? Subject-specific models often still fail on seizure types the patient has not previously exhibited. **Third**, is physics-informed bias (AmiriEtAl2026) genuinely more transferable than purely data-driven approaches, or is it trading generalization for inductive priors that may themselves not transfer?

三個爭議正活躍。**其一**，聯邦學習（FL）是否是正確的隱私保留個人化架構？倡議者認為 FL 保留資料局部性同時實現聚合模型改善；懷疑者（隱含於 KoutsouvelisEtAl2024 與更廣泛地 T1 FL 癲癇論文之闕如）指出若未審慎正則化，聯邦更新可能實際**放大**主體特異過擬合。**其二**，個人化的正確粒度為何——病患、癲癇發作類型或會次？主體特異模型仍常於病患先前未展現的發作類型上失敗。**其三**，物理知情偏差（AmiriEtAl2026）是否真正較純資料驅動方法更可遷移，抑或是以泛化性換取本身可能亦不遷移之歸納先驗？

### Dominant Methods / 主流方法

(a) **Patient-adaptive fine-tuning** — freeze pretrained backbone, fine-tune head per patient (MahdiBaghdadi2026); (b) **Meta-learning / domain adaptation** — learn to adapt quickly to new patients via MAML-style or adversarial domain-adaptation losses; (c) **Physics-informed structural priors** — GNN edges encode known anatomical/functional brain connectivity (AmiriEtAl2026); (d) **Federated learning** — less represented in T1 but heavily cited in T2-T4 (Aldahr et al. 2023 referenced in the positional paper).

（a）**病患自適應微調**——凍結預訓練主幹、每病患微調頭部（MahdiBaghdadi2026）；（b）**元學習／域適應**——透過 MAML 式或對抗式域適應損失學習快速適應新病患；（c）**物理知情結構先驗**——GNN 邊編碼已知解剖／功能性腦連結（AmiriEtAl2026）；（d）**聯邦學習**——T1 較少代表，但於 T2-T4 大量引用（positional paper 引用的 Aldahr et al. 2023）。

### Key Results / 關鍵發現

| Study | Approach | Cross-patient Sensitivity | Notes |
|-------|----------|--------------------------|-------|
| `AmiriEtAl2026` | PI-GNN | 89.3% (68.2% at 90-min horizon) | +4.9% over temporal-GNN baseline |
| `KoutsouvelisEtAl2024` (subject-specific) | Per-patient DL | 99.31% sensitivity, 95.34% specificity | Upper bound |
| `KoutsouvelisEtAl2024` (subject-independent) | Pooled DL | 94.76% sensitivity, 73.54% specificity | >20% specificity gap |
| `ZhengEtAl2025` | Channel-aware 2-stage | 80.1% (2.8 channels from 18) | Trade-off: ~15% drop for 85% channel reduction |
| `MahdiBaghdadi2026` | Patient-adaptive Transformer | (not cleanly reported in fetched excerpt) | Architecture-level adaptation |

The 20-percentage-point sensitivity gap between subject-specific and subject-independent models (KoutsouvelisEtAl2024) is the single most consequential number in Theme 3: it defines the size of the generalization problem that physics-informed, federated, and foundation-model approaches are all trying to close. No paper in this shortlist has closed it.

主體特異與主體無關模型間的 20 個百分點敏感度差距（KoutsouvelisEtAl2024）是 Theme 3 中單一最具後果的數字：它定義了物理知情、聯邦與基礎模型方法皆試圖彌合之泛化問題的規模。此精選清單中無論文已將其彌合。

---

## Theme 4: Efficient & Deployable Predictive BCIs / 高效可部署預測式 BCI

**Papers (13) / 論文數:** `CaoEtAl2026`, `ZhangEtAl2026`, `LiEtAl2022`, `YedurkarEtAl2025`, `JangEtAl2026`, `ThahniyathEtAl2024`, `SEtAl2025`, `SharmaEtAl2025`, `RenEtAl2022`, `Paneru2026`, `PaillardEtAl2025`, `YangEtAl2025`, `De2025`

**Tier 1 anchor papers / T1 錨定論文 (5):** `CaoEtAl2026`, `ZhangEtAl2026`, `LiEtAl2022`, `YedurkarEtAl2025`, `JangEtAl2026`

### Consensus / 共識

Deployability — i.e., running predictive BCIs on wearable hardware with power, latency, and channel-count constraints — is increasingly treated as a first-order design constraint rather than a post-hoc engineering concern. CaoEtAl2026 demonstrates a knowledge-distilled compact model achieving 99.54% CHB-MIT AUC with only 0.082M parameters — orders of magnitude smaller than non-distilled baselines. LiEtAl2022 implements parallel memristive CNN seizure detection with 2×–2,800× fewer network parameters than prior SOTA CNNs while achieving 93.46% detection accuracy on a memristor crossbar. AbbasiEtAl2025 explicitly targets edge deployment with a GCN pipeline reporting 97.1% mean accuracy. YedurkarEtAl2025's SPA-IoT with MCSV-CNN integrates IoT deployment into the pipeline reporting 99.5% accuracy with 98.3% sensitivity. JangEtAl2026's single-channel EEG approach is an extreme form of the same commitment, reducing hardware requirements dramatically. The consensus is that wearable-compatible prediction is no longer aspirational — multiple T1 demonstrations exist — but that the resulting systems have yet to be prospectively validated at scale.

可部署性——即在穿戴硬體上於功耗、延遲與通道數限制下執行預測式 BCI——日益被視為一級設計約束而非事後工程考量。CaoEtAl2026 展示知識蒸餾緊緻模型於 CHB-MIT 上達 99.54% AUC，僅用 0.082M 參數——比非蒸餾基線小數個量級。LiEtAl2022 實現並行憶阻 CNN 癲癇偵測，網路參數相較既有 SOTA CNN 少 2×–2,800×，於憶阻交叉陣列上達 93.46% 偵測準確度。AbbasiEtAl2025 明確針對邊緣部署，其 GCN 流水線報告 97.1% 平均準確度。YedurkarEtAl2025 之 SPA-IoT 搭配 MCSV-CNN 將 IoT 部署整合入流水線，報告 99.5% 準確度與 98.3% 敏感度。JangEtAl2026 之單通道 EEG 方法是同一承諾之極端形式，大幅降低硬體需求。共識為：穿戴相容的預測不再只是願景——多個 T1 展示已存在——但所產生系統仍未經大規模前瞻性驗證。

### Debates / 爭議

The unresolved debate within Theme 4 concerns **accuracy-deployability trade-offs at clinical thresholds**. Compact models (CaoEtAl2026 at 0.082M params) report parity with larger baselines on CHB-MIT, but channel-reduction experiments (ZhengEtAl2025, reducing 18→2.8 channels) show 15+ point sensitivity drops. JangEtAl2026's single-channel approach achieves 97.92% on CHB-MIT but 94.93% on SNUH — the channel reduction penalty is dataset-dependent. A second debate is **memristor / in-memory compute vs. conventional edge** (LiEtAl2022 memristor-based vs. standard edge CNN): memristor arrays offer fundamentally different energy profiles but have not yet matched the deployment maturity of conventional hardware. A third debate concerns **on-device training vs. on-device inference only** — most T1 papers assume training happens off-device, but this conflicts with the patient-adaptive requirements of Theme 3.

Theme 4 內的未解爭議涉及**臨床門檻下的準確度－可部署性權衡**。緊緻模型（CaoEtAl2026 於 0.082M 參數）於 CHB-MIT 上報告與較大基線平手，但通道縮減實驗（ZhengEtAl2025 將 18→2.8 通道）顯示 15+ 點敏感度下降。JangEtAl2026 之單通道方法於 CHB-MIT 達 97.92%，但於 SNUH 僅 94.93%——通道縮減懲罰是資料集依賴的。第二個爭議是**憶阻／記憶體內運算 vs. 傳統邊緣**（LiEtAl2022 基於憶阻 vs. 標準邊緣 CNN）：憶阻陣列提供根本上不同的能耗剖面，但尚未達到傳統硬體的部署成熟度。第三個爭議涉及**裝置上訓練 vs. 僅裝置上推理**——多數 T1 論文假設訓練於裝置外進行，但這與 Theme 3 的病患自適應需求衝突。

### Dominant Methods / 主流方法

(a) **Knowledge distillation** — distill large teacher model into compact student (CaoEtAl2026's distillation cascade of Transformer teacher → CNN-LSTM-attention student); (b) **Parameter pruning and quantization** — reduce model footprint via structured pruning; (c) **Channel reduction** — select informative EEG channels and discard the rest (ZhengEtAl2025, JangEtAl2026); (d) **Specialized hardware** — memristor crossbars (LiEtAl2022), neuromorphic processors, FPGA pipelines; (e) **IoT pipelines** — full end-to-end sensor-to-cloud architectures (YedurkarEtAl2025 SPA-IoT).

（a）**知識蒸餾**——將大型教師模型蒸餾為緊緻學生（CaoEtAl2026 之 Transformer 教師 → CNN-LSTM-attention 學生蒸餾級聯）；（b）**參數剪枝與量化**——透過結構化剪枝降低模型佔用；（c）**通道縮減**——選擇有資訊量的 EEG 通道並捨棄其餘（ZhengEtAl2025、JangEtAl2026）；（d）**專用硬體**——憶阻交叉陣列（LiEtAl2022）、神經形態處理器、FPGA 流水線；（e）**IoT 流水線**——完整端對端感測器至雲端架構（YedurkarEtAl2025 SPA-IoT）。

### Key Results / 關鍵發現

| Study | Deployability Target | Performance | Resource Footprint |
|-------|---------------------|-------------|---------------------|
| `CaoEtAl2026` | Compact DL | 99.54% AUC / 0.01 FPR (CHB-MIT) | 0.082M parameters |
| `LiEtAl2022` | Memristor crossbar | 93.46% detection accuracy | 2×–2,800× fewer params than SOTA |
| `AbbasiEtAl2025` | Edge GCN | 97.1% mean Acc | (pipeline edge-deployable) |
| `YedurkarEtAl2025` | IoT pipeline | 99.5% Acc / 98.3% Sens / 0.045 FPR | End-to-end sensor-to-cloud |
| `JangEtAl2026` | Single-channel EEG | 97.92% Sens (CHB-MIT) / 94.93% (SNUH) | 1 channel |
| `ZhengEtAl2025` | Channel-reduced | 80.1% Sens / 0.11 FPR | 2.8 channels (from 18) |

Cross-cutting observation: the best benchmark numbers in Theme 4 are achieved on CHB-MIT; when the same architectures are deployed or evaluated on more ambulatory-like conditions (single channel, SNUH cohort), performance drops 5–15 points. Deployability claims that do not report external-dataset or channel-reduced numbers should be interpreted cautiously.

跨越觀察：Theme 4 最佳標竿數字於 CHB-MIT 達成；當相同架構於較類似門診條件（單通道、SNUH 群組）上部署或評估時，效能下降 5–15 點。不報告外部資料集或通道縮減數字之可部署性宣稱應審慎解讀。

---

## Theme 5: Cross-Domain Predictive BCIs & Reviews / 跨域預測式 BCI 與文獻回顧

**Papers (55) / 論文數:** `MaioraEtAl2024`, `CesariEtAl2023`, `GuanEtAl2025`, `KapustynskaEtAl2025`, `TomalinEtAl2025`, `ZhangEtAl2024`, `LinEtAl2025`, `Chakraborty2026`, `DinhEtAl2025`, `NesaragiEtAl2025`, `JamaraniEtAl2026`, `BanvilleEtAl2020`, `ZhangEtAl2025`, `JankevičiūtėEtAl2026`, `LiaoEtAl2025b`, … (+40 more)

**Tier 1 anchor papers / T1 錨定論文 (1):** `MaioraEtAl2024`

### Consensus / 共識

Across the five positional-paper domains beyond seizure prediction — falls, sleep, migraine, vigilance/drowsiness, pre-stimulus/predictive-coding — the methodological consensus mirrors Theme 1 (CNN/LSTM/Transformer hybrids on EEG or multimodal physiological signals are the default approach) but the *evidence base is an order of magnitude thinner*. MaioraEtAl2024 (the only Tier 1 full-text paper in this theme) reports BiLSTM-based fall prediction with 0.83 accuracy and 0.73 AUC on older-adult IMU data — numbers that, while competitive for the fall-prediction subfield, are notably below the 95–99% accuracy territory routine in seizure prediction. Reviews in this theme (WesalEtAl2026 on wearable seizure detection/prediction, WuEtAl2025 on ML/DL EEG trends, Al-QuraishiEtAl2024 on driver state monitoring, several bci_methods reviews) serve a different function from the empirical papers in Themes 1–4: they catalogue methodological diversity in under-consolidated subfields.

於癲癇預測之外的五個 positional paper 域——跌倒、睡眠、偏頭痛、警覺度／嗜睡、預刺激／預測編碼——方法學共識呼應 Theme 1（EEG 或多模態生理訊號上的 CNN/LSTM/Transformer 混合為預設進路），但**證據基礎薄一個數量級**。MaioraEtAl2024（此主題中唯一 T1 全文論文）報告以 BiLSTM 於老年人 IMU 資料上進行跌倒預測，準確度 0.83、AUC 0.73——數字對跌倒預測子領域雖有競爭力，但明顯低於癲癇預測常態之 95–99% 準確度區間。本主題之文獻回顧（WesalEtAl2026 之穿戴式癲癇偵測／預測、WuEtAl2025 之 ML/DL EEG 趨勢、Al-QuraishiEtAl2024 之駕駛員狀態監測、若干 bci_methods 回顧）相較 Themes 1–4 之實證論文發揮不同功能：它們編目尚未鞏固子領域中的方法學多樣性。

### Debates / 爭議

The central debate in Theme 5 is not methodological but **structural**: does each non-seizure subdomain require its own specialized architecture and benchmarks, or can the seizure-prediction playbook (CHB-MIT-style benchmarking + hybrid deep architectures) be imported wholesale? The evidence is mixed. Multimodal fall prediction (MaioraEtAl2024 and related abstracts) shares enough signal structure with pre-ictal EEG that BiLSTM/CNN approaches transfer reasonably well, but migraine prediction (only 2 papers in the entire 162-paper collection) has no equivalent benchmark and no consensus architecture. Sleep forecasting (7 papers) sits in between, with most papers treating it as a classification problem rather than a true forecasting problem. The Al-QuraishiEtAl2024 vigilance review explicitly highlights that driver-state prediction uses fundamentally different methodology (eye-tracking + physiological fusion) from EEG-centric seizure prediction, suggesting that wholesale import is not straightforward.

Theme 5 核心爭議非方法學而是**結構性**：每一非癲癇子域是否需自身專用架構與標竿，或癲癇預測手冊（CHB-MIT 式標竿 + 混合深度架構）可否整批引入？證據紛雜。多模態跌倒預測（MaioraEtAl2024 與相關摘要）與預發作 EEG 共享足夠訊號結構，BiLSTM/CNN 方法可合理遷移；但偏頭痛預測（整個 162 篇集中僅 2 篇）無對等標竿亦無共識架構。睡眠預測（7 篇）居於其間，多數論文將其視為分類問題而非真正的預測問題。Al-QuraishiEtAl2024 警覺度回顧明確指出駕駛員狀態預測使用根本不同的方法學（眼動追蹤 + 生理融合），暗示整批引入並不直截。

### Dominant Methods / 主流方法

**Fall prediction:** IMU/accelerometry + BiLSTM or 1D-CNN (MaioraEtAl2024, Al-HammouriEtAl2025, Bianco et al.-aligned papers in the fall_prediction cluster). **Sleep forecasting:** pre-sleep EEG spectral analysis + classical ML or shallow DL. **Migraine prediction:** resting-state EEG features + ML (2 papers only — notably sparse). **Vigilance/drowsiness:** EEG + eye-tracking multimodal fusion (Al-QuraishiEtAl2024 review, Cinquetti et al. cited in positional paper). **Predictive coding / pre-stimulus:** spectral power analysis tied to active inference / free energy theory (BalarKapila2025 and predictive_coding cluster). **Reviews:** narrative and scoping reviews dominate over systematic reviews — a maturity gap vs. seizure prediction where systematic reviews have started to appear.

**跌倒預測：** IMU／加速度計 + BiLSTM 或 1D-CNN（MaioraEtAl2024、Al-HammouriEtAl2025、fall_prediction 簇中 Bianco 等人對齊論文）。**睡眠預測：** 睡前 EEG 頻譜分析 + 古典 ML 或淺層 DL。**偏頭痛預測：** 靜息態 EEG 特徵 + ML（僅 2 篇——特別稀疏）。**警覺度／嗜睡：** EEG + 眼動追蹤多模態融合（Al-QuraishiEtAl2024 回顧、positional paper 引用之 Cinquetti 等人）。**預測編碼／預刺激：** 頻譜功率分析連結主動推論／自由能理論（BalarKapila2025 與 predictive_coding 簇）。**回顧：** 敘事與範疇回顧主導，系統性回顧稀少——相較癲癇預測中系統性回顧已開始出現的成熟度差距。

### Key Results / 關鍵發現

| Subdomain | # Papers | Best Tier 1 Result | Methodological Maturity |
|-----------|---------|--------------------|-------------------------|
| Fall prediction | 14 | `MaioraEtAl2024` — 0.83 Acc, 0.73 AUC (BLSTM on IMU) | Moderate — benchmarks exist but are cohort-specific |
| Sleep forecasting | 7 | No T1 full text | Low — no agreed benchmark |
| Vigilance / drowsiness | 4 | No T1 full text (positional paper cites Cinquetti 2024) | Moderate — multimodal protocols established |
| Migraine prediction | 2 | No T1 full text | Very low — sparsest subdomain |
| Predictive coding / pre-stimulus | 3 | No T1 full text | Theoretical — limited empirical predictive BCI translation |
| Reviews (cross-subdomain) | 12 | `WesalEtAl2026`, `WuEtAl2025`, `Al-QuraishiEtAl2024` | Scoping-review stage |

The most actionable signal from Theme 5 is the **paper-count asymmetry itself**: the ratio between seizure-prediction (83 papers) and migraine-prediction (2 papers) is ~40:1. The positional paper's framing of these as parallel domains is not supported by the volume of methodological work actually underway in each. This directly informs the gap-analysis step.

Theme 5 最可行之訊號是**論文數不對稱本身**：癲癇預測（83 篇）與偏頭痛預測（2 篇）之比例約為 40:1。positional paper 將此等域框為平行之定位，並未被各域實際進行中之方法學工作量所支持。此直接啟發缺口分析步驟。

---

## Cross-Theme Analysis / 跨主題分析

### Methodological Trends Over Time / 方法學時間趨勢

A clear temporal arc runs across all five themes. **2019–2021** was the era of CNN + LSTM establishment (Nasseri et al. 2021 wrist-worn LSTM, Aldahr et al. 2023 federated CNN-LSTM — both cited as hubs in Step 2). **2022–2023** saw attention mechanisms and first Transformer variants (LiEtAl2022 memristor CNN, GuoEtAl2023 contrastive). **2024–2026** has been the Transformer-dominance era: CaoEtAl2026, PhamTran2026 EEG-Titans, ZhangEtAl2026 HCFT, QuEtAl2026 causal attention, LiEtAl2025b spatio-temporal attention, WangEtAl2025c CGTNet, AhmadEtAl2026 hybrid with attention — essentially all 2025–2026 T1 seizure-prediction papers use attention as a core architectural component. Alongside this, **2024–2026** also sees the emergence of foundation-model / SSL approaches (BaryMacq2024, Anjum2024 LiPCoT, AmiriEtAl2026 PI-GNN), and the first serious deployment-constrained papers (CaoEtAl2026 distillation, AbbasiEtAl2025 edge, JangEtAl2026 single-channel). The methodological trajectory is: CNN → CNN+LSTM → CNN+LSTM+attention → Transformer-dominant → (emerging) SSL-pretrained Transformers + edge deployment.

一條清晰的時間弧線貫穿五主題。**2019–2021** 是 CNN + LSTM 建立期（Nasseri et al. 2021 腕戴式 LSTM、Aldahr et al. 2023 聯邦 CNN-LSTM——皆於 Step 2 被引用為樞紐）。**2022–2023** 見證注意力機制與首批 Transformer 變體（LiEtAl2022 憶阻 CNN、GuoEtAl2023 對比式）。**2024–2026** 為 Transformer 主導期：CaoEtAl2026、PhamTran2026 EEG-Titans、ZhangEtAl2026 HCFT、QuEtAl2026 因果注意、LiEtAl2025b 時空注意、WangEtAl2025c CGTNet、AhmadEtAl2026 混合含注意——本質上所有 2025–2026 年 T1 癲癇預測論文皆以注意力作為核心架構組件。同時，**2024–2026** 亦見基礎模型／SSL 方法興起（BaryMacq2024、Anjum2024 LiPCoT、AmiriEtAl2026 PI-GNN），以及首批嚴肅的部署約束論文（CaoEtAl2026 蒸餾、AbbasiEtAl2025 邊緣、JangEtAl2026 單通道）。方法學軌跡為：CNN → CNN+LSTM → CNN+LSTM+注意 → Transformer 主導 → （新興）SSL 預訓練 Transformer + 邊緣部署。

### Converging Findings / 匯聚發現

Three findings converge robustly across themes. **(1) Subject-specific models strongly outperform subject-independent models** — this holds in seizure prediction (KoutsouvelisEtAl2024's 20-point gap), in fall prediction (MaioraEtAl2024 explicitly notes class-imbalance and subject-specific calibration matter), and by implication in every subdomain of Theme 5 where small-cohort studies dominate. **(2) Multimodal fusion outperforms unimodal pipelines when modalities are carefully chosen** — WesalEtAl2026 documents this explicitly for wearable seizure detection (best combination EDA + BVP + ACC + temperature reaches 75.6% sensitivity vs. single-modality baselines), and the same pattern appears across fall prediction (MaioraEtAl2024's IMU fusion) and multimodal seizure prediction (Saeizadeh et al. 2024 cited in positional paper with EEG+ECG). **(3) CHB-MIT performance has saturated** — multiple independent groups report ≥96% sensitivity with FPR ≤ 0.05/h, and the distribution of reported numbers on this benchmark is now narrower than the measurement uncertainty of the underlying annotation process. The converging implication is that future quantitative progress will be demonstrated on *other* datasets, not CHB-MIT.

三項發現跨主題穩健匯聚。**（1）主體特異模型強烈勝過主體無關模型**——此於癲癇預測成立（KoutsouvelisEtAl2024 之 20 點差距）、於跌倒預測成立（MaioraEtAl2024 明確指出類別不平衡與主體特異校準至關重要），並經由隱含推論於 Theme 5 各小群組研究主導之子域皆然。**（2）審慎選擇模態下，多模態融合勝過單模態流水線**——WesalEtAl2026 明確記錄此於穿戴式癲癇偵測（最佳組合 EDA + BVP + ACC + 溫度達 75.6% 敏感度 vs. 單模態基線），跨跌倒預測（MaioraEtAl2024 之 IMU 融合）與多模態癲癇預測（positional paper 引用之 Saeizadeh et al. 2024 以 EEG+ECG）出現相同模式。**（3）CHB-MIT 效能已飽和**——多個獨立研究團隊報告 ≥96% 敏感度、FPR ≤ 0.05/h，且此標竿上報告數字之分佈現已窄於底層標註過程之測量不確定性。匯聚意涵：未來定量進展將於**其他**資料集展現，而非 CHB-MIT。

### Diverging Findings / 分歧發現

Two divergences are substantive. **(1) Cross-dataset transferability** — same architecture gives very different numbers on CHB-MIT vs. SNUH vs. MSSM vs. Siena (LiEtAl2025b: 96.6% CHB-MIT vs. 94.2% MSSM; JangEtAl2026: 97.92% CHB-MIT vs. 94.93% SNUH; QiEtAl2025: 92.97% CHB-MIT vs. 92.79% Siena). This divergence is not noise; it reflects genuine dataset structural differences (annotation protocols, patient demographics, recording hardware) that the field has not fully characterized. **(2) Accuracy-deployability frontier** — papers targeting edge deployment (CaoEtAl2026 at 0.082M params, ZhengEtAl2025 at 2.8 channels, JangEtAl2026 single-channel) report noticeably different accuracy-resource trade-off curves, with no consensus on the Pareto frontier. CaoEtAl2026 claims essentially no accuracy loss at 3-4 orders of magnitude parameter reduction; ZhengEtAl2025 reports ~15-point sensitivity loss for 85% channel reduction. These cannot both be reflecting the same frontier.

兩項分歧實質存在。**（1）跨資料集可遷移性**——相同架構於 CHB-MIT vs. SNUH vs. MSSM vs. Siena 上給出非常不同的數字（LiEtAl2025b：96.6% CHB-MIT vs. 94.2% MSSM；JangEtAl2026：97.92% CHB-MIT vs. 94.93% SNUH；QiEtAl2025：92.97% CHB-MIT vs. 92.79% Siena）。此分歧非噪聲；它反映真實之資料集結構差異（標註協定、病患人口統計、記錄硬體），此領域尚未充分刻劃。**（2）準確度－可部署性前沿**——針對邊緣部署之論文（CaoEtAl2026 於 0.082M 參數、ZhengEtAl2025 於 2.8 通道、JangEtAl2026 單通道）報告明顯不同的準確度－資源權衡曲線，對於 Pareto 前沿無共識。CaoEtAl2026 宣稱於參數減少 3–4 個數量級時基本無準確度損失；ZhengEtAl2025 於 85% 通道縮減時報告 ~15 點敏感度損失。二者不可能同時反映相同前沿。

### Theme Interactions / 主題交互

Five papers sit at theme boundaries and serve as methodological bridges. **AmiriEtAl2026** (primary: Theme 3 cross-patient) also materially contributes to Theme 2 (uses self-supervised pre-training as a component) and Theme 1 (architecturally is a graph attention network). **BaryMacq2024** (primary: Theme 2) informs Theme 3 through its dataset-construction methodology for cross-centre SSL. **CaoEtAl2026** (primary: Theme 4 deployment) anchors Theme 1 benchmarks via its 99.54% CHB-MIT AUC. **MaioraEtAl2024** (primary: Theme 5 falls) imports Theme 1 architectures (BiLSTM) wholesale into the fall-prediction subdomain, providing the strongest empirical case that the seizure-prediction playbook transfers. **WuEtAl2025 / WesalEtAl2026** (primary: Theme 5 reviews) explicitly review Themes 1 and 4 methods, serving as narrative bridges between the empirical and deployment branches of the literature. The methodological dependency graph is therefore: Theme 2 (SSL) → feeds Theme 3 (generalization) → feeds Themes 1 & 4 (benchmarked performance and deployment) → reviewed by Theme 5.

五篇論文處於主題邊界並作為方法學橋樑。**AmiriEtAl2026**（主要：Theme 3 跨病患）亦實質貢獻於 Theme 2（使用自監督預訓練為組件）與 Theme 1（架構上為圖注意力網路）。**BaryMacq2024**（主要：Theme 2）透過其跨中心 SSL 之資料集建構方法學啟發 Theme 3。**CaoEtAl2026**（主要：Theme 4 部署）經其 99.54% CHB-MIT AUC 錨定 Theme 1 標竿。**MaioraEtAl2024**（主要：Theme 5 跌倒）將 Theme 1 架構（BiLSTM）整批引入跌倒預測子域，提供癲癇預測手冊遷移之最強實證。**WuEtAl2025 / WesalEtAl2026**（主要：Theme 5 回顧）明確回顧 Themes 1 與 4 之方法，作為文獻實證與部署分支之敘事橋樑。方法學依賴圖因此為：Theme 2（SSL）→ 餵入 Theme 3（泛化）→ 餵入 Themes 1 與 4（標竿效能與部署）→ 由 Theme 5 回顧。

---

## Paper–Theme Mapping / 論文主題對照

> Full index of all 162 shortlisted papers with theme, methodology, tier, and bridge-paper annotations. Sorted by theme, then tier, then composite score.
> 全部 162 篇入選論文之主題、方法學、層級與橋樑論文註記完整索引。依主題、層級、綜合分排序。

| Citation Key / 引用鍵 | Theme / 主題 | Methodology / 方法學 | Tier | Composite | Bridge? / 跨主題 |
|----------------------|-------------|---------------------|------|-----------|-------------------|
| `WesalEtAl2026` | T1 | Review | 1 | 4.80 | T5↔T4 |
| `KoutsouvelisEtAl2024` | T1 | Computational | 1 | 4.50 | T1↔T3 |
| `WuEtAl2025` | T1 | Review | 1 | 4.50 | T5↔T1↔T4 |
| `SunkaraRajakumari2023` | T1 | Computational | 1 | 4.50 | — |
| `QuEtAl2026` | T1 | Computational | 1 | 4.50 | — |
| `AhmadEtAl2026` | T1 | Computational | 1 | 4.50 | T1↔T3 |
| `LiaoEtAl2025a` | T1 | Computational | 1 | 4.50 | — |
| `PhamTran2026` | T1 | Computational | 1 | 4.50 | — |
| `ZhengEtAl2025` | T1 | Computational | 1 | 4.50 | T3↔T4 |
| `AbbasiEtAl2025` | T1 | Computational | 1 | 4.50 | T1↔T4 |
| `WangEtAl2026b` | T1 | Computational | 1 | 4.50 | — |
| `AlkhrijahEtAl2025` | T1 | Computational | 1 | 4.50 | — |
| `WangEtAl2025c` | T1 | Computational | 1 | 4.50 | — |
| `LiEtAl2025b` | T1 | Computational | 1 | 4.50 | — |
| `EsmaeilpourEtAl2024` | T1 | Computational | 2 | 4.40 | — |
| `CostaEtAl2024` | T1 | Computational | 2 | 4.40 | — |
| `PrathabanBalasubramanian2021` | T1 | Computational | 2 | 4.30 | — |
| `YamakawaEtAl2020` | T1 | Computational | 2 | 4.30 | — |
| `WangEtAl2021a` | T1 | Computational | 2 | 4.30 | — |
| `ShiLiu2023` | T1 | Computational | 2 | 4.20 | — |
| `GunasekaranEtAl2025` | T1 | Computational | 2 | 4.20 | — |
| `GhanimiEtAl2024` | T1 | Computational | 2 | 4.20 | — |
| `Cherouati2023` | T1 | Computational | 2 | 4.20 | — |
| `HusseinEtAl2022` | T1 | Computational | 2 | 4.20 | — |
| `KimEtAl2025b` | T1 | Computational | 2 | 4.20 | — |
| `TanEtAl2025` | T1 | Review | 2 | 4.20 | — |
| `YimanWenqi2025` | T1 | Computational | 2 | 4.20 | — |
| `QamarEtAl2025` | T1 | Review | 2 | 4.20 | — |
| `MohammadSaeed2025` | T1 | Computational | 2 | 4.20 | — |
| `KapustynskaEtAl2024` | T1 | Computational | 2 | 4.20 | — |
| `NEtAl2025` | T1 | Computational | 2 | 4.20 | — |
| `KumarEtAl2026` | T1 | Computational | 2 | 4.20 | — |
| `FengEtAl2025` | T1 | Computational | 2 | 4.20 | — |
| `WangEtAl2021b` | T1 | Computational | 3 | 4.10 | — |
| `CaoEtAl2018` | T1 | Computational | 3 | 4.10 | — |
| `NasseriEtAl2021` | T1 | Computational | 3 | 4.00 | — |
| `AbdelhameedBayoumi2021` | T1 | Computational | 3 | 4.00 | — |
| `SaadoonEtAl2025` | T1 | Computational | 3 | 4.00 | — |
| `Chen2023` | T1 | Computational | 3 | 4.00 | — |
| `RenEtAl2025` | T1 | Computational | 3 | 4.00 | — |
| `AlarfajEtAl2025` | T1 | Computational | 3 | 4.00 | — |
| `GodoyEtAl2022` | T1 | Computational | 3 | 4.00 | — |
| `ZhouEtAl2026a` | T1 | Computational | 3 | 4.00 | — |
| `ZhangZhang2025` | T1 | Computational | 3 | 4.00 | — |
| `HasnaouiDjebbari2026` | T1 | Computational | 3 | 4.00 | — |
| `WongEtAl2023` | T1 | Review | 3 | 3.90 | — |
| `PN2024` | T1 | Computational | 3 | 3.90 | — |
| `RaibagEtAl2024` | T1 | Computational | 3 | 3.90 | — |
| `AnsariEtAl2020` | T1 | Computational | 3 | 3.80 | — |
| `FeudjioEtAl2021` | T1 | Computational | 3 | 3.80 | — |
| `MalikEtAl2026` | T1 | Review | 3 | 3.80 | — |
| `VelasquezEtAl2024` | T1 | Review | 3 | 3.80 | — |
| `KhanEtAl2018` | T1 | Computational | 3 | 3.80 | — |
| `DissanayakeEtAl2020` | T1 | Computational | 3 | 3.80 | — |
| `XuEtAl2022` | T1 | Computational | 4 | 3.70 | — |
| `WangEtAl2026a` | T1 | Computational | 4 | 3.70 | — |
| `JiangEtAl2024a` | T1 | Computational | 4 | 3.70 | — |
| `WangEtAl2025b` | T1 | Computational | 4 | 3.70 | — |
| `HasijaEtAl2025` | T1 | Computational | 4 | 3.70 | — |
| `FengEtAl2026` | T1 | Computational | 4 | 3.70 | — |
| `GuoEtAl2023` | T2 | Computational | 1 | 4.50 | T1↔T2 |
| `QiEtAl2025` | T2 | Theoretical | 1 | 4.50 | T1↔T2 |
| `BaryMacq2024` | T2 | Computational | 1 | 4.50 | T2↔T3 |
| `MahdiBaghdadi2026` | T2 | Computational | 1 | 4.50 | — |
| `YinEtAl2026` | T2 | Computational | 3 | 4.00 | — |
| `StaffordEtAl2026` | T2 | Observational | 3 | 4.00 | — |
| `LiaoEtAl2024` | T2 | Computational | 3 | 4.00 | — |
| `ShiEtAl2025` | T2 | Computational | 3 | 4.00 | — |
| `LutesEtAl2022` | T2 | Computational | 3 | 4.00 | — |
| `HoffsommerEtAl2025` | T2 | Computational | 3 | 4.00 | — |
| `PuahEtAl2025` | T2 | Computational | 3 | 4.00 | — |
| `PelentritouEtAl2025` | T2 | Computational | 3 | 4.00 | — |
| `Anjum2024` | T2 | Theoretical | 3 | 4.00 | — |
| `KollaEtAl2026` | T2 | Computational | 3 | 4.00 | — |
| `ZhouEtAl2026b` | T2 | Computational | 3 | 4.00 | — |
| `MajumderEtAl2026` | T2 | Computational | 3 | 4.00 | — |
| `Kumar2025` | T2 | Computational | 4 | 3.70 | — |
| `KeyEtAl2024` | T2 | Computational | 4 | 3.70 | — |
| `TruongDelorme2025` | T2 | Computational | 4 | 3.70 | — |
| `MoncyEtAl2025b` | T2 | Computational | 4 | 3.70 | — |
| `MoncyEtAl2025a` | T2 | Computational | 4 | 3.70 | — |
| `SaeediEtAl2023` | T2 | Computational | 4 | 3.70 | — |
| `KimEtAl2025a` | T2 | Computational | 4 | 3.70 | — |
| `YangModesitt2023` | T2 | Computational | 4 | 3.70 | — |
| `AmiriEtAl2026` | T3 | Computational | 1 | 4.50 | T1↔T2↔T3 |
| `TariqEtAl2020` | T3 | Computational | 2 | 4.30 | — |
| `DaoudBayoumi2019` | T3 | Computational | 2 | 4.20 | — |
| `ChoiEtAl2022` | T3 | Computational | 2 | 4.20 | — |
| `RevathyM2025` | T3 | Computational | 3 | 4.00 | — |
| `LiEtAl2025a` | T3 | Engineering | 3 | 4.00 | — |
| `KhanEtAl2025` | T3 | Computational | 4 | 3.70 | — |
| `JeongEtAl2025` | T3 | Computational | 4 | 3.70 | — |
| `JabbarEtAl2025` | T3 | Theoretical | 4 | 3.70 | — |
| `JadduEtAl2024` | T3 | Computational | 4 | 3.70 | — |
| `CaoEtAl2026` | T4 | Computational | 1 | 4.80 | T1↔T4 |
| `ZhangEtAl2026` | T4 | Computational | 1 | 4.80 | — |
| `LiEtAl2022` | T4 | Engineering | 1 | 4.50 | — |
| `YedurkarEtAl2025` | T4 | Computational | 1 | 4.50 | — |
| `JangEtAl2026` | T4 | Computational | 1 | 4.50 | T1↔T4 |
| `ThahniyathEtAl2024` | T4 | Computational | 2 | 4.40 | — |
| `SEtAl2025` | T4 | Computational | 2 | 4.20 | — |
| `SharmaEtAl2025` | T4 | Computational | 2 | 4.20 | — |
| `RenEtAl2022` | T4 | Computational | 3 | 3.90 | — |
| `Paneru2026` | T4 | Computational | 4 | 3.70 | — |
| `PaillardEtAl2025` | T4 | Theoretical | 4 | 3.70 | — |
| `YangEtAl2025` | T4 | Computational | 4 | 3.70 | — |
| `De2025` | T4 | Computational | 4 | 3.70 | — |
| `MaioraEtAl2024` | T5 | Computational | 1 | 4.50 | T1→T5 |
| `CesariEtAl2023` | T5 | Computational | 2 | 4.20 | — |
| `GuanEtAl2025` | T5 | Computational | 2 | 4.20 | — |
| `KapustynskaEtAl2025` | T5 | Computational | 2 | 4.20 | — |
| `TomalinEtAl2025` | T5 | Computational | 2 | 4.20 | — |
| `ZhangEtAl2024` | T5 | Computational | 2 | 4.20 | — |
| `LinEtAl2025` | T5 | Computational | 2 | 4.20 | — |
| `Chakraborty2026` | T5 | Computational | 2 | 4.20 | — |
| `DinhEtAl2025` | T5 | Computational | 3 | 4.00 | — |
| `NesaragiEtAl2025` | T5 | Computational | 3 | 4.00 | — |
| `JamaraniEtAl2026` | T5 | Computational | 3 | 4.00 | — |
| `BanvilleEtAl2020` | T5 | Computational | 3 | 4.00 | — |
| `ZhangEtAl2025` | T5 | Theoretical | 3 | 3.90 | — |
| `JankevičiūtėEtAl2026` | T5 | Computational | 3 | 3.90 | — |
| `LiaoEtAl2025b` | T5 | Review | 3 | 3.90 | — |
| `CavanaghEtAl2024` | T5 | Computational | 3 | 3.90 | — |
| `MehrlatifanMolla2024` | T5 | Review | 3 | 3.80 | — |
| `MouEtAl2026` | T5 | Review | 3 | 3.80 | — |
| `Al-QuraishiEtAl2024` | T5 | Review | 3 | 3.80 | — |
| `SakakibaraEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `ChenEtAl2026a` | T5 | Computational | 4 | 3.70 | — |
| `GeEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `YangEtAl2026` | T5 | Computational | 4 | 3.70 | — |
| `SercekEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `GongEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `EguinoaEtAl2026` | T5 | Theoretical | 4 | 3.70 | — |
| `SuffianEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `DegirmenciEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `RommelEtAl2022` | T5 | Computational | 4 | 3.70 | — |
| `ZhongEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `Gómez-MoralesEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `FuEtAl2026` | T5 | Theoretical | 4 | 3.70 | — |
| `WangEtAl2025a` | T5 | Computational | 4 | 3.70 | — |
| `ZhongEtAl2026` | T5 | Computational | 4 | 3.70 | — |
| `ChenEtAl2026b` | T5 | Computational | 4 | 3.70 | — |
| `XuYu2026` | T5 | Computational | 4 | 3.70 | — |
| `Al-HammouriEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `BalarKapila2025` | T5 | Theoretical | 4 | 3.70 | — |
| `JiangEtAl2024b` | T5 | Computational | 4 | 3.70 | — |
| `ZhuEtAl2026` | T5 | Computational | 4 | 3.70 | — |
| `GongEtAl2026` | T5 | Computational | 4 | 3.70 | — |
| `SchwarzEtAl2023` | T5 | Computational | 4 | 3.70 | — |
| `LuEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `SonntagEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `GargEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `ZuoEtAl2024` | T5 | Computational | 4 | 3.70 | — |
| `AkamaEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `ChanEtAl2023` | T5 | Observational | 4 | 3.70 | — |
| `HrubýEtAl2026` | T5 | Review | 4 | 3.70 | — |
| `KölblEtAl2025` | T5 | Theoretical | 4 | 3.70 | — |
| `CinquettiEtAl2025` | T5 | Computational | 4 | 3.70 | — |
| `DercksenEtAl2026` | T5 | Computational | 4 | 3.70 | — |
| `Lanini-MaggiEtAl2021` | T5 | Computational | 4 | 3.50 | — |
| `KrishnaEtAl2020` | T5 | Computational | 4 | 3.50 | — |
| `TheivadasPonnan2025` | T5 | Computational | 4 | 3.50 | — |

---

Files / 檔案: `step6_sota_review.md`, `step6_knowledge_graph.canvas`
Next step / 下一步: `/research-gaps` (Step 7 — gap identification with Checkpoint 3: 戰場選擇)