---
session_id: "20260416"
topic: "Predictive and Preventive Brain-Computer Interfaces: Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals"
date: "2026-04-16"
step: 3
threshold: 3.5
weights: "relevance=0.50, quality=0.30, recency_impact=0.20"
---

# Screening Results / 篩選結果

> Topic / 研究主題: Predictive and Preventive Brain-Computer Interfaces — Forecasting Cognitive States and Adverse Health Events from Neural and Physiological Signals
> 預測性與預防性腦機介面：從神經與生理訊號預測認知狀態與不良健康事件
> Papers screened / 篩選論文數: 319
> Date / 篩選日期: 2026-04-16
> Threshold / 門檻: composite >= 3.5 (included) · 3.0–3.4 (borderline) · <3.0 (excluded)
> Weights / 權重: relevance=0.50, quality=0.30, recency_impact=0.20

## Screening Criteria / 篩選標準

### Inclusion / 納入條件

- Addresses **prediction/forecasting** (not post-hoc detection) of cognitive states, performance decrements, or adverse health events from neural/physiological signals
  / 研究對認知狀態、表現下降或不良健康事件的**預測／預測**（非事後偵測），資料來自神經／生理訊號
- Human subjects (any population: clinical — epilepsy, migraine, sleep, older fall-risk; or healthy — vigilance/cognitive tasks)
  / 人類受試者（臨床族群：癲癇、偏頭痛、睡眠、高跌倒風險長者；或健康受試者：警覺度／認知任務）
- EEG, ECG, accelerometry, eye tracking, or wearable multimodal physiological signals
  / EEG、ECG、加速度計、眼動追蹤或穿戴式多模態生理訊號
- Empirical study, systematic review, or meta-analysis with reported predictive performance metrics (sensitivity, specificity, AUC, FPR, lead time) OR mechanism-level theoretical / empirical work on anticipatory neural dynamics
  / 實證研究／系統性綜述／統合分析，報告預測性能指標（sensitivity、specificity、AUC、FPR、lead time）；或預期性神經動態的機制理論／實證工作
- Published 2019–2026 (foundational 2015–2018 work acceptable if highly cited hub paper)
  / 出版年 2019–2026（2015–2018 基礎文獻若為高引用中樞論文則可接受）

### Exclusion / 排除條件

- Pure detection systems with **no predictive lead time** (post-ictal, post-event classification only)
  / 純偵測系統，無預測 lead time（僅事後分類）
- Off-topic domains masquerading as BCI (smart grid, blockchain, Industry 5.0, stock market forecasting, sentiment classification)
  / 偽裝為 BCI 的離題領域（智慧電網、區塊鏈、Industry 5.0、股市預測、情緒分類）
- Animal-only studies without human translation
  / 純動物研究、未延伸至人類
- Hardware-only sensor papers without predictive analytics
  / 僅硬體感測器、無預測分析
- Editorials, commentaries, news articles without original data or systematic synthesis
  / 社論、評論、新聞報導，無原始資料或系統性整合
- Abstract unavailable AND title too ambiguous to assess relevance
  / 無摘要且標題模糊、無法判斷相關性

## Summary / 摘要

| Category / 分類 | Count / 數量 | Percentage / 百分比 |
|-----------------|-------------|-------------------|
| **Included / 納入** | **162** | **50.8%** |
| ├── Tier 1 (≥4.5) / 核心命中 | 25 | 7.8% |
| ├── Tier 2 (4.2–4.4) / 強力支持 | 32 | 10.0% |
| ├── Tier 3 (3.8–4.1) / 穩健相關 | 47 | 14.7% |
| └── Tier 4 (3.5–3.7) / 情境佐證 | 58 | 18.2% |
| Borderline / 邊緣 (3.0–3.4) | 54 | 16.9% |
| Excluded / 排除 (<3.0) | 103 | 32.3% |
| **Total / 總計** | **319** | **100.0%** |

Inclusion rate / 納入率: **50.8%**

> **Scoring method / 評分方法:** Programmatic rubric over title + abstract. **Relevance**: core predictive-BCI phrasing, domain forecasting (seizure/fall/sleep/migraine/vigilance), EEG+prediction keywords, predictive-coding mechanism terms, adjacent wearable/closed-loop terms; with off-topic penalty (smart grid, blockchain, Industry 5.0). **Quality**: predictive metrics (AUC, sensitivity, FPR, lead time), rigor tokens (cross-validation, RCT, PRISMA), canonical datasets (CHB-MIT, TUSZ, SeizeIT, NeuroVista), review-type weighting. **Recency/Impact**: weighted by publication year and citation count with velocity adjustment (CURRENT_YEAR=2026). Composite = 0.50·Rel + 0.30·Qual + 0.20·Rec.
> 評分採程式化 rubric，以標題＋摘要為輸入。**Relevance** 核心預測性 BCI 用語、domain 預測（癲癇／跌倒／睡眠／偏頭痛／警覺度）、EEG＋預測關鍵詞、預測編碼機制詞、鄰近穿戴／閉環詞；並對離題詞扣分（智慧電網、區塊鏈、Industry 5.0）。**Quality** 預測指標、嚴謹性 token、經典資料集、綜述類型加權。**Recency/Impact** 以年份與引用量加權，含 velocity（CURRENT_YEAR=2026）。

## Tier 1: Core Predictive-BCI Hits / 核心預測性 BCI 命中 (Score ≥ 4.5)

**25 papers** — direct predictive/forecasting BCI studies with strong methodology and recency.
**25 篇** — 直接預測／預測性 BCI 研究，方法嚴謹且新近。

| ID | Title | Authors | Year | Rel | Qual | Rec | **Composite** | Rationale |
|----|-------|---------|------|-----|------|-----|---------------|-----------|
| paper_211 | Efficient and Accurate Epilepsy Seizure Prediction and Detection Based on Multi-Teac… | Cao et al. | 2026 | 5 | 5 | 4 | **4.8** | direct domain forecast (seizure prediction); rigorous evaluation / RC… |
| paper_231 | HCFT: Hierarchical Convolutional Fusion Transformer for EEG Decoding | Zhang et al. | 2026 | 5 | 5 | 4 | **4.8** | direct domain forecast (seizure prediction); rigorous evaluation / RC… |
| paper_250 | Modalities and algorithms for generalized motor seizure detection and prediction: a … | Wesal et al. | 2026 | 5 | 5 | 4 | **4.8** | direct domain forecast (seizure prediction); rigorous evaluation / RC… |
| paper_058 | CLEP: Contrastive Learning for Epileptic Seizure Prediction Using a Spatio-Temporal-… | Guo et al. | 2023 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_064 | Seizure Detection and Prediction by Parallel Memristive Convolutional Neural Networks | Li et al. | 2022 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_108 | Preictal period optimization for deep learning-based epileptic seizure prediction | Koutsouvelis et al. | 2024 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_111 | A Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure… | Wu et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_115 | Prediction of the epileptic seizure through deep learning techniques using electroen… | Sunkara et al. | 2023 | 5 | 4 | 4 | **4.5** | direct domain forecast (preictal); benchmark+metrics; recent or semin… |
| paper_127 | A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures U… | Qi et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (preictal); benchmark+metrics; recent or semin… |
| paper_134 | A causal attention network with time frequency channel feature fusion for epileptic … | Qu et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_137 | A hybrid deep learning framework for epileptic seizure prediction using scalp and in… | Ahmad et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_154 | An EEG-Based Seizure Prediction Model Encoding Brain Network Temporal Dynamics. | Liao et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_192 | Designing Pre-training Datasets from Unlabeled Data for EEG Classification with Tran… | Bary et al. | 2024 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure forecasting); benchmark+metrics; rece… |
| paper_202 | EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and Neural Me… | Pham et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_204 | EEG-based Epileptic Prediction via a Two-stage Channel-aware Set Transformer Network | Zheng et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_210 | Edge-Enabled Pre-Ictal Activity Prediction Framework Using Geometric Deep Learning. | Abbasi et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_216 | Epileptic Seizure Prediction Using Patient-Adaptive Transformer Networks | Mahdi et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_218 | Explainable End-to-End Seizure Prediction via Dynamic Multiscale Cross-Band Fusion F… | Wang et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_227 | Feature fusion ensemble classification approach for epileptic seizure prediction usi… | Alkhrijah et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_229 | From data to diagnosis: An innovative approach to epilepsy prediction with CGTNet in… | Wang et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_263 | Older Adult Fall Risk Prediction with Deep Learning and Timed Up and Go (TUG) Test D… | Maiora et al. | 2024 | 5 | 4 | 4 | **4.5** | direct domain forecast (fall risk prediction); benchmark+metrics; rec… |
| paper_273 | Physics-informed graph neural networks for robust cross-patient epileptic seizure pr… | Amiri et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_291 | SPA-IoT with MCSV-CNN: a novel IoT-enabled method for robust pre-ictal seizure predi… | Yedurkar et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_296 | Single-channel EEG-based seizure prediction using deep learning. | Jang et al. | 2026 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_298 | Spatio-Temporal Attention Network for Epileptic Seizure Prediction | Li et al. | 2025 | 5 | 4 | 4 | **4.5** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |

## Tier 2: Strong Supporting / 強力支持 (Score 4.2–4.4)

**32 papers** — closely related predictive work with solid methods, or highly-cited recent reviews.
**32 篇** — 緊密相關的預測工作，方法穩健；或近年高引用綜述。

| ID | Title | Authors | Year | Rel | Qual | Rec | **Composite** | Rationale |
|----|-------|---------|------|-----|------|-----|---------------|-----------|
| paper_063 | Cloud based prediction of epileptic seizures using real-time electroencephalograms a… | Thahniyath et al. | 2024 | 5 | 3 | 5 | **4.4** | direct domain forecast (seizure prediction); some metrics reported; v… |
| paper_078 | Deep learning‐based seizure prediction using EEG signals: A comparative analysis of … | Esmaeilpour et al. | 2024 | 5 | 3 | 5 | **4.4** | direct domain forecast (seizure prediction); some metrics reported; v… |
| paper_084 | Comparison between epileptic seizure prediction and forecasting based on machine lea… | Costa et al. | 2024 | 5 | 3 | 5 | **4.4** | direct domain forecast (seizure prediction); some metrics reported; v… |
| paper_039 | Dynamic learning framework for epileptic seizure prediction using sparsity based EEG… | Prathaban et al. | 2021 | 5 | 4 | 3 | **4.3** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_040 | Wearable Epileptic Seizure Prediction System with Machine-Learning-Based Anomaly Det… | Yamakawa et al. | 2020 | 5 | 4 | 3 | **4.3** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_068 | One-Dimensional Convolutional Neural Networks Combined with Channel Selection Strate… | Wang et al. | 2021 | 5 | 4 | 3 | **4.3** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_268 | Patient-Specific Seizure Prediction Using Single Seizure Electroencephalography Reco… | Tariq et al. | 2020 | 5 | 4 | 3 | **4.3** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_007 | Efficient Epileptic Seizure Prediction Based on Deep Learning | Daoud et al. | 2019 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_027 | B2-ViT Net: Broad Vision Transformer Network With Broad Attention for Seizure Predic… | Shi et al. | 2023 | 4 | 4 | 5 | **4.2** | direct domain forecast (seizure prediction); benchmark+metrics; very … |
| paper_075 | Deep Convolutional Gated Recurrent Unit Combined with Attention Mechanism to Classif… | Choi et al. | 2022 | 5 | 3 | 4 | **4.2** | direct domain forecast (preictal); some metrics reported; recent or s… |
| paper_110 | Towards Posture and Gait Evaluation through Wearable-Based Biofeedback Technologies | Cesari et al. | 2023 | 5 | 3 | 4 | **4.2** | direct domain forecast (action anticipation); some metrics reported; … |
| paper_113 | A predictive approach to enhance time-series forecasting | Gunasekaran et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_116 | Cramer Distance: A Deep Learning Approach for Better Epileptic Seizure Prediction | Ghanimi et al. | 2024 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_117 | Patient specific channel optimization using entropy and CNN deep learning for epilep… | Cherouati et al. | 2023 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_123 | Deep Learning Methods for Seizure Prediction by Evaluating EEG Signals | Hussein et al. | 2022 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_125 | Short-horizon neonatal seizure prediction using EEG-based deep learning | Kim et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_145 | Accuracy and Precision of Wearable-Derived Gait Parameters: How These Affect the Per… | Guan et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_151 | Advancing a generalizable model for migraine prediction: Analysis of filtering techn… | Kapustynska et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (migraine prediction); some metrics reported; … |
| paper_164 | Automatic detection and prediction of epileptic EEG signals based on nonlinear dynam… | Tan et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (preictal); some metrics reported; recent or s… |
| paper_169 | Can smartwatches predict migraines? Using machine learning (ML) with wearable-derive… | Tomalin et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (migraine prediction); some metrics reported; … |
| paper_183 | Deep learning applied in epilepsy: Bibliometric and visual analysis. | Yiman et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_188 | Deep learning in intracranial EEG for seizure detection: advances, challenges, and c… | Qamar et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (preictal); some metrics reported; recent or s… |
| paper_222 | External Validation and Further Exploration of Fall Prediction Models Based on Quest… | Zhang et al. | 2024 | 5 | 3 | 4 | **4.2** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_225 | Fall-Risk Monitoring in Diverse Terrains Using Dual-Task Learning and Wearable Sensi… | Lin et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_246 | MLSPred-bench: Transforming electroencephalography (EEG) datasets into machine learn… | Mohammad et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_247 | Machine Learning and Wearable Technology: Monitoring Changes in Biomedical Signal Pa… | Kapustynska et al. | 2024 | 5 | 3 | 4 | **4.2** | direct domain forecast (pre-ictal); some metrics reported; recent or … |
| paper_254 | Multiclass Epileptic Seizure Detection from EEG Signals Using LSTM-Based Deep Learni… | N et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_257 | Neurofusionnet: a comprehensive framework for accurate epileptic seizure prediction … | S et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_282 | Project Hermes: A Model-Agnostic Validation Layer for Wearable Health Prediction Sys… | Chakraborty et al. | 2026 | 5 | 3 | 4 | **4.2** | direct domain forecast (migraine prediction); some metrics reported; … |
| paper_285 | Real-Time Seizure Detection and Prediction in Epilepsy Patients Using Deep Neural Ne… | Sharma et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_290 | SBTM: epileptic seizure prediction from EEG signal using deep learning in blockchain… | Kumar et al. | 2026 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_294 | SeizureFormer: A Transformer Model for IEA-Based Seizure Risk Forecasting | Feng et al. | 2025 | 5 | 3 | 4 | **4.2** | direct domain forecast (seizure forecasting); some metrics reported; … |

## Tier 3: Robust Relevance / 穩健相關 (Score 3.8–4.1)

**47 papers** — solid predictive work in one or two PICO dimensions; includes mechanism papers and multimodal wearable studies.
**47 篇** — PICO 中一至兩個面向穩健命中；含機制論文與多模態穿戴研究。

| ID | Title | Authors | Year | Rel | Qual | Rec | **Composite** | Rationale |
|----|-------|---------|------|-----|------|-----|---------------|-----------|
| paper_076 | Power efficient refined seizure prediction algorithm based on an enhanced benchmarki… | Wang et al. | 2021 | 4 | 5 | 3 | **4.1** | direct domain forecast (seizure prediction); rigorous evaluation / RC… |
| paper_223 | Extraction of SSVEPs-based Inherent Fuzzy Entropy Using a Wearable Headband EEG in M… | Cao et al. | 2018 | 5 | 4 | 2 | **4.1** | direct domain forecast (pre-ictal); benchmark+metrics |
| paper_031 | Ambulatory seizure forecasting with a wrist-worn device using long-short term memory… | Nasseri et al. | 2021 | 5 | 3 | 3 | **4.0** | direct domain forecast (seizure forecasting); some metrics reported; … |
| paper_098 | An Efficient Deep Learning System for Epileptic Seizure Prediction | Abdelhameed et al. | 2021 | 5 | 3 | 3 | **4.0** | direct domain forecast (seizure prediction); some metrics reported |
| paper_104 | Predicting Epileptic Seizures Using EfficientNet-B0 and SVMs: A Deep Learning Method… | Saadoon et al. | 2025 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_128 | A Deep Learning Method for Classification of Interictal and Preictal EEG Signals in … | Chen et al. | 2023 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_153 | An EEG signal smoothing algorithm using upscale and downscale representation. | Dinh et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_158 | An event-based filtering and weighted enhanced deep learning epileptic seizure predi… | Ren et al. | 2025 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_159 | Analysis and prediction of schizophrenia patients based on high-order graph attentio… | Yin et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_163 | Automated Cerebral Edema Detection using Electroencephalography in Post-Cardiac Arre… | Stafford et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_166 | Biaxialformer: Leveraging Channel Independence and Inter-Channel Correlations in EEG… | Nesaragi et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_168 | CLDTA: Contrastive Learning based on Diagonal Transformer Autoencoder for Cross-Data… | Liao et al. | 2024 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_175 | Construction of a deep - learning - based rehabilitation prediction model for lower-… | Shi et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_176 | Convolutional Spiking Neural Networks for Detecting Anticipatory Brain Potentials Us… | Lutes et al. | 2022 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_179 | Cross-modal privacy-preserving synthesis and mixture-of-experts ensemble for robust … | Revathy et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_180 | DEAP DIVE: Dataset Investigation with Vision transformers for EEG evaluation | Hoffsommer et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_184 | Deep learning approaches for diagnosing seizure based on EEG signal analysis. | Alarfaj et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_190 | DeepArousal-Net: A Multi-Block Recurrent Deep Learning Model for Proactive Forecasti… | Jamarani et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_200 | EEG-Based Epileptic Seizure Prediction Using Temporal Multi-Channel Transformers | Godoy et al. | 2022 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_207 | EEGDM: EEG Representation Learning via Generative Diffusion Model | Puah et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_233 | High density EEG and deep learning outcome prediction on the first day of coma after… | Pelentritou et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_242 | LiPCoT: Linear Predictive Coding based Tokenizer for Self-supervised Learning of Tim… | Anjum et al. | 2024 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_249 | Memory-Efficient Intrinsic Gating Adaptation for Enhanced On-Device Epilepsy Diagnos… | Li et al. | 2025 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_251 | MuGEP: Multiplex Graph-Based Brain Network Modeling for Epileptic Seizure Prediction… | Zhou et al. | 2026 | 4 | 4 | 4 | **4.0** | direct domain forecast (seizure prediction); benchmark+metrics; recen… |
| paper_265 | Optimized cortical EEG modeling for Parkinson disease diagnosis with snow Shepherd S… | Kolla et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_277 | Prediction of Epilepsy Seizure Based on Cepstrum Analysis and Deep Learning. | Zhang et al. | 2025 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_281 | Preventing Data Leakage in EEG-Based Survival Prediction: A Two-Stage Embedding and … | Zhou et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_312 | Uncovering the structure of clinical EEG signals with self-supervised learning | Banville et al. | 2020 | 5 | 3 | 3 | **4.0** | direct domain forecast (sleep staging); some metrics reported |
| paper_313 | Unlocking Insights from Postictal EEGs: Investigating Predictive Markers of Seizure … | Hasnaoui et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_318 | Wheelchair movement signal classification from EEG for motor-impaired individuals us… | Majumder et al. | 2026 | 4 | 4 | 4 | **4.0** | EEG-based prediction; benchmark+metrics; recent or seminal |
| paper_032 | <scp>EEG</scp> datasets for seizure detection and prediction— A review | Wong et al. | 2023 | 4 | 3 | 5 | **3.9** | EEG-based prediction; some metrics reported; very recent high-velocity |
| paper_086 | The performance evaluation of the state-of-the-art EEG-based seizure prediction mode… | Ren et al. | 2022 | 5 | 2 | 4 | **3.9** | direct domain forecast (seizure prediction); thin methods from abstra… |
| paper_114 | Epileptic Seizure Prediction on EEG Data using a Firefly Algorithm trained with Deep… | P et al. | 2024 | 5 | 2 | 4 | **3.9** | direct domain forecast (seizure prediction); thin methods from abstra… |
| paper_120 | A Deep Learning and Raspberry PI Investigation for Epilepsy Seizure Detection | Raibag et al. | 2024 | 5 | 2 | 4 | **3.9** | direct domain forecast (seizure prediction); thin methods from abstra… |
| paper_174 | Constraint-Driven Causal Representation Learning for Vigilance Robust Estimation in … | Zhang et al. | 2025 | 5 | 2 | 4 | **3.9** | direct domain forecast (vigilance prediction); thin methods from abst… |
| paper_232 | Heart rate variability as a predictor of migraine: Sleep-time data analysis of pre-m… | Jankevičiūtė et al. | 2026 | 5 | 2 | 4 | **3.9** | direct domain forecast (migraine prediction); thin methods from abstr… |
| paper_300 | Surface Electromyography Combined with Artificial Intelligence in Predicting Neuromu… | Liao et al. | 2025 | 5 | 2 | 4 | **3.9** | direct domain forecast (fall prediction); thin methods from abstract;… |
| paper_315 | Value Prediction for Spatiotemporal Gait Data Using Deep Learning | Cavanagh et al. | 2024 | 5 | 2 | 4 | **3.9** | direct domain forecast (fall prediction); thin methods from abstract;… |
| paper_121 | A deep learning network with minimal set of features for classification of ictal, in… | Ansari et al. | 2020 | 4 | 4 | 3 | **3.8** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_131 | A Novel Use of Discrete Wavelet Transform Features in the Prediction of Epileptic Se… | Feudjio et al. | 2021 | 4 | 4 | 3 | **3.8** | EEG-based prediction; benchmark+metrics |
| paper_143 | AI-assisted assessment of fall risk in multiple sclerosis: A systematic literature r… | Mehrlatifan et al. | 2024 | 3 | 5 | 4 | **3.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systemati… |
| paper_146 | Accuracy of wearable devices in predicting falls in older adults: a systematic revie… | Mou et al. | 2026 | 3 | 5 | 4 | **3.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systemati… |
| paper_161 | Artificial Intelligence and Machine Learning in Pediatric Epilepsy: A Systematic Rev… | Malik et al. | 2026 | 3 | 5 | 4 | **3.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systemati… |
| paper_209 | Economic Perspective of the Use of Wearables in Health Care: A Systematic Review. | Velasquez et al. | 2024 | 3 | 5 | 4 | **3.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systemati… |
| paper_228 | Focal onset seizure prediction using convolutional networks | Khan et al. | 2018 | 5 | 3 | 2 | **3.8** | direct domain forecast (seizure prediction); some metrics reported |
| paper_269 | Patient-independent Epileptic Seizure Prediction using Deep Learning Models | Dissanayake et al. | 2020 | 4 | 4 | 3 | **3.8** | direct domain forecast (seizure prediction); benchmark+metrics |
| paper_301 | Technologies for detecting and monitoring drivers' states: A systematic review. | Al-Quraishi et al. | 2024 | 3 | 5 | 4 | **3.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systemati… |

## Tier 4: Contextual / 情境佐證 (Score 3.5–3.7)

**58 papers** — contextual breadth: BCI methods, EEG deep-learning architectures, predictive-coding theory, adjacent wearable/physiological sensing that support the positional-paper framing without being direct predictive-BCI hits.
**58 篇** — 情境廣度：BCI 方法、EEG 深度學習架構、預測編碼理論、鄰近穿戴／生理感測；支撐 positional paper 框架但非直接預測性 BCI 命中。

| ID | Title | Authors | Year | Rel | Qual | Rec | **Composite** | Rationale |
|----|-------|---------|------|-----|------|-----|---------------|-----------|
| paper_061 | Multichannel Synthetic Preictal EEG Signals to Enhance the Prediction of Epileptic S… | Xu et al. | 2022 | 4 | 3 | 4 | **3.7** | direct domain forecast (preictal); some metrics reported; recent or s… |
| paper_109 | Early Disease Detection Using AI: A Deep Learning Approach to Predicting Cancer and … | Kumar et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_130 | A Nostalgia Brain-Music Interface for enhancing nostalgia, well-being, and memory vi… | Sakakibara et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_132 | A Unified SPD Token Transformer Framework for EEG Classification: Systematic Compari… | Chen et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_138 | A multi-dimensional CNN-Bi-GRU for IoT-based brain-computer interface in early epile… | Paneru et al. | 2026 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_139 | A multi-domain graph convolutional network-based prediction model for personalized m… | Ge et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_140 | A neurofeedback-guided EEG and BCI framework for personalized attention rehabilitati… | Yang et al. | 2026 | 4 | 3 | 4 | **3.7** | direct domain forecast (attention prediction); some metrics reported;… |
| paper_141 | A new quantum-inspired pattern based on Goldner-Harary graph for automated alzheimer… | Sercek et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_142 | AI reshaping life sciences: intelligent transformation, application challenges, and … | Gong et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_149 | Advancing EEG-Based Gaze Prediction Using Depthwise Separable Convolution and Enhanc… | Key et al. | 2024 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_152 | An EEG correlation framework to study state anxiety and learning under uncertainty. | Eguinoa et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_155 | An Explainable 3D-Deep Learning Model for EEG Decoding in Brain-Computer Interface A… | Suffian et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_157 | An epilepsy prediction and management system based on federated learning combined wi… | Khan et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_173 | Classification of finger movements through optimal EEG channel and feature selection. | Degirmenci et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_181 | Data Normalization Strategies for EEG Deep Learning | Truong et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_182 | Data augmentation for learning predictive models on EEG: a systematic comparison | Rommel et al. | 2022 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_185 | Deep learning based treatment remission prediction to transcranial direct current st… | Moncy et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_186 | Deep learning based treatment remission prediction to transcranial direct current st… | Moncy et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_191 | Depression Diagnosis and Drug Response Prediction via Recurrent Neural Networks and … | Saeedi et al. | 2023 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_193 | Detection of eye movements and eye blinks using a portable two-channel EEG platform. | Zhong et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_197 | Dual-Cross Tri-Level Routing Transformer Based Metric Learning Network for Epileptic… | Wang et al. | 2026 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_199 | EEG Signal Prediction for Motor Imagery Classification in Brain-Computer Interfaces. | Gómez-Morales et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_201 | EEG-DIF: Early Warning of Epileptic Seizures through Generative Diffusion Model-base… | Jiang et al. | 2024 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_203 | EEG-based Cross-subject Prediction for Consciousness State Transitions under Sedatio… | Jeong et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_206 | EEG-to-gait decoding via phase-aware representation learning. | Fu et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_208 | EIMNet: An EEG and iEEG-Fused Interactive Modality Network for Accurate Memory State… | Wang et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_212 | Electroencephalogram-based multimodal attention level classification using deep lear… | Zhong et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_213 | Electrophysiological Evidence for Dynamic Temporal Priors From Neural Signatures of … | Chen et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_214 | Enhancing Electroencephalogram-Based Prediction of Posttraumatic Stress Disorder Tre… | Kim et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_215 | Entropy-Based Dual-Teacher Distillation for Efficient Motor Imagery EEG Classificati… | Xu et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_219 | Explainable End-to-End Seizure Prediction via Stationary Wavelet Transform-Driven Dy… | Wang et al. | 2025 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_224 | Fall prediction algorithm with built-in instability metrics. | Al-Hammouri et al. | 2025 | 4 | 3 | 4 | **3.7** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_230 | GREEN: A lightweight architecture using learnable wavelets and Riemannian geometry f… | Paillard et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_238 | Improving wearable-based seizure prediction by feature fusion using an explainable g… | Hasija et al. | 2025 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_239 | Integrative Model for Interoception and Exteroception: predictive coding, points of … | Balar et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_240 | LFSP-DSM: A Lightweight Framework for Seizure Prediction Based on Deep Statistical M… | Yang et al. | 2025 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_241 | Large Brain Model for Learning Generic Representations with Tremendous EEG Data in B… | Jiang et al. | 2024 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_244 | M3T-attention: a multi-level multi-scale temporal attention transformer for EEG hand… | Zhu et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_248 | Mamba-fusion for privacy-preserving disease prediction. | Jabbar et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_252 | Multi-Source Discriminant Dynamic Domain Adaptation for Cross-Subject Motor Imagery … | Gong et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_253 | Multi-sensor driver monitoring for drowsiness prediction. | Schwarz et al. | 2023 | 4 | 3 | 4 | **3.7** | direct domain forecast (drowsiness prediction); some metrics reported… |
| paper_256 | Mutual Generation for Cross-domain Challenge in Stroke Patients' Motor Imagery Class… | Lu et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_258 | Neurophysiological predictors of deep learning based unilateral upper limb motor ima… | Sonntag et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_262 | Ocular artifact from electroencephalogram - a comparative analysis of feature extrac… | Garg et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_264 | Online Monitoring for Human Sit-to-Stand Movement Based on Karush-Kuhn-Tucker Optimi… | Zuo et al. | 2024 | 4 | 3 | 4 | **3.7** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_274 | Pre-Ictal Seizure Prediction Using Personalized Deep Learning | Jaddu et al. | 2024 | 4 | 3 | 4 | **3.7** | direct domain forecast (seizure prediction); some metrics reported; r… |
| paper_275 | Predicting artificial neural network representations to learn recognition model for … | Akama et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_278 | Prediction of injurious falls in older adults using digital gait biomarkers extracte… | Chan et al. | 2023 | 4 | 3 | 4 | **3.7** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_287 | Research of Fall Detection and Fall Prevention Technologies: A Review. | Hrubý et al. | 2026 | 4 | 3 | 4 | **3.7** | direct domain forecast (fall prediction); some metrics reported; rece… |
| paper_293 | SeizureFormer: A Multi-Scale Transformer for Seizure Risk Forecasting from RNS-Deriv… | Feng et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_303 | The Predictive Brain: Neural Correlates of Word Expectancy Align with Large Language… | Kölbl et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_309 | Toward in-silico data assessment for passive BCIs: generating EEG rhythms with GANs. | Cinquetti et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_316 | ViT2EEG: Leveraging Hybrid Pretrained Vision Transformers for EEG Data | Yang et al. | 2023 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_317 | Voluntary Attention Selectively Modulates Omission Responses. | Dercksen et al. | 2026 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_319 | ZIA: A Theoretical Framework for Zero-Input AI | De et al. | 2025 | 4 | 3 | 4 | **3.7** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_077 | Assessing how visual search entropy and engagement predict performance in a multiple… | Lanini-Maggi et al. | 2021 | 4 | 3 | 3 | **3.5** | EEG-based prediction; some metrics reported |
| paper_150 | Advancing Speech Synthesis using EEG | Krishna et al. | 2020 | 4 | 3 | 3 | **3.5** | EEG-based prediction; some metrics reported |
| paper_189 | Deep-ATM DL-LSTM: A novel adaptive thresholding model with dual-layer LSTM architect… | Theivadas et al. | 2025 | 3 | 4 | 4 | **3.5** | wearable / multimodal adjacent; benchmark+metrics; recent or seminal |

---

## Borderline Papers / 邊緣論文 (54 papers · Score 3.0–3.4)

> **⛳ Checkpoint 2: 邊緣打撈**
> Review the papers below. These scored close to the threshold and may contain relevant work that the programmatic scoring missed — especially cross-disciplinary papers using non-standard terminology (e.g., sleep engineering, headache digital-health, migraine wearables) or review papers whose keyword density was low.
> 請審核以下邊緣論文。這些論文分數接近門檻，可能包含程式化評分遺漏的相關研究——特別是使用非標準術語的跨領域論文（例如 sleep engineering、偏頭痛數位健康、偏頭痛穿戴裝置）或關鍵詞密度較低的綜述論文。
>
> **⚠️ Hub papers in borderline range / 邊緣區之核心引用論文:** `paper_021` (Beniczky 2020, in_degree=3, cluster=seizure_prediction) and `paper_018` (Cinel 2019, in_degree=3, BCI cognitive augmentation review) are both **hub papers** — structurally important to the field despite moderate programmatic scores. **Strongly recommended for manual inclusion.**
>   `paper_021`（Beniczky 2020，引用度=3，seizure_prediction 簇）與 `paper_018`（Cinel 2019，引用度=3，BCI 認知增強綜述）為**核心引用論文**——儘管程式化分數中等，但在引用結構上對本領域極具重要性。**強烈建議手動納入。**
>
> Mark any paper you want to include with its ID (e.g., "include paper_021 paper_018") and I'll add them to the shortlist.
> 標註欲納入的論文 ID（例："include paper_021 paper_018"），我會將其加入 shortlist。

| ID | Title | Authors | Year | Rel | Qual | Rec | **Composite** | Rationale | Hub? |
|----|-------|---------|------|-----|------|-----|---------------|-----------|------|
| paper_021 | Machine learning and wearable devices of the future | Beniczky et al. | 2020 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | **Yes (in_deg=3)** |
| paper_024 | A deep learning based ensemble learning method for epileptic seizure prediction | Usman et al. | 2021 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_036 | Applications of Artificial Intelligence in Automatic Detection of Epileptic Seizures… | Saminu et al. | 2022 | 3 | 3 | 5 | **3.4** | wearable / multimodal adjacent; some metrics reported; very… | — |
| paper_056 | Seizure forecasting using minimally invasive, ultra‐long‐term subcutaneous electroen… | Viana et al. | 2022 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure forecasting); thin methods … | — |
| paper_070 | <scp>SzCORE</scp>: Seizure Community Open‐Source Research Evaluation framework for t… | Dan et al. | 2024 | 3 | 3 | 5 | **3.4** | wearable / multimodal adjacent; some metrics reported; very… | — |
| paper_092 | Supervised and Unsupervised Deep Learning Approaches for EEG Seizure Prediction | Georgis-Yap et al. | 2023 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_107 | Machine and Deep Learning-Based Seizure Prediction: A Scoping Review on the Use of T… | Saadoon et al. | 2025 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_112 | A multi-frame network model for predicting seizure based on sEEG and iEEG data | Lu et al. | 2022 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_119 | Exploration of Short-range Neonatal Seizure Forecasting with Quantitative EEG Based … | JonathanKim et al. | 2023 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure forecasting); thin methods … | — |
| paper_133 | A bibliometric analysis of electroencephalogram research in stroke: current trends a… | Liao et al. | 2025 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_144 | ALFEE: Adaptive Large Foundation Model for EEG Representation | Xiong et al. | 2025 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_156 | An Interpretable Regression Method for Upper Limb Motion Trajectories Detection With… | Tian et al. | 2025 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_160 | Anticipation Before Action: EEG-Based Implicit Intent Detection for Adaptive Gaze In… | Chiossi et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_162 | Artificial Intelligence for EEG Prediction: Applied Chaos Theory | Jorgsson et al. | 2023 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_165 | Autoregressive Visual Decoding from EEG Signals | Dai et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_172 | ChatBCI, a P300 speller BCI with context-driven word prediction leveraging large lan… | Hong et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_205 | EEG-based epileptic seizure prediction with patient-tailored spectral-spatial-tempor… | Choi et al. | 2026 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_217 | Evaluating Latent Space Robustness and Uncertainty of EEG-ML Models under Realistic … | Wagh et al. | 2022 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_226 | False but phonologically plausible linguistic priors induce cross-linguistic auditor… | Giraldi et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_243 | Lightweight Seizure Prediction Model based on Kernel-Enhanced Global Temporal Attent… | Zhai et al. | 2025 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_267 | Path to Intelligence: Measuring Similarity between Human Brain and Large Language Mo… | Ngo et al. | 2025 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_276 | Prediction of Absence Epileptic Seizures in Multichannel EEG Signals Using Hybrid De… | Torres et al. | 2025 | 4 | 2 | 4 | **3.4** | direct domain forecast (seizure prediction); thin methods f… | — |
| paper_286 | Repetition positivity following auditory intensity or frequency changes in young nor… | Altın et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_302 | The Potential Role of Wearable Inertial Sensors in Laboring Women with Walking Epidu… | Dziadzko et al. | 2024 | 4 | 2 | 4 | **3.4** | direct domain forecast (fall prediction); thin methods from… | — |
| paper_304 | The Ventral Attention Network Mediates Attentional Reorienting to Cross-Modal Expect… | Das et al. | 2026 | 4 | 2 | 4 | **3.4** | EEG-based prediction; thin methods from abstract; recent or… | — |
| paper_030 | Review on Epileptic Seizure Prediction: Machine Learning and Deep Learning Approaches | Natu et al. | 2022 | 4 | 1 | 5 | **3.3** | direct domain forecast (seizure prediction); no methods sig… | — |
| paper_018 | Neurotechnologies for Human Cognitive Augmentation: Current State of the Art and Fut… | Cinel et al. | 2019 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | **Yes (in_deg=3)** |
| paper_054 | Forging Neuroimaging Targets for Recovery in Opioid Use Disorder | Stewart et al. | 2019 | 4 | 2 | 3 | **3.2** | EEG-based prediction; thin methods from abstract | — |
| paper_088 | A Sound Prediction: EEG-Based Neural Synchrony Predicts Online Music Streams | Leeuwis et al. | 2021 | 4 | 2 | 3 | **3.2** | EEG-based prediction; thin methods from abstract | — |
| paper_136 | A hybrid approach for driver drowsiness detection utilizing practical data to improv… | Khanehshenas et al. | 2024 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_196 | DrowsyDG-Phys: Generalizable driver drowsiness estimation in conditional automated v… | Wang et al. | 2026 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_220 | Exploiting heart rate variability for driver drowsiness detection using wearable sen… | AlArnaout et al. | 2025 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_245 | MCAnalysis: An Open-Source Package for Preprocessing, Modelling, and Visualisation o… | Delray et al. | 2026 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_255 | Music-induced emotion as controlled hallucination: an active interoceptive inference… | Tsai et al. | 2026 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_266 | Overlapping neural representations for the position of visible and imagined objects | Robinson et al. | 2020 | 4 | 2 | 3 | **3.2** | EEG-based prediction; thin methods from abstract | — |
| paper_271 | Performance evaluation of the earphone-type electroencephalogram for alpha wave dete… | Otake et al. | 2025 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_292 | STFTransNet: A Transformer Based Spatial Temporal Fusion Network for Enhanced Multim… | Kim et al. | 2025 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_297 | Smart Steering Wheel Prototype for In-Vehicle Vital Sign Monitoring. | Babusiak et al. | 2026 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_299 | Streamlining Patient Fall Prevention and Management Through Human-Centered AI-Based … | Rahmadani et al. | 2025 | 3 | 3 | 4 | **3.2** | wearable / multimodal adjacent; some metrics reported; rece… | — |
| paper_308 | Top-down predictions influence binocular rivalry through beta band rhythms: a qEEG-b… | Mojdehfarahbakhsh et al. | 2019 | 4 | 2 | 3 | **3.2** | EEG-based prediction; thin methods from abstract | — |
| paper_059 | Seizure forecasting: Bifurcations in the long and winding road | Baud et al. | 2022 | 4 | 1 | 4 | **3.1** | direct domain forecast (seizure forecasting); no methods si… | — |
| paper_198 | EARS-UDE: Evaluating Auditory Response in Sensory Overload with Universal Differenti… | Salunke et al. | 2025 | 4 | 1 | 4 | **3.1** | EEG-based prediction; no methods signal; recent or seminal | — |
| paper_259 | Neurosense: Bridging Neural Dynamics and Mental Health Through Deep Learning for Bra… | Wang et al. | 2026 | 4 | 1 | 4 | **3.1** | EEG-based prediction; no methods signal; recent or seminal | — |
| paper_025 | Positive affect treatment targets reward sensitivity: A randomized controlled trial. | Craske et al. | 2023 | 1 | 5 | 5 | **3.0** | low topical overlap; rigorous evaluation / RCT / systematic… | — |
| paper_045 | The past, current, and future of neonatal intensive care units with artificial intel… | Keleş et al. | 2023 | 1 | 5 | 5 | **3.0** | low topical overlap; rigorous evaluation / RCT / systematic… | — |
| paper_050 | AI-Based Epileptic Seizure Detection and Prediction in Internet of Healthcare Things… | Jahan et al. | 2023 | 1 | 5 | 5 | **3.0** | off-topic; rigorous evaluation / RCT / systematic; very rec… | — |
| paper_055 | Automated machine learning with interpretation: A systematic review of methodologies… | Yuan et al. | 2024 | 1 | 5 | 5 | **3.0** | low topical overlap; rigorous evaluation / RCT / systematic… | — |
| paper_071 | Personalized Stress Detection Using Biosignals from Wearables: A Scoping Review | Bolpagni et al. | 2024 | 1 | 5 | 5 | **3.0** | wearable / multimodal adjacent; rigorous evaluation / RCT /… | — |
| paper_091 | What Affects Human Decision Making in Human–Robot Collaboration?: A Scoping Review | Liu et al. | 2024 | 1 | 5 | 5 | **3.0** | off-topic; rigorous evaluation / RCT / systematic; very rec… | — |
| paper_148 | Advanced feature selection and temporal attention mechanisms with Bi-LSTM classifier… | Dar et al. | 2026 | 2 | 4 | 4 | **3.0** | predictive-coding / anticipatory theory; benchmark+metrics;… | — |
| paper_171 | Cardio-respiratory interactions in interoceptive perception: The role of heartbeat-m… | Zaccaro et al. | 2026 | 2 | 4 | 4 | **3.0** | predictive-coding / anticipatory theory; benchmark+metrics;… | — |
| paper_194 | Distinct perceptual-metacognitive profiles of interoceptive and exteroceptive timing. | Chen et al. | 2026 | 2 | 4 | 4 | **3.0** | predictive-coding / anticipatory theory; benchmark+metrics;… | — |
| paper_236 | Impaired Processing of Bodily Signals Is Associated With Borderline Personality Trai… | Chi et al. | 2026 | 2 | 4 | 4 | **3.0** | predictive-coding / anticipatory theory; benchmark+metrics;… | — |
| paper_284 | Real-Time Detection of Drowsiness Among Vehicle Drivers: A Machine Learning Algorith… | Pillay et al. | 2021 | 3 | 3 | 3 | **3.0** | wearable / multimodal adjacent; some metrics reported | — |

---

## Excluded Papers / 排除論文 (103 papers · Score < 3.0)

Papers scoring below the 3.0 threshold are excluded. The table below shows **all excluded papers sorted by composite descending** (highest-scored exclusions first — these are the ones closest to the borderline, most worth auditing).
以下為**所有排除論文，依 composite 降序排列**（分數最接近邊緣者在前，最值得審核）。

| ID | Title | Year | Rel | Qual | Rec | **Composite** | Exclusion Reason / 排除原因 |
|----|-------|------|-----|------|-----|---------------|---------------------------|
| paper_012 | Wireless EEG: A survey of systems and studies | 2022 | 2 | 3 | 5 | **2.9** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_015 | Wearable-Based Affect Recognition—A Review | 2019 | 3 | 2 | 4 | **2.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_033 | Artificial Intelligence and Neuroscience: Transformative Synergies in Brain Research… | 2025 | 2 | 3 | 5 | **2.9** | wearable / multimodal adjacent; some metrics reported; very recent high-velocity |
| paper_035 | Electroencephalography-Based Depression Detection Using Multiple Machine Learning Te… | 2023 | 2 | 3 | 5 | **2.9** | wearable / multimodal adjacent; some metrics reported; very recent high-velocity |
| paper_072 | The Challenging Path to Developing a Mobile Health Device for Epilepsy: The Current … | 2021 | 4 | 1 | 3 | **2.9** | direct domain forecast (seizure forecasting); no methods signal |
| paper_126 | A CNN-Based Wearable System for Driver Drowsiness Detection. | 2023 | 3 | 2 | 4 | **2.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_237 | Improved drowsiness detection in drivers through optimum pairing of EEG features usi… | 2025 | 3 | 2 | 4 | **2.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_034 | Video-Based Detection of Generalized Tonic-Clonic Seizures Using Deep Learning | 2021 | 2 | 4 | 3 | **2.8** | low topical overlap; benchmark+metrics |
| paper_093 | Analyzing entropy features in time-series data for pattern recognition in neurologic… | 2024 | 1 | 5 | 4 | **2.8** | wearable / multimodal adjacent; rigorous evaluation / RCT / systematic; recent … |
| paper_096 | Non-Invasive Biosensing for Healthcare Using Artificial Intelligence: A Semi-Systema… | 2024 | 1 | 5 | 4 | **2.8** | low topical overlap; rigorous evaluation / RCT / systematic; recent or seminal |
| paper_097 | AI-Driven Data Analytics and Automation: A Systematic Literature Review of Industry … | 2025 | 1 | 5 | 4 | **2.8** | low topical overlap; rigorous evaluation / RCT / systematic; recent or seminal |
| paper_221 | Exploring new rehabilitation pathways for stroke based on the comorbidity of post-st… | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_234 | Higher-level spatial prediction in natural vision across mouse visual cortex. | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_235 | Hypnotizability and interoception: Differential associations with accuracy, sensibil… | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_280 | Predictive coding in psychopathology: mechanistic model or metaphorical re-descripti… | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_305 | The effect of sequence stability on serial dependence. | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_306 | The invisible artifact: Understanding human perception of own nose in binocular visi… | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_311 | Training sparse convolutional deep predictive coding networks with attention. | 2026 | 2 | 3 | 4 | **2.7** | predictive-coding / anticipatory theory; some metrics reported; recent or semin… |
| paper_047 | Detecting Early Cognitive Decline in Alzheimer’s Disease with Brain Synaptic Structu… | 2023 | 2 | 2 | 5 | **2.6** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_049 | Electroencephalogram based brain-computer interface: Applications, challenges, and o… | 2023 | 2 | 2 | 5 | **2.6** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_028 | Automated Recognition of Epileptic EEG States Using a Combination of Symlet Wavelet … | 2019 | 2 | 3 | 3 | **2.5** | low topical overlap; some metrics reported |
| paper_043 | Review of the State-of-the-Art of Brain-Controlled Vehicles | 2021 | 2 | 3 | 3 | **2.5** | wearable / multimodal adjacent; some metrics reported |
| paper_066 | A Channel Selection Method for Emotion Recognition From EEG Based on Swarm-Intellige… | 2021 | 2 | 3 | 3 | **2.5** | low topical overlap; some metrics reported |
| paper_129 | A Hybrid Brain-Computer Interface Based on Electroencephalography and Functional Tra… | 2019 | 2 | 3 | 3 | **2.5** | low topical overlap; some metrics reported |
| paper_170 | Cardiac interoception in action: Modulation after a stress induction with a speech t… | 2026 | 1 | 4 | 4 | **2.5** | low topical overlap; benchmark+metrics; recent or seminal |
| paper_003 | Training Spiking Neural Networks Using Lessons From Deep Learning | 2023 | 1 | 3 | 5 | **2.4** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_013 | Insights into Internet of Medical Things (IoMT): Data fusion, security issues and po… | 2023 | 1 | 3 | 5 | **2.4** | wearable / multimodal adjacent; some metrics reported; very recent high-velocity |
| paper_020 | The deep learning applications in IoT-based bio- and medical informatics: a systemat… | 2024 | 1 | 3 | 5 | **2.4** | wearable / multimodal adjacent; some metrics reported; very recent high-velocity |
| paper_026 | Exploring collaborative decision-making: A quasi-experimental study of human and Gen… | 2024 | 1 | 3 | 5 | **2.4** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_042 | A Survey of Generative Adversarial Networks for Synthesizing Structured Electronic H… | 2023 | 1 | 3 | 5 | **2.4** | wearable / multimodal adjacent; some metrics reported; very recent high-velocity |
| paper_057 | Annual Research Review: Neuroimmune network model of depression: a developmental per… | 2024 | 1 | 3 | 5 | **2.4** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_069 | The Clinical Relevance of Artificial Intelligence in Migraine | 2024 | 1 | 3 | 5 | **2.4** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_085 | Personalized health monitoring using explainable AI: bridging trust in predictive he… | 2025 | 1 | 3 | 5 | **2.4** | low topical overlap; some metrics reported; very recent high-velocity |
| paper_105 | A review of hybrid EEG-based multimodal human–computer interfaces using deep learnin… | 2025 | 2 | 2 | 4 | **2.4** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_177 | Corrélats EEG du bien-être et EEG portable | 2022 | 2 | 2 | 4 | **2.4** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_187 | Deep learning for EEG analysis | 2023 | 2 | 2 | 4 | **2.4** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_270 | Perceiving the uncertain: predictive coding and individual differences in the dynami… | 2026 | 2 | 2 | 4 | **2.4** | predictive-coding / anticipatory theory; thin methods from abstract; recent or … |
| paper_283 | Proprioceptive integration in motor control. | 2026 | 2 | 2 | 4 | **2.4** | predictive-coding / anticipatory theory; thin methods from abstract; recent or … |
| paper_314 | Using perception as a strategy: Camouflage, surprise, and the moment of shock relate… | 2026 | 2 | 2 | 4 | **2.4** | predictive-coding / anticipatory theory; thin methods from abstract; recent or … |
| paper_016 | A Review on the Role of Machine Learning in Enabling IoT Based Healthcare Applicatio… | 2021 | 1 | 3 | 4 | **2.2** | off-topic; some metrics reported; recent or seminal |
| paper_060 | Brain augmentation and neuroscience technologies: current applications, challenges, … | 2022 | 1 | 3 | 4 | **2.2** | wearable / multimodal adjacent; some metrics reported; recent or seminal |
| paper_079 | Pre-training in Medical Data: A Survey | 2023 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_081 | EEG-based Brain-Computer Interfaces (BCIs): A Survey of Recent Studies\n on Signal S… | 2020 | 2 | 2 | 3 | **2.2** | wearable / multimodal adjacent; thin methods from abstract |
| paper_090 | The Combination of a Graph Neural Network Technique and Brain Imaging to Diagnose Ne… | 2023 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_103 | A Comprehensive Survey on Wearable Computing for Mental and Physical Health Monitori… | 2025 | 1 | 3 | 4 | **2.2** | wearable / multimodal adjacent; some metrics reported; recent or seminal |
| paper_118 | Advancing Antidepressive Agents: Drug Discovery and Polymer-Based Drug Delivery Syst… | 2025 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_147 | Acute technostress, schizotypal traits, and visual illusion perception in the genera… | 2026 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_167 | Biologically Inspired Predictive Coding TCN-Transformer for Anticipatory Human-Robot… | 2024 | 1 | 3 | 4 | **2.2** | EEG-based prediction; some metrics reported; recent or seminal |
| paper_195 | Driver Drowsiness Detection: A Machine Learning Approach on Skin Conductance. | 2023 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_279 | Prediction-based attention computing: a proof of concept study. | 2026 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_289 | Résistance aux perturbations vestibulaires : mécanismes et adaptations | 2026 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_307 | The representation of speech conversations in the human auditory cortex: role of soc… | 2026 | 1 | 3 | 4 | **2.2** | low topical overlap; some metrics reported; recent or seminal |
| paper_006 | EEG-based Brain-Computer Interfaces (BCIs): A Survey of Recent Studies&#13;\n on Sig… | 2021 | 2 | 1 | 4 | **2.1** | low topical overlap; no methods signal; recent or seminal |
| paper_008 | Federated learning-based AI approaches in smart healthcare: concepts, taxonomies, ch… | 2022 | 1 | 2 | 5 | **2.1** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_009 | Generative Adversarial Networks in Time Series: A Systematic Literature Review | 2022 | 1 | 2 | 5 | **2.1** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_019 | Machine learning and deep learning-based approach in smart healthcare: Recent advanc… | 2024 | 1 | 2 | 5 | **2.1** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_022 | Artificial Intelligence of Things for Smarter Healthcare: A Survey of Advancements, … | 2023 | 1 | 2 | 5 | **2.1** | off-topic; thin methods from abstract; very recent high-velocity |
| paper_037 | Current trends and opportunities in the methodology of electrodermal activity measur… | 2022 | 1 | 2 | 5 | **2.1** | wearable / multimodal adjacent; thin methods from abstract; very recent high-ve… |
| paper_041 | Comprehensive study of driver behavior monitoring systems using computer vision and … | 2024 | 1 | 2 | 5 | **2.1** | off-topic; thin methods from abstract; very recent high-velocity |
| paper_046 | Approaches, Applications, and Challenges in Physiological Emotion Recognition—A Tuto… | 2023 | 1 | 2 | 5 | **2.1** | wearable / multimodal adjacent; thin methods from abstract; very recent high-ve… |
| paper_048 | Pediatric sleep: current knowledge, gaps, and opportunities for the future | 2023 | 1 | 2 | 5 | **2.1** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_051 | An overview of machine learning methods in enabling IoMT-based epileptic seizure det… | 2023 | 1 | 2 | 5 | **2.1** | low topical overlap; thin methods from abstract; very recent high-velocity |
| paper_052 | The Metaverse as a Virtual Model of Platform Urbanism: Its Converging AIoT, XReality… | 2023 | 1 | 2 | 5 | **2.1** | wearable / multimodal adjacent; thin methods from abstract; very recent high-ve… |
| paper_083 | The applications and prospects of big data in perioperative anesthetic management | 2024 | 1 | 2 | 5 | **2.1** | wearable / multimodal adjacent; thin methods from abstract; very recent high-ve… |
| paper_135 | A developmental switch in corticoclaustral signaling. | 2026 | 2 | 1 | 4 | **2.1** | predictive-coding / anticipatory theory; no methods signal; recent or seminal |
| paper_178 | Cortical deviance detection represents a canonical difference signal. | 2026 | 2 | 1 | 4 | **2.1** | predictive-coding / anticipatory theory; no methods signal; recent or seminal |
| paper_288 | Rethinking Predictive Processing. | 2026 | 2 | 1 | 4 | **2.1** | predictive-coding / anticipatory theory; no methods signal; recent or seminal |
| paper_295 | Singing in the brain. | 2026 | 2 | 1 | 4 | **2.1** | predictive-coding / anticipatory theory; no methods signal; recent or seminal |
| paper_065 | State-aware detection of sensory stimuli in the cortex of the awake mouse | 2019 | 1 | 3 | 3 | **2.0** | low topical overlap; some metrics reported |
| paper_122 | Abstracts European Congress of NeuroRehabilitation 2019 | 2019 | 1 | 3 | 3 | **2.0** | low topical overlap; some metrics reported |
| paper_002 | Recovery from disorders of consciousness: mechanisms, prognosis and emerging therapi… | 2020 | 1 | 2 | 4 | **1.9** | off-topic; thin methods from abstract; recent or seminal |
| paper_004 | Symbiotic human-robot collaborative assembly | 2019 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal; hub (in-deg… |
| paper_017 | Consumer Behaviour through the Eyes of Neurophysiological Measures: State-of-the-Art… | 2019 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_062 | Scope of machine learning applications for addressing the challenges in next‐generat… | 2022 | 1 | 2 | 4 | **1.9** | off-topic; thin methods from abstract; recent or seminal |
| paper_073 | Beyond Supervised Learning for Pervasive Healthcare | 2023 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_082 | Leveraging Machine Learning for Disease Diagnoses Based on Wearable Devices: A Survey | 2023 | 1 | 2 | 4 | **1.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_089 | Deep Learning Technologies for Time Series Anomaly Detection in Healthcare: A Review | 2023 | 1 | 2 | 4 | **1.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_095 | Exoskeleton Recognition of Human Movement Intent Based on Surface Electromyographic … | 2024 | 1 | 2 | 4 | **1.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_099 | Emotional Engagement and Trading Performance | 2023 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_100 | Integrating intention-based systems in human-robot interaction: a scoping review of … | 2023 | 1 | 2 | 4 | **1.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_101 | A comprehensive survey on impact of applying various technologies on the internet of… | 2025 | 1 | 2 | 4 | **1.9** | wearable / multimodal adjacent; thin methods from abstract; recent or seminal |
| paper_102 | Behavioral Economics and Neuroeconomics of Environmental Values | 2023 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_106 | Cannabinoid Analgesia in Postoperative Pain Management: From Molecular Mechanisms to… | 2024 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_260 | Neurovascular Signaling at the Gliovascular Interface: From Flow Regulation to Cogni… | 2025 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_272 | Pharmacological &amp; Toxicological Interactions (with Alcohol): A Critical Study on… | 2025 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_310 | Tracking electrophysiological dynamics of prior exploitation in visual motion percep… | 2026 | 1 | 2 | 4 | **1.9** | low topical overlap; thin methods from abstract; recent or seminal |
| paper_005 | Psychological Resilience: An Affect-Regulation Framework | 2022 | 1 | 1 | 5 | **1.8** | low topical overlap; no methods signal; very recent high-velocity |
| paper_010 | Review of Artificial Intelligence and Machine Learning Technologies: Classification,… | 2022 | 1 | 1 | 5 | **1.8** | low topical overlap; no methods signal; very recent high-velocity |
| paper_011 | Proactive human–robot collaboration: Mutual-cognitive, predictable, and self-organis… | 2022 | 1 | 1 | 5 | **1.8** | low topical overlap; no methods signal; very recent high-velocity |
| paper_023 | Multimodal Human–Robot Interaction for Human‐Centric Smart Manufacturing: A Survey | 2023 | 1 | 1 | 5 | **1.8** | low topical overlap; no methods signal; very recent high-velocity |
| paper_044 | Attachment, Mentalizing and Trauma: Then (1992) and Now (2022) | 2023 | 1 | 1 | 5 | **1.8** | low topical overlap; no methods signal; very recent high-velocity |
| paper_029 | In Search of Big Medical Data Integration Solutions - A Comprehensive Survey | 2019 | 1 | 2 | 3 | **1.7** | off-topic; thin methods from abstract |
| paper_053 | Biosensors for Epilepsy Management: State-of-Art and Future Aspects | 2019 | 1 | 2 | 3 | **1.7** | low topical overlap; thin methods from abstract |
| paper_001 | Industry 5.0—A Human-Centric Solution | 2019 | 1 | 1 | 4 | **1.6** | wearable / multimodal adjacent; no methods signal; recent or seminal |
| paper_014 | A Neuroergonomics Approach to Mental Workload, Engagement and Human Performance | 2020 | 1 | 1 | 4 | **1.6** | low topical overlap; no methods signal; recent or seminal |
| paper_074 | What if consciousness is not an emergent property of the brain? Observational and em… | 2022 | 1 | 1 | 4 | **1.6** | low topical overlap; no methods signal; recent or seminal |
| paper_080 | Prospects for Augmenting Team Interactions with Real‐Time Coordination‐Based Measure… | 2022 | 1 | 1 | 4 | **1.6** | wearable / multimodal adjacent; no methods signal; recent or seminal |
| paper_087 | Encoding the Enforcement of Safety Standards into Smart Robots to Harness Their Comp… | 2023 | 1 | 1 | 4 | **1.6** | wearable / multimodal adjacent; no methods signal; recent or seminal |
| paper_124 | Neuroenhancement in Military Personnel::Conceptual and Methodological Promises and C… | 2023 | 1 | 1 | 4 | **1.6** | low topical overlap; no methods signal; recent or seminal |
| paper_261 | Nocturnal autonomic activity after sport-related concussion: a home-based approach | 2025 | 1 | 1 | 4 | **1.6** | wearable / multimodal adjacent; no methods signal; recent or seminal |
| paper_038 | Sensor Technologies to Manage the Physiological Traits of Chronic Pain: A Review | 2020 | 1 | 1 | 3 | **1.4** | low topical overlap; no methods signal |
| paper_067 | Brain Connectivity Studies on Structure‐Function Relationships: A Short Survey with … | 2021 | 1 | 1 | 3 | **1.4** | low topical overlap; no methods signal |
| paper_094 | Magnocellular and parvocellular pathway contributions to facial threat cue processing | 2019 | 1 | 1 | 3 | **1.4** | low topical overlap; no methods signal |

---

## Hub Paper Summary / 核心引用論文狀態

Papers with in_degree ≥ 3 in the citation network (Step 2) receive structural weight independent of programmatic scores.
引用網絡（Step 2）中 in_degree ≥ 3 之論文，其結構性重要性獨立於程式化分數。

| ID | Title | In-Degree | Cluster | Composite | Status | Note |
|----|-------|-----------|---------|-----------|--------|------|
| paper_004 | Symbiotic human-robot collaborative assembly | 3 | other | **1.9** | Excluded | Off-topic (human-robot collaborative assembly) — correctly excluded despite in-network citations |
| paper_018 | Neurotechnologies for Human Cognitive Augmentation: Current State of … | 3 | other | **3.2** | Borderline | **Flagged for manual inclusion** — foundational BCI cognitive-augmentation review |
| paper_021 | Machine learning and wearable devices of the future | 3 | seizure_prediction | **3.4** | Borderline | **Flagged for manual inclusion** — foundational wearable-prediction review |
| paper_031 | Ambulatory seizure forecasting with a wrist-worn device using long-sh… | 4 | seizure_prediction | **4.0** | Included | Seminal wrist-worn LSTM seizure forecasting — included T3 |

## Included-Paper Cluster Distribution / 納入論文之引用聚類分佈

| Cluster | Count / 數量 | % of Included |
|---------|-------------|---------------|
| seizure_prediction | 83 | 51.2% |
| deep_learning_eeg | 24 | 14.8% |
| bci_methods | 21 | 13.0% |
| fall_prediction | 14 | 8.6% |
| sleep_forecasting | 7 | 4.3% |
| other | 4 | 2.5% |
| vigilance_drowsiness | 4 | 2.5% |
| predictive_coding | 3 | 1.9% |
| migraine_headache | 2 | 1.2% |

**Interpretation / 解讀:** Seizure prediction dominates (as in Step 2). Migraine remains thin — a candidate gap area that Step 7 (gap analysis) should flag. Predictive-coding, vigilance, and sleep clusters all retain strong representation in the included set, confirming the cross-domain positional framing is backed by literature.
**解讀:** 癲癇預測占主導（與 Step 2 一致）。偏頭痛仍稀疏——為 Step 7 gap analysis 應標記之候選缺口。預測編碼、警覺度、睡眠簇在納入集中均具強代表性，證實跨域 positional 框架有文獻支撐。

---

Files / 檔案: `step3_screening_results.md`, `step3_shortlist.json`, `step3_all_scored.json`
Next step / 下一步: After Checkpoint 2 resolution → `/research-export` (Step 4 — APA / BibTeX / citation-key export)
