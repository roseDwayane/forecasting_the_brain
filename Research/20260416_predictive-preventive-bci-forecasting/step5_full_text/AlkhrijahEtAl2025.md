---
citation_key: "AlkhrijahEtAl2025"
paper_id: "paper_227"
title: "Feature fusion ensemble classification approach for epileptic seizure prediction using electroencephalographic bio-signals."
authors: "Yazeed Alkhrijah; Shehzad Khalid; Syed Muhammad Usman; Amina Jameel; Muhammad Zubair; Haya Aldossary; Aamir Anwar; Saad Arif"
year: 2025
doi: "10.3389/fmed.2025.1566870"
source: "publisher-pdf (doi: 10.3389/fmed.2025.1566870)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Feature fusion ensemble classification approach for epileptic seizure prediction using electroencephalographic bio-signals.

**Citation:** `AlkhrijahEtAl2025` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.3389/fmed.2025.1566870](https://doi.org/10.3389/fmed.2025.1566870)
**Source PDF:** `full_pdf/Yazeed2025.pdf`

## Abstract

Epilepsy is a neurological disorder in which patients experience recurrent seizures, with the frequency of occurrence more than twice a day, which highly affects a patient's life. In recent years, multiple researchers have proposed multiple machine learning and deep learning-based methods to predict the onset of seizures using electroencephalogram (EEG) signals before they occur; however, robust preprocessing to mitigate the effect of noise, channel selection to reduce dimensionality, and feature extraction remain challenges in accurate prediction. This study proposes a novel method for accurately predicting epileptic seizures. In the first step, a Butterworth filter is applied, followed by a wavelet and a Fourier transform for the denoising of EEG signals. A non-overlapping window of 15 s is selected to segment the EEG signals, and an optimal spatial filter is applied to reduce the dimensionality. Handcrafted features, including both time and frequency domains, have been extracted and concatenated with the customized one-dimensional convolutional neural network-based features to form a comprehensive feature vector. It is then fed into three classifiers, including support vector machines, random forest, and long short-term memory (LSTM) units. The output of these classifiers is then fed into the model-agnostic meta learner ensemble classifier with LSTM as the base classifier for the final prediction of interictal and preictal states. The proposed methodology is trained and tested on the publicly available CHB-MIT dataset while achieving 99.34% sensitivity, 98.67% specificity, and a false positive alarm rate of 0.039. The proposed method not only outperforms the existing methods in terms of sensitivity and specificity but is also computationally efficient, making it suitable for real-time epileptic seizure prediction systems.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
TYPE Original Research
                                                                                                                          PUBLISHED 04 August 2025
                                                                                                                          DOI 10.3389/fmed.2025.1566870


                                                    Feature fusion ensemble
OPEN ACCESS                                         classiﬁcation approach for
                                                    epileptic seizure prediction using
EDITED BY
Salil Bharany,
Chitkara University, India

REVIEWED BY
Diponkor Bala,
                                                    electroencephalographic
City University, Bangladesh
Prabhsimran Singh,
Guru Nanak Dev University, India
                                                    bio-signals
*CORRESPONDENCE
Syed Muhammad Usman                                 Yazeed Alkhrijah1,2 , Shehzad Khalid3,4 ,
  smusman.h11@bahria.edu.pk
Saad Arif                                           Syed Muhammad Usman5*, Amina Jameel4 , Muhammad Zubair6 ,
  sarif@kfu.edu.sa
                                                    Haya Aldossary7 , Aamir Anwar8 and Saad Arif9*
RECEIVED 25 January 2025
ACCEPTED 04 July 2025                                 Department of Electrical Engineering, Imam Mohammad Ibn Saud Islamic University (IMSIU), Riyadh,
PUBLISHED 04 August 2025                            Saudi Arabia, 2 King Salman Center for Disability Research (KSCDR), Riyadh, Saudi Arabia, 3 Computer
                                                    and Information Sciences Research Center (CISRC), Imam Mohammad Ibn Saud Islamic University,
CITATION
                                                    Riyadh, Saudi Arabia, 4 Department of Computer Engineering, Bahria University, Islamabad, Pakistan,
Alkhrijah Y, Khalid S, Usman SM, Jameel A,          5
                                                      Department of Computer Science, Bahria University, Islamabad, Pakistan, 6 Interdisciplinary Research
Zubair M, Aldossary H, Anwar A and Arif S
                                                    Center for Finance and Digital Economy, King Fahd University of Petroleum and Minerals, Dhahran,
(2025) Feature fusion ensemble classiﬁcation
                                                    Saudi Arabia, 7 Computer Science Department, College of Science and Humanities, Imam
approach for epileptic seizure prediction
                                                    Abdulrahman Bin Faisal University, Jubail, Saudi Arabia, 8 School of Computing, University of
using electroencephalographic bio-signals.
                                                    Portsmouth, London Campus, London, United Kingdom, 9 Department of Mechanical Engineering,
Front. Med. 12:1566870.
                                                    College of Engineering, King Faisal University, Al Ahsa, Saudi Arabia
doi: 10.3389/fmed.2025.1566870

COPYRIGHT
© 2025 Alkhrijah, Khalid, Usman, Jameel,
Zubair, Aldossary, Anwar and Arif. This is an       Introduction: Epilepsy is a neurological disorder in which patients experience
open-access article distributed under the           recurrent seizures, with the frequency of occurrence more than twice a day,
terms of the Creative Commons Attribution           which highly affects a patient’s life. In recent years, multiple researchers have
License (CC BY). The use, distribution or
reproduction in other forums is permitted,          proposed multiple machine learning and deep learning-based methods to
provided the original author(s) and the             predict the onset of seizures using electroencephalogram (EEG) signals before
copyright owner(s) are credited and that the        they occur; however, robust preprocessing to mitigate the effect of noise,
original publication in this journal is cited, in
accordance with accepted academic practice.         channel selection to reduce dimensionality, and feature extraction remain
No use, distribution or reproduction is             challenges in accurate prediction.
permitted which does not comply with these
terms.                                              Methods: This study proposes a novel method for accurately predicting epileptic
                                                    seizures. In the ﬁrst step, a Butterworth ﬁlter is applied, followed by a wavelet
                                                    and a Fourier transform for the denoising of EEG signals. A non-overlapping
                                                    window of 15 s is selected to segment the EEG signals, and an optimal spatial ﬁlter
                                                    is applied to reduce the dimensionality. Handcrafted features, including both
                                                    time and frequency domains, have been extracted and concatenated with the
                                                    customized one-dimensional convolutional neural network-based features to
                                                    form a comprehensive feature vector. It is then fed into three classiﬁers, including
                                                    support vector machines, random forest, and long short-term memory (LSTM)
                                                    units. The output of these classiﬁers is then fed into the model-agnostic meta
                                                    learner ensemble classiﬁer with LSTM as the base classiﬁer for the ﬁnal prediction
                                                    of interictal and preictal states.
                                                    Results: The proposed methodology is trained and tested on the publicly
                                                    available CHB-MIT dataset while achieving 99.34% sensitivity, 98.67% speciﬁcity,
                                                    and a false positive alarm rate of 0.039.
                                                    Discussion: The proposed method not only outperforms the existing methods
                                                    in terms of sensitivity and speciﬁcity but is also computationally efficient, making
                                                    it suitable for real-time epileptic seizure prediction systems.

                                                    KEYWORDS

                                                    AI in healthcare, epilepsy, electroencephalogram, epileptic seizure prediction, signal
                                                    quality index, optimal spatial ﬁlter, 1DCNN, ensemble classiﬁer


Frontiers in Medicine                                                      01                                                               frontiersin.org

Alkhrijah et al.                                                                                                          10.3389/fmed.2025.1566870


1 Introduction                                                                 patients still face considerable challenges due to inaccurate seizure
                                                                               forecasting, leading to compromised safety and anxiety among
    Epilepsy is a neurological disorder in which patients suffer from          epilepsy patients.
seizures, and it affects their quality of life as a sudden seizure                  A typical method of epileptic seizure prediction involves
may cause an accident or injury while driving, climbing stairs, or             preprocessing of EEG signals for noise removal and channel
walking on the road, etc. Seizure disturbs the activity of the brain,          selection, followed by feature extraction and classification.
which can be observed by visualizing the electroencephalographic               Numerous techniques to preprocess EEG signals have been
(EEG) signals recorded by placing electrodes on the scalp of the               proposed in recent years for removing noise and artifacts such as
patient’s brain (1). Seizures are divided into four states: interictal,        eye blinks, eye movements, and muscle activity before feeding the
the normal state; preictal, which starts a few minutes before the              data into the model. Fei et al. (6) and Usman et al. (14) proposed
onset of seizure and ends with the seizure onset; ictal, in which              bandpass filters to preprocess the EEG signals. Wang et al. (20)
the seizure occurs; and postictal, which starts after the seizure.             has employed an infinite impulse response (IIR) bandpass filter
Seizures can be categorized into two types, i.e., focal and generalized        and filtered the segmented data to filter out artifacts. Cho et al. (8)
seizures. Focal seizures are normally treatable with surgical                  has used the fast Fourier transform (FFT). Common spatial pattern
procedures, whereas generalized seizures can only be treated with              (CSP) is applied to reduce the effect of artifacts from EEG signals
the help of medicines; however, it has been observed that in 70%               by Birjandtalab et al. (4). Researchers (14, 21, 22) have made use
of the cases these seizures cannot be completely controlled with the           of the short-time Fourier transform (STFT) for preprocessing. Jana
help of medicines (2). Researchers (3–19) have proposed multiple               et al. (9) has utilized a pool-based technique with a 30-s window for
methods to predict the onset of seizures before they occur by                  noise reduction.
predicting the preictal state; however, accurate prediction remains                 Duun-Henriksen et al. (23) selected channels based on the
a challenge due to multiple factors. EEG signals are susceptible               maximum variance, the difference in variance, and entropy.
to noise added during signal acquisition, high dimensionality                  Entropy indicates the extent of disorder, impurity, and uncertainty,
due to the number of channels, and computational complexity                    so the channels with the highest entropy were selected. To select
of feature extraction and accurate classification. Figure 1 shows              channels that carry the highest information and are optimal,
a plot of three EEG signals from 1-h continuous recordings.                    Daoud and Bayoumi (10) has selected channels with the maximum
Accurate seizure prediction significantly impacts patient safety               variance entropy product. Birjandtalab et al. (4) has used a random
and quality of life by reducing the risks of sudden accidents                  decision forest for channel selection. Cogan et al. (7) selected the
or injuries during seizures. Despite advancements, clinicians and              best channel by ranking all the features based on the information


    FIGURE 1
    One-hour span session of EEG recordings for three channels.


Frontiers in Medicine                                                     02                                                            frontiersin.org

Alkhrijah et al.                                                                                                              10.3389/fmed.2025.1566870


gain for each subject. Parvez and Paul (24) checked the significance            by Bajaj and Sharma (31) on a variety of LSTM-based architectures.
of each channel individually, then eliminated the channel of low                A novel mobile network information gain (M-NIG) technique was
significance and selected the best channels by calculating the                  presented by Meng et al. (32) with a focus on individual-specific
average classification accuracy iteratively. Wang et al. (20) in                multi-channel EEG networks to lower noise and greatly improve
their research study calculated a signal quality index (SQI), based             prediction robustness. Notwithstanding these developments, there
on signal complexity. They brought three types of signals into                  are still issues that need to be addressed, mainly in the areas
consideration, and the optimal channels were selected accordingly.              of computational complexity, practicality for real-time clinical
     Commonly used feature extraction methods include                           applications, efficient dimensionality reduction, and reliable
continuous wavelet transform (CWT), discrete cosine                             handling of class-imbalanced data. These issues together highlight
transformation (DCT), and discrete wavelet transform (DWT).                     the necessity for further research.
Tsiouris et al. (25), Jana and Mukherjee (16), Alotaiby et al.                       Current approaches for epileptic seizure prediction
(5), and Arif et al. (21) applied DWT to extract time-frequency                 predominantly utilize all available EEG channels. This practice
features and then support vector machines (SVM) for predictions.                is computationally expensive, increases time complexity, and
Asharindavida et al. (11) utilized empirical mode decomposition                 raises hardware and financial costs, highlighting the need for
(EMD) for feature extraction. Birjandtalab et al. (4), Birjandtalab             methods that can identify and utilize only the most informative
et al. (3), and Borhade et al. (12) employed power spectral density             channels. The high dimensionality of EEG data often affects
(PSD) for feature extraction. Fei et al. (6) has applied a FrFT-based           the efficiency and accuracy of predictive models. Despite its
chaos method to obtain relevant features. Both time and frequency               critical impact, this challenge has been largely overlooked in
domain features, along with total energy spectrum and energy                    existing studies, necessitating effective dimensionality reduction
percentage-based features, were extracted to be used as input to                techniques to enhance prediction performance. Many researchers
the classifier (15). Zhang et al. (13) has made use of CSP-based                have not adequately addressed the issue of class imbalance, a
feature extraction. Truong et al. (22) and Arif et al. (26) used STFT           prevalent challenge in seizure prediction where certain classes
to extract features. Deep learning (DL) can also be used for feature            (e.g., seizure events) are underrepresented compared to others.
extraction, as Daoud and Bayoumi (10) has extracted features                    This imbalance can skew model performance and compromise
through DL techniques.                                                          prediction reliability.
     Once features are extracted, the next task is to distinguish                    We propose a novel method for epileptic seizure prediction
the signal between interictal and preictal states. Researchers have             to address these research gaps, which have been identified after a
made use of machine learning (ML) and DL classifiers for the                    comprehensive literature review. In the first step, the Butterworth
classification of EEG signals in seizure prediction methods. SVM                filter is applied, followed by wavelet and Fourier transforms for
with cross-validation was used for classification by Tamanna et al.             denoising of EEG signals. A non-overlapping window of 15 s
(15), Alotaiby et al. (5), and Asharindavida et al. (11), a least square        is selected to segment the EEG signals, and an optimal spatial
SVM classifier was applied to classify the EEG signals. Back-forward            filter is applied to reduce the dimensionality. Handcrafted features,
propagation neural networks (BPNN) and linear discriminant                      including both time and frequency domains, have been extracted
analysis (LDA) were also used for classification (6, 11, 13). Fei               and concatenated with the customized one-dimensional CNN
et al. (6), Usman et al. (14), Alotaiby et al., (5), Asharindavida              (1DCNN)-based features to form a comprehensive feature vector.
et al. (11), and Alickovic et al. (27) employed k-nearest neighbor              It is then fed into three classifiers, including SVM, RF, and LSTM
(kNN), and random forest (RF) for classification. In the study by               units, and the output of these classifiers is then fed into a model-
Truong et al. (22), a convolutional neural network (CNN) was                    agnostic meta learner (MAML) ensemble classifier with LSTM as
utilized for the classification of preictal and interictal states. Daoud        base classifier for the final prediction of interictal and preictal states.
and Bayoumi (10) and Alotaiby et al. (5) have used DL models                    The contributions of this research include:
[multilayer perceptron (MLP), deep CNN (DCNN), bidirectional
LSTM (Bi-LSTM)] for classification tasks.                                         • Introduced a novel technique to identify the most informative
     DL and EEG-based seizure prediction has advanced                               EEG channels, improving prediction accuracy while
significantly in recent years. By successfully modeling EEG data                    significantly reducing computational costs, a key challenge in
across several spatial and temporal scales, Dong et al. (28) proposed               real-time applications.
a novel multi-scale spatio-temporal attention network (MSAN),                     • Developed an effective dimensionality reduction method to
which increased the accuracy of seizure prediction. Alasiry et al.                  deal with the high-dimensional nature of EEG data, which
(29) suggested a heterogeneous graph neural network (GNN) that                      affects the performance of prediction algorithms.
enhanced clinical interpretability and predictive performance by                  • Proposed a surrogate channel by combining optimal EEG
capturing intricate EEG channel interactions. A CNN-Bi-LSTM                         channels that contribute the most to seizure prediction.
hybrid model was presented by Cao et al. (30), who also developed a               • Demonstrated the effectiveness of the proposed method on the
feature-level fusion technique that showed improved performance                     publicly available CHB-MIT dataset, achieving a sensitivity of
for epileptic seizure prediction across multiple datasets. Bi-LSTM                  99.34% and specificity of 98.67% with a false positive alarm
consistently outperformed other recurrent neural network (RNN)                      rate of 0.03. These results outperform various state-of-the-art
structures like gated recurrent units (GRU), MLP, and DCNN for                      techniques, establishing a new benchmark in epileptic seizure
seizure prediction tasks according to an ablation study conducted                   prediction.


Frontiers in Medicine                                                      03                                                               frontiersin.org

Alkhrijah et al.                                                                                                            10.3389/fmed.2025.1566870


    FIGURE 2
    Flow diagram of the proposed methodology of epileptic seizure prediction.


2 Methodology                                                                   critical to ensure data quality for reliable seizure prediction. In this
                                                                                research, we used a publicly available CHB-MIT dataset (33) that
    To overcome the identified limitations and enhance seizure                  comprises EEG recordings of 24 pediatric individuals recorded in
prediction accuracy, our methodology strategically targets the three            the Children’s Hospital Boston. The dataset has been annotated
main challenges: noise reduction in EEG signals, dimensionality                 by the medical experts with the start and end time of the seizure
reduction, and class imbalance mitigation. We propose a novel                   for each session of all individuals. EEG signals have been recorded
method of epileptic seizure prediction using EEG signals. It consists           with 23 channels and follow the 10–20 electrode placement method.
of three steps, including the preprocessing of EEG signals, feature             The dataset has been sampled at 256 Hz and totals 644 h of
extraction, and classification between preictal and interictal states.          recordings. We have divided EEG signals into equal-sized segments
The preprocessing step involves segmentation of EEG signals into                with the help of an equal-sized, non-overlapping window of 15 s.
equal-size segments using a non-overlapping window, followed                    Figure 3 shows the plot of segmented EEG signals proposed in this
by multistage noise removal using Butterworth filter, wavelet,                  research.
and Fourier transforms, and conversion of multi-channel EEG                          After segmenting the EEG signals, preictal and interictal signals
signals into a single surrogate channel. After preprocessing, both              were separated. Preictal and interictal samples were carefully
handcrafted and automated features have been extracted and                      selected, considering that preictal and postictal samples may
concatenated to form a single feature vector. Time and frequency                overlap. Therefore, we included only those sessions for interictal
domain features include statistical and spectral signatures, whereas            state samples where no seizure onset occurred within two sessions
a customized architecture of 1DCNN has been proposed to                         before or after. Preictal state has been considered as 30 min before
extract automated features. Figure 2 shows the flow diagram of the              the onset of the seizure, provided that there was no seizure in the
proposed method. The following subsection presents all three steps              last session to avoid the postictal state overlapping with the preictal
of the proposed methodology in detail.                                          state. EEG signals are sensitive to noise, making it essential to apply
                                                                                various techniques to remove noise and artifacts, ensuring that
                                                                                the raw data is suitable for further processing. Methods include:
2.1 Preprocessing of EEG signals                                                Butterworth bandpass filter, EMD, FFT, CWT, DWT, and CSP,
                                                                                which help deal with noise and artifacts. Additionally, a window
     Due to the inherent susceptibility of EEG signals to noise from            duration, overlapping and non-overlapping, can also be used to
artifacts and external sources, a robust preprocessing strategy is              reduce the effect of noise to achieve better results.

Frontiers in Medicine                                                     04                                                              frontiersin.org

Alkhrijah et al.                                                                                                       10.3389/fmed.2025.1566870


    FIGURE 3
    EEG data segmented into 15-s windows.


     We preprocessed EEG signals to remove noise and artifacts to
enhance signal quality, as shown in Figure 4. The wavelet transform
and Butterworth filter, a high-pass filter with a cutoff frequency
of 0.5 Hz and a low-pass filter with a cutoff frequency of 40 Hz,
were applied. These filters were used to remove low-frequency,
high-frequency drifts and fluctuations caused by internal and
external sources during data recording. Figure 5 illustrates the
raw signal alongside the denoised signals after applying these
filters. The EEG signals are acquired through multi-channel
recordings. Using a large set of channels leads to computational
complexity. Additionally, not all channels provide valuable insights
for seizure prediction. The use of all channels can also result
in misclassifications of seizures. To address these issues, channel
selection is a critical step in reducing the number of channels while
preserving essential information.
     The number of channels is not only reduced, but optimal
channels are also combined, which are highly contributing to
seizure prediction, to make a surrogate channel. The channels are               FIGURE 4

selected based on two criteria: high SQI and maximum variance.                  Raw vs. denoised EEG signals.

A higher SQI indicates superior signal quality, while lower values
suggest poorer quality. Higher variance suggests increased brain
activity. By selecting channels that meet these criteria, we ensure
that the most informative and relevant channels are retained,                of overfitting to noise rather than extracting meaningful patterns.
leading to more accurate and efficient seizure prediction. A                 Addressing this issue can not only increase the performance of the
combined plot of all five selected channels is presented in Figure 6.        classifier but also reduce the computational complexity. To convert
                                                                             multiple EEG channels into a surrogate channel, an averaging filter,
                                                                             CSP, and an optimal spatial filter were applied. These techniques
                                        k
                                     1X                                      were applied to increase the signal-to-noise ratio (SNR) and
                        Vict (C) =      (xc (i) − µc ))2         (1)
                                     k                                       variance interval between two classes. The averaging filter is a
                                       i=1
                                                                             method used to increase the SNR by replacing each sample with
                                                                             the average value of neighboring samples within a defined window.
                                         
                   Selected Channel = max Vict(c)                (2)         This averaging filter calculates the mean of all the channels to
                                             1:N
                                                                             form a single channel (surrogate channel). The surrogate channel
                                                                             obtained after applying an averaging filter contains more SNR
                                                                             than multiple channels. The surrogate channel aims to capture the
2.1.1 Surrogate channel                                                      collective signal from multiple electrodes, potentially improving
    Given the computational inefficiency caused by analyzing                 interpretability and simplifying analysis.
high-dimensional EEG data from multiple channels, we introduce                    Despite its effectiveness in noise reduction, residual noise may
a surrogate channel technique. Unlike previous methods that                  persist in the surrogate channel, necessitating further refinement
typically analyze all channels equally, our approach identifies              or the consideration of complementary filtering techniques to
and combines the most informative EEG channels into a                        optimize signal quality for further analysis. The CSP filter is a
single surrogate channel, significantly reducing computational               technique that is frequently used in EEG signal processing to
complexity while maintaining prediction accuracy. High-                      enhance the discriminative features of EEG signals by spatially
dimensional EEG signals pose significant problems in EEG                     filtering them. The CSP algorithm identifies spatial filters that
analysis, including increased computational cost and a higher risk           increase the variance of EEG signals for one class while minimizing


Frontiers in Medicine                                                   05                                                          frontiersin.org

Alkhrijah et al.                                                                                                       10.3389/fmed.2025.1566870


    FIGURE 5
    Five EEG channel waveforms before and after noise removal.


    FIGURE 6
    Waveforms of selected optimal EEG channels.


it for another class. CSP not only increases the SNR but also                (non-seizure states), potentially biasing prediction models.
enhances the variance interval between two or more classes. This             To address this imbalance, we utilize advanced oversampling
suggests that relevant information becomes more distinct while               techniques. Imbalanced data refers to too many instances in one
noise is effectively suppressed. In essence, CSP can convert a multi-        class and too few examples in another. Imbalanced data can
channel EEG signal into a surrogate channel that encapsulates the            highly affect the model’s overall effectiveness and make it difficult
most discriminative features for the task at hand.                           for the model to distinguish between the decision boundaries
                                                                             of different classes. One of the solutions to deal with this is to
                                                                             over-sample the instances in the minority class. Over-sampling
2.1.2 Mitigating the class imbalance problem                                 can be attained by simply duplicating instances from the minority
   Class imbalance is a critical challenge in EEG-based seizure              class in the training dataset before fitting a model. This does not
prediction because the number of preictal segments (indicating               give any extra information to the model, but it can deal with the
impending seizures) is significantly fewer than interictal segments          data imbalance issue. An enhancement on duplicating instances


Frontiers in Medicine                                                   06                                                          frontiersin.org

Alkhrijah et al.                                                                                                           10.3389/fmed.2025.1566870


    FIGURE 7
    Comparison of original and SMOTE-generated EEG signals for the minority class.


from the minority class is to synthesize new instances from                    critical step in the prediction of epileptic seizures. To capture both
the minority class. In this study, data splitting was performed                interpretable signal characteristics and complex spatial-temporal
after an initial oversampling process to address class imbalance               dependencies, we adopted a hybrid feature extraction strategy.
and improve model performance. Specifically, we utilized the                   Handcrafted features such as Hjorth parameters and entropy
synthetic minority over-sampling technique (SMOTE) and the soft                measures are well-established in EEG analysis for their ability to
prototype instance discrimination for enhancing representation                 reflect signal complexity and variance.
(SPIDER) techniques to generate additional synthetic samples and
improve the representation of minority classes. SMOTE selects
a minority class instance randomly and then finds its k nearest                2.2.1 Handcrafted features
minority class neighbors.                                                          Various techniques for feature extraction are presented in
    The synthetic instances are then generated as a convex                     the literature, including both handcrafted and automatic feature
combination of the selected instances. SPIDER works by producing               extraction methods. ML techniques are commonly used for
synthetic samples for the minority class in accordance with                    handcrafted feature extraction, while DL is well-suited for
prototype instances. Prototype instances are representative samples            automatic feature extraction. After a comprehensive literature
from the minority class that capture its characteristics. SPIDER               review, we identified features that provide better inter-class
synthesizes new instances by perturbing these prototypes, creating             separability. Inter-class separability refers to the measure that
variations that are still representative of the minority class. After          how two classes are distant, different, or separable from one
applying these oversampling methods, the dataset was partitioned               another. The higher the inter-class separability, the easier it
into training and validation subsets. Figure 7 presents a visual               is for the classifier to distinguish and classify the classes.
comparison between an original EEG segment and a synthetic                     Conversely, the lower the inter-class separability, the more
sample generated using the SMOTE. The synthetic EEG maintains                  challenging for the classifier to distinguish between the classes,
the temporal rhythm and amplitude range of the original signal,                because lower inter-class separability indicates that the classes
with minor variations that reflect the data-driven interpolation               are overlapping significantly. Temporal and spectral features
characteristics of SMOTE. To assess the fidelity of the generated              can be identified and extracted, revealing significant patterns
samples, we evaluated similarity using statistical metrics such as             within the EEG signal. Following preprocessing and channel
Pearson correlation and dynamic time warping (DTW), both of                    selection, the temporal features were extracted including min,
which confirmed a high degree of alignment between the original                max, mean (Equation 3), variance (Equation 4), standard deviation
and synthetic signals. This validates the suitability of SMOTE for             (Equation 5) and skewness (Equation 6). The mean represented as
augmenting the minority class in EEG-based classification tasks                µ, is calculated as follows:
without introducing unrealistic distortions.                                                                          K
                                                                                                               1 X
                                                                                                          µ=       (xi )                          (3)
                                                                                                               K
                                                                                                                     i=1

2.2 Feature extraction from EEG signals                                                                          K
                                                                                                             1 X
                                                                                                      σ2 =       (xi − µ)2                        (4)
    Effective feature extraction is crucial to distinguish between                                           K
                                                                                                                i=1
seizure states clearly. Thus, we combine handcrafted temporal
and spectral features with automated DL-based features to ensure                                        v
                                                                                                        u   K
                                                                                                        u1 X
high inter-class separability, which is key for robust classification.                               σ =t     (xi − µ)2                           (5)
After preprocessing and channel selection, feature extraction is a                                        K
                                                                                                                 i=1


Frontiers in Medicine                                                     07                                                           frontiersin.org

Alkhrijah et al.                                                                                                                                  10.3389/fmed.2025.1566870


TABLE 1 Statistical and spectral features extracted from 10 EEG segments of preictal state.


  Feature                              Seg1       Seg2        Seg3        Seg4            Seg5          Seg6              Seg7             Seg8           Seg9          Seg10
  Min                                  -0.00013   -0.00013   -0.00025     -0.00016       -9.75E-05      -0.00010      -8.15E-05          -7.33E-05       -0.00017       -0.00012

  Max                                  0.00010    0.00013    0.00022      8.22E-05       9.20E-05       8.46E-05      6.58E-05            7.29E-05       9.24E-05        0.00014

  Mean                              -7.13E-08     1.20E-06   -1.16E-06    5.84E-07       1.38E-07       4.44E-07      -4.14E-07           5.12E-07       -4.70E-08      9.59E-07

  Variance                             9.17E-10   1.09E-09   3.57E-09     6.31E-10       6.65E-10       5.29E-10      3.81E-10            4.52E-10       8.28E-10       1.26E-09

  Standard deviation                   3.03E-05   3.30E-05   5.98E-05     2.51E-05       2.58E-05       2.30E-05      1.95E-05            2.13E-05       2.88E-05       3.56E-05

  Skewness                              -0.191     -0.166     -0.198       -1.230         -0.269         -0.271           -0.162           -0.182         -1.007          0.120

  Spectral centroid                     5.794      5.090       7.621       5.550           5.365         6.426            7.066             6.591          4.529          4.653

  Spectral variance                     36.896     45.557    293.917       55.709         47.305         58.932           67.889           59.246         38.331         32.890

  Spectral skewness                     4.079      6.505       4.177       5.755           5.441         4.426            4.580             3.972          5.160          4.747


TABLE 2 Statistical and spectral features extracted from 10 EEG segments of interictal state.


  Feature                              Seg1       Seg2       Seg3         Seg4            Seg5          Seg6              Seg7             Seg8           Seg9          Seg10
  Min                                  -0.00062   -0.00083   -0.00075    -0.00075        -0.00046       -0.00015      -0.000078           -0.00063       -0.00062        -0.00070

  Max                                  0.00074    0.00084    0.00080      0.00064        0.00065        0.00011       0.000099            0.00058         0.00062        0.00069

  Mean                              -1.98E-07     3.82E-07   2.00E-06    -1.94E-08       -1.29E-06      1.07E-06      1.19E-07           -8.82E-08       -3.99E-07      -5.19E-07

  Variance                             1.17E-08   2.06E-08   3.38E-08    2.30E-08        1.02E-08       6.95E-10      5.15E-10            7.89E-09       1.79E-08        1.56E-08

  Standard deviation                   1.08E-04   1.44E-04   1.84E-04    1.52E-04        1.01E-04       2.64E-05      2.27E-05            8.88E-05       1.34E-04        1.25E-04

  Skewness                              0.966      -0.168     0.359       -0.135           0.663         -0.599           0.283            -0.238          0.433          0.108

  Spectral centroid                     20.206     22.993     12.441      15.491           6.892         11.051           9.771            18.497         15.589          19.211

  Spectral variance                    478.771    509.770    358.245      442.970        248.950        393.654       265.381             458.774         447.203        477.597

  Spectral skewness                     1.527      1.447      2.345        2.012           4.128         2.770            2.881             1.663          2.019          1.718


                                                                                    is calculated as:
                                   K
                             1 X                                                                                          Z ∞
                          S=    (xi − µ)3                                (6)
                             K                                                                             Sx (t) =                Rx (τ ).e−2πif τ df                        (8)
                                  i=1                                                                                      −∞

     where, µ is EEG signal mean, xi is value of the EEG signal at                      Spectral features are frequency domain features, that include
ith sample, K is number of samples in EEG signals. Variance is the                  spectral centroid, variational coefficient, and spectral skewness.
measurement value used to show how far a set of numbers is spread                   These features can be computed with the help of PSD, which is
with respect to the mean or average value. σ 2 is variance of EEG                   computed by Equation 8. where, Rx (τ ) denotes autocorrelation
signals. Standard deviation is a measure representing the amount                    of the signal x(t). Spectral centroid, variational coefficient, and
of how much dispersed or variation, such as spread, dispersion is in                spectral skewness can be computed by following equations.
the data from the mean. σ is the standard deviation of EEG signals.
Skewness is a measure of asymmetry of the distribution around the                                                         P
                                                                                                                             tSx (t)
mean. It shows in which direction the data is skewed.                                                                Cs = Pt                                                  (9)
                                                                                                                            t Sx (t)
     The spectral analysis of EEG signals is commonly done
by obtaining the PSD. PSD is a Fourier transform of the
                                                                                                                          P
autocorrelation function (Equation 7). PSD and auto-correlation                                                               t (t − Cs ) Sx (t)
                                                                                                                  σs2 =            P                                         (10)
are very closely related to each other in the analysis of signals and                                                                  t Sx (t)
time series. The auto-correlation function can be calculated as:
                                                                                                                     P
                                                                                                                          t ((t − Cs )/σs ) Sx (t)
                                                                                                            βs =                  P                                          (11)
                        Rx (τ ) = E[x(t).x(t + τ )]                      (7)                                                          t Sx (t)

                                                                                        Tables 1, 2 present the statistical and spectral features extracted
where, x(t) is EEG signal sample, E is expected or mean value.                      from 10 EEG segments corresponding to the preictal and interictal
    PSD describes the distribution of power over frequency and                      states, respectively. Each table lists features such as minimum,
may be computed with the Fourier transform or the distribution                      maximum, mean, variance, standard deviation, skewness, spectral
of mean power of a signal in the frequency domain (26). The PSD                     centroid, spectral variance, and spectral skewness for each segment.


Frontiers in Medicine                                                          08                                                                                  frontiersin.org

Alkhrijah et al.                                                                                                             10.3389/fmed.2025.1566870


    FIGURE 8
    Proposed customized architecture of 1DCNN.


                                                                               TABLE 3 Proposed architecture of 1DCNN with list of parameters.
This layout allows for segment-wise analysis of feature variation
within each class and supports comparative evaluation between
                                                                                Layer type                       Output Shape          Parameters
preictal and interictal brain states, offering valuable insights into
the distinguishing characteristics relevant for seizure prediction.             Conv1D                           (None, 5,118, 32)          608

                                                                                Batch normalization              (None, 5,118, 32)          128

                                                                                Leaky ReLU                       (None, 5,118, 32)           0
2.2.2 Customized 1DCNN for automated feature                                    Max pooling 1D                   (None, 2,559, 32)           0
extraction
                                                                                Conv1D                           (None, 2,557, 64)          6,208
     CNN is extensively utilized for EEG feature extraction and
classification tasks due to its ability to automatically learn spatial          Leaky ReLU                       (None, 2,557, 64)           0
patterns within the data. For automated features, we implemented                Max pooling 1D                   (None, 1,278, 64)           0
1DCNN following the preprocessing of EEG signals, which
                                                                                Dropout                          (None, 1,278, 64)           0
includes channel selection and data segmentation. Our proposed
1DCNN is composed of several distinct layers, designed to apply                 Conv1D                           (None, 1,276, 128)        24,704
filters that identify essential patterns within the EEG signal. These           Leaky ReLU                       (None, 1,276, 128)          0
layers are followed by activation functions and pooling layers.
                                                                                Average pooling 1D               (None, 638, 128)            0
The activation function adds non-linearity to the network, which
allows the network to learn complex patterns and relationships                  Dropout                          (None, 638, 128)            0

within the data and can highly reduce the dimensionality while                  Conv1D                           (None, 636, 256)          98,560
keeping the critical information. The output of the extracted
                                                                                Leaky ReLU                       (None, 636, 256)            0
features was flattened and passed through fully connected layers
for classification of interictal and preictal states. The feature-level         Average pooling 1D               (None, 318, 256)            0

fusion of handcrafted and automated features was also performed                 Conv1D                           (None, 316, 512)          393,728
before passing them to the dense layer.                                         Leaky ReLU                       (None, 316, 512)            0
     Figure 8 presents the visual description of the proposed
                                                                                Global average pooling 1D        (None, 512)                 0
architecture of customized 1DCNN, whereas, detailed list of
parameters is listed in Table 3. It begins with a Conv1D layer                  Dense                            (None, 1)                  513
featuring 32 filters of size 3, followed by batch normalization
and Leaky ReLu activation to stabilize the training and add non-
linearity. After that MaxPool1D layer is added for down-sampling.
                                                                               CNN architecture is 524,449. Figure 9 illustrates the distribution of
The network succeeded with several additional convolutional
                                                                               interictal and preictal EEG segments based on 1DCNN-extracted
layers: 64 filters of size 3, 128 and 256 filters of size 3, each
                                                                               features.
followed by ReLu activation. Average pooling is applied after the
third and fourth convolutional layers to reduce dimensionality with
0.5 dropout layers to mitigate overfitting. The final convolutional
layer uses 512 filters, followed by a one-dimensional global                   2.3 Classiﬁcation of EEG signals
average pooling layer that aggregates the features. The architecture
concludes with a dense layer with an ensemble classifier for binary                Once a comprehensive feature vector is extracted, preictal and
classification. The total number of trainable parameters in this               interictal class samples are then classified. Given the complex


Frontiers in Medicine                                                     09                                                             frontiersin.org

Alkhrijah et al.                                                                                                              10.3389/fmed.2025.1566870


    FIGURE 9
    Scatter plot of 1DCNN features showing the distribution of interictal and preictal EEG segments.


     Require: Training dataset D = {(xi , yi )}ni=1 , base                        to enhance prediction robustness and generalizability. We propose
          classifiers {C1 , C2 , . . . , Cm }, meta-learner M                     a novel ensemble meta learner classifier with base classifiers
     Ensure: Final prediction ŷ                                                  including SVM, RF, and LSTM to perform classification between
     1: Split D into Dtrain and Dmeta for training base                           preictal and interictal classes. We used a radial basis function (RBF)
          classifiers and meta-learner respectively.                              kernel in SVM due to the non-linear data, which was selected
     2: for each base classifier Ck in {C1 , C2 , . . . , Cm } do                 empirically. Similarly, in the case of RF, we selected 150 trees after
     3:      Train Ck on Dtrain                                                   experimentation. In case of LSTM, 32 repeating units were used,
     4: end for                                                                   followed by meta learning classifier described in Algorithm 1.
     5: Initialize meta-training dataset Dmeta_train ← ∅
     6: for each (xj , yj ) in Dmeta do
     7:      Obtain predictions {p1 , p2 , . . . , pm } from                      3 Results and discussion
             {C1 , C2 , . . . , Cm } on xj
     8:      Form meta-instance zj = [p1 , p2 , . . . , pm ]                          We performed multiple experiments on the CHB-MIT dataset
     9:      Add (zj , yj ) to Dmeta_train                                        and evaluated the methods based on accuracy, sensitivity, and
     10: end for                                                                  specificity. Python 3 and MATLAB were used on a Windows
     11: Train meta-learner M on Dmeta_train                                      11 system for the implementation. The experiments for epileptic
     12: Prediction Phase:                                                        seizure prediction are performed on NVIDIA GeForce RTX
     13: Given a new instance x:                                                  3,090 and 64 GB of RAM. All the implementations were done
     14: Obtain predictions {p1 , p2 , . . . , pm } from                          using Tensorflow and Scikit-learn for seizure classification. Table 4
          {C1 , C2 , . . . , Cm } on x                                            presents the results of the ablation study performed. Figure 10
     15: Form meta-instance z = [p1 , p2 , . . . , pm ]                           presents the confusion matrices of all experiments. We performed
     16: Use M to predict ŷ from z                                               multiple experiments by varying approaches in preprocessing,
     17: return         ŷ                                                        feature extraction, and classification. In the first experimental setup,
                                                                                  we selected a non-overlapping window and extracted temporal
                                                                                  and spectral features, and performed classification using a kNN
Algorithm 1. Meta-learner ensemble classiﬁer.
                                                                                  classifier. With this experimental setup, we achieved an accuracy
                                                                                  of 71.65%, sensitivity and specificity of 53.27% and 78.08%,
                                                                                  respectively. Preprocessing and feature extraction were kept the
nature of EEG signals and subtle differences between seizure states,              same in experiments 2 and 3, whereas RF and SVM classifiers
relying on a single classifier can limit predictive performance.                  were used for classification between preictal and interictal states.
Hence, we propose an ensemble approach combining diverse                          SVM achieved an accuracy of 78.15% which was more than 4%
classifiers (SVM, RF, and LSTM) through a meta-learning strategy                  increased compared to RF. Similarly, CNN and LSTM were used for


Frontiers in Medicine                                                        10                                                             frontiersin.org

Alkhrijah et al.                                                                                                                            10.3389/fmed.2025.1566870


TABLE 4 Results obtained after performing an ablation study on the CHB-MIT dataset for epileptic seizure prediction.


  Preprocessing                          Feature                      Classiﬁcation         Accuracy         Sensitivity     Speciﬁcity      MCC       AUC-ROC
                                         extraction                                            (%)              (%)             (%)
  Non-overlapping window                 Handcrafted features         KNN                        71.65           53.27           78.08       0.2997       0.6568

  Non-overlapping window                 Handcrafted features         RF                         73.26           59.50           78.08       0.3541       0.6879

  Non-overlapping window                 Handcrafted features         SVM                        78.15           65.89           82.44       0.4618       0.7417

  Non-overlapping window                 Handcrafted features         CNN                        77.02           63.71           81.68       0.4337       0.7269

  Non-overlapping window                 Handcrafted features         LSTM                       80.01           67.91           84.24       0.5023       0.7608

  Non-overlapping window,                Handcrafted features         SVM                        82.47           70.56           86.64       0.5572       0.7860
  Butter-worth filter

  Non-overlapping window,                Handcrafted features         SVM                        84.09           72.90           88.00       0.5958       0.8032
  Butter-worth filter, Wavelet
  transform

  Non-overlapping window,                Handcrafted features         SVM                        86.67           76.48           90.24       0.6581       0.8336
  Butter-worth filter, Wavelet
  and Fourier transform

  Non-overlapping window,                Handcrafted features         SVM                        88.77           79.60           91.98       0.7101       0.8579
  Butter-worth filter, Wavelet
  and Fourier transform,
  channel selection

  Non-overlapping window,                1DCNN                        SVM                        90.47           82.40           93.29       0.7532       0.8775
  Butter-worth filter, Wavelet
  and Fourier transform,
  channel selection

  Non-overlapping window,                Handcrafted features         SVM                        92.61           86.14           94.87       0.8081       0.9051
  Butter-worth filter, Wavelet
  and Fourier transform,
  surrogate channel

  Non-overlapping window,                1DCNN                        SVM                        95.40           91.74           96.67       0.8806       0.9420
  Butter-worth filter, Wavelet
  and Fourier transform,
  surrogate channel

  Non-overlapping window,                Handcrafted and              SVM                        97.01           94.86           97.76       0.9225       0.9621
  Butter-worth filter, Wavelet           1DCNN feature
  and Fourier transform,                 fusion
  surrogate channel

  Non-overlapping window,                Handcrafted and              Ensemble classifier        99.52           99.22           99.62        0.97        0.9970
  Butter-worth filter, Wavelet           1DCNN feature
  and Fourier transform,                 fusion
  surrogate channel
Bold entries represent the highest achieved results of each metric.


classification with the same preprocessing and feature extraction,                               effectiveness in prior seizure prediction research and its suitability
and LSTM outperformed CNN in terms of all three performance                                      for real-time implementation. However, we acknowledge that
measures.                                                                                        such static segmentation may result in the loss of critical
    Effective preprocessing plays an important role in the accurate                              information, particularly near transitional states such as the
prediction of epileptic seizures using EEG signals. Therefore, a                                 onset or termination of seizures. These transitions often contain
Butterworth bandpass filter was applied to remove noise from EEG                                 subtle but clinically significant changes that may not be fully
signals, whereas feature extraction and classification were kept the                             captured within rigid window boundaries. To enhance temporal
same, and an increased accuracy of 84.07% was observed. In the                                   sensitivity, future extensions of this work could incorporate
next experiments, preprocessing was further enhanced by applying                                 overlapping windows or adaptive windowing strategies that
the wavelet transform along with the Butterworth filter to increase                              dynamically adjust based on signal characteristics such as variance,
the SNR, and it resulted in increased accuracy, sensitivity, and                                 entropy, or frequency shifts. Such approaches have the potential
specificity. Similarly, the Fourier transform was also applied in                                to capture transitional dynamics more effectively, improving
addition to the Butterworth filter and wavelet transform, and the                                both the responsiveness and predictive accuracy of seizure
results were promising.                                                                          detection systems.
    The choice of a fixed, non-overlapping 15-s window for                                           To assess the computational efficiency of the proposed
EEG segmentation in our study was guided by its demonstrated                                     framework, we evaluated the complete pipeline comprising


Frontiers in Medicine                                                                       11                                                           frontiersin.org

Alkhrijah et al.                                            10.3389/fmed.2025.1566870


    FIGURE 10
    Confusion matrices of all experiments performed.


Frontiers in Medicine                                  12               frontiersin.org

Alkhrijah et al.                                                                                                          10.3389/fmed.2025.1566870


    FIGURE 11
    Training and validation performance curves of the proposed model over 50 epochs.


    FIGURE 12
    Receiver operating characteristic curve of the proposed method of epileptic seizure prediction.


preprocessing, feature extraction, and ensemble-based                             SciPy, and PyWavelets. The peak memory usage remained
classification on a high-performance system equipped with                         well within the hardware limits, ensuring that the proposed
an NVIDIA GeForce RTX 3090 and 64 GB of RAM. With GPU                             approach is suitable for real-time or near real-time deployment in
acceleration, the average processing time per 15-s EEG segment                    high-throughput clinical environments.
was approximately 0.12 s. This includes Butterworth filtering,                        An important aspect in real-time seizure prediction is the
wavelet and Fourier-based feature extraction, spatial filtering, and              time taken to classify the test sample. EEG signals have high
ensemble inference. The 1DCNN module benefited significantly                      dimensionality due to the number of channels. It is extremely
from GPU parallelism using PyTorch, while classical models such                   important to either reduce the number of channels by performing
as RF and SVM, as well as handcrafted feature operations, were                    a channel selection method or by combining all channels to form
efficiently handled on the CPU. All modules were implemented                      a single surrogate channel. It was observed that the surrogate
using optimized scientific computing libraries, including PyTorch,                channel using an optimized spatial filter outperformed channel


Frontiers in Medicine                                                        13                                                        frontiersin.org

Alkhrijah et al.                                                                                                           10.3389/fmed.2025.1566870


selection. It is extremely important to extract a feature vector with           and max pooling. A Leaky ReLU with the value of 0.01 has
high interclass variance and low intraclass variance. Therefore,                been used to avoid the problem of vanishing gradients. In
we propose a customized architecture of 1DCNN that consists                     this research, a comprehensive feature vector is formed by
of five convolutional layers followed by batch normalization                    concatenating the handcrafted, and features extracted using a
                                                                                customized 1DCNN. We also propose an ensemble classifier that
                                                                                uses MAML with three base classifiers, including SVM, RF, and
TABLE 5 Comparison of results achieved by proposed method with                  LSTM. We used k-fold cross validation and were able to achieve
state-of-the-art existing methods.
                                                                                an accuracy of 99.52% along with sensitivity of 99.22% and
  Authors                     Accuracy       Sensitivity    Speciﬁcity          specificity of 99.62%, with standard deviation of 0.53, 0.61, and 0.59,
                              (%)            (%)            (%)                 respectively.
  Birjandtalab et al. (3)     95             96.27          Not reported             To further validate the robustness of the proposed model,
                                                                                we computed the Matthews correlation coefficient (MCC) and
  Birjandtalab et al. (4)     Not reported   89.80          Not reported
                                                                                the area under the receiver operating characteristic curve (AUC-
  Alotaiby et al. (5)         Not reported   89             37                  ROC). The ensemble classifier achieved an MCC score of 0.99,
  Fei et al. (6)              89.67          89.50          89.75               reflecting a strong correlation between predicted and actual class
                                                                                labels even in the presence of class imbalance. Furthermore,
  Cogan et al. (7)            86             100            73
                                                                                the AUC-ROC score of 0.997 confirms the high discriminative
  Cho et al. (8)              80.74          80.54          80.50               power of the proposed model in distinguishing between preictal
  Jana et al. (9)             90.66          97             95.87               and interictal states. Figure 11 shows the ROC curve of the
                                                                                proposed method. To evaluate the learning behavior and check
  Daoud and Bayoumi (10)      99.60          99.72          99.6
                                                                                for overfitting, we plotted the training and validation accuracy
  Asharindavida et al. (11)   82.7           Not reported   Not reported
                                                                                and loss curves, as shown in Figure 12. Table 5 compares the
  Borhade et al. (12)         96.54          96.52          97.53               performance of our proposed method with recent state-of-the-
  Zhang et al. (13)           89.98          92.9           87.04
                                                                                art methods proposed by researchers on the same dataset, and
                                                                                it shows that the proposed method outperforms not only in
  Usman et al. (14)           Not reported   92.7           90.8
                                                                                terms of accuracy, sensitivity, and specificity but also uses less
  Tamanna et al. (15)         96.38          76.73          83.16               computational power due to reduced dimensionality. Although
  Jana and Mukherjee (16)     99.47          97.83          92.35               the proposed model achieves a low false positive rate during
                                                                                evaluation, its practical implications must be considered in
  Jemal et al. (17)           90.9           96.1           84.6
                                                                                continuous monitoring scenarios. Even a few false alarms per
  Koutsouvelis et al. (19)    97.32          99.31          95.34               day can lead to alarm fatigue, reduced trust in the system, and
  Quadri et al. (34)          98.3           97.63          Not reported        clinical inefficiencies. In real-world deployment, such issues could
                                                                                be mitigated by incorporating post-processing techniques such
  Proposed method             99.47          97.83          92.35
                                                                                as temporal smoothing, majority voting across time windows, or


    FIGURE 13
    SHAP summary plot showing the impact of top handcrafted EEG features on the output of the proposed ensemble model.


Frontiers in Medicine                                                      14                                                            frontiersin.org

Alkhrijah et al.                                                                                                        10.3389/fmed.2025.1566870


hybrid decision systems that validate alerts through additional               Author contributions
signals. These enhancements would further improve the practical
viability of the proposed method in continuous, long-term                         YA: Conceptualization, Data curation, Formal analysis,
monitoring contexts.                                                          Funding acquisition, Methodology, Project administration,
    To ensure transparency in model decision-making, we applied               Resources, Supervision, Writing – review & editing. SK:
Shapley additive explanations (SHAP) to interpret the influence of            Conceptualization, Data curation, Formal analysis, Methodology,
individual handcrafted features on the predicted seizure class. As            Writing – original draft. SU: Conceptualization, Data curation,
shown in Figure 13, features like min, max, and mean had the most             Formal analysis, Funding acquisition, Methodology, Project
significant positive impact on the model’s output. The direction and          administration, Resources, Supervision, Writing – review &
magnitude of each feature’s contribution can be observed from the             editing. AJ: Investigation, Software, Validation, Visualization,
horizontal spread of SHAP values. For instance, high values of max            Writing – original draft. MZ: Funding acquisition, Investigation,
and mean features (indicated in red) consistently push the model              Project administration, Resources, Software, Supervision,
toward predicting the preictal state. This interpretability analysis          Validation, Visualization, Writing – original draft. HA:
enhances trust in the model’s outputs and provides useful insights            Conceptualization, Data curation, Formal analysis, Methodology,
for potential clinical validation.                                            Writing – original draft. AA: Funding acquisition, Investigation,
                                                                              Project administration, Resources, Software, Supervision,
                                                                              Validation, Visualization, Writing – review & editing. SA: Funding
4 Conclusion and future directions                                            acquisition, Investigation, Project administration, Resources,
                                                                              Software, Supervision, Validation, Visualization, Writing –
    In this research, we propose a novel method for the prediction            review & editing.
of epileptic seizures using scalp electroencephalographic (EEG)
signals. The proposed method consists of three steps, including
preprocessing, feature extraction, and classification. We propose             Funding
a robust preprocessing method that involves conversion of 23
channels into a single surrogate channel using an optimized                       The author(s) declare that financial support was received for the
spatial pattern filter to reduce the dimensionality, followed                 research and/or publication of this article. The authors extend their
by denoising using a Butterworth filter, wavelet, and Fourier                 appreciation to the King Salman center For Disability Research for
transform. We also propose a customized architecture of a one-                funding this work through Research Group no KSRG-2024-376.
dimensional convolutional neural network (1DCNN), which is
not only lightweight but also provides a feature vector with
high interclass variance. Both handcrafted and 1DCNN features                 Acknowledgments
are concatenated to form a feature vector, which is then fed
                                                                                  The authors extend their appreciation to the King Salman
into three classifiers, including support vector machines, random
                                                                              center For Disability Research for funding this work through
forest, long short-term memory, and a model-agnostic meta
                                                                              Research Group no KSRG-2024-376.
learner ensemble classifier. The proposed method performs better
compared to existing state-of-the-art methods in terms of accuracy,
sensitivity, and specificity, and is also computationally less complex
due to reduced dimensionality and a customized light-weight
                                                                              Conﬂict of interest
architecture. In the future, integrating other physiological signals,
                                                                                  The authors declare that the research was conducted in the
such as heart rate and blood oxygen levels, with EEG data
                                                                              absence of any commercial or financial relationships that could be
could provide a more comprehensive understanding of seizures
                                                                              construed as a potential conflict of interest.
before onset. The proposed method can also be applied in
real-time analysis of epileptic seizures. As part of future work,
we plan to develop a lightweight graphical user interface to                  Generative AI statement
facilitate user interaction with the proposed model. This interface
will enable real-time EEG data input, feature visualization, and                  The author(s) declare that no Gen AI was used in the creation
display of model predictions and performance metrics, thereby                 of this manuscript.
enhancing the practical applicability of the system in clinical or
research environments.
                                                                              Publisher’s note
Data availability statement                                                       All claims expressed in this article are solely those of the
                                                                              authors and do not necessarily represent those of their affiliated
    Publicly available datasets were analyzed in this study. This             organizations, or those of the publisher, the editors and the
data can be found at: Direct Data Link: https://physionet.org/                reviewers. Any product that may be evaluated in this article, or
content/chbmit/1.0.0/, Repository: PhysioNet, DOI: https://doi.               claim that may be made by its manufacturer, is not guaranteed or
org/10.13026/C2K01R.                                                          endorsed by the publisher.


Frontiers in Medicine                                                    15                                                          frontiersin.org

Alkhrijah et al.                                                                                                                                        10.3389/fmed.2025.1566870


References
  1. Mormann F, Andrzejak RG, Elger CE, Lehnertz K. Seizure prediction: the long                     19. Koutsouvelis P, Chybowski B, Gonzalez-Sulser A, Abdullateef S, Escudero J.
and winding road. Brain. (2007) 130:314–33. doi: 10.1093/brain/awl241                              Preictal period optimization for deep learning-based epileptic seizure prediction. J
                                                                                                   Neural Eng. (2024) 21:ad9ad0. doi: 10.1088/1741-2552/ad9ad0
  2. Pitton Rissardo J, Fornari Caprara AL, Casares M, Skinner HJ, Hamid U.
Antiseizure medication-induced alopecia: a literature review. Medicines. (2023) 10:35.               20. Wang Y, Long X, Van Dijk H, Aarts R, Arends J. Adaptive EEG channel
doi: 10.3390/medicines10060035                                                                     selection for nonconvulsive seizure analysis. In: 2018 IEEE 23rd International
                                                                                                   Conference on Digital Signal Processing (DSP). Shanghai: IEEE (2018). p. 1–5.
  3. Birjandtalab J, Heydarzadeh M, Nourani M. Automated EEG-based epileptic
                                                                                                   doi: 10.1109/ICDSP.2018.8631844
seizure detection using deep neural networks. In: 2017 IEEE International Conference
on Healthcare Informatics (ICHI). IEEE (2017). p. 552–5. doi: 10.1109/ICHI.2017.55                    21. Arif S, Munawar S, Marie RR, Shah SA. Leveraging wavelets and deep CNN for
                                                                                                   sleep pattern recognition in road safety: an EEG study. In: International Conference on
  4. Birjandtalab J, Pouyan MB, Cogan D, Nourani M, Harvey J. Automated seizure
                                                                                                   Recent Trends in Image Processing and Pattern Recognition. Springer: New York (2023).
detection using limited-channel EEG and non-linear dimension reduction. Comput
                                                                                                   p. 227–41. doi: 10.1007/978-3-031-53082-1_19
Biol Med. (2017) 82:49–58. doi: 10.1016/j.compbiomed.2017.01.011
                                                                                                     22. Truong ND, Nguyen AD, Kuhlmann L, Bonyadi MR, Yang J, Ippolito S,
  5. Alotaiby TN, Alshebeili SA, Alotaibi FM, Alrshoud SR. Epileptic seizure
                                                                                                   et al. Convolutional neural networks for seizure prediction using intracranial
prediction using CSP and LDA for scalp EEG signals. Comput Intell Neurosci. (2017)
                                                                                                   and scalp electroencephalogram. Neural Networks. (2018) 105:104–11.
2017:1240323. doi: 10.1155/2017/1240323
                                                                                                   doi: 10.1016/j.neunet.2018.04.018
  6. Fei K, Wang W, Yang Q, Tang S. Chaos feature study in fractional Fourier
                                                                                                     23. Duun-Henriksen J, Kjaer TW, Madsen RE, Remvig LS, Thomsen CE, Sorensen
domain for preictal prediction of epileptic seizure. Neurocomputing. (2017) 249:290–8.
                                                                                                   HBD. Channel selection for automatic seizure detection. Clin Neurophysiol. (2012)
doi: 10.1016/j.neucom.2017.04.019
                                                                                                   123:84–92. doi: 10.1016/j.clinph.2011.06.001
  7. Cogan D, Birjandtalab J, Nourani M, Harvey J, Nagaraddi V. Multi-biosignal
                                                                                                     24. Parvez MZ, Paul M. EEG signal classification using frequency band
analysis for epileptic seizure monitoring. Int J Neural Syst. (2017) 27:1650031.
                                                                                                   analysis towards epileptic seizure prediction. In: IEEE International conference
doi: 10.1142/S0129065716500313
                                                                                                   on Computer and Information Technology. IEEE: Bangladesh (2014). p. 126–130.
  8. Cho D, Min B, Kim J, Lee B. EEG-based prediction of epileptic seizures                        doi: 10.1109/ICCITechn.2014.6997315
using phase synchronization elicited from noise-assisted multivariate empirical
                                                                                                     25. Tsiouris KM, Pezoulas VC, Zervakis M, Konitsiotis S, Koutsouris DD,
mode decomposition. IEEE Trans Neural Syst Rehabil Eng. (2016) 25:1309–18.
                                                                                                   Fotiadis DI. A long short-term memory deep learning network for the
doi: 10.1109/TNSRE.2016.2618937
                                                                                                   prediction of epileptic seizures using EEG signals. Elsevier. (2018) 99:24–37.
  9. Jana R, Bhattacharyya S, Das S. Epileptic seizure prediction from EEG signals                 doi: 10.1016/j.compbiomed.2018.05.019
using DenseNet. In: 2019 IEEE Symposium Series on Computational Intelligence (SSCI).
                                                                                                     26. Arif S, Munawar S, Ali H. Driving drowsiness detection using spectral
Xiamen: IEEE (2019). p. 604–9. doi: 10.1109/SSCI44817.2019.9003059
                                                                                                   signatures of EEG-based neurophysiology. Front Physiol. (2023) 14:1–23.
  10. Daoud H, Bayoumi MA. Efficient epileptic seizure prediction based                            doi: 10.3389/fphys.2023.1153268
on deep learning. IEEE Trans Biomed Circuits Syst. (2019) 13:804–13.
                                                                                                     27. Alickovic E, Kevric J, Subasi A. Performance evaluation of empirical
doi: 10.1109/TBCAS.2019.2929053
                                                                                                   mode decomposition, discrete wavelet transform, and wavelet packed
  11. Asharindavida F, Shamim Hossain M, Thacham A, Khammari H, Ahmed I,                           decomposition for automated epileptic seizure detection and prediction.
Alraddady F, et al. A forecasting tool for prediction of epileptic seizures using a machine        Biomed Signal Process Control. (2018) 39:94–102. doi: 10.1016/j.bspc.2017.
learning approach. Wiley Online Library. (2020) 32:e5111. doi: 10.1002/cpe.5111                    07.022
  12. Borhade RR, Nagmode MS. Modified atom search optimization-based deep                           28. Dong Q, Zhang H, Xiao J, Sun J. Multi-scale spatio-temporal attention network
recurrent neural network for epileptic seizure prediction using electroencephalogram               for epileptic seizure prediction. IEEE J Biomed Health Inform. (2025) 29:4784–95.
signals. Biocybern Biomed Eng. (2020) 40:1638–53. doi: 10.1016/j.bbe.2020.10.001                   doi: 10.1109/JBHI.2025.3545265
   13. Zhang S, Chen D, Ranjan R, Ke H, Tang Y, Zomaya AY, et al. A lightweight                      29. Alasiry A, Sampedro GA, Almadhor A, Juanatas RA, Alsubai S,
solution to epileptic seizure prediction based on EEG synchronization measurement.                 Karovic V. Epileptic seizures diagnosis and prognosis from EEG signals using
J Supercomput. (2021) 77:3914–32. doi: 10.1007/s11227-020-03426-4                                  heterogeneous graph neural network. PeerJ Computer Science. (2025) 11:e2765.
                                                                                                   doi: 10.7717/peerj-cs.2765
  14. Usman SM, Khalid S, Aslam MH. Epileptic seizures prediction
using deep learning techniques. IEEE Access. (2020) 8:39998–40007.                                   30. Cao X, Zheng S, Zhang J, Chen W, Du G. A hybrid CNN-Bi-
doi: 10.1109/ACCESS.2020.2976866                                                                   LSTM model with feature fusion for accurate epilepsy seizure detection.
                                                                                                   BMC Med Inform Decis Mak. (2025) 25:6. doi: 10.1186/s12911-024-02
  15. Tamanna T, Rahman MA, Sultana S, Haque MH, Parvez MZ. Predicting seizure
                                                                                                   845-0
onset based on time-frequency analysis of EEG signals. Chaos, Solitons Fractals. (2021)
145:110796. doi: 10.1016/j.chaos.2021.110796                                                         31. Bajaj A, Sharma Vl. EEG-based epileptic seizure prediction using variants of the
                                                                                                   long short term memory algorithm. Int J Comput Inf Syst Ind Manag Appl. (2025)
  16. Jana R, Mukherjee I. Deep learning based efficient epileptic seizure prediction
                                                                                                   17:13–13. doi: 10.70917/ijcisim-2025-0001
with EEG channel optimization. Biomed Signal Process Control. (2021) 68:102767.
doi: 10.1016/j.bspc.2021.102767                                                                      32. Meng Y, Liu Y, Wang G, Song H, Zhang Y, Lu J, et al. M-NIG: mobile network
                                                                                                   information gain for EEG-based epileptic seizure prediction. Sci Rep. (2025) 15:15181.
  17. Jemal I, Mezghani N, Abou-Abbas L, Mitiche A. An interpretable deep
                                                                                                   doi: 10.1038/s41598-025-97696-8
learning classifier for epileptic seizure prediction using EEG data. IEEE Access. (2022)
10:60141–50. doi: 10.1109/ACCESS.2022.3176367                                                        33. PhysioNet. CHB-MIT EEG Database. (2024). Available online at: https://www.
                                                                                                   physionet.org/content/chbmit/1.0.0/ (Accessed August 29, 2024).
  18. Zarei A, Zhu B, Shoaran M. Enhancing epileptic seizure detection
with eeg feature embeddings. In: 2023 IEEE Biomedical Circuits and                                   34. Quadri ZF, Akhoon MS, Loan SA. Epileptic seizure prediction using stacked
Systems Conference (BioCAS). Toronto, ON: IEEE (2023). p. 1–5.                                     CNN-BiLSTM: a novel approach. IEEE Trans Artif Intellig. (2024) 5:5553–60.
doi: 10.1109/BioCAS58349.2023.10388670                                                             doi: 10.1109/TAI.2024.3410928


Frontiers in Medicine                                                                         16                                                                         frontiersin.org
```
