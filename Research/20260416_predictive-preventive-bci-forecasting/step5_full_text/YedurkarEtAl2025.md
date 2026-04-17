---
citation_key: "YedurkarEtAl2025"
paper_id: "paper_291"
title: "SPA-IoT with MCSV-CNN: a novel IoT-enabled method for robust pre-ictal seizure prediction."
authors: "Dhanalekshmi Prasad Yedurkar; Shilpa P Metkar; Thompson Stephan; Vijay Mohan; Saurabh Agarwal"
year: 2025
doi: "10.1186/s12911-025-03191-5"
source: "publisher-pdf (doi: 10.1186/s12911-025-03191-5)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# SPA-IoT with MCSV-CNN: a novel IoT-enabled method for robust pre-ictal seizure prediction.

**Citation:** `YedurkarEtAl2025` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1186/s12911-025-03191-5](https://doi.org/10.1186/s12911-025-03191-5)
**Source PDF:** `full_pdf/Dhanalekshmi2025.pdf`

## Abstract

This paper introduces a new approach to real-time epileptic seizure prediction using a lightweight Convolutional Neural Network (CNN) architecture and multiresolution feature extraction from electroencephalogram (EEG) recordings. Multiresolution Critical Spectral Verge CNN (MCSV-CNN), the suggested model, is best suited for use in wearable technology that is connected to the Internet of Things (IoT). The software module uses pre-ictal and inter-ictal EEG segments to forecast seizures early, and the signal acquisition module collects EEG data. Multiscale frequency analysis and spatial feature learning are combined in the MCSV-CNN architecture to capture minute signal changes that precede seizures. Both actual clinical EEG recordings and the Temple University Hospital EEG Seizure Corpus (TUH-EEG) were evaluated. Predicting has been performed using a 5-minute pre-ictal window and a 10-minute seizure occurrence prediction (SOP) horizon. The approach proposed outperformed a number of existing CNN-based seizure prediction techniques with an average prediction accuracy of 99.5%, sensitivity of 98.3%, false prediction rate of 0.045, and a high Area Under the Curve (AUC). These findings show that MCSV-CNN has the potential to be a dependable, real-time seizure prediction tool that could be used practically in wearable medical technology. The prediction accuracy and lightweight architecture of the technology point to its potential application in early clinical intervention and ongoing at-home monitoring.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Yedurkar et al. BMC Medical Informatics and Decision Making                            (2025) 25:354                                                                BMC Medical Informatics
https://doi.org/10.1186/s12911-025-03191-5
                                                                                                                                                                      and Decision Making


 RESEARCH                                                                                                                                                                                       Open Access


SPA-IoT with MCSV-CNN: a novel IoT-enabled
method for robust pre-ictal seizure prediction
Dhanalekshmi Prasad Yedurkar1, Shilpa P. Metkar2, Thompson Stephan3, Vijay Mohan4* and Saurabh Agarwal5*


 Abstract
 This paper introduces a new approach to real-time epileptic seizure prediction using a lightweight Convolutional
 Neural Network (CNN) architecture and multiresolution feature extraction from electroencephalogram (EEG)
 recordings. Multiresolution Critical Spectral Verge CNN (MCSV-CNN), the suggested model, is best suited for use
 in wearable technology that is connected to the Internet of Things (IoT). The software module uses pre-ictal and
 inter-ictal EEG segments to forecast seizures early, and the signal acquisition module collects EEG data. Multiscale
 frequency analysis and spatial feature learning are combined in the MCSV-CNN architecture to capture minute
 signal changes that precede seizures. Both actual clinical EEG recordings and the Temple University Hospital EEG
 Seizure Corpus (TUH-EEG) were evaluated. Predicting has been performed using a 5-minute pre-ictal window
 and a 10-minute seizure occurrence prediction (SOP) horizon. The approach proposed outperformed a number
 of existing CNN-based seizure prediction techniques with an average prediction accuracy of 99.5%, sensitivity of
 98.3%, false prediction rate of 0.045, and a high Area Under the Curve (AUC). These findings show that MCSV-CNN
 has the potential to be a dependable, real-time seizure prediction tool that could be used practically in wearable
 medical technology. The prediction accuracy and lightweight architecture of the technology point to its potential
 application in early clinical intervention and ongoing at-home monitoring.
 Keywords Seizure prediction, EEG, IoT, Deep learning, Multiresolution critical spectral verge


                                                                                                          Introduction
                                                                                                          Health and wellness surveillance systems that operate in
                                                                                                          the realm of IoT make it possible to monitor individuals
                                                                                                          continuously, especially in the case of chronic conditions
                                                                                                          and long-term surveillance applications like epileptic sei-
*Correspondence:                                                                                          zures (ES) [1], [2]. IoT, through its multiple sensors and
Vijay Mohan
vijay.mohan@manipal.edu                                                                                   networks, plays a crucial role in creating a direct line of
Saurabh Agarwal                                                                                           communication of medical information between medical
saurabh@yu.ac.kr                                                                                          sensors and devices attached to patients and medical per-
  School of Computing, MIT Art Design & Technology University, Pune,
India                                                                                                     sonnel. In doing so, it provides continuous medical moni-
  Department of Electronics & Telecommunication and Engineering, COEP                                     toring of very significant seizure data of patients like the
Technological University, Pune, India                                                                     pre-ictal (PIL) state [3], [4]. Information such as this is
  Thumbay College of Management and AI in Healthcare, Gulf Medical
University, Ajman, United Arab Emirates                                                                   extremely useful in the remote prediction of the occur-
  Department of Mechatronics, Manipal Institute of Technology, Manipal                                    rence of seizures, thus facilitating immediate and pre-
Academy of Higher Education, Manipal, Karnataka 576104, India                                             emptive assistance. Epilepsy is known to be a lingering
  School of Computer Science and Engineering, Yeungnam University,
Gyeongsan 38541, Republic of Korea                                                                        neurological disease that afflicts nearly 70 million human


                                       © The Author(s) 2025. Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use,
                                       sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and
                                       the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this
                                       article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included
                                       in the article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will
                                       need to obtain permission directly from the copyright holder. To view a copy of this licence, visit ​h​t​t​p​​:​/​/​​c​r​e​a​​t​i​​v​e​c​​o​m​m​​o​n​s​.​​o​r​​g​/​l​i​c​e​n​s​e​s​/​b​y​/​4​.​0​/.

Yedurkar et al. BMC Medical Informatics and Decision Making           (2025) 25:354                                                 Page 2 of 17


Fig. 1 Summary of research in the direction of prediction of epileptic seizure


Fig. 2 An overview of the quantitative comparisons presented in earlier studies

beings the world over [5]. Seizure prediction (SP) is per-                       begun to concentrate on the inter-relationship that exists
formed by identifying the pre-seizure (PIL) region, a few                        between multichannel EEG seizure signals [6], [9].
minutes to seconds before the seizure onset, from the                              Deep learning (DL) algorithms are also very useful in
EEG recordings. Predicting ES is crucial for several rea-                        the prediction of ES as they are able to identify PIL EEG
sons, and it can greatly enhance the lives of people with                        segments. One type of DL is the Convolutional Neural
epilepsy [6]. Here are some key reasons why predicting                           Network (CNN) [10]. According to research by [11],
ES is essential: i. early intervention and treatment plan-                       CNN time domain analysis is used to operate a fully
ning; ii. Enhancing safety; iii. Improving quality of life;                      portable, wireless, flexible scalp electronic system in the
iv. Reducing side effects of medication; v. Optimizing                           occipital lobe. Here, a high information transfer rate has
healthcare resource utilization; vi. Enabling personal-                          been achieved by a two-channel scalp electronic system
ized treatment; vii. Facilitating research and understand-                       with six human participants, enabling real-time EEG cat-
ing; and viii. Empowering epileptic individuals. Although                        egorization. Truong et al. proposed a scheme based on
there have been major advances in SP, predicting seizures                        CNN. The input to this CNN is the extricated short-time
with high accuracy remains a complex challenge, and                              Fourier transform (STFT) time-frequency map for the
ongoing research is essential to improve prediction capa-                        identification of PIL as well as inter-ictal (IIL) stages [12].
bilities. Figs. 1 and 2 summarize prior research in this                         Based on STFT CNN, uses 2D CNN to classify EEG seg-
direction.                                                                       ments after extracting spectrograms from them. Despite
   Currently, various algorithms are used to predict the                         their effectiveness, they are computationally demanding
epileptic seizure state. The most prevalent types of algo-                       and necessitate precise window selection. Wavelet-based
rithms include time domain, frequency domain, a com-                             CNNs provide better temporal resolution; however, they
bination of frequency-time domain, and non-linear                                are often patient-specific and susceptible to interference
approaches. Out of all the methods that are used, the                            [13].
frequency spectral analysis has been fairly successful [7].                        Khan et al. proposed an epileptic prediction technique
Correlation dimension, Lyapunov exponent, and approxi-                           based on wavelet transform and CNN, utilizing scalp
mate entropy are techniques that have been employed                              EEG electrodes [13]. Ozcan et al. predicted seizures
in feature analysis of the prediction of ES [8]. Besides                         by using spectral band power, statistical moment, and
the single-channel analysis of EEG, current research has                         Hjorth parameters as input to a 3D-CNN model, which

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                           Page 3 of 17


had a multi-frame [14]. Zhang et al. were authors of an              operate in real-time, particularly in edge-computing
innovative solution for predicting ES, making use of a               scenarios. Third, many methods rely on black-box deep
shared spatial pattern along with CNN to enhance the                 networks without incorporating physiologically mean-
total accuracy even as the technique reduces the time                ingful features or robust artifact filtering, which limits
taken for training [15]. Additionally, research has been             clinical interpretability and can degrade performance in
undertaken to develop wearable EEG devices [16], [17],               noisy real-world EEG. Taken together, these gaps high-
[18], [19]. The following observations are presented in              light the need for a seizure prediction framework that:
regard to the literature review: There is little proof that          a) captures EEG information at multiple temporal and
seizure prediction algorithms are clinically applicable,             frequency scales, b) supports efficient, real-time deploy-
despite the fact that many of them have been devel-                  ment on wearable or mobile platforms, and c) enhances
oped and tested on benchmark datasets. The majority                  interpretability and robustness to artifacts. In particular,
of models undergo retrospective testing with carefully               sensor placement and attack problems introduce spa-
labeled data under controlled conditions, which might                tial and spectral inconsistencies, which degrade the reli-
not accurately reflect the unpredictability and diver-               ability of prediction systems. These existing models lack
sity of actual clinical settings. Furthermore, only a small          mechanisms to extract robust features across multiple
number of these algorithms have been used in continu-                time–frequency scales adaptively and are vulnerable to
ous, real-time monitoring scenarios with wearable EEG                adversarial signals or signal misplacement. To address
sensors or verified in prospective clinical studies. Their           these challenges, we propose the MCSV-CNN archi-
current usefulness in practice is limited by this lack of            tecture, which combines Multiresolution convolutional
clinical validation, which emphasizes the need for meth-             subbands and voting strategies to ensure robustness to
ods that are reliable, understandable, and appropriate for           Seizure Prediction Accessment (SPA)-induced variations,
inclusion into real-time healthcare systems. This is a sig-          improved generalization across sensor placements, and
nificant drawback in the domain of predicting seizures.              better resilience to low-SNR or corrupted data segments.
Both wavelet and STFT-based CNN seizure prediction                   In response, this work proposes an MCSV-CNN, which
techniques frequently have low feasibility across data,              integrates adaptive multiresolution analysis with sub-
substantial processing rates, and sensitivity to artifacts.          band energy encoding to reflect the EEG signal struc-
Moreover, there is also much room for improvement                    ture better while maintaining deployment feasibility.
in the development of enhanced DL-based classifiers.                 This architecture aims to bridge the gap between theo-
Besides, the most crucial area that is missed in the cur-            retical prediction performance and real-world clinical
rent studies is developing an integrated and automated               applicability.
SP system. Such a system can assist with the prediction,                The above-mentioned literature survey is ample moti-
diagnosis, and analysis of an oncoming seizure. Hence,               vation for the authors to come up with a proposal namely,
there is a need to focus on developing wearable devices              the SPA-IoT system, with the following main objectives:
that are both handy and compatible with automated sys-               i) To propose a DL-based SPA system using an EEG sig-
tems via the IoT. Multiresolution critical spectral verge            nal and classifying it into PIL and IIL states; ii) To come
(MCSV)-CNN is a lightweight deep learning model that                 up with an automated IoT based SPA system for real-
makes use of multi-channel statistical variability data in           time analysis; and iii) To improve the false prediction rate
order to overcome these drawbacks.                                   (FPR), sensitivity (SEN), and accuracy (ACC) of the pro-
  While prior work has demonstrated the feasibility                  posed SPA-IoT system.
of using DL methods, such as STFT-based CNN and                         An enhanced aspect of the presented investigation
wavelet-based CNN, for seizure prediction from EEG                   is the prediction of EEG seizures using a novel method
signals, these approaches still face several critical limi-          known as MCSV in conjunction with a CNN methodol-
tations. Firstly, fixed-resolution transforms like STFT              ogy known as MCSV-CNN for an integrated IoT system.
struggle to effectively capture the nonstationary and                Since wavelet-based multiresolution analysis can record
multiscale nature of pre-ictal EEG dynamics. Although                brief, nonstationary events across several frequency
wavelet transforms offer multiresolution capabilities,               bands, it is especially well-suited for diagnosing EEG
many implementations use hand-crafted or rigid decom-                seizures. Wavelets offer adjustable time-frequency reso-
position schemes, which may not generalize to patients               lution, providing high frequency resolution for gradual
or types of seizures. Secondly, existing models often pri-           drifts and high temporal accuracy for fast oscillations,
oritize accuracy in offline settings, neglecting important           in contrast to the fixed window limits provided by STFT.
constraints such as real-time processing, energy effi-               DL models like CNN can use rich multiscale patterns
ciency, and memory footprint, all of which are essential             that indicate pre-ictal activity by converting EEG signals
for on-device inference in wearable IoT systems. Few                 into wavelet scalograms. This improves predicted accu-
studies rigorously evaluate whether such models can                  racy and generalization across patients. By extracting

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                           Page 4 of 17


the PIL zone from the recordings of a multichannel EEG               environments where access to both knowledge and treat-
signal for each segment, the experimental findings dem-              ment is limited. Sect. 2 explains the methodology of the
onstrate that this method is capable of predicting ES self-          suggested epileptic SP. Sect. 3 is dedicated to analyzing
sufficiently. In doing so, it will develop the capability to         and exploring each segment of the multichannel EEG sig-
handle and analyze huge volumes of seizure information.              nal prediction results. Sect. 4 discusses the outcomes of
MCSV-CNN will do this by utilizing the MCSV feature                  such predictions and compares the MCSV scheme with
that employs a bio-inspired algorithm (BI), like the flower          other SP techniques. Sect. 5 outlines the general conclu-
pollination method (FPM) [20]. Additionally, FPM aids                sion, highlighting the broader implications of the work.
in pinpointing the precise location where ES occurs by
performing local and global pollination schemes. Hence,              Methodology
FPM is chosen for the proposed SPA unit. The tech-                   Problem formulation
nique proposed in this research has been tested against              Let X(t) ∈ RC×T denote a multichannel EEG segment of
data from a publicly available database. It has also been            duration T recorded across C electrodes. Each segment
verified against an epileptic signal that was recorded in            is labeled as y ∈ {0, 1}, where y = 1 represents a preictal
a local hospital in real time. In accordance with the pro-           window (that is, before a seizure) and y = 0 denotes an
posed MCSV-CNN IoT approach, the SPA technique                       interictal state (nonseizure).
seeks to assist physicians and medical personnel by pro-               The goal is to learn a function fθ : RC×T → {0, 1} such
viding precise diagnoses and offering appropriate ther-              that the predicted label ŷ = fθ (X(t)) approximates the
apy, as well as to prevent seizures in epileptic patients by         true seizure state:
means of timely prediction. While the proposed MCSV-
CNN shares structural similarities with the ensemble                                     ŷ = fθ (X(t)) ≈ y
and multi-path CNN reported in prior literature, its
novelty lies in the integration of multiresolution sub-              The model is trained to:
band decomposition directly into the learning pipeline.
Unlike conventional CNNs that operate on raw or sin-                   i. Accurately identify pre-ictal windows within a
gle-resolution EEG inputs, MCSV-CNN processes mul-                          specified Seizure Prediction Horizon (SPH);
tiple frequency-specific representations in parallel, each             ii. Minimize false positives per hour (FPR/h); and
learned through a dedicated convolutional stream. These                iii. Generalize across multiple patients and recording
frequency bands are not manually engineered but are                         conditions.
derived using adaptive multiresolution filtering, allowing
the model to learn frequency-dependent patterns more                 Proposed SPA-IoT enabled EEG telemetry framework
effectively. A majority-voting fusion layer aggregates out-          The SPA-IoT framework is made up of three units: i) the
puts across these parallel streams, enhancing robustness             EEG signal sensing unit, ii) the SPA unit, and iii) data
to noise and inter-subject variability. Additionally, the            analysis of PIL and IIL zones in conjunction with the
model is optimized for low-latency inference and light-              transmission unit. The SPA-IoT framework is presented
weight deployment on edge IoT devices, which is rarely               in Fig. 3. This research primarily focuses on designing
addressed in prior seizure prediction CNN architectures.             and implementing a real-time EEG SPA prototype that
  The following are significant contributions of this                makes use of the MCSV-CNN technique and validates
research work: i)Designing and developing the novel                  the effectiveness of the suggested SPA-IoT framework
MCSV-CNN technique to predict seizures based on                      in real-time analysis. To begin with, in the suggested
the EEG data that is obtained, and classifying it into               MCSV-CNN approach, preprocessing of the multichan-
PIL and IIL phases, ii)Demonstrating that it is possible             nel epileptic EEG information is undertaken for each
to implement the proposed SPA-IoT technique in real-                 segment, making use of the multiresolution adaptive fil-
time, making use of EEG sensors, the internet, as well               tering (MRAF) approach [21]. Next, an optimized CSV
as a Raspberry Pi, iii)Demonstrating a distinct enhance-             feature is extracted using FPM. The features that are
ment in the performance of measures used to predict                  extracted are a representation of EEG frequency bands
seizures, like Area Under Curve (AUC), ACC, and also                 such as beta (0.5–4 Hz), theta (4–8 Hz), alpha (8–13 Hz),
FPR for training and testing data taken from an EEG sei-             delta (13–30 Hz), gamma (30–100 Hz), and full bands
zure signal, as compared to the latest techniques used               (0.5–100 Hz or up to 250 Hz). Finally, for every segment,
in this field. The suggested prediction method can be                the frequency data for consecutive segments is sent
a patient-specific seizure warning system that can be                over to CNN so that seizures, if any are present, can be
designed to be simple to wear and that records continu-              predicted.
ously in real time. The suggested approach significantly
lowers the fatality rate of ES, particularly in low-resource

Yedurkar et al. BMC Medical Informatics and Decision Making      (2025) 25:354                                                    Page 5 of 17


Fig. 3 Proposed SPA-IoT framework using MCSV-CNN method for epileptic SP. A high-level overview of the proposed system for predicting pre-ictal
seizure using multiresolution EEG analysis and a lightweight CNN model


Signal sensing modules                                                   files, which provide an in-depth breakdown of every
A standard dataset and a clinical database were utilized                 event, thus specifying what takes place within an individ-
to acquire the epileptic seizure database used in this                   ual channel or groups of channels. Further categorization
work.                                                                    and labeling will be essential to the researcher for data
                                                                         analysis in seeking to identify trends and develop predic-
Standard dataset: TUH-EEG                                                tive models of seizure events. The TUH-EEG dataset was
The standard dataset, TUH-EEG, utilized for analyzing                    selected due to two key factors: the availability of mark-
the proposed new method is made up of records of hun-                    ings indicating the beginning and end of seizures, as well
dreds of patients who have had medically complex partial                 as information regarding the channel label. Since channel
seizures procured from Temple University Hospital Elec-                  labels are crucial for pinpointing the seizure site on the
troencephalography Corpus (TUG-EEG) [22]. The TUH-                       scalp, they are unavailable from other standard datasets.
EEG includes recordings of 21-channel EEG signals. The
recordings also include annotations and are sampled                      Clinical dataset
at a frequency that varies between 250 and 400 Hz with                   A hospital near the city of Pune, India, provided the sec-
a resolution of 16 bits per sample. The data is stored in                ond dataset that helped test and validate the suggested
EDF+, a common electrophysiological signal storage for-                  methodology. The recording device consists of 21 chan-
mat. The annotations in this version of the database are                 nels, sampled at 250 Hz, with electrodes positioned
mostly of two kinds: i) giving the start and end times for               according to the international 10–20 electrode placement
seizure events, also including within themselves detailed                standard. The sensing unit includes built-in hardware for
information about the event, such as channel label and                   initial filtering (0.5–60 Hz bandpass) and artifact sup-
seizure category; ii) providing the classification of the                pression, and transmits data via Bluetooth for real-time
signal, either as normal or abnormal. These are the label                or offline analysis. The unit’s resolution was 16-bit, and it

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                         Page 6 of 17


was capable of detecting subtle pre-ictal variations with            frequency that is procured from the EEG signal is 0.5 Hz
minimal latency, making it suitable for real-time seizure            [10], [19]. Hence, in order to handle the lowest fre-
prediction. Each patient underwent recording sessions,               quency information and on the basis of the pre-experi-
resulting in a dataset that included both interictal and             ment, the authors chose a sliding time window of 1040
pre-ictal segments annotated by experienced clinicians.              points for the EEG signal, or 4 seconds with no overlaps.
Informed consent was obtained from all individual par-                  Details of the EEG signal are frequently impacted by
ticipants included in the study. This dataset was used               the physiological artifacts present [24]. Since physio-
after obtaining permission from the ethical committee. In            logical abnormalities can mask or imitate pre-ictal signs,
the case of EEG recordings that varied from 1 to 8 hours             they provide a significant challenge for EEG-based sei-
and were unipolar, from 5 distinct patients.                         zure identification. Reduced model dependability results
                                                                     from these nonstationary phenomena, which frequently
Seizure prediction and assessment                                    overlap with the frequency bands of interest. Therefore,
In this research, preprocessing is undertaken for the mul-           minimizing artifacts that interfere with the precise iden-
tichannel EEG information for every segment, making                  tification of epileptogenic regions becomes crucial. The
use of MRAF [21]. Next, the MCSV feature is extracted                current research uses MRAF, which combines scale-wise
using FPM. For each of the EEG signal’s frequency bands,             artifact suppression with wavelet-based decomposition,
including theta, alpha, delta, beta, and gamma, the pro-             to address this. This method increases the robustness
posed MCSV technique is applied. In the end, the feature             of downstream seizure prediction models by selectively
set that is thus obtained is fed as input to a CNN model.            attenuating artifact-dominated components while main-
For this research, 05 minutes prior to the onset of a sei-           taining diagnostically significant characteristics [21].
zure was selected as the PIL period.                                    The first step is the decomposition of the input EEG
  The requirement to balance early detection with effec-             data into various frequency levels by employing the
tive response time in real-world clinical and wearable               Discrete Wavelet Transform (DWT). Then, the wave-
IoT uses led to the choice of a 5-minute PIL before sei-             let coefficients at high frequencies are subjected to soft
zure onset. While longer windows, such as the 20-min-                thresholding that has been procured. Soft thresholding is
ute preictal window used in [6], will give longer lead               expressed in Eq. (1) as follows [25]:
periods, they frequently devote a large amount of time                                             √
to post-processing and preventative actions instead of                                   Zl = σl        2log(P )(1)
active forecasting. On the other hand, this study employs
multiresolution EEG characteristics for real-time predic-            The DWT decomposition level is l, σl is the input sig-
tion during the 5-minute timeframe, which allows for                 nal’s standard deviation, and Zl is the threshold value. P
low-latency replies appropriate for wearable deployment.             is the EEG sample. The MRAF technique is subsequently
This period is also in line with results from several recent         employed to produce preprocessed data for the seizure
studies that show the crucial preictal brain dynamics                region. The data generated by this process is represented
typically show up most strongly in the last few minutes              by the following MRAF expression in Eq. (2) [25]:
prior to seizure onset. Therefore, the selected window is
                                                                                                  s−1
not only adequate for accurate seizure prediction but also                                        ∑
optimally suitable for integration into time-sensitive IoT-                       Do (u)pr(b) =         wi (u)di (u − j)(2)
                                                                                                  i=0
based systems.

Preprocessing of EEG signals                                         Here, Do (u)pr(b) represents the output of the MRAF
The multichannel EEG information that is input is                    obtained for each band b. At the output stage, theta,
divided into segments by using a sliding, non-overlapping            delta, alpha, gamma, and beta are incorporated, each
window technique [23]. The sliding window ensures the                corresponding to distinct frequency resolutions, thereby
continuity of the input data. However, it can also result            achieving multiresolution filtering. The term wi (u) sig-
in redundancy of information. This work examined three               nifies the weight associated with the MRAF scheme and
different window sizes - two seconds, four seconds, and              reflects the adaptive filter’s updated components. Mean-
five seconds—analyzing their impact on the outcome                   while, di (u − j) denotes the most recent updates applied
of SP to explore the effect of varying non-overlapping               to the adaptive filter.
window lengths. This analysis revealed that using vari-
ous segment sizes, with or without segment overlap, had              Critical spectral verge computation
no discernible impact on the epileptic recognition out-              The EEG data were preprocessed using the MRAF
comes. Nonetheless, the EEG segment ought not to be so               technique, and feature extraction was performed for
tiny that it takes too long to analyze. Also, the minimum            every EEG signal segment using the proposed MCSV

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                             Page 7 of 17


technique. The proposed MCSV technique is applied to                 The SV point computed above has been taken into
all frequency bands of multichannel EEG data, including              account as a requirement for the classification of seizure
theta, alpha, delta, beta, and gamma. The features have              activities. However, since frequency variations of the sei-
been extracted using the MCSV technique to capture                   zure zones are specific to each patient, there is a possi-
the frequency details in the EEG data and highlight the              bility of misclassification due to misleading frequency
seizure-related information, especially in the high-fre-             points in certain segments. The authors have chosen the
quency regions. Feature extraction starts by calculating             FPM technique as a swarm-based intelligence method
the average power spectral density for each of the men-              for optimization that has been motivated by the way that
tioned frequency bands. PSD is computed for each seg-                blooming plants behave during pollination. To address
ment in these bands. Then, it identifies the point where             the optimization issue, the FPM algorithm requires the
the PSD of a segment exceeds the mean PSD of its fre-                initialization of both the objective function f(d) and the
quency band. The peak point is called the Spectral Verge             initial solution. Eqs (4) and (5) have been combined as
(SV). Because this region contains more noise and arti-              the objective function, and it can be expressed as shown
facts, low-frequency segments may distract from the                  below in Eq. (6):
most critical seizure information. The identified SV is
further enhanced through the FPM to find an accurate                             max{m | m ∈ Y Skb (m) > Y Savg }(6)
seizure detection. This acts as a seed point, taking the
beginning and optimizing it through FPM via Lévy flight.             Therefore, the objective function yields the initial solu-
The Critical SV is the resulting optimised point, which is           tion, which is the best input for the first iteration. The
more accurate and reliable for seizure detection in EEG              next task is to optimise the obtained initial solution to
data.                                                                achieve the ideal fit using the FPM technique. FPM is
  To simplify, let’s call the filtered output per band,              based on the concept of the abiotic process of pollination,
Do (u), as d(u). We split d(u) into segments for extract-            which can be either local or global, to search for the ideal
ing features and refer to it simply as d, dropping the index         match. To highlight the differences between global and
u. The segments of the signal d are defined as follows in            local seizure abnormalities, the FPM algorithm performs
Eq. (3): Let d = {d1 , d2 , . . . , dk }, where k is the segment     repeat passes through both, virtually optimizing the solu-
index.                                                               tion for accurate identification of segments with seizure
                                                                     information using the pollination algorithm.
                                   U                                   The following Eq. (7) is the definition of the best-suited
                              k=      (3)
                                   fs                                solution:

Here, k is the number of EEG segments, fs is the sam-                                        Si = ﬁt∗ (fsi )(7)
pling frequency, and U represents the total number of
segments.                                                            Here, the decision variables vary within the range from 0
  The filtered signal can be divided uniformly in each               to fs, and f it∗ denotes the optimal fitness. Consequently,
band, and this method is applied across each frequency               the solution derived will range from the minimum fre-
band. The average spectral power (SP) is calculated for              quency limit (0Hz) to the maximum frequency limit
all. The SP is evenly dispersed in the high-frequency                (fs ). Reaching the optimal fit requires a consistent solu-
range, particularly in segments with epileptic data.                 tion that surpasses all other possible solutions or shows
  Denote the power spectrum of dk for b as                           the most frequent occurrence in solution generation. The
Y Skb . The set Y Sk can be written as Y Sk = Y Skb (0),             population function map is defined as given by Eq. (8)
Y Skb (1), . . . , Y Skb (m), where m ranges from 0 to fs. Fol-      below for reaching the ideal solution:
lowing this, we compute the average SP.
  We are now focused on identifying a frequency point                                        f : f it∗ → si (8)
m within the range of 0 to fs Hz that fulfils the require-
ments listed below: Requirement 1: If the set of frequen-            where the set of solutions obtained from the optimal map
cies ms is such that:                                                for iteration is denoted by Si. At this stage, FPM can be
                                                                     applied to the population that has previously obtained
            ms = {m | m ∈ Y Skb (m) > Y Savg }(4)                   the solution to achieve the ideal solution. In the end, the
                                                                     optimal solution is identified as the CSV, which is refined
Requirement 2: If the SV point is max(ms ), then:                    from all available solutions on the map. Presently, the
                                                                     CSV for each of the other EEG segments can be similarly
                         SV = max(ms )(5)                           procured and represented by {CSV1 , CSV2 , . . . , CSVn }.
                                                                     The CSV for each of the bands (α), (β), (γ), (θ), (δ), and full

Yedurkar et al. BMC Medical Informatics and Decision Making        (2025) 25:354                                                Page 8 of 17


                                                                          Table 1 Layer-wise architecture of the MCSV-CNN
                                                                          Layer       Type           Ker- Filters   Stride Activation
                                                                                                     nel                   function
                                                                                                     size
                                                                          Input       EEG feature    -    -         -       -
                                                                                      maps
                                                                          Conv1       Conv2D         3 ×3   8       1 ×1    ReLU
                                                                          MaxPool1    MaxPooling2D   2 ×2   -       2 ×2    -
                                                                          Conv2       Conv2D         5 ×5   16      1 ×3    ReLU
                                                                          MaxPool2    MaxPooling2D   2 ×2   -       2 ×2    -
                                                                          Conv3       Conv2D         3 ×3   32      1 ×3    ReLU
                                                                          Flatten     Flatten        -      -       -       -
                                                                          Dense1      Fully          -      256     -       ReLU + Drop-
                                                                                      Connected                             out (0.5)
                                                                          Dense2      Fully          -      128     -       ReLU + Drop-
                                                                                      Connected                             out (0.5)
                                                                          Dense3      Fully          -      2       -       Softmax
                                                                                      Connected


                                                                          is initialized with a convolutional layer (CL), which uses
                                                                          eight kernels of size 3 × 3with a stride of 1 × 1to filter the
                                                                          frequency feature maps across channels. The second is a
                                                                          CL, taking the output of the first with 16 kernels, while
                                                                          the kernel size is 5 × 5, and the stride is 1x3. Connected
                                                                          after the second in the series, the architecture of the third
Fig. 4 Methodology for the CSV feature computing process flow. A pro-     CL contains 32 kernels in each dimension, kernel size
cess flow for computing sub-band EEG features using multiresolution de-   3 × 3with a stride of 1x3. Finally, max-pooling layers are
composition for input into the MCSV-CNN model                             provided after both the first and second convolution lay-
                                                                          ers. Their pool size is chosen to be 2 × 2with a stride of
band (fb) is acquired similarly. Eq. (9) below represents                 2x2.
the feature map that has been generated:                                    The ReLU introduces non-linearity in the process-
                                                                          ing and is used throughout the CLs. Following the con-
                 CSV , CSV , ..., CSV                                   volutional stack, three fully connected layers play a vital
                      α1      α2
                 CSVβ1 , CSVβ 2, ..., CSVβk
                                              αk                         role in distinguishing between the PIL signal and the

                 CSVγ1 , CSVγ 2, ..., CSVγk
                                                                         IIL signal. The final output of the fully connected layer
                 CSV , CSV 2, ..., CSV (9)                             goes through a softmax activation function, which pro-
                      θ1      θ              θk
                 CSVδ1 , CSVδ 2, ..., CSVδk                             duces the probability of being in either the PIL or IIL

                  CSVf b1 , CSVf b2 , ..., CSVf bk                        state. Dropout layers with a rate of 0.5 are added after
                                                                          the first two fully connected layers to avoid overfitting. It
The CSV serves as the ideal map, showing the signal con-                  processes data in batches of 100, uses categorical cross-
nections among EEG segments from 1 to k, as well as                       entropy for loss, and employs Adaptive Moment Esti-
every frequency band that ranges from alpha to full band,                 mation with a 0.001 learning rate for optimization [27].
and the channels of the EEG signal. This work proposes                    Table 1 highlights the layer-wise architecture of the
a method to compute the optimal feature band based on                     MCSV-CNN.
the CSV. Fig. 4 shows the approach for the CSV feature
computation.                                                              Hyperparameter selection
                                                                          The design of the MCSV-CNN architecture was guided
Convolution neural network                                                by domain knowledge in EEG signal processing, empiri-
In the last few years, CNN has significantly evolved in the               cal experimentation, and considerations for deployment
domain of neuro-computing. This is because CNN has                        on resource-constrained wearable devices.
many features that give it an advantage, such as feature
selection, weight sharing, automatic feature extraction,                    i. Kernel size: Small kernel sizes such as 3 × 3 are
and so on. As per the AlexNet network, for this study, a                       effective for capturing local spatial and temporal
six-layer CNN is utilized in order to select features and                      features, particularly transient patterns found in EEG
also for classification [26]. The suggested CNN model                          pre-ictal signals. In the second CL, a kernel 5 × 5

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                           Page 9 of 17


       was used to allow the model to integrate slightly             the efficacy of the suggested framework accurately. For
       more contextual information after initial feature             a particular patient who experienced U seizures, using a
       detection.                                                    hold-out validation technique, the recorded EEG signals
  ii. Stride: The asymmetric stride in the second and                were divided into training and testing sets, allotting 80%
       third CLs (1 × 3) was selected to prioritize temporal         of the data for training and 20% for testing. In order to
       abstraction while preserving the spatial resolution           give the model enough data to identify broad trends and
       across channels. This allows for better alignment             maintain a separate set for objective assessment, this split
       with time-sensitive seizure precursors.                       was selected. Furthermore, in order to increase the per-
  iii. Number of filters: A gradually increasing number              formance measures’ resilience, the split was carried out
       of filters across layers enables the extraction of            again using many other random seeds, and the average
       increasingly complex patterns. Keeping filter counts          performance was published. This methodology ensures
       relatively low, compared to a very deep CNN,                  that the efficacy of the model is not attributable to a par-
       maintains computational efficiency, suitable for              ticular data configuration and aids in assessing its appli-
       wearable implementation.                                      cability to further data.
  iv. Pooling parameters: Max pooling is applied after                 In this study, the CNN was trained using the EEG data-
       the first two CLs to reduce dimensionality while              set, which included labels for the PIL stage occurring
       retaining dominant activations. The 2 × 2 pool size           5 minutes prior to a seizure. The rate of error of the vali-
       with matching stride downscales the input, limiting           dation dataset was computed after each training epoch to
       overfitting and accelerating training.                        confirm whether the CNN overfitted the training dataset.
  v. Dropout: Dropout layers are inserted after the first            The training process was halted when either the maxi-
       two fully connected layers to prevent overfitting,            mum number of iterations was reached or the validation
       particularly important given the limited availability of      error rate increased over ten consecutive training epochs.
       seizure data. A dropout rate of 0.5 is commonly used          In this research work, it was possible to terminate the
       in biomedical CNN applications and was empirically            training process after around 150 iterations. After com-
       found to provide stable validation performance.               pleting the CNN training, the PIL and IIL recordings
  vi. Batch size: A batch size of 100 balances training              from the clinical EEG signals were examined using the
       stability and memory efficiency. Smaller batches led          pre-trained CNN model. Calculation of evaluation mea-
       to noisier gradients, while larger batches showed             sures like ACC, FPR, and SEN followed. The SPA-IoT
       diminished generalization.                                    model was set up on a Raspberry Pi 4 Model 4B. This
  vii. Optimize: Adam was selected for its adaptive                  device features a modern 64-bit quad-core processor that
       learning capabilities and proven performance in non-          operates at 1.5 GHz and includes a metal heat sink. It also
       stationary EEG data settings. A learning rate of 0.001        offers dual-band wireless LAN across 2.4 GHz and 5 GHz
       provided fast convergence without instability.                bands, as well as BLE gigabit Ethernet. The model is
  viii. Activation function: ReLU activation was                     equipped with 8GB of RAM, improved dual-band 802.11
       used in all hidden layers due to its simplicity and           b/g/n/ac wireless LAN, Bluetooth 5.0, and a much faster
       effectiveness in avoiding vanishing gradient issues.          300 Mbit/s Ethernet. In this research, the offline EEG sig-
       The final layer uses a softmax activation to produce a        nals were relayed to the Raspberry Pi 4 via the internet
       normalized probability distribution over the PIL and          on a continuous basis.
       IIL classes.                                                    The following criteria are employed in this study for
                                                                     assessing the effectiveness of the proposed technique in
These choices were supported by preliminary experi-                  quantitative terms:
ments and align with standard practices in EEG-based
DL systems. Future work may explore automated hyper-                                                       TP
                                                                                    Sensitivity(Sen) =           (10)
parameter tuning via Bayesian optimization or neural                                                     TP + FN
architecture search.
                                                                                                      TP + TN
                                                                               Accuracy(Acc) =                     (11)
Data analysis and communication module                                                           TP + FN + TN + FP
The data analysis and communication module is imple-
mented as a lightweight embedded routine running on                                                                FP
                                                                              F alseP redictionRate(F P R) =                (12)
a low-power processor. It performs real-time EEG fea-                                                          T imeP eriod
ture extraction and seizure prediction using the trained
MCSV-CNN model. Predicted events are then communi-                   where TP represents the True Positive;
cated via Bluetooth to a mobile device or caregiver inter-            TN represents the True Negative;
face. The results of the SP were calculated to evaluate               FP is the False Positive; and

Yedurkar et al. BMC Medical Informatics and Decision Making   (2025) 25:354                                          Page 10 of 17


  FN represents the False Negative.                                  measures are applied in a stringent way to keep the net-
                                                                     work environment safe for IoT devices and ensure safe
The sensitivity of the MCSV-CNN prediction model to                  data interaction and sharing.
pre-ictal data has made it possible to measure the classi-
fier’s ability to gather this data. The sensitivity mentioned        Results
above refers to the particular capability of the proposed            In the current study, we analyze seizures predicted by
prediction framework to accurately recognize the pre-                the algorithm developed herein and confirmed by cer-
ictal EEG data as the pre-ictal stage, and this, in turn, is a       tified epileptologists. Our investigation makes use of a
measure of the ability of the classifier to identify the non-        SP characteristic technique and utilizes specific perfor-
pre-ictal information. Accuracy refers to the prediction             mance metrics as delineated by the referenced indices
model’s potential to predict seizures accurately. The algo-          [28]. The focus of our analysis is the SP horizon, which
rithm proposed in this work was tried out on epileptic               is the time between when a seizure warning is issued and
data of a hundred patients who had suffered from more                when the seizure actually begins. SOP stands for seizure
than a hundred seizures in both the TUH-EEG and the                  occurrence period, which is a 10-minute window antici-
clinical EEG datasets.                                               pated for the seizure onset. In the methodology, SPH is
   In addition, for each patient, a separate seizure predic-         assumed to be 5 minutes. Predictive accuracy and early
tion model was trained and tested using their own EEG                detection are balanced by the pre-ictal window selection.
data. Performance metrics were calculated per patient,               Although these decisions are consistent with previous
and results were aggregated to compute overall averages.             research and provide enough time for behavioral reac-
This approach supports personalized seizure prediction,              tions, they might reduce sensitivity to seizures involving
which is more realistic for clinical deployment scenarios.           more gradual or prolonged pre-ictal transitions [28].
                                                                     Additionally, potentially helpful near-miss predictions
System deployment                                                    could be penalized by the stringent SOP cutoff. To bet-
This is deployed on the server powered by Raspberry Pi 4,            ter represent the variation in seizure onset patterns and
which can be reached by web and mobile users with the                enhance clinical value, future research should include
host’s IP address. In the event of any login request sent            dynamic or patient-specific pre-ictal modeling and
by a user, the central server itself can interact with many          graded SOP evaluation.
databases, both online and offline. Users can also use                  An SP is considered accurate if the seizure onset takes
their local databases for offline operations or subscribe            place within the SOP and not during the SPH. An accu-
to certain databases for online procedures. The hosting              rate prediction is recorded as TP. On the other hand,
server provides all the online data services. In this work,          when a seizure happens but is not predicted within the
we connected to the TUH-EEG database, which con-                     time frame of the SOP, it is labeled as an FN. Further-
tained data from a hundred patients. In future work, we              more, not all alarms match real seizure events; if there is
will extend our system by connecting it to more free and             an alarm but no seizure in the SOP, it counts as a false
paid databases. It has been implemented on a Raspberry               positive. Such less-than-perfect predictions are bound to
Pi hosting server with log-in protocols and database                 occur and make this system quite realistic, considering
management. It provides access to EEG data analysis and              SP is a tough problem in reality.
processing tools like MCSV-CNN. This server enables                     Figure 5 depicts the result of SPs. Fig. 5 shows that the
raw EEG data preprocessing, provides analytical tools                MCSV-CNN model accurately predicted that the SOP
for various research purposes, and offers classification             phase came before the PIL phase. This proves that the
and prediction models that are particularly helpful in               method suggested in this work is ideal for predicting sei-
seizure analysis. These are the services provided using              zures accurately and with FPR.
cloud-based solutions. For this purpose, Azure has been                 The sensitivity of the MCSV-CNN prediction model
selected as the main cloud platform. The integration of              to the PIL data enables the measurement of the classi-
Python and YAML scripts helps manage these services                  fier’s ability to gather this data. The specificity mentioned
effectively. Security is of major concern; handled within            above refers to the particular capability of the proposed
a private cloud, it ensures protection for user data and             prediction framework to recognize the PIL EEG data as
database integrity. JFROG does storage management.                   the PIL stage accurately, and this, in turn, indicates how
Additionally, edge computing handles IoT devices, which              well the classifier can recognize the non-PIL informa-
also have their separate sets of security and privacy vul-           tion. ACC is a reference to the potential of the predic-
nerabilities. It not only speeds up data handling and                tion model to predict seizures accurately. The suggested
decision-making but also ensures data backup and secure              scheme is applied to the epileptic data of a hundred
transmission to data centers for further analysis and pro-           patients who had suffered from more than a hundred sei-
longed storage. Pre-deployment encryption and security               zures in both the TUH-EEG and clinical EEG datasets.

Yedurkar et al. BMC Medical Informatics and Decision Making          (2025) 25:354                                                     Page 11 of 17


Fig. 5 Result of SP by capturing the PIL stage in the EEG signal. Outcome of prediction achieved by detecting early EEG patterns during the PIL stage,
enabling timely intervention before seizure onset

Table 2 Performance assessment of SP results                                 research, the AUC was computed to verify how the sug-
Dataset      Purpose       No.of signals      SEN      ACC       FPR         gested SP model performed. A value that is as close to 1
                                              %        %         (/h)        as possible signifies a better performance of the model.
TUH-EEG      Training      100                99       99.8      0.09        The prediction model suggested in this work obtained an
Clinical     Testing       5                  97.6     99.2      0           AUC of 0.9994, which is far greater than any of the recent
Average      -             -                  98.3     99.5      0.045
                                                                             advanced models [22–25]. The dataset was partitioned
                                                                             on a per-patient basis using a leave-one-seizure-out
Table 2 enumerates the results of the SPs made by the                        cross-validation strategy. Specifically, for each patient,
method in this study on all the patients. The average per-                   all but one seizure instance were used for training, and
formance measures reported here are computed by com-                         the held-out seizure formed the test set. This approach
bining evaluations on both the standard and clinical EEG                     was repeated iteratively for all seizures, and average met-
datasets. However, to ensure clarity and transparency,                       rics were reported. To test generalizability, an additional
we emphasize that the model was trained and validated                        cross-subject evaluation was performed in which data
separately on each dataset - no inter-dataset mixing                         from all but one patient were used for training, and the
occurred during training.                                                    model was tested on the unseen patient. Data balancing
   Although the results report average performance met-                      was ensured across the PIL and IIL classes in both train-
rics, the system was designed for patient-specific sei-                      ing and test sets. All segments were padded or truncated
zure prediction. That is, a separate model was trained                       to fixed lengths before input into the model.
and evaluated for each patient using only their own EEG                         The outcome of the experiments conducted in this
recordings. The final performance metrics (ACC, SEN,                         study reveals that the SPA that is based on the MCSV-
FPR) were then averaged across all patients to provide                       CNN can obtain an FPR of 0.045 per hour. This number
an overall assessment. This individualized modeling                          is higher than that achieved by prediction techniques
approach aligns with previous work, acknowledging the                        currently in use [22–25]. Experimentation has revealed
high variability between patients in seizure patterns. No                    that the proposed technique performs better when there
single patient was selected to represent performance. No                     are high positive rates with lower false alarms. The con-
data mixing across patients was done.                                        clusion that can be derived is that the proposed approach
   The average SEN of the SP for each of the one hun-                        is able to predict seizures for epileptic patients effectively.
dred patients was 98.3%. The average FPR was 0.045 per
hour. The training and testing of the model took 150                         System deployment
epochs, achieving a testing ACC of 0.9898%. Up until                         Wearable integration and real-time performance are key
84 epochs, the percentage of the training ACC of the                         design considerations for the suggested seizure predic-
model was almost 0.9%. Beyond that, there was a small                        tion system. To guarantee continuous monitoring, EEG
rise in the ACC of around 0.02%. It was observed that                        data are obtained via a multi-channel wearable sensor
from 105 epochs to 150 epochs, no additional improve-                        and processed in overlapping windows. Important fea-
ment was noticed in the ACC. Beyond training for 150                         tures are effectively extracted without requiring exten-
epochs, the development loss of the algorithm increased                      sive preprocessing. Fast DWT is used in wavelet-based
slightly, and there was a small decrease in its training                     extensions to acquire multiscale representations with
loss. Still, it nearly leveled off, indicating that, most likely,            low latency. These characteristics are loaded into a low-
the model was under-fitting the data. The AUC is a sig-                      resource platform-optimized lightweight MCSV-CNN,
nificant curve for measuring the prediction model. In this                   which achieves inference on embedded hardware in

Yedurkar et al. BMC Medical Informatics and Decision Making            (2025) 25:354                                                        Page 12 of 17


30–50 ms per window. Real-time operation with mini-                            data is 590 milliamps (mA). It is verified that the CNN
mum processing overhead and excellent temporal resolu-                         model consumes less power for computation than other
tion is made possible by this approach.                                        methods, such as support vector machine, k-nearest
  Figure 6 shows the predicted output using the seizure                        neighbor, and K-means clustering. This is because the
analysis application (App). The average SPA latency                            Raspberry Pi’s CPU is completely ( > 90%) occupied for
reported in this study is 0.93 seconds. This latency                           processing an EEG segment throughout the prediction
accounts for the preprocessing, extraction of high-fre-                        phase. Hence, the proposed technique normalizes energy
quency oscillations (HFO) from the seizure signal, and                         consumption in comparison to other methods.
the use of a CNN for segment-by-segment prediction.
The energy consumption for the transmission of the EEG


Fig. 6 Result of SP by capturing the PIL stage in the EEG signal. Prediction outcome is derived by analyzing EEG signals during the PIL stage to anticipate
seizures before onset

Yedurkar et al. BMC Medical Informatics and Decision Making      (2025) 25:354                                          Page 13 of 17


Ablation study                                                          band of the incoming EEG signal contains varying yet
To better understand the contribution of individual com-                useful information that can be utilized in SP, integrating
ponents of the MCSV-CNN architecture, we conducted                      these features provides the CNN model with additional
an ablation study by systematically removing or modify-                 MCSV characteristics to categorize into IIL and PIL
ing key modules:                                                        recordings. Therefore, the suggested technique signifi-
                                                                        cantly enhances the outcome of SP.
  i. Without Multiresolution Filtering: Replacement
       of multiresolution input with raw EEG degraded the               Inequality analysis of PIL data
       performance by 94.1%, confirming the importance of               In the EEG data received from epilepsy patients, PIL epi-
       subband representations;                                         leptic zones are normally much shorter than IIL epileptic
  ii. Without Sub-band Voting: Aggregating outputs                      areas. As observed by the outcome of the experiments in
       through simple averaging, instead of majority voting,            this study, it was observed that the ratio of the IIL area
       resulted in a drop in sensitivity and increased FP; and          to the PIL area is very high at 15:1. The imbalance in
  iii. Shallower CNN: Reducing convolutional layers led                 the data made the data unsuitable for training the CNN
       to poorer generalization in clinical datasets.                   model due to the inadequacy in learning for samples of
                                                                        the minority class (PIL zones). To overcome the hurdles
These results highlight that both the multiresolution                   arising from class imbalance, data resampling techniques
decomposition and the structured subband voting mech-                   were utilized [29, 30]. Out of the currently available
anism are key to the robustness and accuracy of MCSV-                   methods, three techniques were selected, namely, ran-
CNN [Table 3].                                                          dom oversampling (ROS), borderline synthetic minority
                                                                        oversampling technique (bSMOTE), and random unders-
Discussion                                                              ampling (RUS) [31].
Results of seizure prediction for various frequency bands                 For ROS, the average Acc was 99.5%, and the SEN was
of EEG                                                                  98%. The bSMOTE achieved an average Acc of 97.1% and
MCSV is mainly found in the higher frequency bands                      an average SEN of 92%. RUS attained an average Acc of
in the case of IIL recordings. However, in the case of                  89.1% and a SEN of 88%. It was observed that there were
PIL recordings, the distribution of the MCSV is even in                 no major variations in the Acc values between ROS and
both the low and the high-frequency bands. To explore                   bSMOTE in relation to SP results. These observations
the impact of different frequency bands on SP results,                  have led to the conclusion that using DL to overcome
features from various EEG bands were incorporated into                  class imbalance issues in seizure prediction would make a
the CNN to aid in seizure prediction. Once MCSV ana-                    sampling method like ROS a more convenient and easier
lyzes the EEG signals, a feature map that fits in a 0.1 Hz              technique compared to other methods, such as bSMOTE
frequency resolution is fed as input to the CNN. The                    and RUS.
size of such a feature map was 21 ×the number of seg-
ments that contained the specific frequency components                  Seizure behavior in scalp
like δ (0–4 Hz), θ (4–8 Hz), α (8–13 Hz), β (13–30 Hz),                 The EEG topographic representation of the spread of
γ − 1 (30–70 Hz), γ − 2 (70–128 Hz), and fb respec-                     spectrum in various frequency bands and sub-bands
tively. The average SEN of SP of seven frequency bands                  throughout the PIL and IIL phases is highlighted in Fig. 7.
was 71.23%, 82.3%, 85.8%, 85.5%, 87.2%, 89.9%, and                      Important details regarding the structure and operation
97.7%, respectively. The average ACC was 80.2%, 86.6%,                  of the brain are learned from topographic organization.
87.3%, 82.3%, 94.3%, 94.9%, and 98.9% respectively. How-                More significant values in the ictal state are indicated by
ever, the ACC outcome of SP making use of the entire                    red, while an ictal-free condition is indicated by blue. The
frequency band of the signal was significantly higher in                spread of seizure activity (IIL state) in the relevant brain
comparison to just the six bands of the EEG signal. It has              lobes is represented by the color orange. It is noted that
been observed that ES is associated not only with low-                  the PIL stage, preceded by the IIL phase, is precisely cap-
frequency signals but they are also with high-frequency                 tured by the proposed MCSV-CNN model. Fig. 7 demon-
areas of the signal [28–30]. Given that each frequency                  strates that the brain’s left and right ear lobes are sending
                                                                        out powerful signals. These signals are enhanced by the
Table 3 Ablation study on key MCSV-CNN components                       gamma and full frequency bands used in the MCSV-
Model Variant                       SEN (%)       FPR/h       AUC       CNN technique. Subsequently, Fig. 7 shows a clear indi-
Full MCSV-CNN                       98.3          0.045       99.94     cation of seizure spread from the ear lobes to other brain
Without multiresolution filtering   94.1          0.14        93.0      regions following the seizure onset. The presented results
Without sub-band voting             91.5          0.29        91.0      are cross-verified with the data provided in the annota-
Shallower CNN (2 conv layers)       89.1          0.34        88.6      tion [22].

Yedurkar et al. BMC Medical Informatics and Decision Making             (2025) 25:354                                                         Page 14 of 17


Fig. 7 Topographic representation of the various IIL stages. This represents the illustration of the various phases of the IIL stage, highlighting spatial EEG
dynamics between seizure events

Runtime and computational requirements                                           in predicting seizures for all subjects, hence setting the
To assess the feasibility of real-time deployment, the                           highest benchmark performance. The MCSV-CNN
proposed MCSV-CNN model was implemented using                                    method is superior to all others with respect to its ACC,
TensorFlow and tested on a system with an Intel i7 CPU                           SEN, and FPR. This is justified by two major principles:
(2.9 GHz), 16 GB RAM, and an NVIDIA GTX 1660 GPU.                                first, the multichannel EEG data used in the model cap-
The average inference time per EEG window (5 seconds)                            tures holistic seizure-related information, and second,
was approximately 32 ms, well within the constraints of                          the capability of the MCSV-CNN model to detect HFOs
real-time seizure prediction. The model contains approx-                         effectively, which are important biomarkers of seizure
imately 1.2 million parameters and requires 4.7 MB of                            activities. Comparing the proposed MCSV-CNN method
storage, making it lightweight enough for integration into                       with other techniques is challenging due to differences
edge devices. Memory footprint and latency were further                          in channel-segment selection, specific features used, and
reduced by quantizing weights and pruning redundant                              classifiers employed in each method. However, from the
filters after training, without a significant drop in accu-                      literature review, it can be inferred that the MCSV-CNN
racy (less than 1.5%). Preliminary tests on a Raspberry                          technique outperforms others in performance values on
Pi 4B (ARM Cortex-A72, 4 GB RAM) showed that infer-                              all EEG channel segments, reflecting its robustness and
ence could still be performed under 100 ms per window,                           efficiency for SP.
suggesting compatibility with low-power embedded
systems. These characteristics support the scalability of                        Limitations and future work
the MCSV-CNN for continuous monitoring in resource-                              This study suggests employing the MCSV-CNN scheme
constrained wearable or IoT-based environments, pro-                             for SP. The primary difficulty in SP lies in choosing the
vided efficient model deployment frameworks such as                              right algorithm to process and evaluate the EEG data and
TensorFlow.                                                                      correctly identify the various epileptic states. Further-
                                                                                 more, our prediction is substantially hampered by the
Comparative analysis                                                             fact that a sizable fraction of the PIL EEG signal remains
This section discusses different SP methods that                                 highly identical across periods in the same patient.
check the efficacy of the proposed MCSV-CNN-based                                Through the capture of HFOs in EEG data, this research
approach. Table 4 presents a comparison between dif-                             concentrated on the PIL phase. In addition, the CNN
ferent methods for SP. Various works confirm the sig-                            model predicts seizure activity based on segment-wise
nificance of the feature based on power spectra and the                          multichannel HFO extraction. Nevertheless, the outcome
usage of DL models for SP. Both are decisive factors in                          will be significantly improved if the DL algorithm makes
a correct and rapid seizure diagnosis. The proposed                              use of an adaptive approach for seizure details. DL model
technique from this paper has the highest performance                            architecture continues to be hampered by IoT device

Yedurkar et al. BMC Medical Informatics and Decision Making          (2025) 25:354                                              Page 15 of 17


Table 4 Comparative analysis of the suggested SPA-IoT technique
Author                                  Method used                                                                  Performance analysis
                                                                                                                     Sen/Acc/AU Cin%
                                                                                                                     F P Rin/hr.
Gao et al. [32]                         Multi-scale features with weighted fusion based CNN                          SEN-93.3,
                                                                                                                     FPR-0.007
Xu et al. [33]                          Preictal artificial signal synthesis algorithm                               SEN-NS
                                        based on a GAN                                                               ACC:78
Jemal et al. [34]                       Interpretable DL classifier                                                  SEN-94.96,
                                                                                                                     FPR-0.096
Zhao et al. [35]                        Adder network and supervised contrastive learning (AddNet-SCL)               SEN-89.1- 94.9,
                                                                                                                     FPR-0.120–0.077,
                                                                                                                     AUC: 83.1–94.2
Lopes et al. [36]                       Ensemble deep neural network based on the                                    SEN-92.84,
                                        combination of time-series, PSDs, and topoplots
Albaqami et al. [37]                    WaveNet based Long Short Term Memory                                         SEN-97.09,
                                                                                                                     ACC:97.45
Yang et al. [38]                        Multilevel temporal spectral feature
                                        extraction network                                                           ACC:85.7
Wei and Mooney [39]                     Twenty features based on Time and
                                        frequency domain features                                                    ACC:98.95
Bidgoli et al. [40]                     Generative Adversarial Networks                                              ACC:71.27
                                                                                                                     AUC:72
The proposed technique                  SPA system using                                                             SEN-98.3,
                                        Multiresolution critical spectral verge (MCSV)                               AUC: 99.94,
                                        and CNN technique                                                            ACC:99.5,
                                                                                                                     FPR-0.045

asset limitations. Efficacy and time efficiency are two                       missed seizure warnings and potential injury, and false
major issues in the design of DL in actual IoT systems.                       positives, which cause needless worry or disruption of
The future of the proposed approach lies in being able to                     lifestyle. The system is assistive, not deterministic, and
attain cross-patient prediction effectively. That would be                    ought to be avoided in place of clinical judgment; this
a major enhancement for this work. Moreover, the pro-                         must be made apparent.
posed system has been deployed using private data and                            While the proposed MCSV-CNN framework demon-
a private API in a confined space. However, considering                       strates promising preliminary results, it is important to
that numerous connected things exist, future systems will                     note that the size and diversity of the datasets used limit
be implemented in open settings, referred to as software                      the current study’s validation. Several statements regard-
environments, with a dizzying array of services offered.                      ing model generalizability, robustness, and clinical appli-
  In addition, while the current evaluation benchmarks                        cability remain to be confirmed through larger-scale,
demonstrate that the proposed MCSV-CNN outperforms                            multi-center studies and prospective real-world testing.
several traditional DL approaches, we acknowledge the                         Future work will focus on expanding validation to include
increasing relevance of more recent architectures, such                       more heterogeneous patient populations, rigorous abla-
as graph neural networks (GNNs) and transformer-based                         tion studies to isolate key architectural contributions,
models, particularly for EEGs spatial-temporal structure.                     and deployment trials in realistic IoT environments to
Future work will involve benchmarking MCSV-CNN                                solidify the claims made.
against these state-of-the-art models to provide a more                          Lastly, as the system is a decision-support tool that may
comprehensive performance comparison, especially in                           have medical ramifications, regulations should govern it,
wearable IoT scenarios where attention mechanisms and                         undergo clinical studies, and be continuously monitored
graph representations can capture inter-electrode depen-                      after implementation. Safe and ethical incorporation
dencies more explicitly [41], [42].                                           into epilepsy care will depend on ensuring adherence to
  Although there is potential for real-time clinical and                      medical device laws and including stakeholders, such as
ambulatory applications of the suggested IoT-based sei-                       patients, neurologists, and caregivers.
zure prediction system, there are a number of practical
and ethical issues with its implementation. The most
prevalent risks include false negatives, which result in

Yedurkar et al. BMC Medical Informatics and Decision Making                                                                      (2025) 25:354                                                                                                                Page 16 of 17


                                                                                                                                          6.    Hasnaoui LH, Djebbari A. Epileptic activity prediction within pre–ictal epochs:
Conclusion                                                                                                                                      application on selected channels. 2022 7th International Conference on
A monitoring system SPA and IoT-enabled SP based on                                                                                             Image and Signal Processing and their Applications (ISPA). Mostaganem,
the suggested MCSV-CNN architecture were presented                                                                                              Algeria: 2022, pp. 1–6, doi: ​h​t​t​p​s​:​​​/​​/​d​o​​i​.​​o​r​​g​​/​​1​0​​.​1​1​​​0​9​​/​I​S​​P​A​5​​4​​0​0​​4​.​​2​​0​2​2​.​9​7​8​6​3​3​4.
                                                                                                                                          7.    Zhang ZS, Parhi KK. Low-complexity seizure prediction from iEEG/sEEG using
and assessed in this work. When compared to other                                                                                               spectral power and ratios of spectral power. IEEE Trans Biomed Circuits Syst.
approaches, the method showed a lower FPR, better                                                                                               2016, Jun;10(3):693–706.
AUC scores, and good precision in detecting pre-ictal                                                                                     8.    Aarabi A, He B. A rule-based seizure prediction method for focal neocortical
                                                                                                                                                epilepsy. Clin neurophysiol. 2012;123(6):1111–22.
regions in EEG recordings. According to experimental                                                                                      9.    Supratak A, Dong H, Wu C, Guo YK. DeepSleepNet: a Model for automatic
findings, seizure-related patterns have been observed                                                                                           Sleep Stage scoring based on raw single-channel EEG. IEEE Trans On Neural
throughout the entire EEG spectrum, especially in the                                                                                           Syst And Rehabil Eng. 2017, Nov;25(11):1998–2008.
                                                                                                                                          10.   Sakhavi S, Guan CT, Yan SC. Learning temporal information for brain-com-
high-frequency components. Additionally, the system                                                                                             puter interface using convolutional neural networks. IEEE Trans On Neural
demonstrated resilience in noisy and real-time environ-                                                                                         Networks And Learn Syst. 2018, Nov;29(11):5619–29.
ments, suggesting that it might be used practically in                                                                                    11.   Mahmood M, Mzurikwao D, Kim YS, Lee Y, Mishra S, Herbert R, Duarte A, Ang
                                                                                                                                                CS, Yeo WH. Fully portable and wireless universal brain–machine interfaces
wearable and clinical monitoring scenarios.                                                                                                     enabled by flexible scalp electronics and deep learning algorithm. Nat Mach
                                                                                                                                                Intell. 2019;(1):412–22.
Author contributions statement                                                                                                            12.   Truong ND, Nguyen AD, Kuhlmann L, Bonyadi MR, Yang JW, Ippolito S, Kave-
Conceptualization, DPY, SPM, TS, VM, SA; methodology, DPY, SPM, TS, VM, SA;                                                                     hei O. Convolutional neural networks for seizure prediction using intracranial
writing—original draft preparation, DPY, SPM, TS, VM, SA; writing—review and                                                                    and scalp electroencephalogram. Neural Netw. 2018, Sep;105:104–11.
editing, DPY, SPM, TS, VM, SA; visualization, DPY, SPM, TS, VM, SA. All authors                                                           13.   Khan H, Marcuse L, Fields M, Swann K, Yener B. Focal onset seizure
have read and agreed to the published version of the manuscript.                                                                                prediction using convolutional networks. IEEE Trans Biomed Eng. 2018,
                                                                                                                                                Sep;65(9):2109–18.
Funding                                                                                                                                   14.   Ozcan AR, Erturk S. Seizure prediction in scalp EEG using 3D convolutional
Open access funding provided by Manipal Academy of Higher Education,                                                                            neural networks with an image-based approach. IEEE Trans On Neural Syst
Manipal.                                                                                                                                        And Rehabil Eng. 2019, Nov;27(11):2284–93.
                                                                                                                                          15.   Zhang Y, Guo Y, Yang P, Chen W, Lo B. Epilepsy seizure prediction on EEG
Data availability                                                                                                                               using common spatial pattern and convolutional neural network. IEEE J
The TUH-EEG datasets used in this paper is publicly available at ​h​t​t​p​​s​:​/​​/​i​s​i​​p​.​​p​i​c​​                                         Biomed And Health Inf. 2020, Feb;24(2):465–74.
o​n​e​​p​r​e​s​​s​.​​c​o​m​​/​p​r​​o​j​e​c​​t​s​​/​n​e​d​c​/​h​t​m​l​/​t​u​h​_​e​e​g​/. The clinical data set is available                16.   Sogamoso KVA, Parra OJS. Internet of things for epilepsy detection in
upon reasonable request ​h​t​t​p​​s​:​/​​/​i​s​i​​p​.​​p​i​c​​o​n​e​​p​r​e​s​​s​.​​c​o​m​​/​p​r​​o​j​e​c​​t​s​​/​n​e​d​c​/​h​t​m​l​/​t​         patients. International Conference on Cooperative Design, Visualization and
u​h​_​e​e​g​/.                                                                                                                                  Engineering. 2018 October, pp. 237–44.
                                                                                                                                          17.   Ahmed A, Ahmad W, Khan MJ, Siddiqui SA, Cheema HM. A wearable sensor
Declarations                                                                                                                                    based multi-criteria-decision-system for real-time seizure detection, in 39th
                                                                                                                                                Annual International Conference of the IEEE Engineering in Medicine and
Ethics approval and consent to participate                                                                                                      Biology Society (EMBC), 2017 July, pp. 2377–80.
The study was carried out according to Declaration of National Ethics                                                                     18.   Myers MH, Threatt M, Solies KM, McFerrin BM, Hopf LB, Birdwell JD, Sillay KA.
Guidelines for Biomedical and Health Research, and was approved by the                                                                          Ambulatory seizure monitoring: from concept to prototype device. Ann Of
Ethics Committee of Yardi Hospital (E6R2, 28/12/2021). The study was carried                                                                    Neurosciences. 2016;23(2):100–11.
out with the consent and guidance of Dr. Nandan Yardi, senior consultant in                                                               19.   Pinho F, Cerqueira J, Correia J, Sousa N, Dias N. myBrain: a novel EEG embed-
epileptology and President, Indian Epilepsy Association, Pune chapter, Pune,                                                                    ded system for epilepsy monitoring. J Med Eng Technol. 2017;41(7):564–85.
2022.                                                                                                                                     20.   Alyasseri ZA, Khader AT, Al-Betar MA, Papa JP, Alomari OA. EEG feature
                                                                                                                                                extraction for person identification using wavelet decomposition and multi-
Consent for publication                                                                                                                         objective flower pollination algorithm. IEEE Access- Spec Sect On New Trends
Not applicable.                                                                                                                                 In Brain Signal Process And Anal. 2018, Nov;6.
                                                                                                                                          21.   Yedurkar DP, Metkar SP. Multiresolution approach for artifacts removal and
Conflict of interest                                                                                                                            localization of seizure onset zone in epileptic EEG signal. Biomed Signal
There is no conflict of interest.                                                                                                               Process Control. 2020, March;57.
                                                                                                                                          22.   Golmohammadi M, Obeid I, Picone J. Deep residual learning for automatic
                                                                                                                                                seizure detection. Seizure. 2018;21:16.
Received: 4 June 2025 / Accepted: 8 September 2025                                                                                        23.   Pathak AR, Pandey M, Rautaray S. Topic-level sentiment analysis of social
                                                                                                                                                media data using deep learning. Appl Soft Comput. 2021;108, pp. 107440.
                                                                                                                                          24.   Rosso OA, Martin MT, Plastino A. Brain electrical activity analysis using
                                                                                                                                                wavelet-based informational tools. Physica A. 2002, Oct;313(3):587–608.
                                                                                                                                          25.   Orhan U, Hekim M, Ozer M. EEG signals classification using the K-means
References                                                                                                                                      clustering and a multilayer perceptron neural network model. Expert Syst
1. World Health Organization, Epilepsy: a Public Health imperative. Geneva,                                                                     With Appl. 2011;38(10):13475–81.
    Switzerland: WHO; 2019.                                                                                                               26.   Krizhevsky A, Sutskever I, Hinton GE. ImageNet classification with deep
2. Y.Wang WC, Yu T, Li X, Liao X, Li Y. Dynamic multi-graph convolution based                                                                   convolutional neural networks. Commun Of The ACM. 2017, Jun;60(6):84–90.
    Channel-weighted transformer feature fusion network for epileptic seizure                                                             27.   Kingma DP, Ba J. Adam: a method for stochastic optimization. 3rd Interna-
    prediction. IEEE Transactions on Neural Systems and Rehabilitation Engineer-                                                                tional Conference for Learning Representations. San Deigo, USA: 2015, pp.
    ing. 2023.                                                                                                                                  1–15.
3. D.Puri RC, Kachare P. Detection of epilepsy using wavelet packet sub-bands                                                             28.   Winterhalder M, Maiwald T, Voss HU, Aschenbrenner-Scheibe R, Timmer J,
    from EEG signals. Appl Comput Technol. 2022;302–10.                                                                                         Schulze-Bonhage A. The seizure prediction characteristic: a general frame-
4. Ranganathan LN, Chinnadurai SA, Samivel B, Kesavamurthy B, Mehndi-                                                                           work to assess and compare seizure prediction methods. Epilepsy Behav.
    ratta MM. Application of mobile phones in epilepsy care. Int J Epilepsy.                                                                    2003, Jun;4(3):318–25.
    2015;2(1):028–037.                                                                                                                    29.   Liu XY, Wu JX, Zhou ZH. Exploratory undersampling for class-imbalance learn-
5. Witte H, Iasemidis LD, Litt B. Special issue on epileptic seizure prediction. IEEE                                                           ing. IEEE Trans Syst, Man, Cybern, Syst Man And Cybern Part b-Cybern. 2009,
    Trans Biomed Eng. 2003, May;50(5):537–39.                                                                                                   Apr;39(2):539–50.

Yedurkar et al. BMC Medical Informatics and Decision Making                      (2025) 25:354                                                              Page 17 of 17


30. He HB, Garcia EA. Learning from imbalanced data. IEEE Trans Knowl Data Eng.          38. Yang Y, Li F, Qin X, Wen H, Lin X, Huang D. Feature separation and adversarial
    2009, Sep;21(9):1263–84.                                                                 training for the patient-independent detection of epileptic seizures. Front
31. Chawla NV, Bowyer KW, Hall LO, Kegelmeyer WP. SMOTE: Synthetic minority                  Comput Neurosci. 2023;17.
    over-sampling technique. J Artif Intell Res. 2002;16:321–57.                         39. Wei L, Mooney C. Pediatric and adolescent seizure detection: a machine
32. Gao Y, Chen X, Liu A, Liang D, Wu L, Qian R, Zhang Y. Pediatric seizure predic-          learning approach exploring the influence of age and sex in electroencepha-
    tion in scalp EEG using a multi-scale neural network with dilated convolu-               logram analysis. BioMedinformatics. 2024;4(1):796–810.
    tions. IEEE J Transl Eng Health Med. 2022;10:1–9.                                    40. Bidgoli NS, Kheradpisheh SR, Farahani H. EEG anomaly detection using gener-
33. Xu Y, Yang J, Sawan M. Multichannel synthetic preictal EEG signals to enhance            ative adversarial networks (GANs). 2024 20th CSI International Symposium on
    the prediction of epileptic seizures. IEEE Transactions on Biomedical Engi-              Artificial Intelligence and Signal Processing (AISP). IEEE, pp. 1–6. 21 February
    neering. 2022.                                                                           2024.
34. Jemal I, Mezghani N, Abou-Abbas L, Mitiche A. An interpretable deep learn-           41. Puri DV, Gawande JP. H.Kachare, and I.Al-shourbaji, optimal time-frequency
    ing classifier for epileptic seizure prediction using EEG data. IEEE Access. 2022.       localized wavelet filters for identification of Alzheimer’s disease from EEG
35. Zhao Y, Li C, Liu X, Qian R, Song R, Chen X. Patient-specific seizure prediction         signals. Cogn NeuroDyn. 2025;19(1):12.
    via adder network and supervised contrastive learning. IEEE transactions on          42. P.Kachare SBS, D.Puri MMK, Al-Shourbaji I. steadynet: Spatiotemporal EEG
    neural systems and rehabilitation engineering. 2022.                                     analysis for dementia detection using convolutional neural network. Cogn
36. Lopes F, Leal A, Medeiros J, Pinto MF, Dourado A, Dümpelmann M, Teixeira                 NeuroDyn. 2024;18(5):3195–208.
    C. Ensemble deep neural network for automatic classification of EEG
    Independent components. IEEE Trans On Neural Syst And Rehabil Eng.
    2022;30:559–68.                                                                      Publisher’s Note
37. Albaqami H, Hassan GM, Datta A. Automatic detection of abnormal EEG                  Springer Nature remains neutral with regard to jurisdictional claims in
    signals using WaveNet and LSTM. Sensors. 2023;23(13):5960.                           published maps and institutional affiliations.
```
