---
citation_key: "WuEtAl2025"
paper_id: "paper_111"
title: "A Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction"
authors: "Yitong Wu; Eileen Lee Ming Su; Mingyu Wu; Chia Yee Ooi; William Holderbaum"
year: 2025
doi: "10.1109/access.2025.3606966"
source: "publisher-pdf (doi: 10.1109/access.2025.3606966)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# A Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction

**Citation:** `WuEtAl2025` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/access.2025.3606966](https://doi.org/10.1109/access.2025.3606966)
**Source PDF:** `full_pdf/YITONG2025.pdf`

## Abstract

Epileptic seizures impair patients’ health and quality of life, and electroencephalography (EEG)-based prediction enables timely intervention. Early work on epileptic seizure prediction employed linear models, whereas recent studies employ more advanced machine learning and deep learning models. We review 149 studies (2018—May 2025), summarizing trends and gaps across the full pipeline in EEG-based epileptic seizure prediction. We find that four persistent challenges related to this domain remain. First, severe dataset imbalance, with overreliance on Children’s Hospital Boston–Massachusetts Institute of Technology EEG dataset (CHB-MIT), minimal use of intracranial electroencephalography (iEEG) datasets, and infrequent integration of public and private datasets. Second, preprocessing practices remain rigid, often involving segmentation into windows of 10 s or less, fixed preictal horizons of 30 to 60 min, basic filtering and undersampling procedures. Third, limited model diversity, as most studies use convolutional neural networks (CNNs), with scant exploration of Transformers or graph neural networks (GNNs), dimensionality reduction is predominantly implicit and few linear baselines. Fourth, validation and deployment are fragmented, with fixed warning horizons, single evaluation protocols, missing clinical metrics, static thresholds or k-of-n voting, minimal interpretability, and few real-world implementations. Future work should assemble heterogeneous EEG datasets, adopt adaptive multiscale preprocessing, and build unified benchmarks that pit CNN, Transformer, GNN, and related models against well-tuned linear baselines— advancing flexible non-convolutional designs beyond the time-frequency paradigm, mandating ablations that contrast implicit with explicit, task-aware dimensionality reduction, and pairing these evaluations with clinically aligned validation, dynamic risk-aware thresholds, embedded interpretability, and prospective testing on energy-efficient edge ha

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
IEEE ENGINEERING IN MEDICINE AND BIOLOGY SOCIETY SECTION


Received 8 August 2025, accepted 28 August 2025, date of publication 8 September 2025, date of current version 17 September 2025.
Digital Object Identifier 10.1109/ACCESS.2025.3606966


A Review of Machine Learning and Deep Learning
Trends in EEG-Based Epileptic Seizure Prediction
YITONG WU 1,2,3 , EILEEN LEE MING SU 4 , MINGYU WU1,4 ,
CHIA YEE OOI 3 , (Senior Member, IEEE), AND WILLIAM HOLDERBAUM                                                               5
1 Thanh Dong University, H    i D ng 171967, Vietnam
2 Jiaxing Key Laboratory of Industrial Intelligence and Digital Twin, Jiaxing Vocational and Technical College, Jiaxing, Zhejiang 314036, China
3 Malaysia-Japan International Institute of Technology, Universiti Teknologi Malaysia, Kuala Lumpur 54100, Malaysia
4 Faculty of Electrical Engineering, Universiti Teknologi Malaysia, Johor Bahru 81310, Malaysia
5 Manchester Metropolitan University, M15 6BX Manchester, U.K.

Corresponding author: Eileen Lee Ming Su (eileensu@utm.my)
This work was supported in part by Thanh Dong University, Vietnam; and in part by Jiaxing Science and Technology Bureau Research
Project under Jiaxing Science Plan Project under Grant 2024AY10032.


  ABSTRACT Epileptic seizures impair patients’ health and quality of life, and electroencephalography
  (EEG)-based prediction enables timely intervention. Early work on epileptic seizure prediction employed
  linear models, whereas recent studies employ more advanced machine learning and deep learning models.
  We review 149 studies (2018—May 2025), summarizing trends and gaps across the full pipeline in
  EEG-based epileptic seizure prediction. We find that four persistent challenges related to this domain remain.
  First, severe dataset imbalance, with overreliance on Children’s Hospital Boston–Massachusetts Institute of
  Technology EEG dataset (CHB-MIT), minimal use of intracranial electroencephalography (iEEG) datasets,
  and infrequent integration of public and private datasets. Second, preprocessing practices remain rigid, often
  involving segmentation into windows of 10 s or less, fixed preictal horizons of 30 to 60 min, basic filtering
  and undersampling procedures. Third, limited model diversity, as most studies use convolutional neural
  networks (CNNs), with scant exploration of Transformers or graph neural networks (GNNs), dimensionality
  reduction is predominantly implicit and few linear baselines. Fourth, validation and deployment are
  fragmented, with fixed warning horizons, single evaluation protocols, missing clinical metrics, static
  thresholds or k-of-n voting, minimal interpretability, and few real-world implementations. Future work
  should assemble heterogeneous EEG datasets, adopt adaptive multiscale preprocessing, and build unified
  benchmarks that pit CNN, Transformer, GNN, and related models against well-tuned linear baselines—
  advancing flexible non-convolutional designs beyond the time-frequency paradigm, mandating ablations
  that contrast implicit with explicit, task-aware dimensionality reduction, and pairing these evaluations with
  clinically aligned validation, dynamic risk-aware thresholds, embedded interpretability, and prospective
  testing on energy-efficient edge hardware in ward and home settings.


  INDEX TERMS Electroencephalography, epileptic seizure prediction, machine learning, deep learning.


I. INTRODUCTION                                                                                   one-third of patients with epilepsy still experience drug-
Epilepsy is a major neurological disorder affecting approx-                                       resistant seizures [3]. In addition to the direct health impacts,
imately 50 million people worldwide. It constitutes a                                             epilepsy imposes substantial socioeconomic burdens, includ-
significant cause of morbidity, disability, and mortality,                                        ing healthcare costs, employment challenges, and diminished
particularly in low- and middle-income countries where                                            quality of life for patients and their families.
access to specialized care is limited [1], [2]. Despite                                              Epileptic seizures are abrupt manifestations of abnormal,
advances in pharmacological and surgical treatments, nearly                                       excessive neuronal activity in the brain, which can cause
                                                                                                  serious injuries, accidents, and sudden unexpected death
   The associate editor coordinating the review of this manuscript and                            in epilepsy [4]. Beyond these immediate risks, recurrent
approving it for publication was Eunkyoung Park.                                                  seizures also impose substantial psychological burdens that
                                                  2025 The Authors. This work is licensed under a Creative Commons Attribution 4.0 License.
159812                                                   For more information, see https://creativecommons.org/licenses/by/4.0/                      VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


FIGURE 1. Flowchart of the general process for EEG-based seizure prediction.


severely impair quality of life. In epilepsy management,                          brain’s electrical activity, capturing subtle preictal changes
monitoring systems fall into two categories: seizure detection                    that precede seizure onset, and plays a central role in both
and seizure prediction. Detection systems identify ictal                          seizure prediction research and clinical applications.
events at onset or within seconds. They are evaluated by                             EEG offers several unique advantages for seizure pre-
sensitivity, specificity, false detection rate per hour (FDR/h),                  diction, including millisecond-scale temporal resolution
and detection latency to enable real-time interventions such                      that is critical for detecting the rapid electrophysiological
as closed-loop neurostimulation or caregiver alerts [5].                          transitions preceding seizures [9]. Unlike neuroimaging
In contrast, prediction systems aim to forecast seizures                          modalities such as magnetic resonance imaging (MRI) or
during the preictal period with horizons of 60, 90, or                            computed tomography (CT), EEG enables continuous, real-
120 min; their performance is measured by sensitivity, false                      time monitoring of brain activity, making it particularly
prediction rate per hour (FPR/h), and mean warning time to                        well suited for dynamic seizure forecasting [10]. In clinical
provide sufficient lead time for preventive action. Because                       practice, EEG not only supports the diagnosis of epilepsy
uncontrolled seizures have severe consequences, effective                         but also contributes to seizure classification, epilepsy subtype
prediction has become a critical goal in epilepsy care [6].                       identification, treatment monitoring, and presurgical evalua-
By issuing warnings, prediction systems allow patients to                         tion [10], [11]. Nevertheless, conventional EEG interpretation
reach safe environments, initiate rescue therapies, or alert                      remains manual and subjective, with reported sensitivity
caregivers, thereby reducing morbidity and mortality and                          after a first clinical seizure ranging between 29% and
improving overall quality of life.                                                55% [11]. The complexity, variability, and volume of EEG
   The core idea of seizure prediction is that there exists                       data necessitate automated analysis techniques to improve
a discernible transition period (the preictal state) whose                        diagnostic accuracy, scalability, and reliability, particularly in
timely detection allows for warning of an impending event.                        long-term monitoring settings.
Mormann et al. [7] systematically argued that, to surpass                            Early EEG-based studies often relied on simple linear
random chance truly, models must be patient-specific, have                        classifiers—such as linear discriminant analysis (LDA),
clearly defined prediction horizons, and be validated with rig-                   least-squares linear discriminant (LSLD), and logistic regres-
orous statistical tests. Among various physiological modali-                      sion (LR)—which provided crucial insights into the temporal
ties explored for seizure forecasting, electroencephalography                     electrophysiological signatures preceding seizures [12], [13].
(EEG) has emerged as the primary and most clinically                              Nonetheless, because these models assume a single linear
validated tool [8]. EEG provides direct insights into the                         decision boundary, they struggle to capture the nonlinear,

VOLUME 13, 2025                                                                                                                              159813

                                          Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


high-dimensional dynamics of multichannel EEG signals,                  TABLE 1. Inclusion and exclusion criteria for study selection.
limiting their ability to model the subtle spatiotemporal
interactions that foreshadow imminent seizures. To transcend
these limitations, researchers have progressively adopted arti-
ficial intelligence (AI) approaches, beginning with machine
learning pipelines and more recently embracing deep learning
architectures that can autonomously learn the intricate
nonlinear spatiotemporal patterns embedded in EEG record-
ings [14], [15]. Alotaiby et al. [5] applied subject-specific
typical spatial pattern filters followed by machine learning
to scalp EEG recordings, achieving an average sensitivity of
0.89, 0.39 false alarms per hour, and a mean warning time
of approximately 69 min. Bandarabadi et al. [16] showed
that the optimal preictal window varies across seizures
and introduced an amplitude-distribution-histogram over-
lap criterion to select this window automatically, thereby
improving class separability and providing an interpretable             of algorithmic methodologies or frameworks for clinical
predictability metric. Recent AI pipelines have demonstrated            translation.
higher sensitivity, lower false-positive rates, and greater                Although these prior reviews offer valuable insights, they
reproducibility than conventional expert visual inspection or           remain largely narrow in scope, each addressing only a
simple heuristic postprocessing rules [17]. Reviews suggest             specific subset of topics within the broader domain of
that AI-assisted seizure prediction models can achieve                  epileptic seizure prediction. None delivers an integrated,
experimental accuracies exceeding 80%; however, real-                   systematic, and comprehensive treatment that simultaneously
world deployment remains challenging because of dataset                 encompasses methodological approaches, dataset utilization,
heterogeneity and limited model interpretability [15], [17].            evaluation frameworks, and clinical applicability. Conse-
   As shown in Fig. 1, the general workflow of EEG-based                quently, a critical gap persists: there is currently no review
seizure prediction begins with preprocessing of the raw                 that holistically maps the whole landscape of machine
recordings, including signal segmentation, preictal window              learning and deep learning applications to EEG-based seizure
definition, noise removal, and balancing preictal and inter-            prediction. To address this unmet need, we conducted a
ictal samples. Next, feature extraction produces informative            comprehensive review with the following objectives:
descriptors from the time, frequency, and time–frequency                  (i) to identify and synthesize current trends and advance-
domains, among others. These features are input to a predic-                  ments in seizure prediction research using EEG data;
tion model, whose outputs can be refined by postprocessing               (ii) to highlight methodological limitations present in cur-
routines to enhance performance. Finally, the complete                        rent seizure prediction studies;
system undergoes experimental validation and is prepared for            (iii) to propose future research directions and strategies to
deployment.                                                                   bridge the gap between experimental development and
   This paper aims to provide a comprehensive overview of                     real-world clinical implementation.
the development and evolving trends in machine learning                    The structure of this review is as follows: Section II
and deep learning approaches for EEG-based epileptic                    outlines the review methodology, including the search
seizure prediction. Several prior systematic reviews have               strategy, selection criteria, and data extraction process.
addressed the application of machine learning and deep                  Section III summarizes key findings by comparatively
learning in epilepsy research, but each exhibits important              analyzing datasets, EEG preprocessing, model architectures,
gaps. Shafiezadeh et al. [18] focused solely on cross-patient           validation setups, postprocessing strategies, and clinical
seizure prediction, neglecting patient-specific modeling and            interpretability and deployment. Section IV discusses key
complete coverage of the end-to-end pipeline. Ong et al. [19]           trends, strengths, limitations, and challenges in the field.
reviewed medical devices for epilepsy management, empha-                Section V concludes the review and proposes directions for
sizing hardware development while giving limited atten-                 future research.
tion to algorithmic strategies. Saeidi et al. [20] offered a
broad survey of EEG neural decoding, in which seizure                    II. MATERIALS AND METHODS
prediction played only a peripheral role. More recently,                To promote transparent reporting and facilitate retrieval
Tautan et al. [21] examined unsupervised learning methods               of studies relevant to its objectives, this review followed
but did not provide an extensive treatment of mainstream                established best-practice guidelines, and data were collected
supervised and deep learning approaches. Wong et al. [22]               as follows. Two primary search queries—‘‘EEG machine
evaluated publicly available EEG datasets for seizure detec-            learning epilepsy prediction’’ and ‘‘EEG deep learning
tion and prediction, yielding valuable insights into dataset            epilepsy prediction’’—were employed to capture the core
characteristics but stopping short of a comprehensive analysis          themes. Literature searches were conducted in the Web of

159814                                                                                                                               VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


                                 FIGURE 2. Flowchart of literature search, screening, and selection process for
                                 EEG-based epileptic seizure prediction studies.


Science and PubMed databases, and study selection was                             illustrated in Fig. 2. An initial screening was conducted
governed by predefined inclusion and exclusion criteria                           using the built-in database filters to restrict the document
(Table 1).                                                                        type to ‘‘Article’’. Duplicate entries were then identified and
   Based on the inclusion and exclusion criteria summarized                       removed with Zotero, leaving 213 unique records for further
in Table 1, a comprehensive search was conducted to identify                      evaluation.
the latest research published since 2018. The electronic                              Only records that passed the initial title and abstract
search was executed on 1 May 2025. Although studies                               screening were retrieved in full text and subjected to further
published prior to 2018 were relatively sparse, recent years                      assessment against the predefined inclusion criteria. Full-text
have seen a pronounced surge in research activity, reflecting                     evaluation involved a comprehensive review of each record’s
substantial methodological and technological evolution. The                       title, abstract, and entire content. At this stage, the following
initial retrieval yielded 256 records from the Web of                             records were excluded:
Science and 102 from PubMed, for a combined total of                                  • 31 records that focused primarily on epileptic seizure
357 records.                                                                             detection rather than prediction,
   To provide an overview of the literature screening pro-                            • Seven records whose full texts revealed that they were
cedure, a summary of the search and selection process is                                 review-type studies,

VOLUME 13, 2025                                                                                                                             159815

                                                Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


FIGURE 3. Number of included studies by year (from 2018 till 1 May 2025).


   • Seven records addressing non-standard topics (e.g., trau-                32 studies in 2024, the field remained highly active. For
     matic brain injury prognosis, postoperative outcomes,                    2025, only nine studies were included at the time of this
     neonatal hypoxic–ischemic encephalopathy, aura detec-                    review, as the year was still in progress. This overall trend
     tion, simulations, cognitive monitoring),                                underscores the increasing academic and clinical interest
   • Seven records that used non-EEG signals (e.g., electro-                  in applying machine learning/deep learning methods to
     cardiography, questionnaires, functional near-infrared                   EEG-based seizure prediction in recent years.
     spectroscopy),                                                              Among the 149 studies on seizure prediction, deep learning
   • Six records that focused primarily on hardware                           techniques were employed in 107 studies, reaffirming their
     development,                                                             role as the dominant approach in the field. Traditional
   • Three records that involved non-human subjects,                          machine learning methods were utilized in 22 studies.
   • Three retracted articles.                                                In addition, researchers have begun to explore integrated
   After the application of all predefined inclusion and                      strategies: 11 studies proposed hybrid models that combine
exclusion criteria [23], a total of 149 studies were deemed                   deep learning and machine learning, while another nine
eligible and included for qualitative synthesis. These studies                studies conducted explicit comparisons between the two
form the basis of the analysis presented in this review.                      paradigms to benchmark their respective strengths and
                                                                              limitations.
III. RESULTS                                                                     This section provides a comprehensive analysis of the
From 2018 through 2025, research on EEG-based epileptic                       149 studies included in this review, structured around
seizure prediction using machine learning and deep learning                   the key methodological components identified across the
has shown a steady upward trend, with 2025 data covering                      literature. Section III-A outlines the datasets utilized for
publications up to May 1. As illustrated in Fig. 3, only six                  EEG-based seizure prediction. Section III-B reviews the
studies were published annually in both 2018 and 2019,                        EEG signal preprocessing techniques applied prior to model
reflecting the early stage of methodological exploration in                   development. Section III-C describes the model architectures
this domain. The number of studies increased to 12 in                         employed for seizure forecasting. Section III-D summarizes
2020 and 15 in 2021, indicating growing research momen-                       the experimental validation setups, including data partition-
tum. A sharp rise was observed in 2022 and 2023, with                         ing strategies and evaluation metrics. Section III-E discusses
32 and 37 studies published, respectively—marking the peak                    postprocessing decision mechanisms designed to refine
of research activity. Although there was a slight decline to                  predictive outputs. Section III-F addresses issues related to


159816                                                                                                                                     VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 2. Overview of datasets used in EEG-based seizure prediction studies.


clinical interpretability and deployment, focusing on how                            With respect to dataset accessibility, 100 of the 149 studies
models have been evaluated or implemented in real-world                           (67.1%) leveraged open-source datasets, thereby support-
settings. This structured analysis aims to highlight common                       ing reproducibility and enabling cross-study benchmarking.
practices, emerging trends, and methodological gaps within                        In contrast, 29 studies (19.5%) relied exclusively on
the field.                                                                        non-public clinical datasets, which were typically acquired in
                                                                                  specialized epilepsy monitoring units. An additional 20 stud-
A. DATASETS                                                                       ies (13.4%) combined both open and non-open datasets,
An essential foundation of EEG-based epileptic seizure                            reflecting a growing effort to improve generalizability by
prediction research is the datasets used for model develop-                       augmenting standardized benchmark data with real-world
ment and evaluation. In our review of 149 primary studies,                        clinical recordings. Table 2 presents an overview of the
we observed substantial heterogeneity in both the EEG                             datasets used in EEG-based seizure prediction studies;
recording modalities and the accessibility of the underlying                      individual papers may appear in multiple categories if they
datasets. Specifically, scalp electroencephalography (sEEG)                       incorporate more than one dataset.
was the most frequently used dataset type, appearing in                              As shown in Table 2, several public datasets have been
87 studies (58.4%), reflecting its popularity due to noninva-                     widely adopted in recent studies. The most frequently used is
sive nature and the presence of multiple publicly available                       Children’s Hospital Boston–Massachusetts Institute of Tech-
repositories. Intracranial electroencephalography (iEEG) was                      nology Scalp EEG Dataset (CHB-MIT), cited in 107 studies.
utilized in 29 studies, while 32 studies (21.5%) combined                         It contains sEEG recordings from 23 pediatric patients (aged
iEEG and sEEG to leverage their complementary spatial cov-                        1.5 to 19 years) acquired with 23 channels at 256 Hz.
erage and signal characteristics. Only a single study (0.7%)                      In total, 916 h of data were collected over 2 to 4 monitoring
employed ear-EEG [167], an emerging wearable modality                             days per subject (median 4 days), stored in 664 EDF
that offers portable monitoring but remains underexplored in                      files (about 29 one-hour segments per subject). Annotations
the seizure prediction literature.                                                by clinicians indicated 198 clinical seizures, averaging

VOLUME 13, 2025                                                                                                                            159817

                                           Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


8.6 seizures per subject. The second most used public datasets           minimal patient-specific data. These studies demonstrate
is American Epilepsy Society Seizure Prediction Challenge                that combining CHB-MIT with institution-specific clinical
Dataset (AES-Kaggle), cited in 24 studies. It provides long-             recordings across modalities enhances both predictive perfor-
term iEEG from 7 subjects—2 human patients and 5 epileptic               mance and practical applicability.
dogs—recorded on 15 to 24 channels. In total, 1333.7 h of                   Across the 149 studies reviewed, the dataset landscape is
data were acquired, sampled at 5 kHz for humans and 400 Hz               heavily skewed toward a small set of public sEEG dataset.
for canines. Recordings are provided as 1-h files that are               67.1% of papers rely exclusively on open repositories, and
further subdivided into 6 non-overlapping 10-min clips,                  the pediatric CHB-MIT dataset alone constitutes 71.8% of
yielding 4067 segments with 111 annotated seizures (one                  all dataset citations. By contrast, long-duration, high-density
preictal clip per seizure and 3956 interictal clips). Siena Scalp        intracranial collections such as EPILEPSIAE and Freiburg
EEG Dataset (Siena EEG), referenced in 10 studies, contains              appear in fewer than one in ten studies, and only 13.4% of
adult scalp recordings from 14 patients (ages 20 to 71)                  investigations fuse public benchmarks with center-specific
recorded at 512 Hz with 19 to 21 international 10-20 leads.              clinical data. This pronounced imbalance implies that many
Across the cohort, it includes 128 h of video-EEG (mean                  headline performance numbers are optimized for low-
9.1 h per subject), collected over 1 to 5 sessions per patient,          channel, child-specific signal characteristics and may not
with 47 clinically annotated seizures in total. SWEC-ETHZ                generalize to adult populations, high-frequency iEEG, or real-
Intracranial EEG Dataset (SWEC-ETHZ), used in 5 studies,                 world ambulatory recordings. Reported ‘‘state-of-the-art’’
comprises continuous long-term recordings from 18 drug-                  results should therefore be interpreted as best-case outcomes
resistant epilepsy patients, sampled at 512 to 1024 Hz via               within a narrow data regime, not as evidence of broad clinical
24 to 128 implanted electrodes. It provides 2664 h of iEEG               robustness.
containing 116 annotated seizures—approximately 148 h per
subject—with data stored as hourly files.                                 B. EEG SIGNAL PREPROCESSING METHODS
   In contrast, non-public datasets remain indispensable                 Preprocessing is a foundational step in EEG-based seizure
for studies requiring high-quality, long-duration, or high-              prediction because it shapes feature fidelity and therefore
channel-count iEEG recordings. The most frequently used                  downstream model performance. This section focuses on
non-public datasets is European Epilepsy Dataset (EPILEP-                four core components of the preprocessing pipeline: segment
SIAE) (nine studies), which aggregates long-term surface                 division and preictal definition, denoising methods, and data
and iEEG from 275 patients, each monitored for at least                  balancing strategies.
96 h, yielding over 30000 h of data and approximately
1800 clinically annotated seizures; recordings include up to             1) SEGMENT DIVISION AND PREICTAL DEFINITION
122 channels sampled at rates of up to 2500 Hz. Freiburg EEG             Of the 149 studies, epoch length is explicitly reported
Dataset (Freiburg) (eight studies) comprises depth electrode             in 131 studies (87.9%), with a clear preference for short
recordings from 21 drug-resistant epilepsy patients using                segments. The most frequently adopted lengths are 5 to 10 s
64 or 128 channels. In total, 509 h of data were collected               (50 studies, 33.6%), followed by durations shorter than 5 s (36
over 3 to 10 days per subject (median 5 days), stored as                 studies, 24.2%) and those between 20 and 30 s (35 studies,
509 one-hour segments, and annotated for 87 clinical seizures            23.5%). Longer segments exceeding 30 s are relatively rare,
(mean 4.1 per patient, range 1 to 11). Epilepsy Ecosystem                appearing in only 8 studies (5.4%). In addition, six studies
Platform (EpilepsyEcosystem) (five studies) provides iEEG                (4.0%) employ a multi-scale design, systematically evaluat-
from 18 drug-resistant epilepsy patients recorded on 24 to               ing multiple segment lengths (e.g., from 5 to 60 s) within
128 implanted electrodes at 512 to 1024 Hz; the datasets                 the same work to characterize the trade-off between temporal
comprises 2656 h of data (median 148 h per subject), stored              resolution and prediction accuracy. These exploratory efforts
as one-hour segments, with 116 clinically annotated seizures             underscore the importance of segment length selection in
(mean 6.4 per patient, range 1 to 24).                                   balancing model precision and real-time applicability and
   Lastly, some studies adopt an integrative strategy that               indicate that future research should further refine optimal
leverages both public and non-public datasets to enhance                 segment configurations.
model effectiveness and clinical relevance. For example,                    Regarding the preictal prediction horizon, 125 studies
Chen et al. [109] validated their statistical method on both             (83.9%) explicitly specify a single prediction window. The
CHB-MIT and a non-public sEEG dataset from Peking                        most common choice is the 30 to 60 min window (91
University First Hospital (FH-PKU), achieving high accuracy              studies, 61.1%), with a 30-min horizon alone used in
with interpretability. Guo et al. [104] pretrained their model           61 studies (40.9%), reflecting a prevailing compromise
on CHB-MIT and fine-tuned it using non-public intracranial               between clinical usefulness and predictive reliability. Shorter
EEG recordings from Xuanwu Hospital, Capital Medical                     horizons (≤10 min) are less frequent (17 studies, 11.4%),
University (CMU-XWH), which improved generalization.                     as are intermediate windows of 15 to 20 min (six studies,
Shafiezadeh et al. [105] trained on CHB-MIT and calibrated               4.0%); horizons longer than 60 min appear rarely (four stud-
their model with non-public sEEG data collected at E. Medea              ies, 2.7%). Nine studies (6.0%) adopt multi-scale designs,
Hospital in Conegliano, Italy, boosting performance with                 systematically evaluating performance across a range of

159818                                                                                                                                VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 3. Overview of denoising methods applied during EEG preprocessing (cutoff frequencies in Hz).


TABLE 4. Overview of EEG seizure prediction data balancing strategy.


windows (5 to 120 min) to characterize model sensitivity and                      γ -band activity. Another eight studies use cutoffs in the 61 to
robustness to temporal specification. These results indicate                      100 Hz range, and 13 studies employ cutoffs above 100 Hz,
that preictal horizon selection should be adapted to the                          indicating that some deep learning approaches attempt to
clinical context, balancing early warning lead time against                       exploit ultra–high–frequency features. Only three studies
prediction accuracy.                                                              apply a low-pass cutoff of 30 Hz or lower. High-pass filtering
                                                                                  exhibits a consistent practice: 27 studies set the cutoff at
2) DENOISING METHODS                                                              or below 0.5 Hz to remove direct current (DC) drift and
Of the 149 studies, 60 (40.3%) skip explicit denoising. Two                       slow baseline fluctuations, while an additional seven studies
studies—Halawa et al. [42] and Wu et al. [135]—employed                           employ cutoffs in the 0.6 to 1 Hz range to provide further
advanced signal-based denoising techniques, namely discrete                       attenuation of residual very low-frequency noise.
wavelet transform (DWT) soft-thresholding and multidi-                               Notch filtering is predominantly used to suppress power-
mensional singular value mode decomposition (SVMD),                               line interference, with 50 Hz and 60 Hz notches apply
respectively. The remaining 87 studies (58.4%) rely on                            in 22 and 26 studies, respectively, reflecting widespread
classical filtering approaches, applying one or more of low-                      agreement on removing mains contamination. A further nine
pass, high-pass, or notch filters during preprocessing prior to                   and 17 studies employ notches at 100 Hz and 120 Hz,
any feature extraction. Table 3 summarizes these approaches,                      respectively, to target higher-order harmonics and thereby
because some studies employ multiple filter types, and                            attenuate residual line-related artifacts. 10 studies apply
individual papers may be counted in more than one category.                       broader filter types (e.g., band-pass or band-stop) without
   In epileptic seizure prediction research, filter cutoff fre-                   reporting specific cutoff frequencies, and seven others
quencies reflect the trade-off between preserving informative                     rely on alternative denoising strategies, including extended
EEG components and suppressing noise. As summarized                               training segments [48], independent component analysis
in Table 3, the most common low-pass cutoff lies between                          (ICA) [57], Kalman filtering [59], wide-bandwidth filtering
31 and 60 Hz (14 studies), balancing attenuation of                               as in Whitehead’s approach [62], Fourier-domain smooth-
high-frequency artifacts such as electromyography (EMG)                           ing [133], manual artifact-channel rejection [136], and
contamination with retention of seizure-related β- and                            principal component analysis (PCA) [152].

VOLUME 13, 2025                                                                                                                            159819

                                          Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


3) DATA BALANCING STRATEGIES                                            extraction methods and the core algorithms employed in these
EEG-based seizure prediction routinely confronts severe                 frameworks.
class imbalance, since interictal segments vastly outnumber
preictal ones. To mitigate this, a variety of data-balancing             a: FEATURE EXTRACTION
strategies have been employed.
                                                                        Table 5 summarizes the feature extraction methods used
   As shown in Table 4, interictal undersampling is the
                                                                        in the 22 studies adopting conventional machine learning
most prevalent data-balancing strategy (57 studies), reducing           frameworks for seizure prediction. All of these studies rely on
the majority class size to match preictal data and thereby              manually extracted features, reflecting the dominant practice
mitigating classifier bias. 19 studies expand the minority
                                                                        in traditional machine learning approaches.
class through overlapping preictal segments generated by
                                                                           As summarized in Table 5, time- and frequency-domain
sliding windows, while 14 combine undersampling and
                                                                        features remain foundational in machine learning-based
oversampling to both balance class proportions and preserve
                                                                        seizure prediction, appearing in 14 and 15 studies respec-
temporal resolution.                                                    tively, and reflecting a reliance on basic statistical descrip-
   Some investigations explore synthetic augmentation: four             tors and spectral analyses. Time-domain features—–mean,
studies apply synthetic minority over-sampling technique
                                                                        variance, peak-to-peak, zero-crossing rate, skewness, and
(SMOTE) and another four perform straightforward preictal
                                                                        kurtosis—directly characterize EEG amplitude dynamics.
duplication. A smaller subset develops bespoke reconstruc-
                                                                        Frequency-domain methods typically apply fast Fourier
tion schemes, partitioning existing preictal periods into short
                                                                        transform (FFT) to convert signals [68], estimate power
subsegments (e.g., 1 s) and randomly reassembling them                  spectral density (PSD) (using classical approaches and
to approximate incomplete or sparse preictal data. More                 Welch’s method) to quantify δ, θ, α, β, and γ band
recent efforts (four studies) employ generative methods—
                                                                        energies [81], and employ DWT for multi-scale decompo-
such as generative adversarial networks (GANs) or temporal
                                                                        sition [140]. Joint time–frequency representations—such as
neural data augmentation (TNDA)—–to synthesize diverse
                                                                        the wavelet transform (WT) [68], [120], [144], stationary
and physiologically plausible preictal examples.                        wavelet transform (SWT) [151], and synchrosqueezing
   These methodological pipelines are implemented in                    transform (SET) [102])—capture combined temporal and
diverse software environments. Among the 149 studies,                   spectral information but, due to higher computational cost,
74 (49.7%) use Python, 23 (15.4%) use MATLAB, five
                                                                        appear in only nine studies. Nonlinear complexity metrics
employ hybrid Python–MATLAB workflows, and two rely
                                                                        (sample entropy, approximate entropy, Lempel–Ziv complex-
on R. Fewer than 10% of the studies included direct links to
                                                                        ity) are employed in just 4 studies, suggesting that their
their code repositories in the main text.                               potential for detecting preictal chaotic dynamics remains
   In most studies, EEG recordings are divided into short               underexplored. Connectivity features— phase-locking value
epochs of 10 s or less, and a preictal prediction horizon
                                                                        (PLV) [163], phase lag index (PLI), weighted phase lag
of 30 to 60 min is the most common choice. A large
                                                                        index (WPLI) [138], and graph-theoretical measures [109]—
fraction of the study relies solely on basic notch or band-pass
                                                                        are emerging in about five studies: phase-synchrony indices
filtering for signal denoising. Class imbalance is chiefly
                                                                        are first computed between channel pairs, then converted
mitigated via interictal undersampling; only a minority of              into brain networks from which node degree, clustering
studies incorporate oversampling or synthetic data augmen-              coefficient, and global efficiency are extracted. Finally,
tation. While these convenient defaults simplify training and
                                                                        second-level cross-domain fusion features generated via
reduce methodological complexity, they frequently neglect
                                                                        genetic algorithms represent an advanced trend in automated
longer-term prodromal dynamics, constrain the available
                                                                        feature optimization, combining multiple primary feature sets
contextual background, and can elevate false-alarm rates in
                                                                        to enhance predictive performance.
noisy, continuous recordings.                                              Notably, Chen et al. [109] introduced an additional pro-
                                                                        cessing stage in which Graphical Lasso was applied to
C. MODEL STRUCTURE                                                      estimate dynamic functional connectivity, producing a sparse
This section examines the structural design of seizure                  brain network from which topological and connectivity
prediction models in the reviewed studies, organized into four          features were subsequently derived.
main categories: traditional machine learning models, deep
learning models, studies that compare the two approaches,                b: CORE ALGORITHM
and hybrid models that integrate both. These categories
                                                                        The second part of this section examines the core algorithms
reflect the dominant modeling strategies adopted in current
                                                                        used in conventional machine learning pipelines. Among the
research.
                                                                        22 included studies, support vector machine (SVM) are the
                                                                        most frequently used, followed by LR, k-nearest neighbors
1) CONVENTIONAL MACHINE LEARNING FRAMEWORKS                             (k-NN), and extreme gradient boosting (XGBoost). As shown
Among the reviewed studies, 22 adopt conventional machine               in Table 6, the usage frequency and representative references
learning approaches. This subsection outlines the feature               for each algorithm are clearly presented.

159820                                                                                                                               VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 5. Overview of feature extraction methods in machine learning-based seizure prediction.


TABLE 6. Overview of core algorithms in machine learning–based seizure            on-device deployment [138]. Finally, a discrete hidden
prediction.
                                                                                  Markov model coupled with Wilks’ Lambda feature selection
                                                                                  models the EEG as a sequence of latent states, capturing
                                                                                  temporal dependencies that purely static classifiers can
                                                                                  not [151].
                                                                                     Notably, although using linear models as baselines is
                                                                                  essential for meaningful comparison, only a handful of
                                                                                  studies have quantified how much advanced models improve
                                                                                  upon these linear benchmarks. For example, in Qureshi et al.
   Among the reviewed studies, SVM emerges as the                                 [45] the RBF kernel SVM reached an accuracy of 94.94%
most frequently applied classifier, appearing in 8 studies;                       and a sensitivity of 97.43% representing increases of
it is valued for its capacity to maximize class separa-                           3.18 and 5.20 percentage points over the linear kernel
tion via kernel-induced mappings and its robustness in                            SVM respectively; In Shafiezadeh et al. [106] the XGBoost
high-dimensional, small-sample regimes. LR follows as a                           classifier achieved a mean accuracy of 78.75% under
lightweight, interpretable linear model used in four studies,                     random cross validation improving performance by nearly
both as a standalone baseline and as a component within                           28 percentage points over the baseline logistic regression
ensemble constructions. k-NN appears in two studies; despite                      model; In Ramachandran et al. [132] the linear kernel SVM
its simplicity and absence of an explicit training phase,                         outperformed both logistic regression and LDA in classifica-
it remains effective in lower-dimensional feature spaces or                       tion accuracy on the same feature set.
modest dataset sizes through straightforward distance-based
voting. Finally, XGBoost is adopted in two studies to capture                     2) COMPARATIVE EVALUATIONS OF MACHINE LEARNING
complex nonlinear relationships, with built-in regularization                     AND DEEP LEARNING MODELS
that mitigates overfitting—particularly potent when EEG                           Among the reviewed studies, nine conduct comparative
features are preextracted into a compact representation.                          evaluations between deep learning and conventional machine
Beyond these mainstream models, six studies each introduce                        learning approaches. This subsection summarizes the feature
or adapt a distinct classification strategy. One employs                          extraction techniques and core algorithms used in these
a shallow multi-layer perceptron (MLP) to illustrate how                          studies.
slowly varying noise patterns in EEG can be misinterpreted
as seizure activity, underscoring the need for rigorous data                      a: FEATURE EXTRACTION
validation [130]. Another uses random forest (RF) on fused                        Table 7 summarizes the feature extraction methods used
frequency-domain and phase-coupling features, achieving                           in the nine studies that conduct comparisons between deep
high accuracy through ensemble voting over multiple deci-                         learning and conventional machine learning approaches.
sion trees [119]. A third study implements boosted trees                          In all of these studies, the machine learning components
(BT) in a lightweight configuration tailored to wearable                          rely entirely on manually extracted features. For the deep
devices, balancing prediction performance with real-time                          learning components, five studies employ fully automated
constraints [167]. Kapoor et al. [120] designed a hybrid                          feature extraction through the model itself, while the other
ensemble—tuned via a novel seek-optimization routine—that                         four studies incorporate manually extracted features as input,
combines AdaBoost, RF, and single decision trees to further                       followed by additional feature learning within the model [30],
elevate accuracy on standard benchmarks. A low-complexity,                        [76], [131], [168].
threshold-based classifier leverages phase-locking indices                           Across the nine comparative studies, spectral features
for real-time feature selection, making it well suited for                        proved to be the workhorse for both machine learning

VOLUME 13, 2025                                                                                                                          159821

                                                Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 7. Overview of feature extraction methods in machine learning vs. deep learning seizure prediction studies.


and deep learning pipelines: eight of the studies rely                        thereby probing the validity of the fixed 65- to 5-min preictal
on hand-crafted frequency-domain descriptors—discrete                         assumption.
Fourier transform (DFT) [131], empirical mode decom-                             In the remaining five studies conducted under identical
position (EMD) [74], power spectral analysis [136]—to                         experimental conditions, only Sun et al. and Abdellatef et al.
characterize preictal versus interictal EEG. Time-domain                      explicitly included simple linear classifiers as baseline
statistics—mean, variance, skewness, kurtosis, and the like—                  models: Sun et al. [131] compared LDA and LR with CNN
are nearly as ubiquitous, appearing in seven studies as                       and recurrent neural network (RNN), finding that the CNN
the foundation for conventional classifiers and sometimes                     achieved an overall accuracy at least five percentage points
as inputs to hybrid deep learning models. In contrast,                        higher than the linear models and Abdellatef et al. [74]
joint time–frequency features are relatively rare, adopted                    included LR as a linear baseline, alongside HMS-feature–
by only one study, suggesting a trade-off between analytic                    based SVM and k-NN, when comparing these machine
richness and complexity. A smaller subset of two studies                      learning methods with their residual CNN and other deep
employ nonlinear complexity measures (e.g., entropy and                       learning models, and found that HMS-SVM nonetheless
fractal dimension) to characterize dynamical irregularities                   outperformed the CNN. By contrast, Massoud et al. [153]
beyond what linear spectral methods capture, while two other                  evaluated SVM and random under-sampling boost alongside
investigations explore network-level topology by deriving                     temporal convolutional neural network (TCNN), CNN, and
functional connectivity and graph-theoretic metrics.                          long short-term memory (LSTM), reporting that SVM
   In addition, only one study [131] transform EEG segments                   attained the highest accuracy in the cross-patient general
into short-time Fourier transform (STFT) spectrograms                         model, whereas TCNN led in average accuracy follow-
before feeding them into a convolutional neural network                       ing patient-specific fine-tuning; Kannan et al. [30] compared
(CNN), whereas the other five studies supply their inputs                     three conventional classifiers—repeated incremental pruning
directly to deep learning models without constructing any                     to produce error reduction (RIPPER), decision tree, and
time–frequency image representations.                                         SVM—against a CNN and several LSTM variants; the
                                                                              deepest LSTM variant achieved the highest overall accuracy;
                                                                              Sidaoui and Sadouni [168] compared SVM with two CNN
b: CORE ALGORITHM                                                             architectures, and the CNN exhibited slightly superior
Among the nine studies that set machine-learning methods                      performance and faster inference.
head-to-head with deep learning models, four carry out the                       Of the studies conducting head-to-head comparisons
comparison under clearly defined, often restrictive experi-                   between machine learning and deep learning, only three
mental scenarios. Only Gao et al. [28] employed a traditional                 include linear models as baselines, emphasizing that bench-
linear SVM as their baseline, applying a genetic algorithm-                   marking against simple linear reference models remains
based sample-weighting framework on the CHB-MIT dataset                       uncommon.
and demonstrating that the Transformer achieved the highest
sensitivity and accuracy. By contrast, Shafiezadeh et al. [105]               3) HYBRID ARCHITECTURES INTEGRATING MACHINE
compared CNN with XGBoost classifier using both ran-                          LEARNING AND DEEP LEARNING
domized cross-validation and leave-one-patient-out schemes,                   Among the reviewed studies, 11 employ hybrid approaches.
finding that the CNN consistently achieved slightly greater                   This subsection outlines the feature extraction methods and
accuracy gains than XGBoost; Feizbakhsh and Omran-                            core algorithms used in these combined frameworks.
pour [76] extracted cluster-based phase-space density fea-
tures via k-means on reconstructed EEG windows, then fed                       a: FEATURE EXTRACTION
these into RF and CNN, observing that the CNN performed                       Among the 11 hybrid studies, six studies rely on end-
marginally better than the RF. Müller et al. [136] contrasted a               to-end deep architectures that automatically learn features
shallow MLP with CNN and examined whether false alarms                        directly from their inputs, without any handcrafted pre-
from fundamentally different pipelines align temporally,                      processing. Of these six studies, four studies specifically

159822                                                                                                                                     VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


convert raw EEG into a time-frequency representation prior                        b: CORE ALGORITHM
to model ingestion: Usman et al. [26], Parveen et al. [62],                       In this section, 11 studies are presented that combine machine
Toraman [67], and Esmaeilpour et al. [70]—all first convert                       learning and deep learning techniques. Eight of these employ
EEG windows into 2D spectrograms via STFT or Fourier                              a canonical two-stage framework—first using a deep learning
transform (FT), then feed those images into CNN-based                             model for automatic feature extraction and then a traditional
architectures for automatic feature learning and seizure                          machine learning classifier for prediction.
prediction. The remaining two deep models in this group                              Among these eight studies, six studies propose a single
bypass any time-frequency imaging and consume either raw                          hybrid machine learning and deep learning algorithm: five
EEG snippets or prevectorized feature arrays directly.                            utilize SVM as the classifier [26], [37], [62], [165], and one
   In a distinct ensemble strategy, Reuben et al. [161] aggre-                    uses Bayesian linear discriminant analysis (BLDA) [148];
gated the outputs of multiple crowd-sourced machine learn-                        on the feature-extraction side, four employ CNN [26],
ing and deep learning models instead of relying on raw EEG                        [148], [154], [165], one employs pretrained EfficientNet-B0
signals. Each base model produced a time series of ‘‘preictal                     network [37], and one adopts dense layered network model
probability’’ estimates; these series are concatenated into a                     (DLNM) [62]. The remaining two studies construct multiple
single composite probability vector that served as input to                       hybrid deep learning and machine learning pipelines: Tora-
a downstream MLP. The final MLP was trained to learn                              man [67] proposed three hybrid frameworks that combine
optimal combination weights over the constituent model                            pretrained 2D CNN with SVM classifiers, where each
outputs, yielding a fused forecast that improves overall                          model first extracts deep spectral features via the CNN and
seizure prediction accuracy.                                                      then feeds the resulting feature vectors into an SVM to
   The remaining four studies employ a hybrid pipeline in                         distinguish preictal from interictal states; Zargar et al. [146]
which EEG segments are first represented by a suite of                            proposed nine concise hybrid pipelines combining pre-
manually engineered features; these feature vectors are then                      trained CNN for feature embedding with traditional machine
input to deep neural networks to perform a second-stage,                          learning classifiers to discriminate preictal from interictal
automated representation learning. This two-tiered approach                       segments. In contrast to the canonical two-stage hybrids
enables the models to refine the initial handcrafted descrip-                     described above, the remaining three studies employ more
tors, learning higher-order abstractions and compensating for                     intricate ensemble strategies. Usman et al. [86] outputed
their limitations. In Usman et al. [86], each 30-s EEG window                     meta-learn from SVM, CNN, and LSTM base learners using
was first decomposed using empirical mode decomposition,                          model-agnostic meta-learning (MAML); Reuben et al. [161]
after which a rich set of features was extracted: time-                           ensembled 8 crowd-sourced seizure prediction pipelines via
domain statistics such as mean, variance, skewness and                            a shallow, lightweight MLP; and Esmaeilpour et al. [70]
kurtosis; spectral descriptors including centroid, variance,                      applied parallel classifiers—a fully connected network, RF,
skewness and kurtosis computed on the intrinsic mode                              and SVM—on embeddings extracted from a CNN and fuse
functions; entropy-based metrics; autoregressive prediction                       their predictions through majority voting.
errors; Hjorth parameters; and various energy-related                                Among these hybrid approaches, only Parveen et al. [62]
measures. Saadoon et al. [37] extracted five band-limited                         proposed a novel method combining DLNM with linear
amplitude profiles (δ through γ ) via normalized STFT                             SVM, using pure linear SVM as the baseline and increasing
and inter-channel Pearson correlations from each 10-s                             average accuracy on the CHB-MIT dataset from 95.6% to
epoch. Hosseini et al. [165] employed Daubechies-4 wavelet                        96.0%, an improvement of 0.4 percentage points.
decomposition to extract detail coefficients at levels 4 to 6 and
computed multidimensional handcrafted features—including
time-domain statistics, frequency descriptors, entropy and                        4) DEEP LEARNING ARCHITECTURES
fractal dimensions, Hjorth parameters, and autoregressive                         Among the reviewed studies, 107 adopt deep learning
prediction errors—then rearranged these feature vectors into                      architectures. This subsection outlines the feature extrac-
‘‘feature maps’’ which, together with three-channel EEG                           tion methods and the core algorithms employed in these
images generated from θ/α/β band power topographies,                              frameworks.
were fed into a convolutional neural network for deep
representation learning. Finally, Zargar et al. [146] computed
22 univariate measures—including time-domain moments,                             a: FEATURE EXTRACTION
spectral moments, entropy, correlation dimension, and                             Of the 107 studies leveraging deep learning architectures,
Lyapunov exponents—for each 5-s epoch; the resulting                              a majority—75 studies—eschew any manual feature engi-
22-dimensional vectors were reshaped into 2D ‘‘feature                            neering, instead relying wholly on their models’ internal
images’’ and passed through ImageNet-pretrained CNN                               representation learning. Within this subset of 75 end-to-end
backbones (e.g., Xception, MobileNet-V2, EfficientNet-                            approaches, 31 studies operate directly on raw EEG signals or
B0) to learn higher-order representations that were                               minimally preprocessed time series. The remaining 44 studies
then classified either by a fully connected head or                               incorporate an explicit format conversion step to generate
by SVM.                                                                           two-dimensional spectrograms or scalograms that then serve

VOLUME 13, 2025                                                                                                                            159823

                                               Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


as the network’s input. Table 8 provides a detailed breakdown                single sparse network representation, emphasizing the most
of these distinctions.                                                       salient interactions.
                                                                                The remaining 32 studies adopt a two-stage feature
TABLE 8. Overview of format conversion in end-to-end deep learning           extraction pipeline: handcrafted EEG features are computed
studies.
                                                                             first, and these preextracted representations are then supplied
                                                                             to deep learning architectures for secondary data-driven
                                                                             representation learning. Table 9 presents an overview of the
                                                                             feature extraction methods.
                                                                                Among the 32 studies that employ handcrafted feature
                                                                             extraction before deep learning, frequency-domain features
                                                                             are the most prevalent, used in 25 studies. These features are
                                                                             typically derived through methods such as FFT [61], [126],
                                                                             [141], [162], power spectral analysis [59], [69], [150], [165],
                                                                             MFCC [29], [118], or wavelet packet decomposition [31],
                                                                             [32], highlighting the rhythmic structure of EEG signals and
                                                                             aligning well with convolutional architectures. Time-domain
                                                                             features appear in 14 studies, relying on basic statistical
   Among the reviewed studies, STFT—which partitions                         descriptors like mean, standard deviation, and skewness
EEG recordings into overlapping windows and computes a                       to capture signal amplitude characteristics. Time–frequency
localized spectrum for each—is by far the most common                        domain features are adopted in 10 studies, where transfor-
time-frequency preprocessing step, appearing in 21 papers.                   mations like STFT [43], [73], [85], DWT [24], [141], [152],
Continuous wavelet transform (CWT), used in four studies,                    [165], or CWT [65], [114] provide a joint temporal and
offers a multiscale time-frequency decomposition by corre-                   spectral representation of EEG; these are especially useful
lating the signal with scaled and shifted mother wavelets. The               for capturing nonstationary behaviors associated with preictal
S-transform, reported in three studies, combines elements of                 transitions. Nonlinear features, reflecting the complex and
STFT and CWT by applying a frequency-dependent Gaussian                      chaotic properties of EEG signals, are utilized in nine
window, thereby achieving improved spectral resolution.                      studies, often based on sample entropy [73], [110] or fractal
DWT, cited in two studies, hierarchically decomposes                         analysis [39], [126], [141]. Spatial and connectivity-based
the signal into sub-bands aligned with canonical EEG                         features—those that represent inter-channel dependencies
rhythms. FFT—an efficient algorithm for obtaining the                        via functional connectivity metrics or graph-theoretical
global spectrum—and mel-frequency cepstral coefficient                       constructs—are relatively uncommon. References [24],
(MFCC)—which capture the spectral envelope on a per-                         [59], and [98], reported in only six studies. Finally,
ceptually motivated scale—are each applied in two studies.                   dynamic features—designed to reflect the evolution of
Finally, two studies construct Pearson-correlation-based                     signal properties over time—are used in just three studies.
brain-network graphs from pairwise channel correlations and                  In Borhade et al.’s ResNeXt–LeNet work [59], EEG frames
derived connectivity features for classification.                            undergo STFT and spectral flux was computed to capture
   In addition to these dominant time–frequency transforms,                  dynamic changes; in Ravindranath et al.’s MMA study [162],
eight studies explore more specialized conversion tech-                      a multivariate channel graph was Gaussian-smoothed across
niques. One study employed global field power (GFP)                          scales to extract random matrix theory features; and in
to condense multichannel EEG into a single time series                       Assali et al.’s CNN classification [73], a Kalman-filtered
reflecting overall signal variance [139]. Another used ICA                   multivariate autoregressive model (MVAR) model applied to
to isolate and remove artifacts while preserving neural                      2-s windows produced an eigenvalue-based stability index
components [57]. Markov transition field (MTF) was applied                   that captured temporal dynamics.
in one study to encode temporal transitions into image-                         Distinct from the preceding extraction methods, eight
like representations [103]. The multivariate weighted fuzzy                  of the 32 studies augment their pipelines with additional
granular recurrence plot method was used to construct graphs                 format transformations to enrich the learned representations.
that capture frequency-specific connectivity patterns. [97].                 Two of these first construct specialized graph structures—
Another study employed PLV analysis to quantify phase                        one by using maximum cross-correlation to generate a
synchrony between electrode pairs, using the resulting mea-                  channel-wise brain graph [24] and the other by leveraging
sures as input features [122]. Power spectral density (PSD)                  metadata to build a multimodal association graph [162]—
mapping was used to capture the distribution of signal power                 and subsequently extract graph embedding features from
across frequencies [142]. The synchrosqueezing transform                     those structures. Five others manually extract feature sets and
(SST) provided sharpened time–frequency localization by                      encode them as graph-based inputs, such as spatial and func-
reassigning spectral energy [113]. Finally, Li et al. [159]                  tional edge-weight graphs between electrodes [32], Pearson
proposed a multi-metric similarity-weighted sparse electrode                 correlation–based functional connectivity graphs [65], [150],
graph that combines several connectivity measures into a                     global phase-amplitude coupling (GPAC) maps [114], and

159824                                                                                                                                    VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 9. Overview of feature extraction methods in deep learning based seizure prediction.


power spectral density energy diagrams [69]. The last study                       deep MLP [89], [152] and deep neural network (DNN) [142]
employ a dual-stream configuration, supplying the model                           to fully connected feedforward networks [170].
with both an STFT spectrogram and manually computed                                  Finally, one TCN-based study uses an anchoring temporal
feature values, thereby enriching its spatiotemporal and                          convolutional network (ATCN) with dilated causal convo-
spectral representations [72].                                                    lutions for very long receptive fields, and one variational
                                                                                  autoencoder (VAE)-based study employs a residual convolu-
                                                                                  tional variational autoencoder that flags preictal windows as
b: CORE ALGORITHM                                                                 reconstruction outliers in the learned latent space.
Of the 107 studies applying deep learning to seizure                                 In the hybrid-architecture group, 30 studies fuse com-
prediction, only Georgis–Yap et al. conducted a direct head-                      plementary modules to harness multiple feature domains.
to-head comparison of multiple architectures, evaluating                          The most common configuration—reported in 16 studies—
supervised CNN, CNN–LSTM hybrids, and TCN along-                                  stacks a CNN front end with an RNN back end: lightweight
side their unsupervised autoencoder counterparts (CNN-AE,                         1-D/2-D CNN [27], [39], [72], [98], [171] or residual
CNN–LSTM-AE, and TCN-AE) [124]. The other 106 studies                             variants such as ResNet-50 [44] and deep residual shrinkage
each examine a single primary model; these algorithms are                         network (DRSN) [50] distill spatial-spectral patterns, which
listed in Table 10. Collectively, the table provides a compact                    are then temporally aggregated by LSTM/bidirectional long
yet comprehensive overview of the purely deep learning                            short-term memory (BiLSTM) [27], [39], [44], [52], [53],
based approaches reported in the literature.                                      [64], [92], [169] or, less often, GRU units [35], [50]. Eight
   In the single-architecture category, 76 studies each imple-                    studies fuse CNN with Transformer blocks, typically using
ment one core deep learning backbone. Among these,                                a lightweight 1-D or 2-D CNN front end [43], [55], [103]
44 CNN-based studies feature architectures ranging from                           followed by a standard self-attention encoder [43], [55],
lightweight 1-D [42], [84], [101], [149], to deep multi-                          [91] that refines the convolutional feature maps to capture
branch 2-D [25], [29], [36], [38], [87], [100], [129], [159]                      long-range dependencies. Less common hybrids include
and 3D–2D hybrids [88]; whether using dilated kernels,                            two CNN-GNN pipelines. Dynamic functional connectivity
channel attention, or multi-view inputs, each relies on                           neural network [54] is a dual-branch architecture with
convolutional filters to capture spatial–spectral signatures                      separate GCN and CNN streams, while spatio-temporal-
of preictal EEG. 14 studies utilize RNN-based designs to                          spectral network [104] integrates a spatio dynamic graph
model the long-range temporal dynamics of preictal EEG                            convolution network branch with triple-attention and multi-
sequences; examples include two-layer LSTM [24], [61],                            scale CNN layers, thereby coupling spectral filtering with
bidirectional LSTM [31], [157], deep gated recurrent unit                         graph-based reasoning.
(GRU)–LSTM cascades [49], stacked LSTM variants [123],                               Four additional hybrids appear only once each, under-
[158], and LSTM enhanced with metadata-supported multi-                           scoring the field’s exploratory breadth: a CNN-FNN
variate attention [162]. Seven studies adopt Transformer-                         network [111] augments convolutional embeddings with
based encoders, substituting self-attention for recurrence to                     a Fourier neural network branch to enrich spectral
model global context across extensive windows.                                    cues; a restricted Boltzmann machine (RBM)-Transformer
   Five studies investigate GNN–based approaches, including                       model [33] couples contractive slab-and-spike generative
graph convolutional network (GCN) [32], [57], [118], joint                        layers with self-attention to capture higher-order dependen-
graph structure and representation learning network [150],                        cies; a RNN-Transformer cascade [125] stacks a LSTM
and graph attention network (GAT) [122]; these methods                            encoder beneath a Transformer, uniting sequence memory
model electrodes as graph nodes and leverage message                              with global context; and a GNN-RNN pipeline [65] combines
passing to infer dynamic connectivity. Four studies employ                        spatial GCN with temporal LSTM reasoning to jointly model
feedforward neural network (FNN)-based architectures, from                        electrode connectivity and signal evolution.

VOLUME 13, 2025                                                                                                                         159825

                                                Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 10. Overview of core algorithms in deep learning based seizure prediction.


   Among the 107 studies that applied deep learning to                        features, yielding a compact and informative subset. Wilks’
seizure prediction, only 10 explicitly benchmark their models                 Lambda–based selection [151] evaluates multivariate dis-
against simple linear baselines. Qiao et al. [33] proposed                    crimination via the ratio of within-group to total variance and
Attention-CssCDBN, raising sensitivity on the CHB–MIT                         retains features that minimize this statistic to enhance class
dataset from 81.0% to 98.5% compared with LDA;                                separability. Other studies performed channel selection using
Pandey et al. [123] developed a stacked LSTM enhanced by                      statistical or learned criteria—such as entropy (signal unpre-
hybrid feature augmentation and FB-SARO optimisation,                         dictability), variance (signal power), kurtosis and skewness
improving accuracy by 1.40% to 4.94% over LR across                           (non-Gaussian characteristics), or attention-derived weights
four public datasets; Hassoon et al. [141] introduced the                     from trained models—–to identify the most relevant EEG
HSA-CAE-CNN, achieving roughly a 9.9-percentage-point                         channels for downstream analysis [35], [84]. Furthermore,
performance gain relative to the minimum-distance classifier                  two studies combine both explicit and implicit approaches:
(MDC); Tsiouris et al. [24] employed a two-layer LSTM,                        these works first applied PCA to extract the leading principal
boosting average sensitivity and specificity by 7.2%–16.4%                    components and then embedded additional compression
compared with a linear SVM over 15 to 120 min prediction                      within the model architecture via low-dimensional bottleneck
horizons. Collectively, these comparisons underscore the                      layers or 1 × 1 convolutional filters to further refine and
substantial advantage of deep models in capturing the                         compact EEG feature representations [141], [162].
non-linear preseizure dynamics embedded in EEG signals.                          Seizure prediction modelling remains overwhelmingly
                                                                              convolution-centric: fully 71.8% of studies rely on a pure
5) DIMENSIONALITY REDUCTION TECHNIQUES                                        deep learning backbone, with CNN variants alone accounting
Of the 149 studies, 49 (32.9%) incorporate implicit dimen-                    for 48.3%. Hybrid stacks occasionally append LSTM or
sionality reduction directly within model architectures.                      Transformer layers to extend temporal context, yet archi-
These include autoencoders that impose compression via                        tectures driven entirely by attention mechanisms or graphs
a low-dimensional bottleneck layer; convolutional neural                      appear only as proofs of concept. Because most pipelines con-
networks that reduce representation size through spatial                      vert EEG into short-time spectrograms, networks are tuned to
downsampling and 1 × 1 convolutional filters; and attention                   local time–frequency textures rather than large-scale network
mechanisms that adaptively weight and aggregate the most                      dynamics; features such as phase synchrony or cross-channel
informative feature dimensions during training.                               graph structure are seldom learned directly. Dimensional-
   Eight studies (5.4%) apply explicit dimensionality reduc-                  ity reduction is likewise predominantly implicit, achieved
tion or channel selection techniques. PCA [90], [148],                        through architectural operations (e.g., pooling and strides)
[152], [167] identifies orthogonal directions that capture                    rather than explicit feature selection, which further narrows
the greatest variance, ranks components by explained vari-                    the representational scope. Compounding this methodolog-
ance, and retains the minimal subset whose cumulative                         ical narrowness, only a small subset of studies benchmark
variance exceeds a predefined threshold, thereby denoising                    their models against linear baselines, making it difficult to
and reducing dimensionality. Minimum redundancy maxi-                         quantify the true incremental value of deep architectures
mum relevance (mRMR) feature selection [39] iteratively                       and risking overestimation of ‘‘state-of-the-art’’ gains. The
chooses features that maximize mutual information with                        field thus exhibits both technical maturity—strong, repeat-
the target while minimizing redundancy among selected                         able CNN baselines—and methodological conservatism that


159826                                                                                                                                     VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 11. Overview of SOP and SPH settings.


may hamper progress toward robust, patient-independent                               These evaluation indicators offer deep insights into the
generalisation.                                                                   performance of the implemented models and are widely used
                                                                                  to assess their effectiveness. Sensitivity (SEN, see Eq. (1)) is
D. EXPERIMENTAL VALIDATION SETUP                                                  the most frequently reported metric, appearing in 133 studies,
This section covers three core elements of our experimental                       and it intuitively reflects the probability that the predictor
validation: the definitions of seizure occurrence period (SOP)                    will catch an impending seizure: the higher the value, the
and seizure prediction horizon (SPH); the key performance                         fewer attacks slip through and the safer the patient. Recent
metrics for assessing accuracy and timeliness; and the data                       experimental work generally regards a SEN of ≈ 0.80–
partitioning schemes for training, validation, and testing.                       0.90 as clinically acceptable. At the same time, markedly
Rigorous validation is vital to prove our method’s reliability                    lower scores suggest a higher risk of missed events and
and generalizability across varied EEG datasets.                                  limited practical usefulness [31], [38], [45], [64], [86], [108],
                                                                                  [135]. The next most common metric is accuracy (ACC,
                                                                                  see Eq. (2)), reported in 89 studies. It captures the overall
1) SOP AND SPH                                                                    share of epochs that the predictor labels correctly—whether
Of the 149 studies, 54 explicitly define and apply a                              seizure or non-seizure—so higher values imply fewer total
SOP, whereas 58 clearly specify and implement a SPH,                              misclassifications. On widely used public benchmarks, ACC
as summarized in Table 11.                                                        values around 0.85 and above are typical, yet this figure
   Among the studies that explicitly report their timing                          alone is not enough to demonstrate practical utility unless it
configurations, two consistent patterns stand out. First, for                     is supported by strong sensitivity and acceptably low false-
the SOP, a 30 min window is overwhelmingly favored—37                             alarm rates [42], [65], [73], [98], [125], [165]. Specificity
studies adopt this setting—while alternative durations of 20,                     (SPE, see Eq. (3)) ranks third with 75 studies. It expresses the
40, 50, and 60 min appear only sporadically. Second, the                          probability that the predictor correctly dismisses non-seizure
SPH most commonly centers on 5 min, cited by 30 studies;                          (interictal) segments, so higher values translate directly into
the next-most-frequent choice is 10 min, reported by nine                         fewer false alarms and less patient or caregiver disruption.
studies, whereas ultra-short windows of 1 to 3 min are rarely                     In practice, seizure-prediction systems often aim for SPE
used. Longer or atypical settings (e.g., 10 s, 14 min, or a                       above 0.90 to keep the hourly false-alarm rate within an
30 min SPH) are exceptionally uncommon. Collectively,                             acceptable clinical burden; if SPE drops much below that
these findings reveal a strong convergence on clinically                          level, even a highly sensitive model can become impractical
pragmatic defaults—namely, a 30 min SOP paired with a                             because of the volume of unnecessary warnings [54], [72],
5 min SPH.                                                                        [129]. The false prediction rate per hour (FPR/h, see Eq. (4))
                                                                                  equals the number of false positives divided by the total
2) EVALUATION INDICATORS                                                          monitoring hours and is noted in 69 studies. It measures
In this section, we analyze the evaluation metrics most fre-                      how many spurious alerts the system generates each hour;
quently reported in the surveyed study. Figure 4 summarizes                       lower figures reduce alarm fatigue for patients and staff.
these metrics and depicts their prevalence across the reviewed                    A practical benchmark is ≤ 0.1 alarms per hour—roughly
studies.                                                                          one false alert every 10 h—to keep the burden acceptable

VOLUME 13, 2025                                                                                                                             159827

                                                Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


     FIGURE 4. Distribution of the included studies by reported evaluation metric. SEN—sensitivity (recall or true positive rate), ACC—accuracy,
     SPE—specificity (true negative rate), FPR/h—false prediction rate per hour, ROC-AUC—area under the receiver operating characteristic curve,
     F1-score—harmonic mean of precision and recall, Pre—precision, FPR—false positive rate, Time-in-Warning—proportion of monitoring time
     spent in warning state, FDR—false discovery rate, FNR—false negative rate, NPV—negative predictive value, MCC—Matthews correlation
     coefficient, PR-AUC—area under the precision–recall curve.

in continuous monitoring [24], [54]. Area under the receiver                  it is plotted on a maintenance dashboard; a rising trend
operating characteristic curve (ROC-AUC) captures how                         signals that postprocessing rules or thresholds may need
well the model separates seizure from non-seizure cases                       retuning to keep user trust high. False negative rate (FNR,
independent of any single threshold: 0.5 indicates no better                  three studies [165], see Eq. (10)) quantifies missed seizures—
than chance, 1.0 reflects perfect discrimination. Values ≥                    –the complement of sensitivity. Deployment logs track it
0.90 signal strong overall performance, but ROC-AUC alone                     continuously; any sustained increase prompts checks for
may obscure precision issues on highly imbalanced data [91],                  sensor noise, channel drop-outs, or model drift that could
[115], [142].                                                                 jeopardise patient safety. Negative predictive value (NPV,
   Additionally, the F1-score (30 studies [98], see Eq. (5))                  three studies [170], see Eq. (11)) reflects how reliable a ‘‘no-
is the harmonic mean of precision and sensitivity. F1-score                   seizure’’ state is. A stable, high NPV reassures users that daily
balances ‘‘how many seizures are caught’’ with ‘‘how many                     activities can continue during ‘‘safe’’ periods, whereas a dip
alerts are correct’’. It is beneficial on imbalanced datasets:                typically triggers signal-quality diagnostics or recalibration,
values ≥ 0.80 suggest that the model is not favouring one                     and Matthews correlation coefficien (MCC, two studies [98],
class at the expense of the other; Precision (PRE, 28 stud-                   see Eq. (12)) combines all four confusion-matrix terms into a
ies [35], see Eq. (6)) tells how trustworthy each alarm is—the                single value ranging from –1 (inverse prediction) through 0
higher it is, the fewer false alerts clinicians must dismiss.                 (random) to 1 (perfect). Because it remains informative
Practical systems often aim for PRE ≥ 0.70 to keep user                       even when class proportions vary, MCC is well-suited for
confidence high; False positive rate (FPR, 12 studies [44],                   comparing models across datasets and tracking performance
see Eq. (7)) is the probability that a nonseizure segment is                  over time. Area under the precision–recall curve (PR-AUC)
erroneously classified as preictal; lower values are preferable;              is mentioned in only one study [124]. The area under the
Time-in-Warning is the proportion of total monitoring time                    precision–recall curve summarises the trade-off between
that the system remains in an alert state (five studies [161], see            catching seizures (recall) and avoiding false alarms (preci-
Eq. (8)); it directly quantifies user burden. Maintaining Time-               sion) at every threshold. It is routinely reported alongside
in-Warning below 20–30% is generally recommended so that                      ROC-AUC during pre-deployment validation to demonstrate
patients do not live in a near-constant state of anticipatory                 robustness on the highly imbalanced data typical of long-term
stress.                                                                       EEG monitoring.
   Less frequently reported yet still important is the false
discovery rate (FDR, three studies [109], see Eq. (9)), which                                   TP
                                                                                    SEN =                                                              (1)
shows what proportion of issued alerts are false. In practice,                                TP + FN

159828                                                                                                                                     VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


                 TP + TN
    ACC =                                       (2)                               the model is trained and evaluated K times, each time using
           TP + TN + FP + FN                                                      a different fold for testing and the others for training. This
              TN                                                                  scheme ensures that every sample contributes to both training
    SPE =                                       (3)
           TN + FP                                                                and validation, yielding a more balanced and comprehensive
                     FP                                                           assessment.
  FPR/h =                                       (4)
           Total monitoring hours                                                    Leave-one-patient-out (LOPO) is used in nine studies
                 2 TP                                                             (6.0%). In each iteration, all data from a single patient
     F1 =                                       (5)
           2 TP + FP + FN                                                         are withheld for testing while the model is trained on
              TP                                                                  data from the remaining patients. LOPO directly measures
     Pre =                                      (6)
           TP + FP                                                                cross-subject generalization and is especially important for
              FP                                                                  patient-independent seizure prediction scenarios.
    FPR =                                       (7)
           FP + TN                                                                   Another seven studies employ alternative validation
                               Twarning                                           schemes grouped under ‘‘Others’’, highlighting method-
        Time − in − warning =                   (8)                               ological heterogeneity beyond the mainstream. Two adopt
                                 Ttotal
              FP                                                                  sample-level leave-one-out (LOO), which maximizes data
   FDR =                                        (9)                               usage but can produce optimistic performance estimates [36],
           FP + TP
              FN                                                                  [132]. An intra-patient, instance-level, multi-round cross-
   FNR =                                       (10)                               validation scheme balances seizure coverage at the expense
           FN + TP
              TN                                                                  of assessing inter-patient generalization [138]. Leave-one-
   NPV =                                       (11)                               day-out (LODO) is used to account for day-to-day EEG
           TN + FN
                      TP × TN − FP × FN                                           variability [163], while sequential time-window analysis
   MCC = √                                                                        characterizes temporal performance trends [107]. Reuse of
             (TP + FP)(TP + FN)(TN + FP)(TN + FN)
                                                                                  standardized splits from MLSPred-Bench enhances repro-
                                               (12)                               ducibility [164], and a critical appraisal of partitioning
                                                                                  schemes reveals common validation pitfalls [130]. Collec-
where TP, TN , FP, and FN denote the counts of true                               tively, these approaches reflect efforts to mitigate method-
positives, true negatives, false positives, and false negatives,                  ological weaknesses and improve clinical relevance.
respectively; Twarning is the total duration during which the                        Validation strategies typically prioritize privilege conve-
system is in an alarm state, and Ttotal is the overall monitoring                 nience over clinical realism. A single 30 min SOP and
time.                                                                             5 min SPH dominate timing choices, and SEN/ACC headline
                                                                                  most scorecards, while practical metrics like false alarms per
3) DATA VALIDATION STRATEGY                                                       hour are reported in fewer than half of the studies. Hold-
Effective data partitioning is indispensable for unbiased per-                    out or leave-one-seizure-out splits cover about 67.8% of
formance evaluation and for assessing model generalization                        studies; rigorous cross-patient leave-one-patient-out valida-
in seizure prediction research. In this section, we summarize                     tion is used sparingly. Consequently, many impressive AUCs
and compare the training, validation, and test splits employed                    represent intra-subject performance on curated data rather
in the reviewed studies, including hold-out, k-fold cross-                        than proof that a model will hold up across new individuals,
validation, leave-one-seizure-out, and leave-one-patient-out                      devices, or 24-h home monitoring—an essential step for
schemes. Table 12 presents a statistical overview of these                        clinical adoption.
validation strategies.
   In the surveyed studies, the hold-out scheme is the most
prevalent data-partitioning strategy, appearing in 57 studies                     E. POSTPROCESSING DECISION STRATEGIES
(38.2%). It divides the data into fixed proportions—                              After model inference, postprocessing decision strategies
commonly 70% to 80% for training and the remainder for                            transform raw outputs into reliable seizure alarms. By impos-
testing—without subsequent reshuffling. This single, one-                         ing temporal consistency and filtering out isolated spurious
time split is simple to implement and is widely used in both                      signals, they enhance robustness and reduce the false alarm
traditional machine learning and deep learning studies.                           rate.
   Leave-one-seizure-out (LOSO) is employed in 44 studies                            Among the 149 studies, 58 incorporate explicit post-
(29.5%). Under this protocol, each seizure is held out in                         processing mechanisms, underscoring their essential role in
turn as the test set, with the remaining seizures and interictal                  turning raw model outputs into actionable seizure warnings.
segments forming the training data. Repeating this procedure                      These mechanisms cluster into four principal categories—
for every seizure permits evaluation of the model’s ability                       voting, thresholding, temporal smoothing, and advanced
to predict previously unseen seizure events from the same                         fusion strategies. Table 13 summarizes the specific tech-
patient.                                                                          niques; because many studies adopt more than one approach,
   K-fold cross-validation appears in 32 studies (21.5%). The                     the method frequencies reported exceed the study count and
data are partitioned into K approximately equal folds, and                        therefore do not correspond directly to the number of studies.

VOLUME 13, 2025                                                                                                                          159829

                                                Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 12. Overview of validation strategies.


TABLE 13. Overview of postprocessing decision strategies.


   The voting mechanism is the most widely used post-                         TABLE 14. Top three most frequently used combination postprocessing
                                                                              methods.
processing strategy, appearing in 31 studies. Among these
approaches, the k-of-n scheme predominates and is reported
in 15 studies. In this approach, a window of n consecutive
segments is examined, and an alarm is issued once at least
k segments within that window are classified as positive.
The segment-ratio method—issuing an alarm when the
proportion of positive segments in the window exceeds
a preset threshold—appears in eight studies, whereas the
consecutive—segment method—requiring several successive
positive segments to confirm an alarm—is employed in six
studies. Less common variants include the segment-max
approach, which triggers an alarm based on the maximum                           To curb prediction volatility and reduce false-positive
probability (or score) among segments in the window                           alarms, many studies apply temporal smoothing and
and is reported by only one study [172], as well as the                       debouncing techniques. Moving-average smoothing is the
multi-channel voting method, which integrates votes across                    most common, appearing in 21 studies; it averages prediction
multiple EEG channels and is also documented in a single                      scores or probabilities over a sliding window to produce
study [129].                                                                  steadier outputs. A refractory-period scheme is reported in
   The threshold mechanism is reported in 22 studies,                         10 studies, inserting a fixed silent interval after each alarm
with fixed thresholding representing the dominant method,                     to prevent rapid re-triggering. Finally, a sliding-window
adopted by 21 studies. In this approach, a threshold is                       counting approach, used in five studies, tallies positive
predefined, and an alarm is triggered once the model output                   detections within a preset interval and issues an alarm only
exceeds this threshold. By contrast, adaptive thresholding,                   when the count exceeds a predefined threshold.
which dynamically adjusts the threshold based on changing                        Only a handful of studies investigate advanced fusion
conditions or patient-specific data, is rarely explored, having               strategies designed to boost generalization and sustain
been reported in only a single study [162].                                   stable, long-term predictions. Four studies discuss adaptive

159830                                                                                                                                     VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 15. Overview of post-hoc explainability mechanisms.


ensemble mechanisms, introducing advanced fusion                                  actual deployment strategies that bring these models into
approaches such as MAML-based ensemble classifiers [86],                          clinical or edge environments.
simple fully connected ensemble classifiers [158], and
multi-classifier voting methods [37], [70]. Temporal cal-                         1) INTERPRETABILITY
ibration and scoring techniques are reported in three                             To assess how interpretability is addressed in practice,
studies, involving specific approaches like platt calibra-                        we cataloged the post-hoc explainability techniques reported
tion [163], circadian weighting which accounts for circadian                      across the literature. Of the 149 seizure prediction studies
rhythms [161], and both chronological and cumulative firing                       reviewed, only 11 explicitly integrate an explainability mod-
power methods [143], all of which integrate prediction                            ule, which highlights a considerable gap between algorithmic
probabilities over time. Lastly, the meta-decision framework                      performance and clinical transparency. As summarized in
is introduced in only one study through the learn-then-test                       Table 15, the post-hoc explainability mechanisms employed
(LTT) approach [137], dynamically adjusting predictions                           in EEG-based seizure prediction studies predominantly fall
following an initial learning phase to improve statistical                        into three main categories: feature attribution or contri-
robustness.                                                                       bution scoring, statistical or network visual analytics, and
   However, as Table 14 illustrates, combination methods are                      gradient-based activation visualisation.
the most frequently employed postprocessing strategies in                            Feature-attribution methods, reported in four studies,
these studies.                                                                    mainly utilize algorithms such as layer-wise relevance prop-
   The k-of-n voting scheme is the most prevalent strategy,                       agation (LRP), SHapley additive exPlanations (SHAP), and
appearing in 15 studies. The next most common workflow—                           Local Interpretable Model-Agnostic Explanations (LIME),
reported in 5 studies—first smooths model probabilities                           generating heat maps that highlight the relevance of EEG
using a moving-average filter and then applies a fixed                            channels or frequency bands. For example, Jemal et al. [25]
threshold, thereby attenuating transient spikes and stabilizing                   applied LRP to their CNN by backpropagating relevance
the decision boundary. An additional refinement, documented                       scores from the output back to each input channel and time
in four studies, appends a 30-minute refractory period to this                    point, producing heat-maps that directly visualise which EEG
pipeline, such that once an alert is issued, any subsequent                       channels drove the model’s seizure prediction decisions.
detections occurring within the refractory window are                                Meanwhile, statistical or network visual-analytics
automatically suppressed.                                                         approaches, reported in four studies, leverage functional-
   Although front-end networks continue to grow deeper, the                       connectivity analyses (e.g., directed transfer function),
final alert logic remains predominantly heuristic. Approxi-                       Kullback–Leibler (KL) divergence, and feature-importance
mately one-third of the studies implement a simple k-of-n                         ranking to interpret model decisions by quantifying changes
voting scheme or a fixed probability threshold. Another                           in statistical patterns or network structures across seizure
fifth incorporate moving-average smoothing or a refractory                        states. For example, Wang et al. [65] computed directed
silent period; however, adaptive or risk-aware calibration                        transfer function–based information-flow features between
remains largely absent. Only four studies explore learned                         iEEG channels, rebuilt them into channel-frequency maps,
ensembles or meta-decision layers, and just one introduces                        and then used BrainNet Viewer to plot the resulting func-
dynamic thresholds aligned with circadian context. This                           tional networks—clearly showing how preictal connectivity
continued reliance on hard-coded postprocessing leads many                        patterns differ from interictal ones.
systems to exhibit elevated false-alarm rates under conditions                       Finally, gradient-based activation-visualization tech-
of degraded signal quality or shifting patient states—                            niques, reported in three studies, apply methods such as
constituting a major barrier to real-world deployment.                            gradient-weighted class activation mapping (Grad-CAM) and
                                                                                  saliency maps to highlight the regions of spectro-temporal
                                                                                  EEG representations on which the model focuses. For
F. CLINICAL INTERPRETABILITY AND DEPLOYMENT                                       example, Guo et al. [104] used Grad-CAM on their STS-
To bridge the gap between algorithmic development and                             Net’s pyramid convolution outputs—back-propagating class
real-world use, this section examines two complementary                           gradients to each rhythm’s feature map—to produce
facets of model practicality: first, the post-hoc interpretability                heat-maps that pinpointed δ and θ band activations as the
techniques that make predictions transparent, and then the                        most discriminative for preictal prediction.

VOLUME 13, 2025                                                                                                                         159831

                                               Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


TABLE 16. Overview of deployment categories for EEG-based seizure prediction systems.


2) DEPLOYMENT                                                                the proposed convolutional autoEncoder–ensemble long
To evaluate how research prototypes have been translated into                short-term memory (CAE-eLSTM) hardware predictor in
practical systems, we analyze the deployment approaches                      stand-alone VHDL on an Altera Arria 10 GX FPGA and syn-
employed in EEG-based seizure prediction studies.                            thesized it to 45 nm ASIC technology using Synopsys Design
   Currently, the majority of studies focus on developing and                Compiler at 120 MHz, achieving 1.53 mW power consump-
training prediction models without explicit deployment or                    tion. Massoud et al. [152] deployed the patient-specific MLP
practical validation. Typical computational setups reported                  seizure prediction model on a Xilinx Virtex-7 FPGA using
in these training-focused studies exhibit significant diversity.             10-bit fixed-point arithmetic, occupying 65401 LUTs and
For instance, Truong et al. [112] trained their model in a                   10208 registers with 7.3% device utilization, and achiev-
Python 2.7 environment using Keras 2.0 with a TensorFlow                     ing 200 MHz operation at 1.5 W power—demonstrating
1.4.0 backend. They parallelized convolutional neural net-                   markedly higher energy efficiency than inference on an
work computations across four NVIDIA Tesla K80 GPUs                          NVIDIA RTX 2060 GPU.
(each 24 GB VRAM; 96 GB total), markedly accelerating                           Additionally, three studies respectively deploy seizure
the processing of 30 s short-time Fourier transform (STFT)                   prediction models or conduct performance testing on an
feature matrices. Toraman et al. [67] ran experiments in                     IoT edge device, a cloud platform, and an LTE edge-
Python 3.5 with Keras 2.1.6 on a Linux server equipped with                  computing testbed. Ahmad et al. [64] trained and evaluated
an NVIDIA GTX 1080 GPU and at least 16 GB of system                          their CNN–BiLSTM attention-based multi-feature fusion
RAM, enabling efficient forward and backward propagation                     model on a Lenovo Legion PC with 2.60 GHz Intel Core
on 224 × 224-pixel EEG spectrograms. Singh et al. [63]                       i9 CPU, 32 GB RAM and 8 GB NVIDIA RTX 2060 Max-Q
trained their CNN on a Windows 10 workstation featuring                      GPU using Python 3.7, TensorFlow and Keras and deployed
an Intel Core i7-8750H CPU (2.21 GHz), 16 GB RAM,                            the CIoT framework on a Raspberry Pi 4B with 8 GB
and an NVIDIA GeForce GTX 1060 Max-Q GPU (6 GB                               LPDDR4 SDRAM, dual-band Wi-Fi, Bluetooth 5.0 and
VRAM; 1.506 GHz), under Python 3.8, supporting end-to-                       Gigabit Ethernet for real-time EEG acquisition and SMS
end preprocessing and training workflows. Dong et al. [116]                  alerts via AWS IoT. Hassoon et al. [141] deployed a cloud-
performed training on a workstation with an AMD Ryzen 5                      based, real-time EEG signal acquisition, preprocessing,
3400G CPU (3.70 GHz), 32 GB RAM, and an NVIDIA                               and CAE-CNN inference pipeline on AWS elastic com-
GeForce RTX 2080 GPU, using Python 3.8, PyTorch                              pute instances using a three-tier infrastructure architecture.
1.12.1, and MATLAB R2020a. Saadoon et al. [37] utilized                      Hosseini et al. [165] implemented an LTE edge-computing
MATLAB’s deep learning toolbox on a workstation with                         testbed using USRP B210 software-defined radios with
an Intel Core i9 processor, 32 GB DDR4 RAM, and an                           the OpenAirInterface LTE stack on a virtual machine and
NVIDIA RTX 3090 GPU (24 GB VRAM) for EfficientNet-                           conducted performance testing.
B0 feature extraction and a six-model SVM ensemble                              Meanwhile, three studies propose conceptual system archi-
classification. These heterogeneous computational resources                  tectures, outlining potential deployment frameworks, data
and framework selections indicate that most studies remain at                flow, and interaction schemes between model components
the prototype stage and are still a considerable distance from               and external hardware, although these lacked experimental
practical system deployment.                                                 validation or practical implementation details. Finally, just
   Despite the extensive detailing of computational envi-                    one study present a tangible clinical prototype explicitly
ronments for model development, only nine studies have                       tested within a hospital or patient setting, showcasing direct
progressed to actual system deployment. As summarized                        clinical interaction, usability assessment, and preliminary
in Table 16, 2 studies demonstrated hardware-accelerated                     validation under realistic usage scenarios [167].
inference leveraging field-programmable gate array (FPGA)                       Only 11 of 149 papers incorporate any post-hoc
or application-specific integrated circuit (ASIC) technology                 explainability—typically LRP, SHAP, or Grad-CAM—and
to achieve low-power, high-speed processing essential for                    fewer than ten present hardware, edge, or IoT prototypes.
real-time seizure prediction. Khalil et al. [127] implemented                A single study reports bedside testing with real patients.

159832                                                                                                                                    VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


Without transparent rationales and on-device feasibility                          cross-dataset evaluation protocols, reported transfer gains
data, clinicians remain justifiably sceptical of ‘‘black-box’’                    are difficult to interpret. Research groups often employ
predictions, and regulatory pathways stay unclear. Bridging                       custom data splits, variable resampling strategies, and
this gap will require embedding explainability into user                          inconsistent channel selections; thus, a reported 5% AUC
interfaces, validating models under hospital workflows, and                       improvement in one study may correspond to a 10% drop
demonstrating low-power, low-latency inference on wearable                        under another lab’s configuration. Without harmonized inter-
or implantable platforms.                                                         database benchmarks, it remains impossible to disentangle
                                                                                  architectural innovation from favorable domain alignment.
IV. DISCUSSION                                                                       In sum, many reported performance gains likely reflect
While this review synthesizes major challenges and promis-                        overfitting to a pediatric scalp EEG niche rather than genuine
ing directions across five core dimensions of seizure                             advances toward generalizable, bedside seizure prediction
prediction research datasets, preprocessing methods, model                        systems. These issues stem from substantial dataset imbal-
architecture, validation strategy, and decision refinement,                       ances, including overreliance on pediatric data and limited
but it is limited by (i) searches confined to PubMed and                          adoption of high-density intracranial recordings. To improve
Web of Science and (ii) the inclusion of English-language                         robustness across diverse clinical scenarios, future research
studies only, which may have excluded relevant non-indexed                        should prioritize the integration of more representative
or non-English work.                                                              EEG datasets—–encompassing adult populations, multiple
                                                                                  recording modalities, and a broader spectrum of clinical use
A. DATASETS                                                                       cases.
Statistical profiling of 149 primary studies reveals three
structural imbalances in the dataset landscape that funda-                        B. PREPROCESSING
mentally shape what today’s ‘‘state of the art’’ actually                         Among the 149 studies surveyed, a clear ‘‘convenience
measures. First, a pronounced pediatric sEEG bias dominates                       paradigm’’ emerges in EEG preprocessing. Of the studies
current practice: 67.1% of studies rely exclusively on public                     that explicitly report segment duration, 65.6% adopt epochs
datasets, with the CHB-MIT dataset alone accounting for                           of 10 s or shorter. The most commonly used preictal
71.8% of all dataset citations. Since CHB-MIT comprises                           window falls within the 30–60-min range, and approximately
recordings from only 23 children, sampled at 256 Hz using                         58.4% of studies rely solely on standard notch or high-
a 23-channel montage, models achieving high performance                           /low-pass filters for signal denoising. Class imbalance is
on this benchmark are more likely leveraging a narrow,                            most often addressed through interictal undersampling,
age-specific feature space than demonstrating broad clinical                      reported in 57 studies, while only 19 apply sliding-window
robustness. Pediatric EEG signals characteristically exhibit                      augmentation, and fewer than 10 use advanced techniques
stronger delta activity and distinct artifact profiles compared                   such as SMOTE or GAN-based synthesis. These streamlined
to adult EEG. As a result, filters trained on this dataset                        preprocessing choices improve code portability and increase
tend to overemphasize low-frequency components while                              data volume, facilitating the reproduction of early CNN-
underrepresenting fast rhythms critical for detecting seizure                     and LSTM-based baselines. However, they introduce three
onset in adults, leading to measurable drops in sensitivity                       critical methodological constraints.
when generalized to adult cohorts.                                                   First, segmenting EEG into epochs shorter than 10 seconds
   Second, long-term, high-density iEEG remains chronically                       implicitly assumes that all discriminative preictal cues are
underutilized. Private repositories such as EPILEPSIAE (nine                      strictly local. This practice truncates hour-scale dynamics—
studies) and Freiburg (eight studies) provide up to 122 chan-                     such as gradual shifts in dominant frequency or multiday
nels at 1 kHz sampling rates, yet collectively appear in fewer                    circadian rhythms—thereby limiting the model’s access
than 12% of publications. Intracranial recordings capture                         to broader temporal context and reducing the achievable
high-frequency oscillations (80 to 250 Hz) and sub-second                         warning horizon. Second, the widespread use of raw or lightly
phase couplings that are not observable in scalp EEG. These                       filtered EEG shifts the burden of artifact rejection onto the
features enable earlier and more localized seizure warnings,                      model. While deep networks often learn to suppress line noise
but are rarely learned by current algorithms. Moreover,                           and ocular artifacts under controlled conditions, they may
iEEG datasets often span multiple weeks of continuous                             also attenuate subtle high-frequency oscillations (> 80 Hz)
monitoring, revealing circadian and multiday seizure cycles                       that serve as important intracranial biomarkers, thus dimin-
absent in scalp benchmarks. Consequently, biomarkers that                         ishing predictive performance. Third, class imbalance is
depend on high-frequency activity or fine-grained spatial                         most commonly addressed by discarding interictal data.
synchrony remain validated on limited samples, constraining                       With 57 studies undersampling the majority class, models
the generalizability of localization studies.                                     train on seizure-rich data streams that poorly reflect the
   Third, genuine cross-source integration remains rare. Only                     distribution of real-world EEG. When deployed in continuous
13.4% of studies combine public and private datasets—–                            bedside settings, such models encounter extended periods
typically via a ‘‘pre-train on CHB-MIT, fine-tune on local                        of background activity absent during training, which often
data’’ paradigm. However, in the absence of standardized                          results in false-alarm rates that exceed clinically acceptable

VOLUME 13, 2025                                                                                                                          159833

                                            Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


thresholds, despite reporting high cross-validated accuracy in               Second, because dimensionality reduction is embedded
laboratory settings.                                                      within hidden mechanisms such as convolutional strides,
   As a result, the field continues to rely on one-size-                  pooling layers, and automated channel mixing, it operates
fits-all preprocessing choices that limit comparability and               as a virtual ‘‘black box’’: researchers have no direct control
generalizability. To overcome these limitations, future                   over which channels, frequency bands, or temporal scales
research systematically explores the effects of varying epoch             survive compression and in what proportions. This opacity
lengths and prediction horizons across multiple temporal                  not only erodes interpretability and clinician trust but also
scales. It also rigorously compares state-of-the-art denoising            weakens reproducibility and precludes systematic, principled
algorithms with raw-signal pipelines. Equally important                   exploration of alternative compression strategies that might
is the adoption of robust class-balancing methods—such                    better preserve patient-specific dynamics.
as generative augmentation or active resampling—which                        Third, a pervasive limitation is the widespread exclusion
provide richer and more realistic alternatives to simple                  of basic linear baselines. Researchers often assume that deep
undersampling.                                                            learning architectures inherently outperform simpler models,
                                                                          leading to the omission of linear approaches as trivial or
                                                                          already well established—particularly given novelty expec-
C. MODEL STRUCTURE                                                        tations and publication space constraints. Incentives within
Our review reveals that contemporary EEG-based seizure                    the publication process further exacerbate this bias, favoring
prediction adheres to a ‘‘convolution-dominated, end-to-                  reports of large performance gains rather than more tempered
end-emerging, heavy time–frequency-reliant’’ paradigm.                    but rigorous comparisons to modest baselines. In addition,
Approximately 71.8% of studies employ pure deep                           linear models often require deliberate adaptation to fit within
learning architectures—predominantly CNN, followed by                     deep learning-oriented preprocessing pipelines, which further
CNN–RNN cascades, CNN–Transformer hybrids, and a                          reduces their appeal. Without such comparisons, it remains
small number of pure Transformer models—while promising                   difficult to disentangle genuine modeling advances from arti-
alternatives such as GNN, TCN, and VAE remain limited                     facts introduced through extensive preprocessing or dataset-
to isolated proofs of concept. Within these pipelines,                    specific tuning. Incorporating well-tuned linear baselines
dimensionality reduction is almost always implicit: 83%                   substantially enhances the interpretability and credibility of
of studies describing their approach rely on reductions                   performance claims for complex deep learning models.
built into the architecture rather than on explicit feature                  Consequently, the field remains dominated by convolution-
selection steps, further narrowing the representational scope             centric architectures and relies primarily on implicit dimen-
to local time–frequency textures and leaving phase syn-                   sionality reduction, yet only a limited fraction of stud-
chrony or cross-channel graph structure largely unexplored.               ies compare these models with basic linear predictors.
Compounding this methodological narrowness, only a small                  Future research should establish standardized benchmarks
minority of studies benchmark against basic linear baselines              that consistently include linear baselines, evaluate CNN,
(e.g., LDA, LR, linear SVM), making it difficult to gauge the             RNN, Transformer, and emerging architectures such as
true incremental value of convolution-heavy frameworks and                GNN and TCN under unified experimental settings, and
risking overestimation of ‘‘state-of-the-art’’ gains.                     explore lightweight hybrid models that integrate attention or
   First, this skew largely reflects the practicality of CNN on           graph-based components into compact backbones to balance
small, well-curated datasets such as CHB–MIT, where local                 accuracy and efficiency. Furthermore, a unified evaluation
time–frequency textures dominate and annotated data are                   framework that considers data dimensionality, sample size,
limited. Most pipelines either discard handcrafted descriptors            real-time constraints, and interpretability goals is essential
entirely or first project the raw EEG waveform into two-                  when assessing implicit, explicit, or hybrid dimensionality
dimensional time–frequency representations before model                   reduction strategies.
training begins. Although this strategy accelerates conver-
gence, it also removes phase information and inter-channel                 D. EXPERIMENTAL VALIDATION
relationships, both of which are crucial for modeling the                 Experimental validation in seizure prediction research con-
network dynamics that precede a seizure. Moreover, it tends               sistently relies on a narrow set of default configurations.
to couple the learned filters tightly to the noise characteristics        Approximately one-quarter of studies set the SOP at 30 min,
and sampling scheme of a specific dataset, thereby limiting               while another fifth adopt a 5-min SPH. Sensitivity and accu-
generalization to larger and more heterogeneous dataset such              racy dominate the performance metrics, whereas clinically
as Temple University Hospital EEG Corpus (TUH). Until                     meaningful measures—such as the FPR/h—appear in fewer
the field systematically benchmarks raw waveform-based,                   than half of the publications, and time-in-warning is reported
graph-aware, and Transformer-based models under unified                   only occasionally. Validation strategies also remain limited,
cross-patient evaluation protocols, this convolution-heavy                with most studies relying on single hold-out splits or leave-
paradigm continues to produce impressive in-lab accuracies                one-seizure-out protocols; cross-patient evaluation using
that do not translate reliably into patient-specific forecasts in         leave-one-patient-out is applied in only a small minority of
real-world settings.                                                      cases. These preferences often reflect practical constraints:

159834                                                                                                                                 VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


the 30-min/5-min window aligns with clinical routines                             to proof-of-concept experiments on static datasets and fail
and regulatory expectations; sensitivity and accuracy are                         to address the challenges of generalization when models
intuitive and widely accepted; and simple data partitioning                       are deployed across different electrode montages, wearable
methods are easier to implement, particularly in early-stage                      sensors, or out-of-hospital environments.
experiments or when datasets are limited.                                            Interpretability further compounds this issue. Despite
   Although these defaults support reproducibility and facil-                     its clinical relevance, only 11 studies apply explanation
itate direct comparisons, they also introduce several critical                    techniques such as LIME, SHAP, Integrated Gradients,
limitations. First, the use of a fixed 30-min SOP and 5-min                       or Grad-CAM to identify which channels, frequency bands,
SPH implicitly assumes a uniform prodromal duration and                           or time segments contribute to model decisions. Without
intervention window, overlooking patients whose seizures                          transparent interpretive feedback, clinicians are left unable
are preceded by only seconds of warning or who require                            to assess whether false alarms stem from artifacts, feature
extended lead time for treatment or caregiving logistics.                         biases, or true preictal signals, which undermines confidence
Second, segment-level sensitivity and accuracy may obscure                        in the system’s reliability.
the risk of alarm fatigue: a model that issues warnings every                        Translation from proof-of-concept to functional deploy-
10 min may achieve 99% sensitivity on imbalanced test                             ment on point-of-care or wearable platforms also remains
sets, yet remain clinically impractical due to excessive false                    rare. Few studies progress beyond offline evaluation to
alarms. Third, single hold-out validation fails to account                        on-device inference, and even fewer conduct prospective
for domain shifts caused by differences in EEG montages,                          real-time testing in clinical settings. This gap arises from
recording artifacts, or acquisition hardware, often resulting                     several interrelated challenges: deep learning models often
in inflated performance estimates that do not generalize to                       exceed the computational constraints of portable hardware;
new clinical settings or wearable platforms. Finally, the lack                    patient-specific variability necessitates continuous model
of uncertainty quantification and cost-sensitive metrics limits                   adaptation, which is difficult to implement on embedded
the adaptability of models to diverse clinical use cases, such                    systems; and integration with hospital information systems
as pediatric versus adult care or closed-loop stimulation                         or caregiver alert mechanisms introduces additional concerns
versus caregiver notification.                                                    around cybersecurity, data privacy, and interoperability.
   Continued reliance on fixed SOP/SPH configurations, lim-                          The ongoing dependence on heuristic postprocessing,
ited performance metrics, and simplistic validation protocols                     minimal use of interpretability tools, and lack of real-world
inflates reported accuracy, conceals the risk of alarm fatigue,                   deployment collectively hinder generalizability, reduce clini-
and weakens confidence in the generalizability of seizure                         cian trust, and prevent most seizure prediction systems from
prediction systems. To overcome these limitations, future                         advancing beyond in-silico prototypes into reliable, clinically
work prioritizes the use of variable, patient-specific windows;                   deployable early-warning solutions.
incorporates clinically meaningful evaluation criteria—
such as FPR/h, time-in-warning, and calibrated probability                        V. CONCLUSION
estimates; and validates models across patients, devices,                         This work presents the first quantitative survey of 149 EEG-
and clinical environments to reflect real-world variability.                      based seizure prediction studies published between 2018 and
Adopting leave-one-patient-out or external-dataset testing,                       May 2025. For each study, the datasets employed, preprocess-
integrating uncertainty estimates, and involving clinicians                       ing procedures, model architectures, validation protocols,
early in defining acceptable false-alarm thresholds further                       postprocessing strategies, and any claims related to inter-
supports the translation of promising laboratory models into                      pretability or deployment are systematically documented,
reliable bedside seizure-warning solutions.                                       thereby encompassing the entire pipeline from data acquisi-
                                                                                  tion to potential bedside application. The search methodology
E. DECISION REFINEMENT & CLINICAL TRANSLATION                                     and screening criteria are described in a step-by-step manner
Most epileptic seizure prediction pipelines continue to treat                     to facilitate reproducibility and allow other researchers to
the decision-refinement layer as an ancillary component                           replicate or extend the corpus.
rather than an integral part of the model. The dominant                              Based on this analysis, four actionable contributions are
practices—k-of-n majority voting, fixed confidence thresh-                        identified: these collectively characterize prevailing trends
olds, and simple moving-average filters—offer ease of                             and methodological advances in the field (Objective (i)) while
implementation but reduce to coarse, manual tuning of raw                         also highlighting the persistent limitations that continue to
prediction scores. These heuristic approaches disregard the                       hinder progress in seizure prediction research (Objective (ii)).
full probability distribution of model outputs, neglect tem-                         • 72.8% of dataset citations concentrate on the pediatric
poral context beyond short windows, and lack the flexibility                            CHB-MIT sEEG dataset, while fewer than 10% utilize
to adapt to baseline shifts induced by medication changes,                              high-density iEEG. This imbalance leads to overfit-
circadian rhythms, or electrode displacement. Only a limited                            ting on short, low-channel pediatric recordings and
number of studies explore more adaptive postprocessing                                  limits generalization to adult populations, high-channel
strategies, such as combining multiple techniques or applying                           configurations, and long-term monitoring scenarios,
dynamic thresholds. However, these efforts remain confined                              thereby constraining clinical translation.

VOLUME 13, 2025                                                                                                                            159835

                                          Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


  • The    prevailing convenience paradigm—characterized                     implicit compression with explicit, task-aware dimen-
     by sub 10-s epochs, a 30 to 60 min preictal window,                     sionality reduction. This allows for meaningful com-
     routine reliance on basic notch or band-pass filtering                  parisons that isolate true modeling improvements while
     for signal denoising, and interictal undersampling—                     balancing predictive accuracy, computational efficiency,
     facilitates experimentation and inflates in lab accuracy.               and interpretability.
     However, it also truncates long-range temporal depen-                 • Adopt clinically aligned evaluation protocols that
     dencies, induces a distribution shift from training to                  incorporate patient-specific splits, clinically meaning-
     deployment, and obscures the nature of lost predictive                  ful metrics (e.g., FPR/h, time-in-warning), and both
     information, thereby undermining both interpretability                  cross-patient and external-dataset validation. In addi-
     and real-world robustness.                                              tion, static postprocessing thresholds should be replaced
  • Model development remains dominated by convolution-                      with dynamic, risk-aware mechanisms. Interpretability
     and time-frequency-based architectures, while explo-                    should be embedded by design, and final systems should
     ration of more flexible alternatives such as GNN and                    be deployed on energy-efficient edge hardware with
     Transformer is still sparse. Dimensionality reduction is                prospective validation in both clinical and home settings.
     handled almost entirely implicitly, leaving researchers               Only through comprehensive reform can seizure prediction
     without explicit control over the information retained.            models be transformed from promising prototypes into
     Moreover, only a minority of studies benchmark their               reliable solutions for real-world clinical application.
     models against simple linear baselines, making it
     difficult to determine whether reported performance                 REFERENCES
     gains stem from genuine modeling advances or from                     [1] K. M. Fiest, K. M. Sauro, S. Wiebe, S. B. Patten, C.-S. Kwon, J. Dykeman,
     added architectural complexity and preprocessing effort.                  T. Pringsheim, D. L. Lorenzetti, and N. Jetté, ‘‘Prevalence and incidence
  • Experimental protocols disproportionately prioritize                       of epilepsy: A systematic review and meta-analysis of international stud-
                                                                               ies,’’ Neurology, vol. 88, no. 3, pp. 296–303, Jan. 2017. [Online]. Avail-
     convenience—favoring fixed 30-min SOP and 5-min                           able: https://www.neurology.org/doi/10.1212/WNL.0000000000003509
     SPH windows, as well as simplistic validation strategies              [2] E. Beghi et al., ‘‘Global, regional, and national burden of epilepsy, 1990–
     such as single hold-out or leave-one-seizure-out splits—                  2016: A systematic analysis for the global burden of disease study 2016,
                                                                               Lancet Neurol., vol. 18, no. 4, pp. 357–375, Apr. 2019. [Online]. Avail-
     over clinical realism. Postprocessing commonly relies                     able: https://linkinghub.elsevier.com/retrieve/pii/S147444221830454X
     on static, opaque heuristics such as fixed thresholds and             [3] R. S. Fisher, C. Acevedo, A. Arzimanoglou, A. Bogacz, J. H. Cross,
     k-of-n voting, offering limited interpretability. Trans-                  C. E. Elger, J. Engel, L. Forsgren, J. A. French, M. Glynn,
                                                                               D. C. Hesdorffer, B. I. Lee, G. W. Mathern, S. L. Moshé, E. Perucca,
     lation from proof-of-concept to bedside or wearable                       I. E. Scheffer, T. Tomson, M. Watanabe, and S. Wiebe, ‘‘ILAE official
     deployment remains exceedingly rare. As a result, mod-                    report: A practical clinical definition of epilepsy,’’ Epilepsia, vol. 55,
     els often fail to generalize, produce poorly calibrated                   no. 4, pp. 475–482, Apr. 2014. [Online]. Available: https://onlinelibrary.
                                                                               wiley.com/doi/10.1111/epi.12550
     alerts with high false-alarm and missed-seizure rates,                [4] J. J. Falco-Walter, I. E. Scheffer, and R. S. Fisher, ‘‘The new
     and erode clinician trust, ultimately hindering real-world                definition and classification of seizures and epilepsy,’’ Epilepsy Res.,
                                                                               vol. 139, pp. 73–79, Jan. 2018. [Online]. Available: https://linkinghub.
     adoption.
                                                                               elsevier.com/retrieve/pii/S0920121117303819
  To address these limitations (Objective (iii)),                          [5] T. N. Alotaiby, S. A. Alshebeili, F. M. Alotaibi, and S. R. Alrshoud,
we recommend that future research:                                             ‘‘Epileptic seizure prediction using CSP and LDA for scalp EEG signals,’’
                                                                               Comput. Intell. Neurosci., vol. 2017, pp. 1–11, Jan. 2017. [Online].
  • Assemble diverse and representative EEG datasets that
                                                                               Available: https://www.hindawi.com/journals/cin/2017/1240323/
     encompass both pediatric and adult populations, inte-                 [6] A. M. Pack, ‘‘Epilepsy overview and revised classification of
     grate high-density intracranial alongside scalp record-                   seizures and epilepsies,’’ Continuum Lifelong Learn. Neurol., vol. 25,
                                                                               no. 2, pp. 306–321, Apr. 2019. [Online]. Available: https://journals.
     ings, and capture a broad spectrum of clinical scenarios.                 lww.com/00132979-201904000-00004
     This approach mitigates the field’s current overreliance              [7] F. Mormann, R. G. Andrzejak, C. E. Elger, and K. Lehnertz, ‘‘Seizure pre-
     on the CHB-MIT benchmark and supports more robust                         diction: The long and winding road,’’ Brain, vol. 130, no. 2, pp. 314–333,
                                                                               Feb. 2007. [Online]. Available: https://academic.oup.com/brain/article-
     generalization.                                                           lookup/doi/10.1093/brain/awl241
  • Replace convenience-driven preprocessing with adap-                    [8] L. Kuhlmann, K. Lehnertz, M. P. Richardson, B. Schelter, and
     tive, multi-scale pipelines by evaluating varied epoch                    H. P. Zaveri, ‘‘Seizure prediction— Ready for a new era,’’ Nature Rev.
                                                                               Neurol., vol. 14, no. 10, pp. 618–630, Oct. 2018. [Online]. Available:
     lengths and prediction horizons, benchmarking denois-                     https://www.nature.com/articles/s41582-018-0055-2
     ing techniques under realistic deployment constraints,                [9] Y. Roy, H. Banville, I. Albuquerque, A. Gramfort, T. H. Falk,
     and addressing class imbalance through generative                         and J. Faubert, ‘‘Deep learning-based electroencephalography analysis:
                                                                               A systematic review,’’ J. Neural Eng., vol. 16, no. 5, Oct. 2019,
     augmentation or active resampling instead of simple                       Art. no. 051001. [Online]. Available: https://iopscience.iop.org/article/
     undersampling.                                                            10.1088/1741-2552/ab260c
  • Establish unified benchmarks that systematically pit                  [10] A. Van de Vel, K. Cuppens, B. Bonroy, M. Milosevic, K. Jansen,
                                                                               S. Van Huffel, B. Vanrumste, P. Cras, L. Lagae, and B. Ceulemans, ‘‘Non-
     CNN, RNN, Transformer, GNN, TCN, and other emerg-                         EEG seizure detection systems and potential SUDEP prevention: State of
     ing architectures against well-tuned linear baselines,                    the art,’’ Seizure, vol. 41, pp. 141–153, Oct. 2016. [Online]. Available:
     thereby propelling flexible, non-convolutional designs                    https://linkinghub.elsevier.com/retrieve/pii/S1059131116301145
                                                                          [11] D. L. Schomer, E. Niedermeyer, and F. H. L. da Silva, Niedermeyer’s
     beyond the prevailing time–frequency paradigm and                         Electroencephalography: Basic Principles, Clinical Applications, and
     mandating ablation experiments that contrast default                      Related Fields, 6th ed., Boston, MA, USA: Kluwer, 2011.

159836                                                                                                                                   VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


 [12] C. Mugruza-Vassallo, ‘‘Different regressors for linear modelling of             [28] Y. Gao, A. Liu, X. Cui, R. Qian, and X. Chen, ‘‘A general sample-
      ElectroEncephaloGraphic recordings in visual and auditory tasks,’’ in                weighted framework for epileptic seizure prediction,’’ Comput. Biol.
      Proc. IEEE 13th Int. Conf. Wearable Implant. Body Sensor Netw. (BSN),                Med., vol. 150, Nov. 2022, Art. no. 106169. [Online]. Available: https://
      Jun. 2016, pp. 260–265. [Online]. Available: http://ieeexplore.ieee.org/             linkinghub.elsevier.com/retrieve/pii/S0010482522008770
      document/7516270/                                                               [29] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and
 [13] C. Mugruza-Vassallo and D. Potter, ‘‘Context dependence signature,                   C. Fookes, ‘‘Deep learning for patient-independent epileptic
      stimulus properties and stimulus probability as predictors of ERP                    seizure prediction using scalp EEG signals,’’ IEEE Sensors J.,
      amplitude variability,’’ Frontiers Human Neurosci., vol. 13, p. 39,                  vol. 21, no. 7, pp. 9377–9388, Apr. 2021. [Online]. Available:
      Feb. 2019. [Online]. Available: https://www.frontiersin.org/article/10.              https://ieeexplore.ieee.org/document/9347465/
      3389/fnhum.2019.00039/full                                                      [30] S. Kannan, G. Premalatha, M. Jamuna Rani, D. Jayakumar, P. Senthil,
 [14] X. Zhang, X. Zhang, Q. Huang, and F. Chen, ‘‘A review of epilepsy                    S. Palanivelrajan, S. Devi, and K. Sahile, ‘‘Effective evaluation of
      detection and prediction methods based on EEG signal processing and                  medical images using artificial intelligence techniques,’’ Comput.
      deep learning,’’ Frontiers Neurosci., vol. 18, Nov. 2024, Art. no. 1468967.          Intell. Neurosci., vol. 2022, pp. 1–9, Aug. 2022. [Online]. Available:
 [15] W. T. Kerr, K. N. McFarlane, and G. Figueiredo Pucci, ‘‘The present                  https://www.hindawi.com/journals/cin/2022/8419308/
      and future of seizure detection, prediction, and forecasting with machine       [31] C. Cheng, B. You, Y. Liu, and Y. Dai, ‘‘Patient-specific method of sleep
      learning, including the future impact on clinical trials,’’ Frontiers                electroencephalography using wavelet packet transform and bi-LSTM for
      Neurol., vol. 15, Jul. 2024, Art. no. 1425490. [Online]. Available:                  epileptic seizure prediction,’’ Biomed. Signal Process. Control, vol. 70,
      https://www.frontiersin.org/articles/10.3389/fneur.2024.1425490/full                 Sep. 2021, Art. no. 102963.
 [16] M. Bandarabadi, J. Rasekhi, C. A. Teixeira, M. R. Karami, and                   [32] M. Jia, W. Liu, J. Duan, L. Chen, C. L. P. Chen, Q. Wang, and Z. Zhou,
      A. Dourado, ‘‘On the proper selection of preictal period for seizure                 ‘‘Efficient graph convolutional networks for seizure prediction using
      prediction,’’ Epilepsy Behav., vol. 46, pp. 158–166, May 2015.                       scalp EEG,’’ Frontiers Neurosci., vol. 16, Aug. 2022, Art. no. 967116.
      [Online]. Available: https://linkinghub.elsevier.com/retrieve/pii/S152550            [Online]. Available: https://www.frontiersin.org/articles/10.3389/fnins.
      5015001158                                                                           2022.967116/full
 [17] P. Handa, Lavanya, N. Goel, and N. Garg, ‘‘Software advancements                [33] W. Qiao, X. Bi, L. Han, and Y. Zhang, ‘‘Epilepsy prediction
      in automatic epilepsy diagnosis and seizure detection: 10-year review,’’             and detection using attention-CssCDBN with dual-task learning,’’
      Artif. Intell. Rev., vol. 57, no. 7, p. 181, Jun. 2024. [Online]. Available:         Sensors, vol. 25, no. 1, p. 51, Dec. 2024. [Online]. Available:
      https://link.springer.com/10.1007/s10462-024-10799-y                                 https://www.mdpi.com/1424-8220/25/1/51
 [18] S. Shafiezadeh, G. Marco Duma, M. Pozza, and A. Testolin, ‘‘A system-           [34] S. Hu, J. Liu, R. Yang, Y. Wang, A. Wang, K. Li, W. Liu, and
      atic review of cross-patient approaches for EEG epileptic seizure predic-            C. Yang, ‘‘Exploring the applicability of transfer learning and feature
      tion,’’ J. Neural Eng., vol. 21, no. 6, Dec. 2024, Art. no. 061004. [Online].        engineering in epilepsy prediction using hybrid transformer model,’’
      Available: https://iopscience.iop.org/article/10.1088/1741-2552/ad9682               IEEE Trans. Neural Syst. Rehabil. Eng., vol. 31, pp. 1321–1332,
 [19] J. S. Ong, S. N. Wong, A. Arulsamy, J. L. Watterson, and M. F. Shaikh,               2023. [Online]. Available: https://ieeexplore.ieee.org/document/
      ‘‘Medical technology: A systematic review on medical devices utilized                10046136/
      for epilepsy prediction and management,’’ Current Neuropharmacol-               [35] A. Affes, A. Mdhaffar, C. Triki, M. Jmaiel, and B. Freisleben,
      ogy, vol. 20, no. 5, pp. 950–964, May 2022. [Online]. Available:                     ‘‘Personalized attention-based EEG channel selection for epilep-
      https://www.eurekaselect.com/197799/article                                          tic seizure prediction,’’ Expert Syst. Appl., vol. 206, Nov. 2022,
 [20] M. Saeidi, W. Karwowski, F. V. Farahani, K. Fiok, R. Taiar, P. A.                    Art. no. 117733. [Online]. Available: https://linkinghub.elsevier.com/
      Hancock, and A. Al-Juaid, ‘‘Neural decoding of EEG signals with                      retrieve/pii/S0957417422010144
      machine learning: A systematic review,’’ Brain Sci., vol. 11, no. 11,           [36] Q. Lan, B. Yao, and T. Qing, ‘‘Epileptic seizure prediction using convolu-
      p. 1525, Nov. 2021. [Online]. Available: https://www.mdpi.com/2076-                  tional neural networks and fusion features on scalp EEG signals,’’ IEICE
      3425/11/11/1525                                                                      Trans. Inf. Syst., vol. 106, no. 5, pp. 821–823, May 2023. [Online]. Avail-
 [21] A.-M. Tautan, A.-G. Andrei, C. L. Smeralda, G. Vatti, S. Rossi, and                  able: https://www.jstage.jst.go.jp/article/transinf/E106.D/5/E106.D2022
      B. Ionescu, ‘‘Unsupervised learning from EEG data for epilepsy: A                    DLL0002/article
      systematic literature review,’’ Artif. Intell. Med., vol. 162, Apr. 2025,       [37] Y. A. Saadoon, M. Khalil, and D. Battikh, ‘‘Predicting epileptic seizures
      Art. no. 103095.                                                                     using EfficientNet-B0 and SVMs: A deep learning methodology for EEG
 [22] S. Wong, A. Simmons, J. Rivera-Villicana, S. Barnett, S. Sivathamboo,                analysis,’’ Bioengineering, vol. 12, no. 2, p. 109, Jan. 2025. [Online].
      P. Perucca, Z. Ge, P. Kwan, L. Kuhlmann, R. Vasa, K. Mouzakis, and                   Available: https://www.mdpi.com/2306-5354/12/2/109
      T. J. O’Brien, ‘‘EEG datasets for seizure detection and prediction—             [38] H. Daoud and M. A. Bayoumi, ‘‘Efficient epileptic seizure prediction
      A review,’’ Epilepsia Open, vol. 8, no. 2, pp. 252–267, Jun. 2023.                   based on deep learning,’’ IEEE Trans. Biomed. Circuits Syst., vol. 13,
      [Online]. Available: https://onlinelibrary.wiley.com/doi/10.1002/epi4.               no. 5, pp. 804–813, Oct. 2019. [Online]. Available: https://ieeexplore.
      12704                                                                                ieee.org/document/8765420/
 [23] M. J. Page et al., ‘‘The PRISMA 2020 statement: An updated guideline for        [39] X. Liu, C. Li, X. Lou, H. Kong, X. Li, Z. Li, and L. Zhong, ‘‘Epilep-
      reporting systematic reviews,’’ BMJ, vol. 372, p. 71, Mar. 2021. [Online].           tic seizure prediction based on EEG using pseudo-three-dimensional
      Available: https://www.bmj.com/lookup/doi/10.1136/bmj.n71                            CNN,’’ Frontiers Neuroinform., vol. 18, Mar. 2024, Art. no. 1354436.
 [24] K. M. Tsiouris, V. C. Pezoulas, M. Zervakis, S. Konitsiotis,                         [Online]. Available: https://www.frontiersin.org/articles/10.3389/fninf.
      D. D. Koutsouris, and D. I. Fotiadis, ‘‘A long short-term memory                     2024.1354436/full
      deep learning network for the prediction of epileptic seizures using EEG        [40] S. Yuan, K. Yan, S. Wang, J.-X. Liu, and J. Wang, ‘‘EEG-based seizure
      signals,’’ Comput. Biol. Med., vol. 99, pp. 24–37, Aug. 2018. [Online].              prediction using hybrid DenseNet–ViT network with attention fusion,’’
      Available: https://linkinghub.elsevier.com/retrieve/pii/S001048251830                Brain Sci., vol. 14, no. 8, p. 839, Aug. 2024. [Online]. Available:
      132X                                                                                 https://www.mdpi.com/2076-3425/14/8/839
 [25] I. Jemal, N. Mezghani, L. Abou-Abbas, and A. Mitiche, ‘‘An interpretable        [41] J. Yan, J. Li, H. Xu, Y. Yu, and T. Xu, ‘‘Seizure prediction based on
      deep learning classifier for epileptic seizure prediction using EEG data,’’          transformer using scalp electroencephalogram,’’ Appl. Sci., vol. 12, no. 9,
      IEEE Access, vol. 10, pp. 60141–60150, 2022. [Online]. Available:                    p. 4158, Apr. 2022. [Online]. Available: https://www.mdpi.com/2076-
      https://ieeexplore.ieee.org/document/9777979/                                        3417/12/9/4158
 [26] S. Muhammad Usman, S. Khalid, and M. H. Aslam, ‘‘Epileptic seizures             [42] R. I. Halawa, S. M. Youssef, and M. N. Elagamy, ‘‘An efficient hybrid
      prediction using deep learning techniques,’’ IEEE Access, vol. 8,                    model for patient-independent seizure prediction using deep learning,’’
      pp. 39998–40007, 2020. [Online]. Available: https://ieeexplore.ieee.org/             Appl. Sci., vol. 12, no. 11, p. 5516, May 2022. [Online]. Available:
      document/9016244/                                                                    https://www.mdpi.com/2076-3417/12/11/5516
 [27] A. Ghosh and D. Dey, ‘‘Digital twin for EEG seizure prediction using            [43] Y. Zhang, T. Xiao, Z. Wang, H. Lv, S. Wang, H. Feng, S. Zhao,
      time reassigned multisynchrosqueezing transform-based CNN-BiLSTM-                    and Y. Zhao, ‘‘Hybrid network for patient-specific seizure prediction
      attention mechanism model,’’ Biomed. Phys. Eng. Exp., vol. 11, no. 1,                from EEG data,’’ Int. J. Neural Syst., vol. 33, no. 11, Nov. 2023,
      Jan. 2025, Art. no. 015034. [Online]. Available: https://iopscience.iop.             Art. no. 2350056. [Online]. Available: https://www.worldscientific.com/
      org/article/10.1088/2057-1976/ad992c                                                 doi/10.1142/S0129065723500569

VOLUME 13, 2025                                                                                                                                              159837

                                                      Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


[44] Y. P. Singh and D. K. Lobiyal, ‘‘Automatic prediction of epilep-                 [61] K. Singh and J. Malhotra, ‘‘Two-layer LSTM network-based prediction
     tic seizure using hybrid deep ResNet-LSTM model,’’ AI Com-                            of epileptic seizures using EEG spectral features,’’ Complex Intell.
     mun., vol. 36, no. 1, pp. 57–72, Feb. 2023. [Online]. Available:                      Syst., vol. 8, no. 3, pp. 2405–2418, Jun. 2022. [Online]. Available:
     https://journals.sagepub.com/doi/full/10.3233/AIC-220177                              https://link.springer.com/10.1007/s40747-021-00627-z
[45] M. M. Qureshi and M. Kaleem, ‘‘EEG-based seizure prediction                      [62] S. Parveen, S. A. S. Kumar, P. MohanRaj, K. Jabakumar, and
     with machine learning,’’ Signal, Image Video Process.,                                R. S. Ganesh, ‘‘Design of a dense layered network model for epilep-
     vol. 17, no. 4, pp. 1543–1554, Jun. 2023. [Online]. Available:                        tic seizures prediction with feature representation,’’ Int. J. Adv.
     https://link.springer.com/10.1007/s11760-022-02363-4                                  Comput. Sci. Appl., vol. 13, no. 10, pp. 218–223, 2022. [Online].
[46] B. Sun, J.-J. Lv, L.-G. Rui, Y.-X. Yang, Y.-G. Chen, C. Ma, and Z.-K.                 Available: http://thesai.org/Publications/ViewPaper?Volume=13&Issue=
     Gao, ‘‘Seizure prediction in scalp EEG based channel attention dual-                  10&Code=IJACSA&SerialNo=27
     input convolutional neural network,’’ Phys. A, Stat. Mech. Appl., vol. 584,      [63] K. Singh and J. Malhotra, ‘‘Predicting epileptic seizures from EEG
     Dec. 2021, Art. no. 126376. [Online]. Available: https://linkinghub.                  spectral band features using convolutional neural network,’’ Wireless
     elsevier.com/retrieve/pii/S037843712100649X                                           Pers. Commun., vol. 125, no. 3, pp. 2667–2684, Aug. 2022. [Online].
[47] X. Wu, Z. Yang, T. Zhang, L. Zhang, and L. Qiao,                                      Available: https://link.springer.com/10.1007/s11277-022-09678-y
     ‘‘An end-to-end seizure prediction approach using long                           [64] I. Ahmad, M. Zhu, Z. Liu, M. Shabaz, I. Ullah, M. C. F. Tong, A.
     short-term memory network,’’ Frontiers Human Neurosci.,                               Sambas, L. Men, Y. Chen, and S. Chen, ‘‘Multi-feature fusion-based
     vol. 17, May 2023, Art. no. 1187794. [Online]. Available:                             convolutional neural networks for EEG epileptic seizure prediction
     https://www.frontiersin.org/articles/10.3389/fnhum.2023.1187794/full                  in consumer Internet of Things,’’ IEEE Trans. Consum. Electron.,
[48] R. Jana and I. Mukherjee, ‘‘Deep learning based efficient epileptic                   vol. 70, no. 3, pp. 5631–5643, Aug. 2024. [Online]. Available:
     seizure prediction with EEG channel optimization,’’ Biomed. Signal                    https://ieeexplore.ieee.org/document/10423813/
     Process. Control, vol. 68, Jul. 2021, Art. no. 102767. [Online]. Available:      [65] Z. Kuang, S. Liu, J. Zhao, L. Wang, and Y. Li, ‘‘Epilepsy EEG seizure
     https://linkinghub.elsevier.com/retrieve/pii/S1746809421003645                        prediction based on the combination of graph convolutional neural
[49] D. Kalita, S. Dash, and K. B. Mirza, ‘‘EpiNET: An optimized, resource                 network combined with long- and short-term memory cell network,’’
     efficient deep GRU-LSTM network for epileptic seizure prediction,’’                   Appl. Sci., vol. 14, no. 24, p. 11569, Dec. 2024. [Online]. Available:
     Biomed. Eng., Appl., Basis Commun., vol. 36, no. 4, Aug. 2024,                        https://www.mdpi.com/2076-3417/14/24/11569
     Art. no. 2450021.                                                                [66] X. Lu, A. Wen, L. Sun, H. Wang, Y. Guo, and Y. Ren, ‘‘An epileptic
[50] X. Xu, Y. Zhang, R. Zhang, and T. Xu, ‘‘Patient-specific method for                   seizure prediction method based on CBAM-3D CNN-LSTM model,’’
     predicting epileptic seizures based on DRSN-GRU,’’ Biomed. Signal                     IEEE J. Transl. Eng. Health Med., vol. 11, pp. 417–423, 2023. [Online].
     Process. Control, vol. 81, Mar. 2023, Art. no. 104449.                                Available: https://ieeexplore.ieee.org/document/10164022/
[51] Y. Gao, X. Chen, A. Liu, D. Liang, L. Wu, R. Qian, H. Xie, and Y. Zhang,         [67] S. Toraman, ‘‘Preictal and interictal recognition for epileptic seizure
     ‘‘Pediatric seizure prediction in scalp EEG using a multi-scale neural                prediction using pre-trained 2D-CNN models,’’ Traitement Du Sig-
     network with dilated convolutions,’’ IEEE J. Transl. Eng. Health Med.,                nal, vol. 37, no. 6, pp. 1045–1054, Dec. 2020. [Online]. Available:
     vol. 10, pp. 1–9, 2022. [Online]. Available: https://ieeexplore.ieee.org/             http://www.iieta.org/journals/ts/paper/10.18280/ts.370617
     document/9684436/                                                                [68] Z. Altaf, M. A. Unar, S. Narejo, M. A. Zaki, and N.-U-Din,
[52] Y. Xu, J. Yang, and M. Sawan, ‘‘Multichannel synthetic preictal EEG                   ‘‘Generalized epileptic seizure prediction using machine learning
     signals to enhance the prediction of epileptic seizures,’’ IEEE Trans.                method,’’ Int. J. Adv. Comput. Sci. Appl., vol. 14, no. 1, pp. 502–
     Biomed. Eng., vol. 69, no. 11, pp. 3516–3525, Nov. 2022. [Online].                    510, 2023. [Online]. Available: http://thesai.org/Publications/ViewPaper?
     Available: https://ieeexplore.ieee.org/document/9767764/                              Volume=14&Issue=1&Code=IJACSA&SerialNo=55
[53] S. Ryu and I. Joe, ‘‘A hybrid DenseNet-LSTM model for epileptic seizure          [69] Y. Gao, B. Gao, Q. Chen, J. Liu, and Y. Zhang, ‘‘Deep convolutional neu-
     prediction,’’ Appl. Sci., vol. 11, no. 16, p. 7661, Aug. 2021. [Online].              ral network-based epileptic electroencephalogram (EEG) signal classifi-
     Available: https://www.mdpi.com/2076-3417/11/16/7661                                  cation,’’ Frontiers Neurol., vol. 11, p. 375, May 2020. [Online]. Available:
[54] T. Xu, Y. Wu, Y. Tang, W. Zhang, and Z. Cui, ‘‘Dynamic                                https://www.frontiersin.org/article/10.3389/fneur.2020.00375/full
     functional connectivity neural network for epileptic seizure                     [70] A. Esmaeilpour, S. S. Tabarestani, and A. Niazi, ‘‘Deep learning-
     prediction using multi-channel EEG signal,’’ IEEE Signal                              based seizure prediction using EEG signals: A comparative anal-
     Process. Lett., vol. 31, pp. 1499–1503, 2024. [Online]. Available:                    ysis of classification methods on the CHB-MIT dataset,’’ Eng.
     https://ieeexplore.ieee.org/document/10529534/                                        Rep., vol. 6, no. 11, p. 12918, Nov. 2024. [Online]. Available:
[55] P. Koutsouvelis, B. Chybowski, A. Gonzalez-Sulser, S. Abdullateef,                    https://onlinelibrary.wiley.com/doi/10.1002/eng2.12918
     and J. Escudero, ‘‘Preictal period optimization for deep learning-               [71] F. E. Ibrahim, H. M. Emara, W. El-Shafai, M. Elwekeil, M. Rihan,
     based epileptic seizure prediction,’’ J. Neural Eng., vol. 21, no. 6,                 I. M. Eldokany, T. E. Taha, A. S. El-Fishawy, E. M. El-Rabaie, E. Abdel-
     Dec. 2024, Art. no. 066040. [Online]. Available: https://iopscience.                  latef, and F. E. A. El-Samie, ‘‘Deep-learning-based seizure detection and
     iop.org/article/10.1088/1741-2552/ad9ad0                                              prediction from electroencephalography signals,’’ Int. J. Numer. Methods
[56] D. Liang, A. Liu, L. Wu, C. Li, R. Qian, R. K. Ward, and X. Chen,                     Biomed. Eng., vol. 38, no. 6, p. 3573, Jun. 2022. [Online]. Available:
     ‘‘Semisupervised seizure prediction in scalp EEG using consistency reg-               https://onlinelibrary.wiley.com/doi/10.1002/cnm.3573
     ularization,’’ J. Healthcare Eng., vol. 2022, pp. 1–10, Jan. 2022. [Online].     [72] M. H. Aslam, S. M. Usman, S. Khalid, A. Anwar, R. Alroobaea,
     Available: https://www.hindawi.com/journals/jhe/2022/1573076/                         S. Hussain, J. Almotiri, S. S. Ullah, and A. Yasin, ‘‘Classification of EEG
[57] Y. Li, Y. Liu, Y.-Z. Guo, X.-F. Liao, B. Hu, and T. Yu, ‘‘Spatio-temporal-            signals for prediction of epileptic seizures,’’ Appl. Sci., vol. 12, no. 14,
     spectral hierarchical graph convolutional network with semisupervised                 p. 7251, Jul. 2022. [Online]. Available: https://www.mdpi.com/2076-
     active learning for patient-specific seizure prediction,’’ IEEE Trans.                3417/12/14/7251
     Cybern., vol. 52, no. 11, pp. 12189–12204, Nov. 2022. [Online].                  [73] I. Assali, A. Ghazi Blaiech, A. Ben Abdallah, K. Ben Khalifa, M.
     Available: https://ieeexplore.ieee.org/document/9440862/                              Carrère, and M. Hédi Bedoui, ‘‘CNN-based classification of epileptic
[58] S. Toraman, ‘‘Automatic recognition of preictal and interictal                        states for seizure prediction using combined temporal and spectral
     EEG signals using 1D-capsule networks,’’ Comput. Electr.                              features,’’ Biomed. Signal Process. Control, vol. 82, Apr. 2023,
     Eng., vol. 91, May 2021, Art. no. 107033. [Online]. Available:                        Art. no. 104519. [Online]. Available: https://linkinghub.elsevier.com/
     https://linkinghub.elsevier.com/retrieve/pii/S0045790621000550                        retrieve/pii/S1746809422009739
[59] R. R. Borhade, S. S. Barekar, S. N. Ohatkar, P. K. Mathurkar,                    [74] E. Abdellatef, H. M. Emara, M. R. Shoaib, F. E. Ibrahim, M. Elwekeil,
     R. H. Borhade, and P. M. Bangare, ‘‘ResneXt-leNet: A hybrid                           W. El-Shafai, T. E. Taha, A. S. El-Fishawy, E.-S.-M. El-Rabaie,
     deep learning for epileptic seizure prediction,’’ Intell. Decis. Tech-                I. M. Eldokany, and F. E. Abd El-Samie, ‘‘Automated diagnosis of EEG
     nol., vol. 18, no. 3, pp. 1675–1693, Sep. 2024. [Online]. Available:                  abnormalities with different classification techniques,’’ Med. Biol. Eng.
     https://journals.sagepub.com/doi/full/10.3233/IDT-240923                              Comput., vol. 61, no. 12, pp. 3363–3385, Dec. 2023. [Online]. Available:
[60] X. Yang, L. Liu, Z. Li, Y. Xia, Z. Fan, and J. Zhou, ‘‘Semi-supervised                https://link.springer.com/10.1007/s11517-023-02843-w
     seizure prediction model combining generative adversarial networks               [75] P. He, L. Wang, Y. Cui, R. Wang, and D. Wu, ‘‘Unsupervised feature
     and long short-term memory networks,’’ Appl. Sci., vol. 13, no. 21,                   learning based on autoencoder for epileptic seizures prediction,’’ Appl.
     p. 11631, Oct. 2023. [Online]. Available: https://www.mdpi.com/2076-                  Intell., vol. 53, no. 18, pp. 20766–20784, Sep. 2023. [Online]. Available:
     3417/13/21/11631                                                                      https://link.springer.com/10.1007/s10489-023-04582-9

159838                                                                                                                                                VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


 [76] B. Feizbakhsh and H. Omranpour, ‘‘Cluster-based phase space density            [92] L. Lu, F. Zhang, Y. Wu, S. Ma, X. Zhang, and G. Ni, ‘‘A multi-
      feature in multichannel scalp EEG for seizure prediction by deep                    frame network model for predicting seizure based on sEEG and iEEG
      learning,’’ Biomed. Signal Process. Control, vol. 86, Sep. 2023,                    data,’’ Frontiers Comput. Neurosci., vol. 16, Nov. 2022, Art. no. 1059565.
      Art. no. 105276. [Online]. Available: https://linkinghub.elsevier.com/              [Online]. Available: https://www.frontiersin.org/articles/10.3389/fncom.
      retrieve/pii/S1746809423007097                                                      2022.1059565/full
 [77] T. Meyer, C. Shultz, N. Dehak, L. Moro-Velázquez, and P. Irazoqui,             [93] S. Shi and W. Liu, ‘‘B2-ViT Net: Broad vision transformer network
      ‘‘Time scale network: An efficient shallow neural network for time                  with broad attention for seizure prediction,’’ IEEE Trans. Neural
      series data in biomedical applications,’’ IEEE J. Sel. Topics Signal                Syst. Rehabil. Eng., vol. 32, pp. 178–188, 2024. [Online]. Available:
      Process., vol. 19, no. 1, pp. 129–139, Jan. 2025. [Online]. Available:              https://ieeexplore.ieee.org/document/10373959/
      https://ieeexplore.ieee.org/document/10637669/                                 [94] C.-L. Liu, B. Xiao, W.-H. Hsaio, and V. S. Tseng, ‘‘Epileptic
 [78] B. C. Rebello, A. R. G. Ramirez, F. Heredia-Negron, and A. Roche-Lima,              seizure prediction with multi-view convolutional neural networks,’’
      ‘‘A machine learning-based approach to epileptic seizure prediction using           IEEE Access, vol. 7, pp. 170352–170361, 2019. [Online]. Available:
      electroencephalographic signals,’’ J. Eng. Res., vol. 2, no. 8, pp. 2–9,            https://ieeexplore.ieee.org/document/8910555/
      May 2022. [Online]. Available: https://www.atenaeditora.com.br/post-           [95] Y. Zhao, C. Li, X. Liu, R. Qian, R. Song, and X. Chen,
      artigo/65340                                                                        ‘‘Patient-specific seizure prediction via adder network and
 [79] J. Liao, H. Li, C. Zhan, and F. Yang, ‘‘Construction of an epileptic                supervised contrastive learning,’’ IEEE Trans. Neural Syst.
      seizure prediction model using a semi-supervised method of generative               Rehabil. Eng., vol. 30, pp. 1536–1547, 2022. [Online]. Available:
      adversarial and long short term memory network combined with                        https://ieeexplore.ieee.org/document/9787538/
      Stockwell transform],’’ J. Southern Med. Univ., vol. 43, no. 1, pp. 17–28,     [96] C. Li, Y. Zhao, R. Song, X. Liu, R. Qian, and X. Chen, ‘‘Patient-
      Jan. 2023.                                                                          specific seizure prediction from electroencephalogram signal via mul-
 [80] W. Feng, Y. Zhao, H. Peng, C. Nie, H. Lv, S. Wang, and H. Feng,                     tichannel feedback capsule network,’’ IEEE Trans. Cognit. Develop.
      ‘‘FusionXNet: Enhancing EEG-based seizure prediction with inte-                     Syst., vol. 15, no. 3, pp. 1360–1370, Sep. 2023. [Online]. Available:
      grated convolutional and transformer architectures,’’ J. Neural Eng.,               https://ieeexplore.ieee.org/document/9911679/
      vol. 22, no. 2, Apr. 2025, Art. no. 026067. [Online]. Available:               [97] G. Yang, D. Long, K. Wang, S. Xia, and J. Zou, ‘‘Epileptic seizure
      https://iopscience.iop.org/article/10.1088/1741-2552/adce33                         prediction method based on transition network data augmentation and
 [81] A. A. Shaik Gadda, D. Vedantham, J. Thomas, Y. Rajamanickam,                        fuzzy granular recurrence plot,’’ Biomed. Signal Process. Control,
      R. N. Menon, and J. F. Agastinose Ronickom, ‘‘Optimization of pre-                  vol. 107, Sep. 2025, Art. no. 107837. [Online]. Available: https://
      ictal interval time period for epileptic seizure prediction using temporal          linkinghub.elsevier.com/retrieve/pii/S1746809425003489
      and frequency features,’’ in Caring is Sharing–Exploiting the Value in         [98] S. Liu, J. Wang, S. Li, and L. Cai, ‘‘Multi-dimensional hybrid bilinear
      Data for Health and Innovation (Studies in Health Technology and                    CNN-LSTM models for epileptic seizure detection and prediction using
      Informatics), M. Hägglund, Ed., Amsterdam, The Netherlands: IOS                     EEG signals,’’ J. Neural Eng., vol. 21, no. 6, Dec. 2024, Art. no. 066045.
      Press, 2023. [Online]. Available: https://ebooks.iospress.nl/doi/10.3233/           [Online]. Available: https://iopscience.iop.org/article/10.1088/1741-
      SHTI230109                                                                          2552/ada0e5
                                                                                     [99] I. Andrade, C. Teixeira, and M. Pinto, ‘‘On the performance of
 [82] H. Ma, Y. Wu, Y. Tang, R. Chen, T. Xu, and W. Zhang, ‘‘Parallel
                                                                                          seizure prediction machine learning methods across different
      dual-branch fusion network for epileptic seizure prediction,’’ Comput.
                                                                                          databases: The sample and alarm-based perspectives,’’ Frontiers
      Biol. Med., vol. 176, Jun. 2024, Art. no. 108565. [Online]. Available:
                                                                                          Neurosci., vol. 18, Jul. 2024, Art. no. 1417748. [Online]. Available:
      https://linkinghub.elsevier.com/retrieve/pii/S0010482524006498
                                                                                          https://www.frontiersin.org/articles/10.3389/fnins.2024.1417748/full
 [83] U. Mohammad and F. Saeed, ‘‘Robustness of ML-based seizure
                                                                                    [100] R. Hussein, S. Lee, R. Ward, and M. J. McKeown, ‘‘Semi-dilated
      prediction using noisy EEG data from limited channels,’’ in Proc.
                                                                                          convolutional neural networks for epileptic seizure prediction,’’ Neu-
      20th Int. Conf. Distrib. Comput. Smart Syst. Internet Things
                                                                                          ral Netw., vol. 139, pp. 212–222, Jul. 2021. [Online]. Available:
      (DCOSS-IoT), Apr. 2024, pp. 620–626. [Online]. Available:
                                                                                          https://linkinghub.elsevier.com/retrieve/pii/S0893608021000885
      https://ieeexplore.ieee.org/document/10621571/                                [101] S. Zhao, J. Yang, and M. Sawan, ‘‘Energy-efficient neural network
 [84] B. Cherouati, ‘‘Patient specific channel optimization using entropy                 for epileptic seizure prediction,’’ IEEE Trans. Biomed. Eng.,
      and CNN deep learning for epileptic seizure prediction,’’ Przegląd                  vol. 69, no. 1, pp. 401–411, Jan. 2022. [Online]. Available:
      Elektrotechniczny, vol. 1, no. 7, pp. 108–112, Jul. 2023. [Online].                 https://ieeexplore.ieee.org/document/9479737/
      Available: https://sigma-not.pl/publikacja-144166-2023-7.html                 [102] J. S. Ra, T. Li, and Y. Li, ‘‘Epileptic seizure prediction based on
 [85] A. Bhattacharya, T. Baweja, and S. P. K. Karri, ‘‘Epileptic seizure                 synchroextracting transform and sparse representation,’’ IEEE
      prediction using deep transformer model,’’ Int. J. Neural Syst., vol. 32,           Access, vol. 12, pp. 187684–187695, 2024. [Online]. Available:
      no. 2, Feb. 2022, Art. no. 2150058.                                                 https://ieeexplore.ieee.org/document/10788676/
 [86] S. Muhammad Usman, S. Khalid, and S. Bashir, ‘‘A deep learning based          [103] J. Qin, Z. Liu, J. Zhuang, and F. Liu, ‘‘Dual-modality transformer
      ensemble learning method for epileptic seizure prediction,’’ Comput.                with time series imaging for robust epileptic seizure prediction,’’
      Biol. Med., vol. 136, Sep. 2021, Art. no. 104710. [Online]. Available:              Appl. Sci., vol. 15, no. 3, p. 1538, Feb. 2025. [Online]. Available:
      https://linkinghub.elsevier.com/retrieve/pii/S0010482521005047                      https://www.mdpi.com/2076-3417/15/3/1538
 [87] Y. Gao, A. Liu, L. Wang, R. Qian, and X. Chen, ‘‘A self-                      [104] L. Guo, T. Yu, S. Zhao, X. Li, X. Liao, and Y. Li, ‘‘CLEP:
      interpretable deep learning model for seizure prediction using a                    Contrastive learning for epileptic seizure prediction using a
      multi-scale prototypical part network,’’ IEEE Trans. Neural Syst.                   spatio-temporal-spectral network,’’ IEEE Trans. Neural Syst.
      Rehabil. Eng., vol. 31, pp. 1847–1856, 2023. [Online]. Available:                   Rehabil. Eng., vol. 31, pp. 3915–3926, 2023. [Online]. Available:
      https://ieeexplore.ieee.org/document/10078917/                                      https://ieeexplore.ieee.org/document/10272683/
 [88] N. Qi, Y. Piao, P. Yu, and B. Tan, ‘‘Predicting epileptic seizures based on   [105] S. Shafiezadeh, G. M. Duma, G. Mento, A. Danieli, L. Antoniazzi,
      EEG signals using spatial depth features of a 3D-2D hybrid CNN,’’ Med.              F. Del Popolo Cristaldi, P. Bonanni, and A. Testolin, ‘‘Calibrating deep
      Biol. Eng. Comput., vol. 61, no. 7, pp. 1845–1856, Jul. 2023. [Online].             learning classifiers for patient-independent electroencephalogram seizure
      Available: https://link.springer.com/10.1007/s11517-023-02792-4                     forecasting,’’ Sensors, vol. 24, no. 9, p. 2863, Apr. 2024. [Online].
 [89] C. Li, C. Shao, R. Song, G. Xu, X. Liu, R. Qian, and X. Chen, ‘‘Spatio-             Available: https://www.mdpi.com/1424-8220/24/9/2863
      temporal MLP network for seizure prediction using EEG signals,’’              [106] S. Shafiezadeh, G. M. Duma, G. Mento, A. Danieli, L. Antoniazzi,
      Measurement, vol. 206, Jan. 2023, Art. no. 112278. [Online]. Available:             F. Del Popolo Cristaldi, P. Bonanni, and A. Testolin, ‘‘Methodological
      https://linkinghub.elsevier.com/retrieve/pii/S0263224122014749                      issues in evaluating machine learning models for EEG seizure prediction:
 [90] D. Liang, A. Liu, C. Li, J. Liu, and X. Chen, ‘‘A novel consistency-                Good cross-validation accuracy does not guarantee generalization to
      based training strategy for seizure prediction,’’ J. Neurosci.                      new patients,’’ Appl. Sci., vol. 13, no. 7, p. 4262, Mar. 2023. [Online].
      Methods, vol. 372, Apr. 2022, Art. no. 109557. [Online]. Available:                 Available: https://www.mdpi.com/2076-3417/13/7/4262
      https://linkinghub.elsevier.com/retrieve/pii/S016502702200084X                [107] F. Asharindavida, M. Shamim Hossain, A. Thacham, H. Khammari,
 [91] C. Shao, C. Li, R. Song, X. Liu, R. Qian, and X. Chen, ‘‘Machine                    I. Ahmed, F. Alraddady, and M. Masud, ‘‘A forecasting tool for prediction
      unlearning for seizure prediction,’’ IEEE Trans. Cognit. Develop.                   of epileptic seizures using a machine learning approach,’’ Concurrency
      Syst., vol. 16, no. 6, pp. 1969–1981, Dec. 2024. [Online]. Available:               Comput., Pract. Exper., vol. 32, no. 1, p. 5111, Jan. 2020. [Online].
      https://ieeexplore.ieee.org/document/10517285/                                      Available: https://onlinelibrary.wiley.com/doi/10.1002/cpe.5111

VOLUME 13, 2025                                                                                                                                            159839

                                                      Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


[108] K. Rasheed, J. Qadir, T. J. O’Brien, L. Kuhlmann, and A. Razi, ‘‘A            [123] A. Pandey, S. K. Singh, S. S. Udmale, and K. K. Shukla,
      generative model to synthesize EEG data for epileptic seizure prediction,’’         ‘‘An intelligent optimized deep learning model to achieve
      IEEE Trans. Neural Syst. Rehabil. Eng., vol. 29, pp. 2322–2332,                     early prediction of epileptic seizures,’’ Biomed. Signal Process.
      2021. [Online]. Available: https://ieeexplore.ieee.org/document/                    Control, vol. 84, Jul. 2023, Art. no. 104798. [Online]. Available:
      9599660/                                                                            https://linkinghub.elsevier.com/retrieve/pii/S1746809423002318
[109] H. Chen, T. Ji, X. Zhan, X. Liu, G. Yu, W. Wang, Y. Jiang,                    [124] Z. Georgis-Yap, M. R. Popovic, and S. S. Khan, ‘‘Supervised and
      and X.-H. Zhou, ‘‘An explainable statistical method for seizure                     unsupervised deep learning approaches for EEG seizure prediction,’’ J.
      prediction using brain functional connectivity from EEG,’’ Comput.                  Healthcare Informat. Res., vol. 8, no. 2, pp. 286–312, Jun. 2024. [Online].
      Intell. Neurosci., vol. 2022, pp. 1–8, Dec. 2022. [Online]. Available:              Available: https://link.springer.com/10.1007/s41666-024-00160-x
      https://www.hindawi.com/journals/cin/2022/2183562/                            [125] L. Xia, R. Wang, H. Ye, B. Jiang, G. Li, C. Ma, and Z. Gao, ‘‘Hybrid
[110] S. Rao, M. Liu, Y. Huang, H. Yang, J. Liang, J. Lu, Y. Niu, and B. Wang,            LSTM–transformer model for the prediction of epileptic seizure using
      ‘‘Anchoring temporal convolutional networks for epileptic seizure                   scalp EEG,’’ IEEE Sensors J., vol. 24, no. 13, pp. 21123–21131, Jul. 2024.
      prediction,’’ J. Neural Eng., vol. 21, no. 6, Dec. 2024, Art. no. 066008.           [Online]. Available: https://ieeexplore.ieee.org/document/10539056/
      [Online]. Available: https://iopscience.iop.org/article/10.1088/1741-         [126] Z. Yu, L. Albera, R. Le Bouquin Jeannes, A. Kachenoura, A. Karfoul,
      2552/ad8bf3                                                                         C. Yang, and H. Shu, ‘‘Epileptic seizure prediction using deep neural
[111] P. Peng, L. Xie, and H. Wei, ‘‘A deep Fourier neural network for seizure            networks via transfer learning and multi-feature fusion,’’ Int. J. Neural
      prediction using convolutional neural network and ratios of spectral                Syst., vol. 32, no. 7, Jul. 2022, Art. no. 2250032. [Online]. Available:
      power,’’ Int. J. Neural Syst., vol. 31, no. 8, Aug. 2021, Art. no. 2150022.         https://www.worldscientific.com/doi/10.1142/S0129065722500320
      [Online]. Available: https://www.worldscientific.com/doi/abs/10.1142/         [127] K. Khalil, A. Kumar, and M. Bayoumi, ‘‘Accurate hardware predictor
      S0129065721500222                                                                   for epileptic seizure,’’ IEEE Trans. Circuits Syst. I, Reg. Papers, vol. 72,
[112] N. D. Truong, A. D. Nguyen, L. Kuhlmann, M. R. Bonyadi, J. Yang, S.                 no. 5, pp. 1–14, May 2025. [Online]. Available: https://ieeexplore.ieee.
      Ippolito, and O. Kavehei, ‘‘Convolutional neural networks for seizure               org/document/10833708/
      prediction using intracranial and scalp electroencephalogram,’’ Neural        [128] Y. Shi, S. Tang, Y. Li, Z. He, S. Tang, R. Wang, W. Zheng,
      Netw., vol. 105, pp. 104–111, Sep. 2018. [Online]. Available: https://              Z. Chen, and Y. Zhou, ‘‘Continual learning for seizure prediction via
      linkinghub.elsevier.com/retrieve/pii/S0893608018301485                              memory projection strategy,’’ Comput. Biol. Med., vol. 181, Oct. 2024,
[113] M. A. Ozdemir, O. K. Cura, and A. Akan, ‘‘Epileptic EEG classi-                     Art. no. 109028. [Online]. Available: https://linkinghub.elsevier.com/
      fication by using time-frequency images for deep learning,’’ Int. J.                retrieve/pii/S0010482524011132
      Neural Syst., vol. 31, no. 8, Aug. 2021, Art. no. 2150026. [Online].          [129] X. Ding, W. Nie, X. Liu, X. Wang, and Q. Yuan, ‘‘Compact
      Available: https://www.worldscientific.com/doi/abs/10.1142/S01290657                convolutional neural network with multi-headed attention
      2150026X                                                                            mechanism for seizure prediction,’’ Int. J. Neural Syst., vol. 33,
[114] C. Lucasius, V. Grigorovsky, H. Nariai, A. S. Galanopoulou, J. Gursky,              no. 3, Mar. 2023, Art. no. 2350014. [Online]. Available:
      S. L. Moshé, and B. L. Bardakjian, ‘‘Biomimetic deep learning networks              https://www.worldscientific.com/doi/10.1142/S0129065723500144
      with applications to epileptic spasms and seizure prediction,’’ IEEE          [130] J. West, Z. Dasht Bozorgi, J. Herron, H. J. Chizeck, J. D. Chambers, and L.
      Trans. Biomed. Eng., vol. 71, no. 3, pp. 1056–1067, Mar. 2024. [Online].            Li, ‘‘Machine learning seizure prediction: One problematic but accepted
      Available: https://ieeexplore.ieee.org/document/10287599/                           practice,’’ J. Neural Eng., vol. 20, no. 1, Feb. 2023, Art. no. 016008.
[115] H. Khan, L. Marcuse, M. Fields, K. Swann, and B. Yener, ‘‘Focal onset               [Online]. Available: https://iopscience.iop.org/article/10.1088/1741-
      seizure prediction using convolutional networks,’’ IEEE Trans. Biomed.              2552/acae09
      Eng., vol. 65, no. 9, pp. 2109–2118, Sep. 2018. [Online]. Available:          [131] M. Sun, F. Wang, T. Min, T. Zang, and Y. Wang, ‘‘Prediction for high
      https://ieeexplore.ieee.org/document/8239676/                                       risk clinical symptoms of epilepsy based on deep learning algorithm,’’
[116] X. Dong, L. He, H. Li, Z. Liu, W. Shang, and W. Zhou, ‘‘Deep                        IEEE Access, vol. 6, pp. 77596–77605, 2018. [Online]. Available:
      learning based automatic seizure prediction with EEG time-frequency                 https://ieeexplore.ieee.org/document/8548556/
      representation,’’ Biomed. Signal Process. Control, vol. 95, Sep. 2024,        [132] V. R. Karuppiah Ramachandran, H. J. Alblas, D. V. Le, and N.
      Art. no. 106447. [Online]. Available: https://linkinghub.elsevier.com/              Meratnia, ‘‘Towards an online seizure advisory system—An adap-
      retrieve/pii/S1746809424005056                                                      tive seizure prediction framework using active learning heuristics,’’
[117] H. Li, J. Liao, H. Wang, C. A. Zhan, and F. Yang, ‘‘EEG                             Sensors, vol. 18, no. 6, p. 1698, May 2018. [Online]. Available:
      power spectra parameterization and adaptive channel selection                       https://www.mdpi.com/1424-8220/18/6/1698
      towards semi-supervised seizure prediction,’’ Comput. Biol.                   [133] O. Ouichka, A. Echtioui, and H. Hamam, ‘‘Deep learning models for pre-
      Med., vol. 175, Jun. 2024, Art. no. 108510. [Online]. Available:                    dicting epileptic seizures using iEEG signals,’’ Electronics, vol. 11, no. 4,
      https://linkinghub.elsevier.com/retrieve/pii/S0010482524005948                      p. 605, Feb. 2022. [Online]. Available: https://www.mdpi.com/2079-
[118] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C.                        9292/11/4/605
      Fookes, ‘‘Geometric deep learning for subject independent epileptic           [134] R. Chen and K. K. Parhi, ‘‘Seizure prediction using convolutional neural
      seizure prediction using scalp EEG signals,’’ IEEE J. Biomed. Health                networks and sequence transformer networks,’’ in Proc. 43rd Annu. Int.
      Informat., vol. 26, no. 2, pp. 527–538, Feb. 2022. [Online]. Available:             Conf. IEEE Eng. Med. Biol. Soc. (EMBC), Nov. 2021, pp. 6483–6486.
      https://ieeexplore.ieee.org/document/9497714/                                       [Online]. Available: https://ieeexplore.ieee.org/document/9629732/
[119] X. Jiang, X. Liu, Y. Liu, Q. Wang, B. Li, and L. Zhang, ‘‘Epileptic           [135] X. Wu, T. Zhang, L. Zhang, and L. Qiao, ‘‘Epileptic seizure prediction
      seizures detection and the analysis of optimal seizure prediction                   using successive variational mode decomposition and transformers
      horizon based on frequency and phase analysis,’’ Frontiers Neu-                     deep learning network,’’ Frontiers Neurosci., vol. 16, Sep. 2022,
      rosci., vol. 17, May 2023, Art. no. 1191683. [Online]. Available:                   Art. no. 982541. [Online]. Available: https://www.frontiersin.org/
      https://www.frontiersin.org/articles/10.3389/fnins.2023.1191683/full                articles/10.3389/fnins.2022.982541/full
[120] B. Kapoor, B. Nagpal, P. K. Jain, A. Abraham, and L. A. Gabralla,             [136] J. Müller, H. Yang, M. Eberlein, G. Leonhardt, O. Uckermann,
      ‘‘Epileptic seizure prediction based on hybrid seek optimization tuned              L. Kuhlmann, and R. Tetzlaff, ‘‘Coherent false seizure
      ensemble classifier using EEG signals,’’ Sensors, vol. 23, no. 1,                   prediction in epilepsy, coincidence or providence?’’ Clin.
      p. 423, Dec. 2022. [Online]. Available: https://www.mdpi.com/1424-                  Neurophysiol., vol. 133, pp. 157–164, Jan. 2022. [Online]. Available:
      8220/23/1/423                                                                       https://linkinghub.elsevier.com/retrieve/pii/S1388245721007689
[121] I. Jemal, L. Abou-Abbas, K. Henni, A. Mitiche, and N. Mezghani,               [137] G. Segal, N. Keidar, R. M. Lotan, Y. Romano, M. Herskovitz,
      ‘‘Domain adaptation for EEG-based, cross-subject epileptic seizure pre-             and Y. Yaniv, ‘‘Utilizing risk-controlling prediction calibration to
      diction,’’ Frontiers Neuroinform., vol. 18, Feb. 2024, Art. no. 1303380.            reduce false alarm rates in epileptic seizure prediction,’’ Frontiers
      [Online]. Available: https://www.frontiersin.org/articles/10.3389/fninf.            Neurosci., vol. 17, Sep. 2023, Art. no. 1184990. [Online]. Available:
      2024.1303380/full                                                                   https://www.frontiersin.org/articles/10.3389/fnins.2023.1184990/full
[122] J. Xiang, Y. Li, X. Wu, Y. Dong, X. Wen, and Y. Niu, ‘‘Synchronization-       [138] P. Detti, G. Vatti, and G. Zabalo Manrique de Lara, ‘‘EEG synchronization
      based graph spatio-temporal attention network for seizure prediction,’’             analysis for seizure prediction: A study on data of noninvasive record-
      Sci. Rep., vol. 15, no. 1, p. 4080, Feb. 2025. [Online]. Available:                 ings,’’ Processes, vol. 8, no. 7, p. 846, Jul. 2020. [Online]. Available:
      https://www.nature.com/articles/s41598-025-88492-5                                  https://www.mdpi.com/2227-9717/8/7/846

159840                                                                                                                                                VOLUME 13, 2025

Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


[139] C.-Y. Yang, P.-C. Chen, and W.-C. Huang, ‘‘Cross-domain transfer              [154] N. Abderrahim, A. Echtioui, R. Khemakhem, W. Zouch, M. Ghor-
      of EEG to EEG or ECG learning for CNN classification models,’’                      bel, and A. Ben Hamida, ‘‘Epileptic seizures detection using iEEG
      Sensors, vol. 23, no. 5, p. 2458, Feb. 2023. [Online]. Available:                   signals and deep learning models,’’ Circuits, Syst., Signal Process.,
      https://www.mdpi.com/1424-8220/23/5/2458                                            vol. 43, no. 3, pp. 1597–1626, Mar. 2024. [Online]. Available:
[140] E. D. Pontes, M. Pinto, F. Lopes, and C. Teixeira, ‘‘Concept-drifts                 https://link.springer.com/10.1007/s00034-023-02527-8
      adaptation for machine learning EEG epilepsy seizure prediction,’’            [155] M. Bayram and M. A. Arserim, ‘‘Analysis of epileptic iEEG data by
      Sci. Rep., vol. 14, no. 1, p. 8204, Apr. 2024. [Online]. Available:                 applying convolutional neural networks to low-frequency scalograms,’’
      https://www.nature.com/articles/s41598-024-57744-1                                  IEEE Access, vol. 9, pp. 162520–162529, 2021. [Online]. Available:
[141] N. H. Hassoon, M. H. Ali, M. M. Jaber, S. K. Abd, A. S. Abosinnee,                  https://ieeexplore.ieee.org/document/9632561/
      and Z. H. Kareem, ‘‘Prediction and analysis of chronic epilepsy               [156] A. Subasi, T. Tuncer, S. Dogan, and D. Tanko, ‘‘Local binary
      using electroencephalographic signals on medical Internet                           pattern based feature extraction and machine learning for epileptic
      of Things platform,’’ Intell. Data Anal., vol. 27, pp. 65–82,                       seizure prediction and detection,’’ in Modelling and Analysis of Active
      Nov. 2023. [Online]. Available: https://journals.sagepub.com/doi/full/              Biopotential Signals in Healthcare. Bristol, U.K.: IOP Publishing,
      10.3233/IDA-237434                                                                  2020. [Online]. Available: https://iopscience.iop.org/book/edit/978-0-
[142] C. Meisel and K. A. Bailey, ‘‘Identifying signal-dependent infor-                   7503-3411-2/chapter/bk978-0-7503-3411-2ch6
      mation about the preictal state: A comparison across ECoG, EEG                [157] T. D. K., P. B. G., and F. Xiong, ‘‘Epileptic seizure detection and
      and EKG using deep learning,’’ EBioMedicine, vol. 45, pp. 422–431,                  prediction using stacked bidirectional long short term memory,’’ Pattern
      Jul. 2019. [Online]. Available: https://linkinghub.elsevier.com/retrieve/           Recognit. Lett., vol. 128, pp. 529–535, Dec. 2019. [Online]. Available:
      pii/S2352396419304360                                                               https://linkinghub.elsevier.com/retrieve/pii/S0167865519303125
[143] J. Batista, M. F. Pinto, M. Tavares, F. Lopes, A. Oliveira,                   [158] J. D. Chambers, M. J. Cook, A. N. Burkitt, and D. B. Grayden,
      and C. Teixeira, ‘‘EEG epilepsy seizure prediction: The post-                       ‘‘Using long short-term memory (LSTM) recurrent neural networks
      processing stage as a chronology,’’ Sci. Rep., vol. 14, no. 1, p. 407,              to classify unprocessed EEG for seizure prediction,’’ Frontiers Neu-
      Jan. 2024. [Online]. Available: https://www.nature.com/articles/s41598-             rosci., vol. 18, Nov. 2024, Art. no. 1472747. [Online]. Available:
      023-50609-z                                                                         https://www.frontiersin.org/articles/10.3389/fnins.2024.1472747/full
[144] M. Pinto, T. Coelho, A. Leal, F. Lopes, A. Dourado, P. Martins, and C.        [159] Z. Li, M. Fields, F. Panov, S. Ghatan, B. Yener, and L. Marcuse, ‘‘Deep
      Teixeira, ‘‘Interpretable EEG seizure prediction using a multiobjective             learning of simultaneous intracranial and scalp EEG for prediction,
      evolutionary algorithm,’’ Sci. Rep., vol. 12, no. 1, p. 4420, Mar. 2022.            detection, and lateralization of mesial temporal lobe seizures,’’ Frontiers
      [Online]. Available: https://www.nature.com/articles/s41598-022-08322-              Neurol., vol. 12, Nov. 2021, Art. no. 705119. [Online]. Available:
      w                                                                                   https://www.frontiersin.org/articles/10.3389/fneur.2021.705119/full
[145] M. F. Pinto, A. Leal, F. Lopes, A. Dourado, P. Martins, and C. A. Teixeira,
                                                                                    [160] S. Lu, L. Liu, J. Li, J. Chambers, M. J. Cook, and D. B. Grayden,
      ‘‘A personalized and evolutionary algorithm for interpretable EEG
                                                                                          ‘‘Leveraging channel coherence in long-term iEEG data
      epilepsy seizure prediction,’’ Sci. Rep., vol. 11, no. 1, p. 3415,
                                                                                          for seizure prediction,’’ IEEE J. Biomed. Health Informat.,
      Feb. 2021. [Online]. Available: https://www.nature.com/articles/s41598-
                                                                                          vol. 29, no. 8, pp. 5541–5548, Aug. 2025. [Online]. Available:
      021-82828-7
                                                                                          https://ieeexplore.ieee.org/document/10946758/
[146] B. Sarvi Zargar, M. R. Karami Mollaei, F. Ebrahimi, and J. Rasekhi,
                                                                                    [161] C. Reuben et al., ‘‘Ensembling crowdsourced seizure prediction
      ‘‘Generalizable epileptic seizures prediction based on deep transfer
                                                                                          algorithms using long-term human intracranial EEG,’’ Epilepsia,
      learning,’’ Cognit. Neurodynamics, vol. 17, no. 1, pp. 119–131, Feb. 2023.
                                                                                          vol. 61, no. 2, pp. e7–e12, Feb. 2020. [Online]. Available:
      [Online]. Available: https://link.springer.com/10.1007/s11571-022-
                                                                                          https://onlinelibrary.wiley.com/doi/10.1111/epi.16418
      09809-y
[147] G. Wang, D. Wang, C. Du, K. Li, J. Zhang, Z. Liu, Y. Tao, M. Wang,            [162] M. Ravindranath, K. S. Candan, M. L. Sapino, and B. Appavu, ‘‘MMA:
      Z. Cao, and X. Yan, ‘‘Seizure prediction using directed transfer                    Metadata supported multi-variate attention for onset detection and pre-
      function and convolution neural network on intracranial EEG,’’                      diction,’’ Data Mining Knowl. Discovery, vol. 38, no. 4, pp. 1545–1588,
      IEEE       Trans.     Neural     Syst.   Rehabil.      Eng.,   vol.    28,          Jul. 2024. [Online]. Available: https://link.springer.com/10.1007/s10618-
      no. 12, pp. 2711–2720, Dec. 2020. [Online]. Available:                              024-01008-z
      https://ieeexplore.ieee.org/document/9248064/                                 [163] L. Cousyn, R. B. Messaoud, K. Lehongre, V. Frazzini, V. Lambrecq,
[148] Z. Yu, W. Nie, W. Zhou, F. Xu, S. Yuan, Y. Leng, and Q. Yuan, ‘‘Epileptic           C. Adam, B. Mathon, V. Navarro, and M. Chavez, ‘‘Daily resting-
      seizure prediction based on local mean decomposition and deep convolu-              state intracranial EEG connectivity for seizure risk forecasts,’’ Epilep-
      tional neural network,’’ J. Supercomput., vol. 76, no. 5, pp. 3462–3476,            sia, vol. 64, no. 2, pp. e23–e29, Feb. 2023. [Online]. Available:
      May 2020. [Online]. Available: http://link.springer.com/10.1007/s11227-             https://onlinelibrary.wiley.com/doi/10.1111/epi.17480
      018-2600-6                                                                    [164] P. Parani, U. Mohammad, and F. Saeed, ‘‘Lightweight transformer
[149] X. Wang, C. Zhang, T. Kärkkäinen, Z. Chang, and F. Cong,                            exhibits comparable performance to LLMs for seizure prediction: A
      ‘‘Channel increment strategy-based 1D convolutional neural networks                 case for light-weight models for EEG data,’’ in Proc. IEEE Int. Conf.
      for seizure prediction using intracranial EEG,’’ IEEE Trans. Neural                 Big Data (BigData), Dec. 2024, pp. 4941–4945. [Online]. Available:
      Syst. Rehabil. Eng., vol. 31, pp. 316–325, 2023. [Online]. Available:               https://ieeexplore.ieee.org/document/10825319/
      https://ieeexplore.ieee.org/document/9950283/                                 [165] M.-P. Hosseini, T. X. Tran, D. Pompili, K. Elisevich, and
[150] Q. Lian, Y. Qi, G. Pan, and Y. Wang, ‘‘Learning graph in graph                      H. Soltanian-Zadeh, ‘‘Multimodal data analysis of epileptic EEG
      convolutional neural networks for robust seizure prediction,’’ J. Neural            and rs-fMRI via deep learning and edge computing,’’ Artif. Intell.
      Eng., vol. 17, no. 3, Jun. 2020, Art. no. 035004. [Online]. Available:              Med., vol. 104, Apr. 2020, Art. no. 101813. [Online]. Available: https://
      https://iopscience.iop.org/article/10.1088/1741-2552/ab909d                         linkinghub.elsevier.com/retrieve/pii/S0933365718306882
[151] M. H. Abdullah, H. Ibrahim, J. M. Abdullah, and M. Z. Abdullah,               [166] Y. G. Chung, Y. Jeon, S. A. Choi, A. Cho, H. Kim, H. Hwang,
      ‘‘Improved seizure prediction using discrete hidden Markov model and                and K. J. Kim, ‘‘Deep convolutional neural network based interictal-
      Wilks’ lambda analysis of the electroencephalographic signals,’’ Current            preictal electroencephalography prediction: Application to focal cortical
      Med. Imag. Rev., vol. 14, no. 3, pp. 407–415, May 2018. [Online].                   dysplasia type-II,’’ Frontiers Neurol., vol. 11, Nov. 2020, Art. no. 594679.
      Available: http://www.eurekaselect.com/148745/article                               [Online]. Available: https://www.frontiersin.org/articles/10.3389/fneur.
[152] Y. M. Massoud, A. A. Ahmad, M. Abdelzaher, L. Kuhlmann,                             2020.594679/full
      and M. A. Abd El Ghany, ‘‘Hardware implementation of deep                     [167] D. Zambrana-Vinaroz, J. M. Vicente-Samper, J. Manrique-Cordoba, and
      neural network for seizure prediction,’’ AEU - Int. J. Electron.                    J. M. Sabater-Navarro, ‘‘Wearable epileptic seizure prediction system
      Commun., vol. 172, Dec. 2023, Art. no. 154961. [Online]. Available:                 based on machine learning techniques using ECG, PPG and EEG
      https://linkinghub.elsevier.com/retrieve/pii/S1434841123004351                      signals,’’ Sensors, vol. 22, no. 23, p. 9372, Dec. 2022. [Online]. Available:
[153] Y. M. Massoud, M. Abdelzaher, L. Kuhlmann, and M. A. Abd El                         https://www.mdpi.com/1424-8220/22/23/9372
      Ghany, ‘‘General and patient-specific seizure classification using            [168] B. Sidaoui and K. Sadouni, ‘‘Epilepsy seizure prediction from
      deep neural networks,’’ Anal. Integr. Circuits Signal Process.,                     EEG signal using machine learning techniques,’’ Adv. Electr. Com-
      vol. 116, no. 3, pp. 205–220, Sep. 2023. [Online]. Available:                       put. Eng., vol. 23, no. 2, pp. 47–54, 2023. [Online]. Available:
      https://link.springer.com/10.1007/s10470-023-02153-z                                http://www.aece.ro/abstractplus.php?year=2023&number=2&article=6

VOLUME 13, 2025                                                                                                                                               159841

                                                     Y. Wu et al.: Review of Machine Learning and Deep Learning Trends in EEG-Based Epileptic Seizure Prediction


[169] X. Wei, L. Zhou, Z. Zhang, Z. Chen, and Y. Zhou, ‘‘Early prediction of                                 MINGYU WU received the B.S. degree in
      epileptic seizures using a long-term recurrent convolutional network,’’ J.                             software engineering from Zhejiang Normal Uni-
      Neurosci. Methods, vol. 327, Nov. 2019, Art. no. 108395. [Online]. Avail-                              versity, China, in 2020, and the M.S. degree in
      able: https://linkinghub.elsevier.com/retrieve/pii/S0165027019302523                                   electrical engineering from Temple University,
[170] A. F. Struck, A. A. Rodriguez-Ruiz, G. Osman, E. J. Gilmore,                                           USA, in 2021. He is currently pursuing the Ph.D.
      H. A. Haider, M. B. Dhakar, M. Schrettner, J. W. Lee, N. Gaspard,                                      degree in electrical engineering with Universiti
      L. J. Hirsch, and M. B. Westover, ‘‘Comparison of machine learning                                     Teknologi Malaysia (UTM), with a research focus
      models for seizure prediction in hospitalized patients,’’ Ann. Clin.
                                                                                                             on energy optimization for industrial robots. He is
      Translational Neurol., vol. 6, no. 7, pp. 1239–1247, Jul. 2019. [Online].
                                                                                                             also a Lecturer with the School of Industrial Inter-
      Available: https://onlinelibrary.wiley.com/doi/10.1002/acn3.50817
                                                                                                             net, Jiaxing Vocational and Technical College,
[171] W. Choi, M.-J. Kim, M.-S. Yum, and D.-H. Jeong, ‘‘Deep convolutional
      gated recurrent unit combined with attention mechanism to classify           China, and a Distinguished Research Fellow with Thanh Dong University,
      pre-ictal from interictal EEG with minimized number of channels,’’ J.        Vietnam. His research interests include embodied intelligence, computer
      Personalized Med., vol. 12, no. 5, p. 763, May 2022. [Online]. Available:    vision, and machine learning. He currently serves as a Topic Editor for a
      https://www.mdpi.com/2075-4426/12/5/763                                      Special Issue of Frontiers in Robotics and AI.
[172] P. F. Viana, T. P. Attia, M. Nasseri, J. Duun-Henriksen, A. Biondi,
      J. S. Winston, I. P. Martins, E. S. Nurse, M. Dümpelmann,
      A. Schulze-Bonhage, D. R. Freestone, T. W. Kjaer, M. P. Richardson,
      and B. H. Brinkmann, ‘‘Seizure forecasting using minimally invasive,
      ultra-long-term subcutaneous electroencephalography: Individualized
      intrapatient models,’’ Epilepsia, vol. 64, no. S4, pp. S124–S133,
      Dec. 2023. [Online]. Available: https://onlinelibrary.wiley.com/doi/10.
      1111/epi.17252

                                                                                                             CHIA YEE OOI (Senior Member, IEEE) received
                                                                                                             the B.E. and M.E. degrees in electrical engineer-
                                                                                                             ing from Universiti Teknologi Malaysia, Skudai,
                          YITONG WU received the B.Eng. degree from                                          Malaysia, in 2001 and 2003, respectively, and
                          China Jiliang University, China, in 2019, and                                      the Ph.D. degree in information science from the
                          the M.Eng. degree from Nanjing University of                                       Nara Institute of Science and Technology, Kansai
                          Science and Technology, China, in 2022. He is cur-                                 Science City, Japan, in 2006. She is currently
                          rently pursuing the Ph.D. degree with Universiti                                   an Associate Professor with Universiti Teknologi
                          Teknologi Malaysia (UTM), where his research                                       Malaysia. Her research interests include hardware
                          focuses on EEG-based intelligent analysis and                                      security, VLSI design, and testing.
                          early seizure prediction—–a deep-learning-driven
                          pathway toward precision neuro-medicine. He is
                          also a Lecturer with the School of Industrial Inter-
net, Jiaxing Vocational and Technical College, China, and a Distinguished
Research Fellow with Thanh Dong University, Vietnam. His research
interests include machine learning, deep learning, and computer vision.


                                                                                                            WILLIAM HOLDERBAUM received the Ph.D.
                            EILEEN LEE MING SU received the B.Eng.                                          degree in automatic control from the University of
                            degree in mechatronics and the M.Eng. degree in                                 Lille, focusing on developing new methodologies
                            electrical engineering from Universiti Teknologi                                for control laws in hybrid systems. He began his
                            Malaysia, and the Ph.D. degree in bioengineering                                academic career at the University of Glasgow,
                            from Imperial College London. She is currently                                  later becoming a Lecturer, a Senior Lecturer,
                            an Associate Professor with the Faculty of Elec-                                and a Professor with the University of Reading.
                            trical Engineering, Universiti Teknologi Malaysia.                              He was recently appointed as a Professor of
                            Her research interests include medical monitor-                                 control engineering with Manchester Metropolitan
                            ing devices, surgical simulators, virtual reality                               University. His research interests include mathe-
                            systems, rehabilitation robots, haptic devices,        matical modeling, control theory, rehabilitation engineering, smart grids,
machine vision, robotics, automation, and artificial intelligence. She holds       power generation, and autonomous vehicles. He has published over
the titles of a Chartered Engineer (Engineering Council U.K.), a Professional      100 articles and serves as an expert reviewer for the EPSRC and MRC,
Engineer (Board of Engineers Malaysia), and a Professional Technologist            holding memberships in IEEE, the Higher Education Academy, and IEE.
(Malaysia Board of Technologists).


159842                                                                                                                                           VOLUME 13, 2025
```
