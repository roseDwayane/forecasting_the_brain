---
citation_key: "QuEtAl2026"
paper_id: "paper_134"
title: "A causal attention network with time frequency channel feature fusion for epileptic seizure prediction."
authors: "Yimin Qu; Songhui Rao; Ting Li; Ying Li; Yan Niu; Ruiyun Chang; Xianchuan Chen; Bin Wang"
year: 2026
doi: "10.1016/j.jneumeth.2025.110665"
source: "publisher-pdf (doi: 10.1016/j.jneumeth.2025.110665)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# A causal attention network with time frequency channel feature fusion for epileptic seizure prediction.

**Citation:** `QuEtAl2026` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1016/j.jneumeth.2025.110665](https://doi.org/10.1016/j.jneumeth.2025.110665)
**Source PDF:** `full_pdf/Yimin2026.pdf`

## Abstract

Epilepsy poses ongoing physical and mental threats and causes substantial economic burdens. Better seizure forecasting enables faster medical responses, improving patients' quality of life and lowering healthcare costs. Research mainly focuses on early forecasting within a short preictal window, often too brief for effective drug administration. A major challenge is that a longer preictal phase may resemble the interictal state, making differentiation difficult. We propose a causal attention network (CANet) with a longer interictal and preictal of 1 h and 2 h respectively as the research object. In the feature extraction, a dilated causal convolution network is employed to extract local features. Causal attention is innovatively incorporated into epilepsy prediction to capture global correlation features. The complementary integration of these two methods enhances feature extraction and enables a more precise distinction between interictal and preictal periods. A double-layer dynamic window algorithm is developed for seizure prediction. We evaluate the performance on Freiburg and CHB-MIT datasets. On the Freiburg dataset, the sensitivity(Sen) of the 1/2-hour preictal intervals was 100.00%/96.67%, with a false alarm rate per hour (FAR) of 0.0077/h/0.0472/h, and the average prediction time (APT) was 97.59 min. On the CHB-MIT dataset, we achieved Sen of 97.06%/92.31%, FAR of 0.0251/h/0.0666/h, and APT of 94.85 min, under the same conditions. Our approach outperforms most of the previous methods, and the intracranial EEG (Freiburg) can more effectively distinguish interictal and preictal periods than scalp EEG (CHB-MIT).

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Journal of Neuroscience Methods 428 (2026) 110665


                                                                    Contents lists available at ScienceDirect


                                                          Journal of Neuroscience Methods
                                                         journal homepage: www.elsevier.com/locate/jneumeth


A causal attention network with time frequency channel feature fusion for
epileptic seizure prediction
Yimin Qu a ,1 , Songhui Rao b ,1 , Ting Li a , Ying Li a , Yan Niu a , Ruiyun Chang a , Xianchuan Chen a ,
Bin Wang a ,∗
a
    College of Computer Science and Technology (College of Data Science), Taiyuan University of Technology, Taiyuan, China
b Genome Analysis Laboratory of the Ministry of Agriculture and Rural Affairs, Agricultural Genomics Institute at Shenzhen, Chinese Academy of Agricultural

Sciences, Shenzhen, China


ARTICLE                  INFO                              ABSTRACT

Keywords:                                                  Background: Epilepsy poses ongoing physical and mental threats and causes substantial economic burdens.
Seizure prediction                                         Better seizure forecasting enables faster medical responses, improving patients’ quality of life and lowering
EEG                                                        healthcare costs. Research mainly focuses on early forecasting within a short preictal window, often too brief
Causal attention network
                                                           for effective drug administration. A major challenge is that a longer preictal phase may resemble the interictal
Signal processing
                                                           state, making differentiation difficult.
Deep learning
                                                           New methods: We propose a causal attention network (CANet) with a longer interictal and preictal of 1 h
                                                           and 2 h respectively as the research object. In the feature extraction, a dilated causal convolution network
                                                           is employed to extract local features. Causal attention is innovatively incorporated into epilepsy prediction to
                                                           capture global correlation features. The complementary integration of these two methods enhances feature
                                                           extraction and enables a more precise distinction between interictal and preictal periods. A double-layer
                                                           dynamic window algorithm is developed for seizure prediction.
                                                           Results: We evaluate the performance on Freiburg and CHB-MIT datasets. On the Freiburg dataset, the
                                                           sensitivity(Sen) of the 1/2-hour preictal intervals was 100.00%/96.67%, with a false alarm rate per hour
                                                           (FAR) of 0.0077/h/0.0472/h, and the average prediction time (APT) was 97.59 min. On the CHB-MIT dataset,
                                                           we achieved Sen of 97.06%/92.31%, FAR of 0.0251/h/0.0666/h, and APT of 94.85 min, under the same
                                                           conditions.
                                                           Comparison with existing methods and conclusion: Our approach outperforms most of the previous
                                                           methods, and the intracranial EEG (Freiburg) can more effectively distinguish interictal and preictal periods
                                                           than scalp EEG (CHB-MIT).


1. Introduction                                                                                 2012). Rescue medications must achieve onset of action within 5 to
                                                                                                30 min to prevent progression to established status epilepticus; pro-
    Epilepsy is a long-term neurological condition resulting from ab-                           longed status epilepticus exceeding 30 min may result in cerebral dam-
normal electrical impulses in brain cells. It is defined by abrupt and                          age (Trinka et al., 2015; Glauser et al., 2016). Fast-acting antiepileptic
transient episodes. Its global prevalence ranges from 0.6% to 1%, with
                                                                                                drugs work within 30 min and are mainly benzodiazepines, which pose
a notable proportion unresponsive to antiepileptic medications (Dalic
and Cook, 2016; Kuhlmann et al., 2018). The condition lead to cogni-                            key risks of respiratory and circulatory depression. They should only be
tive decline, psychological issues, and significant economic burden due                         used in facilities with resuscitation capabilities (Brophy et al., 2012).
to frequent medical visits and long-term medication use (Fisher et al.,                         This underscoring the importance of maintenance antiepileptic drugs.
2000). Therefore, precise and prompt forecasting of epileptic seizures                          Most Maintenance antiepileptic drugs take more than 30 min to take
has received extensive attention and research worldwide.                                        effect, and some even need over an hour (Johannessen Landmark et al.,
    Administering antiepileptic medications promptly during the pre-                            2020; Meirinho et al., 2021; Patsalos et al., 2008). Recent research
ictal stage can significantly reduce the likelihood of seizure occur-                           primarily centers around short-term epilepsy forecasting. The Period
rence (Assali et al., 2023; Litt and Echauz, 2002; Tetzlaff and Senger,


     ∗ Corresponding author.
         E-mail address: wangbin01@tyut.edu.cn (B. Wang).
         Equal contributions to this article are considered as co-first authors.

https://doi.org/10.1016/j.jneumeth.2025.110665
Received 22 July 2025; Received in revised form 14 December 2025; Accepted 31 December 2025
Available online 7 January 2026
0165-0270/© 2025 Published by Elsevier B.V.

Y. Qu et al.                                                                                                    Journal of Neuroscience Methods 428 (2026) 110665


preceding seizure onset (SOP) is typically defined as half an hour or               • This is the first time introduces the Causal Attention Network to
one hour, while the APT generally falls below half an hour (Yuan et al.,              epilepsy seizure prediction. By building a global causal reasoning
2020; Assali et al., 2023; Pinto et al., 2021). A sufficiently long APT is            framework, the model captures deep-level correlations across EEG
necessary to enable patients and caregivers to implement preventive                   signals.
actions promptly (Li et al., 2021; Gao et al., 2023; Guo et al., 2023).             • The dilated causal Convolution Network is used to simultaneously
    Recent research findings a longer SOP and an extended APT sug-                    extract the time-domain features and spectral domain features,
gest promising prospects of providing epilepsy patients with more                     and cross-channel feature fusion eliminates noise interference
time for proactive intervention (Trinka et al., 2015; Bruno et al.,                   from a single channel.
2020; Hu et al., 2020). An alarm meter were created that can provide                • A double-layer dynamic window is used to evaluate false alarm
a warning period ranging from 5 to 960 min (with an average of                        errors and false positive rates, providing precise early warnings
114 ± 151 min) (Cook et al., 2013). An approach utilized multi-day                    for patients.
cycles captured through wearable technology were proposed to fore-
casting epileptic seizures (Xiong et al., 2023). These studies employed          2. Materials and methods
various methods to predict epileptic seizures within hours or days, and
the experimental outcomes confirmed that it is possible to forecast              2.1. Data description
epileptic seizures across extended periods. However, the challenge of
accurately distinguishing between longer pre-seizure and inter-seizure               We evaluated our proposed CANet through comprehensive experi-
phases has led to a reduction in the accuracy of epilepsy prediction             ments on two well-known EEG datasets: Freiburg and CHB-MIT. The
research.                                                                        Freiburg dataset includes 87 seizures from 21 epilepsy patients (13
    Currently, deep learning algorithms have achieved notable effec-             females, 8 males), aged 10–50 years. Each patient experienced 2 to
tiveness in multiple domains, such as speech recognition and computer            5 seizures. Recordings were made with 256 Hz sampling rate, 128
vision (Yadav et al., 2022; Long et al., 2022), and are increasingly             channels. Seizure initiation and epileptic-like patterns were labeled by
being utilized in epileptic prediction. Several studies have used time–          experts (Aschenbrenner-Scheibe et al., 2003). The CHB-MIT database
frequency analysis. Truong et al. (2018) combined short-time Fourier             includes EEG recordings from 22 children: 17 girls (ages 1.5–19) and
transformation (STFT) with convolution neural networks, while As-                5 boys (ages 3–22). Of these, chb21 and chb01 were recorded from
sali et al. (2023) merged spectral and temporal features. In spatio-             the same female participant, separated by 1.5 years. All of whom had
temporal modeling, Zhang et al. (2023) introduced the STCNN, and Liu             taken antiepileptic drugs for several days. To ensure consistency in the
                                                                                 method and to maximize the utilization of data from more patients,
et al. (2024) developed a 3D convolution-bidirectional LSTM-attention
                                                                                 we followed (Zhang et al., 2019; Park et al., 2018), collected the data
model. Regarding attention mechanisms, Bhattacharya et al. (2022) ap-
                                                                                 using 18 standard channels at a sampling rate of 256 Hz (Anugraha
plied deep Transformers to time–frequency data, and Sun et al. (2021)
                                                                                 et al., 2017).
proposed the CADCNN framework. These innovations have improved
                                                                                     Complex, irregular brain activity appears about 7 h before seizure
seizure prediction and advanced epilepsy forecasting.
                                                                                 onset, while electrophysiological patterns resembling typical epilep-
    Among the aforementioned methods, the maximum SOP of 60 min
                                                                                 tic seizures emerge approximately 2 h prior, signaling an impending
limits the APT nearly impossible to extend further. An extended APT
                                                                                 seizure (Litt et al., 2001). To evaluate our method’s performance and
period enables patients and caregivers to have sufficient time to in-
                                                                                 explore longer SOP prediction, we defined multiple 1-hour and 2-hour
tervene proactively in advance. When the APT is longer than that of
                                                                                 preictal segments per patient in both datasets. Consistent with Yang
conventional anti-epileptic drugs, taking medication after receiving a
                                                                                 et al. (2021), the inter-seizure interval was defined as the period start-
warning can effectively suppress seizures. Precise prediction alerts are
                                                                                 ing 4 h post-seizure and ending 4 h pre-next-seizure. Given the inherent
expected to reduce the frequency of medication and dependence for
                                                                                 imbalance favoring interictal data, we balanced the count of preictal
those who require daily administration of medication at fixed intervals.
                                                                                 and interictal segments per patient. Specifically, for each preictal pe-
However, in practice, extending the SOP still faces challenges. As
                                                                                 riod, we randomly selected an interictal segment of the same duration,
the preictal duration increases, its electrophysiological characteristics
                                                                                 repeating this process three times to incorporate diverse interictal data
begin to overlap with those of the interictal period. This similarity            and ensure consistent segment counts between the training and testing
makes it progressively more challenging to differentiate preictal from           phases (Wang et al., 2021). To fulfill the basic criteria for training and
interictal phases using feature-based analysis. For spectrograms gener-          testing in experiments involving consistent 1-hour preictal intervals per
ated by STFT, EEG signals are correlated both across time and between            patient, a minimum of two 1-hour preictal segments and two 1-hour
frequency domains. Additionally, each channel has its own unique                 interictal segments are required. Since some patients did not have at
characteristics. In previous studies, causal relationships at both the           least two 1-hour preictal and interictal data periods, these patients were
time–frequency and channel levels have rarely been considered.                   excluded from our study. Similarly, for experiments that uniformly used
    Based on the above problems, we propose the causal attention                 2-hour preictal periods, the patient selection criteria were the same as
network (CANet). This approach fully leverages the local feature ex-             those used for experiments with 1-hour preictal periods. Based on the
traction and fusion capabilities of convolution networks across various          aforementioned definitions and constraints, Tables 1 and 2 respectively
dimensions, along with the global causal feature extraction advantages           outline the details of the qualified patients in the two datasets.
of CANet. Initially, dilated causal convolution networks capture local
causal features in the time and frequency dimensions, followed by                2.2. Pre-processing
convolution to fuse all channel features. Subsequently, a causal at-
tention network is introduced firstly in epilepsy prediction research.               Due to the inherent non-stationarity and high variability of raw
It learns the global causal relationships within the data fed into the           EEG, time–frequency analysis methods are often used for preprocessing
module. Additionally, we present a new double-layer dynamic window               and feature extraction for epileptic seizure prediction (Usman et al.,
prediction algorithm, developed to minimize false positives and im-              2020; Peng et al., 2022). In this paper, STFT is used because it can pro-
prove the timing of medication administration for better patient safety.         vide local spectral representation and reveal the instantaneous changes
The Freiburg dataset and the CHB-MIT dataset were used to evaluate               of frequency components before epileptic seizures, which is difficult to
our method, exhibiting better performance than many of the leading               obtain from time domain signals or a single global Fourier transform.
existing approaches.                                                             We set the EEG window length to 30 s, following Truong et al. (2018).
    The key contributions of our study are presented as follows:                 The core idea of the STFT is to apply a fixed-length window function to


Y. Qu et al.                                                                                                          Journal of Neuroscience Methods 428 (2026) 110665


Table 1                                                                               value of 61, ‘‘𝑇 ’’ as the time frame of 114, ‘‘𝑇 _𝑆’’ as the sample size of
Details of qualified patients in the Freiburg dataset.                                7680 in the time domain and ‘‘𝑇 𝐹 ’’ as the number of time–frequency
 Patient ID    Sex (F/M)       Age     1h                     2h                      features in the STFT output of 6954. For the Freiburg dataset, the data
                                       No.      Preictal(h)   No.   Preictal(h)       input format was 𝐶1×𝑇 _𝑆, representing 6 electrode channels, with each
 Burg01        F               15      3        6             2     4                 channel containing 7680-time samples. The STFT processes each chan-
 Burg03        M               14      4        8             –     –                 nel independently. For each channel, the STFT decomposes the time
 Burg04        F               26      4        8             2     4                 series into 61 frequency bins and 114-time frames, thereby generating
 Burg05        F               16      2        4             2     4
                                                                                      a frequency-time matrix of size 𝐹 × 𝑇 for each channel. Therefore, the
 Burg06        F               31      3        6             2     4
 Burg07        F               42      3        6             –     –                 overall output of the STFT across all channels forms a 𝐶1 × 𝐹 × 𝑇 three-
 Burg08        F               32      2        4             –     –                 dimensional array, fully encapsulating the spectral information of the
 Burg09        M               44      5        10            2     4                 original signal as it evolves over time. In the CHB-MIT dataset, the
 Burg10        M               47      5        10            2     4                 only difference from the Freiburg dataset is the number of electrode
 Burg11        F               10      4        8             2     4
 Burg12        F               42      4        8             2     4
                                                                                      channels is 18. This transformation enables us to track epileptic seizure
 Burg13        F               22      2        4             –     –                 activity across both the time and frequency domains, providing critical
 Burg14        F               41      3        6             –     –                 features for subsequent analysis.
 Burg15        M               31      3        6             3     6                     The EEG recordings in the Freiburg and CHB-MIT datasets were
 Burg16        F               50      5        10            2     4
                                                                                      exposed to 50 Hz and 60 Hz power line noise contamination, respec-
 Burg17        M               28      5        10            4     8
 Burg18        F               25      5        10            4     8                 tively (Truong et al., 2018, 2019). Power line noise can be effec-
 Burg19        F               28      4        8             2     4                 tively removed by filtering out components within specific frequency
 Burg20        M               33      5        10            4     8                 bands (Park et al., 2011). We use a bandpass filter to remove the
 Burg21        M               13      4        8             2     4                 current noise in the corresponding frequency band, enabling the model
 Totals        –               –       75       150           37    74                to learn more effective features. For the Freiburg dataset, we exclude
                                                                                      components within the 47–53 Hz and 97–103 Hz bands to remove
Table 2                                                                               50 Hz noise. Similarly, for the CHB-MIT dataset, we filtered out com-
Details of qualified patients in the CHB-MIT dataset.                                 ponents in the 57–63 Hz and 117–123 Hz bands to eliminate 60 Hz
 Patient ID    Sex (F/M)       Age      1h                    2h                      interference. In addition, the DC component (0 Hz) was removed from
                                                                                      all records (Ma et al., 2019). Due to the removal of specific frequency
                                        No.     Preictal(h)   No.   Preictal(h)
                                                                                      bands, other bands were naturally spliced together to reconstruct EEG
 Chb01         F               11       5       10            5     10
                                                                                      signals with better data quality.
 Chb02         M               11       2       4             2     4
 Chb03         F               14       4       8             –     –                     We saved these preprocessed spectrogram data as a NumPy matrix
 Chb04         M               22       3       6             3     6                 and used it as the input for module B (causal attention network with
 Chb05         F               7        5       10            4     8                 time frequency channel feature fusion) as shown in Fig. 1. The spectro-
 Chb06         F               1.5      9       18            6     12
                                                                                      gram of the Freiburg and CHB-MIT datasets are represented as NumPy
 Chb07         F               14.5     3       6             3     6
 Chb09         F               10       4       8             3     6
                                                                                      matrices with dimensions 𝐶1 × 𝐹 × 𝑇 and 𝐶2 × 𝐹 × 𝑇 , respectively.
 Chb10         M               3        6       12            6     12                Here, 𝐶1 and 𝐶2 denote the number of common EEG channels across
 Chb13         F               3        3       6             3     6                 patients in each dataset, while the dimensions 𝐹 × 𝑇 correspond to the
 Chb16         F               7        3       6             2     4                 frequency-time resolution of a 30-second time window.
 Chb18         F               18       3       6             2     4
 Chb19         F               19       3       6             –     –
 Chb20         F               6        3       6             2     4                 2.3. Network architecture
 Chb21         F               13       3       6             –     –
 Chb22         F               9        3       6             3     6                     As shown in Fig. 1, Module B is the "causal attention network with
 Chb23         F               6        3       6             –     –                 time frequency channel feature fusion’’. The data processed by Module
 Totals        –               –        65      130           44    88                A is used as the input for Module B. Module B is composed of time
                                                                                      frequency channel feature fusion and CANet. The time frequency chan-
                                                                                      nel feature fusion part uses dilated causal convolution to perform local
analyze a signal in the time domain. Captured segments are analyzed                   feature extraction and fusion in the time–frequency domain, followed
using a Fourier transform to obtain a representation of the local spec-               by a convolutional layer that integrates features from all channels.
trum within a narrow time window around time t. The STFT is used to                   In the CANet part, causal attention is used to extract global causal
generate a series of local spectra for each time interval. As the window              features, and then processed through two fully connected layers to
                                                                                      finally output a series of labels for predicting the interictal or preictal
moves along the entire time axis, the STFT generates a series of local-
                                                                                      period for Module B.
ized spectra for each time interval. Consequently, STFT provides a 2-D
time–frequency representation, and its core computational formulation
                                                                                      2.3.1. Time frequency channel feature fusion
is expressed as follows:
                                                                                          Traditional manual feature extraction requires a lot of time and
                       ∞
STFT{𝑥(𝑡)}(𝑡, 𝜔) =         𝑥(𝜏) 𝑓 (𝜏 − 𝑡) 𝑒−𝑗𝜔𝜏 𝑑𝜏                          (1)       professional knowledge. Moreover, it may not be able to discover some
                     ∫−∞                                                              hidden features in the data (Jia et al., 2016). Therefore, this paper
    Here, 𝑥(𝑡) is the time-domain signal, 𝑡 and 𝜏 denote the time, 𝑤                  uses automatic feature extraction. Recently, the temporal convolutional
denotes the frequency and 𝑓 (𝜏 −𝑡) is a window function whose center is               network (TCN) with a core component of dilated causal convolutional
at time 𝑡, 𝑒−𝑗𝑤𝑡 denotes the Fourier kernel. The output STFT{𝑥(𝑡)}(𝑡, 𝑤)              networks (Ji et al., 2024) has been employed to predict epilepsy,
is a complex matrix representing the amplitude and phase of the EEG                   with numerous studies demonstrating its effectiveness in forecasting
signal at each time–frequency point (Ozdemir et al., 2021). In this                   seizures. As shown in Fig. 2.
study, a series of multi-channel EEG signal data were input into the                      The dilated causal convolution incorporates dilation rates to in-
STFT using a sliding window approach. In order to show the specific                   crease spacing between kernel elements, thereby substantially expand-
input and output data changes more clearly, we uniformly denote ‘‘𝐶1’’                ing the receptive field without increasing parameter count or com-
as the number of 6 channels in the Freiburg dataset, ‘‘𝐶2’’ as the                    putational cost, enabling efficient processing. Through hierarchical
number of 18 channels in the CHB-MIT dataset, ‘‘𝐹 ’’ as the frequency                 stacking of layers with progressively varied dilation rates, this approach


Y. Qu et al.                                                                                                           Journal of Neuroscience Methods 428 (2026) 110665


Fig. 1. Overview of the CANet. Where 𝐶ℎ denotes Channel, 𝑇 𝐹 denotes Time–frequency, In-ic and Pre-ic respectively represent interictal and preictal period,
while INTERICTAL and PREICTAL respectively denote interictal pre-ictal data segmentation.


                                               Fig. 2. Structural diagram of the dilated causal convolutional networks.


supports multi-scale feature extraction with exponentially growing re-                      We use dilated causal convolutional networks for automatic feature
ceptive fields, while preserving temporal causality by relying solely on               extraction and fusion at the time and frequency levels, and standard
past inputs. This capability makes it particularly effective in capturing              convolution for feature fusion at the channel level. Inspired by Bi et al.
long-range pathological correlations in time series applications such as               (2024) and Xu et al. (2018), we separated the two-dimensional con-
epilepsy prediction. The dilated causal convolutional network F can be                 volution into two one-dimensional convolution layers operating along
formulated as:                                                                         distinct directions. We refer to Bi et al. (2024) for the methodology
                                                                                       on flattening 2D spectrograms into 1D time–frequency data. Time–
                        ∑
                        𝑘−1
                                                                                       frequency domain feature extraction is first performed automatically
𝐅(𝑠) = (𝑋 ∗𝑑 𝑓 )(𝑠) =         𝑓 (𝑖) ⋅ 𝑋𝑠−𝑑×𝑖                                 (2)
                        𝑖=0                                                            using dilated causal convolution with k convolution kernels of size
    Here, 𝑠 is the input sequence index, 𝑋 ∈ R𝑁 is the input sequence,                 (1, 128), where the step size is 2𝑛−1 (n is the number of layers of
∗𝑑 is the dilated causal convolution operation and 𝑑 is the dilation                   the dilated causal convolution). We have shown experimentally that
rate, 𝑓 ∶ 0, … , 𝑘 − 1 → R represents the filter and 𝑘 is the filter                   three time–frequency causal convolutional network layers have the best
size. This operation exhibits causal relevance, as the output at the                   performance, so we finally use a three-layer time–frequency causal con-
current point 𝑠 depends solely on the input data from the current                      volutional network. The second step involves applying k convolution
point 𝑠 and earlier points (that is, 𝑋𝑠−𝑑×𝑖 , 𝑖 ≥ 0), thereby ensuring no              kernels of size (𝑐ℎ, 1) and stride (1, 1) to fuse the channel features. Here,
leakage of information about future points. This extension mechanism                   ch represents the number of electrode channels in the EEG data. Subse-
                                                                                       quently, we use batch normalization to enhance training stability and
enables the model to capture dependencies along this dimension. In
                                                                                       reduce the risk of overfitting. Following the method outlined in Shah
our architecture, the input to the dilated causal convolutional network
                                                                                       et al. (2016), we selected the activation function of the Exponential
in the Freiburg dataset is the STFT output shaped as 𝐶1 × 𝑇 𝐹 , where
                                                                                       Linear Unit (ELU) to enhance the nonlinear expression ability of the
𝐶1 denotes the number of electrode channels and 𝑇 𝐹 represents the
                                                                                       model. In the subsequent layer implements we utilized a kernel size
time–frequency data integration (i.e., 114 time frames × 61 frequency                  of (1, 128) and a stride of (1, 32) for the average pooling operation
bins). The output data format is 𝐻_𝐾 × 𝐶1 × 𝑇 𝐹 , where 𝐻_𝐾 denotes                    along the time–frequency dimension. This pooling mechanism serves
that the hyperparameter 𝑘 in the dilated causal convolutional network                  to smooth the time–frequency features, thus mitigating overfitting and
is 16, and 𝐶1×𝑇 𝐹 preserves the temporal and spectral resolution of the                lowering computational demands. Subsequently, the time–frequency
input. In this procedure, the CHB-MIT dataset differs from the Freiburg                and channel features are restructured: the electrode channel dimension
dataset in that it employs 18 electrode channels. This configuration                   is flattened and transposed with respect to the time–frequency dimen-
is crucial to maintain the consistency of the dimensions in the data,                  sion. As described in Table 3, the hyperparameter 𝑘 is configured to 16.
enabling the extraction of multiscale features from epileptic EEG signals              The time–frequency and channel features corresponding to each time
while preserving spatiotemporal information.                                           point are fed into the CANet as input.


Y. Qu et al.                                                                                                          Journal of Neuroscience Methods 428 (2026) 110665


Table 3
Details of causal attention with time frequency channel feature fusion.
 Layer                        Layer number        In             Out          Kernel/Value                                                                    Stride
 TF dilated causal Conv                           1(𝑘)           𝑘            (1128)                                                                          (1, 2𝑛−1 )
 Batch normalization                                                          –                                                                               –
 Elu activation               3                                               –                                                                               –
                                                  𝑘              𝑘
 Average pooling                                                              (1128)                                                                          (1, 32)
 Dropout                                                                      0.5                                                                             –
 Channel conv                                                                 (𝑐ℎ, 1)                                                                         (1, 1)
 Batch normalization                                                          –                                                                               –
 Elu activation               1                   𝑘              𝑘            –                                                                               –
 Average pooling                                                              (1128)                                                                          (1, 32)
 Dropout                                                                      0.5                                                                             –
 Rearrange                    1                   (𝑘, 1, 𝑚)      (𝑚, 𝑘)       –                                                                               –
 Layer normalization                                                          Embedding Size = 8
 Causal attention                                                             Embedding Size = 8; attention heads = 1; Dropout = 0.6; block size = 45
                              3                   (𝑚, 𝑘)         (𝑚, 𝑘)                                                                                       –
 Layer normalization                                                          Embedding Size = 8
 Feedforward                                                                  Forward expansion = 1; Dropout = 0.5; Embedding Size = 8
 Fully connected              2                   (𝑚, 𝑘)         2            –                                                                               -


2.3.2. Causal attention network                                                       and output data are maintained throughout the process. In the causal
    The coherence of epileptic neural activity makes both time–frequency              attention network, we defined the number of causal attention layers
and channel features critical for epilepsy classification and prediction.             as three. The detailed parameters of the causal attention network are
This paper employs causal attention to capture global causal correla-                 presented in Table 3.
tions in the fused time–frequency and channel features, while also ad-                    Finally, two fully connected layers are employed, followed by a
dressing the limitations of constrained receptive fields in dilated causal            softmax activation function that transforms the output into a probabil-
convolutional networks. The tokens arranged in the time–frequency                     ity distribution, resulting in a one-dimensional predicted classification
channel feature fusion section are linearly transformed to produce                    vector. The cross-entropy is used as the loss function to evaluate the
equal-sized triples called queries (𝑄), keys (𝐾), and values (𝑉 ). we                 error between the model’s predicted output and the true labels (Wang
use the dot product between 𝑄 and the transposed vectors of 𝐾 to                      et al., 2019), as shown below:
assess the relationship among distinct tokens. To uphold the causality                           𝑁𝑏 𝑀
principle within the model, we introduce a masking matrix 𝑀 that                             1 ∑∑
                                                                                      =−               𝑦 log( ̂𝑦)                                                   (5)
conceals subsequent information frames beyond the current point. This                        𝑁𝑏 𝑖=1 𝑐=1
masking is applied subsequent to the scaled dot product operation with                     Here, 𝑀 is the classification number of epilepsy, 𝑦 is the truth label,
the factor 𝑑. The attention mechanism utilizes the 𝑆𝑜𝑓 𝑡𝑚𝑎𝑥 function to               𝑦̂ is the predicted label, and 𝑁𝑏 is the number of trials for a batch.
compute attention weights (Fan et al., 2022). To prevent the model
from accessing future information, a masking matrix is applied, where                 2.4. Seizure alarm
the upper triangular part (corresponding to future positions) is filled
with −∞, and the lower triangular part (representing the current
                                                                                          Frequent alarms may impose significant psychological stress on
and past positions) is set to 1. This strategic masking ensures that
                                                                                      patients, interfere with their normal behaviors, and potentially result
the model only attends to available, non-future data, thus preserving
                                                                                      in unnecessary medical interventions. Thus, we introduce a double-
causality. A scaling factor is meticulously crafted to circumvent the
                                                                                      layer dynamic window prediction algorithm to minimize false alert.
issue of vanishing gradients, thereby ensuring a stable training regimen.
                                                                                      The method is presented in Module C of Fig. 1, the corresponding
This output is then funneled through a 𝑆𝑜𝑓 𝑡𝑚𝑎𝑥 function, yielding a
                                                                                      mathematical formulation are outlined below. The sliding window
weighting matrix that represents the causal attention scores, effectively
                                                                                      mechanism progresses sequentially from interictal to preictal states.
capturing the significance of each token interaction. Subsequently,
                                                                                      The first-level window encompasses 4 labels (as illustrated by the five
the causal attention scores are applied to the values (𝑉 ) through
                                                                                      colored small boxes in Fig. 1), here, label 0 is the interictal state, 1
dot product operations, thus effectively regulating the contribution
                                                                                      is the preictal state; 4 labels represent 2 min of data. If the count of
of each feature dimension (Fan et al., 2022). This procedure can be
                                                                                      label 1 within this window does not exceed 2 (𝑛1 ≤ 𝑃 1), the window is
encapsulated mathematically as:
                         (          )                                                 classified as In-ic; otherwise, it is labeled as Pre-ic. The second-level
                               𝑄𝐾 𝑇                                                   window spans 20 labels (represented by the large blue box), which
𝐶𝐴(𝑄, 𝐾, 𝑉 ) = Sof tmax 𝑀 ⋅ √          𝑉                               (3)            corresponds to five consecutive first-level windows or 10 min of data.
                                  𝑘
           {                                                                          When the number of Pre-ic classifications within this window is no
             1,     𝑝 ≤ 𝑚 − 𝑞,                                                        more than 3 (𝑛2 ≤ 𝑃 2), the window is categorized as INTERICTAL;
𝑀(𝑝, 𝑞) =                                                              (4)
             −∞, otherwise.                                                           otherwise, it is designated as PREICTAL. This second-level window then
    Here, 𝑘 is a token’s length, 𝐶𝐴 is causal attention, 𝑄, 𝐾, (and 𝑉 de- )           advances non-overlappingly along the interictal-to-preictal direction,
                                                                          𝑇
note the query, key, and value matrices, respectively. Sof tmax 𝑀 ⋅ 𝑄𝐾
                                                                     √                and an alarm is activated upon its classification as PREICTAL.
                                                                          𝑘                        {
is applied to row vectors, converting the log-likelihood values from the                             In-ic,   𝑛1 ≤ 𝑇 1,
attention layer into a probability distribution. 𝑀 is the causal masking              State1[𝑡] =                                                              (6)
                                                                                                     Pre-ic, 𝑛1 > 𝑇 1.
matrix. 𝑝 and 𝑞 represent the horizontal and vertical coordinates of the                           {
causal masking matrix. The input to the causal attention module is a                                  INTERICTAL, 𝑛2 ≤ 𝑇 2,
                                                                                      State2[𝑇 ] =                                                             (7)
tensor of shape 𝑚 × 𝑘. This operation produces an output of the same                                  PREICTAL,       𝑛2 > 𝑇 2.
dimensions 𝑚 × 𝑘, integrating global information from past and present                    Here, 0 is predicted interictal label; 1 is predicted preictal label; 𝑛1
data while preserving the sequence length and feature size.                           is the count of label 1 in the first-level window; 𝑇 1 is the threshold of
    Furthermore, we employed two fully connected feedforward layers                   2; 𝑛2 is the number of Pre-ic labeled within the second-level window;
to conduct deep global semantic modeling. The dimensions of the input                 𝑇 2 is the threshold of 3.


Y. Qu et al.                                                                                                       Journal of Neuroscience Methods 428 (2026) 110665


2.5. Experimental strategy                                                              𝐹 𝐴𝑅 indicates total false alarms produced by the epilepsy alert
                                                                                    system per hour. It is defined as:
    This study employed the leave-one-out cross-validation (LOOCV)                           𝑓 𝑎𝑙
                                                                                    𝐹 𝐴𝑅 =                                                               (9)
strategy (Gao et al., 2022), and ‘‘one’’ refers to a single seizure event.                    𝑇
Specifically, for a patient with 𝑁 seizure episodes (with the pre-ictal                 Here, 𝑓 𝑎𝑙 is the total count of false alarms; 𝑇 denotes the overall
period corresponding to 1 or 2 h), we randomly selected 𝑁 interictal                duration hours of the EEG signal.
segments of the same quantity as the pre-ictal periods to ensure class                  At the segment-based level, the accuracy(𝐴𝑐𝑐), sensitivity(𝑆𝑒𝑛),
balance during model training (Wang et al., 2021). The interictal and               specificity(𝑆𝑝𝑒), and false prediction rate(𝐹 𝑝𝑟) are employed as evalu-
pre-ictal periods were randomly combined in pairs (left: interictal,                ation metrics. The formulas of these four metrics are given as follows:
right: pre-ictal) to form 𝑁 paired segments. In each epoch, one segment                           𝑇𝑃 + 𝑇𝑁
was selected as the test set, and the remaining N-1 segments were                   𝐴𝑐𝑐 =                                                                     (10)
                                                                                             𝑇𝑃 + 𝑇𝑁 + 𝐹𝑁 + 𝐹𝑃
used as the training set until each segment was considered as a test
                                                                                               𝑇𝑃
data once. Therefore, our model was experimented 𝑁 times for each                   𝑆𝑒𝑛 =                                                                     (11)
                                                                                             𝑇𝑃 + 𝐹𝑁
patient, outputting a series of labels indicating the interictal or pre-ictal
period. We calculate the average accuracy, sensitivity and false positive                      𝑇𝑁
                                                                                    𝑆𝑝𝑒 =                                                                     (12)
rate as the final results. The entire experiment was repeated six times,                     𝑇𝑁 + 𝐹𝑃
generating six sets of predicted labels, each of which was input into                         𝐹𝑃
                                                                                    𝐹 𝑝𝑟 =                                                              (13)
module C (seizure alert) in Fig. 1.                                                        𝑇𝑁 + 𝐹𝑃
    For the two datasets employed in our study, the parameters of the                  Here, 𝑇 𝑃 (True Positive): The number of windows correctly labeled
model were set to batch size of 32, learning rate of 0.0005, embedding              as preictal; 𝐹 𝑃 (False Positive): The number of windows wrongly la-
dimension of 8, epochs of 200, the number of layers of dilated causal               beled as preictal when they are actually interictal; 𝑇 𝑁 (True Negative):
convolution was set to 3, and the causal attention mechanism was con-               The number of windows correctly labeled as interictal; 𝐹 𝑁 (False
figured with 3 layers. The model employed in this study was developed               Negative): The number of windows wrongly labeled as preictal when
using Python 3.10 and executed on an NVIDIA GTX 4090 GPU. The                       they are actually interictal.
model contains approximately 5M parameters, with a computational
complexity of about 11 GFLOPs per sample. For instance, training                    3.2. Experimental results
time in a 1-hour preictal experiment on the Freiburg dataset was
approximately 2 min.                                                                3.2.1. The experiments on freiburg dataset
                                                                                        We evaluated the effectiveness of our proposed approach at both the
                                                                                    segment-based and event-based levels with a 1-hour preictal interval
3. Results
                                                                                    durations, as presented in Table 4. On the segment-based level, our
                                                                                    method achieved an Acc of 96.12%, a Sen of 93.87%, a Spe of 98.37%,
    In this section, we first introduce the performance evaluation crite-           and a Fpr of 0.0163/h. Among 20 patients, 17 achieved over 90.00%
ria based on segments and events. Then, we present the results on the               Acc with our method, and for half of the patients, the Acc exceeded
two datasets we chose, including detailed performance of our seizure                99.00%. For Patient 4, although the Sen was less than ideal, the
prediction method and comparisons showing how key components                        Spe was very high, indicating that the method was less effective at
affect overall system effectiveness.                                                predicting the preictal period but performed well at identifying the
                                                                                    interictal periods. The main reason for this is that the patient’s partial
3.1. Evaluation metrics                                                             preictal is too close to the interictal state, resulting in a lower overall
                                                                                    Sen in this patient. For Patient 20, our method exhibited mediocre
    In seizure prediction, approaches are typically evaluated at the                performance compared to other patients, with a Sen of 80.33% and
event-based level. Simultaneously, we conducted experiments at the                  a Fpr of 0.1217/h. This suggests that, for this specific patient, our
segment-based level to more thoroughly assess method performance                    method exhibited a diminished ability to distinguish between preictal
and the differences between event-based and segment-based evalua-                   and interictal phases. On the event-based level, our method achieved a
tions.                                                                              100.00% SEN and a FAR of 0.0077/h. This level of sensitivity indicates
    Before running the algorithm, the SOP and the Seizure Prediction                that the method can effectively predict each epileptic seizure, enabling
Horizon (SPH) should be defined (Maiwald et al., 2004). At the event-               patients to take necessary measures before the seizure occurs, thereby
based level, SPH is defined as the time interval between the system’s               alleviating or reducing the serious consequences brought about by
alert trigger and the actual onset of an epileptic seizure. SOP typically           epilepsy. Among these patients, 80% had a FAR of 0, indicating that
                                                                                    our method produced no false alarms for them, which significantly
represents equivalent to the preictal interval (Hu et al., 2023; Rao et al.,
                                                                                    reduced patient anxiety. The results at both the segment-based and
2024; Lopes et al., 2023). A longer interictal and preictal period is more
                                                                                    event-based levels for the Freiburg dataset with a preictal interval
conducive to our experimental research. Therefore, we chose a longer
                                                                                    durations of 1 h demonstrate that our method effectively identifies
interictal and preictal of 1 and 2 h respectively as the research object.
                                                                                    preictal and interictal periods and exhibits excellent performance in
Thereby, the SOP is set to 1 and 2 h, respectively. We used a longer
                                                                                    seizure prediction.
interictal and preictal period in our experiment, since extended data
                                                                                        Moreover, we evaluated the effectiveness of the 2 h preictal interval
segments allow for more thorough learning, a relatively long SPH was
                                                                                    durations, both at the segment-based and event-based levels, as pre-
also employed. In this study, the SPH was defined as 10 min. The SEN
                                                                                    sented in Table 5. At the segment-based level, our method achieved an
and FAR was employed to evaluate our prediction model. as explained
                                                                                    Acc of 91.89%, Sen of 89.36%, Spe of 94.42%, and a Fpr of 0.0558/h.
in the following sections.
                                                                                    Among the 15 patients, 10 exhibited an Acc of over 95.00% with
    𝑆𝐸𝑁 is the percentage of correctly predicted warnings among all                 our method. Our method struggled to accurately identify the preictal
seizure episodes. It is defined as:                                                 and interictal periods for patients 4 and 19. Specifically, for patient
         𝑐𝑜𝑟                                                                        4, the Sen was 59.79%, indicating difficulty in determining the true
𝑆𝐸𝑁 =        × 100%                                                    (8)
         𝑁                                                                          preictal period for this patient. For patient 19, the Fpr was 0.4279/h,
    Here, 𝑐𝑜𝑟 is the total count of accurate alerts; 𝑁 is the total number          reflecting challenges in identifying the true interictal period. At the
of episode seizures.                                                                event-based level, our method achieved a SEN of 96.67% and a FAR


Y. Qu et al.                                                                                                          Journal of Neuroscience Methods 428 (2026) 110665


Table 4
Freiburg dataset: predictive performance with a preictal interval duration of 1 h.
 Patient ID            No. of seizures            Segment-based level                                                                Event-based level
                                                  Acc (%)               Sen (%)             Spe (%)             Fpr (/h)             SEN (%)                FAR (/h)
 Burg01                3                          92.64                 86.94               98.33               0.0167               100.00                 0.0000
 Burg03                4                          99.17                 98.61               99.72               0.0028               100.00                 0.0000
 Burg04                4                          81.67                 63.43               99.91               0.0009               100.00                 0.0000
 Burg05                2                          98.33                 99.68               96.99               0.0301               100.00                 0.0278
 Burg06                3                          99.17                 98.89               99.44               0.0056               100.00                 0.0000
 Burg07                3                          96.81                 94.44               99.17               0.0083               100.00                 0.0000
 Burg08                2                          99.17                 98.52               99.81               0.0019               100.00                 0.0000
 Burg09                5                          99.83                 99.75               99.92               0.0008               100.00                 0.0000
 Burg10                5                          97.08                 95.16               99.01               0.0099               100.00                 0.0000
 Burg11                4                          99.58                 99.38               99.79               0.0021               100.00                 0.0000
 Burg12                4                          97.81                 95.75               99.87               0.0013               100.00                 0.0000
 Burg13                2                          88.33                 82.50               94.17               0.0583               100.00                 0.0417
 Burg14                3                          99.86                 99.98               99.74               0.0026               100.00                 0.0000
 Burg15                3                          97.08                 98.61               95.56               0.0444               100.00                 0.0185
 Burg16                5                          99.75                 99.91               99.59               0.0041               100.00                 0.0000
 Burg17                5                          99.92                 99.98               99.85               0.0015               100.00                 0.0000
 Burg18                5                          99.75                 99.67               99.83               0.0017               100.00                 0.0000
 Burg19                4                          99.27                 99.17               99.38               0.0062               100.00                 0.0000
 Burg20                5                          84.08                 80.33               87.83               0.1217               100.00                 0.0667
 Burg21                4                          93.13                 86.74               99.51               0.0049               100.00                 0.0000
 Average               75                         96.12                 93.87               98.37               0.0163               100.00                 0.0077


Table 5
Freiburg dataset: predictive performance with a preictal interval duration of 2 h.
 Patient ID            No. of seizures            Segment-based level                                                                Event-based level
                                                  Acc (%)               Sen (%)             Spe (%)             Fpr (/h)             SEN (%)                FAR (/h)
 Burg01                2                          88.75                 78.33               99.17               0.0083               100.00                 0.0000
 Burg04                2                          72.71                 59.79               85.63               0.1437               50.00                  0.1111
 Burg05                2                          97.81                 97.71               97.92               0.0208               100.00                 0.0000
 Burg06                2                          99.06                 99.79               98.33               0.0167               100.00                 0.0000
 Burg09                2                          98.02                 99.92               96.13               0.0388               100.00                 0.0278
 Burg10                2                          91.56                 84.65               98.47               0.0153               100.00                 0.0000
 Burg11                2                          95.94                 94.13               97.75               0.0225               100.00                 0.0139
 Burg12                2                          96.35                 94.10               98.61               0.0139               100.00                 0.0000
 Burg15                3                          99.65                 99.70               99.61               0.0039               100.00                 0.0000
 Burg16                2                          98.54                 98.54               98.54               0.0146               100.00                 0.0000
 Burg17                4                          96.67                 94.76               98.58               0.0142               100.00                 0.0069
 Burg18                4                          96.35                 93.96               98.75               0.0125               100.00                 0.0000
 Burg19                2                          61.56                 65.92               57.21               0.4279               100.00                 0.5139
 Burg20                4                          87.66                 82.60               92.71               0.0729               100.00                 0.0347
 Burg21                2                          97.71                 96.49               98.93               0.0108               100.00                 0.0000
 Average               37                         91.89                 89.36               94.42               0.0558               96.67                  0.0472


of 0.0472/h. Out of 37 seizures in this dataset, 36 were predicted by                 does not effectively identify the true interictal periods for this patient.
our method. Notably, 60% of the patients had a FAR of 0, indicating                   At the event-based level, our method achieved a SEN of 97.06% and
no false alarms and thereby significantly reducing patient anxiety. The               a FAR of 0.0251/h. Our method successfully predicted 64 out of 65
SEN for patient 4 is 50.00%, which means that only one out of the                     seizures in this dataset, demonstrating its strong predictive capability.
patient’s two seizures can be correctly predicted. For patient 19, the                Furthermore, for 11 out of 17 patients, the FAR was 0, indicating
FAR was 0.5139/h, indicating a high false alarm rate for this patient.                that our method does not produce false alarms for these individuals.
The results indicate that performance at the segment-based level is                   Overall, the experimental results show that our method also performs
generally aligned with that at the event-based level, though the latter               well in predicting seizures at a 1-hour preictal interval durations in the
consistently demonstrates superior performance. Overall, our method                   CHB-MIT dataset.
shows high SEN and low FAR at the event-based level. Comparing                            Furthermore, in the CHB-MIT dataset, we evaluated the perfor-
the 1-hour and 2-hour preictal intervals durations that the 1-hour                    mance of our method for seizure prediction at a 2-hour preictal interval,
interval durations better overall results. Nevertheless, this comparison              both at the segment-based and event-based levels, as shown in Table 7.
also demonstrates that our method performs well over longer prediction                At the segment-based level, our method achieved an Acc of 86.10%,
horizons.                                                                             a Sen of 80.63%, a Spe of 91.58%, and a Fpr of 0.0842/h. For 5 out
                                                                                      of 13 patients, our method reached an Acc of over 95.00%. However,
3.2.2. The experiments on CHB-MIT dataset                                             for patients 2 and 13, the prediction results were not satisfactory.
   We effectiveness the performance of our approach at a 1-hour                       Specifically, the Sen for patients 2 and 13 were 57.08% and 59.54%,
preictal interval, both at the segment-based and event-based levels, as               respectively, and at the event-based level, both patients had a SEN of
presented in Table 6. At the segment-based level, our method achieved                 50.00%, indicating that our method does not effectively identify the
an Acc of 95.09%, a Sen of 93.95%, a Spe of 96.23%, and a Fpr of                      true preictal periods for these patients. At the event-based level, our
0.0377/h. For 12 out of 17 patients, our method achieved an Acc                       method achieved a SEN of 92.31% and a FAR of 0.0666/h. For 11 out
greater than 95.00%. Only patient 2 had a Sen below 80.00%, with a                    of 13 patients, our method achieved a SEN of 100.00%, meaning it
SEN of just 50.00% at the event-based level, indicating that our method               accurately predicted seizures for these individuals. Overall, while the


Y. Qu et al.                                                                                                        Journal of Neuroscience Methods 428 (2026) 110665


Table 6
CHB-MIT dataset: predictive performance with a preictal interval duration of 1 h.
 Patient ID            No. of seizures           Segment-based level                                                               Event-based level
                                                 Acc (%)               Sen (%)             Spe (%)            Fpr (/h)             SEN (%)                FAR (/h)
 Chb01                 5                         99.75                 99.67               99.83              0.0017               100.00                 0.0000
 Chb02                 2                         80.16                 60.45               99.88              0.0012               50.00                  0.0000
 Chb03                 4                         92.40                 86.88               97.92              0.0208               100.00                 0.0000
 Chb04                 3                         97.77                 98.60               96.94              0.0306               100.00                 0.0185
 Chb05                 5                         99.00                 99.33               98.67              0.0133               100.00                 0.0000
 Chb06                 9                         83.10                 82.96               83.24              0.1676               100.00                 0.1481
 Chb07                 3                         88.03                 97.83               78.22              0.2178               100.00                 0.1667
 Chb09                 4                         99.72                 99.94               99.51              0.0049               100.00                 0.0000
 Chb10                 6                         93.54                 90.42               96.67              0.0333               100.00                 0.0417
 Chb13                 3                         98.19                 97.20               99.19              0.0081               100.00                 0.0000
 Chb16                 3                         98.58                 99.78               97.39              0.0261               100.00                 0.0000
 Chb18                 3                         97.14                 99.31               94.97              0.0503               100.00                 0.0370
 Chb19                 3                         96.11                 92.84               99.39              0.0061               100.00                 0.0000
 Chb20                 3                         99.86                 99.91               99.81              0.0019               100.00                 0.0000
 Chb21                 3                         96.81                 98.05               95.56              0.0444               100.00                 0.0139
 Chb22                 3                         97.50                 95.42               99.59              0.0042               100.00                 0.0000
 Chb23                 3                         98.88                 98.60               99.17              0.0083               100.00                 0.0000
 Average               65                        95.09                 93.95               96.23              0.0377               97.06                  0.0251


Table 7
CHB-MIT dataset: predictive performance with a preictal interval duration of 2 h.
 Patient ID            No. of seizures           Segment-based level                                                               Event-based level
                                                 Acc (%)               Sen (%)             Spe (%)            Fpr (/h)             SEN (%)                FAR (/h)
 Chb01                 5                         99.75                 99.60               99.90              0.0010               100.00                 0.0000
 Chb01                 5                         99.75                 99.60               99.90              0.0010               100.00                 0.0000
 Chb02                 2                         66.15                 57.08               75.21              0.2479               50.00                  0.2917
 Chb04                 3                         97.08                 95.57               98.61              0.0139               100.00                 0.0000
 Chb05                 4                         97.71                 99.01               96.40              0.0360               100.00                 0.0208
 Chb06                 6                         80.83                 77.29               84.38              0.1563               100.00                 0.1111
 Chb07                 3                         80.76                 71.84               89.69              0.1031               100.00                 0.0833
 Chb09                 3                         99.28                 98.92               99.64              0.0036               100.00                 0.0000
 Chb10                 6                         72.19                 62.71               81.67              0.1833               100.00                 0.1667
 Chb13                 3                         73.54                 59.54               87.54              0.1246               50.00                  0.1042
 Chb16                 2                         89.38                 83.04               95.71              0.0429               100.00                 0.0000
 Chb18                 2                         85.63                 77.13               94.13              0.0588               100.00                 0.0208
 Chb20                 2                         79.43                 68.37               90.48              0.0952               100.00                 0.0667
 Chb22                 3                         97.60                 98.05               97.15              0.0285               100.00                 0.0000
 Average               44                        86.10                 80.63               91.58              0.0842               92.31                  0.0666


performance of our method at a 2-hour preictal interval was not as good              of our approach on the Freiburg and CHB-MIT datasets are shown in
as at a 1-hour interval, the results are still considered satisfactory.              Fig. 3.
    From the above four experiments, it is evident that the results at a 1-              As illustrated in Fig. 3, on the Freiburg dataset, our method achieved
hour preictal interval are superior to those at a 2-hour preictal interval.          an average APT of 97.59 min. Among the 15 patients, patients 4 and
However, for patients, the results at a 2-hour preictal interval are more            19 had lower APT but still exceeded 70.00 min. Thirteen out of the
valuable. A longer prediction horizon provides the potential to prevent              15 patients had APT greater than 90.00 min. On the CHB-MIT dataset,
seizures through the use of antiepileptic drugs, which can help patients             our method achieved an average APT of 94.85 min. Patients 2, 10
avoid the severe consequences of seizures. The overall results from                  and 13 had lower APT but still exceeded 60.00 min. Nine out of the
the Freiburg dataset are better than those from the CHB-MIT dataset,                 13 patients had APT greater than 90.00 min. Most antiepileptic drugs
indicating that our method performs better with intracranial EEG data.               require more than 30.00 min to become effective, with some even
                                                                                     taking over an hour (Johannessen Landmark et al., 2020; Meirinho
                                                                                     et al., 2021; Patsalos et al., 2008). The experimental results indicate
3.2.3. The experiments on APT prediction
                                                                                     that our method provides an APT greater than 60.00 min for all patients
    Following the methods (Li et al., 2021; Gao et al., 2023; Guo et al.,
                                                                                     in both the Freiburg dataset and CHB-MIT dataset, allowing for the
2023), We use APT (Average Prediction Time, the mean interval be-                    timely administration of antiepileptic drugs with a faster onset time to
tween our system alert and actual epilepsy onset) to evaluate whether                prevent seizures. Moreover, with over 60% of patients in both datasets
our method predicts epilepsy effectively and in a timely manner. An                  having an APT exceeding 90.00 min, our method for seizure prediction
effective seizure prediction method should have a sufficiently long                  allows these patients to administer most antiepileptic drugs in a timely
APT to help patients get enough time to take measures. Specifically,                 manner, thereby helping to avert seizures.
antiepileptic drugs can effectively prevent epilepsy. Timely and ac-
curate epilepsy warnings can help those patients who need to take                    3.2.4. Ablation experiments
medication at regular intervals every day, potentially reducing the                     To better validate the impact of different modules on the overall
reliance on routine medication. This requires that our APT time exceeds              model, we conducted a series of ablation experiments. The STFT trans-
the onset time of conventional antiepileptic drugs. Our goal is to                   forms time-domain EEG signal data into time–frequency domain data.
explore longer APT, and with a larger SOP setting, the APT is relatively             To validate the effectiveness of the STFT module within the overall
larger. Therefore, we only analyze the APT in experiments with a 2-                  model, we conducted ablation experiments with and without STFT on
hour preictal interval durations (i.e., SOP equals 2 h). The APT results             two datasets and at the preictal periods of 1 h and 2 h, as shown in


Y. Qu et al.                                                                                                             Journal of Neuroscience Methods 428 (2026) 110665


                                        Fig. 3. Results of the APT in the Freiburg dataset and the CHB-MIT dataset.


                Fig. 4. Comparison of accuracy results with and without STFT in the preictal interval durations of 1 and 2 h on two datasets.


Fig. 4. In the Freiburg and CHB-MIT datasets, the average accuracy was            Table 8
higher for models with the STFT module compared to those without                  Details of the statistical significance with and without STFT.
it. Furthermore, for each patient, the average accuracy was higher                 Experiment              t-Statistic                 p-Value                  Cohen_d
for models incorporating the STFT module than for those without it.                burg_1h                 8.23                        7.43E−08                 1.80
Whether in the 1-hour or 2-hour preictal period experiments, the CHB-              burg_2h                 10.74                       1.93E−08                 2.69
MIT dataset showed a greater gap between the Freiburg dataset from                 chb_1h                  6.971                       2.25E−06                 1.64
                                                                                   chb_2h                  10.77                       7.55E−08                 2.88
the with and without STFT modules. Specifically, in the 2 h of preictal
period data from the CHB-MIT dataset, the average accuracy without
the STFT module was 75.50%, which was 10.60% lower than the av-
erage accuracy with the STFT module. Therefore, multiple experiments              illustrate the performance differences with and without the component,
have demonstrated that incorporating an STFT module can effectively               we used only the accuracy metric for comparison. We compared the
enhance the overall model performance.                                            accuracy results with and without DCCN for preictal interval durations
    To further validate the effectiveness of the STFT module, we con-             of 1 and 2 h across two datasets, as illustrated in Fig. 5.
ducted paired t-tests to analyze the statistical significance of the accu-            The experimental results in Fig. 5 demonstrate that for both datasets
racy differences between the ‘‘without STFT’’ and ‘‘with STFT’’ condi-            used and for preictal periods of 1 h and 2 h, the average accuracy
tions. The results show that under all experimental conditions (includ-           achieved with DCCN surpasses that obtained without DCCN. In the
ing burg_1h, burg_2h, chb_1h, and chb_2h), the accuracy differences               CHB-MIT dataset the performance gap between the with and without
reached a statistically highly significant level (𝑝 < 0.001), as shown            of DCCN is greater than in the Freiburg dataset, indicating a more
in Table 8. All effect sizes (Cohen_d) were greater than 1.64, indicat-           substantial impact of DCCN on data collected from the scalp. In the
ing that the performance improvement brought by the STFT module                   Freiburg dataset, for patients with a 1-hour preictal interval durations,
is of substantial practical significance. These statistical results fur-          the Acc without DCCN is below 70.00%, whereas with DCCN, it ex-
ther confirm that incorporating the STFT module into the model can                ceeds 80.00%, highlighting the significant benefit of DCCN for these
significantly and substantially enhance the performance.                          patients. For patients with 2-hour preictal interval durations, DCCN
    We explored the performance of the dilated causal convolution                 also contributes significantly to accuracy improvement. Similarly, in
networks (DCCN) with and without its application across different                 the CHB-MIT dataset, some patients with 1 and 2-hour preictal interval
datasets and for preictal interval durations of 1 and 2 h. The event-level        durations also experience a notable impact from DCCN. Overall, across
results of our method show a strong alignment with the segment-level              all datasets and patients, accuracy with DCCN is consistently higher
outcomes, as demonstrated by the various metrics and performance                  than without, demonstrating that DCCN improves the comprehensive
indicators. Specifically, better results at the event-based level are as-         effectiveness.
sociated with better outcomes at the segment-based level. Since the                   Paired t-tests was performed to validate the effectiveness of the
accuracy metric at the segment level is inferred from other metrics,              DCCN module. The result as shown in Table 9 confirmed that integrat-
it effectively evaluates the performance of our method. To clearly                ing the DCCN module significantly improved model accuracy across


Y. Qu et al.                                                                                                     Journal of Neuroscience Methods 428 (2026) 110665


                Fig. 5. Comparison of accuracy results with and without DCCN in the preictal interval durations of 1 and 2 h on two datasets.


                 Fig. 6. Comparison of accuracy results with and without CA in the preictal interval durations of 1 and 2 h on two datasets.


Table 9                                                                           between with and without CA is relatively consistent across datasets,
Details of the statistical significance with and without DCCN.                    indicating a similar impact of CA on intracranial and scalp EEG data.
 Experiment              t-Statistic          p-Value              Cohen_d        For patients 1 and 13 in the Freiburg dataset with a preictal interval
 burg_1h                 3.61                 1.75E−03             0.79           durations of 1 h, CA contributes significantly to accuracy improvement.
 burg_2h                 6.6                  8.48E−06             1.65           Similarly, in the CHB-MIT dataset, some patients show substantial
 chb_1h                  4.81                 1.62E−04             1.13           benefits from CA for preictal interval durations of 1 and 2 h. Over-
 chb_2h                  6.34                 2.56E−05             1.69
                                                                                  all, across all patients and datasets, accuracy with CA consistently
                                                                                  exceeds accuracy without CA, demonstrating that CA improves the
                                                                                  comprehensive effectiveness.
all experimental conditions (all p< 0.001). The improvements were                     Statistical analysis with and without CA confirmed that integrating
substantiated by large to very large effect sizes (Cohen_d: 0.79–1.69),           the CA module significantly improved model accuracy across all experi-
indicating both statistical significance and practical relevance. These           mental conditions (all p< 0.001), and Cohens_d in 1.01–1.98, as shown
results demonstrate that the DCCN module consistently enhances the                in Table 10. These results demonstrate that the CA module consistently
performance.                                                                      enhances the performance.
    Causal attention (CA) is another crucial component of our method.                 Finally, we explored the impact of varying the number of dilated
The objective of this study is to assess how the presence or absence              causal convolutions (DCCs) on the overall method and investigated the
of CA affects performance across various datasets for preictal interval           performance differences among different numbers of DCCs for preictal
durations of 1 and 2 h. We compared accuracy results with and without             interval durations of 1 and 2 h across different datasets. We compared
CA on both the two datasets for preictal interval durations of 1 and 2 h,         accuracy results for different numbers of DCCs on the two datasets for
as shown in Fig. 6.                                                               preictal interval durations of 1 and 2 h, as shown in Fig. 7. To more
    The experimental results in Fig. 6 demonstrate that for both datasets         clearly illustrate the trend in results across different numbers of DCCs
used and for preictal periods of 1 h and 2 h, the average accuracy                used, the accuracy results in this experiment represent the average
achieved with CA is higher than that without CA. The performance gap              accuracy across all patients.


Y. Qu et al.                                                                                                         Journal of Neuroscience Methods 428 (2026) 110665


        Fig. 7. Comparison of accuracy results for different numbers of dilated causal convolutions in the preictal intervals of 1 and 2 h on two datasets.


Table 10                                                                             extract information from the current data and its surrounding context
Details of the statistical significance with and without CA.                         to continuously learn. Compared to attention methods, convolutional
 Experiment               t-Statistic          p-Value               Cohen_d         networks learn more localized data. However, their advantage is that it
 burg_1h                  4.61                 1.70E−04              1.01            can focus more intently on the features of surrounding data, extracting
 burg_2h                  7.93                 9.64E−07              1.98            more effective features from the neighborhood. To clearly demonstrate
 chb_1h                   5.89                 1.80E−05              1.39
                                                                                     the local features extracted by the convolutional network, we present
 chb_2h                   4.35                 7.93E−04              1.16
                                                                                     feature visualizations before and after the convolutional network mod-
                                                                                     ule, as shown in Fig. 8A and 8B. The selected displayed data is the
                                                                                     first test data segment from patient 1 in the Freiburg dataset. As shown
   Fig. 7 shows that for 1 to 3 DCCs, whether in the Freiburg or CHB-                in the figure, the convolutional network extracts a large number of
MIT datasets and for both preictal interval durations of 1 and 2 h,                  data columns into dozens of columns, significantly enhancing feature
accuracy generally increases with the number of DCCs. However, for                   discrimination compared to the input module. However, this module is
3 to 6 DCCs, there is some fluctuation in the Freiburg dataset, but                  limited to local feature extraction.
the overall trend indicates that accuracy decreases with more DCCs.                      Causal attention networks can attend to all features, enabling them
A preictal interval durations of 2 h in the CHB-MIT dataset, accuracy is             to effectively extract global features. The causal attention network
highest with 4 DCCs. Considering the results across different datasets               module performs further global feature extraction on the pre-extracted
and preictal interval durations, our final method uses 3 DCCs, meaning               local features, enabling the model to better capture effective features.
the DCCN is composed of three layers of DCCs.                                        Fig. 8B and 8C illustrate the feature changes before and after the causal
                                                                                     attention network module. As shown in the figure, compared to the
4. Discussion                                                                        features before inputting the causal attention network module, the
                                                                                     features after the causal attention network module are more significant.
    Epilepsy patients suffer both physically and mentally, and bear a                Moreover, the attention mechanism can effectively reference these
heavy economic burden. Better epilepsy prediction can help patients                  features to better enhance the ability of epilepsy prediction.
reshape their lives. The method we proposed use dilated causal convo-                    Regarding the comparison between our approach and other meth-
lution and Causal attention fully capture the EEG signals, and a double-             ods, we discuss it at both the segmentation-based and event-based
layer dynamic window can better predict seizure. This section discusses              levels. At the segment-based level, comparing our method with the
our proposed model, which extracts local features through the con-                   several existing advanced methods using the two datasets. Table 11
volutional networks and global features through the causal attention                 shows the detailed comparison. With respect to the precise differen-
networks. This section evaluates existing methods from segment-based                 tiation between the interictal and preictal phases, the Freiburg dataset
and event-based views, highlighting the strengths of our approach. It                generally outperform those from the CHB-MIT dataset, indicating that
also outlines current limitations and future research directions.                    intracranial EEG data can more effectively compared to scalp EEG data.
    Primarily, to better explain the specific functions of multiple mod-             In the Freiburg dataset, Zhang et al. (2015) used a gradient boosting
ules in the model, we will further discuss the convolutional network                 method to achieve Acc, Sen, and Spe of 95.75%, 91.01%, and 95.77%
module and the causal attention network module. The convolutional                    respectively. This approach constructs a strong classifier from multiple
network module consists of inflated convolutional networks and con-                  weak classifiers, resulting in better classification. Geng et al. (2020)
volutional neural networks. Its core objective is to fuse local features             utilized BiLSTM and S-transform to achieve sensitivity and specificity
across the time domain, frequency domain, and channel domain. Due to                 of 98.09%, 98.69% respectively. This demonstrates that transforming
the inherent characteristics of convolutional networks, they primarily               EEG data into time–frequency features and applying deep learning


Y. Qu et al.                                                                                                                   Journal of Neuroscience Methods 428 (2026) 110665


                                                                      Fig. 8. Data features before and after modules.


Table 11
Segment-based level comparison with the existing advanced methods.
    Authors                               Year             Dataset              Method                          Acc (%)          Sen (%)           Spe (%)            Fpr (/h)
    Zhang et al. (2015)                   2015                                  Gradient boosting               95.75            91.01             95.77              –
    Zhou et al. (2018)                    2018                                  CNN                             96.70            96.70             96.80              –
    Geng et al. (2020)                    2020                                  BiLSTM with S-transform         –                98.09             98.69              –
    Wang et al. (2022b)                   2022             Freiburg             1D-CNN                          95.13            86.23             96.00              –
    Xu et al. (2023)                      2023                                  CNN-BiGRU                       98.35            93.68             –                  0.3970
    Wang et al. (2024)                    2024                                  CNN-LSTM                        93.50            88.10             94.00              –
    Ours                                  2025                                  CANet                           96.12            93.87             98.37              0.0163
    Toraman (2020)                        2020                                  CNN and SVM                     91.05            92.32             89.76              –
    Sun et al. (2021)                     2021                                  CADCNN                          –                97.10             95.60              0.0290
    Yang et al. (2021)                    2021                                  RDANet                          92.07            89.33             93.02              –
    Dissanayake et al. (2021)             2022             CHB-MIT              GDL                             95.38            94.47             94.16              –
    Assali et al. (2023)                  2023                                  CNN                             94.50            92.80             –                  –
    Ahmad et al. (2024)                   2024                                  MCNNN-AT-Bi                     91.39            91.30             90.06              0.1200
    Ours                                  2025                                  CANet                           95.09            93.95             96.23              0.0377
    Acc: Accuracy; Sen: Sensitivity; Spe: Specificity; Fpr: False prediction rate;
    Highlighted indicates the best-performing.


models improves differentiation between interictal and preictal stages,                          (2023) introduced the spatio-temporal causal neural network (STCNN),
resulting in excellent epilepsy prediction performance. Zhou et al.                              which employs dilated causal convolutions to model causal dependen-
(2018) achieved the Acc, Sen and Spe of 96.70%, 96.70%, 96.80%                                   cies in EEG time series, delivering strong performance across multiple
respectively, with a CNN method. Besides, some studies (Xu et al.,                               datasets. Despite these advances, limitations remain: STCNN does not
2023; Wang et al., 2024) have combined CNN with other methods,                                   incorporate advanced mechanisms such as attention modules, and its
also attained favorable results. Similarly, in the CHB-MIT dataset,                              modeling of local and global causal relationships is insufficient. Future
studies combined CNN with other methods achieved a maximum Sen                                   improvements could integrate graph neural networks and multi-modal
and Spe of 97.10%, 95.60% respectively (Sun et al., 2021; Toraman,                               data to enhance predictive accuracy.
2020; Ahmad et al., 2024). This indicates that appropriately combining                               However, it is meaningless that in our experiments where the
multiple methods can leverage their respective advantages and enhance                            preictal interval duration was set to 2 h, our method demonstrated
the performance of epilepsy prediction. Compared to those methods,                               strong performance with an APT exceeding that of commonly used
our model effectively integrates various methods and makes full use                              antiepileptic drugs. This indicates that our approach holds promise for
of the features in both the time–frequency domain and the channel                                preventing seizures. Compared to previous studies, our method not only
domain. Based on the evaluation using Acc, Sen, Spe, and Fpr, our                                integrates features from different levels such as time–frequency and
model outperforms the existing advanced methods.                                                 channels but also utilizes dilated causal convolutions to capture local
    Subsequently, at the event-based level, we compared our approach                             causal features and causal attention to capture global causal features,
with the existing advanced methods across the two datasets. Table 12                             thereby leveraging their respective advantages effectively. Based on
shows the detailed results. Epilepsy prediction research has primarily                           the evaluation of SEN and low FAR, the experimental results show
evolved along three methodological pathways: threshold analysis, ma-                             that the method we proposed has achieved better epilepsy prediction
chine learning, and deep learning. Hung et al. (2010) developed an au-                           performance. As shown in Tables 11 and Tables 12, our approach
tonomous prediction system based on wavelet transform and chaos the-                             outperforms most of the previous methods.
ory, achieving a SEN of 86.96% and a FAR of 0.2500/h. Their key inno-                                As to the Freiburg and CHB-MIT datasets, our method achieves
vation was the introduction of nonlinear energy operators as novel fea-                          high performance. Its APT surpasses the onset time of commonly used
tures. Eftekhar et al. (2014) further enhanced performance by applying                           antiepileptic drugs, suggesting strong potential for effective seizure
threshold-crossing techniques, yielding a SEN of 90.95% and reducing                             prevention. However, our proposed approach has not been evaluated
FAR to 0.0600/h, thereby demonstrating the robustness of threshold-                              the predictive performance on other datasets, and further validation
based approaches. In studies (Sharif and Jafari, 2017; Yang et al.,                              is required to determine its generalization capability. In real-world
2018), support vector machine (SVM) models achieved SEN between                                  applications, an increased number of electrodes may lead to greater
91.80% and 96.60%, with FAR maintained within 0.0500–0.1100/h,                                   patient discomfort. We have not explored strategies for achieving re-
underscoring their effectiveness in feature classification tasks. Recently,                      liable epilepsy prediction using fewer electrodes while maintaining
deep learning methods have gained prominence due to their superior                               high performance. Current epilepsy seizure prediction systems do not
feature extraction capabilities. As summarized in Table 12, LSTM- and                            meet the accuracy standards needed to generate reliable pre-seizure
CNN-based approaches report SEN ranging from 87.80% to 100.00%,                                  medication alerts. Additionally, there is still no clinically advanced
with FAR varying between 0.0500 and 1.6000/h. Notably, Zhang et al.                              early-warning system available for this application.


Y. Qu et al.                                                                                                                        Journal of Neuroscience Methods 428 (2026) 110665


Table 12
Event-based level comparison with the existing advanced methods.
    Authors                                 Year               Dataset               Method                                                SEN (%)                      FAR (/h)
    Hung et al. (2010)                      2010                                     wavelet and chaos theory                              86.96                        0.2500
    Eftekhar et al. (2014)                  2014                                     Threshold crossing                                    90.95                        0.0600
    Sharif and Jafari (2017)                2017                                     SVM                                                   91.80–96.60                  0.0500–0.0800
    Yang et al. (2018)                      2018                                     SVM                                                   94.00                        0.1100
                                                               Freiburg
    Shokouh Alaei et al. (2019)             2019                                     Phase synchronization                                 100.00                       0.1300
    Zhang et al. (2020b)                    2020                                     gradient boosting                                     91.67                        0.1000
    Wang et al. (2022a)                     2023                                     1D-CNNs                                               98.65–100.00                 0.0800–0.1200
    Ours                                    2025                                     CANet                                                 100.00                       0.0077
    Khan et al. (2017)                      2018                                     CNN                                                   87.80                        0.1420
    Affes et al. (2019)                     2019                                     CGRNN                                                 89.00                        1.6000
    Zhang et al. (2020a)                    2020                                     CNN                                                   92.90                        0.1500
    Yu et al. (2022)                        2022                                     MLSTM                                                 89.47                        0.3400
    Li et al. (2021)                        2022               CHB-MIT               STS-HGCN-AL                                           95.50                        0.1090
    Gao et al. (2023)                       2023                                     MSPPNet                                               93.80                        0.0540
    Zhang et al. (2023)                     2023                                     STCNN                                                 98.13                        0.1500
    Liu et al. (2024)                       2024                                     P3DCNN-BiConvLstm3D-Attention3D                       98.03                        –
    Ours                                    2025                                     CANet                                                 97.06                        0.0251
1   SEN: the percentage of correctly predicted warnings among all seizure episodes; FAR: total false alarms produced by the epilepsy alert system per hour.
2   Highlighted indicates the best-performing.


    Future research will use diverse datasets to test the method’s gener-                     Acknowledgments
alizability and predictive performance. We will investigate how channel
count affects epilepsy prediction accuracy and whether fewer channels                             This work was supported in part by the Natural Science Founda-
can still produce reliable results. We are currently focusing on epilepsy                     tion of China (Grant Nos. 62176177 and 62576240), and the Science
prediction research for patient-specific. In future work, we will conduct                     and Technology Cooperation and Exchange Special Projects of Shanxi
cross-patient epilepsy prediction research, try to develop an epilepsy                        (Grant No. 202304041101034).
prediction algorithm model that is applicable to cross-patients, and try
to alleviate the problem of excessive differences in EEG signals between                      Data availability
different patients.
                                                                                                  Data will be made available on request.
5. Conclusion

                                                                                              References
    We propose a method that employs a causal attention network
combined with time, frequency, and channel feature fusion. We use                             Affes, A., Mdhaffar, A., Triki, C., Jmaiel, M., Freisleben, B., 2019. A convolutional gated
dilated causal convolutions and standard convolutions to perform local                            recurrent neural network for epileptic seizure prediction. In: International Confer-
feature extraction and fusion across the time, frequency, and channel                             ence on Smart Homes and Health Telematics. Springer International Publishing
domains. This allows the fused data to retain important information                               Cham, pp. 85–96.
                                                                                              Ahmad, I., Zhu, M., Liu, Z., Shabaz, M., Ullah, I., Tong, M.C.F., Sambas, A., Men, L.,
across these three dimensions. Subsequently, causal attention is em-
                                                                                                  Chen, Y., Chen, S., 2024. Multi-feature fusion-based convolutional neural networks
ployed to extract global causal features, further enabling the automatic                          for eeg epileptic seizure prediction in consumer internet of things. IEEE Trans.
extraction of more significant information. For the Freiburg intracranial                         Consum. Electron. 70 (3), 5631–5643.
EEG dataset, our method achieved 100.00% and 96.67% SEN with                                  Anugraha, A., Vinotha, E., Anusha, R., Giridhar, S., Narasimhan, K., 2017. A ma-
                                                                                                  chine learning application for epileptic seizure detection. In: 2017 International
0.0077/h and 0.0472/h FAR respectively for 1 h and 2 h durations of
                                                                                                  Conference on Computational Intelligence in Data Science. ICCIDS, IEEE, pp. 1–4.
preictal periods. For the CHB-MIT scalp EEG dataset, it attained 97.06%                       Aschenbrenner-Scheibe, R., Maiwald, T., Winterhalder, M., Voss, H.U., Timmer, J.,
and 92.31% SEN with 0.0251/h and 0.0666/h FAR respectively for                                    Schulze-Bonhage, A., 2003. How well can epileptic seizures be predicted? an
1 h and 2 h duration of preictal periods. The APT were 97.59 and                                  evaluation of a nonlinear method. Brain 126 (12), 2616–2626.
94.85 min for the two datasets, respectively. The method proposed                             Assali, I., Blaiech, A.G., Abdallah, A.B., Khalifa, K.B., Carrere, M., Bedoui, M.H., 2023.
                                                                                                  Cnn-based classification of epileptic states for seizure prediction using combined
in this study enhances the Sen, reduces the FAR, and improves the                                 temporal and spectral features. Biomed. Signal Process. Control. 82, 104519.
prediction timeliness compared to existing solutions by optimizing the                        Bhattacharya, A., Baweja, T., Karri, S., 2022. Epileptic seizure prediction using deep
algorithm model. Which is of great significance for improving the                                 transformer model. Int. J. Neural Syst. 32 (02), 2150058.
prognosis of patients.                                                                        Bi, J., Wang, F., Ping, J., Qu, G., Hu, F., Li, H., Han, S., 2024. Fbn-tcn: Temporal
                                                                                                  convolutional neural network based on spatial domain fusion brain networks for
                                                                                                  affective brain–computer interfaces. Biomed. Signal Process. Control. 94, 106323.
CRediT authorship contribution statement                                                      Brophy, G.M., Bell, R., Claassen, J., Alldredge, B., Bleck, T.P., Glauser, T.,
                                                                                                  LaRoche, S.M., Riviello Jr., J.J., Shutter, L., Sperling, M.R., et al., 2012. Guidelines
                                                                                                  for the evaluation and management of status epilepticus. Neurocritical Care 17 (1),
    Yimin Qu: Writing – original draft, Formal analysis. Songhui Rao:
                                                                                                  3–23.
Writing – original draft, Formal analysis. Ting Li: Formal analysis. Ying                     Bruno, E., Viana, P.F., Sperling, M.R., Richardson, M.P., 2020. Seizure detection at
Li: Formal analysis. Yan Niu: Formal analysis. Ruiyun Chang: Formal                               home: Do devices on the market match the needs of people living with epilepsy
analysis. Xianchuan Chen: Formal analysis. Bin Wang: Writing –                                    and their caregivers? Epilepsia 61, S11–S24.
review & editing, Supervision, Project administration.                                        Cook, M.J., O’Brien, T.J., Berkovic, S.F., Murphy, M., Morokoff, A., Fabinyi, G.,
                                                                                                  D’Souza, W., Yerra, R., Archer, J., Litewka, L., et al., 2013. Prediction of seizure
                                                                                                  likelihood with a long-term, implanted seizure advisory system in patients with
Declaration of competing interest                                                                 drug-resistant epilepsy: a first-in-man study. Lancet Neurol. 12 (6), 563–571.
                                                                                              Dalic, L., Cook, M.J., 2016. Managing drug-resistant epilepsy: challenges and solutions.
                                                                                                  Neuropsychiatr. Dis. Treat. 2605–2616.
    The authors declare that they have no known competing finan-
                                                                                              Dissanayake, T., Fernando, T., Denman, S., Sridharan, S., Fookes, C., 2021. Geometric
cial interests or personal relationships that could have appeared to                              deep learning for subject independent epileptic seizure prediction using scalp eeg
influence the work reported in this paper.                                                        signals. IEEE J. Biomed. Health Inform. 26 (2), 527–538.


Y. Qu et al.                                                                                                                              Journal of Neuroscience Methods 428 (2026) 110665


Eftekhar, A., Juffali, W., El-Imad, J., Constandinou, T.G., Toumazou, C., 2014. Ngram-              Park, Y., Luo, L., Parhi, K.K., Netoff, T., 2011. Seizure prediction with spectral power
     derived pattern recognition for the detection and prediction of epileptic seizures.                of eeg using cost-sensitive support vector machines. Epilepsia 52 (10), 1761–1770.
     PLoS One 9 (6), e96235.                                                                        Patsalos, P.N., Berry, D.J., Bourgeois, B.F., Cloyd, J.C., Glauser, T.A., Johannessen, S.I.,
Fan, J., Yang, J., Zhang, X., Yao, Y., 2022. Real-time single-channel speech                            Leppik, I.E., Tomson, T., Perucca, E., 2008. Antiepileptic drugs–best practice
     enhancement based on causal attention mechanism. Appl. Acoust. 201, 109084.                        guidelines for therapeutic drug monitoring: a position paper by the subcommission
Fisher, R.S., Vickrey, B.G., Gibson, P., Hermann, B., Penovich, P., Scherer, A.,                        on therapeutic drug monitoring, ilae commission on therapeutic strategies. Epilepsia
     Walker, S., 2000. The impact of epilepsy from the patient’s perspective i.                         49 (7), 1239–1276.
     descriptions and subjective perceptions. Epilepsy Res. 41 (1), 39–51.                          Peng, P., Song, Y., Yang, L., Wei, H., 2022. Seizure prediction in eeg signals using stft
Gao, Y., Chen, X., Liu, A., Liang, D., Wu, L., Qian, R., Xie, H., Zhang, Y., 2022. Pediatric            and domain adaptation. Front. Neurosci. 15, 825434.
     seizure prediction in scalp eeg using a multi-scale neural network with dilated                Pinto, M.F., Leal, A., Lopes, F., Dourado, A., Martins, P., Teixeira, C.A., 2021. A
     convolutions. IEEE J. Transl. Eng. Health Med. 10, 1–9.                                            personalized and evolutionary algorithm for interpretable eeg epilepsy seizure
Gao, Y., Liu, A., Wang, L., Qian, R., Chen, X., 2023. A self-interpretable deep learning                prediction. Sci. Rep. 11 (1), 3415.
     model for seizure prediction using a multi-scale prototypical part network. IEEE               Rao, S., Liu, M., Huang, Y., Yang, H., Liang, J., Lu, J., Niu, Y., Wang, B., 2024.
     Trans. Neural Syst. Rehabil. Eng. 31, 1847–1856.                                                   Anchoring temporal convolutional networks for epileptic seizure prediction. J.
Geng, M., Zhou, W., Liu, G., Li, C., Zhang, Y., 2020. Epileptic seizure detection based on              Neural Eng. 21 (6), 066008.
     stockwell transform and bidirectional long short-term memory. IEEE Trans. Neural               Shah, A., Kadam, E., Shah, H., Shinde, S., Shingade, S., 2016. Deep residual networks
     Syst. Rehabil. Eng. 28 (3), 573–580.                                                               with exponential linear unit. In: Proceedings of the Third International Symposium
Glauser, T., Shinnar, S., Gloss, D., Alldredge, B., Arya, R., Bainbridge, J., Bare, M.,                 on Computer Vision and the Internet. pp. 59–65.
     Bleck, T., Dodson, W.E., Garrity, L., et al., 2016. Evidence-based guideline:                  Sharif, B., Jafari, A.H., 2017. Prediction of epileptic seizures from eeg using analysis
     treatment of convulsive status epilepticus in children and adults: report of the                   of ictal rules on poincaré plane. Comput. Methods Programs Biomed. 145, 11–22.
     guideline committee of the American epilepsy society. Epilepsy Curr. 16 (1), 48–61.            Shokouh Alaei, H., Khalilzadeh, M.A., Gorji, A., 2019. Optimal selection of sop and
Guo, L., Yu, T., Zhao, S., Li, X., Liao, X., Li, Y., 2023. Clep: Contrastive learning for               sph using fuzzy inference system for on-line epileptic seizure prediction based on
     epileptic seizure prediction using a spatio-temporal-spectral network. IEEE Trans.                 eeg phase synchronization. Australas. Phys. Eng. Sci. Med. 42 (4), 1049–1068.
     Neural Syst. Rehabil. Eng. 31, 3915–3926.                                                      Sun, B., Lv, J.-J., Rui, L.-G., Yang, Y.-X., Chen, Y.-G., Ma, C., Gao, Z.-K., 2021. Seizure
Hu, S., Liu, J., Yang, R., Wang, Y., Wang, A., Li, K., Liu, W., Yang, C., 2023.                         prediction in scalp eeg based channel attention dual-input convolutional neural
     Exploring the applicability of transfer learning and feature engineering in epilepsy               network. Phys. A 584, 126376.
     prediction using hybrid transformer model. IEEE Trans. Neural Syst. Rehabil. Eng.              Tetzlaff, R., Senger, V., 2012. The seizure prediction problem in epilepsy: Cellular
     31, 1321–1332.                                                                                     nonlinear networks. IEEE Circuits Syst. Mag. 12 (4), 8–20.
Hu, M., Zhang, C., Xiao, X., Guo, J., Sun, H., 2020. Effect of intensive self-management            Toraman, S., 2020. Preictal and interictal recognition for epileptic seizure prediction
     education on seizure frequency and quality of life in epilepsy patients with                       using pre-trained 2dcnn models. Trait. Du Signal 37 (6).
     prodromes or precipitating factors. Seizure 78, 38–42.                                         Trinka, E., Cock, H., Hesdorffer, D., Rossetti, A.O., Scheffer, I.E., Shinnar, S.,
Hung, S.-H., Chao, C.-F., Wang, S.-K., Lin, B.-S., Lin, C.-T., 2010. Vlsi implementation                Shorvon, S., Lowenstein, D.H., 2015. A definition and classification of status
     for epileptic seizure prediction system based on wavelet and chaos theory. In:                     epilepticus–report of the ilae task force on classification of status epilepticus.
     TENCON 2010-2010 IEEE Region 10 Conference. IEEE, pp. 364–368.                                     Epilepsia 56 (10), 1515–1523.
Ji, D., He, L., Dong, X., Li, H., Zhong, X., Liu, G., Zhou, W., 2024. Epileptic seizure             Truong, N.D., Kuhlmann, L., Bonyadi, M.R., Querlioz, D., Zhou, L., Kavehei, O., 2019.
     prediction using spatiotemporal feature fusion on eeg. Int. J. Neural Syst. 34 (08),               Epileptic seizure forecasting with generative adversarial networks. Ieee Access 7,
     2450041.                                                                                           143999–144009.
Jia, F., Lei, Y., Lin, J., Zhou, X., Lu, N., 2016. Deep neural networks: A promising tool           Truong, N.D., Nguyen, A.D., Kuhlmann, L., Bonyadi, M.R., Yang, J., Ippolito, S.,
     for fault characteristic mining and intelligent diagnosis of rotating machinery with               Kavehei, O., 2018. Convolutional neural networks for seizure prediction using
     massive data. Mech. Syst. Signal Process. 72, 303–315.                                             intracranial and scalp electroencephalogram. Neural Netw. 105, 104–111.
Johannessen Landmark, C., Johannessen, S.I., Patsalos, P.N., 2020. Therapeutic drug                 Usman, S.M., Khalid, S., Aslam, M.H., 2020. Epileptic seizures prediction using deep
     monitoring of antiepileptic drugs: current status and future prospects. Expert. Opin.              learning techniques. Ieee Access 8, 39998–40007.
     Drug Metab. Toxicol. 16 (3), 227–238.                                                          Wang, X., Gao, Z., Zhang, M., Wang, Y., Yang, L., Lin, J., Kärkkäinen, T., Cong, F.,
Khan, H., Marcuse, L., Fields, M., Swann, K., Yener, B., 2017. Focal onset seizure                      2024. Combination of channel reordering strategy and dual cnn-lstm for epileptic
     prediction using convolutional networks. IEEE Trans. Biomed. Eng. 65 (9),                          seizure prediction using three ieeg datasets. IEEE J. Biomed. Health Inform..
     2109–2118.                                                                                     Wang, Y., Ma, X., Chen, Z., Luo, Y., Yi, J., Bailey, J., 2019. Symmetric cross entropy
Kuhlmann, L., Lehnertz, K., Richardson, M.P., Schelter, B., Zaveri, H.P., 2018. Seizure                 for robust learning with noisy labels. In: Proceedings of the IEEE/CVF International
     prediction—ready for a new era. Nat. Rev. Neurol. 14 (10), 618–630.                                Conference on Computer Vision. pp. 322–330.
Li, Y., Liu, Y., Guo, Y.-Z., Liao, X.-F., Hu, B., Yu, T., 2021. Spatio-temporal-spectral            Wang, Y., Shi, Y., Cheng, Y., He, Z., Wei, X., Chen, Z., Zhou, Y., 2022a. A spatiotemporal
     hierarchical graph convolutional network with semisupervised active learning for                   graph attention network based on synchronization for epileptic seizure prediction.
     patient-specific seizure prediction. IEEE Trans. Cybern. 52 (11), 12189–12204.                     IEEE J. Biomed. Health Inform. 27 (2), 900–911.
Litt, B., Echauz, J., 2002. Prediction of epileptic seizures. Lancet Neurol. 1 (1), 22–30.          Wang, X., Wang, X., Liu, W., Chang, Z., Kärkkäinen, T., Cong, F., 2021. One dimensional
Litt, B., Esteller, R., Echauz, J., D’Alessandro, M., Shor, R., Henry, T., Pennell, P.,                 convolutional neural networks for seizure onset detection using long-term scalp and
     Epstein, C., Bakay, R., Dichter, M., et al., 2001. Epileptic seizures may begin hours              intracranial eeg. Neurocomputing 459, 212–222.
     in advance of clinical onset: a report of five patients. Neuron 30 (1), 51–64.                 Wang, X., Zhang, C., Kärkkäinen, T., Chang, Z., Cong, F., 2022b. Channel increment
Liu, X., Li, C., Lou, X., Kong, H., Li, X., Li, Z., Zhong, L., 2024. Epileptic seizure pre-             strategy-based 1d convolutional neural networks for seizure prediction using
     diction based on eeg using pseudo-three-dimensional cnn. Front. Neuroinformatics                   intracranial eeg. IEEE Trans. Neural Syst. Rehabil. Eng. 31, 316–325.
     18, 1354436.                                                                                   Xiong, W., Stirling, R.E., Payne, D.E., Nurse, E.S., Kameneva, T., Cook, M.J., Viana, P.F.,
Long, T., Gao, Q., Xu, L., Zhou, Z., 2022. A survey on adversarial attacks in computer                  Richardson, M.P., Brinkmann, B.H., Freestone, D.R., et al., 2023. Forecasting seizure
     vision: Taxonomy, visualization and future directions. Comput. Secur. 121, 102847.                 likelihood from cycles of self-reported events and heart rate: a prospective pilot
Lopes, F., Leal, A., Pinto, M.F., Dourado, A., Schulze-Bonhage, A., Dümpelmann, M.,                     study. EBioMedicine 93.
     Teixeira, C., 2023. Removing artefacts and periodically retraining improve per-                Xu, Y., Cheng, J., Wang, L., Xia, H., Liu, F., Tao, D., 2018. Ensemble one-dimensional
     formance of neural network-based seizure prediction models. Sci. Rep. 13 (1),                      convolution neural networks for skeleton-based action recognition. IEEE Signal
     5918.                                                                                              Process. Lett. 25 (7), 1044–1048.
Ma, X., Yu, N., Zhou, W., 2019. Using dictionary pair learning for seizure detection.               Xu, J., Wang, J., Liu, J.-X., Shang, J., Dai, L., Yan, K., Yuan, S., 2023. Epileptic
     Int. J. Neural Syst. 29 (04), 1850005.                                                             seizure detection based on feature extraction and cnn-bigru network with attention
Maiwald, T., Winterhalder, M., Aschenbrenner-Scheibe, R., Voss, H.U., Schulze-                          mechanism. In: International Conference on Intelligent Computing. Springer, pp.
     Bonhage, A., Timmer, J., 2004. Comparison of three nonlinear seizure prediction                    308–319.
     methods by means of the seizure prediction characteristic. Phys. D: Nonlinear                  Yadav, S.P., Zaidi, S., Mishra, A., Yadav, V., 2022. Survey on machine learning in
     Phenom. 194 (3–4), 357–368.                                                                        speech emotion recognition and vision systems using a recurrent neural network
Meirinho, S., Rodrigues, M., Fortuna, A., Falcão, A., Alves, G., 2021. Liquid chro-                     (rnn). Arch. Comput. Methods Eng. 29 (3), 1753–1770.
     matographic methods for determination of the new antiepileptic drugs stiripentol,              Yang, X., Zhao, J., Sun, Q., Lu, J., Ma, X., 2021. An effective dual self-attention
     retigabine, rufinamide and perampanel: a comprehensive and critical review. J.                     residual network for seizure prediction. IEEE Trans. Neural Syst. Rehabil. Eng. 29,
     Pharm. Anal. 11 (4), 405–421.                                                                      1604–1613.
Ozdemir, M.A., Cura, O.K., Akan, A., 2021. Epileptic eeg classification by using                    Yang, Y., Zhou, M., Niu, Y., Li, C., Cao, R., Wang, B., Yan, P., Ma, Y., Xiang, J.,
     time-frequency images for deep learning. Int. J. Neural Syst. 31 (08), 2150026.                    2018. Epileptic seizure prediction based on permutation entropy. Front. Comput.
Park, C., Choi, G., Kim, J., Kim, S., Kim, T.-J., Min, K., Jung, K.-Y., Chong, J.,                      Neurosci. 12, 55.
     2018. Epileptic seizure detection for multi-channel eeg with deep convolutional                Yu, Z., Albera, L., Le Bouquin Jeannes, R., Kachenoura, A., Karfoul, A., Yang, C.,
     neural network. In: 2018 International Conference on Electronics, Information, and                 Shu, H., 2022. Epileptic seizure prediction using deep neural networks via transfer
     Communication. ICEIC, IEEE, pp. 1–5.                                                               learning and multi-feature fusion. Int. J. Neural Syst. 32 (07), 2250032.


Y. Qu et al.                                                                                                                             Journal of Neuroscience Methods 428 (2026) 110665


Yuan, S., Liu, J., Shang, J., Xu, F., Dai, L., Kong, X., 2020. Automatic seizure prediction        Zhang, Y., Li, X., Wang, S., Shen, H., Huang, K., 2023. A robust seizure detection and
   based on modified stockwell transform and tensor decomposition. In: 2020 IEEE                      prediction method with feature selection and spatio-temporal casual neural network
   International Conference on Bioinformatics and Biomedicine. BIBM, IEEE, pp.                        model. J. Neural Eng. 20 (5), 056036.
   1503–1509.                                                                                      Zhang, Y., Yang, R., Zhou, W., 2020b. Roughness-length-based characteristic analysis
Zhang, S., Chen, D., Ranjan, R., Ke, H., Tang, Y., Zomaya, A.Y., 2020a. A lightweight                 of intracranial eeg and epileptic seizure prediction. Int. J. Neural Syst. 30 (12),
   solution to epileptic seizure prediction based on eeg synchronization measurement.                 2050072.
   J. Supercomput.                                                                                 Zhang, Y., Zhou, W., Yuan, S., Yuan, Q., 2015. Seizure detection method based on
Zhang, Y., Guo, Y., Yang, P., Chen, W., Lo, B., 2019. Epilepsy seizure prediction on eeg              fractal dimension and gradient boosting. Epilepsy Behav. 43, 30–38.
   using common spatial pattern and convolutional neural network. IEEE J. Biomed.                  Zhou, M., Tian, C., Cao, R., Wang, B., Niu, Y., Hu, T., Guo, H., Xiang, J., 2018. Epileptic
   Health Informatics 24 (2), 465–474.                                                                seizure detection based on eeg signals and cnn. Front. Neuroinformatics 12, 95.
```
