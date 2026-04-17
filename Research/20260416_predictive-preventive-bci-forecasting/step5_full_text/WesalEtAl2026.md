---
citation_key: "WesalEtAl2026"
paper_id: "paper_250"
title: "Modalities and algorithms for generalized motor seizure detection and prediction: a scoping review."
authors: "Ahmed Wesal; Farida Hesham; Mohamed A M Gad; Mostafa Abdelrahim; Nariman Ahmed Sayed; Nour Bahgat; Nour Allah Zaki; Aliaa Rehan Youssef"
year: 2026
doi: "10.1080/17434440.2026.2632757"
source: "publisher-pdf (doi: 10.1080/17434440.2026.2632757)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.8
---

# Modalities and algorithms for generalized motor seizure detection and prediction: a scoping review.

**Citation:** `WesalEtAl2026` · **Tier:** 1 · **Composite:** 4.8
**DOI:** [10.1080/17434440.2026.2632757](https://doi.org/10.1080/17434440.2026.2632757)
**Source PDF:** `full_pdf/Wesal2026.pdf`

## Abstract

ARTICLE HISTORY

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Expert Review of Medical Devices


      ISSN: 1743-4440 (Print) 1745-2422 (Online) Journal homepage: www.tandfonline.com/journals/ierd20


Modalities and algorithms for generalized motor
seizure detection and prediction: a scoping review

Ahmed Wesal, Farida Hesham, Mohamed A. M. Gad, Mostafa Abdelrahim,
Nariman Ahmed Sayed, Nour Bahgat, Nour Allah Zaki & Aliaa Rehan Youssef

To cite this article: Ahmed Wesal, Farida Hesham, Mohamed A. M. Gad, Mostafa Abdelrahim,
Nariman Ahmed Sayed, Nour Bahgat, Nour Allah Zaki & Aliaa Rehan Youssef (2026) Modalities
and algorithms for generalized motor seizure detection and prediction: a scoping review,
Expert Review of Medical Devices, 23:4, 409-424, DOI: 10.1080/17434440.2026.2632757

To link to this article: https://doi.org/10.1080/17434440.2026.2632757


       View supplementary material


       Published online: 02 Mar 2026.


       Submit your article to this journal


       Article views: 80


       View related articles


       View Crossmark data


                      Full Terms & Conditions of access and use can be found at
             https://www.tandfonline.com/action/journalInformation?journalCode=ierd20

EXPERT REVIEW OF MEDICAL DEVICES
2026, VOL. 23, NO. 4, 409–424
https://doi.org/10.1080/17434440.2026.2632757


REVIEW

Modalities and algorithms for generalized motor seizure detection and prediction: a
scoping review
Ahmed Wesala*, Farida Heshama*, Mohamed A. M. Gada*, Mostafa Abdelrahima*, Nariman Ahmed Sayeda*,
Nour Bahgata*, Nour Allah Zakia* and Aliaa Rehan Youssefa,b
a
 Department of Systems and Biomedical Engineering, Cairo University, Giza, Egypt; bDepartment of Physical Therapy for Musculoskeletal Disorders and
Surgery, Faculty of Physical Therapy, Cairo University, Giza, Egypt


    ABSTRACT                                                                                                                           ARTICLE HISTORY
    Introduction: Generalized tonic – clonic seizures (GTCS) is a major cause of sudden unexpected death                               Received 30 October 2025
    in epilepsy (SUDEP); thus, continuous monitoring is essential. Electroencephalography (EEG) is the                                 Accepted 12 February 2026
    diagnostic gold standard; however, non-EEG wearables have emerged as promising, user-friendly
                                                                                                                                       KEYWORDS
    alternatives enhancing comfort, mobility, and social acceptance.
                                                                                                                                       Epileptic seizures;
    Areas covered: This scoping review compared sensing modalities and computational methods used for                                  generalized motor seizures;
    seizure detection and prediction, identified effective sensor combinations, and highlighted current                                machine learning; deep
    research gaps. Following PRISMA-ScR guidelines, Scopus, IEEE Xplore, and PubMed databases were                                     learning; wearable sensors;
    searched up to 22 April 2025. Twenty-nine studies met inclusion criteria. For seizure detection,                                   detection; prediction
    combining electrodermal activity (EDA) with motion sensors – accelerometers (ACC) and gyroscopes
    (GYR) – and surface electromyography (sEMG) achieved high reliability, 98.6% precision, while using
    ACC and EDA alone yielded superior sensitivities up to 97.2% and a lower false alarm rate (FAR) of 0.53/
    24 h. Regarding seizure prediction, combining EDA, blood volume pulse (BVP), ACC, and temperature
    showed the highest sensitivity of 75.6%.
    Expert opinion: Wearable multimodal non-EEG seizure detection and prediction systems offer perso­
    nalized care but face validation, hardware, and privacy hurdles. Future success depends on efficient AI,
    IoT integration, patient-centric design, and clear regulations ensuring accessible and trustworthy clinical
    tools.
    PLAIN LANGUAGE SUMMARY
    People with epilepsy experience sudden episodes of abnormal brain activity called seizures, or fits. One
    serious type, the generalized tonic – clonic seizure (GTCS), causes loss of consciousness, muscle
    stiffening, and body jerking, which can lead to injury or even sudden unexpected death in epilepsy
    (SUDEP).
        Traditionally, seizures are monitored in hospitals using electroencephalography (EEG), which records
    brain signals. However, EEG systems are uncomfortable for daily use and limit continuous monitoring.
    Recent innovations in wearable sensor technology – such as motion sensors (accelerometers), skin
    conductance sensors (electrodermal activity), and heart or blood flow sensors (photoplethysmography)
    – offer a more practical, noninvasive alternative. These devices can be worn as smartwatches or
    bracelets, fitting naturally into everyday life.
        Artificial intelligence (AI) and machine learning play an increasingly important role in these systems.
    By recognizing complex patterns in motion and physiological signals, AI algorithms can automatically
    detect seizures and, in early research, may even predict when a seizure is likely to occur. While results so
    far are promising, more clinical studies and larger datasets are needed to confirm accuracy and
    reliability across different patient groups.
        Advances in wearable sensors and artificial intelligence could revolutionize epilepsy management by
    making continuous seizure monitoring and prediction possible in daily life. Although more evidence is
    required before widespread clinical adoption, these technologies hold strong potential to improve
    safety, autonomy, and quality of life for people living with epilepsy.


CONTACT Aliaa Rehan Youssef           aliaa.rihan@pt.cu.edu.eg    Faculty of Engineering, Cairo University, Cairo University Street, Giza 12613, Egypt
*
 These authors contributed equally to the conception, analysis, and writing of this work.
    Supplemental data for this article can be accessed online at https://doi.org/10.1080/17434440.2026.2632757
© 2026 Informa UK Limited, trading as Taylor & Francis Group

410      A. WESAL ET AL.


1. Introduction                                                         Accordingly, this scoping review aims to: (1) compare dif­
The estimated global prevalence of epilepsy is 50 million with       ferent modalities and algorithms used for seizures detection
approximately 5 million new cases diagnosed each year [1]. Of        and prediction; (2) identify the most promising sensor combi­
these, approximately 20–40% have refractory epilepsy, a version      nations and approaches for both purposes; and (3) highlight
of the disease that is not controlled by typical antiseizure         current research gaps and limitations in this field. The findings
medications [2]. Generalized motor seizures and specifically         of this review are intended to inform and guide future
generalized tonic – clonic seizures (GTCS) are considered one        research toward the development of accurate, high-perfor­
of the most dangerous seizure subtypes that are strongly asso­       mance systems for the detection and prediction of GTCS.
ciated with sudden unexpected death in epilepsy (SUDEP) [3].
Effective management of seizures requires a multidisciplinary
approach that integrates neurological, motor, and psychosocial
                                                                     2. Methodology
care [4]. Therefore, seizure detection and prediction systems are
critically needed to provide caregivers with timely opportunities    This scoping review was conducted in accordance with the
to intervene and mitigate potentially dangerous seizure-related      PRISMA Extension for Scoping Reviews (PRISMA-ScR) guide­
consequences. Electroencephalography (EEG) is the gold stan­         lines (Figure 1) [13].
dard method for seizure detection [5] and prediction [6], how­           Conference papers and peer-reviewed articles of various
ever, it requires the use of either a hat/headset which is           study designs were included if published in English and inves­
deemed uncomfortable and socially stigmatizing by epileptic          tigated wearable multimodal approaches for the detection or
patients [7]. This has driven research toward investigating the      prediction of epileptic seizures. Studies were excluded if they
feasibility and effectiveness of alternative wearable and non-       (1) were review articles, (2) employed a unimodal detection
EEG systems in detecting and predicting seizure fits.                system, (3) lacked clinical validation, or (4) targeted focal
    There are several physiological measures that can be discri­     seizures only.
minative of generalized motor seizures besides known motor               Three electronic databases (Scopus, IEEE Xplore, and
manifestations. These include electrodermal activity (EDA), mus­     PubMed) were searched until 22 April 2025 using Boolean
cle activity captured by surface electromyography (sEMG), and        operators, wildcards, and keywords relevant to epilepsy as
cardiovascular or respiratory measures obtained from electrocar­     shown in Supplementary file SI.
diography (ECG) or photoplethysmography (PPG), such as heart             After duplicates removal, retrieved articles were screened
rate (HR), heart rate variability (HRV), blood volume pulse (BVP),   first by titles and abstracts, followed by reading through the
and oxygen saturation (SpO2) [8–11]. It is worth noting that         full text. Seven reviewers independently participated as pairs
detection of abnormal movement associated with seizures has          in screening. Screening decisions and record management
been performed using accelerometers (ACC), yet motion signals        were handled using Mendeley for reference organization and
obtained via ACCs exhibit relatively high false alarms when used     Google Sheets for collaborative screening.
alone due to other daily activities mimicking seizure-like move­         Data charting was conducted in duplicate by independent
ments [12]. This prompted the shift toward multimodal seizure        reviewers using Google Sheets. Reviewers extracted data
detection systems, and the incorporation of other either motion-     deemed relevant to the review objectives including: year of
based sensors like gyroscopes (GYR) or the aforementioned            publication; task type (detection, prediction, or forecasting);
physiological sensors.                                               study characteristics (clinical setting, average patient age,
    For seizure prediction, a gold-standard signal has not yet       dataset size, targeted seizure types, and reference standard);
been identified; therefore, progress in this area has been           device characteristics (wearability, commercial device name if
limited. Thus, the autonomic distinctions of the peri-ictal per­     applicable, and sensor placement); signal characteristics (sen­
iod remain an open research question, and ongoing studies            sor modalities, extracted biomarkers, and preprocessing
are investigating how features derived from physiological sig­       steps); algorithm characteristics (task type, real-time applicabil­
nals can provide reliable predictive markers.                        ity, patient specific versus generalized model, and best-

                                                                                                   EXPERT REVIEW OF MEDICAL DEVICES        411


                                                                             3.1. Participants demographics
   Article highlights
                                                                             3.1.1. Detection
  ● Multisensor wearable systems utilizing non-EEG signals demonstrate       Nine (34.62%) studies targeted generalized tonic-clonic and/or
    strong potential for detecting GTCS, offering greater comfort, discre­
    tion, and suitability for daily use compared to traditional EEG-based
                                                                             tonic-clonic seizures only [14,21,29–35]. Four (15.38%) studies
    monitoring.                                                              focused solely on nocturnal seizures [19,20,31,33].
  ● Motion sensors – particularly ACC – were employed in nearly all              Studies included either adults, pediatrics or a mixed popu­
    studies to capture motor manifestations of seizures. EDA sensors
    were used in about half of the studies, while physiological sensors
                                                                             lation as follows: Five studies [21,36–39] focused solely on
    such as ECG were the least applied for tonic – clonic seizure detec­     adults aged 20 [38] to 64 years [36]. From which, only one
    tion. Optical sensors, particularly PPG, were frequently used for        study provided the mean age [37], and another the mean and
    seizure prediction, enabling extraction of physiological biomarkers
    such as HR, HRV, and BVP that tend to change before seizure onset.
                                                                             standard deviation [21]. Eleven out of 26 (42.3%) studies
  ● Data preprocessing techniques – including synchronization, filtering,    [15,18,20,22,24,25,29,31,32,40,41] were conducted exclusively
    and segmentation – were widely implemented but lacked standardi­         on pediatric patients aged between 1 month [22] and 17 years
    zation. The field would benefit from automated quality control,
    adaptive time windowing, and improved strategies for addressing
                                                                             [40]. Among these, two studies [29,31] did not specify exact
    class imbalance to strengthen model reliability.                         age but indicated inclusion of children, while four provided
  ● Machine-learning algorithms, especially convolutional and recurrent      both mean and median ages only [15,18,32,41]. Ten studies
    neural networks, achieved strong performance but were limited by
    small datasets and reduced interpretability. Ensemble models (e.g.
                                                                             [14,16,17,19,23,30,33–35,42] included mixed-age populations,
    Random Forests) and classical algorithms (e.g. Support Vector            with age ranging from 2 [19] to 75 years [33], including two
    Machines) provided more interpretable, robust alternatives with pro­     studies that did not specify the age range [17,35]. In addition
    mising potential for near-term clinical translation.
  ● Overall, strong sensitivity, high accuracy, and low false-alarm rates
                                                                             to seizure patients, five studies included control groups to test
    indicate that non-EEG wearable seizure detection and prediction          the performance of their seizure detection methods
    systems are approaching clinical readiness, enabling applications        [14,19,21,30,33].
    such as home-based monitoring, informed treatment decisions, care­
    giver notifications, and risk mitigation, although expanded clinical
                                                                                 Sample sizes varied from 7 [31] to 166 participants [15] in
    validation, real-world testing, and cost – effectiveness assessments     studies involving children, from 5 patients [39] to 36 [21] in
    remain necessary prior to widespread adoption.                           studies including adults, and from 4 patients [34] to 135
                                                                             patients [16] in the mixed-age population studies.
                                                                                 Twenty studies (76.9%) were conducted in inpatient set­
                                                                             tings, three studies in outpatient settings [30,38,42], and three
performing algorithm); and reported outcomes (performance                    were conducted in both settings [14,16,17].
metrics and key findings).
   Extracted data were synthesized qualitatively and pre­                    3.1.2. Prediction and forecasting
sented using structured tables. Discrepancies during screen­                 The three prediction studies were more uniform in the demo­
ing and data charting were resolved through collaborative                    graphics of enrolled participants. The number of patients
discussion.                                                                  included in data acquisition ranged from 42 [26] to 139 [27],
                                                                             with mean ages ranged between 9.8 [28] and 14 [26] years,
                                                                             indicating a pediatric-dominant cohort. Two studies [26,27]
3. Results                                                                   also included a control group (patients with no seizures) to
                                                                             differentiate seizure-related patterns from normal brain activ­
After full screening and excluding ineligible articles (Table                ity. All prediction studies were conducted in an inpatient
S1), twenty-six studies, concerned with seizure detection,                   setting.
were included in this review, with the most recent pub­
lished in April 2025 [14] (Table S2). These studies utilized a
range of commercial and noncommercial devices for seizure
                                                                             3.2. Modalities
detection. The most frequently used commercial device was
the Empatica E4 (includes sensors for ACC, EDA, PPG, TEMP),                  3.2.1. Detection
which was tested in 15.4% of the studies [15–18]. Additional                 The most frequently used modality was ACC (96.2%) to cap­
studies employed either customized laboratory-developed                      ture the convulsive motor activity associated with tonic-clonic
devices or other commercial devices, such as: Shimmer                        seizures. EDA followed as the second most used modality,
[19,20], Samsung SM-R800 watch [21], Microsoft wristband                     appearing in half of the studies, while ECG was the least
[22], Nightwatch [23], and Biovital P1 System [24,25].                       commonly used (15.4%) (Figure 2).
    All included studies assessed various combinations of the                   Several studies used raw sensor signals in addition to
following physiological and movement sensors and measures:                   extracting specific biomarkers such as HR, HRV, BVP, and
ACC, BVP, GYR, sEMG, HR, HRV, SpO2, EDA, ECG, and TEMP.                      SpO2, which were then used as features in seizure detection
    For seizure prediction and forecasting, three studies were               models. HR was the most commonly used biomarker (34.6%),
found eligible [26–28] (Table S3). All three papers used the                 while SpO2, audio, Number of Wrist Movements (NOWM), a
Empatica E4 wristband device for real-time data acquisition;                 derived feature that summarizes hand and wrist movement
however, the selected modalities for training and analysis                   frequency over time windows, and motion parameters such as
differed among the papers.                                                   pitch and roll, which describe the orientation of the body/limb

412        A. WESAL ET AL.


Figure 1. PRISMA flow diagram.


in the 3D space, were each used in only 3.8% of the studies       exception was the study by Hegarty-Craver [40], where a
(Figure 3).                                                       cardiac algorithm using ECG alone achieved a lower false
   Altogether, 13 different multimodal sensor combinations        positive alarm (FPR) (1 per day) compared to ACC + ECG (2
were reported. The use of wearables in seizure detection is       per day). Additionally, for GTCS specifically, ACC alone out­
rapidly increasing, as illustrated in Figures 4 and 5, Table 1.   performed other modalities and even multimodal combina­
The most common was ACC + GYR + sEMG + EDA (19.2%).               tions including PPG and EDA in two pediatric studies [15,18].
Almost all studies that directly compared unimodal and multi­        The most commonly used multimodal sensor combination,
modal systems [14,15,18,24,29,31,32,34,37,38,40,41] found that    ACC + GYR + sEMG + EDA [24,25,30,34,41] consistently achieved
multimodal systems outperformed unimodal ones. The only           high performance (accuracy range: 93.16% [41] − 96.81% [24]),

                                                                                             EXPERT REVIEW OF MEDICAL DEVICES      413


Figure 2. Frequency of modalities used in reviewed detection studies.


Figure 3. Frequency of biomarkers used in reviewed detection studies.


with the highest sensitivity (95.24%), accuracy (96.81%), precision     the original combination which achieved an accuracy of 93.4%,
(98.55%) and lowest false alarm rate (FAR)/24 h (0.64) reported by      precision of 95.8%, and recall of 90.9%.
Wu et al. [24]. Among these studies, Wang et al. [25] investigated         Another commonly used combination was ACC + PPG
the use of derived biomarkers (pitch and roll, extracted from ACC       [15,18,23,39]. Yu et al. [15] found that for generalized motor
and GYR) instead of or in combination with raw ACC and GYR              seizures, ACC + BVP achieved the best performance with a
data. They found that substituting ACC with pitch or roll               mean AUC-ROC of 0.805, whereas EDA performed worst with
improved performance across all models (e.g. accuracy improved          a mean AUC-ROC of 0.513. For tonic – clonic seizures specifi­
by approximately 2%), with the best results obtained using              cally, ACC alone yielded the highest performance, with an
Support Vector Machine (SVM) classifier (when substituted with          AUC-ROC of 0.973, a sensitivity of 95%, and an FPR of 6.2%.
pitch: Accuracy: 95.7%, Precision: 95.7%, Recall: 93.8%; With roll:     Similarly, Tang et al. [18] reported that ACC alone performed
Accuracy: 95.2%, Precision: 95.7%, Recall: 92.5%) compared to           best for tonic – clonic seizures (AUC-ROC of 0.995), while for

414         A. WESAL ET AL.


Figure 4. Distribution of sensor combinations across detection studies.


Figure 5. Sensor combination distribution over years.


Table 1. Modalities used for detection of seizures.
 Modality                                    Sensitivity                       FAR/24 H                          Accuracy                            Study
 ACC, GYR, sEMG, EDA                     [81.69%–95.24%]                    [0.64–1.21]                      [93.16%–96.81%]                    [24,25,30,34,41]
 ACC, PPG                                [80%–86%]                          [0.2609–13.63]                   —                                  [15,18,23,39]
 ACC, EDA, PPG                           [93%–100%]                         [0.08–2.339]                     —                                  [17,35]
 ACC, ECG                                [87%–92%]                          —                                —                                  [19,40]
 ACC, GYR                                [76.84%–96%]                       [0.98]                           [97.28%]                           [33,42]
 ACC, GYR, sEMG                          [97%–100%]                         —                                —                                  [14,20]
 ACC, sEMG                               [90.91%]                           —                                —                                  [29]
 ACC, EDA                                [93.9%–97.2%]                      [0.53–1.8]                       [96.7%]                            [16,32,38]
 ACC, ECG, sEMG                          [90.9%]                            —                                —                                  [31]
 ACC, ECG, EDA, sEMG                     —                                  —                                —                                  [37]
 ACC, GYR, PPG                           [87%]                              [0.21]                           [93%]                              [21]
 ACC, EDA, GYR, PPG                      [89%]                              [0.54]                           —                                  [22]
 EDA, PPG                                [100%]                             —                                —                                  [36]
Abbreviations: ACC: Accelerometer; ECG: Electrocardiography; EDA: Electrodermal Activity; FAR/24 H: False Alarm Rate per 24 Hours; GYR: Gyroscope; H: Hours; PPG:
 Photoplethysmography; sEMG: Surface Electromyography.

                                                                                           EXPERT REVIEW OF MEDICAL DEVICES         415


seizure-type – agnostic classification, the fusion of ACC + BVP     chance) in 43% of patients (30/69), where the mean sensi­
achieved superior results, with an AUC-ROC of 0.752. Another        tivity was 75.6%, the mean time in warning (TiW), the frac­
study, Arends et al. [23], in their in-home nocturnal cohort        tion of time spent in warning, was 47.2% and the mean
study, reported that their modality combination sensitivity         prediction horizon was 31.6 minutes. Each modality contrib­
was significantly high (median 85%) compared to a rhythmic          uted uniquely, though ACC sometimes reduced perfor­
movement-based bed sensor (median 21%). They further ana­           mance in worst-performing patients -defined as those for
lyzed feature contributions and showed that HR was the cri­         whom seizure forecasting accuracy wasn’t significantly bet­
tical modality for true positives (92%) and also for false          ter than chance.
positives, while ACC contributed only 8% of true positives
and caused no false alarms.
    ACC + EDA was also one of the top and high achieving
combinations [16,32,38] with a reported highest sensitivity
                                                                    3.3. Preprocessing
of 97.2% [38] and the lowest FAR/24 h of 0.53 reported [16].        3.3.1. Signal synchronization and quality control
Their results validated Empatica’s multimodal wristbands            A fundamental preprocessing step reported in reviewed litera­
(E4 and Embrace) as reliable tools for GTCS detection in            ture was the temporal alignment of data from wearable
real-world and Epilepsy Monitoring Units (EMUs) settings.           devices with a ground-truth reference, typically video electro­
Chowdhury et al. [38] also reported that fusing ACC and             encephalography (video-EEG), to ensure accurate event label­
EDA significantly improved classification accuracy (96.7%)          ing. Four studies (15.3%) described specific synchronization
and reduced FAR (unspecified) compared to unimodal                  methods [15,18,21,23]. The reported techniques included
approaches. Similarly, Poh et al. [31] reported that the over­      manual clock synchronization at the start and end of record­
all performance was lower when only ACC features were               ings to correct for time drift [15], the use of a Network Time
included.                                                           Protocol (NTP) for automated alignment [21], a three-step
    While most studies incorporate both physiological and           timing error compensation algorithm [18], and the synchroni­
motion-based sensors in their sensor combination modalities,        zation of sensor data with event logs from video record­
19.2% of the studies were purely motion-based, using sensor         ings [23].
combinations of ACC + GYR [34,42], ACC + GYR + sEMG [14,20]             Following synchronization, quality control was performed
and ACC + sEMG [29]. Among these, the ACC + sEMG + GYR              to ensure data integrity. Ten studies (38.5%) detailed their
configuration achieved the best performance with a sensitivity      quality control procedures [14,15,17,18,22,23,34,39–41]. A
range of 97% [20]–100% [25].                                        common strategy was the removal of data segments where
    In addition to studying their significance in seizure detec­    the device was not worn. Two studies accomplished this using
tion, a few studies have tested for the optimal sensor place­       TEMP data, excluding periods where sensed temperature fell
ment [29,31], showing that using sensors on different body          outside a physiological range [15,18]. Other methods involved
locations can reduce FAR and improve performance. Milosevic         trimming the initial and final 15 minutes of recordings to
et al. [29] identified the left wrist (non-dominant hand) and       account for sensor calibration [15] or implementing signal-
right ankle as optimal positions for ACC sensors, while bilateral   specific quality checks. For instance, HR data were only utilized
biceps were optimal for sEMG.                                       if a signal quality index exceeded an 80% threshold [23], while
    For details of the remaining reported combinations, refer to    data from segments with poor EDA contact were discarded
the (Table S2).                                                     [34]. Other studies also reported using custom quality indices
                                                                    to clean data epochs before analysis [14,17].
                                                                        Furthermore, some protocols involved removing sliding
3.2.2. Prediction and forecasting                                   windows with a high percentage (>60%) of missing data [22]
All three studies used EDA and PPG in their sensor combi­
                                                                    or conducting manual reviews to identify and exclude record­
nations. One study additionally used ACC [28]. PPG was
                                                                    ings with failures or invalid annotations [15]. General artifact
used to extract biomarkers like HR [26,27], HRV [27], and
                                                                    removal and signal cleaning were also explicitly mentioned in
BVP [28]. TEMP was also among the biomarkers used
                                                                    several other papers [39–41].
[27,28], however, in one study [27], TEMP did not differenti­
ate between seizure and non-seizure groups and was there­
fore not included in further analysis. Vieluf et al. [26,27]        3.3.2. Noise and artifact removal
identified EDA and HR as containing sufficient seizure-pre­         Majority of the studies (61.5%) reported applying specific signal
dictive information, with reported performance of 62% sen­          processing techniques to remove noise and artifacts from the raw
sitivity, and an accuracy range of 68–68.89%. These findings        sensor data [14,15,20–22,24,25,29,31,34,35,37,38,40–42]. Filtering
were further supported in the study of Vieluf et al. [27],          was the most common approach, with techniques tailored to the
where HRV showed predictive value with patients with an             specific signal modality. For ACC and GYR data, band-pass filters
impending seizure had lower HR and higher HRV compared              were frequently used, with cutoff frequencies such as 1–24 Hz [24]
to seizure-free patients in evening recordings. In the work         or 0.2–47 Hz [31], to isolate movement patterns relevant to sei­
of Meisel et al. [28], forecasting performance was highest          zures. High-pass filters were also applied to remove baseline drift
when all modalities (EDA, BVP, TEMP, ACC) were combined             or focus on significant movements [14,21,29,34]. In addition to
achieving significant seizure forecasting (better-than-             filtering, smoothing techniques like a five-point median filter [35]

416       A. WESAL ET AL.


or a 3-second smoothing filter [36] were employed to reduce           3.3.4. Class imbalance handling
erratic signal fluctuations.                                          A significant challenge inherent in seizure detection is the
    For other modalities, filtering strategies were similarly tar­    profound class imbalance between rare seizure events and
geted. sEMG signals were commonly processed with a high-              the vast amount of non-seizure data. Of the seizure detection
pass filter (e.g. at 20 Hz) to remove motion artifacts and baseline   studies, 26.9% explicitly reported strategies to address this
noise [29,31,34] or a band-pass filter (e.g. 20–90 Hz) [24]. EDA      issue during model training [15,17,18,21,24,30,33]. No such
signals were often smoothed using a mean or median filter to          methods were detailed in reviewed papers on seizure fore­
reduce noise [15,25,34]. Furthermore, a study reported the use        casting or prediction.
of wavelet transformation for denoising multiple signal types,            The most frequently cited technique was undersampling,
including HR, EDA, and ACC [22], while others used notch filters      where the number of normal non-seizure samples is reduced
to eliminate specific sources of interference like powerline noise    to create a more balanced dataset. Two studies employed
[29,37]. In the context of seizure prediction and forecasting,        random undersampling of non-seizure segments [15,18]. A
noise removal was also a noted preprocessing step. One study          similar approach involved subsampling non-seizure epochs
applied low-pass filtering specifically to the EDA signal to refine   to achieve a specific, more manageable seizure-to-nonseizure
the data before analysis [26]. This highlights that while the         ratio of 1:10 for training [21].
ultimate goal (detection vs. prediction) differs, the foundational        Conversely, other studies used oversampling or data aug­
need to clean and denoise raw sensor signals remains a con­           mentation techniques. One study reported using oversam­
sistent and critical practice across the field.                       pling for seizure events, in combination with algorithmic
                                                                      class weighting, to increase the influence of the minority
                                                                      class [33]. Another study implemented a novel approach by
3.3.3. Data segmentation and windowing                                applying a much higher (90%) overlap in its sliding window
A nearly universal preprocessing step reported in the reviewed        segmentation for seizure data, which effectively increased the
studies was the segmentation of continuous time-series data           number of seizure-labeled samples for training achieving sei­
into fixed-length windows, a necessary step for feature extrac­       zure-to-non-seizure ratio of 1:1.5 [30]. These techniques are
tion in most machine learning models. This technique was              crucial for preventing machine learning models from develop­
described in adequate detail in 69.2% of the detection studies        ing a bias toward the majority (non-seizure) class and thereby
[14,17,21,22,24,25,29–38,40,42] and was also a key component          failing to detect true seizure events.
of all of the 3 forecasting and prediction studies [26–28].
    The duration of these windows varied considerably, often
tailored to the physiological signals being analyzed. For cap­        3.3.5. Features extraction
turing the rapid motor patterns characteristic of tonic-clonic        The extraction of features from the windowed signal data is a
seizures, shorter window sizes ranging from 2 to 6 seconds            critical step. This process transforms the raw, time-series sig­
were frequently employed [14,24,25,29,31,35–37,42]. A 10-sec­         nals into a structured format suitable for detection algorithms.
ond window was also a common choice [17,32–34]. While two             Feature extraction was explicitly detailed in 17 of the detec­
studies used much larger segments, ranging from 5 to 7                tion studies [14,16,20,21,24,25,29–35,37,38,41,42] and was cen­
minutes [21,22].                                                      tral to the methodologies of all three forecasting and
    Overlapping windows approach was implemented to                   prediction studies [26–28].
ensure that seizure events occurring at the boundary of a                 The extracted features spanned multiple domains. The most
window were not missed and to augment the volume of                   common were statistical and time-domain features, including
training data. The degree of overlap typically ranged from            measures like mean, variance, interquartile range, and the num­
50% [21,25,37,42] to 90% [30,33]. Overlaps of 75–80% were             ber of local maxima or zero-crossings [14,29,31,42]. Frequency-
also frequently reported [22,24,29,31,32,36].                         domain features, derived from techniques like the Fourier trans­
    All reviewed forecasting and prediction studies used differ­      form or wavelet transforms, were also widely used [21,31,32,38].
ent data preprocessing segmentation approaches. The seg­              The number of features extracted varied significantly, from 19
mentation strategies ranged from short, fixed-length epochs           [32] to 594 [33]. This process often involved deriving features
(30 seconds) and brief daily snapshots (15 minutes) to longer,        from novel signals, such as attitude angles (pitch and roll), which
seizure-centered windows (45 minutes). For example, one               were shown to be effective proxies or replacements for tradi­
study [28] segmented continuous wristband sensor data into            tional accelerometer and gyroscope data [25].
30-second epochs, extracting features from each segment to                Given the high dimensionality of the feature sets, several
train and evaluate their seizure forecasting model. Another           studies employed feature selection or dimensionality reduc­
study [27] utilized a single 15-minute autonomic recording            tion techniques to identify the most salient predictors and
taken in the evening (9:00–9:15 pm) as a fixed snapshot for           reduce computational complexity. The methods reported
seizure likelihood assessment, combining this with clinical           include Principal Component Analysis (PCA) [38], statistical
data for prediction. In contrast, a study [26] applied segmenta­      tests like analysis of variance (ANOVA) [42], T-tests [41], and
tion of 45-minute preictal and interictal periods based on EEG        the Wilcoxon rank-sum test [21], as well as machine learning-
seizure annotations, focusing on capturing nonlinear correla­         based approaches like Random Forest (RF) feature selection
tions between EDA and HR signals for unsupervised seizure             [35] and minimum Redundancy Maximum Relevance (mRMR)
prediction.                                                           [41]. These techniques were shown to optimize the feature set,

                                                                                          EXPERT REVIEW OF MEDICAL DEVICES        417


for instance by reducing 91 initial features to 71 [35] and         particularly for their ability to capture time-series dynamics.
improve classification performance [41].                            One such study demonstrated that an LSTM model with trans­
   In the context of forecasting and prediction, feature extrac­    fer learning significantly outperformed traditional learning,
tion was similarly vital but sometimes focused on different         achieving 93% sensitivity for in-hospital motor seizures with
aspects of the physiological data. One study calculated HRV         a FAR of 2.3 per day [17]. Another study utilized an LSTM with
metrics, specifically the root mean square of successive differ­    attitude angle signals, among others, to achieve an accuracy
ences (RMSSD), to assess impending seizure likelihood [27].         of 83.4% [25].
Another forecasting approach extracted features from raw               Other neural network architectures were also explored. A
signals and their Fourier transforms as well as incorporated        CNN-based model was found to be feasible for detecting a
non-physiological data such as signal quality indices and the       broad variety of seizure types using ACC and BVP signals [18].
time of day, creating a rich, 17-channel input for its              Simpler Artificial Neural Networks (ANNs) also proved effec­
model [28].                                                         tive, with one study reporting 100% sensitivity in detecting
                                                                    nocturnal tonic seizures in an independent test set [33]. In the
3.3.6. Normalization and baseline correction                        context of personalization, an autoencoder model achieved
Several studies incorporated normalization or baseline correc­      100% sensitivity for GTCS in selected patients, although it
tion steps to account for inter-patient physiological variability   was noted to be less scalable [15].
and to standardize the input for detection algorithms. This            For the forecasting and prediction tasks, one study [28]
process was detailed in seven of the detection-focused studies      employed LSTM neural networks trained using leave-one-
[17,22,25,29,36,40,41].                                             subject-out cross-validation on continuously collected retro­
    A common technique was the use of a moving baseline,            spective data. Another study [26] selected Deep Canonically
where incoming data from a short window (e.g. 5 seconds)            Correlated Autoencoders (DCCAE) for training and valida­
were compared against a constantly updated reference to             tion, testing three different architectures: Fully Connected
detect sudden deviations indicative of a seizure [36]. A more       DCCAE (FC-DCCAE), Convolutional Neural Network DCCAE
personalized approach involved defining subject-specific base­      (CNN-DCCAE), and Gated Recurrent Unit DCCAE (GRU-
lines, for example, by using the median of a patient’s signals
                                                                    DCCAE). Among these, GRU-DCCAE yielded the best cluster­
over a period and then calculating residuals from this baseline
                                                                    ing accuracy of 68.89%. Both studies lacked real-time imple­
for analysis [22]. Other studies mentioned baseline correction
                                                                    mentation, relying instead on retrospective or offline data
or calibration as a general step for motion signals like ACC and
                                                                    analysis.
GYR [25,41], or used high-pass filtering as an implicit method
to remove baseline drift from ACC signals [29].
    In addition to baseline correction, signal normalization or     3.4.2. Ensemble methods
standardization was also performed. Normalization improved          Ensemble learning, which combines multiple machine learn­
signal comparability between different people or recording          ing models to improve predictive performance, was a promi­
sessions. Some studies used z-score normalization, which            nent and effective strategy in several detection studies
adjusts signals to have a mean of zero and a standard devia­        (Table 2b). Ensemble classifiers were used in 23% of the
tion of one [17,40]. These procedures ensure that the scale of      detection studies including bagging, boosting, and more com­
different signals and features does not unduly influence the        plex stacked architectures [21,22,24,30,38,42]. Also, one fore­
model’s performance and help in adapting the algorithm to           casting study reported the use of RF classifier [27].
individual physiological characteristics.                               For the seizure detection task, bagging-based methods,
                                                                    such as RF and Bagged Decision Trees, were particularly com­
                                                                    mon [21,24,30,38]. One study demonstrated that algorithm
3.4. Algorithms
                                                                    achieved 90% sensitivity with a low false alarm rate of 1.21
3.4.1. Deep learning methods                                        per 24 hours for tonic-clonic seizures in a daily setting [30].
Studies have leveraged deep learning architectures to auto­         Another study found that a Bagged Decision Tree classifier,
matically learn hierarchical features and model complex tem­        when applied to fused ACC and EDA data, yielded GTCS
poral dependencies in multimodal sensor data. Deep learning         detection accuracy of 96.7% [38].
methods were employed in 19.2% of the reviewed detection                A more advanced approach was the Two-Layer Ensemble
studies (Table 2a) [15,17,18,25,33] and in 66.7% of the predic­     Method (TLEM), which stacked multiple base learners includ­
tion studies (Table 3) [26,28]. The most prominent architec­        ing RF, Extra Trees (ET), Gradient Boosting Decision Tree
tures included Convolutional Neural Networks (CNNs) [15,18],        (GBDT), and AdaBoost (ADB) [42]. This stacked model was
Long Short-Term Memory (LSTM) networks [15,25,28], and              shown to outperform all of its single-layer components,
hybrid models combining both [15].                                  achieving a particularly high sensitivity of 94.57% and a FAR
   For the seizure detection task, hybrid CNN-LSTM models           of 0.46 per 24 hours for nocturnal seizures. While achieving a
were shown to be particularly effective. One study identified a     sensitivity of 76.84% and a FAR of 0.98 per 24 hours for overall,
CNN-LSTM fusion model using ACC and BVP data as the best            day and night, seizures [42].
overall algorithm, achieving 83.9% sensitivity and a detection          For the seizure forecasting task (Table 3), Vieluf et al. [27]
delay of 28 seconds across 28 seizure types [15]. For GTCS          evaluated the performance of seven supervised learning algo­
specifically, this model reached 95% sensitivity [15].              rithms with RF achieving the higher accuracy of 68% and
Standalone LSTM networks were also successfully applied,            sensitivity of 62%.

418   A. WESAL ET AL.


                        Table 2. Algorithms for seizure detection: (a) Deep learning and personalized algorithms, (b) ensemble
                        algorithms, (c) Traditional machine learning algorithms, (d) Rule-based and threshold-based algorithms.
                        (a) Deep Learning and Personalized Algorithms
                                                          Real-time
                         Algorithm                         Analysis             Sensitivity       FAR        AUC-ROC       Study
                         CNN                                  No                   95%              —            0.769     [15]
                                                                                   80%         13.63/24 h        0.752     [18]
                         CNN + LSTM                         No                    83.9%             —            0.789     [15]
                         LSTM                               Yes                     —           8.46/24 h         —        [25]
                         ANN                                No                     96%         0.23/Night         —        [33]
                         Transfer Learninga                 —                      67%           4.8/24 h        0.97      [17]
                         Personalized                       No                    100%        [0.0–95.36]/        —        [15]
                            Autoencodera                                                            24 h
                        (b) Ensemble Algorithms*
                         Algorithm            Inpatient/           Real-Time    Sensitivity    FAR/24 h      Accuracy      Studies
                                                 Outpatient          Analysis
                         Random Forest        Outpatient              No          90%            1.21          —           [30]
                                              Inpatient                           87%            0.21         93%          [21]
                                              Inpatient                          95.24%           —          96.81%        [24]
                         Bagged decision      Outpatient              Yes          —              —          95.1%         [38]
                           Tree
                           Classifier
                         XGBoost              Inpatient               Yes          80%            1.1           —       [22]
                         Two-Layer                                    No         76.84%           0.98       97.28%
                           Ensemble                                               (Overall)      (Overall)    (Overall)
                           Model
                                              Outpatient                         94.57%       0.46 (Night)   91.37%        [42]
                                                                                  (Night)                     (Night)
                        (c) Traditional Machine Learning Algorithms
                          Algorithm           Real-Time         Sensitivity     FAR/24 h       Accuracy      AUC-ROC       Studies
                                                 Analysis
                         SVM                 No                  88%               1.0            —               —        [32]
                                             No                87.13%               —             —               —        [41]
                                             Yes                  —                0.08          100%             —        [25]
                                             No                 100%              0.107           —               —        [14]
                                             No                 81.7%              0.64           —               —        [34]
                                             No                90.01%               —             —               —        [29]
                         KNN                 No                88.16%               —           93.16%            —        [41]
                         LDA                 No                   —                 —             —              0.914     [37]
                        (d) Rule-based and Threshold-based Algorithms
                         Real-Time Analysis Sensitivity          FAR            Accuracy                AUC-ROC            Studies
                         Yes                  92%                   2.09/24 h      —                      —                [40]
                         Yes                  85%                    26.09%        —                    0.8682             [39]
                         Yes                  86%                  0.25/Night      —                      —                [23]
                         No                   87%                   6.3/Night      —                      —                [19]
                         No                   —                        —          100%                    —                [36]
                         No                   97%                      4%          —                      —                [20]
                        Abbreviations: ANN: Artificial Neural Network; AUC-ROC: Area Under the Receiver Operating
                          Characteristic Curve; CNN: Convolutional Neural Network; FAR: False Alarm Rate; FAR/24 h: False
                          Alarm Rate per 24 Hours; KNN: K-Nearest Neighbors; LDA: Linear Discriminant Analysis; LSTM: Long
                          Short-Term Memory; SVM: Support Vector Machine; XGBoost: Extreme Gradient Boosting.
                        *All studies were inpatient studies except for Table 1b (Ensemble Algorithms) included mixed popula­
                          tion.
                          a
                            Algorithms with personalization.


        Table 3. Modalities and algorithms for prediction and forecasting.
         Modalities                           Algorithm                         Accuracy                     Sensitivity             Study
         ACC, PPG, EDA                      LSTM                                —                            75.6%                   [28]
         PPG, EDA                           Random Forest                       68%                          62%                     [27]
         PPG, EDA                           GRU-DCCAE                           68.89%                       —                       [26]
        All are inpatient studies.
        All studies lack real-time data analysis.
        Abbreviations: ACC: Accelerometer; PPG: Photoplethysmography; EDA: Electrodermal Activity; LSTM: Long Short-Term Memory; GRU-
          DCCAE: Gated Recurrent Unit – Deep Canonical Correlation Autoencoder.

                                                                                         EXPERT REVIEW OF MEDICAL DEVICES        419


3.4.3. Traditional machine learning                               autoencoder was able to achieve 100% sensitivity for GTCS
In detection, 30.8% of the studies reported the successful        in certain individuals, a level of performance not reached by
application of models such as SVM, K-Nearest Neighbors            the generalized model [15]. A particularly effective technique
(KNN), and Linear Discriminant Analysis (LDA) (Table 2c)          was transfer learning, where a pre-trained general model was
[14,29,31,32,34,35,37,41].                                        fine-tuned on patient-specific data. This method significantly
    The most frequently and successfully implemented classi­      improved performance, reducing the FAR from 11.3 per day
fier was SVM [14,29,31,32,34,35,41]. One study found that an      with traditional learning to 2.33 per day [17].
SVM delivered the best trade-off between accuracy and false          Other studies underscored the need for personalization by
alarms, achieving a 100% accurate recognition rate with just      observing that false alarms and key predictive features varied
0.08 false alarms per day [35]. Another study concluded that a    significantly between individuals [29,37]. Some methodologies
linear SVM (SVM-L) provided the optimum sensitivity and           were inherently personalized, such as a system that tracked
overall performance among several tested models, achieving        individual ‘physiomes’ by establishing personal physiological
sensitivity of 100% and FAR/24 h of 0.107 [14]. Other studies     baselines to detect seizure-related deviations [22].
reported SVM sensitivities ranging from 81.7% [34] to 90.01%
[29]. The effectiveness of SVMs was also noted when using
                                                                  4. Discussion
attitude angle signals, where they yielded the highest overall
accuracy compared to decision trees and LDA [25].                 This scoping review provides an overview of the modalities,
    Other traditional classifiers also showed strong perfor­      signal processing approaches and algorithms applied in sei­
mance. KNN, particularly when using a cosine distance metric      zure detection and prediction. It highlights the most promis­
on features from four combined modalities, achieved a high        ing sensor combinations and approaches. These insights could
sensitivity of 88.16% and accuracy of 93.16% [41]. LDA was        guide future choices aimed at developing more accurate and
also utilized, with one study reporting and AUC-ROC of            high-performance systems for detecting and predicting gen­
0.914 [37].                                                       eralized motor seizures, specifically GTCS.


3.4.4. Rule-based and threshold-based methods                     4.1. Participants demographics
These methods rely on predefined physiological patterns or
                                                                  4.1.1. Detection
thresholds to trigger a seizure detection. This approach was
                                                                  Reviewed studies were heterogeneous in populations and
used in 19.2% of the reviewed detection studies (Table 2d)
                                                                  settings, limiting generalizability. Notably, 76.9% (including
[20,23,36,39,40].
                                                                  all pediatric studies) were conducted in an inpatient setting,
    One study developed a system based on a multi-biosignal
                                                                  enabling gold-standard video EEG but restricting movement
pattern, defining a seizure event as a sequence of HR increase,
                                                                  and real-life activity. Consequently, similar models tested in
followed by a decrease in SpO2, and a subsequent rise in EDA
                                                                  outpatient environments showed higher FARs [16,17,30,38].
[36]. This rule-based method achieved an accuracy of 100% for
                                                                  However, studies like Poh et al. [32] reduced inpatient bias
seizure detection in GTCS patients [36]. Another study imple­
                                                                  by adding extensive real-world non-seizure activity data,
mented a system with decision rules based on three factors:
                                                                  enabling a more realistic FAR estimation.
shaking, from an ACC, HR, and TEMP [39]. By classifying risk
                                                                      Additionally, although no standard exists for minimum
into discrete levels, the system achieved a sensitivity of
                                                                  patient numbers in non-EEG seizure detection, datasets of
85% [39].
                                                                  ≥30 patients improve reproducibility. About 57.7% of studies
    A threshold-based algorithm using cardiac physiological
                                                                  included fewer than 30 valid patient recordings [17,23–
features was also reported, detecting 92% of seizures with
                                                                  25,30,31,33–39,41,42]. Including a control group helps reduce
tonic/clonic movements [40]. Another approach applied a
                                                                  false alarms, and balanced datasets improve generalizability.
Shewhart control chart with exponentially weighted moving
                                                                  For example, one study [29] included 56 subjects—7 with
averages to motion inertial and muscular activity, achieving a
                                                                  tonic-clonic seizures and 49 controls.
97% detection rate with a 4% FAR [20]. A further study
                                                                      Limited patient numbers greatly affect algorithm perfor­
employed a combined ACC and HR threshold algorithm in a
                                                                  mance. For example, Yu et al. [15] tested a personalized
residential care setting, reaching a median sensitivity of 86%
                                                                  Autoencoder on a small subset despite having 166 patients.
with a positive predictive value (PPV) of 49% [23].
                                                                  Poh et al. [32] had few seizures despite many participants, and
                                                                  Larsen et al. [33] used a much smaller test set than training set.
3.4.5. Methods with personalization                               Overall, dataset size and balance are critical for reliable seizure
Recognizing the high degree of inter-patient variability in       detection models.
seizure manifestation, many studies investigated or recom­            An additional study [43] involving neonates was excluded
mended personalized algorithms. For detection studies,            as it did not report specific results for motor seizures. Since
30.8% highlighted the benefits of tailoring models to indivi­     neonatal seizures are predominantly of focal onset, distin­
dual patients (Table 2a) [15,17,22,25,29,32,37,40].               guishing between focal and generalized seizures is unneces­
   One study showed that a ‘semi-patient-specific’ approach,      sary. Seizures in this period may present with motor features
which included prior seizure examples from the test patient in    (automatisms, clonic movements, epileptic spasms, myoclonic,
the training data, improved sensitivity from 88% to 94% com­      or tonic activity), non-motor features (autonomic manifesta­
pared to a generic model [32]. Similarly, a personalized          tions or behavioral arrest), or a sequential progression.

420      A. WESAL ET AL.


Typically, neonatal seizure semiology is characterized by focal     audio features from a microphone, identifying them among
tonic movements [44].                                               the top ten discriminative features establishing separability
                                                                    between seizure and non-seizure data in five patients. Wang
4.1.2. Prediction and forecasting                                   et al. [25] found that adding or replacing ACC/GYR with atti­
Reviewed prediction and forecasting studies were limited to         tude angles (pitch or roll) improved performance across all
pediatric inpatient cohorts. Due to physiological and beha­         models due to their better resistance to non-seizure motion
vioral differences, their findings cannot be generalized to         interference. Xu et al. [35] used number of wrist movements
adults without further validation. Although some included           (NOWM) instead of raw ACC data to better distinguish seizures
up to 139 patients, more diverse datasets are needed to             from normal movements.
confirm and extend these results.                                      Beyond sensor type, placement and signal quality signifi­
                                                                    cantly affect detection performance. Tang et al. [18] found
                                                                    inconsistent signals from different body sites. Arends et al.
4.2. Modalities
                                                                    [23] excluded participants with abnormal movements or dar­
4.2.1. Detection                                                    ker skin due to poor PPG signal quality which was affected by
Across the 26 reviewed studies, non-EEG multimodal sensor           light intensity. The chest-worn sensor in Hegarty-Craver et al.
setups show strong potential for motor seizure detection and        [40] missed limb movements, reducing the device’s overall
management methods.                                                 sensitivity, while Cogan et al. [36] reported data loss from
    However, direct comparisons are difficult due to methodo­       SpO2 sensors.
logical and population differences. Nevertheless. The (ACC +           Future studies should validate these biomarkers while opti­
GYR + EDA + sEMG) combination consistently performed well           mizing sensor placement, as outcomes vary by location
(Table 1), likely because motion sensors (ACC, GYR) ensure          [29,31]. They should also diversify cohorts and develop perso­
reliable detection, while EDA reduces false alarms. Notably,        nalized models to address physiological variability, particularly
sEMG enabled rapid detection with a short delay of 11.7 s           for patient-dependent signals like HR and HRV.
[31], supporting its value for timely intervention.
    The ACC + EDA combination is also among the best perfor­        4.2.2. Prediction and forecasting
mers, offering fewer sensors, lower costs, and simpler data         Despite differing methods and objectives, the three prediction
processing. This may be due to EDA’s sensitivity to sympa­          studies collectively support the feasibility of using Empatica E4
thetic activation at seizure onset in both children and adults      wristband data with machine or deep learning for seizure pre­
[8], and its lower susceptibility to motion artifacts compared to   diction. Vieluf et al. [26,27] showed that autonomic signals (EDA
signals like PPG [45]. EDA’s increase has also been linked to       and PPG-from which HR/HRV are derived) could successfully
postictal EEG suppression (PGES), a SUDEP risk factor [16,46],      identify pre-ictal periods in many patients. Meisel et al. [28]
underscoring its preventive potential. However, some studies        achieved the highest performance by using all E4 modalities
reported poor EDA performance alone or with other sensors           (EDA, PPG/BVP, ACC, TEMP), confirming the superiority of multi­
[15,18], possibly due to age-related EDA variability noted in       modal sensor combinations observed in detection studies.
pediatric research [41], emphasizing the need for age-adaptive          PPG-derived biomarkers appear to be key seizure predic­
algorithms.                                                         tors. While two studies [26,27] identified HR as predictive,
    Other physiological sensors such as PPG have also been          clinical observations [47] showed that raw PPG features –
widely used to extract biomarkers such as HR [17,21–23,35,36],      such as frequency, smoothness, and slope – change during
HRV [21,22], SpO2 [36], and BVP [15,17,18]. Among these, BVP        peri- and post-ictal phases, suggesting added predictive value.
showed strong potential, consistently performing well across        Future research should evaluate raw PPG signals directly in
seizure types. This aligns with an observational study [47]         larger, more diverse cohorts.
showing that not only HR but also PPG features like smooth­             Notably, only 26.9% of detection studies [22,23,25,31,38–
ness and slope vary with seizure timing, enhancing BVP-based        40] and none of the prediction or forecasting studies per­
detection accuracy.                                                 formed real-time analysis, revealing a major gap between
    ECG has also been used to derive HR [19,31,40] and HRV          experimental work and practical deployment.
[40], with some studies reporting that unimodal ECG systems
can achieve performance comparable to multimodal
                                                                    4.3. Preprocessing
approaches [31,40]. However, ECG was used less frequently
in the reviewed studies, largely due to its susceptibility to       The reviewed studies followed a multi-stage preprocessing
motion artifacts [19], impractical electrode placement, and         pipeline for wearable sensor data, though lacking standardiza­
high inter-patient variability [19,31].                             tion. Synchronization and quality control – ranging from man­
    Because of these limitations, ECG has mostly been used in       ual alignment [15] to automated NTP [21]—were essential but
nocturnal studies [19,31]. This is relevant since SUDEP often       often manual, limiting scalability. Future work should develop
occurs at night [48]. HR and HRV remain potential SUDEP bio­        fully automated, real-time synchronization and quality assess­
markers [46], suggesting ECG’s dual role in seizure detection and   ment methods.
SUDEP monitoring SUDEP-related autonomic changes.                       Filtering was widely applied and modality-specific (e.g.
    Some studies explored non-traditional biomarkers for sei­       band-pass for motion [24,31], high-pass for sEMG [29]), balan­
zure detection, with several showing performance comparable         cing noise removal with preserving seizure-relevant signals.
to or exceeding established biomarkers. Hamlin et al. [37] used     Window segmentation strongly affected performance –

                                                                                           EXPERT REVIEW OF MEDICAL DEVICES       421


shorter windows (2–10 s) captured rapid motor dynamics                  However, several limitations exist. Only English-language
[29,33], while longer ones (>30 s) suited slower autonomic           studies were included, and many had small, heterogeneous
changes [22,28]. Optimal windowing likely requires adaptive,         samples, limiting generalizability. While methodologies and
patient-specific approaches.                                         results were described, studies quality and robustness were
   Class imbalance was managed mainly by under-/over-sam­            not formally assessed. It should also be noted that we are
pling [15,18,33], though simple undersampling risks losing           conducting a qualitative description rather than a quality
valuable non-seizure data. Advanced methods like synthetic           assessment.
data generation or cost-sensitive learning remain underused.
Feature engineering and selection [35,41] offered interpret­
                                                                     5. Conclusion
ability, while deep learning favored end-to-end automation.
Finally, normalization and baseline correction [17,22] were key      Non-EEG seizure detection and prediction show great poten­
for personalization, improving adaptation to individual phy­         tial for improving epilepsy management. Comprehensive sen­
siological variability.                                              sor combinations (ACC, GYR, sEMG, and EDA) for seizure
                                                                     detection demonstrated high reliability, achieving sensitivities
                                                                     up to 95.24%, accuracies as high as 96.81%, precision reaching
4.4. Algorithms                                                      98.55%, and a low FAR around 0.64 per 24 hours. Notably,
                                                                     using ACC and EDA alone yielded superior sensitivities up to
While algorithmic advances have improved wearable seizure
                                                                     97.2% and a lower FAR around 0.53 per 24 hours, suggesting a
detection, prediction, and forecasting, key challenges remain.
                                                                     simpler, cost-effective, and highly efficient alternative.
The algorithmic landscape is fragmented, with variable matur­
                                                                         For seizure prediction, combinations involving EDA, BVP,
ity and generalizability. Deep learning models (CNNs, LSTMs,
                                                                     ACC, and TEMP sensors were most effective, with sensitivities
hybrids) effectively capture temporal and multimodal patterns
                                                                     around 75.6% and successful predictions in 43% of patients.
but are limited by small, homogeneous datasets and low
                                                                     EDA and HR were identified as containing sufficient seizure-
interpretability. Their high data demands and ‘black-box’ nat­
                                                                     predictive information with performance of 62% sensitivity.
ure hinder clinical adoption [49].
                                                                         Deep learning models, particularly hybrid CNN-LSTM archi­
    Ensemble methods (RF, Bagged Trees) offer robustness and
                                                                     tectures, achieved high sensitivity (95%) for detecting GTCS.
interpretability for multimodal data but face computational
                                                                     While ensemble methods like Random Forest and stacking
and real-time deployment challenges. Few studies tested
                                                                     models showed strong accuracy and low FAR, with the highest
them in live monitoring, indicating a need for optimization
                                                                     sensitivity of 94.57% and FAR around 0.46 for nocturnal sei­
in latency, power efficiency, and adaptability.
                                                                     zures. It was noticed that personalization methods such as
    Traditional machine learning algorithms (SVM, KNN, LDA)
                                                                     transfer learning further improved the model’s robustness
remain competitive for smaller datasets due to their simplicity
                                                                     and lowered the FAR. However, further clinical validation
and interpretability, though they depend on manual feature
                                                                     should be done in real-time and outpatient settings to be
design and may struggle with cross-patient variability.
                                                                     able to advance these systems as practical tools for epilepsy
Standardized preprocessing and feature selection are essential
                                                                     management.
to reduce bias and improve generalizability.
    Personalized and hybrid models – using patient-specific train­
ing, adaptive baselines, or transfer learning – show strong poten­   6. Expert opinion
tial, improving sensitivity and reducing false alarms. However,
                                                                     Wearable systems using non-EEG modalities are emerging as
they raise scalability and privacy concerns. Future research
                                                                     promising tools for long-term seizure monitoring and perso­
should combine deep representation learning, ensemble deci­
                                                                     nalized epilepsy management. These systems commonly inte­
sion fusion, and personalized adaptation, while emphasizing
                                                                     grate ACC, GYR, EDA, PPG, and sEMG to detect GTCS. Reported
explainability, federated learning, and real-world validation.
                                                                     sensitivities exceeding 95% and false-alarm rates below one
    This review excluded non-original studies, those lacking
                                                                     per 24 hours suggest that multimodal non-EEG wearables can
clinical validation, or addressing non-GTCS (Table S1). Some
                                                                     approach EEG-level accuracy while offering greater comfort
excluded studies, such as one on neonates [43], warrant future
                                                                     and practicality for everyday use.
consideration. Neonatal seizures, often focal with motor or
                                                                        For many individuals – particularly those with drug-resis­
autonomic features [44], differ in presentation and clinical
                                                                     tant epilepsy – wearable seizure-detection systems can extend
context. Among non-validated works, Jahanbekam et al. [50]
                                                                     care beyond clinical settings. Objective seizure counts can
and Conradsen et al. [51] showed promise with well-documen­
                                                                     support treatment adjustments, driving guidance, or surgical
ted datasets, though the former relied on synthetic and
                                                                     referral decisions that often rely on unreliable self-reports.
healthy-volunteer data and lacked real-time testing – suggest­
                                                                     Continuous monitoring of physiological and motion signals
ing these approaches merit future patient-based validation.
                                                                     may also uncover peri-ictal heart-rate variability changes or
                                                                     post-ictal movement suppression linked to seizure duration
                                                                     and severity. These measurable markers could serve as future
4.5. Strengths and limitations
                                                                     biomarkers for treatment response in clinical trials.
This scoping review used a rigorous approach to identify and            Several challenges must be addressed before non-EEG
chart relevant studies, emphasizing promising modalities, fea­       wearables can become reliable, widely adopted assistive
tures, and algorithms for future research.                           tools (see Figure S1). Validation and scalability remain key

422       A. WESAL ET AL.


concerns, as most existing studies are small, single-center trials    deployment. By addressing computational efficiency, scalabil­
conducted under controlled conditions. Real-world perfor­             ity, and deployment feasibility, TTM represents a significant
mance can be compromised by motion artifacts, incomplete              step toward practical, continuous, and personalized seizure
annotations, and environmental variability. Large multicenter         forecasting.
studies across age groups and seizure types are needed to                 Integration with Internet of Things (IoT) ecosystems
confirm generalizability. Additionally, shared, high-quality mul­     expands wearable functionality from detection and prediction
timodal datasets are essential for benchmarking and                   toward comprehensive seizure management. Upon seizure
reproducibility.                                                      detection or early warning, IoT connectivity can alert care­
    Hardware and accessibility barriers also limit deployment.        givers, transmit geolocation to emergency services, or trigger
Despite strong analytical performance, current devices face           safety actions such as unlocking doors, lowering beds, or
constraints related to battery life, cost, and form factor.           disabling hazardous equipment. Linking wearables with
Advances in MEMS sensors and low-power edge processors                smart medication dispensers or cloud-based follow-up plat­
enable smaller, lighter, and more discrete devices that               forms can further improve adherence and post-seizure
improve comfort and adherence. Reducing production costs              recovery.
through component integration and scalable manufacturing                  Patient involvement should guide all stages of technologi­
will be critical to ensuring equitable access, particularly in low-   cal development. Engaging individuals with epilepsy during
and middle-income regions where epilepsy burden is highest.           early design ensures that devices address comfort, usability,
Progress should therefore be measured by usability, afford­           and stigma alongside technical performance. Participatory
ability, and comfort – not accuracy alone.                            clinical trials, where patients help define outcomes and usabil­
    Privacy, confidentiality, and data security remain critical       ity metrics, can generate evidence that is both clinically mean­
considerations for wearable implementation. Continuous                ingful and personally relevant. Establishing patient advisory
monitoring generates sensitive biometric and behavioral               panels within research consortia would institutionalize this
data that require robust protection. Encryption, secure authen­       collaboration and align innovation with lived experience and
tication, and transparent consent should be embedded                  ethical priorities.
throughout system design and deployment. The intersection                 Regulators and policymakers should standardize key per­
of privacy regulations such as General Data Protection                formance metrics – such as sensitivity, false-alarm rate, and
Regulation (GDPR) with medical AI transparency requirements           latency – to enable objective comparison across devices and
remains complex. Federated learning and differential-privacy          algorithms. Validating multimodal biomarkers that combine
methods may enable collaborative model development with­              physiological (e.g. EDA, PPG), behavioral, and contextual data
out sharing raw data, although clearer standards for data             may further enhance predictive accuracy and clinical rele­
anonymization and ownership are still needed.                         vance. Policymakers and professional organizations should
    From an algorithmic perspective, deep-learning models             promote open-data standards, interoperability frameworks,
such as CNNs and LSTMs demonstrate strong performance                 and reporting guidelines aligned with TRIPOD-AI and STARD-
but remain limited by interpretability and personalization.           AI, adapted specifically for wearable technologies to
Explainable AI (XAI) methods that reveal decision-driving fea­        strengthen transparency, reproducibility, and regulatory
tures could enhance clinician trust. Because seizure triggers         readiness.
vary across individuals – including stress, sleep disruption,             Over the next five years, wearable seizure-detection, pre­
hormonal changes, and environmental factors – self-super­             diction, and forecasting technologies are likely to transition
vised learning can help identify patient-specific patterns with­      from feasibility research to certified, telehealth-integrated
out extensive labeling. Integrating wearables with digital            medical devices. Advances in miniaturized hardware, cost-effi­
diaries or mobile questionnaires may allow users to log trig­         cient manufacturing, explainable and adaptive AI, and privacy-
gers, enabling systems to adapt dynamically over time. This           preserving analytics will enable scalable, real-world monitor­
adaptive capability could transform wearables from static             ing. Combined with IoT connectivity, these systems may shift
detectors into personalized, evolving companions.                     epilepsy care from reactive monitoring to proactive interven­
    A promising advance in seizure forecasting lies in light­         tion. Ensuring equitable access, regulatory clarity, and mean­
weight neural architectures for multivariate time-series model­       ingful patient participation will be essential to their success. If
ing, particularly compact models such as Tiny Time Mixers             achieved, wearable and IoT-enabled AI systems could redefine
(TTM) [52], optimized for wearable and resource-constrained           personalized neurology by transforming seizure management
devices. Traditional forecasting models remain limited by com­        into a continuous, intelligent, and patient-empowered
putational and energy demands that hinder real-time, on-              process.
device use. TTM addresses these challenges by replacing self-
attention mechanisms with MLP-Mixer blocks, achieving high
                                                                      Funding
accuracy with substantially lower computational cost. With
approximately one million parameters, adaptive temporal               This paper was not funded.
patching, and multi-level modeling, TTM efficiently captures
temporal and cross-channel dependencies from multimodal
sensor streams. Its pretraining on diverse datasets supports          Declaration of interest
strong zero- and few-shot generalization, while CPU-only              The authors have no relevant affiliations or financial involvement with any
operation enables real-time, energy-efficient wearable                organization or entity with a financial interest in or financial conflict with

                                                                                                       EXPERT REVIEW OF MEDICAL DEVICES                423


the subject matter or materials discussed in the manuscript. This includes      16. Regalia G, Onorati F, Lai M, et al. Multimodal wrist-worn devices for
employment, consultancies, honoraria, stock ownership or options, expert            seizure detection and advancing research: focus on the Empatica
testimony, grants or patents received or pending, or royalties.                     wristbands. Epilepsy Res. 2019;153:79–82. doi: 10.1016/j.eplepsyres.
                                                                                    2019.02.007
                                                                                17. Nasseri M, Pal Attia T, Joseph B, et al. Non-invasive wearable seizure
Reviewer disclosures                                                                detection using long-short-term memory networks with transfer
                                                                                    learning. J Neural Eng. 2021;18(5):056017. doi: 10.1088/1741-
Peer reviewers on this manuscript have no relevant financial relationships          2552/abef8a
or otherwise to disclose.                                                       •• This study used ACC, PPG, and electrodermal activity (EDA)
                                                                                    modalities alongside biomarkers including temperature
                                                                                    (TEMP), heart rate (HR), and blood volume pulse (BVP) via
References                                                                          the Empatica E4 wristband in both inpatient and outpatient
                                                                                    settings. By fine-tuning a pre-trained transfer learning model
Papers of special note have been highlighted as either of interest (•)              with patient-specific data, the false alarm rate (FAR) was sig­
or of considerable interest (••) to readers.                                        nificantly reduced from 11.3 to 2.33 per day, demonstrating
    1. Epilepsy — who.Int. [cited 2025 Sep 26]. Available from: https://            the effectiveness of personalized model adaptation in wear­
       www.who.int/news-room/fact-sheets/detail/epilepsy                            able seizure detection.
    2. Kwan P, Brodie MJ. Early identification of refractory epilepsy. N Engl   18. Tang J, El Atrache R, Yu S, et al. Seizure detection using wearable
       J Med. 2000;342(5):314–319. doi: 10.1056/NEJM200002033420503                 sensors and machine learning: setting a benchmark. Epilepsia.
    3. Devinsky O, Hesdorffer DC, Thurman DJ, et al. Sudden unexpected              2021;62(8):1807–1819. doi: 10.1111/epi.16967
       death in epilepsy: epidemiology, mechanisms, and prevention.             19. van Andel J, Ungureanu C, Arends J, et al. Multimodal, automated
       Lancet Neurol. 2016;15(10):1075–1088. doi: 10.1016/S1474-4422                detection of nocturnal motor seizures at home: is a reliable seizure
       (16)30158-2                                                                  detector feasible? Epilepsia Open. 2017;2(4):424–431. doi: 10.1002/
    4. Esposito M, Santomauro R, Dell’isola GB, et al. Developmental                epi4.12076
       coordination disorder and epilepsy. World J Pediatr. 2025;21(1):1–
                                                                                20. Gheryani M, Salem O, Mehaoua A. Detection of nocturnal epileptic
       2. doi: 10.1007/s12519-024-00869-0
                                                                                    seizures from wireless inertial measurements and muscular activity.
    5. Noachtar S, Rémi J. The role of EEG in epilepsy: a critical review.
                                                                                    In: GLOBECOM 2017 – 2017 IEEE Global Communications
       Epilepsy Behav. 2009;15(1):22–33. doi: 10.1016/j.yebeh.2009.02.035
                                                                                    Conference; Singapore. IEEE; 2017 Dec.
    6. Rasheed K, Qayyum A, Qadir J, et al. Machine learning for predict­
                                                                                21. Vakilna YS, Li X, Hampson JS, et al. Reliable detection of general­
       ing epileptic seizures using EEG signals: a review. IEEE Rev Biomed
                                                                                    ized convulsive seizures using an off-the-shelf digital watch: a
       Eng. 2021;14:139–155. doi: 10.1109/RBME.2020.3008792
                                                                                    multisite phase 2 study. Epilepsia. 2024;65(7):2054–2068. doi: 10.
    7. Hadady L, Robinson T, Bruno E, et al. Users’ perspectives and
                                                                                    1111/epi.17974
       preferences on using wearables in epilepsy: a critical review.
                                                                                22. Jiang P, Gao F, Liu S, et al. Longitudinally tracking personal phy­
       Epilepsia. 2025;66(S3):4–13. doi: 10.1111/epi.18280
                                                                                    siomes for precision management of childhood epilepsy. PLOS
    8. Casanovas Ortega M, Bruno E, Richardson MP. Electrodermal activ­
                                                                                    Digit Health. 2022;1(12):e0000161. doi: 10.1371/journal.pdig.
       ity response during seizures: a systematic review and meta-analy­
       sis. Epilepsy Behav. 2022;134(108864):108864. doi: 10.1016/j.yebeh.
                                                                                23. Arends J, Thijs RD, Gutter T, et al. Multimodal nocturnal seizure
       2022.108864
                                                                                    detection in a residential care setting: a long-term prospective trial.
    9. Baumgartner C, Whitmire LE, Voyles SR, et al. Using sEMG to
                                                                                    Neurology.      2018;91(21):e2010–e2019.        doi:    10.1212/WNL.
       identify seizure semiology of motor seizures. Seizure. 2021;86:52–
       59. doi: 10.1016/j.seizure.2020.11.013
                                                                                24. Wu D, Wei J, Vidal P-P, et al. A novel seizure detection method
   10. Beniczky S, Conradsen I, Pressler R, et al. Quantitative analysis of
                                                                                    based on the feature fusion of multimodal physiological signals.
       surface electromyography: biomarkers for convulsive seizures. Clin
                                                                                    IEEE Internet Things J. 2024;11(16):27545–27556. doi: 10.1109/JIOT.
       Neurophysiol. 2016;127(8):2900–2907. doi: 10.1016/j.clinph.2016.
                                                                                    2024.3398418
       04.017
   11. Baumgartner C, Koren J, Britto-Arias M, et al. Epidemiology and          25. Wang J, Hu D, Lai X, et al. Epileptic seizure detection based on
       pathophysiology of autonomic seizures: a systematic review. Clin             attitude angle signal of wearable device. IEEE Trans Instrum Meas.
       Auton Res. 2019;29(2):137–150. doi: 10.1007/s10286-019-00596-x               2025;74:1–10. doi: 10.1109/TIM.2025.3529058
   12. Atwood AC, Drees CN. Seizure detection devices: five new things.         • Exploring ACC, gyroscope (GYR), surface electromyography
       Neurol Clin Pract. 2021;11(5):367–371. doi: 10.1212/CPJ.                     (sEMG), and EDA modalities, this study introduced derived
       0000000000001044                                                             biomarkers pitch and roll extracted from ACC and GYR data.
   13. Tricco AC, Lillie E, Zarin W, et al. PRISMA extension for scoping            Substituting raw ACC signals with these biomechanical mar­
       reviews(PRISMA-ScR): checklist and explanation. Ann Intern Med.              kers improved model performance across all tested classifiers.
       2018;169(7):467–473. doi: 10.7326/M18-0850                                   Patient-specific experiments on 10 individuals showed that
   14. Wang G, Yan H, Li W, et al. Seizure detection using the wristband            half achieved accuracy exceeding 90engineering in seizure
       accelerometer, gyroscope, and surface electromyogram signals                 detection.
       based on in-hospital and out-of-hospital dataset. Seizure Eur J          26. Vieluf S, Hasija T, Kuschel M, et al. Developing a deep canonical
       Epilepsy. 2025;127:127–134. doi: 10.1016/j.seizure.2025.03.016               correlation-based technique for seizure prediction. Expert Syst
   15. Yu S, El Atrache R, Tang J, et al. Artificial intelligence-enhanced          Appl. 2023;234(120986):120986. doi: 10.1016/j.eswa.2023.120986
       epileptic seizure detection by wearables. Epilepsia. 2023;64             • This study applied Deep Canonically Correlated Autoencoders
       (12):3213–3226. doi: 10.1111/epi.17774                                       (DCCAE) with three architectures, fully connected, CNN-based,
   •• This study involved 166 pediatric patients in inpatient settings              and gated recurrent units, to differentiate pre-ictal from inter­
       and did not perform real-time analysis. It proposed a CNN-                   ictal periods through unsupervised clustering. Results demon­
       LSTM fusion model utilizing accelerometry (ACC) and photo­                   strated the DCCAE framework’s ability to accurately segment
       plethysmography (PPG), which was the best performing algo­                   seizure-related periods using autonomic sensor data, high­
       rithm overall. It achieved a sensitivity of 83.9seizure types,               lighting its potential for seizure forecasting without requiring
       improving to 95tonic-clonic seizures (GTCS), and detected 19                 labeled data.
       out of 28 seizure types. The study highlights the promise of             27. Vieluf S, Cantley S, Jackson M, et al. Development of a multivariable
       multimodal biosignals combined with deep learning for com­                   seizure likelihood assessment based on clinical information and
       prehensive seizure detection.                                                short autonomic activity recordings for children with epilepsy.

424       A. WESAL ET AL.


      Pediatr Neurol. 2023;148:118–127. doi: 10.1016/j.pediatrneurol.           37. Hamlin A, Kobylarz E, Lever JH, et al. Assessing the feasibility of
      2023.07.018                                                                   detecting epileptic seizures using non-cerebral sensor data.
  28. Meisel C, El Atrache R, Jackson M, et al. Machine learning from               Comput Biol Med. 2021;130(104232):104232. doi: 10.1016/j.comp
      wristband sensor data for wearable, noninvasive seizure fore­                 biomed.2021.104232
      casting. Epilepsia. 2020;61(12):2653–2666. doi: 10.1111/epi.              38. Chowdhury MEH, Khandakar A, Alzoubi K, et al. Wearable real-time
      16719                                                                         epileptic seizure detection and warning system. In: Murugappan M,
  •• Using the Empatica E4 device’s ACC, PPG, EDA, and TEMP                         Yuvaraj R, editors. Biomedical signals based computer-aided diag­
      sensors, this study investigated seizure forecasting via                      nosis for neurological disorders. Cham: Springer International
      LSTM neural networks. Combining all sensor modalities                         Publishing; 2022. p. 233–265.
      yielded the best performance, achieving statistically signif­             39. Ali SN, Alam MJ. Development of a wearable 3-risk factor accumu­
      icant seizure forecasting in 30 out of 69 patients, with a                    lated epileptic seizure detection system with IoT based warning
      mean sensitivity of 75.6horizon of 31.6 minutes. This high­                   alarm. In: 2020 IEEE 5th International Conference on Computing
      lights the complementary value of multiple physiological                      Communication and Automation (ICCCA); Greater Noida, India.
      signals for effective seizure prediction.                                     IEEE; 2020 Oct.
  29. Milosevic M, Van de Vel A, Bonroy B, et al. Automated detection of        40. Hegarty-Craver M, Kroner BL, Bumbut A, et al. Cardiac-based detec­
      tonic–clonic seizures using 3-D accelerometry and surface electro­            tion of seizures in children with epilepsy. Epilepsy Behav. 2021;122
      myography in pediatric patients. IEEE J Biomed Health Inf. 2016;20            (108129):108129. doi: 10.1016/j.yebeh.2021.108129
      (5):1333–1341. doi: 10.1109/JBHI.2015.2462079                             41. Ge Y, Jiang T, Gao F, et al. Epilepsy analysis with portable device
  • Investigating optimal sensor placement, this study used four                    based multi-modal physiological signals. In: 2023 38th Youth
      wired ACC sensors and two sEMG sensors placed on wrists,                      Academic Annual Conference of Chinese Association of
      ankles, and biceps, applying a least squares support vector                   Automation (YAC); Hefei, China. IEEE; 2023 Aug.
      machine (LS-SVM) for classification. Findings suggested that              42. Dong C, Ye T, Long X, et al. A two-layer ensemble method for
      the left wrist and right ankle are ideal for ACC placement,                   detecting epileptic seizures using a self-annotation bracelet with
      while bilateral biceps provide optimal sEMG signal locations.                 motor sensors. IEEE Trans Instrum Meas. 2022;71:1–13. doi: 10.
      This provides critical guidelines for wearable sensor configura­              1109/TIM.2022.3173270
      tion to balance wearability and detection accuracy.                       • This study used ACC and GYR data collected in outpatient set­
  30. Wang Q, Zhao H, Wang X, et al. Daily epileptic seizure detection              tings from seven patients. Employing a two-layer ensemble
      algorithm based on multi-modal physiological signals. In: 2022 5th            method stacking multiple base learners—random forest (RF),
      International Conference on Communication Engineering and                     extra trees, gradient boosting decision trees, and AdaBoost—it
      Technology (ICCET); Shanghai, China. IEEE; 2022 Feb.                          demonstrated superior performance compared to single-layer
  31. De Cooman T, Varon C, Van de Vel A, et al. Comparison and                     models, emphasizing the efficacy of ensemble approaches in
      combination of electrocardiogram, electromyogram and accelero­                enhancing seizure detection accuracy.
      metry for tonic-clonic seizure detection in children. In: 2018 IEEE       43. Chen H, Wang Z, Lu C, et al. Neonatal seizure detection using a
      EMBS International Conference on Biomedical & Health Informatics              wearable multi-sensor system. Bioengineering. 2023;10(6):658. issn:
      (BHI); Las Vegas, (NV), USA. IEEE; 2018 Mar.                                  2306–5354. doi: 10.3390/bioengineering10060658
  32. Poh MZ, Loddenkemper T, Reinsberger C, et al. Convulsive seizure          44. Ziobro J, Pilon B, Wusthoff CJ, et al. Neonatal seizures: new evi­
      detection using a wrist-worn electrodermal activity and accelero­             dence, classification, and guidelines. Epilepsy Curr. 2024;24(3):
      metry biosensor. Epilepsia. 2012;53(5):e93–7. doi: 10.1111/j.1528-            e375–e389. doi: 10.1177/15357597241253382
      1167.2012.03444.x                                                         45. Ismail S, Akram U, Siddiqi I. Heart rate tracking in photoplethysmo­
  •• This study showed that a semi-patient-specific approach, incor­                graphy signals affected by motion artifacts: a review. EURASIP J
      porating prior seizure examples from the test patient into                    Adv Signal Process. 2021;2021(1). doi: 10.1186/s13634-020-00714-2
      training data, increased sensitivity from 88inpatient environ­            46. Barot N, Nei M. Autonomic aspects of sudden unexpected death in
      ments, the study also successfully introduced extensive real-                 epilepsy (SUDEP). Clin Auton Res. 2019;29(2):151–160. doi: 10.1007/
      world non-seizure data to mitigate false alarm rates, yielding                s10286-018-0576-1
      more reliable performance estimates.                                      47. Mohammadpour Touserkani F, Tamilia E, Coughlin F, et al.
  33. Larsen SA, Johansen DH, Beniczky S. Automated detection of tonic              Photoplethysmographic evaluation of generalized tonic-clonic sei­
      seizures using wearable movement sensor and artificial neural net­            zures. Epilepsia. 2020;61(8):1606–1616. doi: 10.1111/epi.16590
      work. Epilepsia. 2024;65(9):e170–e174. doi: 10.1111/epi.18077             48. Friedman D. Sudden unexpected death in epilepsy. Curr Opin
  34. Li W, Sheng D, Wang G, et al. Generalized tonic-clonic seizure                Neurol. 2022;35(2):181–188. doi: 10.1097/WCO.0000000000001034
      detection through the use of physiological signals. In: 2022 3rd          49. Kumar A, Aelgani V, Vohra R, et al. Artificial intelligence bias in
      International Conference on Pattern Recognition and Machine                   medical system designs: a systematic review. Multimed Tools Appl.
      Learning (PRML); Chengdu, China. IEEE; 2022 Jul.                              2023;83(6):18005–18057. doi: 10.1007/s11042-023-16029-x
  35. Xu G, Chen C, Wang J, et al. Total tonic clonic seizure recognition of    50. Jahanbekam A, Baumann J, Nass RD, et al. Performance of ECG-
      wrist signals. In: 2022 3rd International Conference on Information           based seizure detection algorithms strongly depends on training
      Science, Parallel and Distributed Systems (ISPDS); Guangzhou,                 and test conditions. Epilepsia Open. 2021;6(3):597–606. doi: 10.
      China. IEEE; 2022 Jul.                                                        1002/epi4.12520
  36. Cogan D, Birjandtalab J, Nourani M, et al. Multi-biosignal analysis for   51. Conradsen I, Beniczky S, Wolf P, et al. Seizure onset detection
      epileptic seizure monitoring. Int J Neural Syst. 2017;27(1):1650031.          based on a uni- or multi-modal intelligent seizure acquisition
      doi: 10.1142/S0129065716500313                                                (UISA/MISA) system. In: 2010 Annual International Conference of
  • Using a rule-based method, this study developed a multi-biosignal               the IEEE Engineering in Medicine and Biology; Buenos Aires. IEEE;
      seizure detection pattern defined by a sequence of heart rate                 2010 Aug.
      increase, followed by a decrease in blood oxygen saturation               52. Vijay E, Jati A, Dayama P, et al. Tiny time mixers (TTMs): fast pre-
      (SpO2), and then a rise in electrodermal activity (EDA). This                 trained models for enhanced zero/few-shot forecasting of multi­
      approach achieved 100tonic-clonic seizures (GTCS), showcasing                 variate time series. In: Globerson A, editor. 38th International
      that well-designed physiological rule-based heuristics can sup­               Conference on Neural Information Processing Systems. NIPS ’24;
      plement machine learning methods inwearable devices.                          Vancouver, (BC), Canada. Curran Associates Inc; 2025.
```
