---
citation_key: "JangEtAl2026"
paper_id: "paper_296"
title: "Single-channel EEG-based seizure prediction using deep learning."
authors: "Dabin Jang; Ki-Young Jung; Young-Gyu Jeon; Tae-Joon Kim; Sang Kun Lee; Kyeong-Yuk Min"
year: 2026
doi: "10.1038/s41598-026-44670-7"
source: "publisher-pdf (doi: 10.1038/s41598-026-44670-7)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Single-channel EEG-based seizure prediction using deep learning.

**Citation:** `JangEtAl2026` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1038/s41598-026-44670-7](https://doi.org/10.1038/s41598-026-44670-7)
**Source PDF:** `full_pdf/Dabin2026.pdf`

## Abstract

S S Reliable seizure prediction can improve patient safety by enabling timely protective actions, yet most high-performing approaches E depend on multichannel EEG, limiting feasibility in wearable and low-power environments. This study developed an ultralight PR deep learning model for seizure prediction using only single-channel EEG and evaluated its clinical applicability under predefined, clinically actionable criteria: a seizure prediction horizon (SPH) of 2 minutes and a seizure occurrence period (SOP) of 30 minutes. A 37,985-parameter MobileNet-derived architecture was designed to process STFT spectrograms IN and validated using patient-specific leave-one-out cross-validation on the SNUH and CHB-MIT datasets. Performance was assessed using segment-based accuracy and false positive rate (FPR), along with event-based sensitivity computed under E SPH–SOP constraints. The model demonstrated strong and consistent performance across both datasets. In the SNUH L cohort, it achieved 85.97% accuracy, an FPR of 0.130, and 94.93% sensitivity, successfully predicting 95.08% of seizures C within the SOP window. In the CHB-MIT dataset, it reached 90.72% accuracy, an FPR of 0.092, and 97.92% sensitivity. These I findings provide the first evidence that single-channel EEG can support reliable seizure prediction within clinically meaningful T early-warning windows. The proposed lightweight model delivers multichannel-comparable performance while drastically R reducing computational demand, demonstrating strong potential for real-time deployment in wearable and patient-centered A epilepsy management systems.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Scientific Reports                                                                                      https://doi.org/10.1038/s41598-026-44670-7


Article in Press

Single-channel EEG-based seizure prediction
using deep learning

Received: 28 November 2025                           Dabin Jang, Ki-Young Jung, Young-Gyu Jeon, Tae-Joon Kim, Sang Kun Lee & Kyeong-
Accepted: 12 March 2026                              Yuk Min


Cite this article as: Jang D., Jung K.,              We are providing an unedited version of this manuscript to give early access to its
Jeon Y. et al. Single-channel EEG-based              findings. Before final publication, the manuscript will undergo further editing. Please


                                                                                                              S
seizure prediction using deep learning.              note there may be errors present which affect the content, and all legal disclaimers
                                                     apply.

                                                                                                            S
Sci Rep (2026). https://doi.org/10.1038/


                                                                                                E
s41598-026-44670-7                                     If this paper is publishing under a Transparent Peer Review model then Peer


                                                                                              R
                                                     Review reports will publish with the final article.


                                                                                            P
                                                                               IN
                                                             L E
                                                 I         C
                                             R T
                                       A


© The Author(s) 2026. Open Access This article is licensed under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International
License, which permits any non-commercial use, sharing, distribution and reproduction in any medium or format, as long as you give appropriate credit
to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if you modified the licensed material. You do
not have permission under this licence to share adapted material derived from this article or parts of it. The images or other third party material in this
article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the
article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain
permission directly from the copyright holder. To view a copy of this licence, visit http://creativecommons.org/licenses/by-nc-nd/4.0/.

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


Single-Channel EEG-Based Seizure Prediction Using
Deep Learning
Dabin Jang1,+ , Ki-Young Jung2,3,4,+ , Young-Gyu Jeon1 , Tae-Joon Kim5 , Sang Kun Lee2,† ,
and Kyeong-Yuk Min6,*
1 Department of Biomedical Engineering, Hanyang University, Seoul, 04763, Republic of Korea
2 Department of Neurology, Seoul National University Hospital, Seoul, 03080, Republic of Korea
3 Seoul National University College of Medicine, Seoul, 03080, Republic of Korea
4 Seoul National University Medical Research Center, Neuroscience Research Institute, Sensory Organ Research

Institute, Seoul, 03080, Republic of Korea
5 Department of Neurology, Ajou University School of Medicine, Suwon, 16499, Republic of Korea
6 Department of Electronics Engineering, Hanyang University, Seoul, 04763, Republic of Korea
* Corresponding author: kymin@hanyang.ac.kr
† Co-corresponding author: sangkun2923@gmail.com
+ These authors contributed equally as first authors.


ABSTRACT


                                                                                    S S
Reliable seizure prediction can improve patient safety by enabling timely protective actions, yet most high-performing approaches


                                                                                  E
depend on multichannel EEG, limiting feasibility in wearable and low-power environments. This study developed an ultralight


                                                                         PR
deep learning model for seizure prediction using only single-channel EEG and evaluated its clinical applicability under
predefined, clinically actionable criteria: a seizure prediction horizon (SPH) of 2 minutes and a seizure occurrence period
(SOP) of 30 minutes. A 37,985-parameter MobileNet-derived architecture was designed to process STFT spectrograms


                                                               IN
and validated using patient-specific leave-one-out cross-validation on the SNUH and CHB-MIT datasets. Performance was
assessed using segment-based accuracy and false positive rate (FPR), along with event-based sensitivity computed under


                                           E
SPH–SOP constraints. The model demonstrated strong and consistent performance across both datasets. In the SNUH


                                         L
cohort, it achieved 85.97% accuracy, an FPR of 0.130, and 94.93% sensitivity, successfully predicting 95.08% of seizures


                                       C
within the SOP window. In the CHB-MIT dataset, it reached 90.72% accuracy, an FPR of 0.092, and 97.92% sensitivity. These


                                      I
findings provide the first evidence that single-channel EEG can support reliable seizure prediction within clinically meaningful


                                    T
early-warning windows. The proposed lightweight model delivers multichannel-comparable performance while drastically


                                   R
reducing computational demand, demonstrating strong potential for real-time deployment in wearable and patient-centered


                                 A
epilepsy management systems.


1 Introduction
Epilepsy is a chronic neurological disease characterized by recurrent, unprovoked seizures, affecting approximately 50 million
people worldwide 1 . Despite the development of new pharmacological and non-pharmacological treatments, including epilepsy
surgery, vagus nerve stimulation, and deep brain stimulation, about one-third of patients remain refractory to current treatment
modalities 2, 3 . The unpredictable nature of seizure occurrence can impose a significant burden on patients’ daily living and
psychosocial well-being 4 . Seizure prediction technologies offer patients the ability to prepare in advance, reducing both physical
and psychological risks and enhancing their quality of life 5 . Recent advances in artificial intelligence (AI) have significantly
improved seizure prediction accuracy using EEG signals 7–9 . Models leveraging short-time Fourier transform (STFT) and
attention mechanisms have achieved accuracies above 90%, effectively integrating local and global EEG features while
capturing inter-channel dependencies. Transformer-based architectures using STFT images further enhance spatiotemporal
pattern learning, reaching Area Under the Curve(AUC) values of up to 0.923 and sensitivities exceeding 93%. Additionally,
Vision Transformer models employing Continuous Wavelet Transform (CWT) scalograms from multi-channel EEG data have
demonstrated sensitivities and accuracies as high as 99.8% with false positive rates as low as 0.004. While highly effective,
these methods often require intensive preprocessing and substantial computational resources, limiting their practical deployment
in real-time or wearable settings. To improve computational efficiency, several studies have shifted toward simpler models
using raw EEG data. LSTM-based architectures have been applied to capture temporal dynamics directly, while hybrid models
combining CNNs for spatial features and LSTMs for temporal patterns have achieved high accuracy—up to 99.6%—with
minimal preprocessing and low false positive rates 10 . Despite significant progress in seizure prediction, the majority of existing

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


models rely on in-lab multichannel EEG data, which limits their applicability in real-world, ambulatory settings. This gap
underscores the need for lightweight, computationally efficient models that can reliably predict seizures using single-channel
EEG signals, particularly in the context of wearable devices. To address this critical gap, this study explores the feasibility of
reliable seizure prediction using only a single EEG channel. We propose a lightweight deep learning model, adapted from the
MobileNet architecture, specifically optimized for computational efficiency and minimal channel input. This paper details the
model’s development and evaluates its performance on two distinct scalp EEG datasets. Our goal is to establish a foundation
for practical, long-term monitoring systems that balance predictive performance with the stringent constraints of real-world
wearable applications.

2 Methods
2.1 . Dataset and predefined channel selection for single-channel evaluation
This study employed two EEG datasets—the Seoul National University Hospital (SNUH) dataset and the Children’s Hospital
Boston-Massachusetts Institute of Technology (CHB-MIT) dataset—for training and evaluating the seizure prediction model.
The SNUH dataset includes recordings from 52 patients diagnosed with drug-resistant focal epilepsy, aged between 16 and 74
years. A total of 112 seizures were recorded using the international 10–20 electrode placement system at a sampling rate of 200
Hz. EEG signals were acquired from 21 scalp electrodes (Fp1, F3, C3, P3, Fp2, F4, C4, P4, F7, T1, T3, T5, O1, F8, T2, T4,
T6, O2, Fz, Cz, and Pz), with a common average reference. The CHB-MIT dataset, a publicly accessible and widely cited
benchmark in seizure prediction research, was also included for comparative analysis. It contains EEG recordings from 23
pediatric patients (aged 1.5 to 22 years) collected at Children’s Hospital Boston. A total of 198 seizure events are annotated,
and the data were recorded at a sampling rate of 256 Hz. EEG acquisition employed 18 bipolar channels: Fp1-F7, F7-T7,


                                                                                      S
T7-P7, P7-O1, Fp1-F3, F3-C3, C3-P3, P3-O1, Fp2-F4, F4-C4, C4-P4, P4-O2, Fp2-F8, F8-T8, T8-P8, P8-O2, Fz-Cz, and


                                                                                    S
Cz-Pz (Supplementary table 1). In this study, “single-channel EEG” denotes that the model receives one EEG derivation as the


                                                                                  E
sole input at a time. To ensure feasibility for real-world deployment, we predefined a wearable-feasible candidate set prior


                                                                         PR
to any model training. Specifically, we limited candidate channels to six scalp locations—Fp1, Fp2, T3/T7, T4/T8, O1, and
O2—chosen to support easy attachment with minimal electrodes while maintaining coverage of common focal seizure onset
regions. For the SNUH dataset, these six locations included as unipolar channels against common average reference. For the


                                                               IN
CHB-MIT dataset, which is provided in a bipolar montage, we selected bipolar derivations that best correspond to the same
six scalp locations by mapping each predefined unipolar site to its closest available bipolar pair (e.g., Fp1–F7 and Fp2–F8

                                           E
for frontal; T7–P7 and T8–P8 for temporal; P7–O1 and P8–O2 for occipital). Thus, the evaluated “single-channel” inputs

                                         L
represent a prespecified, cross-dataset-consistent channel set rather than a post hoc selection from all available channels. In

                                       C
                                      I
addition, we assessed whether prediction performance differed by region (frontal/temporal/occipital) and laterality (left/right).


                                    T
As summarized in Table 2, we found no meaningful differences in prediction performance across regions and/or laterality,


                                   R
supporting the use of the predefined wearable-feasible channel set for single-channel evaluation. For model training and


                                 A
validation, only patients with at least two documented seizure events were included. Consequently, the final analysis comprised
62 seizures from 23 patients in the SNUH dataset and 54 seizures from 16 patients in the CHB-MIT dataset (Supplementary
table 1). The seizure focus distribution for the SNUH final analysis set is summarized in Supplementary Table 2. In contrast,
detailed seizure-type/focus annotations are not consistently available at the individual-event level in the CHB-MIT dataset,
limiting stratified analyses by seizure subtype for that cohort. This study was approved by the Seoul National University
Hospital Institutional Review Board (IRB No. H-2308-042-1456) and followed the principles of the Declaration of Helsinki.
The requirement for written consent was waived due to the retrospective design.

2.2 Data Labelling
The entire EEG signals were categorized into three states—ictal, interictal, and preictal—relative to seizure onset 15 . This
categorization enables the model to distinguish between normal brain activity, seizure events, and the critical preictal window
where predictive features are likely to emerge. For both training and evaluation, only interictal and preictal data were used,
excluding ictal data. The ictal state refers to the interval between the onset and the termination of a seizure. The onset and
termination points were determined by two epilepsy specialists (JK and KT) through visual analysis of EEG signals and video
recordings. In cases where the seizure boundaries were ambiguous, the two specialists reached a consensus to finalize the
decision. Because the postictal state can persist for hours and differs from true interictal baseline 16 , we conservatively defined
a 3-hour postictal exclusion window. To prevent potential analytical bias from seizure clusters, any time segment between two
seizures occurring within a 3-hour window was excluded from the analysis. Specifically, if a seizure began within 3 hours of
the previous one’s termination, the interval between them was not labeled as interictal or preictal and was omitted from both
training and evaluation. The preictal state corresponds to an arbitrary interval before a seizure, where predictive information is
presumed to exist. The definition of the preictal interval depends on two parameters: seizure prediction horizon (SPH) and
seizure occurrence period (SOP) 15 . The SPH represents the minimum time before seizure onset during which a warning must


                                                                                                                                   /

                                           ACCEPTED
                                             ARTICLE IN
                                                    MANUSCRIPT
                                                        PRESS


occur. It ensures no seizures occur during this interval, and its validity is evaluated based on subsequent seizure occurrences.
The SOP defines the time window following the SPH during which a warning is considered valid. A shorter SOP enhances the
specificity of predicting seizure onset but risks missing seizures if set too narrowly. Thus, the SOP is determined by balancing
prediction accuracy with practical applicability 15 . In this study, the SPH was set to 2 minutes, ensuring that warnings are
issued at least 2 minutes before seizure onset, allowing patients to prepare. The SOP was set to 30 minutes, validating seizure
occurrence within 30 minutes after the SPH. Consequently, the preictal state was defined as the interval from 2 to 32 minutes
before seizure onset. A schematic overview of the EEG state labeling is shown in Supplementary Figure 1. The figure illustrates
the temporal relationship among interictal, preictal, and ictal states, as well as the SPH, SOP, and the 3-hour exclusion windows
applied around seizure onset.

2.3 Data Preprocessing
The sampling frequencies of all datasets were unified to the lowest sampling frequency by downsampling the CHB-MIT dataset
to 200 Hz to ensure a consistent experimental environment while minimizing data loss. Additionally, we used a fifth order
Butterworth band pass filter from 0.1 to 50 Hz to remove baseline drift and power noise. A sliding window approach was
applied to both preictal and interictal data into 10-second windows with 50% overlap to maintain the continuity of signal
characteristics while increasing the amount of training data 20 . The 10-second window length was selected to balance temporal
resolution and spectral stability and has been commonly adopted in prior seizure prediction studies. Although some seizures in
the CHB-MIT dataset have relatively short durations, the proposed framework focuses on identifying preictal patterns preceding
seizure onset rather than modeling seizure duration itself, and is therefore applicable even for seizures with short ictal durations.
For the interictal data, after excluding certain segments used for evaluation, random sampling was applied to the remaining
interictal data for each epoch, ensuring that the total length of the sampled interictal data matched the length of the preictal


                                                                                      S
data. This approach maximized the utilization of the dataset while maintaining a consistent ratio between the preictal and


                                                                                    S
interictal data during training. The raw EEG signals were transformed into spectrograms in the time-frequency domain using


                                                                                  E
the STFT. The STFT enables the analysis of the data, originally consisting of temporal information, as images containing both


                                                                          PR
time and frequency components 21 . A Hann window with a frame length of 50 was used during the transformation process, with
50% overlap applied to enhance the time resolution. In the resulting spectrogram, frequencies corresponding to DC and those
above 50 Hz were removed through slicing. As a result, the input data were represented as a tensor of size (80, 63, 1). The


                                                                IN
first dimension corresponds to the number of time frames generated by the sliding STFT window within a 10-second segment,
the second dimension represents the number of frequency bins within the analyzed frequency range, and the third dimension


                                         L E
denotes the single EEG channel used in this study.

2.4 Model design
                                      IC
                                    T
The model used in this study is designed to operate on mobile devices and is based on the well-known MobileNet architecture.


                                   R
MobileNet utilizes a lightweight convolution operation called Depthwise Separable Convolution (DSC). DSC combines


                                 A
depthwise convolution and pointwise convolution to improve computational efficiency, enabling a lightweight model design
while maintaining high performance 22 . When implementing layers with the same input and output using DSC, the computational
load can be reduced by the number of output channels compared to conventional convolution. Additionally, stride (one of the
hyperparameters of depthwise convolution) reduces the size of the feature map, thereby decreasing the computational load
while preserving the essential characteristics. The low-resolution single-channel input data used in this study is not directly
compatible with MobileNet. The repeated use of stride in deeper layers would significantly reduce the size of the feature maps,
which may lead to potential loss of information. To mitigate this, we modified the original MobileNet architecture to maintain
its lightweight computational efficiency while optimizing it specifically for low-resolution data, ensuring the preservation of
essential features during training. While the original MobileNet contains 3,230,338 parameters, our modified architecture
drastically reduces both the number of layers and channels, using only 37,985 parameters—just 1.18% of the original size
(Supplementary Table 2). Furthermore, unlike MobileNet, the first convolutional layer in our model employs a stride of 1,
minimizing information loss at the initial stage. The overall reduction in depth also helps prevent information degradation
due to excessive feature map downsampling in deeper layers. This architecture is especially suitable for mobile devices, as it
requires substantially less memory and can operate effectively in resource-constrained environments.

2.5 Patient-specific cross validation
Considering the inter-patient variability in seizure signal characteristics, patient-specific leave one out cross validation (LOOCV)
was applied to ensure a reliable evaluation of the model’s performance. The term "patient-specific" refers to constructing
both the training and validation datasets only using the data from the same patient (i.e., wihtin-subject evaluation). Notably,
“patient-specific” refers to within-subject modeling and does not imply a universal optimal channel across subjects or cohorts.
In addition, candidate channels were restricted to a wearable-feasible set and evaluated accordingly (Fp1, Fp2, T3/T7, T4/T8,
O1, O2). This approach allows the model to effectively learn and recognize the unique EEG characteristics and seizure patterns


                                                                                                                                   /

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


23 . The final score for each patient was calculated by averaging their N trial results. Due to the temporal continuity of EEG

signals, if data sampled from the same preictal segment is used in both training and evaluation, the model’s reliability could be
compromised 24 . To address this, each validation sample was constructed using one preictal segment determined by a specific
ictal event during the labeling process, along with a 30-minute continuous segment randomly extracted from the interictal
data. This setup ensures that the model is evaluated on entirely unseen preictal activity, thereby preserving the integrity of the
assessment and its relevance to real-world seizure prediction tasks.

2.6 Postprocessing for evaluation
In consideration of the usability in clinical practice, the firing power method was applied to the individual window judgment
results of the seizure prediction model 27 . This method was chosen for its ability to enhance the interpretability of the model’s
predictions and improve its practical application in real-world clinical settings. The firing power (FP) is calculated as follows.


                ∑xk=x−N O[k]
      FP[x] =                                                                                                                  (1)
                     N
    FP[x] represents the firing power value between 0 and 1 at time x, while N denotes the number of observed windows. O[k]
takes a value of 1 when it is more like preictal and 0 when it is more like interictal. The decision to generate an alarm based on
FP[x] is determined as follows.

             (
              True, FP[x] ≥ T,
      a[x] =                                                                                                                   (2)

                                                                                     S
              False, FP[x] < T,


                                                                                 E S
    Here, a[x] indicates whether an alarm is generated, and T is a threshold value, which was set to 0.5 in this study. The


                                                                        PR
selection of the smoothing window, N = 119, is empirically supported by performance metrics (Fig. 1) but more fundamentally
reflects a deliberate clinical trade-off essential for real-world applicability 15 . A smaller window increases responsiveness
to preictal signals but is highly susceptible to transient noise, elevating the false positive rate 15 . Frequent false alarms are


                                                              IN
a significant barrier to adoption, as they can induce patient anxiety and "alarm fatigue," ultimately disrupting daily life and
eroding trust in the warning system 26 . Conversely, a larger window enhances system stability and reduces false alarms but

                                           E
introduces a critical risk of delaying the warning 15, 26 . This delay could shorten the actionable window for intervention or

                                         L
cause brief, subtle preictal states to be overlooked entirely 15 . Therefore, the value N = 119 represents a carefully calibrated


                                      IC
equilibrium, optimized to maintain high predictive sensitivity while minimizing the false alarm rate to a level deemed acceptable

                                    T
for long-term clinical use and patient quality of life 26 . Seizure alarms were triggered when the Firing Power value first

                                   R
exceeded the threshold of 0.5. All models were trained using the Adam optimizer with a learning rate of 0.001 and a weight

                                 A
decay of 0.0005. Binary cross-entropy was used as the loss function, and the evaluation metrics included binary accuracy,
precision, recall, and the area under the ROC curve (AUC-ROC). A batch size of 16 was used for training, and models were
trained for up to 300 epochs. To prevent overfitting, early stopping with a patience of 30 epochs was employed, starting from
the 100th epoch. The best model was selected based on the highest validation accuracy.

2.7 Evaluation of seizure prediction performance
To quantitatively evaluate the seizure prediction model and verify its applicability in real-world settings, both Segment-based
Evaluation and Event-based Evaluation metrics were employed. Specifically, Segment-based Evaluation metrics include
Accuracy and FPR, while Event-based Evaluation focuses on Sensitivity 15 . Segment-based Evaluation assesses the model’s
ability to correctly predict each evaluation segment. In the case of binary classification tasks, performance metrics such as
Accuracy and FPR are calculated using a confusion matrix. Accuracy represents the proportion of correctly predicted instances
out of the total dataset, providing a measure of the model’s overall performance. FPR, on the other hand, indicates the proportion
of interictal segments misclassified as preictal, reflecting the occurrence of unnecessary warnings. A low FPR is essential
for enhancing the reliability of the warning system, as it reduces false alarms and minimizes the burden on both patients and
medical professionals. Event-based Evaluation, in contrast, focuses on determining whether the issued warnings accurately
detect seizure events. Sensitivity is defined as the proportion of preictal segments determined by ictal events where warnings are
issued within the desired period. This metric evaluates the model’s success rate in predicting seizures in real-world scenarios.

2.8 Evaluation of single-channel performance in relation to seizure focus proximity
We evaluated whether single-channel prediction performance differed as a function of anatomical proximity between the EEG
channel and the clinically determined seizure focus. For each patient, prediction performance was computed separately for six
wearable-feasible scalp channels, yielding a repeated-measures structure (multiple channels nested within each patient). We


                                                                                                                                 /

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


operationalized “proximity to seizure focus” as a binary indicator (MatchFocus) based on concordance of both hemisphere and
lobar region between the clinical focus label and channel location. Channels were mapped to hemisphere and region as follows:
frontal (Fp1 left, Fp2 right), temporal (T3/T7 left, T4/T8 right), and occipital (O1 left, O2 right). Clinical focus labels were
categorized by hemisphere (left, right, bilateral) and lobe (FLE, TLE, OLE). MatchFocus was coded as 1 when the channel
was in the same lobe and ipsilateral to the focus; for bilateral foci, MatchFocus was coded as 1 for both hemispheres within
the same lobe. All other channel–focus pairs were coded as 0. To test whether focus-matched channels improved accuracy
(ACC), we fitted linear mixed-effects models with random intercepts for patient to account for within-patient correlation across
channels: Model A: ACC MatchFocus + (1 | Patient). To control for systematic differences among channels independent
of focus, we additionally fitted: Model B: ACC MatchFocus + Channel + (1 | Patient), where Channel was included as
a categorical fixed effect. The incremental contribution of MatchFocus in Model B was assessed using a likelihood ratio
test (LRT) comparing Model B to a nested model excluding MatchFocus. False-positive rate (FPR) was bounded (0–1) and
exhibited substantial zero inflation (many observations with FPR = 0). Therefore, we used a two-part hurdle modeling strategy:
Part 1 (occurrence): a mixed-effects logistic model for the probability of any false positives, Pr(FPR > 0), with fixed effects for
MatchFocus and Channel and a patient-level random intercept. Part 2 (magnitude): among observations with FPR > 0, we
modeled the magnitude of FPR after logit transformation, logit(FPR), using a linear mixed-effects model with MatchFocus and
Channel as fixed effects and a patient-level random intercept. The incremental contribution of MatchFocus was tested using
an LRT against a nested model excluding MatchFocus. Effects on the logit scale were exponentiated to report odds ratios for
interpretability. Analyses were conducted in Python using mixed-effects modeling frameworks. Two-sided tests were used with
α = 0.05. Effect sizes are reported as regression coefficients with 95% confidence intervals (or approximate intervals for the
logistic mixed model).


                                                                                     S
3 Results


                                                                                 E S
The following sections detail the model’s performance, evaluated using a subject-specific Leave-One-Out Cross-Validation


                                                                         PR
(LOOCV) protocol. All reported performance metrics, including accuracy, FPR, and sensitivity, represent the average values
calculated across all cross-validation folds for each patient.


                                                               IN
3.1 Segment-based performance
A central finding of this study is that the model’s predictive power was consistently highest when utilizing data from the

                                           E
prefrontal channels (Table 2). In the SNUH dataset, the Fp2 channel yielded the best performance, achieving an accuracy of

                                         L
85.97% and a false positive rate (FPR) of 0.130 (Table 1). This finding was replicated in the CHB-MIT dataset, where the Fp1

                                       C
                                      I
channel demonstrated superior performance with 90.72% accuracy and an FPR of 0.092 (Table 3). Detailed segment-based


                                    T
performance results for the CHB-MIT dataset evaluated with k = 60 and n = 119 are provided in Supplementary Table 4,


                                   R
further supporting the robustness of these findings. This prefrontal advantage was further substantiated by regional analysis.


                                 A
Across both datasets, the frontal region consistently outperformed the temporal and occipital regions in all performance metrics.
A comprehensive summary of channel-wise performance across all EEG channels, presented as mean ± standard deviation, is
provided in Table 4. While this trend was robust, performance variability was observed at the individual patient level, with some
patients demonstrating consistently high performance across all channels and others showing lower predictive accuracy. This
variability underscores the patient-specific nature of seizure dynamics and highlights the importance of personalized modeling
approaches.

3.2 Event-based performance
In the sensitivity analysis of seizure prediction shown in Table 3, the SNUH dataset shows the highest prediction success rate in
the channel corresponding to Fp2 (94.93%). In contrast, the CHB-MIT dataset shows the highest prediction success rate in the
channel corresponding to Fp1 (97.92%) (see Supplementary Table 4). However, certain channels failed to detect seizures for
specific patients. For example, in the SNUH dataset, seizures were undetected in the T3 channel for patient 11, while in the
CHB-MIT dataset, the P7-O1 channel failed to detect seizures for patient 11.

3.3 Seizure prediction pattern
Fig. 2 illustrates the seizure prediction patterns, showing the prediction value for individual windows (10 s), the timing of
seizure alarms, and the actual seizure onset. This analysis highlights the model’s ability to capture preictal states in most
cases while acknowledging limitations in detecting some seizures and managing transient patterns. Out of 62 seizures in the
SNUH dataset from the included SNUH patients ( ≥2 seizures), 48 (77.4%) were successfully predicted with consistent preictal
states detected before seizure onset. Among these, the most common pattern, observed in 43 seizures (Fig. 2a), involved
detecting the preictal state starting 30 minutes before seizure onset. Additionally, 4 seizures (Fig. 2b) and 1 seizure (Fig. 2c)
exhibited preictal states beginning 20 minutes and 10 minutes before onset, respectively. However, 11 seizures demonstrated


                                                                                                                                 /

                                           ACCEPTED
                                             ARTICLE IN
                                                    MANUSCRIPT
                                                        PRESS


less consistent or intermittent preictal patterns (Fig. 2d-f), and 3 seizures were not predicted by the model. In total, the model
successfully predicted 95.16% of seizures, accounting for all cases in which preictal activity was present and could be reliably
identified.

3.4 Seizure focus proximity effect on prediction performance
The analysis included 23 patients, each evaluated on six channels (total 138 patient–channel observations). In the unadjusted
mixed model (Model A), MatchFocus was not associated with higher ACC (β = −0.60 percentage points; 95% CI −4.59
to 3.40; p = 0.77), indicating no detectable advantage for focus-matched channels in accuracy. After adjusting for channel
identity (Model B), the MatchFocus effect remained nonsignificant and small (β = 1.33 percentage points; 95% CI −3.07 to
5.72; p = 0.55). The likelihood ratio test (LRT) comparing the adjusted models with versus without MatchFocus showed no
incremental explanatory value of MatchFocus (χ 2 (1) = 0.35; p = 0.55).
    Because the false positive rate (FPR) was frequently zero, we applied a hurdle mixed-model strategy. MatchFocus (Part 1)
showed no clear association with the probability of observing any false positives (log-odds = 0.19; OR ≈ 1.21; approximate
95% interval 0.46 to 3.19). In contrast, conditional on FPR being nonzero (Part 2), focus-matched channels were associated
with higher FPR. In the mixed-effects model on logit(FPR), MatchFocus was significantly positive (β = 1.35; SE = 0.47;
p = 0.004), corresponding to an odds ratio of 3.84 for FPR/(1 − FPR) (95% CI 1.52 to 9.73). The LRT confirmed improved
model fit when adding MatchFocus (χ 2 (1) = 7.29; p = 0.0069).

4 Discussion
LightSeizureNet is a lightweight, interpretable deep learning model for real-time seizure detection on ultra-low-power devices27 .


                                                                                      S
While it demonstrates that compact architectures can achieve high detection accuracy. Our study builds on this lightweight


                                                                                    S
approach but applies it to single-channel seizure prediction with validated SOP/SPH windows, enabling proactive rather than


                                                                                  E
reactive clinical use. By setting the seizure prediction horizon (SPH) to 2 minutes and the seizure occurrence period (SOP) to


                                                                          PR
30 minutes, this study adopts a clinically meaningful configuration that balances early warning capability with patient usability.
The SPH defines the minimum lead time before seizure onset during which a warning must be issued to be considered valid,
while the SOP represents the window following the SPH within which a seizure is expected to occur. This approach is consistent


                                                                IN
with prior work by Truong et al. (2018), who used a 5-minute SPH and 30-minute SOP in their CNN-based prediction model23 ,
and with trends reviewed by Ren et al. (2022), which emphasize a 30-minute SOP as the most widely used standard due to

                                           E
its practicality and patient acceptance15 . The 2-minute SPH in this study was carefully chosen to allow sufficient time for

                                         L
patients or caregivers to initiate precautionary actions before seizure onset, such as assuming a safe position, alerting assistance,

                                       C
                                      I
or taking preemptive medication. Although shorter than the SPH used in some prior models, our design prioritizes minimal


                                    T
false predictions while maintaining high sensitivity. Ren et al. note that an SPH shorter than 2 minutes may limit intervention


                                   R
potential, while an overly long SOP could lead to unnecessary anxiety due to prolonged alert states. Importantly, these SPH and


                                 A
SOP values also support robust evaluation under event-based criteria. In this framework, a seizure is considered successfully
predicted only if it occurs after the SPH and within the SOP, reducing the likelihood of misclassifying coincidental warnings as
true positives. This rigorous setup enhances the clinical credibility of the model’s predictions, making them both temporally
precise and actionable in real-world, wearable-device scenarios.
    Lu et al. (2024) also attempted single-channel EEG–based seizure prediction using STFT spectrograms and lightweight
CNNs13 , but there are several key differences. While our study proposes channel selection optimized for wearable device
applicability, Lu et al.’s work presented prediction results based on a randomly selected single channel. Such a method of
channel selection is not suitable for wearable applications. Our study evaluated performance under predefined SOP (30 min) and
SPH (2 min)—criteria essential for real-world applicability. We further validated a more compact model (37,985 vs. 213,597
parameters) on both a public dataset and a large in-hospital cohort, using patient-specific cross-validation and post-processing
to minimize false alarms. These methodological advances yielded high sensitivity with low false positives, demonstrating
stronger suitability for clinically reliable, wearable seizure prediction.
    Across patients and channels, proximity to the clinically defined seizure focus (ipsilateral, same-lobe channel) did not
confer a measurable improvement in prediction accuracy. This result remained unchanged after controlling for channel identity,
suggesting that channel selection based solely on anatomical assumptions (e.g., selecting the electrode nearest the presumed
focus) is not sufficient in a wearable-feasible scalp setting. This supports the concept that preictal dynamics detectable
on scalp EEG are not strictly localized to the seizure onset zone, but can reflect distributed network-level changes and/or
volume-conducted activity24 .
    Although focus proximity was not associated with the probability of observing any false positives (Pr[FPR > 0]), it was
associated with higher FPR magnitude conditional on FPR being nonzero. One possible explanation is that channels concordant
with the clinical focus may capture more frequent preictal-like fluctuations or nonstationary activity patterns that increase
false alarms, even if these do not improve overall discrimination enough to raise accuracy. This finding reinforces the need


                                                                                                                                   /

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


to jointly optimize accuracy and false-alarm burden when selecting a single wearable channel. Together, these results argue
for patient-specific, data-driven channel selection rather than a priori focus-based selection. In practice, the “best” wearable
channel should be chosen using an objective criterion that incorporates both predictive accuracy and false-alarm rate, aligning
with the broader principle that personalization can reduce complexity while preserving performance27 .
    Despite its advantages, the model exhibits certain limitations, particularly in cases where preictal segments are not
consistently distinguishable. This highlights the necessity of further research to improve generalization across patients and
datasets by addressing signal variability and dataset heterogeneity. Enhancing the model’s robustness to inter-patient differences
will be key to improving reliability in broader clinical contexts. To avoid contaminating the interictal class with postictal
physiology that may persist for hours, we excluded intervals in which a new seizure began within 3 hours of the prior seizure
termination. This conservative choice may underrepresent seizure-cluster contexts, which are clinically high-value periods
where timely warnings could enable rescue interventions and help prevent further seizures within a cluster. Future work should
explicitly address clusters (e.g., include a postictal/cluster state), report stratified performance for clustered versus isolated
seizures, and evaluate sensitivity to different postictal exclusion windows.
    Both datasets used for model development and evaluation predominantly comprise focal-onset seizures. The SNUH cohort
includes only drug-resistant focal epilepsy cases, with seizure foci in the temporal, frontal, and occipital lobes. Therefore, our
results support single-/few-channel seizure prediction primarily in focal epilepsy cohorts; performance in idiopathic/genetic
generalized epilepsies was not evaluated and should not be inferred.
    In addition, power efficiency is a critical requirement for mobile platforms30 . Drawing on insights from energy-efficient
mobile systems?such as intermittent communication, adaptive display configurations, and hardware-level optimizations?can
further reduce power consumption without sacrificing performance 31 . These strategies will enable prolonged, real-world use of
seizure prediction models by extending battery life while maintaining system stability and responsiveness 32 .

5 Conclusion
                                                                                   S S
                                                                                 E
                                                                        PR
This study highlights the potential of single-channel EEG data for reliable seizure prediction, emphasizing the importance
of computational efficiency and real-time usability. By leveraging lightweight architecture and innovative post-processing
techniques, our method bridges the gap between laboratory accuracy and clinical practicality. Future research should focus on


                                                              IN
expanding datasets, developing patient-specific generalization strategies, and refining energy-efficient deployment methods.
These advancements will further establish single-channel EEG-based prediction as a feasible, patient-friendly solution for
epilepsy management.

                                         L E
                                      IC
                                    T
References

                                   R
1. Fisher RS, Acevedo C, Arzimanoglou A, et al. ILAE Official Report: A practical clinical definition of epilepsy. Epilepsia.

                                 A
  2014;55(4):475-482. doi:10.1111/epi.12550. Lancet Neurol. 2019;18(4):357–375.
2. Kwan P, Brodie MJ. Early Identification of Refractory Epilepsy. N Engl J Med. 2000;342(5):314-319.
3. Fisher RS, Boas WE, Blume W, Elger C, Genton P, Lee P, Engel J Jr. Epileptic seizures and epilepsy: Definitions
  proposed by the International League Against Epilepsy (ILAE) and the International Bureau for Epilepsy (IBE). Epilepsia.
  2005;46(4):470-472.
4. Kerr MP. The impact of epilepsy on patients’ lives. Acta Neurol Scand. 2012;126:1-9.
5. Kerr WT, McFarlane KN, Pucci GF. The present and future of seizure detection, prediction, and forecasting with machine
  learning, including the future impact on clinical trials. Front Neurol. 2024;15:1425490.
6. He C, Chen Y, Phang C, Stevenson C, Chen I, Jung T. Diversity and Suitability of the State-of-the-Art Wearable and Wireless
  EEG Systems Review. IEEE J Biomed Health Inform. 2023;27(8):3830-3843.
7. Yang X, Zhao J, Sun Q, Lu J, Ma X. An Effective Dual Self-Attention Residual Network for Seizure Prediction. IEEE Trans
  Neural Syst Rehabil Eng. 2021;29:1604-1613.
8. Shi S, Liu W. B2-ViT Net: Broad Vision Transformer Network With Broad Attention for Seizure Prediction. IEEE Trans
  Neural Syst Rehabil Eng. 2024;32:178-188.
9. Hussein R, Lee S, Ward R. Multi-Channel Vision Transformer for Epileptic Seizure Prediction. Biomedicines.
  2022;10(7):1551.
10. Daoud H, Bayoumi MA. Efficient Epileptic Seizure Prediction Based on Deep Learning. IEEE Trans Biomed Circuits Syst.
  2019;13(5):804-813.


                                                                                                                                 /

                                         ACCEPTED
                                           ARTICLE IN
                                                  MANUSCRIPT
                                                      PRESS


11. Frankel MA, Lehmkuhle MJ, Spitz MC, Newman BJ, Richards SV, Arain AM. Wearable reduced-channel EEG system for
  remote seizure monitoring. Front Neurol. 2021;12:728484.
12. McKenzie ED, et al. Validation of a smartphone-based EEG among people with epilepsy: A prospective study. Sci Rep.
  2017;7(1):45567.
13. Lu L, et al. A Seizure Prediction Method for Epilepsy Utilizing Lightweight Convolutional Neural Networks and Time-
  frequency Spectrograms of EEG Signals. 2024 IEEE BioCAS; Xi’an, China. 2024:1-5.
14. Chung YG, Cho A, Kim H, Kim KJ. Single-channel seizure detection with clinical confirmation of seizure locations using
  CHB-MIT dataset. Front Neurol. 2024;15:1389731.
15. Ren Z, Han X, Wang B. The performance evaluation of the state-of-the-art EEG-based seizure prediction models. Front
  Neurol. 2022;13:1016224.
16. Ohira J, Yoshimura H, Morimoto T, Ariyoshi K, Kohara N. Factors associated with the duration of the postictal state after a
  generalized convulsion. Seizure. 2019;65:101-105. doi:10.1016/j.seizure.2019.01.001.
17. Yang H, et al. An end-to-end seizure prediction approach using long short-term memory network. Front Neurosci.
  2023;15:733473.
18. Smith RG, et al. Pro-Ictal State in Human Temporal Lobe Epilepsy. NEJM Evidence. 2022;1(3).
19. Leal A, et al. Unsupervised EEG preictal interval identification in patients with drug-resistant epilepsy. Sci Rep.
  2023;13:784.
20. Lee DH, Kim BH, Kim TJ, Joe IW, Chong JW, Min KY, Jung KY. A ResNet-LSTM hybrid model for predicting epileptic

                                                                                   S
  seizures using a pretrained model with supervised contrastive learning. Sci Rep. 2024;14(1):1319.

                                                                                 S
                                                                               E
21. Peng P, Song Y, Yang L, Wei H. Seizure Prediction in EEG Signals Using STFT and Domain Adaptation. Front Neurosci.


                                                                       PR
  2022;15:825434.
22. Howard AG, Zhu M, Chen B, et al. MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications.


                                                             IN
  2017. Available from: http://arxiv.org/abs/1704.04861.
23. Truong ND, Nguyen AD, Kuhlmann L, Bonyadi MR, Yang J, Ippolito S, Kavehei O. Convolutional neural networks for

                                          E
  seizure prediction using intracranial and scalp electroencephalogram. Neural Netw. 2018;105:104-111.


                                      C L
24. Meisel C, Bailey KA. Identifying signal-dependent information about the preictal state: A comparison across ECoG, EEG

                                     I
  and EKG using deep learning. eBioMedicine. 2019;45:422-431. doi:10.1016/j.ebiom.2019.07.001.


                                  RT
25. Peng G, Nourani M, Harvey J, Dave H. Personalized EEG Feature Selection for Low-Complexity Seizure Monitoring. Int J


                                A
  Neur Syst. 2021;31(08):2150018. doi:10.1142/S0129065721500180
26. Wang Z, Yang J, Wu H, Zhu J, Sawan M. Power efficient refined seizure prediction algorithm based on an enhanced
  benchmarking. Sci Rep. 2021;11(1):23498.
27. Teixeira C, Direito B, Bandarabadi M, Dourado A. Output regularization of SVM seizure predictors: Kalman Filter versus
  the “Firing Power” method. IEEE Eng Med Biol Soc Conf. 2012:6530-6533.
28. Hadady L, Robinson T, Bruno E, Richardson MP, Beniczky S. Users’ perspectives and preferences on using wearables in
  epilepsy: A critical review. Epilepsia. 2025;66 Suppl 3(Suppl 3):4-13. doi:10.1111/epi.18280
29. Qiu S, Wang W, Jiao H. LightSeizureNet: A Lightweight Deep Learning Model for Real-Time Epileptic Seizure Detection.
  IEEE J Biomed Health Inform. 2023;27(4):1845-1856.
30. Ghaempour M, Hassanli K, Abiri E. An approach to detect and predict epileptic seizures with high accuracy using
  convolutional neural networks and single-lead-ECG signal. Biomed Phys Eng Express. 2024 Feb 29;10(2). doi: 10.1088/2057-
 1976/ad29a3.
31. Zhang L, Tiwana B, Qian Z, Wang Z, Dick RP, Mao ZM, Yang L. Accurate online power estimation and automatic battery
  behavior based power model generation for smartphones. IEEE/ACM/IFIP Int Conf Hard Soft Codesign Syst Synthesis
 (CODES+ISSS). 2010;:105-114.
32. Yoon C, Lee S, Choi Y, Ha R, Cha H. Accurate power modeling of modern mobile application processors. J Syst Archit.
  2017;81:17-31.
33. Rattagan E, Chu ETH, Lin YD, Lai YC. SEMI: Semi-Online Power Estimates for Smartphone Hardware Components.
  IEEE Trans Sustain Comput. 2016;1(2):54-62.


                                                                                                                              /

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


Funding
This work was supported by the Ministry of Health and Welfare of Korea (MOHW) through the Korea Health Industry
Development Institute (KHIDI) (Grant No. RS-2023-00266765).

Acknowledgements
This work was supported by the Korea Health Industry Development Institute (KHIDI) grant funded by the Korea government
(MOHW) (No. RS-2023-00266765).

Author Contributions
D.J. conceived and implemented the seizure prediction model, performed EEG preprocessing, training, evaluation, and led
the manuscript writing. K.-Y.J. contributed to manuscript writing, supervised the overall clinical component, and provided
clinical interpretation. Y.-G.J. organized and curated the EEG datasets. T.-J.K. provided clinical insights and assisted in medical
interpretation. S.K.L. reviewed the clinical validity and approved the final version of the manuscript. K.-Y.M. contributed to
manuscript revision and writing, led the system design and technical direction, and supervised the project from the engineering
side. All authors reviewed and approved the final manuscript.

Ethics declarations
This study was approved by the Institutional Review Board of Seoul National University Hospital (IRB No. H-2411-051-1585).
All procedures were conducted in accordance with relevant guidelines and regulations, including the Declaration of Helsinki

                                                                                     S
and the Bioethics and Safety Act. Informed consent was obtained from all participants or their legal guardians.

                                                                                   S
                                                                                 E
                                                                         PR
Data availability
The CHB-MIT dataset is publicly accessible on PhysioNet. The SNUH EEG dataset is classified as protected clinical data and


                                                               IN
cannot be shared publicly. External transfer is permitted only with prior IRB approval and institutional authorization, and may
be provided upon reasonable request to the corresponding author.

Competing interests
                                         L E
                                      IC
The authors declare no competing interests.

Supplementary information
                                   RT
                                 A
Supplementary tables are provided in the supplementary file.


                                                                                                                                  /

                                       ACCEPTED
                                         ARTICLE IN
                                                MANUSCRIPT
                                                    PRESS


Figure 1. Representative segment-based accuracy changes as a function of varying N values in the firing power
function for both the SNUH and CHB-MIT datasets. Larger N values result in smoother firing power curves, while smaller N
values make the model more sensitive to short-term variations in preictal features.


                                                                            S S
                                                                          E
                                                                   PR
                                                          IN
                                      L E
                                   IC
                                RT
                              A


                                                                                                                       /

                                          ACCEPTED
                                            ARTICLE IN
                                                   MANUSCRIPT
                                                       PRESS


    (a)


    (b)


    (c)


                                                                                   S S
                                                                                 E
    (d)
                                                                         PR
                                                               IN
                                         L E
                                      IC
    (e)

                                   RT
                                 A
    (f)


Figure 2. Representative seizure prediction patterns using the proposed model. Sky-blue regions indicate windows
classified as preictal. (a) Consistent detection across the entire predictive window, with stable preictal characteristics observed
consistently. (b) Detection beginning 20 minutes before seizure onset, with predictive features becoming apparent at this
interval. (c) Detection occurring only when the seizure is imminent, shortly before onset. (d) Predictive characteristics appear
consistently but disappear just before seizure onset. (e) Predictive features occur intermittently or in bursts within short
intervals, without sustained detection. (f) Patterns characterized by transient or unstable prediction signals, showing less
consistent preictal characteristics. Sky blue indicates individual window identified as the preictal state by our model.


                                                                                                                                  /

                                                  ACCEPTED
                                                    ARTICLE IN
                                                           MANUSCRIPT
                                                               PRESS


                            Table 1. Segment-based evaluation in SNUH dataset with k = 60, n = 119

                                          Fp1                 Fp2                  T3                   T4                   O1                   O2
  Patient No.    Seizure focus
                                    ACC         FPR     ACC         FPR    ACC          FPR     ACC          FPR     ACC          FPR     ACC          FPR

       1             R TLE          100.0     0.000    100.0     0.000     97.29        0.000   94.69        0.000   96.25        0.000   95.52        0.000
       2             R TLE          100.0     0.000    100.0     0.000     100.0        0.000   100.0        0.000   100.0        0.000   100.0        0.000
       3             B TLE          89.00     0.167    89.06     0.167     91.67        0.167   90.07        0.167   84.44        0.097   89.10        0.000
       4             L TLE          89.00     0.221    78.44     0.431     100.0        0.000   100.0        0.000   100.0        0.000   100.0        0.000
       5             L TLE          93.65     0.000    79.17     0.107     87.03        0.114   69.64        0.570   65.57        0.590   50.10        0.250
       6             B TLE          83.91     0.116    87.50     0.000     81.77        0.150   72.40        0.264   69.48        0.000   72.92        0.074
       7             L TLE          75.00     0.500    100.0     0.000     50.00        0.000   75.00        0.500   75.00        0.500   74.48        0.000
       8             L TLE          94.27     0.000    100.0     0.000     100.0        0.000   100.0        0.000   88.96        0.000   100.0        0.000
       9             R TLE          100.0     0.000    77.85     0.000     92.92        0.094   96.32        0.000   91.32        0.000   95.76        0.000
      10             R OLE          80.07     0.301    79.10     0.301     76.81        0.169   58.96        0.238   78.96        0.000   65.76        0.668
      11             R FLE          51.04     0.979    50.31     0.994     61.35        0.273   44.38        0.160   63.44        0.000   77.60        0.448
      12             L TLE          100.0     0.000    99.79     0.000     83.12        0.338   85.21        0.000   61.88        0.763   67.40        0.652
      13             L FLE          100.0     0.000    83.44     0.000     100.0        0.000   75.00        0.000   100.0        0.000   100.0        0.000


                                                                                                    S
      14             L TLE          69.27     0.000    98.85     0.000     85.94        0.000   72.08        0.000   75.94        0.000   75.00        0.500
      15             L TLE          100.0     0.000    98.96     0.000     89.86        0.000

                                                                                                E S
                                                                                                100.0        0.000   94.51        0.000   98.68        0.024


                                                                                        PR
      16             R TLE          75.00     0.000    73.02     0.000     67.08        0.015   77.81        0.000   75.00        0.500   90.94        0.160
      17             R TLE          89.79     0.204    89.03     0.219     70.28        0.000   91.88        0.163   99.72        0.006   88.82        0.224


                                                                          IN
      18             L TLE          86.35     0.000    99.90     0.000     78.33        0.000   77.29        0.000   82.71        0.000   81.35        0.000
      19             L OLE          74.58     0.081    72.60     0.000     76.46        0.075   73.23        0.000   82.81        0.344   71.15        0.002


                                                 E
      20             R FLE          78.54     0.000    78.23     0.000     75.10        0.000   76.15        0.000   87.40        0.252   86.56        0.269
      21             R TLE          76.28

                                             C L
                                              0.151    82.53     0.142     69.58        0.382   78.30        0.138   63.65        0.212   79.51        0.195
      22             L TLE          74.48

                                          T I 0.500    94.06     0.119     83.33        0.000   75.00        0.000   81.98        0.360   94.17        0.117


                                         R
      23             R TLE          84.17     0.000    65.52     0.500     71.25        0.031   58.96        0.231   65.21        0.000   70.42        0.310

     AVG                –
                                       A
                                    85.41     0.140    85.97     0.130     82.14        0.079   80.10        0.106   81.92        0.158   83.71

Abbreviations: ACC, Accuracy; FPR, False Positive Rate; AVG, Average. R, right; L, left; FLE, frontal lobe. epilepsy; TLE, temporal lobe epilepsy; OLE,
occipital lobe epilepsy
                                                                                                                                                       0.169


                                            Table 2. Segment-based performance by brain region

                                                        SNUH                                                                  CHB-MIT
 Region                                 ACC                                FPR                                  ACC                                    FPR

 Frontal                               85.78                              0.134                                 86.94                                  0.121
Temporal                               81.37                              0.120                                 80.89                                  0.164
Occipital                              81.55                              0.163                                 84.65                                  0.105
   Left                                82.82                              0.135                                 86.63                                  0.097
  Right                                82.98                              0.143                                 81.69                                  0.165
Abbreviations: ACC, Accuracy; FPR, False Positive Rate.


                                                                                                                                                               /

                                            ACCEPTED
                                              ARTICLE IN
                                                     MANUSCRIPT
                                                         PRESS


                                        Table 3. Event-based sensitivity in SNUH dataset

Patient No.                    Fp1             Fp2               T3               T4        O1      O2

     1                         100.0          100.0             100.0            100.0     100.0   100.0
     2                         100.0          100.0             100.0            100.0     100.0   100.0
     3                         100.0          100.0             100.0            100.0     83.33   83.33
     4                         100.0          100.0             100.0            100.0     100.0   100.0
     5                         100.0          75.00             100.0            100.0     100.0   50.00
     6                         100.0          75.00             100.0            75.00     50.00   75.00
     7                         100.0          100.0             0.000            100.0     100.0   50.00
     8                         100.0          100.0             100.0            100.0     100.0   100.0
     9                         100.0          100.0             100.0            100.0     100.0   100.0
     10                        100.0          100.0             100.0            66.67     66.67   100.0
     11                        100.0          100.0             50.00            50.00     50.00   100.0
     12                        100.0          100.0             100.0            100.0     100.0   100.0


                                                                                 SS
     13                        100.0          100.0             100.0            50.00     100.0   100.0
     14                        50.00          100.0             100.0            50.00     100.0   100.0


                                                                          RE
     15                        100.0          100.0             100.0            100.0     100.0   100.0


                                                                        P
     16                        50.00          50.00             50.00            100.0     100.0   100.0


                                                              IN
     17                        100.0          100.0             66.67            100.0     100.0   100.0
     18                        100.0          100.0             100.0            100.0     100.0   100.0


                                                      LE
     19                        100.0          100.0             100.0            100.0     100.0   50.00
     20                        100.0

                                            IC100.0             100.0            100.0     100.0   100.0
     21                        83.33

                                         RT   83.33             83.33            83.33     66.67   83.33


                                       A
     22                        100.0          100.0             100.0            50.00     100.0   100.0
     23                        100.0          100.0             100.0            100.0     50.00   100.0

   AVG                         94.93          94.93             89.13            88.04     89.86   90.94
Abbreviations: AVG, Average.


                                                                                                         /

                                     ACCEPTED
                                       ARTICLE IN
                                              MANUSCRIPT
                                                  PRESS


Table 4. Performance metrics of the proposed model across different EEG channels. All values are presented as mean ±
standard deviation.


   Dataset      Channel        Accuracy          Precision          Recall          F1-score            FPR

                FP1–F7       0.902 ± 0.155    0.919 ± 0.189     0.903 ± 0.220    0.892 ± 0.191     0.099 ± 0.253
                FP2–F8       0.837 ± 0.196    0.845 ± 0.298     0.811 ± 0.332    0.793 ± 0.298     0.137 ± 0.310
                 T7–P7       0.843 ± 0.202    0.802 ± 0.353     0.791 ± 0.366    0.776 ± 0.344     0.105 ± 0.272
 CHB-MIT
                 T8–P8       0.775 ± 0.226    0.725 ± 0.371     0.771 ± 0.395    0.711 ± 0.362     0.220 ± 0.388
                 P7–O1       0.854 ± 0.203    0.831 ± 0.333     0.789 ± 0.375    0.780 ± 0.350     0.081 ± 0.233
                 P8–O2       0.838 ± 0.213    0.801 ± 0.344     0.804 ± 0.362    0.780 ± 0.340     0.127 ± 0.283

               Fp1-AVG       0.857 ± 0.182    0.868 ± 0.258     0.851 ± 0.268    0.837 ± 0.247     0.136 ± 0.302
               Fp2-AVG       0.858 ± 0.189    0.863 ± 0.279     0.844 ± 0.298    0.827 ± 0.275     0.128 ± 0.303
                T3-AVG       0.821 ± 0.187    0.834 ± 0.308     0.749 ± 0.367    0.745 ± 0.331     0.106 ± 0.235
   SNUH
                T4-AVG       0.805 ± 0.216    0.802 ± 0.340     0.741 ± 0.397    0.720 ± 0.369     0.131 ± 0.292


                                                                             SS
                O1-AVG       0.806 ± 0.193    0.779 ± 0.347     0.767 ± 0.347    0.748 ± 0.321     0.156 ± 0.311
                O2-AVG       0.826 ± 0.196    0.784 ± 0.326     0.815 ± 0.344    0.775 ± 0.327     0.163 ± 0.293


                                                                  R E
                                                                P
                                                        IN
                                     L E
                                  IC
                               RT
                             A


                                                                                                                   /
```
