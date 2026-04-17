---
citation_key: "KoutsouvelisEtAl2024"
paper_id: "paper_108"
title: "Preictal period optimization for deep learning-based epileptic seizure prediction"
authors: "Petros Koutsouvelis; Bartlomiej Chybowski; A. Gonzalez-Sulser; Shima Abdullateef; Javier Escudero"
year: 2024
doi: "10.1088/1741-2552/ad9ad0"
source: "publisher-pdf (doi: 10.1088/1741-2552/ad9ad0); arxiv (2407.14876)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2407.14876"
tier: 1
composite: 4.5
---

# Preictal period optimization for deep learning-based epileptic seizure prediction

**Citation:** `KoutsouvelisEtAl2024` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1088/1741-2552/ad9ad0](https://doi.org/10.1088/1741-2552/ad9ad0)
**Source PDF:** `full_pdf/Koutsouvelis2024.pdf`

## Abstract

Objective. Accurate seizure prediction could prove critical for improving patient safety and quality of life in drug-resistant epilepsy. While deep learning-based approaches have shown promising performance using scalp electroencephalogram (EEG) signals, the incomplete understanding and variability of the preictal state imposes challenges in identifying the optimal preictal period (OPP) for labeling the EEG segments. This study introduces novel measures to capture model behavior under different preictal definitions and proposes a data-centric deep learning methodology to identify the OPP. Approach. We trained a competent subject-specific CNN-Transformer model to detect preictal EEG segments using the open-access CHB-MIT dataset. To capture the temporal dynamics of the model’s predictions, we fitted a sigmoidal curve to the model outputs obtained from uninterrupted multi-hour EEG recordings prior to seizure onset. From this fitted curve, we derived key performance measures reflecting the timing of predictions, including classifier convergence, average error, output stability, and the transition between interictal and preictal states. These measures were then combined to compute the Continuous Input–Output Performance Ratio, a novel metric designed to comprehensively compare model behavior across different preictal definitions (60, 45, 30, and 15 min) and suggest the OPP for each patient. Main results. The CNN-Transformer model achieved state-of-the-art performance (area under the curve of 99.35% and F1-score of 97.46%) using minimally pre-processed EEG signals. The 60-minute preictal definition was associated with earlier seizure prediction, lower error in the preictal state, and reduced output fluctuations, leading to significantly higher CIOPR scores (p < 0.001). Conventional accuracy-related metrics (sensitivity, specificity, F1-score) were less sensitive to varying preictal definitions and often discordant with CIOPR findings. Cross- and intra-patient heterogenei

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Journal of Neural
Engineering


PAPER • OPEN ACCESS                                                                               You may also like
                                                                                                      - FusionXNet: enhancing EEG-based
Preictal period optimization for deep learning-                                                         seizure prediction with integrated
                                                                                                        convolutional and Transformer
based epileptic seizure prediction                                                                      architectures
                                                                                                        Wenqian Feng, Yanna Zhao, Hao Peng et
                                                                                                        al.
To cite this article: Petros Koutsouvelis et al 2024 J. Neural Eng. 21 066040                         - Anchoring temporal convolutional
                                                                                                        networks for epileptic seizure prediction
                                                                                                        Songhui Rao, Miaomiao Liu, Yin Huang et
                                                                                                        al.

                                                                                                      - Classification of Epileptic Seizures Using
View the article online for updates and enhancements.                                                   AI: A Comparative Study on EEG Data
                                                                                                        Farwa Suman, Ali Raza, Hafiz Zia Ur
                                                                                                        Rehman et al.


                              This content was downloaded from IP address 137.110.51.95 on 17/04/2026 at 02:31

                           J. Neural Eng. 21 (2024) 066040                                                             https://doi.org/10.1088/1741-2552/ad9ad0


                           Journal of Neural Engineering

                           PAPER

                           Preictal period optimization for deep learning-based epileptic
OPEN ACCESS
                           seizure prediction
RECEIVED
19 July 2024               Petros Koutsouvelis1, Bartlomiej Chybowski2,3,4, Alfredo Gonzalez-Sulser2,5,6, Shima Abdullateef 7
REVISED                    and Javier Escudero2,3,∗
6 November 2024
                             Department of Radiation Oncology (Maastro), GROW Research Institute for Oncology and Reproduction, Maastricht University
ACCEPTED FOR PUBLICATION
5 December 2024              Medical Centre+, Maastricht, The Netherlands
                             Muir Maxwell Epilepsy Centre, University of Edinburgh, Edinburgh, United Kingdom
PUBLISHED                  3
                             Institute for Imaging, Data and Communications, School of Engineering, University of Edinburgh, Edinburgh, United Kingdom
27 December 2024           4
                             Child Life and Health, CIR, Deanery of Clinical Sciences, School of Medicine, University of Edinburgh, Edinburgh, United Kingdom
                             Centre for Discovery Brain Sciences, University of Edinburgh, Edinburgh, United Kingdom
Original Content from      6
                             Simons Initiative for the Developing Brain, University of Edinburgh, Edinburgh, United Kingdom
this work may be used      7
                             Centre for Medical Informatics, Usher Institute, School of Medicine, University of Edinburgh, Edinburgh, United Kingdom
under the terms of the     ∗
Creative Commons             Author to whom any correspondence should be addressed.
Attribution 4.0 licence.
                           E-mail: Javier.Escudero@ed.ac.uk
Any further distribution
of this work must           Keywords: deep learning, CNN, transformer, seizure prediction, preictal, interictal, EEG
maintain attribution to
the author(s) and the title Supplementary material for this article is available online
of the work, journal
citation and DOI.

                           Abstract
                           Objective. Accurate seizure prediction could prove critical for improving patient safety and quality
                           of life in drug-resistant epilepsy. While deep learning-based approaches have shown promising
                           performance using scalp electroencephalogram (EEG) signals, the incomplete understanding and
                           variability of the preictal state imposes challenges in identifying the optimal preictal period (OPP)
                           for labeling the EEG segments. This study introduces novel measures to capture model behavior
                           under different preictal definitions and proposes a data-centric deep learning methodology to
                           identify the OPP. Approach. We trained a competent subject-specific CNN-Transformer model to
                           detect preictal EEG segments using the open-access CHB-MIT dataset. To capture the temporal
                           dynamics of the model’s predictions, we fitted a sigmoidal curve to the model outputs obtained
                           from uninterrupted multi-hour EEG recordings prior to seizure onset. From this fitted curve, we
                           derived key performance measures reflecting the timing of predictions, including classifier
                           convergence, average error, output stability, and the transition between interictal and preictal
                           states. These measures were then combined to compute the Continuous Input–Output
                           Performance Ratio, a novel metric designed to comprehensively compare model behavior across
                           different preictal definitions (60, 45, 30, and 15 min) and suggest the OPP for each patient. Main
                           results. The CNN-Transformer model achieved state-of-the-art performance (area under the curve
                           of 99.35% and F1-score of 97.46%) using minimally pre-processed EEG signals. The 60-minute
                           preictal definition was associated with earlier seizure prediction, lower error in the preictal state,
                           and reduced output fluctuations, leading to significantly higher CIOPR scores (p < 0.001).
                           Conventional accuracy-related metrics (sensitivity, specificity, F1-score) were less sensitive to
                           varying preictal definitions and often discordant with CIOPR findings. Cross- and intra-patient
                           heterogeneities in the prediction times were also observed, complicating the establishment of a
                           global preictal interval. Significance. The newly developed metrics demonstrate that varying the
                           preictal period significantly impacts the timing of predictions in ways not captured by conventional
                           accuracy-related metrics. Understanding this impact and the inter-seizure heterogeneities is
                           essential for developing intelligent systems tailored to individual patient needs and for underlining
                           practical limitations in detecting the preictal period in real-world clinical applications.


                           © 2024 The Author(s). Published by IOP Publishing Ltd

J. Neural Eng. 21 (2024) 066040                                                                     P Koutsouvelis et al


1. Introduction                                             model can improve the accuracy of a subject-specific
                                                            classifier from 94.1% to 99.7%. Similarly, ablation
Epilepsy stands as one of the most prevalent neur-          analysis in a cross-patient setting [13] showed that
ological conditions worldwide, impacting an estim-          adding CNN layers prior to a GRU classifier led to a
ated 65 million individuals. This disorder is defined       4% increase in accuracy, illustrating the superiority of
by recurrent epileptic seizures–unprovoked surges           hybrid models.
of electrical activity in the brain, leading to transi-         Attention mechanisms, especially within trans-
ent alterations in behavior or consciousness. Patients      former models, have improved the ability to learn
span diverse socio-demographic backgrounds, with a          data relationships irrespective of sequence dis-
lifetime prevalence rate of 3%. Notably, an approx-         tance, a significant limitation in traditional LSTM
imate of 30% of patients suffer from drug-resistant         applications [14, 15]. Integrating CNNs with trans-
epilepsy [1].                                               formers has led to the emergence of robust models
     An inherent risk factor contributing to mor-           that effectively predict seizures from both raw EEG
tality among epileptic patients is the unpredictable        [16–18], EEG connectivity maps [19], and frequency-
nature of seizure occurrences, leading to elevated          domain features [18, 20, 21]. Other studies have suc-
levels of uncertainty, anxiety, social stigma, distress,    cessfully combined LSTM layers with transformer
and potentially hazardous situations among patients         models and achieved state-of-the-art performance
[2]. These challenges not only diminish their quality       [22, 23], or employed alternative attention mech-
of life but also underscore the critical need for effect-   anisms, such as criss-cross-attention and channel
ive seizure management strategies.                          attention [24].
     Improvements in predicting epileptic seizures
would significantly reduce the burden of uncertainty        1.2. Determining the preictal period length
for patients, enabling them, along with caregivers and      Despite these technological advances, accurately
clinicians, to take preparatory actions, prevent injur-     identifying the optimal preictal period (OPP) [5]
ies, and perform timely interventions [3, 4]. Epileptic     for labeling EEG segments remains a formidable chal-
seizures could be predicted by identifying the preictal     lenge. This difficulty stems from the gradual nature of
state, a period preceding seizure onset (ictal state)       the transition into the preictal state and the significant
characterized by distinct morphological EEG differ-         intra- and inter-patient variability in ictogenesis [25,
ences from the interictal (normal) state. It can typic-     26]. Approaches to determining the OPP are typically
ally last from several minutes to a few hours, varying      categorized into pre-training and post-training. The
upon seizures and individuals [5].                          former involves defining the preictal length for each
                                                            seizure before model training through the analysis
1.1. Deep learning for epileptic seizure prediction         of EEG markers. Researchers in [5] defined the OPP
Deep learning algorithms have gained increasing             as the point at which the discriminability of spec-
popularity in epileptic seizure prediction owing to         tral features between the two classes was maximized,
their ability to learn complex features from data [4].      which on average occurred 44.3 min before the onset.
Convolutional neural networks (CNN) have demon-             Works [25, 26] have computed the preictal length
strated particular efficacy in automatically extracting     using unsupervised clustering methods from non-
underlying patterns of preictal activity from raw EEG       linear, univariate, multivariate, and connectivity EEG
signals [6], EEG wavelets [7], time-frequency data          measures. Preictal events were observed on average
matrices [8], and connectivity-based measures [9].          up to 47.6 ± 27.3 min before onset, with strong inta-
Recurrent neural networks (RNN), including gated            and inter-patient variabilities. As for the post-training
recurrent units (GRU), long short-term memory               approaches, the performance of models trained with
(LSTM), and bi-directional LSTM (BiLSTM), have              varying preictal lengths–usually ranging from 5 to
been successfully employed to capture temporal              120 min–is evaluated against predefined metrics,
dependencies in preictal EEG feature vectors [10, 11].      such as accuracy, sensitivity, specificity, and F1-
However, when applied to raw EEG input, RNNs                score, with the most successful model being selected
exhibit inferior performance compared to CNNs               [7, 8, 10, 27].
[12]. Various studies [6, 12, 13] have proposed hybrid           Although the aforementioned strategies have
models combining the advantages of both architec-           helped mitigate the uncertainty in defining the
tures with superior overall performance. While dir-         preictal period, they still exhibit considerable limita-
ect comparison of reported performances across dif-         tions. Pre-training approaches are constrained by the
ferent studies is not straightforward due to differ-        quality and relevance of the hand-crafted EEG mark-
ences in experimental setups, ablation studies within       ers, which may not accurately represent the under-
a given work can showcase performance improve-              lying dynamics of preictal activity. Often the extrac-
ments due to specific design choices. Authors in [6]        ted features appear indistinguishable among the two
demonstrated that adding a Bi-LSTM layer to a CNN           states, yielding no clear definition of the preictal


J. Neural Eng. 21 (2024) 066040                                                                   P Koutsouvelis et al


state start [5, 26]. Post-training methods, though less   2. Materials and methods
sophisticated, demonstrate greater resilience to our
incomplete understanding of preictal state dynam-         2.1. EEG data and participant selection
ics and align more directly with the targeted dia-        The proposed seizure prediction model was trained
gnostic task. Nonetheless, conventional metrics used      and evaluated on the CHB-MIT dataset [31]. It
for model comparison fail to provide a comprehens-        consists of scalp EEG recordings from 23 pediatric
ive assessment of system performance. Though indic-       patients at the Children’s Hospital Boston follow-
ative of the model’s ability to distinguish preictal      ing an anti-seizure medication withdrawal period of
from interictal segments, they capture neither the        seven days. Patients’ ages ranged from 1.5 to 22 years,
classifier’s behavior during the gradual transition to    with individual epilepsy types not being mentioned.
the preictal state nor the distribution of false pos-     There were 198 recorded seizures in total, for which
itives and negatives, which are critical for evaluat-     seizure start and end times were annotated by experts.
ing the model’s practical implementation. Few studies     Cases chb01 and chb21 came from the same sub-
[28–30] have employed continuous, long-term EEG           ject, with the latter being recorded 1.5 years later.
to visualize the system’s behavior, yet they still        Subject information for case chb24 was not provided.
rely on standard metrics without introducing novel        Electrodes were placed according to the international
measures.                                                 10–20 system with the number of channels for most
                                                          of the patients ranging from 23 to 26. The sampling
1.3. Contributions                                        rate was set to 256 Hz with 16-bit resolution.
Recognizing these gaps, this study introduces a novel         Data recorded up to 4 h before and 1 h after
methodology for evaluating epileptic seizure predic-      each annotated seizure were classified as interictal,
tion models. By training a high-performing classi-        to account for the uncertainty in the duration of
fier, we aim to provide a comprehensive assessment        preictal and postictal effects. The 4-h threshold is
that not only monitors the model’s behavior but           widely adopted in literature [6, 20, 22, 32, 33],
also facilitates the selection of the OPP. Therefore,     while the postictal threshold varies across studies.
the contributions of this work can be summarized          Literature has shown that the postictal state typic-
as:                                                       ally lasts up to 30 min [34], therefore we selected a
                                                          1 h threshold to ensure a sufficient number of train-
(1) We develop a CNN-transformer model to clas-           ing data for cases with more frequent seizures. Cases
    sify spatiotemporal EEG dynamics of preictal          chb08, chb12, chb13, chb15, and chb24 did not yield
    versus interictal EEG segments achieving high         interictal data meeting the defined criteria and were
    sensitivity and early prediction consistently         deemed ineligible and excluded from the study.
    across subjects. CNN-Transformer models have              The maximum duration for the preictal period
    been previously introduced but our architecture       was set to 60 min. Similarly to the interictal class, data
    achieves–to the best of our knowledge–the earli-      collected up to 1 h after seizure termination were not
    est prediction time reported in literature (76.8      considered preictal regardless of an incoming seizure.
    min before onset) while maintaining accuracy          Seizures yielding less than one minute of preictal data
    comparable to state-of-the-art studies.               were excluded as ineligible. Additionally, cases with
(2) We introduce an approach that allows nuance           fewer than two eligible seizures were also excluded,
    assessment of the deep learning model’s per-          since there should be at least one seizure for training
    formance by fitting a sigmoidal curve to the out-     and one for testing each subject-specific model. Cases
    put of the classifier subject to continuous, long     chb01 and chb21 were treated as separate subjects due
    EEG input.                                            to the long time difference between the recordings.
(3) We developed a novel Continuous Input–                In instances where electrode placement varied across
    Output Performance Ratio (CIOPR) metric               recordings, the configuration yielding the greatest
    that provides a comprehensive assessment of           amount of data was selected. A summary of all patient
    the performance of a seizure prediction system        data and eligible seizures, as well as their Patient ID,
    in a realistic implementation setting by combin-      Seizure ID, and file name, are detailed in the supple-
    ing measures of prediction time, output stabil-       mentary material tables 1 and 2, respectively.
    ity, and transition time between interictal and
    preictal states.                                      2.2. Pre-processing
(4) We demonstrate the impact of different preictal       Pre-processing of the EEG signals was kept min-
    state definitions in the system’s performance as      imal and was performed on the files meeting the eli-
    well as how the CIOPR metric can be utilized to       gibility criteria in section 2.1. Firstly, EEG was re-
    determine the OPP for each patient (OPP).             referenced to the common average, which has been


J. Neural Eng. 21 (2024) 066040                                                                    P Koutsouvelis et al


shown to improve the signal-to-noise ratio [35]. A         into a 90% training and 10% validation split, form-
0.5–45 Hz finite impulse response (FIR) non-causal         ing the training set. This process was repeated four
bandpass filter was automatically designed by the          times to ensure consistency across different shuffling
MNE Python package using a Hamming window and              and random weight initializations. Ultimately, this
order N = 1690. The high-pass cutoff at 0.5 Hz served      resulted in N × 4 × k × 4 training and testing sets,
to remove DC offset and low-frequency voltage drifts       where N represents the number of eligible subjects,
[36]. The 45 Hz low-pass cutoff was chosen to sup-         k denotes the number of eligible seizures per patient,
press power line interference without using notch fil-     and the four iterations correspond to the different
tering, which can cause significant signal distortions     preictal lengths (60, 45, 30, and 15 min), as well as
[37]. Additionally, recent studies suggest that inter-     the number of different runs.
ictal SEEG features below 45 Hz are sufficient for loc-
alizing the seizure onset zone [38]. This design choice    2.4. Deep learning model
aims to balance minimal noise contamination while          Following the accelerating emergence of transformer
retaining relevant gamma-band information, explor-         models in seizure-related applications, we decided
ing the hypothesis that a 45 Hz cutoff could also be       to employ a hybrid CNN-Transformer deep learn-
effective in scalp-EEG seizure prediction. Lastly, no      ing model for the classification of preictal and inter-
channels were removed, resulting in 23 channels for        ictal EEG segments. The model architecture is illus-
each eligible patient. Pre-processed data were then        trated in figure 1. The raw pre-processed EEG epochs
segmented into 5 s non-overlapping epochs.                 were first input to a three-layer CNN to extract rel-
                                                           evant spatiotemporal features. Each convolutional
2.3. Training methodology                                  layer, consisting of 32, 64, and 128 filters of size
Four different preictal period lengths – 60, 45, 30,       3 × 3, respectively, was followed by a Max-Pooling
and 15 min–were then extracted from each seizure           operation that reduced dimensionality by a factor of
to explore their effect on model performance and           two. The architecture also incorporated a Dropout
determine the OPP for each subject separately. These       layer with a probability of p = 0.1 before each Max-
intervals were selected to ensure an adequate number       Pooling step to mitigate overfitting, complemented
of seizures were available for training the subject-       by batch normalization and a rectified linear unit
specific deep learning models while maintaining a          (ReLU) activation function.
manageable number of comparisons.                              After the final convolutional layer, the output
     Data extraction was conducted as follows: for         tensor was reshaped into a two-dimensional matrix,
the 60 min duration, all available preictal data were      where rows corresponded to subsequent time points
extracted for each seizure, regardless of the actual       and columns to spatiotemporal features, including
duration available (e.g. some seizures had only 20 min     positional information resulting from integrating the
of data available). For the 45 min duration, only seg-     channel and feature dimensions during the reshaping
ments from the 45 min immediately preceding the            process. To capture long-term temporal dependencies
seizure onset were included; if a seizure had 60 min of    among these features, a transformer architecture was
preictal data available, the first 15 min were excluded.   utilized, with two multi-head attention layers [14].
If, for example, only 20 min were available, none          The reshaped two-dimensional output was passed
were excluded. This procedure was similarly applied        through 3 linear layers per attention head to cre-
to the 30 min and 15 min durations. A histogram of         ate the query, key, and value matrices, respectively.
available preictal data per seizure (in minutes) can be    The linear layers shrunk the dimension of the feature
found in the supplementary material, figure 1.             vectors to 64, while the number of attention heads
     The models were trained and evaluated in a            was set to 8, following experimentation and literature
subject-specific manner. For each definition of            suggestions [39]. Each attention layer was followed by
preictal length, the extracted preictal segments from      a fully-connected (dense) layer of 64 neurons, ReLU
all seizures were concatenated without shuffling. To       activation and p = 0.3 dropout, to highlight the most
mitigate class imbalance, the minority class (preictal)    relevant features, while maintaining the dimensional-
data were oversampled by a factor of 3 through the         ity of the feature vectors.
introduction of a 66% overlap. Similarly, interictal           The resulting attention-weighted feature map was
segments were randomly selected from the pool of           then flattened and processed through a single-neuron
interictal data to match the number of the augmen-         output layer with sigmoid activation for the classi-
ted preictal data instances. The training and test-        fication stage. The output value was rounded to the
ing sets were created using the leave-one-seizure-         nearest integer (0: interictal; 1: preictal) without fur-
out cross-validation (LOOCV) method. Specifically,         ther post-processing. The model was trained using
preictal data of a different seizure each time were        the binary cross-entropy loss function [40], with
isolated, alongside an equal number of randomly            weight updates performed via the Adam optimiza-
selected interictal segments to form the testing set.      tion algorithm. The learning rate was set to l = 0.001,
The remaining samples were shuffled and divided            and the AMSGrad [41] extension was enabled. The


J. Neural Eng. 21 (2024) 066040                                                                                    P Koutsouvelis et al


   Figure 1. Architecture of the CNN-Transformer deep learning model. Inputs were of shape 1280 × 23, for 5 s 23-channel EEG
   segments. Dimensions T, C, and F correspond to time points, channels, and feature maps respectively. The shape of the data
   following each layer is displayed as T × C × F. For the transformer stage, C and F are aggregated into a single dimension and
   expressed as T × (C, F). Specific information on each layer can be found in the supplementary material, table 3.


training utilized a mini-batch size of 64 and was lim-               logistic curve is used, given by equation (1) [42],
ited to 100 epochs. To prevent overfitting, the early-               where parameters a, b, c, and d represent the vertical
stopping callback terminated training if the validation              and horizontal stretch, the point of inflection (Infl),
loss did not improve for 20 consecutive epochs. The                  and the vertical offset, respectively, as
model-checkpoint callback preserved the weights of
the training iteration that achieved the lowest valida-                                              a
                                                                                      f (x) =                + d.                  (1)
tion loss. The complete summary of the model can be                                             1 + e−b(x−c)
found in the supplementary material.
                                                                          Utilizing the fitted sigmoidal curve, we derive key
2.5. CIOPR                                                           performance measures. Specifically, the TP between
We introduce a novel metric that facilitates a dir-                  interictal and preictal states is quantified as the
ect comparison of classifier behaviors across predic-                time interval between the 5th and 95th percentile
tion tasks. Traditional accuracy metrics, which rely                 thresholds of the sigmoid curve’s amplitude. The neg-
heavily on class definitions, often fail to account for              ative duration (ND), the supposed interictal period,
prediction timing and performance during interictal-                 is calculated as the duration between the first output
preictal state transitions. To address these limita-                 prediction and the beginning of the TP. The remain-
tions, our innovative metric, CIOPR, offers a compre-                ing measures are directly computed from the out-
hensive evaluation of model behavior using uninter-                  put data, following average smoothing (1 output pre-
rupted, unlabeled long-term EEG data, allowing for                   diction every 8 min). The seizure prediction con-
objective comparisons independent of class labels. We                vergence (SPC) is the point in time where output
hypothesized that the ideal classifier would provide                 predictions reached 99% of the maximum value, in
early prediction, minimal errors, stable outputs, and                minutes before seizure onset. It represents the period
brief transition periods (TPs). Longer transitions can               of highest incoming-seizure probability by the model
lead to prolonged fluctuations and increased uncer-                  and could reflect the prediction horizon in a real-
tainty in predictions. Therefore, we assumed that                    istic implementation setting. Both output and max-
shorter transitions are crucial for improving reliab-                imum values used for the computation of SPC refer
ility in alarm-generating systems, especially in critical            to the mean of 3 consecutive predictions (3 × 8 min =
applications like seizure prediction.                                24 min). Figure 2 depicts the fitted sigmoid, the out-
     When subjected to continuous EEG data span-                     put predictions, and the aforementioned measures.
ning several hours before a seizure, an accurate classi-                  The average error during the SPC (SPCerr ) and
fier is anticipated to initially produce negative (inter-            ND (NDerr ) are calculated using equations (2)
ictal) predictions, transition through a mix of negat-               and (3), respectively. NSPC and NND refer to the num-
ive and positive predictions, and ultimately converge                ber of output predictions in each of the two regions.
to the preictal state. Consequently, to quantitatively               SPCerr and NDerr also serve as proxies for out-
model the timing of these predictions, we propose                    put fluctuations, which would cause their values to
to fit a sigmoidal curve to the classifier’s continuous              increase. Then, equation (4) is developed to combine
output, which has undergone smoothing with an 8                      all the measures so that the classifier with the longest
min averaging window. In particular, a 4-parameter                   SPC, minimum SPCerr and NDerr , and shortest TP


J. Neural Eng. 21 (2024) 066040                                                                                          P Koutsouvelis et al


   Figure 2. Continuous output predictions based on 600 min of EEG data preceding seizure onset, along with the fitted sigmoidal
   curve. The black dotted vertical lines, derived from the sigmoid fit, denote the start and end points of the TP between interictal
   and preictal states. The red dotted line, directly calculated from the output, designates the start of the SPC, where the classifier’s
   output converges. Notations: ND = negative duration (interictal predictions), TP = transition period, and SPC = seizure
   prediction convergence.


achieved the highest score. SPCeff and NDeff repres-                    durations. This normalization facilitates a relative
ent the effective values of SPC and ND taking into                      performance evaluation, where the highest-scoring
account the average errors, and defined as SPCeff =                     model is assigned a CIOPR score of 1, thus enabling a
SPC(1 − SPCerr ) and NDeff = ND(1 − NDerr )                             comparative analysis of the impact of varying preictal
                                                                        period lengths. Detailed expressions for Inflcomp and
                                1 ∑
                                  NSPC
                                                                        η, as well as elucidation of the underlying intuition
                 SPCerr =                   |1 − yi |            (2)
                             NSPC                                       for CIOPR, are detailed in the supplementary mater-
                                     i =1
                                                                        ial, section 3

                                 1 ∑ND N
                                                                                             CIOPRk
                    NDerr =            |yi |                     (3)         CIOPRk =                , k ∈ {60, 45, 30, 15} .               (5)
                                NND                                                         CIOPCmax
                                       i =1


                         (                )                                 Lastly, the Pearson correlation coefficient, ρ is cal-
       CIOPC = SPCeff + η NDeff + Inflcomp .                     (4)    culated between the output predictions and the fit-
                                                                        ted curve to assess the method’s reliability. It also
    Overall, equation (4) computes the Continuous
                                                                        serves as an indicator of output stability, since greater
Input–Output Performance Coefficient (CIOPC) of
                                                                        fluctuations are expected to decrease the correlation
a model by taking into account two terms. The
                                                                        coefficient.
SPCeff term rewards the model for early prediction
(SPC), high accuracy, and output stability (SPCerr ).
Similarly, the second term, NDeff , rewards the model                   2.6. Additional metrics
for high accuracy and stability (NDerr ), as well as                    Beyond the CIOPR performance metrics including
short TP (longer ND when TP is short). A reduction                      segment-wise sensitivity, specificity, accuracy, and
in ND due to earlier prediction should not get penal-                   F1-score were employed for performance evaluation.
ized and is compensated by the Inflcomp term (NDeff                     These metrics–referred to hereafter as conventional
lost due to an earlier Infl). The scaling factor η ensures              metrics due to their widespread use in classification
that the second term will not have a greater weighting                  tasks–were computed on the test set, the formulation
than SPCeff due to hours-long interictal EEG; hence,                    of which is detailed in section 2.3. Given the equal
maintaining the focus on early and accurate seizure                     representation of classes in the test set, the resulting
prediction.                                                             accuracy is equivalent to the balanced accuracy (BA).
    The CIOPC value for each preictal state defin-
ition is normalized to the CIOPR metric using                           2.7. Testing setup
equation (5), where CIOPCmax denotes the max-                           All parameters in the chosen CNN-Transformer
imal CIOPC obtained across the examined preictal                        architecture, including the decision boundary of


J. Neural Eng. 21 (2024) 066040                                                                     P Koutsouvelis et al


p = 0.5 were kept identical across all patients and test-   3. Results
ing seizures. For each eligible seizure of a qualify-
ing participant (criteria detailed in section 2.1), the     3.1. Classifier training
prediction performance was tested using the conven-         The models were trained using an A100 Tensor Core
tional metrics, for all preictal durations. Seizures with   GPU in Google Colab. The average training dura-
over 2.5 h of uninterrupted continuous EEG data             tion was 8.1 min per model, converging at epoch
were further subjected to CIOPR evaluation for each         54 due to the early-stopping callback. The train-
preictal interval. A maximum of 10 h of continuous          ing duration was notably longer for 60- and 45
EEG was utilized for CIOPR to reduce computation            min preictal class definitions due to increased data
time and maintain consistency across patients.              volume. The convergence minima for both validation
    Metrics were then aggregated across seizures to         and training curves varied more across patients than
compute the average performance for each preictal           across intra-patient seizures or different preictal state
duration. For conventional metrics, averages were           lengths.
calculated on a segment-wise basis rather than
seizure-wise, ensuring that testing seizures with more      3.2. Preictal-interictal classification
data samples were accorded greater weight. These            The proposed architecture demonstrated consistent
averages were then used to determine the OPP. Table 1       performance across multiple subjects with particu-
of the supplementary material provides a summary            larly high sensitivity (> 99%) for all preictal defin-
of the recorded seizures per subject, including both        itions. Figure 3 compares the distributions of the
the count of eligible seizures and those applicable for     achieved sensitivity, specificity, and F1-score across
CIOPR testing.                                              all subjects for each definition of the preictal class.
                                                            The exact values for each patient are detailed in sup-
2.8. OPP selection                                          plementary material, section 4.
A general OPP – 60, 45, 30, or 15 min–was then selec-            Models trained with a 30 min preictal definition
ted for each participant. When at least one seizure was     demonstrated the highest sensitivity with an aver-
eligible for CIOPR testing, the OPP was assigned to         age of 99.49%. However, varying the preictal window
the preictal definition yielding the highest CIOPR val-     had minimal impact on sensitivity, which was con-
ues, averaged across those seizures. Conversely, if no      firmed by the statistical analysis that showed no signi-
CIOPR results were available, the OPP was assigned          ficant differences across different preictal definitions
to the preictal definition attaining the highest F1-        (null hypothesis accepted, p = 0.161). On the con-
score, averaged across all testing seizures. F1-score is    trary, the analysis showed a more pronounced impact
preferred over BA due to its capability to emphas-          on model specificity, with the null hypothesis being
ize minimizing false negatives, which are considered        rejected for the 60-to-15 (p = 0.001) and 45-to-15
more detrimental in epileptic seizure prediction [4].       min (p = 0.034) preictal length comparisons. Overall,
Lastly, the model trained using the OPP was selec-          specificity improved with longer preictal intervals and
ted from each patient to evaluate both the subject-         peaked at 95.03%, which was considerably lower than
specific and aggregate performance of our proposed          sensitivity at the 0.5 decision threshold.
methodology. To further showcase performance, the                Furthermore, the 60 min preictal window gener-
false alarm rate (FAR) (h−1 ) and the area under the        ally yielded the highest average F1-score (97.28%),
receiver operating characteristic (ROC) curve (AUC)         although 45- and 30 min definitions performed bet-
were reported only for the selected models. FAR was         ter in certain individuals. Statistical analysis showed
computed based on the EPOCH [43] method on the              significant impact on F1-score only for the 60-to-
5 s segment level.                                          15 min comparison (p = 0.003). Overall, the per-
                                                            centage changes in F1-score across different preictal
2.9. Statistical analysis                                   intervals were relatively modest, with a maximum
To explore statistical differences in model beha-           variation of 3.2% observed in case chb05. Given the
vior attributed to different preictal definitions, a        minimal impact on sensitivity, fluctuations in F1-
related-samples Friedman’s two-way ANOVA with               score were primarily attributable to reductions in spe-
Bonferroni correction for multiple comparisons was          cificity associated with the shorter preictal intervals.
conducted for all the metrics used in the test-                  Some cases in our study had much lower perform-
ing setup (sensitivity, specificity, accuracy, F1-score,    ance compared to others. For instance, case chb06
SPC, SPCerr , NDerr , Infl, TP, ρ, CIOPR). The null         exhibited a sensitivity of 94.76%, and a specificity
hypothesis tested was that the distributions of scores      of 73.54%, > 20% below the average. Cases chb14
for each metric across the preictal lengths of 60, 45,      and chb22 also showed notably low specificity scores.
30, and 15 min do not differ significantly (significance    Section 4.1 compares the findings with the results
level α = 0.05 after correction).                           reported in the literature.


J. Neural Eng. 21 (2024) 066040                                                                                          P Koutsouvelis et al


   Figure 3. Sensitivity, specificity, and F1-score distributions across the 19 eligible subjects of the CHB-MIT dataset for the 60, 45,
   30, and 15 min preictal definitions. Significant differences (p ⩽ 0.05) were observed across the varying preictal intervals in the
   following metrics: Specificity (60-to-15, 45-to-15), F1-score (60-to-15).


   Figure 4. Four figures showing different levels of fitting between the classifier’s output and the fitted sigmoid curve, sorted with
   decreasing Pearson correlation coefficient (ρ). The horizontal axis represents minutes before seizure onset (seizure onset at utmost
   right), and the vertical axis is the classification output. Captions show the case number, seizure ID, preictal class definition, and ρ.


3.3. Fitting the sigmoidal curve to the classifiers’                    the ρ values for the 60-to-15 (p = 0.005) and 45-to-
output                                                                  15 min (p = 0.005) comparisons.
The proposed CIOPR test in section 2.5 was per-                              Figure 4 demonstrates four fitting examples to
formed on the thirteen patients that met the criteria                   allow visualization of different correlation coef-
described in section 2.7. The first step of the analysis                ficients and corresponding model behavior. Sub-
involved fitting the sigmoidal curve to the smoothed                    figures 4(a) and (b) display high correlation coeffi-
output of the classifiers. The Pearson correlation coef-                cients (ρ > 0.95). Sub-figure 4(c) depicts a fitting with
ficient between the model output and the fitted curve                   ρ ≈ 0.9, enabling reliable identification of both the
across all the tested patients was on average ρ > 0.9                   prediction horizon and the TP. Conversely, sub-figure
for the 60, 45, and 30 min preictal definitions, and                    4(d) shows one of the fittings with the lowest correla-
ρ = 0.876 for the 15 min one. The high correlation                      tion (ρ < 0.75). While the TP and interictal state were
values show the effectiveness of the chosen curve in                    less discernible, a noticeable shift in the density of
modeling the classifiers’ output profile and indic-                     positive predictions still enabled the identification of
ate that the models generally exhibited the intended                    the predicted preictal state start and subsequent per-
behavior. Similar to the F1-score results, the correla-                 formance quantification. Seizure 2 of case chb05 was
tion coefficients differed across patients, seizures and                the only instance in which the curve could not be fit-
preictal state lengths, with 60 min usually leading to                  ted and was therefore excluded from the analysis. The
higher values. Statistical analysis showed that increas-                output plots for this case can be found in supplement-
ing the preictal length led to significant increases in                 ary material, section 5.


J. Neural Eng. 21 (2024) 066040                                                                                        P Koutsouvelis et al


   Figure 5. SPC, SPCerr , NDerr , Infl, TP, and CIOPR distributions across the 13 eligible subjects of the CHB-MIT dataset for the 60,
   45, 30, and 15 minpreictal definitions. Significant differences (p ⩽ 0.05) were observed across the varying preictal intervals in the
   following metrics: SPC (60-to-30, 60-to-15, 45-to-30, 45-to-15), SPCerr (60-to-45, 60-to-30, 60-to-15), Infl (60-to-30, 60-to-15),
   CIOPR (60-to-30, 60-to-15, 45-to-30, 45-to-15). Notations: SPC = seizure prediction convergence, SPCerr = average error during
   the SPC, NDerr = average error between the start of the signal and TP, TP = transition period, Infl = point of inflection, and
   CIOPR = continuous input–output performance ratio.


    The ρ values were generally reduced with                           analysis showed that varying preictal definitions had
decreasing preictal length, primarily due to the                       a significant impact on prediction time, particularly
increased volume of ‘unseen’ data from the classi-                     for the 60-to-30, 60-to-45, 45-to-30, and 45-to-15
fiers. Since the interictal data were taken up to 4 h                  min comparisons. The average error during the SPC
before seizure onset irrespective of the preictal win-                 (SPCerr ) appeared to be also significantly impacted
dow, shorter preictal lengths led to an increased                      by varying preictal windows, with the lowest value
volume of in-between-data that the model had                           observed at the 60 min one. On the other hand, NDerr
not been exposed to during the training pro-                           was on average increased for longer preictal intervals.
cess. This led to prolonged output fluctuations                        However, this increase was driven by only a few test
that reduced ρ, as the output diverged from the                        seizures with high NDerr values for all intervals, there-
‘ideal’ smooth transition of the sigmoidal curve. A                    fore results for this metric were not deemed statistic-
detailed list of average correlation coefficients for all              ally significant.
cases can be found in the supplementary material,                          The TP and Infl metrics quantified the timing
section 6.                                                             of the predictions; i.e. the transition from the inter-
                                                                       ictal to the preictal state. Infl occurred earlier when
3.4. CIOPR testing results                                             longer preictal intervals, averaging 143.1 min before
The fitted curves allowed the computation of the                       onset for the 60 min interval. This translates to
SPC, SPCerr , NDerr , Infl, TP, and CIOPR metrics, as                  a tendency to generate positive predictions farther
explained in section 2.5. Figure 5 compares the distri-                from the seizure onset, with the 60-to-15 and 60-
bution of the aforementioned metrics across all eli-                   to-30 min comparisons showing statistically signific-
gible test patients for each preictal definition. The                  ant differences. Interestingly, the transition between
exact values of all metrics used to compute the CIOPR                  the two states appeared sharper for the 60, and 45
scores are displayed in the supplementary material,                    min preictal lengths, with the latter achieving the
section 6.                                                             lowest average TP of 56 min. However, no statist-
    Longer preictal definitions led to earlier conver-                 ical significance on the TP values (null hypothesis
gence of the classifier output (SPC), which trans-                     accepted with p = 0.135) across the different preictal
lates to earlier prediction of incoming seizures. The                  intervals.
average convergence point for the 60 min interval                          The CIOPR values improved with increasing
occurred at 73.0 min before the onset, while val-                      preictal class definitions, with the 60 min preictal
ues ranged overall from 217.6 to 16.7 min. Statistical                 window showing the best performance. This was


J. Neural Eng. 21 (2024) 066040                                                                                        P Koutsouvelis et al


   Figure 6. Output profiles of four patient-specific classifiers for case chb02 with 60, 45, 30, and 15 min preictal class definitions
   respectively. Input is 5.8 h of continuous EEG recordings before the onset of seizure #1 of chb02. The red dotted line shows the
   SPC, and the black lines show the TP boundaries. The horizontal axis represents minutes before seizure onset (seizure onset at
   utmost right), and the vertical axis is the classification output. Sub-captions show the preictal class definition, CIOPR value, and
   F1-score achieved. Notations: SPC = seizure prediction convergence, TP = transition period, CIOPR = Continuous
   Input–Output Performance Ratio.


confirmed by statistical analysis, where CIOPR was                     the statistical analysis, where the CIOPR distributions
significantly higher with the 60 min definition com-                   varied significantly across 4 preictal length comparis-
pared to the 30 (p < 0.001) and 15 min ones                            ons, compared to only 1 for the F1-score, and visual
(p < 0.001). Similar to the F1-score results, few indi-                inspection of results. Cases chb02, chb07, chb14, and
viduals showed better CIOPR performance with a                         chb16 all presented differences ⩾10% between the
45 min preictal definition (chb01, chb04, chb22). The                  best and second-best performing models based on the
CIOPR scores of the 45 min definition were also                        CIOPR metric.
significantly higher than the 30 (p = 0.003) and 15                         The results can be categorized into two types: a)
min (p < 0.001) ones. Detailed p-values across all the                 concordant, where the same preictal length yielded
hypothesis tests performed can be found in the sup-                    the highest performance in both metrics and b) dis-
plementary material, table 8.                                          cordant, where CIOPR and F1-score values suggested
     Overall, the CIOPR results were aligned with the                  a different OPP8 . A detailed comparison between the
SPC trends, due to the design of the metric to pos-                    F1-scores and CIOPR can be found in supplementary
itively reward early and consistent predictions. Cases                 material, table 6.
chb01 and chb22 were the only exceptions, where                             Figure 6 depicts the output curves for case chb02
they achieved the highest CIOPR values at a 45 min                     alongside the fitted sigmoidal curve. The CIOPR dis-
preictal window while having a maximum SPC at                          crepancies can be attributed to the visually iden-
the 60 min one. This can be attributed to the integ-                   tifiable changes in the model’s behavior, such as
rative nature of the proposed metric, which aims at                    greater prediction horizon, shorter transition time,
balancing minimized error, reduced transition time,                    and reduced error. In this case, the results between
and early prediction time. Interpretation of the find-                 the two metrics were concordant; increasing preictal
ings and importance in terms of intended behavior                      class definition led to improved CIOPR and higher
in real-time implementation settings is discussed in                   F1-score.
section 4.3.                                                                On the other hand, cases chb06, chb07, and
                                                                       chb14 demonstrated similar CIOPR variations
3.5. Comparison between CIOPR and F1-score
metrics
Comparison with the F1-score results indicates that                    8 For case chb21, the LOOCV approach (see section 2.3) resulted in

CIOPR was considerably more sensitive to varying                       training seizures with less than 45 min of preictal data when testing
                                                                       for the only eligible seizure (Seizure ID: 1) for CIOPR evaluation.
preictal lengths, showing an average change of 9.2%
                                                                       Consequently, the results for the 60 and 45 min preictal periods
per 15 min decrease, compared to a 0.3% average                        were identical and the 45 min length was chosen since it provided
change for the F1-score. This was also confirmed by                    a more accurate representation of the training instances.


J. Neural Eng. 21 (2024) 066040                                                                                         P Koutsouvelis et al


   Figure 7. Output profiles of four patient-specific classifiers for case chb07 with 60, 45, 30, and 15 min preictal class definitions,
   respectively. Input is 7.0 h of continuous EEG recordings before the onset of seizure #1 of chb07. The red dotted line shows the
   SPC, and the black lines show the TP boundaries. The horizontal axis represents minutes before seizure onset (seizure onset at
   utmost right), and the vertical axis is the classification output. Sub-captions show the preictal class definition, CIOPR value, and
   F1-score achieved. Notations: SPC = seizure prediction convergence, TP = transition period, CIOPR = Continuous
   Input–Output Performance Ratio.


(⩾10%) across different preictal definitions, yet                       testing seizures, while SPC used only the ones sub-
yielded discordant F1-score results. In particular,                     ject to CIOPR testing. The criterion used to select
using the example of case chb07, the differences in                     the OPP (CIOPR or F1-score) is also displayed. On
SPC and output stability are depicted in figure 7.                      average, the subject-specific models achieved a sens-
Longer preictal periods led to earlier prediction,                      itivity of 99.31%, specificity of 95.34%, accuracy
shorter transition time and reduced output fluc-                        of 97.32%, and F1-score of 97.46%. FAR averaged
tuations, resulting in significantly greater CIOPR.                     33.6 per hour on a segment-wise basis, since they
Conversely, the F1-scores did not follow the same                       were computed on the raw model output. However,
trend, underscoring the inadequacy of conventional                      the average specificity exceeded 95%, suggesting that
metrics to fully capture the complex temporal beha-                     the introduction of a post-processing scheme would
vior of seizure prediction models, as discussed in                      significantly reduce FAR (h−1 ) in a clinical envir-
section 1.2.                                                            onment. The classifiers’ output converged at 76.8
    Overall, there was a discordance in the best-                       min before seizure onset, with a standard devi-
performing preictal definition between the two                          ation of 36.8 min, reflecting anticipated cross-patient
metrics in 7 out of the 13 cases that underwent                         heterogeneities.
CIOPR testing. This discrepancy occurred only
in cases where F1-score variations were less than
                                                                        4. Discussion
1% between the two best-performing preictal
definitions.
                                                                        We trained subject-specific classifiers for 19 pediat-
                                                                        ric patients of the CHB-MIT dataset to predict epi-
3.6. OPP selection and overall performance                              leptic seizures using raw scalp EEG signals. The pro-
For seizures eligible for CIOPR assessment, the OPP                     posed CNN-transformer deep learning architecture
of each patient was determined based on the highest                     achieved a BA of 97.32%, enabling confident seizure
CIOPR values, while for those without CIOPR-                            predictions up to 76.8 min prior to seizure onset on
eligible seizures, it was based on the highest F1-                      average. By introducing the CIOPR metric, we illus-
score, as outlined in section 2.7. Overall results are                  trated the significant impact of preictal class defini-
summarized in table 1, which includes the OPP for                       tion on model behavior and demonstrated how these
each patient and corresponding performance metrics.                     variations can be quantified to determine the OPP
Sensitivity, specificity, FAR, accuracy, AUC, and F1-                   to maximize the model’s usability for each individual
score were computed for the selected OPP using all                      patient.


J. Neural Eng. 21 (2024) 066040                                                                                    P Koutsouvelis et al


Table 1. Overall results for selected preictal definition per patient. Notations: FAR = false alarm rate (computed based on the EPOCH
[43] method), AUC = area under the receiver operating characteristic (ROC) curve, SPC = seizure prediction convergence, OPP =
optimal preictal period.

           Sensitivity      Specificity      FAR        Accuracy       F1-score        AUC         SPC          OPP
Case          (%)              (%)           (h−1 )       (%)            (%)           (%)         (mins)      (mins)       Criterion

chb01         100.0               99.85      1.06          99.93         99.93         99.99       61.8           45        CIOPR
chb02          99.76              96.32      26.5          98.04         98.08         99.86       66.7           60        CIOPR
chb03          99.87              97.56      17.6          98.71         98.73         99.93       N/A            30        F1-score
chb04          99.84              99.19      5.83          99.52         99.40         99.99       175.5          45        CIOPR
chb05          99.62              96.66      24.1          98.14         98.16         99.87       54.9           60        CIOPR
chb06          94.76              73.54      190           84.15         85.71         92.90       52.9           60        CIOPR
chb07          99.54              97.74      16.2          98.64         98.66         99.72       61.5           60        CIOPR
chb09          99.72              98.85      8.30          99.28         99.29         99.98       93.5           60        CIOPR
chb10          98.40              92.84      51.6          95.62         95.76         99.54       68.8           60        CIOPR
chb11          99.86              99.81      1.37          99.83         99.83         99.99       N/A            45        F1-score
chb14          97.85              86.81      95.0          92.33         92.73         97.68       52.1           60        CIOPR
chb16          99.64              97.00      21.6          98.32         98.33         99.82       62.5           60        CIOPR
chb17          99.45              97.57      17.5          98.51         98.51         99.82       N/A            60        F1-score
chb18          99.59              96.40      25.9          98.00         98.02         99.43       56.3           60        CIOPR
chb19         100.0               99.64      2.60          99.82         99.82        100.0        N/A            30        F1-score
chb20         100.0               98.84      8.37          99.39         99.42         99.99       N/A            15        F1-score
chb21          99.74              97.03      21.4          98.37         98.41         99.82       139.6          45        CIOPR
chb22          99.19              86.38      98.1          92.79         93.23         99.38       50.0           45        CIOPR
chb23         100.0               99.36      4.60          99.68         99.68         99.99       N/A            60        F1-score

Mean           99.31              95.34      33.6          97.32          97.46        99.35       76.8
± Std           1.20               6.38      46.0           3.76           3.41          1.61      36.8


4.1. Comparison with literature                                      4.2. CIOPR alongside conventional metrics
The BA metric (average of sensitivity and specificity)               The newly introduced CIOPR metric was used to
was used for comparison with existing literature to                  comprehensively assess model performance and com-
account for variations in the preictal-interictal data               pare the effect of different preictal state definitions.
ratio across studies. Table 2 details the patient-level              Analysis in section 3.5 demonstrated that integrat-
comparison with studies that report the sensitivity                  ive metrics like CIOPR can unravel pronounced per-
and specificity for at least 5 overlapping cases in the              formance differences among different preictal defini-
CHB-MIT dataset.                                                     tions that can strengthen or alter a hypothesis around
     Overall, the BA achieved by our CNN-                            the OPP.
Transformer model is comparable with the state-                          While the F1-score and other conventional met-
of-the-art studies. Additionally, cases chb06 and                    rics remain useful and can guide design choices, com-
chb14 exhibited on average the lowest BA across the                  paring high-performing classifiers necessitates more
included studies. The limited number of patients and                 sophisticated and sensitive measures to capture subtle
the absence of detailed pathological data in the CHB-                behavioral differences. Figure 8 compares the best-
MIT dataset prevent further exploration of the effect                performing preictal definition in our study (60 min)
of various epilepsy sub-types on seizure prediction                  with the most commonly used definition in the lit-
performance. Furthermore, at the chosen decision                     erature (30 min) across sensitivity, F1-score, and
threshold (0.5 in our study), specificity was consist-               CIOPR. Both intervals showed similar performance
ently lower than sensitivity, a pattern appearing also               in terms of sensitivity, while the improvements in the
in other studies [22–24, 46].                                        overall F1-score using the 60 min one remained mar-
     Only two studies investigated the impact of                     ginal, aligning with existing literature. When using
varying preictal intervals on model performance,                     CIOPR however, we were able to outline significant
with ranges from 15 to 120 min in [10] and 5                         performance improvements associated with the 60
to 15 min in [47]. Both showed improved spe-                         min window in terms of the hypothesized ideal model
cificity with longer preictal intervals, yet their over-             behavior (early prediction, low error, output consist-
all performance metrics–same as the ones outlined in                 ency, and sharp transition).
section 2.6–changed subtly across different windows.                     Furthermore, the integrative nature of CIOPR
Given these marginal gains, researchers often priorit-               enables a detailed breakdown of the individual meas-
ize the preictal interval that maximizes the number of               ures comprising it to thoroughly explore specific
seizures available for model training, typically select-             output characteristics. Figure 9 illustrates how these
ing 30 min before the onset [22, 24, 33, 44, 46, 48, 49].            measures were used to comprehensively assess the


     Table 2. Balanced accuracy (%) comparison between state-of-the-art literature and the proposed solution. The table includes studies reporting both sensitivity and specificity measures for at least five cases of the CHB-MIT dataset
     overlapping with our work..

                      Tsiouris        Wang          Xia            Zhu             Qi               Zhang         Ma              Qi                 Ryu            Jemal        Yang            Xu
                                                                                                                                                                                                                                              J. Neural Eng. 21 (2024) 066040


     Case            et al [10]     et al [44]      et al [22]     et al [23]      et al [33]      et al [45]     et al [20]      et al [46]      et al [47]      et al [48]     et al [49]      et al [32]       Average          Ours

     chb01            100.00           99.00        100.00         99.46           99.56             98.95        99.99           97.81             100.00          96.75        99.65           98.35             99.13           99.93
     chb02            100.00           99.00        97.93          99.47           94.70             93.15        89.48           96.12              86.94          95.55        75.75           N/A               93.46           98.04
     chb03            100.00          100.00        99.17          96.02           96.49             97.51        97.74           88.25              96.82          98.80        95.90           92.20             96.57           98.71
     chb04             99.97           99.27        N/A            N/A             N/A               97.07        N/A             N/A                78.26          91.35        N/A             N/A               93.18           99.52
     chb05             99.83           99.67        98.88          99.91           98.51             97.48        97.11           90.38              94.33          85.00        93.50           86.40             95.08           96.20
13   chb06             99.34           99.00        99.26          98.13           N/A               97.75        88.89           N/A                94.20          84.75        N/A             64.80             91.79           84.15
     chb07             99.88          100.00        97.50          92.04           N/A               99.40        83.97           N/A               100.00          93.60        N/A             N/A               95.80           98.64
     chb09            100.00           99.85        99.79          97.58           95.59             98.49        N/A             91.80              99.83          87.75        79.05           N/A               94.97           99.28
     chb10             99.91           97.83        99.86          99.64           93.70             93.68        93.37           90.42              90.53          90.70        80.85           N/A               93.68           95.62
     chb11            100.00           99.94        N/A            96.39           N/A               98.16        99.65           N/A               100.00          99.30        N/A             89.30             97.84           99.83
     chb14             99.86          100.00        98.22          99.65           99.65             86.63        89.93           90.56              89.67          74.70        69.30           79.60             89.81           92.33
     chb16             99.75           99.42        99.17          96.72           N/A               92.63        N/A             N/A                81.03          89.75        N/A             N/A               94.06           98.32
     chb17             99.95           99.76        98.61          97.98           N/A               95.02        N/A             N/A               100.00          97.05        N/A             N/A               98.34           98.51
     chb18             99.66           99.87        N/A            99.89           97.88             88.89        N/A             94.33              92.35          96.10        96.10           N/A               96.12           98.00
     chb19            100.00           98.65        N/A            100.00          98.25             97.30        98.83           95.97             100.00          99.50        95.80           N/A               98.43           99.82
     chb20            100.00           98.89        100.00         99.99           99.79             99.72        99.95           97.01             100.00          98.90        99.35           97.85             99.29           99.39
     chb21            100.00           98.98        98.34          96.88           99.78             89.40        95.55           97.85              96.91          89.10        92.70           78.65             94.51           98.37
     chb22            100.00           97.36        N/A            97.19           N/A               94.96        93.19           N/A                91.46          88.35        N/A             82.75             93.16           92.79
     chb23            100.00           95.00        99.38          99.97           99.80             93.13        99.75           99.52              94.64          94.75        98.90           98.85             97.81           99.68

     Mean              99.90           99.02        99.01          98.16           97.81             95.23        94.81           94.17              94.05          92.20        89.74           86.88             95.42           97.22
     ± Std              0.16            1.19        0.77           2.03            2.08               3.71        4.94            3.57                6.38           6.23        10.08           10.27              2.56            3.76


                                                                                                                                                                                                                                              P Koutsouvelis et al

J. Neural Eng. 21 (2024) 066040                                                                                       P Koutsouvelis et al


   Figure 8. Distribution of normalized sensitivity, F1-score, and CIOPR values across eligible subjects for the 60 and 30 min preictal
   definitions.


   Figure 9. Performance measures used for CIOPR calculation of seizure #1, case chb16 across different preictal state definitions.
   The best performance corresponds to the bottom-right corner. Sub-figure 9(d) assesses the quality of the sigmoidal fitting, where
   the difference between the convergence points of the fitted curve and the model’s output (seizure prediction convergence (SPC))
   are shown in the vertical axis. Data points marked as ‘plus’ in the plots represent different training runs per preictal definition,
   while ‘ring’ markers correspond to the mean values across the runs.


performance for case chb16. The advantages of a 60                     could lead to model overfitting, where classifiers
min preictal definition–early prediction time, minim-                  memorize rather than generalize training data [4].
ized positive and negative errors, short TP, and align-                Although the LOOCV approach prevents the model
ment with the fitted sigmoidal curve representing                      from encountering test seizures during training, the
ideal behavior–can be visualized in an interpretable                   uniform data acquisition setting and the close tem-
manner that conventional metrics lack.                                 poral proximity of recordings might still result in
                                                                       high similarity between training and testing sets [50].
4.3. Preictal length definition and model behavior                     Conversely, interictal data, recorded throughout the
Understanding how and why the chosen preictal                          whole day, exhibit greater variability from circadian
period influences model behavior can prove crit-                       rhythms and additional EEG patterns [51], com-
ical in designing systems tailored to the patients’                    plicating their classification. This greater variability
needs and addressing ongoing limitations in epileptic                  might explain the consistently lower specificity and its
seizure prediction research. In particular, specificity                significant reduction with shorter preictal durations,
increased with shorter preictal lengths, while                         as these entail fewer training samples. Concordance
sensitivity remained relatively invariant. This invari-                with the literature results indicates that the aforemen-
ability combined with the consistently high scores                     tioned limitations are broadly applicable to the field
could be suggestive of a key limitation in the field:                  and could inform future research directions.
insufficient data volume. Data oversampling in the                         Although specificity increased with longer
preictal state along with lack of external validation                  preictal definitions, NDerr did not follow the same


J. Neural Eng. 21 (2024) 066040                                                                      P Koutsouvelis et al


trends. This can be explained by NDerr being                 measures comprising CIOPR, due to the unique elec-
measured only within 10 h before onset, unlike spe-          trophysiological signature of each epileptic seizure.
cificity, which was calculated using all interictal state    Among these measures, prediction time is of utmost
data. Thus, NDerr was computed on the subset of              importance as it directly influences alarm generation
interictal data that was closer to the preictal-interictal   and provides a window for potential intervention.
boundary. Models trained with longer preictal inter-         Keeping two variables among Patient ID, Seizure ID,
vals could detect preictal-like dynamics many hours          Preictal Length fixed, and computing the mean stand-
before onset, leading to an earlier gradual increase         ard deviation on the third showed that variations
in positive predictions and consequently earlier Infl.       in prediction time could be primarily attributed to
Hence, the increased NDerr could be related to the           cross-patient heterogeneities (±38.3 min), followed
impending seizure. However, positive predictions             by intra-patient heterogeneities (±17.7 min), and
this far from the onset could cause patient distress         lastly, by the preictal period lengths used for training
and be considered undesired in a clinical setting.           (±13.2 min).
On the other hand, longer preictal intervals led to               The clinical usefulness of a seizure prediction sys-
reduced SPCerr values, earlier classifier convergence,       tem would rely on meeting the patients’ preferences
and higher correlation coefficients with the fitted          in prediction time and sensitivity-specificity trade-off
curve. This translates to higher accuracy, earlier pre-      [3]. Researchers in [52] highlighted that patient satis-
diction, and reduced output fluctuations, respect-           faction was maximized with short prediction times,
ively, which could be desired in a clinical setting.         allowing effective lifestyle changes. Long prediction
     Extended preictal periods were expected to help         times on the other hand could be more useful in a
classifiers learn spatiotemporal EEG features farther        closed-loop system, allowing room for drug-delivery
from the seizure onset, reducing the uncertainty dur-        or stimulation [53]. However, the observed cross-
ing the interictal-to-preictal transition. TP values         patient variations suggest that prediction time is not
decreased with longer preictal lengths but showed            merely a matter of preference but is intrinsically
no statistical significance. Interestingly, the lowest TP    linked to the preictal characteristics of each patient.
was achieved with the 45 min preictal length, suggest-       Additionally, intra-patient variations, although less
ing that features learned farther than this point might      pronounced, could significantly impact the effective-
often have diminished relevance for epileptic seizure        ness of seizure predictions. For instance, in case chb09,
prediction. Conversely, features learned within the          the SPC ranged from 63.9 to 125 min.
last 30 min before onset achieve high prediction                  A reliable system should predict seizures earlier
accuracy but may be insufficient for early identi-           than a minimum seizure prediction horizon (SPH)
fication of an impending seizure. This could lead            with fluctuations not exceeding the seizure occur-
to increased uncertainty during the TP and poten-            rence period (SOP), such that prediction times range
tially confusion in a clinical implementation setting        within the (SPH, SPH + SOP) interval [54]. SPH
through prolonged output fluctuations. This is fur-          should be large enough to allow clinical interven-
ther highlighted by the fact that across all metrics         tion (e.g. 30 min in [54]), while SOP could be lim-
among adjacent preictal definitions, the 45-to-30 min        ited to the duration of the treatment; e.g. 30 min for
comparison yielded the highest number of significant         some anti-epileptic drugs [54]. Cross-patient hetero-
differences.                                                 geneities could enable setting a realistic SPH inter-
                                                             val, informed by both the patient’s preferences and
4.4. Cross- and intra-patient heterogeneities                the electrophysiological signature of the preictal state.
The CIOPR-related measures and their sensitivity to          Case chb04 for instance exhibited SPC values of
different preictal period lengths varied across test-        133.3 and 217.5 min before the onset. A 30 min
ing seizures. This observation underscores the major         SPH selection would hence prove non-practical for
challenge in epileptic seizure prediction research:          this case, as it would require a SOP of at least 3
inter-seizure heterogeneities, both across and within        h, leading to increased uncertainty for the patient.
patients. These differences caused the OPP to fluc-          Similarly, understanding intra-patient heterogeneity
tuate between 60 and 45 min across patients, and             patterns could allow providing realistic SOP inter-
in some cases (e.g. chb01, chb22) within seizures            vals for each individual. For instance, at the OPP,
of the same patient. Cross-patient variations can            case chb07 experienced considerably less variations
be addressed by designing patient-specific models.           in prediction time (±4.7 min) than case chb09
Intra-patient variations can be managed by choosing          (±30.6 min).
the best average across seizures, as in our study, or
selecting a different preictal length definition for each    4.5. Limitations and future work
training seizure, as suggested by [5].                       Our study utilized raw scalp EEG signals with min-
    These approaches, though effective at improv-            imal pre-processing. Although the observed classi-
ing the classification of interictal and preictal seg-       fication performance was comparable to state-of-
ments, cannot eliminate inconsistent values across           the-art results, the 45 Hz low-pass cut-off could


J. Neural Eng. 21 (2024) 066040                                                                    P Koutsouvelis et al


have excluded high-frequency information relevant           depending on the individual and epilepsy patho-
for detecting preictal-state dynamics. The automatic        logy. This would ultimately lead to providing context-
selection of N = 1690 taps using the MNE pack-              aware warnings and improving the clinical reliability
age for the band-pass filter, though not an issue           of automated seizure prediction models.
in our case, could significantly increase computa-              The proposed solution would also benefit from
tional complexity in real-time systems. Additionally,       developing a channel-selection algorithm at the input
limiting the postictal state to only 1 h could lead         stage, as suggested by authors in [56]. Furthermore,
to contamination of interictal data with seizure-           implementing a post-processing scheme to filter out
related effects and diminish the model’s specificity.       incorrect predictions and generate confident alarms
However, it provided a greater number of eligible           would be useful. Clinically relevant metrics such as
seizures while maintaining competent classification         FAR (h−1 ) should then be computed on the post-
performance.                                                processed output and reported for a predefined SPH
     Besides the risk of overfitting, performance res-      and SOP. While the CIOPR algorithm prioritizes pro-
ults could be affected by data leakage, a prevalent         longed prediction times, future improvements should
issue in machine learning-related research [55]. In         tune it to emphasize convergence within the preferred
particular, the LOOCV approach might introduce              [SPH, SPH + SOP] range. Consistent EEG datasets
temporal leakage, due to the inclusion of ‘future’ data     will enable benchmarking on achieved CIOPC values
(i.e. seizures) in the training process. For example, a     by fixing the input signal duration and the contribu-
model trained on seizures No. 1, 3, 4, 5 and tested         tion of each term (e.g. TP).
on seizure No. 2 had access to information that
occurred both before and after the test seizure, poten-
                                                            5. Conclusions
tially introducing temporal dependencies between the
training and testing sets. This information would not
                                                            We introduced a CNN-Transformer model for pre-
be available in a realistic implementation setting and
                                                            dicting epileptic seizures using scalp EEG signals
could inflate the observed performance.
                                                            and proposed the novel CIOPR metric. Using the
     Furthermore, the classifiers’ output behavior was
                                                            CIOPR metric we established that varying preictal
not uniform across all subjects and seizures, introdu-
                                                            period lengths result in statistically significant dif-
cing limitations in the generalizability of the CIOPR
                                                            ferences in model behavior. Overall, increasing the
metric. Convergence did not always occur right before
                                                            preictal length led to earlier prediction times, sharper
seizure onset (figure 4(b)), while in several cases, per-
                                                            interictal-preictal transitions, and reduced output
sistent output fluctuations complicated the identi-
                                                            fluctuations in the preictal state, at the expense of
fication of the SPC start (figure 4(d)). Additionally,
                                                            an increased volume of positive predictions several
the TP was directly computed from the fitted curve,
                                                            hours before the onset. This finding highlights the
making it dependent on the quality of the fitting.
                                                            need for careful selection of the OPP depending on
Figure 7 highlighted the issue, where small variations
                                                            the desired usability.
in model behavior caused large differences in the
                                                                To the best of our knowledge, this is the first
stretch of the sigmoidal curve and consequently in the
                                                            study that uses a fitting curve to model the output of
calculated TP. Lastly, the penalty introduced due to
                                                            a seizure prediction classifier. The newly introduced
long TPs was dependent on the interictal duration,
                                                            CIOPR metric provides interpretability on model
ND, inhibiting direct comparisons across different
                                                            performance that conventional metrics lack, by out-
seizures.
                                                            lining how the distribution of positive predictions
     Future efforts should prioritize improving the
                                                            varies over time. With the increasing complexity and
quality of EEG datasets. Extended recording times
                                                            classification capabilities of deep learning architec-
and longitudinal acquisitions are necessary to assess
                                                            tures, more intuitive and sophisticated measures are
algorithms’ generalizability over time. Such a dataset
                                                            required to capture subtle performance differences.
could alleviate the need for the LOOCV approach and
                                                            Integrative measures like CIOPR, apart from being
consequently mitigate data leakage issues. Reporting
                                                            useful in selecting the most suitable deep learning
pathological information, such as the location of the
                                                            model, they can provide meaningful clinical insights
seizure onset zone, clinical semiology, and epilepsy
                                                            and shed light on future research directions.
sub-type, would be crucial in drawing clinically rel-
evant conclusions, including which seizure sub-types
could be more challenging to predict. Additionally,         Data availability statement
it could enable an understanding of preictal state-
related heterogeneities across seizures and patients.       The raw CHB-MIT dataset that supports the find-
Unraveling those patterns could enable tailored iden-       ings of this study are available in the following
tification of SPH and SOP intervals, that could be          links: https://doi.org/10.13 026/C2K01R; and further
dynamically adjusted during the course of the day,          inquiries can be directed to the corresponding author.


J. Neural Eng. 21 (2024) 066040                                                                                      P Koutsouvelis et al


Acknowledgments                                                       [12] Tang L, Xie N, Zhao M and Wu X 2020 Seizure prediction
                                                                           using multi-view features and improved convolutional gated
                                                                           recurrent network IEEE Access 8 172352–61
The authors would like to acknowledge the Epilepsy
                                                                      [13] Choi W, Kim M-J, Yum M-S and Jeong D-H 2022 Deep
Research UK Doctoral Training Centre and Simons                            convolutional gated recurrent unit combined with attention
Initiative for the Developing Brain for providing the                      mechanism to classify pre-ictal from interictal EEG with
scholarship to B C and a University of Edinburgh’s                         minimized number of channels J. Pers. Med. 12 763
                                                                      [14] Vaswani A Shazeer N Parmar N Uszkoreit J Jones L
Harmonised Impact Acceleration Account (IAA)
                                                                           Gomez A N Kaiser L and Polosukhin I 2017 Attention is all
grant to J E and A G S.                                                    you need (arXiv:1706.03 762)
                                                                      [15] Uddin M R, Mahbub S, Rahman M S and Bayzid M S 2020
                                                                           Saint: self-attention augmented inception-inside-inception
ORCID iDs                                                                  network improves protein secondary structure prediction
                                                                           Bioinformatics 36 4599–608
                                                                      [16] Chen Q Sun C Gao C and Liu S-C 2024 Epilepsy seizure
Petros Koutsouvelis  https://orcid.org/0009-0002-                         detection and prediction using an approximate spiking
3020-0030                                                                  convolutional transformer (arXiv:2402.09424)
Bartlomiej Chybowski  https://orcid.org/0000-                        [17] Ke N, Lin T, Lin Z, Zhou X-H and Ji T 2022 Convolutional
                                                                           transformer networks for epileptic seizure detection Proc.
0002-1323-4370                                                             31st ACM Int. Conf. on Information & Knowledge
Alfredo Gonzalez-Sulser  https://orcid.org/0000-                          Management, ser. CIKM ‘22 (Association for Computing
0003-3494-4029                                                             Machinery Association for Computing Machinery)
Shima Abdullateef  https://orcid.org/0000-0002-                           pp 4109–13
                                                                      [18] Hu S, Liu J, Yang R, Wang Y, Wang A, Li K, Liu W and
6091-7094                                                                  Yang C 2023 Exploring the applicability of transfer learning
Javier Escudero  https://orcid.org/0000-0002-                             and feature engineering in epilepsy prediction using hybrid
2105-8725                                                                  transformer model IEEE Trans. Neural Syst. Rehabil. Eng.
                                                                           31 1321–32
                                                                      [19] Tian Z, Hu B, Si Y and Wang Q 2023 Automatic seizure
                                                                           detection and prediction based on brain connectivity
References                                                                 features and a CNNs meet transformers classifier Brain
                                                                           Sciences 13 820
 [1] Milligan T A 2021 Epilepsy: a clinical overview Am. J. Med.      [20] Ma H, Wu Y, Tang Y, Chen R, Xu T and Zhang W 2024
     134 840–7                                                             Parallel dual-branch fusion network for epileptic seizure
 [2] Malik N I, Fatima R, Ullah I, Atta M, Awan A, Nashwan A J             prediction Comput. Biol. Med. 176 108565
     and Ahmed S 2022 Perceived stigma, discrimination and            [21] Li C, Huang X, Song R, Qian R, Liu X and Chen X 2022
     psychological problems among patients with epilepsy Front.            EEG-based seizure prediction via transformer guided CNN
     Psychiatry 13 1000870                                                 Measurement 203 111948
 [3] Meisel C, El Atrache R, Jackson M, Schubach S, Ufongene C        [22] Xia L, Wang R, Ye H, Jiang B, Li G, Ma C and Gao Z 2024
     and Loddenkemper T 2020 Machine learning from                         Hybrid lsTM–transformer model for the prediction of
     wristband sensor data for wearable, noninvasive seizure               epileptic seizure using scalp EEG IEEE Sens. J. 24 21123–31
     forecasting Epilepsia 10 1–14                                    [23] Zhu R, Pan W-x, Liu J-X and Shang J-l 2024 Epileptic seizure
 [4] Chung Y, Jeon Y, Yoo S, Kim H and Hwang H 2021 Big data               prediction via multidimensional transformer and recurrent
     analysis and artificial intelligence (AI) in epilepsy – common        neural network fusion J. Trans. Med. 22 10
     data model analysis and machine learning–based seizure           [24] Zhu L, Wang W, Huang A, Ying N, Xu P and Zhang J 2024
     detection and forecasting Clin. Exp. Pediatr. 65 11                   An efficient channel recurrent criss-cross attention
 [5] Bandarabadi M, Rasekhi J, Teixeira C A, Karami M R and                network for epileptic seizure prediction Med. Eng. Phys.
     Dourado A 2015 On the proper selection of preictal period             130 104213
     for seizure prediction Epilepsy Behavior 46 158–66               [25] Li F et al 2019 Transition of brain networks from an
 [6] Daoud H and Bayoumi M A 2019 Efficient epileptic seizure              interictal to a preictal state preceding a seizure revealed
     prediction based on deep learning IEEE Trans. Biomed.                 by scalp EEG network analysis Cogn. Neurodynamics
     Circuits Syst. 13 804–13                                              13 175–81
 [7] Khan H, Marcuse L, Fields M, Swann K and Yener B 2018            [26] Leal A et al 2023 Unsupervised EEG preictal interval
     Focal onset seizure prediction using convolutional networks           identification in patients with drug-resistant epilepsy Sci.
     IEEE Trans. Biomed. Eng. 65 2109–18                                   Rep. 13 01
 [8] Chung Y, Jeon Y, Choi S, Cho A, Kim H, Hwang H and               [27] Singhal B and Pooja F 2023 Unveiling intractable
     Kim K 2020 Deep convolutional neural network based                    epileptogenic brain networks with deep learning algorithms:
     interictal-preictal electroencephalography prediction:                a novel and comprehensive framework for scalable seizure
     application to focal cortical dysplasia type-ii Frontiers             prediction with unimodal neuroimaging data in pediatric
     Neurol. 11 11                                                         patients 2023 1st DMIHER Int. Conf. on Artificial Intelligence
 [9] Wang G, Wang D, Du C, Li K, Zhang J, Liu Z, Tao Y,                    in Education and Industry 4.0 (IDICAIEI) (Wardha, India)
     Wang M, Cao Z and Yan X 2020 Seizure prediction using                 vol 1 pp 1–6
     directed transfer function and convolution neural network        [28] Eberlein M, Müller J, Yang H, Walz S, Schreiber J, Tetzlaff R,
     on intracranial EEG IEEE Trans. Neural Syst. Rehabil. Eng.            Creutz S, Uckermann O and Leonhardt G 2019 Evaluation of
     28 2711–20                                                            machine learning methods for seizure prediction in epilepsy
[10] Tsiouris K, Pezoulas V, Zervakis M, Konitsiotis S,                    Curr. Dir. Biomed. Eng. 5 109–12
     Koutsouris D and Fotiadis D 2018 A long short-term               [29] Batista J, Pinto M, Tavares M, Lopes F, Oliveira A and
     memory deep learning network for the prediction of                    Teixeira C 2024 EEG epilepsy seizure prediction: the
     epileptic seizures using EEG signals Comput. Biol. Med.               post-processing stage as a chronology Sci. Rep. 14 01
     99 24–37                                                         [30] Zhang Z and Parhi K K 2016 Low-complexity seizure
[11] Singh K and Malhotra J 2022 Two-layer LSTM                            prediction from IEEG/SEEG using spectral power and ratios
     network-based prediction of epileptic seizures using EEG              of spectral power IEEE Trans. Biomed. Circuits Syst.
     spectral features Complex Intell. Syst. 8 02                          10 693–706


J. Neural Eng. 21 (2024) 066040                                                                                     P Koutsouvelis et al


[31] Shoeb A, Edwards H, Connolly J, Bourgeois B, Ted Treves S              synchronization for epileptic seizure prediction IEEE J.
     and Guttag J 2004 Patient-specific seizure onset detection             Biomed. Health Inform. 27 900–11
     Epilepsy Behavior 5 483–98                                        [45] Zhang J, Zheng S, Chen W, Du G, Fu Q and Jiang H 2024 A
[32] Xu T, Wu Y, Tang Y, Zhang W and Cui Z 2024 Dynamic                     scheme combining feature fusion and hybrid deep learning
     functional connectivity neural network for epileptic seizure           models for epileptic seizure detection and prediction Sci.
     prediction using multi-channel EEG signal IEEE Signal                  Rep. 14 16916
     Process. Lett. 31 1499–503                                        [46] Qi N, Piao Y, Zhang H, Wang Q and Wang Y 2024 Seizure
[33] Qi N, Piao Y, Yu P and Tan B 2023 Predicting epileptic                 prediction based on improved vision transformer model for
     seizures based on EEG signals using spatial depth features of          EEG channel optimization Comput. Methods Biomech.
     a 3D-2D hybrid CNN Med. Biol. Eng. Comput. 61 03                       Biomed. Eng. 0 1–12
[34] Abood W and Susanta B 2024 (StatPearls Publishing)                [47] Ryu S and Joe I 2021 A hybrid densenet-lSTM model for
     (available at: https://www.ncbi.nlm.nih.gov/books/                     epileptic seizure prediction Appl. Sci. 11 7661
     NBK526004/)                                                       [48] Jemal I, Mezghani N, Abou-Abbas L and Mitiche A
[35] Ein Shoka A A, Dessouky M M, El-Sayed A and Hemdan E                   2022 An interpretable deep learning classifier for epileptic
     E-D 2023 EEG seizure detection: concepts, techniques,                  seizure prediction using EEG data IEEE Access
     challenges and future trends Multimedia Tools Appl.                    10 60141–50
     82 42021–51                                                       [49] Yang X, Zhao J, Sun Q, Lu J and Ma X 2021 An effective dual
[36] de Cheveigné A and Arzounian D 2018 Robust detrending,                 self-attention residual network for seizure prediction IEEE
     rereferencing, outlier detection and inpainting for                    Trans. Neural Sys. Rehabil. Eng. 29 1604–13
     multichannel data NeuroImage 172 903–12                           [50] Moutonnet N, White S, Campbell B P, Mandic D and Scott G
[37] Leske S and Dalal S S 2019 Reducing power line noise in EEG            2024 Clinical translation of machine learning algorithms for
     and meg data via spectrum interpolation NeuroImage                     seizure detection in scalp electroencephalography: a
     189 763–76                                                             systematic review (arXiv:2404.15332)
[38] Klimes P et al 2024 Interictal stereo-electroencephalography      [51] Karoly P, Freestone D, Boston R, Grayden D, Himes D,
     features below 45 Hz are sufficient for correct localization of        Leyde K, Seneviratne U, Berkovic S, O’Brien T and Cook M
     the epileptogenic zone and postsurgical outcome prediction             2016 Interictal spikes and epileptic seizures: their
     Epilepsia 65 2935–45                                                   relationship and underlying rhythmicity Brain
[39] Dutta A et al 2024 Deep learning-based multi-head                      139 aww019
     self-attention model for human epilepsy identification from       [52] Cook M J et al 2013 Prediction of seizure likelihood with a
     EEG signal for biomedical traits Multimedia Tools Appl.                long-term, implanted seizure advisory system in patients
     83 80201–23                                                            with drug-resistant epilepsy: a first-in-man study Lancet
[40] Terven J Cordova-Esparza D M Ramirez-Pedraza A and                     Neurol. 12 563–71
     Chavez-Urbiola E A 2023 Loss functions and metrics in deep        [53] Gadhoumi K, Lina J-M, Mormann F and Gotman J 2016
     learning. a review (arXiv:2307.02694)                                  Seizure prediction for therapeutic devices: a review J.
[41] Reddi S J Kale S and Kumar S 2019 On the convergence of                Neurosci. Methods 260 270–82
     Adam and beyond (arXiv:1904.09237)                                [54] Alaei H, Khalilzadeh M and Gorji A 2019 Optimal selection
[42] Jandó G, Miko E, MarkÓ K, Hollody K, TÖrÖk B and                      of SOP and SPH using fuzzy inference system for on-line
     Kovacs I 2012 Early-onset binocularity in preterm infants              epileptic seizure prediction based on EEG phase
     reveals experience-dependent visual development in humans              synchronization Australas. Phys. Eng. Sci. Med. 42 10
     Proc. Natl Acad. Sci. USA 109 11049–52                            [55] Kapoor S and Narayanan A 2022 Leakage and the
[43] Ziyabari S Shah V Golmohammadi M Obeid I and Picone J                  reproducibility crisis in ML-based science Patterns 4 100804
     2017 Objective evaluation metrics for automatic                   [56] Affes A, Mdhaffar A, Triki C, Jmaiel M and Freisleben B
     classification of EEG events (arXiv:1712.10107)                        2022 Personalized attention-based EEG channel selection
[44] Wang Y, Shi Y, Cheng Y, He Z, Wei X, Chen Z and Zhou Y                 for epileptic seizure prediction Expert Syst. Appl.
     2023 A spatiotemporal graph attention network based on                 206 117733
```
