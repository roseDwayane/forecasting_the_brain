---
citation_key: "AhmadEtAl2026"
paper_id: "paper_137"
title: "A hybrid deep learning framework for epileptic seizure prediction using scalp and intracranial EEG data."
authors: "Izza Mujeeb Ahmad; Bisma Ashar; Shehryar Munir; Aamir Wali; Muhammad Saif Ul Islam"
year: 2026
doi: "10.1016/j.compmedimag.2026.102759"
source: "publisher-pdf (doi: 10.1016/j.compmedimag.2026.102759)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# A hybrid deep learning framework for epileptic seizure prediction using scalp and intracranial EEG data.

**Citation:** `AhmadEtAl2026` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1016/j.compmedimag.2026.102759](https://doi.org/10.1016/j.compmedimag.2026.102759)
**Source PDF:** `full_pdf/Izza2026.pdf`

## Abstract

Epilepsy is a prevalent neurological disorder affecting over 50 million people globally, often impairing quality of life due to unpredictable and recurrent seizures. Despite advances in seizure prediction, challenges remain due to variability in EEG signals. EEG data exists in two primary modalities: non-invasive scalp EEG (sEEG) and invasive intracranial EEG (iEEG), and current deep learning models often exhibit limited generalizability across these modalities due to signal and structural differences. In this study, we propose a custom hybrid CNN-LSTM model optimized for scalp EEG, and assess its effectiveness across modalities by also evaluating it on invasive EEG datasets. We utilize the CHB-MIT (sEEG) and AES-Kaggle (iEEG) datasets employing a unified pipeline of preprocessing, signal transformation, and deep learning techniques. The model reported an accuracy of 98.84% on sEEG, using a 10-minute seizure anticipation window, outperforming conventional CNN, LSTM and several recent state-of-the-art models. On iEEG data, the hybrid model performed comparably well, achieving an impressive accuracy of 97.18%. The models are further validated using real-world scalp EEG data collected from the General Hospital Lahore, Pakistan. This additional validation demonstrates strong generalizability to clinical settings and confirms the practical applicability of the proposed approach. These findings not only highlight the effectiveness of the proposed approach for seizure prediction but also underscore its readiness for real-world deployment, potentially enabling reliable early warning systems to improve the lives of epilepsy patients.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Computerized Medical Imaging and Graphics 130 (2026) 102759


                                                                 Contents lists available at ScienceDirect


                                          Computerized Medical Imaging and Graphics
                                                  journal homepage: www.elsevier.com/locate/compmedimag


A hybrid deep learning framework for epileptic seizure prediction using scalp
and intracranial EEG dataI
                                                                                                         ∗
Izza Mujeeb Ahmad, Bisma Ashar, Shehryar Munir, Aamir Wali                                                , Muhammad Saif ul Islam
FAST School of Computing, National University of Computer and Emerging Science, Faisal Town, Lahore, Pakistan


ARTICLE                INFO                             ABSTRACT

Dataset link: https://physionet.org/content/ch          Epilepsy is a prevalent neurological disorder affecting over 50 million people globally, often impairing quality
bmit/1.0.0/                                             of life due to unpredictable and recurrent seizures. Despite advances in seizure prediction, challenges remain
Keywords:
                                                        due to variability in EEG signals. EEG data exists in two primary modalities: non-invasive scalp EEG (sEEG) and
EEG signal classification                               invasive intracranial EEG (iEEG), and current deep learning models often exhibit limited generalizability across
Seizure detection                                       these modalities due to signal and structural differences. In this study, we propose a custom hybrid CNN-LSTM
Deep learning                                           model optimized for scalp EEG, and assess its effectiveness across modalities by also evaluating it on invasive
CNN                                                     EEG datasets. We utilize the CHB-MIT (sEEG) and AES-Kaggle (iEEG) datasets employing a unified pipeline
LSTM                                                    of preprocessing, signal transformation, and deep learning techniques. The model reported an accuracy of
                                                        98.84% on sEEG, using a 10-minute seizure anticipation window, outperforming conventional CNN, LSTM and
                                                        several recent state-of-the-art models. On iEEG data, the hybrid model performed comparably well, achieving
                                                        an impressive accuracy of 97.18%. The models are further validated using real-world scalp EEG data collected
                                                        from the General Hospital Lahore, Pakistan. This additional validation demonstrates strong generalizability to
                                                        clinical settings and confirms the practical applicability of the proposed approach. These findings not only
                                                        highlight the effectiveness of the proposed approach for seizure prediction but also underscore its readiness
                                                        for real-world deployment, potentially enabling reliable early warning systems to improve the lives of epilepsy
                                                        patients.


1. Introduction                                                                             patterns associated with the onset of epileptic seizures. Neurologists
                                                                                            traditionally analyze EEG recordings to detect historical seizure pat-
   Globally, an estimated 5 million individuals are diagnosed with                          terns and assess seizure likelihood. However, the manual scrutiny of
epilepsy annually, marking it as a significant neurological disorder                        extensive EEG datasets to discern these critical preictal patterns is a
with potentially life-threatening consequences. The documented risk                         labor-intensive and time-sensitive task.
of premature mortality in people with epilepsy is alarmingly high,
                                                                                                Our work is motivated by the potential to assist neurologists through
reported to be up to three times greater than that of the general
                                                                                            the development of an optimized computational solution that meets
population (Cui et al., 2018). This escalating prevalence and the critical
                                                                                            current state-of-the-art results. Recent studies have explored various
nature of epileptic seizures underscore the urgent need for proactive,
preventive techniques rather than solely reactive interventions.                            deep learning architectures — such as attention mechanisms, tem-
   Electroencephalogram (EEG) is a widely used technique that records                       poral convolutional networks, and hybrid CNN-LSTM models — for
the brain’s electrical activity through scalp-mounted electrodes (ul Is-                    automatic seizure classification and detection, often achieving high
lam and Farooq, 2017). EEG data can be acquired via non-invasive                            intra-dataset accuracy (Daoud et al., 2020; Liu et al., 2019; Varnos-
Scalp Electroencephalogram (sEEG) or invasive Intracranial Electroen-                       faderani et al., 2021). However, many of these models are trained and
cephalogram (iEEG), with the latter offering higher spatial resolution                      validated on either scalp or intracranial EEG data exclusively, limiting
and signal fidelity. The analysis of EEG data offers crucial insights                       their ability to generalize across modalities. Furthermore, while detec-
that can substantially aid in the prediction of epileptic seizures. They                    tion performance is often strong, predictive performance — especially
can also serve as a valuable source of information for identifying


 I This article is part of a Special issue entitled: ‘AI-based CDSS’ published in Computerized Medical Imaging and Graphics.
 ∗ Corresponding author.
    E-mail addresses: l201314@lhr.nu.edu.pk (I.M. Ahmad), l201386@lhr.nu.edu.pk (B. Ashar), l201302@lhr.nu.edu.pk (S. Munir), aamir.wali@nu.edu.pk
(A. Wali), muhammad.saif@nu.edu.pk (M.S. ul Islam).

https://doi.org/10.1016/j.compmedimag.2026.102759
Received 30 May 2025; Received in revised form 3 March 2026; Accepted 27 March 2026
Available online 28 March 2026
0895-6111/© 2026 Elsevier Ltd. All rights are reserved, including those for text and data mining, AI training, and similar technologies.

I.M. Ahmad et al.                                                                                     Computerized Medical Imaging and Graphics 130 (2026) 102759


with extended anticipation windows and real-world constraints — re-              highlighting the research gaps that this work aims to address. Section 3
mains underexplored. These limitations highlight the need for robust,            details the methodology employed, including the datasets used, prepro-
generalizable models capable of operating across heterogeneous EEG               cessing steps, feature extraction techniques, and the architecture of the
sources in realistic clinical environments.                                      proposed hybrid CNN-LSTM model. Section 4 presents and discusses the
    From a clinical perspective, the proposed seizure prediction frame-          experimental results obtained on both scalp and intracranial EEG data,
work has the potential to serve as a component of a Clinical Deci-               along with a comparison to state-of-the-art methods and an evaluation
sion Support System (CDSS) for epilepsy management. By providing                 of seizure time anticipation. Finally, Section 5 concludes the paper and
accurate and timely identification of preictal states, such a system             outlines potential directions for future research.
could alert healthcare professionals or caregivers in advance, enabling
preventive interventions, personalized treatment adjustments, and im-            2. Literature review
proved patient safety. Integration into clinical workflows would require
the model to operate in real-time, process continuous EEG streams,                   Several traditional and machine learning-based methods have been
and deliver results through interfaces compatible with existing hospital         proposed for epileptic seizure prediction. Slimen et al. (2020) employed
information systems.                                                             a spike-based detection approach using EEG, triggering an alarm when
                                                                                 spike counts exceeded a predefined threshold. Although simple and
1.1. Problem statement                                                           interpretable, this method was constrained by its exclusive reliance
                                                                                 on scalp EEG and the absence of machine learning or deep learning
    The core challenge lies in the accurate and timely prediction of             integration. Yuan et al. (2018) introduced Bayesian Linear Discriminant
epileptic seizures by analyzing EEG data. While existing research has            Analysis to calculate diffusion distances between wavelet coefficients.
made significant strides in seizure detection (identifying seizures as           However, its performance could be enhanced through a richer set of
they occur), the anticipation of impending seizures remains a critical           handcrafted features for better pattern discrimination.
unmet need. Furthermore, many current approaches focus on either                     Cui et al. (2018) applied EEG synchronization using a Bag-of-Words
scalp or intracranial EEG data in isolation, potentially limiting the            model and Extreme Learning Machine (ELM), suggesting that deeper
generalizability and robustness of the models. There is also a need for          learning models could yield better representation and predictive power.
improved timeliness in prediction, enhanced sensitivity to minimize              Similarly, Shiao et al. (2016) used Support Vector Machines on iEEG
false negatives, and solutions that are computationally efficient for            data from epileptic dogs, achieving 90% sensitivity. However, their
real-world deployment.                                                           subject-specific approach and the use of imbalanced datasets limited
                                                                                 broader applicability. Usman et al. (2017) explored empirical mode
1.2. Objectives                                                                  decomposition with K-Nearest Neighbors (KNN), Naïve Bayes, and Sup-
                                                                                 port Vector Machine (SVM) classifiers, demonstrating effective feature
    In this study, we propose a hybrid CNN-LSTM model for the predic-            extraction but lacking modern deep learning capabilities and being
tion of epileptic seizures. The primary objectives of this research are as       restricted to scalp EEG data.
follows:                                                                             With the advent of deep learning, Liu et al. (2019) proposed a
                                                                                 Multiview CNN that leveraged both time and frequency EEG features.
    • To design a hybrid deep learning framework that combines the               While effective, its high computational complexity posed scalability
      spatial feature extraction capabilities of Convolutional Neural            concerns. Daoud et al. (2020) developed an IoT-enabled deep learning
      Network (CNN) with the temporal sequence modeling strength of              model using DCNN for spatio-temporal feature classification. However,
      Long Short-Term Memory (LSTM) for accurate seizure prediction.             using data from only 8 out of 22 subjects reduced generalizability.
    • To rigorously evaluate the model’s performance on both non-                Varnosfaderani et al. (2021) introduced an LSTM model with Swish
      invasive scalp EEG data (CHB-MIT dataset ) and invasive intracra-          activation, showing strong classification performance across patient-
      nial EEG data (Kaggle American Epilepsy Society (AES) dataset ).           specific and patient-independent cases, though the lack of automated
    • To improve the accuracy and anticipation timing of seizure pre-            feature selection points to potential benefits from hybrid architectures.
      diction, enabling reliable early warnings ahead of seizure onset.              Ryu and Joe (2021) combined DenseNet and LSTM in a hybrid
    • To explore strategies such as feature fusion for minimizing over-          architecture, surpassing 92% accuracy. Despite its strength, the model’s
      fitting and improving the model’s robustness for deployment in             dependence on pre-ictal segment assumptions and its exclusive use
      real-world healthcare settings.                                            of scalp EEG data limit its universality. In Truong et al. (2019), a
                                                                                 semi-supervised Generative Adversarial Networks (GAN) based method
1.3. Significance and impact                                                     was explored, attaining a 75% accuracy. As a claimed first effort in
                                                                                 applying GANs for seizure prediction, further refinement could boost
    The successful development of an accurate and timely seizure pre-            its effectiveness. Yan et al. (2022) employed a three-tower transformer
diction system holds significant potential to improve the quality of life        model but faced limitations in sensitivity and efficiency due to its
for individuals living with epilepsy, their caregivers, and the health-          simplistic architecture.
care professionals involved in their diagnosis and management. By                    Early feature extraction techniques also contributed foundational
providing early warnings before seizure onset, our proposed solution             insights. Fadzal et al. (2012) employed the Wavelet Transform, lever-
can enable timely medical intervention, potentially preventing injuries,         aging the properties of a mother wavelet, yet did not address compu-
reducing cognitive impairment, and alleviating the social isolation              tational efficiency. Hazarika et al. (1997) applied Short-Time Fourier
often associated with this condition. Furthermore, an efficient and              Transform (STFT), noting its utility in temporal analysis but also indi-
robust prediction model can reduce the burden on neurologists by                 cating room for improvement in real-time processing contexts.
automating the initial analysis of EEG data, allowing them to focus on               Recent studies have also explored graph-based deep learning and at-
more complex cases and personalized treatment strategies.                        tention mechanisms to model inter-channel relationships in EEG signals
                                                                                 explicitly. Graph Attention Networks (GATs) have shown promise in
1.4. Paper organization                                                          both seizure detection and broader epilepsy classification tasks by rep-
                                                                                 resenting EEG channels as nodes and their functional or spatial relation-
    The remainder of this paper is organized as follows: Section 2               ships as edges. Mazurek et al. (2025) proposed a lightweight GAT-based
provides a comprehensive review of the existing literature on epileptic          framework designed for low-cost EEG hardware in low-resource set-
seizure prediction using traditional and machine learning techniques,            tings, highlighting how learned attention weights enable visualization


I.M. Ahmad et al.                                                                                            Computerized Medical Imaging and Graphics 130 (2026) 102759


                    Table 1
                    Review of ML-Based Epileptic Seizure Detection Studies.
                     Ref.                                      Method                                           Result                     Metric
                     Slimen et al. (2020)                      EEG Spike Detection                              –                          –
                     Yuan et al. (2018)                        Wavelet + Bayesian LDA                           85%                        Sensitivity
                     Cui et al. (2018)                         BoWav + ELM                                      85%                        Sensitivity
                     Liu et al. (2019)                         Multiview CNN                                    82%                        Accuracy
                     Daoud et al. (2020)                       DCNN (IoT-based)                                 –                          –
                     Varnosfaderani et al. (2021)              LSTM + Swish Activation                          –                          –
                     Shiao et al. (2016)                       SVM on Nonlinear Features                        90%                        Sensitivity
                     Bandarabadi et al. (2015)                 Spectral Power + SVM                             –                          –
                     Usman et al. (2021)                       EMD + k-NN/SVM/NB                                –                          –
                     Savadkoohi et al. (2020)                  Wavelet + SVM/k-NN                               92%                        Accuracy
                     Ryu and Joe (2021)                        DenseNet + LSTM                                  92%                        Accuracy
                     Usman et al. (2017)                       MAML-based Ensemble                              91%                        Sensitivity
                     Truong et al. (2019)                      GAN-based Semi-Supervised                        75%                        F1-Score
                     Yan et al. (2022)                         Transformer (Three-Tower)                        91%                        Accuracy
                     Hazarika et al. (1997)                    STFT + Spectrogram                               –                          –
                     Fadzal et al. (2012)                      Wavelet Transform                                –                          –
                     Liu et al. (2024)                         Multi-dimensional Hybrid Bilinear                98.44%                     Accuracy
                                                               CNN-LSTM
                     Shawly et al. (2025)                      MAFBN: Multi-Attention Forward                   97.88%                     Accuracy
                                                               and Backward Network
                     Ghosh and Dey (2024)                      CNN-BiLSTM-Attention with                        99.70%                     Accuracy
                                                               Multisynchrosqueezing Transform
                     Patel (2024)                              SeizureSight: 2D CNN-LSTM                        94.00%                     Accuracy
                                                               Hybrid
                     Helgesen (2024)                           Machine Learning-based Seizure                   96.30%                     Sensitivity
                                                               Prediction
                     Fu et al. (2025)                          WCE-MASE-PGCN                                    97.9%                      Sensitivity


of critical channel-to-channel interactions and potential biomarkers.                  Table 2
Building on this, Fu et al. (2025) introduced a Spatiotemporal Posterior               Number of preictal and interictal segments in CHB-MIT and AES datasets.
Graph Convolutional Neural Network (WCE-MASE-PGCN) that inte-                           Dataset                 Preictal segments                     Interictal segments
grates multi-head attention with a Squeeze-and-Excitation (SE) module.                  CHB-MIT                 150                                   150
By combining graph convolutions with attention-driven feature re-                       AES                     211                                   211
calibration, this approach enhances the model’s ability to distinguish
subtle preictal transitions while providing a sophisticated framework
for mapping the spatiotemporal evolution of seizures.                                  et al., 2025; Ather et al., 2024), audio/speech (Fawaz et al., 2021;
    Existing research spans from traditional signal processing methods                 Mahmood et al., 2024), videos (Hamza and Wali, 2023, 2025) and
to advanced deep learning architectures, each contributing unique                      text (Shahzad and Wali, 2022; Shahid et al., 2024).
insights into seizure prediction. While CNNs excel in extracting spatial
and frequency-based features from EEG data, they often lack temporal                   3.1. Dataset
sensitivity. Conversely, LSTMs effectively capture temporal dependen-
cies but may underperform in spatial feature learning when used in                         We employ two EEG datasets: the Children’s Hospital Boston-
isolation. The literature thus reveals a critical gap: the need for a uni-             Massachusetts Institute of Technology (CHB-MIT) Scalp EEG dataset
fied framework that leverages the spatial learning strength of CNNs and                (Goldberger and Amaral, 2010) and the American Epilepsy Society
the temporal sequence modeling capabilities of LSTMs. This motivates                   (AES) Seizure Prediction Challenge iEEG dataset (Cukierski, 2014).
the development of a hybrid deep learning system designed to enhance                   These datasets differ in recording modality and structure, which pro-
predictive accuracy and generalizability across diverse EEG modalities.                vides complementary perspectives on seizure activity. CHB-MIT com-
A comparative summary of the reviewed approaches is provided in                        prises non-invasive scalp EEG recordings from 23 pediatric patients
Table 1.                                                                               (aged 1.5–22 years) collected through multiple electrodes placed on the
                                                                                       scalp. It contains long-term continuous recordings with varying seizure
3. Methodology and experimentation                                                     types, making it a widely used benchmark for seizure detection and
                                                                                       prediction tasks.
    This section outlines the proposed methodology for predicting epi-                     In contrast, the AES dataset utilizes intracranial EEG (iEEG) record-
leptic seizures using EEG data. The approach begins with a detailed                    ings obtained via invasive electrode implantation directly within brain
description of the datasets used, followed by a comprehensive data                     tissue, with labeled 10-minute segments categorized as interictal or
preprocessing pipeline that includes annotation, channel selection, and                preictal. The AES dataset includes long-duration intracranial EEG from
feature extraction. The classification task is framed as a binary classifi-            5 human and 2 canine subjects with labeled preictal and interictal
cation problem, where the two target classes are: preictal, referring to               segments. This dataset offers higher spatial resolution and signal-to-
the period leading up to a seizure (before onset), and ictal, representing             noise ratio, capturing localized brain activity that is critical for the
the period during the seizure. The objective is to distinguish between                 precise detection of seizure onset. Using both datasets allows for a
these two states by identifying subtle changes in EEG patterns, thereby                comprehensive evaluation of predictive models across different signal
enabling early seizure prediction. This distinction is critical for real-              acquisition modalities, patient populations, and clinical settings. Spec-
world medical applications, as accurate preictal detection can provide                 ifications of the datasets are summarized in Table 2. Visualizations of
patients and caregivers with timely warnings. The classification models                channels for CHB-MIT and iEEG datasets are shown in Fig. 1 and Fig.
evaluated include CNN, LSTM, and a hybrid CNN-LSTM architecture de-                    2, respectively.
signed to capture both spatial and temporal features from EEG signals.                     While the iEEG dataset is well-suited for seizure prediction due
CNNs have been used for all kinds of data such as images (Shahzad                      to its pre-segmented and labeled structure, the CHB-MIT dataset was


I.M. Ahmad et al.                                                                                        Computerized Medical Imaging and Graphics 130 (2026) 102759


                                                     Fig. 1. Multiple channels for CHB-MIT scalp data.


                                                      Fig. 2. Multiple channels for Kaggle iEEG data.


originally designed for seizure detection, not prediction. It contains no         3.2. Data preprocessing
explicit labels for preictal or interictal states. Therefore, manual anno-
tation was necessary to adapt it for predictive modeling. Additionally,           3.2.1. Data annotation and sampling
most files in CHB-MIT span only around 1 h, limiting the possibility of               To adapt the CHB-MIT dataset for seizure prediction, we imple-
defining long interictal windows far from seizure events within a single          mented a manual labeling strategy to determine the preictal periods.
recording.                                                                        This process included neurologist input and visualization of EEG traces
    To ensure the proposed hybrid CNN-LSTM model generalizes be-                  to manually identify intervals of 10, 20, and 30 min immediately
yond the datasets used for initial training, an additional external dataset       preceding the seizure onset. These durations were chosen to evaluate
was incorporated. This dataset consisted of scalp EEG recordings col-             how early the model can predict an upcoming seizure. Experiments
lected from 10 patients at General Hospital Lahore, Pakistan, includ-             were conducted on all three sets of data, and the most optimal time
ing preictal and interictal segments. EEG data were collected using               of 30 min was selected for experimentation based on the models’
the KT88-1032 multichannel digital EEG system (supporting 18–32                   performance.
channels), with electrodes positioned in accordance with the Interna-                 Due to the limited recording duration (often 1 h), identifying
tional 10–20 system. All recordings were preprocessed using the same              interictal segments several hours away from a seizure was not feasible.
pipeline as the CHB-MIT and AES datasets to maintain consistency.                 Instead, we selected interictal windows that were at least 40 min
This external dataset was used exclusively for final testing and was not          away from any seizure onset within the same or different seizure-free
involved in any stage of model training, validation, or hyperparameter            recording files from the same patient. This helped ensure the selected
optimization.                                                                     interictal data were not contaminated by nearby preictal states.


I.M. Ahmad et al.                                                                                      Computerized Medical Imaging and Graphics 130 (2026) 102759


                                     Fig. 3. MNE library used to visualize and annotate seizure data in the EDF file.


                                  Fig. 4. Selection of the FP1-F7 channel from all the electrode channels using a script.


    MNE is a Python library for neurophysiological data that effectively         ‘–4’, and ‘–5’ were excluded as their purpose was to include metadata.
reads and processes EEG data. This library was used to visualize and             As a result, 16 intersecting channels across all recordings were chosen:
annotate EEG EDF files. This involved using a translucent color overlay          ‘FP1-F7’, ‘F7-T7’, ‘T7-P7’, ‘P7-O1’, ‘FP1-F3’, ‘F3-C3’, ‘C3-P3’, ‘P3-O1’,
to highlight the segments where seizures were detected. This whole step          ‘FP2-F4’, ‘F4-C4’, ‘C4-P4’, ‘P4-O2’, ‘FP2-F8’, ‘F8-T8’, ‘T8-P8’, and ‘P8-
helped to obtain a detailed visual analysis of seizure and non-seizure           O2’, ‘FZ-CZ’, ‘CZ-PZ’. Some of these channels are named differently for
data and separate them. The MNE library and how it visualizes data               Patient 12. Fig. 4 shows how one of these channels was separated from
are shown in Fig. 3.                                                             all other channels using scripts.
                                                                                     The AES-Kaggle dataset, on the other hand, contains uniform elec-
3.2.2. Class imbalance                                                           trode configurations and pre-segmented labeled intervals. As a result,
    Class imbalance, i.e., preictal class being underrepresented in the          no cross-modal channel alignment was required.
dataset, can adversely affect model performance. To address this con-
cern, we worked with an expert neurologist to select only a subset               3.2.4. Butterworth bandpass filter
of normal (interictal) data that was as far away as possible from the                A Butterworth bandpass filter was applied to the EEG data to
ictal region. The remaining normal data of 30 min duration each were             reduce noise and preserve signal integrity. This filter was chosen for
randomly selected from files of patients without seizures, matching the          its maximally flat passband, which ensures minimal signal distortion,
count of seizure samples. This ensured equal representation of both              critical for detecting subtle spectral and temporal features in EEG
classes.                                                                         analysis (Craik et al., 2019). The selected frequency range, 0.5–40 Hz,
                                                                                 is standard in EEG preprocessing (Acharya et al., 2013). Frequencies
3.2.3. Channel selection                                                         below 0.5 Hz were excluded to eliminate slow drifts and baseline
   The CHB-MIT (sEEG) and AES-Kaggle (iEEG) datasets differ in                   wander caused by sweat or movement artifacts. Frequencies above
EEG acquisition setups, with variations in electrode placement, num-             40 Hz were removed to suppress muscle artifacts and power-line inter-
ber of channels, and signal morphology due to scalp vs. intracranial             ference (50/60 Hz), which do not contribute meaningfully to seizure
recording. To account for these differences, we processed each dataset           prediction and can degrade model performance. The Butterworth filter
independently and developed dataset-specific pipelines.                          was preferred over alternatives like Chebyshev or Elliptic filters because
   In the CHB-MIT dataset, patient EEGs were recorded with electrode             it avoids ripples in both the passband and stopband, maintaining a
channels on their scalp, and these channels in some cases differed               smoother frequency response. Although Chebyshev and Elliptic filters
between patients. Therefore, EEG channels that were common to all                offer steeper roll-off, they often introduce phase and amplitude dis-
patients were selected. Furthermore, erroneous EEG channels were also            tortions, which can compromise the fidelity of EEG signals (Widmann
excluded to mitigate the impact of faulty channels on the prediction             et al., 2015). Fig. 5 represents the filtered signal after applying the BFB
model. For the CHB-MIT dataset, the channels ‘-’, ‘–0’, ‘–1’, ‘–2’, ‘–3’,        filter. Note that the Butterworth bandpass filter was selected not only


I.M. Ahmad et al.                                                                                       Computerized Medical Imaging and Graphics 130 (2026) 102759


                                                    Fig. 5. Applying Butterworth filter on iEEG data.


                                              Fig. 6. Features extracted for various channels in iEEG data.


for its favorable frequency characteristics but also based on empirical         the feature extraction process. The EEG windows, once transformed
evidence — unfiltered EEG data yielded classification accuracies below          into spectrograms using Short-Time Fourier Transform, are fed into the
60%, indicating that preprocessing was essential to enhance signal              CNN model to extract a feature vector.
quality and model performance.
                                                                                3.4. Hardware and software requirements
3.3. Feature extraction
                                                                                    The experiments were conducted on a system equipped with the
3.3.1. Handcrafted feature extraction                                           following hardware components: an AMD Ryzen 7 5800H CPU and a
    Handcrafted features were generated from 20-second overlapping              GeForce RTX Ti graphics processing unit (GPU), along with 64 GB of
windows with a 50% overlap of EEG data. The final set of features               RAM.
                                                                                    On the software side, the development environment was configured
included statistical measures, including mean, median, kurtosis, skew-
                                                                                using Python 3.10 as the primary programming language. For deep
ness, variance, standard deviation, power, root mean square (RMS),
                                                                                learning model implementation, we utilized TensorFlow 2.15.0 coupled
zero-crossing rate (ZCR), and signal envelope. Fig. 6 presents the
                                                                                with Keras 3.1.1 as the high-level neural network API. This combina-
handcrafted features extracted across multiple channels in the iEEG
                                                                                tion allowed for efficient model design and execution and leveraged
dataset, demonstrating spatial variability and feature diversity relevant
                                                                                the GPU for accelerated training. MATLAB was immensely useful for
to seizure prediction.
                                                                                visualizing signal data in various forms.

3.3.2. Short-time fourier transform                                             3.5. Model architecture
    The Short-Time Fourier Transform (STFT) was utilized to extract
frequency domain features from the EEG data segments. This technique                In this study, we propose a CNN-LSTM model, where CNN functions
provided a time-frequency representation of the EEG signals, which              as a feature extractor while LSTM is used for time series classifi-
is valuable for identifying patterns associated with seizure events.            cation. Given that the proposed architecture integrates two distinct
From this representation, spectrogram images, which visually represent          deep learning models—CNN and LSTM—we also evaluate each model
the frequency content of the EEG signals over time, were generated.             independently as a baseline for comparative analysis. The architec-
Fig. 7 shows a spectrogram extracted from a segment of channel 1.               tural details of the individual CNN and LSTM models, along with the
Various window lengths and overlaps were experimented with during               combined CNN-LSTM framework, are presented in this section.


I.M. Ahmad et al.                                                                                        Computerized Medical Imaging and Graphics 130 (2026) 102759


                                             Fig. 7. sample spectrograms extracted using STFT from channel 1.


                                                              Fig. 8. CNN Model Architecture.


3.5.1. Convolutional neural network (CNN)                                          in the EEG data. This is followed by a dropout rate of 0.2. The same
    A Convolutional Neural Network model is employed for spectro-                  alternating structure of layers is followed next. A Dense layer with a
gram analysis. Transfer learning with ResNet, MobileNet, and                       single unit and sigmoid activation function is used for the final binary
EfficientNet-B3, as well as a custom CNN model trained from scratch,               classification, distinguishing between interictal and preictal EEG states.
was explored to enhance model performance. The custom model per-                   The architecture of the custom LSTM network is provided in Fig. 9.
formed most optimally as discussed in the results section.
    A custom CNN model has been developed that processes 2D spectro-               3.5.3. Hybrid CNN-LSTM model
grams with an input shape of 129 × 92. The architecture includes two                   In the proposed hybrid architecture, we integrate both handcrafted
Conv1D layers with 64 and 128 filters, respectively. Both of the layers            and deep-learned features to enhance seizure prediction accuracy. First,
use a kernel size of 3 and ReLU activation. Each convolutional layer is            spectrograms are generated from EEG signal segments to capture time-
followed by a MaxPooling1D layer with a pool size of 2 and a Dropout               frequency information. These spectrograms are then fed into a cus-
layer having a dropout rate of 0.3, specifically for regularization. The           tom CNN, which extracts deep feature representations. Simultaneously,
model ends with a Flatten layer, followed by Dense layers with 128                 handcrafted features are derived from the same EEG segments to cap-
and 64 units. Each of these layers is accompanied by a dropout for                 ture statistical and signal-based characteristics.
optimal regularization. The final output layer uses sigmoid activation                 The deep CNN features are concatenated with the handcrafted
for binary classification, i.e., the preictal stage or the interictal stage.       features, forming a comprehensive feature matrix that encapsulates
The architecture of the custom CNN is provided in Fig. 8.                          both learned and domain-specific insights. This hybrid feature repre-
                                                                                   sentation serves as the input to the LSTM model, which is designed to
3.5.2. Long short-term memory (LSTM)                                               capture temporal dependencies in the sequential data. To ensure proper
   The analysis of the problem led to the understanding that for a                 label alignment, class labels are matched accordingly with each feature
10-minute segment, each 20-second spectrogram image is treated sep-                matrix.
arately, and the context for the sequence is not understood. Therefore,                This hybrid approach leverages the CNN’s strength in extracting
RNNs are crucial to solving this problem more efficiently. A Long Short-           spatial and frequency-domain patterns, alongside the LSTM’s capabil-
Term Memory network is designed to efficiently capture the temporal                ity to model temporal dynamics, ultimately leading to a robust and
dependencies in the combined feature vector obtained from the CNN                  generalizable prediction framework.
and handcrafted features. LSTMs are crucial for sequence prediction
problems due to their ability to maintain long-term dependencies and,              Methodological contribution. While CNN-LSTM combinations have been
most importantly, reduce the vanishing gradient problem common in                  explored in prior studies, our proposed framework introduces three
traditional Recurrent Neural Networks (RNNs). The LSTM component                   important innovations: (i) the use of a custom, lightweight CNN ar-
of the model comprises two layers. The first layer consists of 100                 chitecture tailored for spectrogram-based seizure prediction; (ii) the
units, which enables the network to learn complex temporal patterns                integration of handcrafted EEG signal features (e.g., skewness, kurtosis,


I.M. Ahmad et al.                                                                                                      Computerized Medical Imaging and Graphics 130 (2026) 102759


                                                                       Fig. 9. LSTM Model Architecture.


                    Table 3
                    Validation accuracy on CHB-MIT and testing accuracy on PINS-sEEG using the Custom CNN-LSTM model. Anticipation time for
                    all experiments: 600 s.
                     Feature extraction                                                                               Validation Acc. (% ± SD) Testing Acc. (%)
                     Handcrafted statistical features (mean, variance, skewness, standard deviation, kurtosis, entropy) 94.96 ± 1.10           84.50
                     Short-Time Fourier Transform (STFT)                                                                97.52 ± 0.78           87.22
                     Handcrafted + STFT                                                                                 98.84 ± 0.54           89.15


ZCR), chosen in consultation with clinical experts, with CNN-extracted                        4.1. Results on scalp EEG (sEEG) data
features to form a hybrid input; and (iii) the demonstration of gener-
alization across scalp and intracranial EEG modalities using a unified                            We first evaluated the proposed model on the CHB-MIT scalp EEG
training and evaluation pipeline. This design not only improves pre-                          dataset to assess its core performance on non-invasive data. As shown in
dictive accuracy but also supports real-time feasibility, enhancing the                       Table 3, the CNN-LSTM model achieved its highest accuracy of 98.84%
model’s translational value for clinical settings.                                            using a combination of handcrafted statistical features and Short-Time
                                                                                              Fourier Transform (STFT). This demonstrates the effectiveness of fea-
3.6. Training procedure                                                                       ture fusion for seizure prediction on scalp data and confirms the model’s
                                                                                              ability to handle lower-resolution scalp signals. The recall is 0.99, the
    We used subject-independent five-fold cross-validation to ensure
                                                                                              precision is 0.9803, and the FPR is 1.16%. The same model was then
reliable performance estimation and prevent data leakage. For the CHB-
                                                                                              tested on an unseen dataset (PINS-sEEG from General Hospital Lahore),
MIT dataset, EEG recordings from distinct patients were divided into
                                                                                              and the proposed method achieved an accuracy of 89.15% indicating
five non-overlapping subsets, ensuring that data from any single subject
                                                                                              the strong generalization ability of the model.
appeared in only one fold. In each iteration, four folds were used
for training and one for testing. This subject/session-wise partitioning
prevents overlap between training and test data and avoids the risk                           4.2. Generalization on invasive EEG (iEEG) data
of learning subject-specific patterns. The process was repeated five
times, and the final accuracy was computed as the average of the five                             We next assessed the model’s generalizability to invasive EEG data
individual test accuracies, providing a robust estimate of the model’s                        using the AES-Kaggle dataset. While we use the term ‘‘generalization’’
generalization to unseen subjects.                                                            in this section, it refers to the model’s robustness when applied to a
    The CNN model was trained for 100 epochs using the Adam opti-                             different EEG modality (iEEG) using the same training pipeline—not
mizer with an initial learning rate of 0.001 and binary cross-entropy as                      to training on one dataset and testing on the other. Each dataset was
the loss function. A learning rate scheduler was applied to exponentially                     treated as an independent validation scenario.
decay the learning rate by a factor of 0.9 per epoch. Additionally,                               Table 4 presents the performance of all models on the AES iEEG
a ReduceLROnPlateau callback was used to adjust the learning rate                             dataset. Since the proposed architecture integrates two distinct deep
dynamically. If the validation loss did not improve for five consecutive                      learning models, CNN and LSTM, we first conducted experiments using
epochs, the learning rate was reduced by a factor of 0.2, with a                              each of these models independently. ResNet achieved the lowest per-
minimum threshold of 0.001. To prevent overfitting, early stopping was                        formance across both feature types, reaching 61.18% with handcrafted
employed with a patience of five epochs. The model was trained with                           features and 55.61% with STFT features. In contrast, the custom CNN
a batch size of 32. These training parameters were selected to ensure                         trained from scratch achieved 83.97% with handcrafted features and
stable convergence and generalization across subjects and are reported                        85.61% with STFT. This shows that a task-specific shallow CNN extracts
here to support reproducibility. The primary evaluation metric was                            spatial patterns from EEG signals more effectively than the deeper
accuracy, with particular emphasis on the model’s ability to increase                         ResNet architecture. The LSTM model further improved performance,
anticipation time for seizure onset.                                                          obtaining 88.29% with handcrafted features and 89.47% with STFT.
    It is important to note that the CHB-MIT and AES-Kaggle datasets
                                                                                              This improvement reflects the importance of temporal modeling in EEG
were used independently. For each dataset, the model was trained and
                                                                                              analysis.
evaluated using 5-fold cross-validation, and no cross-dataset training
                                                                                                  The proposed hybrid CNN-LSTM model achieved the highest ac-
or testing was performed. This design allows for assessing the model’s
                                                                                              curacy across all configurations. It reached 94.12% with handcrafted
ability to generalize within each EEG modality, without introducing
                                                                                              features and 96.36% with STFT. When both handcrafted and STFT
bias from cross-domain transfer.
                                                                                              features were combined, accuracy increased to 97.18%, which is the
4. Results and discussion                                                                     best overall result.
                                                                                                  The false alarm rate, also known as the false positive rate is also a
    This section presents the experimental evaluation of the proposed                         very important indicator for the detection and prediction of epilepsy.
CNN-LSTM model across three stages: performance on scalp EEG (sEEG),                          Fig. 10 shows for the binary classification of preictal and interictal EEG
generalization to intracranial EEG (iEEG), and robustness under varying                       segments for the iEEG data using our custom CNN-LSTM model. In this
seizure anticipation times and real-world data. In all experiments,                           context, the positive class corresponds to preictal segments (i.e., in-
a Butterworth bandpass filter was applied during preprocessing to                             tervals preceding seizure onset), while the negative class corresponds
remove noise and retain relevant EEG frequency bands.                                         to interictal segments (i.e., seizure-free periods between events). The


I.M. Ahmad et al.                                                                                            Computerized Medical Imaging and Graphics 130 (2026) 102759


                    Table 4
                    Accuracy (% ± SD) of different models on AES iEEG dataset. Anticipation time for all experiments: 600 s.
                     Feature Extraction                          ResNet                 Custom CNN             LSTM                      CNN-LSTM
                     Handcrafted features                        61.18 ± 1.15           83.97 ± 0.95           88.29 ± 0.88              94.12 ± 1.05
                     Short-Time Fourier Transform (STFT)         55.61 ± 1.20           85.61 ± 0.72           89.47 ± 0.72              96.36 ± 0.82
                     Handcrafted + STFT                          65.23 ± 0.50           87.16 ± 0.82           91.48 ± 0.91              97.18 ± 0.65


                                                                                      Table 5
                                                                                      Prediction using a combination of STFT and handcrafted features with different
                                                                                      anticipation times of seizure.
                                                                                       Data                               Accuracy                            Time (s)
                                                                                       sEEG                               99.24%                              300
                                                                                       sEEG                               97.35%                              900
                                                                                       AES iEEG                           98.67%                              300
                                                                                       AES iEEG                           96.13%                              900


                                                                                      4.4. Testing on local sEEG recordings from Pakistan

                                                                                          To further validate the model in real-world clinical settings, scalp
                                                                                      EEG recordings were obtained from a patient at Punjab Institute of
                                                                                      Neurosciences (PINS), located at Lahore General Hospital, Pakistan.
                                                                                      This dataset included a documented seizure event. The dataset was
                                                                                      taken after IRB approval. It consisted of 5 segments with labeled
                                                                                      preictal and interictal segments. Each segment was 20 min in duration.
                                                                                          Experimental analysis was conducted on both the preictal and in-
                                                                                      terictal states using the proposed pre-trained model. The model was
                                                                                      pre-trained on the sEEG dataset. Despite hardware differences (KT88-
  Fig. 10. Confusion matrix representing model evaluation for iEEG data.              1032 device with 18–32 channels), preprocessing and channel realign-
                                                                                      ment enabled model compatibility. The model achieved an accuracy
                                                                                      of 89.15% on this dataset, demonstrating strong practical applicability
                                                                                      under previously unseen conditions. The high precision (90.12%) in-
model records a recall of 0.98 and a precision of 0.96. The false positive            dicates a low false alarm rate, while the recall of 88.47% reflects the
rate is 0.037.                                                                        model’s effectiveness in correctly identifying seizure events. Further-
    Fig. 10 presents the confusion matrix. The model achieved 207 true                more, the specificity of 89.24% and a relatively low false positive rate
positives and 203 true negatives, with only 8 false positives and                     of 10.84% confirm the model’s robustness in distinguishing non-seizure
4 false negatives. This translates to a recall of 99.33%, precision of                activity. Collectively, these results highlight the reliability and gener-
96.28%, false positive rate (FPR) of 3.79%, and false negative rate                   alization capability of the proposed approach for real-world EEG-based
(FNR) of 1.90%, yielding an overall accuracy of 97.16%. The low FPR                   seizure prediction.
indicates that the model generates few false seizure warnings, which
is critical for clinical applicability, while the high recall demonstrates            4.5. Comparison with state-of-the-art
its effectiveness in detecting imminent seizures with minimal missed
events.                                                                                   To benchmark the proposed CNN-LSTM model, we compared its
                                                                                      performance with recent state-of-the-art approaches for epileptic seizure
                                                                                      detection using the CHB-MIT scalp EEG dataset. Table 6 summarizes the
4.3. Seizure time anticipation
                                                                                      comparative results based on reported accuracies.
                                                                                          The proposed hybrid CNN-LSTM model achieved a classification
    The effectiveness of the proposed CNN-LSTM model in early seizure                 accuracy of 98.84%, exceeding the performance of several recent mod-
prediction was evaluated using varying anticipation windows of 5 and                  els, including the hybrid CNN-LSTM by Liu et al. (2024) and the
15 min, as summarized in Table 5. On the CHB-MIT (sEEG) dataset,                      MAFBN architecture by Shawly et al. (2025). Although Ghosh and
the model achieved a peak accuracy of 99.24% with a 5-minute an-                      Dey’s attention-augmented model reached a higher accuracy (99.70%),
ticipation window. As the anticipation window extended to 15 min,                     it relies on a computationally intensive architecture involving complex
accuracy slightly decreased to 97.35%, indicating a trade-off between                 time-frequency transformations and deep recurrent neural networks.
early prediction and predictive performance. Similarly, on the AES                    In contrast, our approach offers a much shallower, custom CNN-LSTM
(iEEG) dataset, the model maintained strong performance, achieving                    model that not only generalizes effectively across EEG modalities,
98.67% accuracy at 5 min and 96.13% at 15 min.                                        including invasive iEEG, but is also well-suited for real-world clinical
    These results show that shorter anticipation windows lead to higher               deployment due to its lower computational overhead.
prediction accuracy, likely due to stronger preictal signal characteris-
tics closer to the onset. Longer windows introduce greater variability                4.6. Clinical integration and real-world utility
and noise, making reliable prediction more difficult. Still, the model
demonstrates stable performance across both sEEG and iEEG datasets,                       Beyond strong predictive performance, the proposed model aligns
highlighting its adaptability to different electrode types and recording              with the broader goal of clinical deployment by offering practical utility
setups. This consistency suggests that the CNN-LSTM framework can                     for integration into CDSS. In real-world scenarios, timely and accurate
serve as a strong candidate for early warning systems in clinical or                  seizure prediction can enable clinicians to take preemptive measures,
home-based EEG monitoring applications, especially where rapid and                    adjust medication, or alert caregivers. Our unified preprocessing and
accurate prediction is critical.                                                      prediction pipeline is lightweight enough for real-time implementation


I.M. Ahmad et al.                                                                                             Computerized Medical Imaging and Graphics 130 (2026) 102759


                    Table 6
                    Comparison of the proposed CNN-LSTM with State-of-the-Art methods using the CHB-MIT dataset.
                     Ref.                          Year            Model                                                                       Accuracy
                     Liu et al. (2024)             2024            Multi-dimensional Hybrid Bilinear CNN-LSTM                                  98.44
                     Shawly et al. (2025)          2025            MAFBN: Multi-Attention Forward and Backward Network                         97.88
                     Ghosh and Dey (2024)          2024            CNN-BiLSTM-Attention with Multisynchrosqueezing Transform                   99.70
                     Patel (2024)                  2024            SeizureSight: 2D CNN-LSTM Hybrid                                            94.00
                     Helgesen (2024)               2024            Machine Learning-based Seizure Prediction                                   96.30
                     This Study                    2025            Custom CNN-LSTM (Handcrafted + STFT)                                        98.84


in hospital monitoring systems or wearable EEG devices. Moreover,                   performance and deployment feasibility using a hybrid CNN–LSTM
by validating the model on clinical EEG data from General Hospital                  architecture, future work will explore the integration of attention-based
Lahore, we demonstrate its robustness in non-controlled, real-world en-             and graph neural network approaches to enhance model explainability.
vironments. This paves the way for its integration into existing clinical           Finally, integration with wearable EEG hardware and collaboration
workflows as a seizure alert module within a CDSS framework. Such                   with clinical institutions will be essential for transitioning this research
integration can assist medical professionals in monitoring high-risk pa-            from the lab to the bedside.
tients, reducing false alarms, and improving treatment personalization
through data-driven insights.                                                       CRediT authorship contribution statement

4.7. Limitations and challenges                                                        Izza Mujeeb Ahmad: Writing – original draft, Methodology, In-
                                                                                    vestigation, Data curation, Conceptualization. Bisma Ashar: Writing
    The persistent high imbalance in the interictal-to-ictal ratio remains          – original draft, Validation, Methodology. Shehryar Munir: Writing –
a challenge that may impact the model’s generalization in real-time                 original draft, Methodology, Data curation, Conceptualization. Aamir
systems. Furthermore, while a subject-independent training approach                 Wali: Writing – review & editing, Writing – original draft, Validation,
was explored, the significant inter-subject variability in seizure patterns         Supervision. Muhammad Saif ul Islam: Writing – review & editing,
indicates that personalized models could provide further performance                Supervision.
enhancements, an aspect not fully addressed in this work. Although
local EEG testing in Pakistan demonstrated a promising 89.15% ac-                   Compliance with ethical standards
curacy, practical implementation revealed challenges with hardware
compatibility and signal variation, highlighting the need for more ro-                 This statement is to certify that the author list is correct. The Au-
bust preprocessing and model adaptation techniques. Lastly, even with               thors also confirm that this research has not been published previously
the model’s computationally efficient design, its seamless deployment               and that it is not under consideration for publication elsewhere. On
on low-power wearable devices for continuous real-                                  behalf of all Co-Authors, the Corresponding Author shall bear full
                                                                                    responsibility for the submission. There is no conflict of interest. This
5. Conclusion and future work                                                       research did not involve any human participants and/or animals.

    This study presents a robust and clinically relevant framework
                                                                                    Funding
for epileptic seizure prediction using deep learning across both non-
invasive scalp EEG (sEEG) and invasive intracranial EEG (iEEG) modal-
                                                                                       The authors did not receive support from any organization for the
ities. By leveraging the CHB-MIT and AES-Kaggle datasets, we designed
                                                                                    submitted work.
and evaluated a custom CNN, LSTM, and a hybrid CNN-LSTM architec-
ture. Among these, the proposed hybrid model demonstrated superior
                                                                                    Declaration of competing interest
performance, achieving 98.84% accuracy on sEEG and 97.18% on iEEG
with a 10-minute anticipation window.
                                                                                        The authors declare that they have no known competing finan-
    A key strength of our approach lies in its ability to combine spa-
                                                                                    cial interests or personal relationships that could have appeared to
tial and temporal representations through handcrafted features and
                                                                                    influence the work reported in this paper.
STFT-based spectral analysis, enabling accurate seizure prediction with
extended lead times. Unlike more computationally intensive models,
                                                                                    Data availability
our framework remains lightweight, generalizes well across modalities,
and supports real-time feasibility. This was further confirmed through
                                                                                       sEEG dataset was manually annotated. The dataset is available at:
validation on real-world scalp EEG data collected from General Hospital
Lahore, where the model maintained high performance under non-ideal                 https://physionet.org/content/chbmit/1.0.0/.
conditions.
    Overall, the findings validate our four core design objectives: im-             References
proved predictive accuracy, generalization across modalities, reduced
complexity, and early seizure anticipation. The results highlight the               Acharya, U.R., Sree, S.V., Swapna, G., Martis, R.J., Suri, J.S., 2013. Automated eeg
potential of the proposed model as a practical foundation for real-time,                analysis of epilepsy: A review. Knowl.-Based Syst. 45, 147–165. http://dx.doi.org/
patient-centered early warning systems that can enhance proactive                       10.1016/j.knosys.2013.02.014.
care and significantly improve the quality of life for individuals with             Ather, S., Wali, A., Malik, T.G., Fahd, K.M., Fatima, S., 2024. A novel vessel extraction
                                                                                        technique for a three-way classification of diabetic retinopathy using cascaded
epilepsy.                                                                               classifier. Multimedia Tools Appl. 83, 1–21.
    Future work will focus on expanding the datasets to include more                Bandarabadi, M., Teixeira, C.A., Rasekhi, J., Dourado, A., 2015. Epileptic seizure
diverse subjects and seizure types to enhance model robustness and                      prediction using relative spectral power features. Clin. Neurophysiol. 126, 237–248.
reduce bias. Additionally, deploying the model on edge devices or                   Craik, A., He, Y., Contreras-Vidal, J.L., 2019. Deep learning for electroencephalogram
                                                                                        (eeg) classification tasks: a review. J. Neural Eng. 16, 031001. http://dx.doi.org/
mobile platforms will be explored for real-time prediction. We also
                                                                                        10.1088/1741-2552/ab0ab5.
aim to investigate personalized models through transfer learning or                 Cui, S., Duan, L., Qiao, Y., Xiao, Y., 2018. Learning eeg synchronization patterns for
federated learning, enabling tailored predictions while preserving pa-                  epileptic seizure prediction using bag-of-wave features. J. Ambient. Intell. Humaniz.
tient privacy. While the present study focuses on maximizing predictive                 Comput. 1–16.


I.M. Ahmad et al.                                                                                                          Computerized Medical Imaging and Graphics 130 (2026) 102759


Cukierski, W., 2014. American epilepsy society seizure prediction challenge, kaggle.             Shahzad, N.A., Javaid, A., Wali, A., Naeem, M., 2025. A novel parallelnet model
    https://www.kaggle.com/c/seizure-prediction. (Accessed: 17 May 2025).                            with domain-specific feature integration for handwritten pattern recognition. Signal
Daoud, H., Williams, P., Bayoumi, M., 2020. 2020 IEEE 6th World Forum on Internet                    Image Video Process. 19, 719.
    of Things. WF-IoT, IEEE, pp. 1–6.                                                            Shahzad, A., Wali, A., 2022. Computerization of off-topic essay detection: a
Fadzal, C.C.W., Mansor, W., Khuan, L., Zabidi, A., 2012. Short-time fourier transform                possibility? Educ. Inf. Technol. 27, 5737–5747.
    analysis of eeg signal from writing. In: 2012 IEEE 8th International Colloquium on           Shawly, T., Alsheikhy, A.A., Said, Y., AbuEid, A.I., Alzahrani, A.A., Alshdadi, A.A.,
    Signal Processing and Its Applications. IEEE, pp. 525–527.                                       Ahmed, H.E., 2025. Mafbn: Multi-attention forward and backward network to
Fawaz, A., Ali, M.B., Adan, M., Mujtaba, M., Wali, A., 2021. A deep learning framework               predict epileptic seizure. Biomed. Signal Process. Control. 104, 107574.
    for efficient high-fidelity speech synthesis: Styletts. IKSP J. Comput. Sci. Eng. 1.         Shiao, H.-T., Cherkassky, V., Lee, J., Veber, B., Patterson, E.E., Brinkmann, B.H.,
Fu, R., Zhang, B., Xue, B., Wang, D., 2025. A spatiotemporal posterior graph convo-                  Worrell, G.A., 2016. Svm-based system for prediction of epileptic seizures from
    lutional neural network based on multihead attention with squeeze-and-excitation                 ieeg signal. IEEE Trans. Biomed. Eng. 64, 1011–1022.
    module for patient-specific epileptic seizure prediction. IEEE Trans. Instrum. Meas.         Slimen, I.B., Boubchir, L., Seddik, H., 2020. Epileptic seizure prediction based on eeg
    74, 1–13. http://dx.doi.org/10.1109/TIM.2025.3551573.                                            spikes detection of ictal-preictal states. J. Biomed. Res. 34, 162.
Ghosh, A., Dey, D., 2024. Digital twin for eeg seizure prediction using time re-                 Truong, N.D., Zhou, L., Kavehei, O., 2019. 2019 41st Annual International Conference
    assigned multisynchrosqueezing transform-based cnn-bilstm-attention mechanism                    of the IEEE Engineering in Medicine and Biology Society. EMBC, IEEE, pp.
    model. Biomed. Phys. Eng. Express 11, 015034.                                                    2369–2372.
Goldberger, A.L., Amaral, L.A.N., 2010. CHB-MIT scalp eeg database. http://dx.doi.org/           Usman, S.M., Khalid, S., Bashir, S., 2021. A deep learning based ensemble learning
    10.13026/C2K01R, https://physionet.org/content/chbmit/1.0.0/. (Accessed: 17                      method for epileptic seizure prediction. Comput. Biol. Med. 136, 104710.
    May 2025).                                                                                   Usman, S.M., Usman, M., Fong, S., et al., 2017. Epileptic seizures prediction using
Hamza, H.M., Wali, A., 2023. Pakistan sign language recognition: leveraging deep                     machine learning methods. Comput. Math. Methods Med. 2017.
    learning models with limited dataset. Mach. Vis. Appl. 34, 71.                               Varnosfaderani, S.M., Rahman, R., Sarhan, N.J., Kuhlmann, L., Asano, E., Luat, A., Al-
Hamza, H.M., Wali, A., 2025. Pakistan sign language recognition: From videos to                      hawari, M., 2021. 2021 IEEE 3rd International Conference on Artificial Intelligence
    images. Signal Image Video Process. 19, 1–25.                                                    Circuits and Systems. AICAS, IEEE, pp. 1–4.
Hazarika, N., Chen, J.Z., Tsoi, A.C., Sergejew, A., 1997. Classification of eeg signals          Widmann, A., Schröger, E., Maess, B., 2015. Digital filter design for electrophysiological
    using the wavelet transform. Signal Process. 59, 61–72.                                          data–a practical approach. J. Neurosci. Methods 250, 34–46. http://dx.doi.org/10.
Helgesen, M., 2024. Epileptic Seizure Prediction from EEG Signals using Machine                      1016/j.jneumeth.2014.08.002.
    Learning, Specialization Project in Cybernetics and Robotics. Norwegian University           Yan, J., Li, J., Xu, H., Yu, Y., Xu, T., 2022. Seizure prediction based on transformer
    of Science and Technology, Available from ResearchGate, (Accessed 20 January                     using scalp electroencephalogram. Appl. Sci. 12, 4158.
    2026).                                                                                       Yuan, S., Zhou, W., Chen, L., 2018. Epileptic seizure prediction using diffusion distance
ul Islam, M.S., Farooq, H., 2017. 2017 International Conference on Information and                   and bayesian linear discriminate analysis on intracranial eeg. Int. J. Neural Syst.
    Communication Technologies. ICICT, ICICT, pp. 23–27.                                             28, 1750043.
Liu, S., Wang, J., Li, S., Cai, L., 2024. Multi-dimensional hybrid bilinear CNN-LSTM
    models for epileptic seizure detection and prediction using eeg signals. J. Neural
    Eng. 21, 066045.
Liu, C.-L., Xiao, B., Hsaio, W.-H., Tseng, V.S., 2019. Epileptic seizure prediction with         Izza has a BS in Software Engineering. She was a research assistants in the DataGen
    multi-view convolutional neural networks. IEEE Access 7, 170352–170361.                      Lab, working on EEG data acquisition and analysis.
Mahmood, H., Iftikhar, M., Wali, A., Ali, A., Gulzar, M., 2024. A novel cascaded ap-
    proach for classification of tuberculosis using cough audio in real-time environment.
                                                                                                 Bisma has a BS in Software Engineering. She was a research assistants in the DataGen
    IEEE Access.
                                                                                                 Lab, working on EEG data acquisition and analysis.
Mazurek, S., Moore, S.E., Crimi, A., 2025. Graph attention networks for detecting
    epilepsy from eeg signals using accessible hardware in low-resource settings. IEEE
    Open J. Eng. Med. Biol. http://dx.doi.org/10.1109/OJEMB.2025.3642070.                        Shehryar has a BS in Software Engineering. He is a research assistants in the DataGen
Patel, J., 2024. 2024 3rd International Conference on Applied Artificial Intelligence            Lab, working on EEG data acquisition and analysis.
    and Computing. ICAAIC, IEEE, pp. 252–256.
Ryu, S., Joe, I., 2021. A hybrid densenet-lstm model for epileptic seizure prediction.
    Appl. Sci. 11, 7661.                                                                         Dr. Aamir Wali is Professor and Head of Data Science at FAST NUCES and Director
Savadkoohi, M., Oladunni, T., Thompson, L., 2020. A machine learning approach to                 of the DataGen Lab, conducting research on EEG data acquisition and analysis.
    epileptic seizure prediction using electroencephalogram (eeg) signal. Biocybern.
    Biomed. Eng. 40, 1328–1341.
Shahid, R., Wali, A., Bashir, M., 2024. Next word prediction for Urdu language using             Mr. Saif is a Lecturer in Data Science at FAST NUCES. He holds a Master’s in Data
    deep learning models. Comput. Speech Lang. 87, 101635.                                       Science and specializes in time series analysis, and provided his contributions in this
                                                                                                 domain.
```
