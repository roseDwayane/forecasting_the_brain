---
citation_key: "ZhengEtAl2025"
paper_id: "paper_204"
title: "EEG-based Epileptic Prediction via a Two-stage Channel-aware Set Transformer Network"
authors: "Ruifeng Zheng; Cong Chen; Shuang Wang; Yiming Liu; Lin You; Jindong Lu; Ruizhe Zhu; Guodao Zhang; Kejie Huang"
year: 2025
doi: ""
source: "arxiv (2507.15364)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2507.15364"
tier: 1
composite: 4.5
---

# EEG-based Epileptic Prediction via a Two-stage Channel-aware Set Transformer Network

**Citation:** `ZhengEtAl2025` · **Tier:** 1 · **Composite:** 4.5

**Source PDF:** `full_pdf/Ruifeng2025.pdf`

## Abstract

Epilepsy is a chronic, noncommunicable overhead compared to standard Transformers, was employed brain disorder, and sudden seizure onsets can significantly to organize EEG features. The reason for the selection is arXiv:2507.15364v1 [eess.SP] 21 Jul 2025 impact patients’ quality of life and health. However, wear- our observation that certain segments of the EEG signal and able seizure-predicting devices are still limited, partly due to the bulky size of EEG-collecting devices. To relieve the certain electrode channels hold greater predictive importance problem, we proposed a novel two-stage channel-aware than others, and the specific order in which they are arranged Set Transformer Network that could perform seizure pre- is less significant. The input features were merged temporally diction with fewer EEG channel sensors. We also tested a by a Set Transformer in the first stage of our network. In the seizure-independent division method which could prevent second stage, we developed a channel-aware Set Transformer the adjacency of training and test data. Experiments were performed on the CHB-MIT dataset which includes 22 pa- to process the temporally-merged features obtained from the tients with 88 merged seizures. The mean sensitivity before first stage. This channel-aware Transformer incorporated fea- channel selection was 76.4% with a false predicting rate tures from all channels and conducted patient-specific channel (FPR) of 0.09/hour. After channel selection, dominant chan- selection when the prediction results for a given patient were nels emerged in 20 out of 22 patients; the average number heavily influenced by a few specific channels. of channels was reduced to 2.8 from 18; and the mean sensitivity rose to 80.1% with an FPR of 0.11/hour. Fur- Furthermore, we tested a more rigorous method for dividing thermore, experimental results on the seizure-independent EEG data. In many previous studies, all interictal EEG signals division supported our assertion that 

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025                                                                       1


                                            EEG-based Epileptic Prediction via a Two-stage
                                              Channel-aware Set Transformer Network
                                           Ruifeng Zheng, Cong Chen, Shuang Wang, Yiming Liu, Lin You, Jindong Lu, Ruizhe Zhu, Guodao Zhang,
                                                                                  and Kejie Huang


                                              Abstract— Epilepsy is a chronic, noncommunicable                   overhead compared to standard Transformers, was employed
                                           brain disorder, and sudden seizure onsets can significantly           to organize EEG features. The reason for the selection is


arXiv:2507.15364v1 [eess.SP] 21 Jul 2025
                                           impact patients’ quality of life and health. However, wear-           our observation that certain segments of the EEG signal and
                                           able seizure-predicting devices are still limited, partly due
                                           to the bulky size of EEG-collecting devices. To relieve the           certain electrode channels hold greater predictive importance
                                           problem, we proposed a novel two-stage channel-aware                  than others, and the specific order in which they are arranged
                                           Set Transformer Network that could perform seizure pre-               is less significant. The input features were merged temporally
                                           diction with fewer EEG channel sensors. We also tested a              by a Set Transformer in the first stage of our network. In the
                                           seizure-independent division method which could prevent               second stage, we developed a channel-aware Set Transformer
                                           the adjacency of training and test data. Experiments were
                                           performed on the CHB-MIT dataset which includes 22 pa-                to process the temporally-merged features obtained from the
                                           tients with 88 merged seizures. The mean sensitivity before           first stage. This channel-aware Transformer incorporated fea-
                                           channel selection was 76.4% with a false predicting rate              tures from all channels and conducted patient-specific channel
                                           (FPR) of 0.09/hour. After channel selection, dominant chan-           selection when the prediction results for a given patient were
                                           nels emerged in 20 out of 22 patients; the average number             heavily influenced by a few specific channels.
                                           of channels was reduced to 2.8 from 18; and the mean
                                           sensitivity rose to 80.1% with an FPR of 0.11/hour. Fur-                 Furthermore, we tested a more rigorous method for dividing
                                           thermore, experimental results on the seizure-independent             EEG data. In many previous studies, all interictal EEG signals
                                           division supported our assertion that a more rigorous                 were concatenated together and then divided evenly (this
                                           seizure-independent division should be used for patients              dividing method will be referred to as “even division” in
                                           with abundant EEG recordings.                                         this article for brevity). However, the even division usually
                                             Index Terms— seizure prediction, epilepsy, Transformer,             fragments an integrated interictal sequence into pieces that
                                           electroencephalogram, channel selection                               can appear in both training and test data. Therefore, we
                                                                                                                 tested a seizure-independent division which is closer to clinical
                                                                 I. I NTRODUCTION                                practice. Among this division, an interictal EEG sequence
                                                                                                                 before a specific seizure acts as either training or test data,
                                              Epilepsy is a chronic noncommunicable brain disease that
                                                                                                                 avoiding the adjacency of training and test data.
                                           affects around fifty million people globally. [1] Approximately
                                                                                                                    Additionally, many prior studies chose to leave out four-
                                           one-third of epilepsy patients grapple with intractable epilepsy
                                                                                                                 hour EEG signals before or after seizures to constitute the
                                           [2]. The sudden onset of epilepsy contributes to anxiety in
                                                                                                                 interictal data, likely leading to alarms being triggered four
                                           patients’ daily life and may result in accidents that threaten
                                                                                                                 hours before a seizure. To mitigate this issue, our study only
                                           their health and even their lives. Effective seizure prediction
                                                                                                                 excluded one-hour data before or after seizures to form the
                                           can provide early warnings to patients, alleviating the risks
                                                                                                                 interictal data.
                                           posed by seizures. It can also prompt wearable medical devices
                                                                                                                    EEG data of patients from CHB-MIT database [7] were
                                           to initiate clinical interventions [3], [4] to suppress imminent
                                                                                                                 used in this study. Twenty-two patients were included, and 18
                                           seizure onset. Electroencephalogram (EEG) has been widely
                                                                                                                 channels shared by all patients were selected as input channels.
                                           adopted for epilepsy diagnosis due to its non-invasive nature.
                                                                                                                 Several band power features of EEG signals were chosen
                                              However, the commercial application of wearable EEG
                                                                                                                 as the key indicators for prediction. The seizure prediction
                                           collection devices is limited. This can be partly attributed to
                                                                                                                 horizon (SPH) and seizure occurrence period (SOP) were set
                                           their discomfort and inconvenience for all-day wear, especially
                                                                                                                 to three and 30 minutes, respectively. Adjacent seizures with
                                           considering their often bulky size. If the number of electrode
                                                                                                                 an interval of less than one hour were merged, and seizures
                                           channels could be reduced, the devices would be implemented
                                                                                                                 with preictal lengths significantly less than 30 minutes were
                                           with fewer sensors, leading to a smaller size, reduced power
                                                                                                                 omitted. The even division was conducted on 22 patients with
                                           consumption, and lower cost. To reduce the number of sensors,
                                                                                                                 88 merged seizures, and the seizure-independent division was
                                           we proposed a novel two-stage channel-aware Set Transformer
                                                                                                                 conducted on seven patients with 26 qualified seizures.
                                           Network which can identify dominant electrode channels for
                                                                                                                    Experiment results on the even division demonstrate that
                                           seizure prediction. Specifically, Set Transformer [5], [6], which
                                                                                                                 our two-stage channel-aware Set Transformer has achieved
                                           features permutation invariant and has a lower computational
                                                                                                                 good performance in epileptic prediction. Before channel se-
                                             Corresponding author: Kejie Huang (e-mail: huangkejie@zju.edu.cn)   lection, the mean sensitivity was 76.4% with a false predicting

2                                                                                GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025


rate of 0.09 per hour. After introducing channel selection,           while Shu et al. [23] employed a generative diffusion model for
dominant channels emerged in 20 out of 22 patients. A                 data augmentation in seizure prediction. Besides, Lopes et al.
mean sensitivity of 80.1% with an FPR of 0.11 per hour                explored the effect of using a deep convolution neural network-
were achieved after channel selection. The average number             based EEG artifact removal model [24] and tried to addressing
of channels was reduced to 2.8 after the selection, such that         data limitations in seizure prediction through transfer learning
EEG collecting devices can be implemented with smaller sizes          [25].
and less power consumption, thus increasing the popularity
among epilepsy patients. In addition, experiment results on the       B. Deep learning algorithms
seizure-independent division support our suggestion that the
                                                                         For works taking spectrograms as inputs, the convolutional
seizure-independent division should be conducted for patients
                                                                      neural network (CNN) is a typical solution for processing two-
with abundant EEG recordings.
                                                                      dimensional data and has been adopted by many studies [10]–
   In summary, our contributions are as follows:
                                                                      [16]. Some studies, such as Tsiouris et al. [9] and Singh et
   • The bulky size of EEG collecting sensors hinders the
                                                                      al. [18], utilized Long Short-Term Memory (LSTM) to further
      popularity of wearable seizure predicting devices. To
                                                                      aggregate features.
      relieve the problem, we proposed a novel two-stage
                                                                         Transformer has outperformed RNN [26] and its variants,
      channel-aware Set Transformer Network which could per-
                                                                      such as LSTM and GRU [27], in the natural language pro-
      form seizure prediction with much fewer EEG collecting
                                                                      cessing area in recent years, and it is one of the backbone
      sensors.
                                                                      algorithms of current popular large language models. Several
   • We employed low-complexity input features, and our
                                                                      solutions have been proposed to introduce Transformers into
      solution took about 33.5 ms to handle an input EEG
                                                                      seizure prediction. Affes et al. [10] and Hu et al. [28] utilized
      signal segment arriving every second, allowing for real-
                                                                      transformer-based networks to complement a domain adver-
      time monitoring and rapid response.
                                                                      sarial model and transfer learning. Li et al. [11] combined
   • Our method achieves a mean sensitivity of 80.1% with
                                                                      CNN and Transformer to extract features. Hussein et al.
      0.11 false alarms per hour on patients in the CHB-MIT
                                                                      [29] fed spectrograms directly to Transformer after position
      dataset on the even division, and the average number of
                                                                      embedding, and Yan et al. [4] transformed the spectrograms
      electrode channels reduces to 2.8 from 18 after selection.
                                                                      to three matrices before feeding them to Transformer. Further-
   The paper is structured as follows: Section II introduces
                                                                      more, Koutsouvelis et al. [30] trained a competent subject-
relevant studies about epileptic EEG signal analyses; Sec-
                                                                      specific CNN-Transformer model to identify the optimal pre-
tion III details our data preprocessing, the definition of the
                                                                      ictal period for seizure prediction.
seizure-independent division, and the structure of the two-
                                                                         In our study, we took a different approach by selecting
stage channel-aware Set Transformer network; Section IV
                                                                      several band power features as inputs and utilizing the Set
presents the experiment settings and results; limitations and a
                                                                      Transformer to process these inputs temporally and channel-
conclusion are given in Section V and Section VI, respectively.
                                                                      wisely. Set Transformer, compared to standard Transformer,
                     II. R ELATED W ORKS                              decreases the computation complexity of self-attention from
A. Input features                                                     quadratic to linear in the number of elements. Therefore, in
                                                                      our study, the need for position embedding was eliminated,
   Both time-domain and spectral-domain features have been
                                                                      and computational overhead was reduced.
widely used to analyze EEG signals. Time-domain features
utilized by Craley et al. [8] and Tsiouris et al. [9] include
mean, variance, skewness, kurtosis, zero-crossing, etc. Al-           C. Graph or channel selection
though features extracted from the time-domain are intuitive             Some studies [9], [19], [31] employed graph neural net-
for humans, they are more susceptible to noise and other              works (GCN) [32], [33] to aggregate signals from different
disturbances. On the other hand, different cerebral rhythms           channels. GCN values the connections between channels and
are classified based on their frequency range in the medical          builds Laplacian Matrices with Adjacency Matrices and De-
field, and spectral features play vital roles in classification and   gree Matrices so that features can diffuse between channels.
prediction tasks based on EEG data. Time–frequency features           Conversely, some researchers hypothesized that the prediction
can be extracted by Short Time Fourier Transform or Wavelet           results could be dominated by several channels.
Transform in the form of spectrograms, and many studies,                 Reducing the number of EEG collecting sensors and cover-
such as [10]–[16], chose spectrograms directly as their inputs.       ing a higher proportion of 24-hour EEG signals help introduce
Differently, Zhang et al. [17] and Singh et al. [18] selected the     seizure prediction devices into the daily life of patients.
spectral power distribution over different frequency bands as         Some studies [34]–[38] calculated different metrics for each
their inputs. Additionally, Zeng et al. [19] and Li et al. [20]       channel and then selected a pre-defined number of channels
combined time-domain and spectral-domain features together            whose metrics rank best. Zhang et al. [17] elaborated on
as inputs. There are also studies, such as Li et al. [21], that       patient-specific channel selection via iteration over all possible
used raw EEG signals as inputs.                                       channel combinations and picked features through a branch
   Recently, research has been conducted to address the imbal-        and bound algorithm.
ance between pre-ictal and inter-ictal data. Li et al. [22] im-          Birjandtalab et al. [34] adopted a random forest ranking
plemented a semi-supervised approach for seizure prediction,          to pick channels. Affes et al. [10] developed an unassisted

AUTHOR et al.: PREPARATION OF PAPERS FOR IEEE TRANSACTIONS AND JOURNALS (JULY 2023)                                                             3


Fig. 1. Illustrations of ictal/preictal/interictal periods, SPH, and data excluded. ‘U’ point is at the beginning of an uncertain period.


methodology that identified and selected the most pertinent                    SOP was set to 30 minutes. Moreover, if the interval between
EEG channels for each patient without pre-defining any pa-                     two consecutive seizures was less than one hour, the latter one
rameters, and this work only excluded data one-hour before or                  was not treated as an independent seizure but was combined
after seizures. Specifically, it designed a two-phase approach                 with the former one.
for epileptic seizure prediction: a neural network with an
attention mechanism selected channels at the first phase,                      B. Preprocessing
and another neural network processed data of the selected
channels at the second phase. On the other hand, our two-stage                    An appropriate segment length should be set to make a
Set Transformer network is capable of conducting seizure                       trade off among temporal resolution, information integrity, and
prediction and channel selection simultaneously.                               computational overhead. In this study, the EEG signals were
                                                                               analyzed in a 2-seconds-long segment with 50% overlapping
                                                                               following Zeng et al. [19] and Cao et al. [14].
                             III. M ETHOD
                                                                                  Each EEG signal segment was processed using a fast Fourier
A. Dataset and Configurations                                                  transform method [41] to obtain its power spectra. EEG
   The MIT Physionet EEG (CHB-MIT) dataset, acquired                           signals are usually accompanied by noise from sources like
at Children’s Hospital Boston, encompasses EEG recordings                      muscles, eye movements, sleep spindle waves, power lines,
from pediatric subjects with intractable seizures. The Interna-                and the environment. To enhance the robustness of the entire
tional 10–20 system [39], which defines EEG electrode posi-                    system, non-physiological slow drifts, power line noise, and
tions and nomenclature, is employed for these recordings. The                  high-frequency environmental noise should be eliminated [42].
dataset contains 23 subjects, with EEG recording durations                     Therefore, a band-stop filter was used to remove the spectral
spanning between 9 and 42 hours. We selected 18 channels                       power with a frequency between 57 and 63 Hz, and a band-
shared by all the patients as input channels. Patient 23 was                   pass filter was used to discard spectral power with a frequency
not included in this study because the subject only contains                   above 128 Hz.
0.27 hour interictal EEG data.                                                    Several studies [10]–[16] utilized spectrograms generated
   Many prior studies [10]–[13], [21] chose to leave out four-                 by wavelet transform as their inputs directly. Differently,
hour EEG signals before or after seizures to constitute the                    following Zhang et al. [17], we employed several band power
interictal data. However, adhering to this clinical division                   features (absolute spectral power, relative spectral power, and
results in ambiguous prediction outputs during this period,                    spectral power ratio) as low-complexity inputs.
likely leading to alarms being triggered four hours before a                      The rhythmic activity in an EEG signal is typically de-
seizure. Considering the possibility of incorrect predictions,                 scribed in terms of the standard frequency bands. In our study,
this provides limited assistance to patients in managing their                 the band was divided into eight sub-bands: (1) θ(4–8 Hz), (2)
schedules based on the predictive outcomes. To mitigate this                   α(8–13 Hz), (3) β(13–30 Hz), (4) γ1(30–50 Hz), (5) γ2(50–70
issue, our study only excluded one-hour data before or after                   Hz), (6) γ3(70–90 Hz), (7) γ4(90–110 Hz), (8) γ5(110–128
seizures to form the interictal data. Thus, even if an alarm is                Hz). The absolute spectral power of a signal in a frequency
triggered at the beginning of the uncertain period, as the ‘U’                 band is computed as the logarithm of the sum of the power
point depicted in Figure 1, a seizure will occur within one                    spectral density (PSD) coefficients within that frequency band:
hour.                                                                                                    X
   The seizure prediction horizon (SPH) and seizure occur-                         Pabsolute (i) = log         P SD(w), i = 1, 2, ..., 8    (1)
                                                                                                           w∈band i
rence period (SOP) are defined by Maiwald et al. [40], as
shown in Figure 1. The SOP denotes the period in which a                          The relative spectral power measures the ratio of the power
seizure is anticipated to occur, and the SPH should provide                    in the i-th band to the total power of the signal in a logarithmic
sufficient time for doctors to perform clinical interventions                  scale, which is computed as:
or for patients to implement safety precautions. For a correct                                        P
                                                                                                                  P SD(w)
prediction, a seizure onset must occur after the SPH and within                  Prelative (i) = log P w∈band i             , i = 1, 2, ..., 8 (2)
the SOP. Conversely, a false alarm occurs when the predictive                                           w∈all band P SD(w)

system gives a positive result but no seizure transpires during                  The spectral power ratios represent the spectral power ratio
the SOP. In this study, the SPH was set to 3 minutes, and the                  of every two bands, with the ratio of band i to band j

4                                                                                       GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025


Fig. 2. An illustration of the even division and the seizure-independent division.


                                                                             results that machine learning methods may learn to memorize
                                                                             the features of adjacent EEG sequences rather than identifying
                                                                             the latent differences between preictal and interictal sequences.
                                                                                To tackle this concern, our study employed a seizure-
                                                                             independent division, where interictal sequences can only be
                                                                             divided by seizures. This division avoids the adjacency of
                                                                             training and test data, as depicted in Figure 2. Furthermore, the
                                                                             seizure-independent division aligns more closely with clinical
                                                                             practice, where the EEG sequence to be predicted is unknown,
                                                                             and therefore neither its preictal sequence nor its interictal
                                                                             sequence should be included during training.
Fig. 3. The architecture of MAB. ⊕ means adding operation, and
H = LayerNorm(X + MultiHeadMAB (X, Y ))

                                                                             D. Network Architecture
represented as:                                                                 1) Set Transformer: Raw EEG signals are essentially mul-
                                                                             tichannel one-dimensional signals in the time domain. Pro-
               Ri,j = Pabsolute (i) − Pabsolute (j)                   (3)
                                                                             cessing these signals involves two steps: extracting features
Spectral power ratios have been effectively used as features in              from each individual electrode channel and combining the
[43] for seizure prediction.                                                 outputs of all electrode channels. CNN can be utilized to
   In summary, 44 features, including eight absolute power                   accomplish these steps within a network [12], where different
features, eight relative power features, and 28 power ratio                  electrode channels are represented as input channels of the
features, were extracted for each electrode channel.                         CNN. Besides, some studies opted for LSTM to aggregate
                                                                             features from different electrode channels [9], [18]. Given that
C. EEG Sequence Division                                                     the Transformer has surpassed traditional RNN algorithms in
   Comparing the performance of works with different EEG                     natural language processing, it has also been recently intro-
dividing schemes is not meaningful, as dividing schemes can                  duced to handle EEG features after embedding the features
seriously influence prediction results. LOOCV (leave one out                 with position encoding [10], [29].
cross validation) has been widely used to prevent overfitting.                  However, using Transformer with additional position encod-
However, in previous LOOCV, the event left as testing data                   ing may render the network redundant, leading to substantial
only included the preictal data of a seizure and did not include             computation overhead. On the contrary, Set Transformer [6]
the interictal data before the seizure. For example, for a patient           is permutation invariant and reduces the computation time
with n seizures, all the interictal records are concatenated                 of self-attention from quadratic to linear in the number of
together and then split evenly into n segments. Afterward,                   elements.
the n interictal segments and n preictal segments are merged                    The Scaled Dot-Product Attention in the Transformer can
respectively to form n pseudo-independent events.                            be computed as:
   We refer to this division method as “even division”. It is                                                          
                                                                                                                         QK T
                                                                                                                                
widely implemented because many patients have no or only                              Attention(Q, K, V ) = softmax √              V      (4)
                                                                                                                            dk
one seizure with its own independent interictal periods, such as
Patient 3 and Patient 11 in Table II, even if we only excluded               where Q, K ∈ R1×dk represents queries and keys, respec-
one-hour data before or after a seizure. Most previous works                 tively; V ∈ R1×dv represents values.
excluded four-hour data before or after a seizure, which makes                  Multi-head attention version of attention is found more
the phenomenon more serious. However, the even division may                  beneficial and applied widely in previous studies:
increase the risk of overfitting. It breaks an integrated interictal
sequence before a specific seizure into pieces which can appear                MultiHead(Q, K, V ) = Concat (head1 , . . . , headh ) W O
in both training and test data, as shown in Figure 2. This                                                                              (5)

AUTHOR et al.: PREPARATION OF PAPERS FOR IEEE TRANSACTIONS AND JOURNALS (JULY 2023)                                                            5


Fig. 4. The overall architecture of the proposed two-step Set Transformer seizure predictor. T is the number of EEG signal segments, and C is the
number of electrode channels.

                                                      
where headi = Attention QWiQ , KWiK , V WiV , and                            2) Temporal Set Transformer: Inputs of the two-stage Set
W O is a matrix fusing the outputs of h heads to-                         Transformer were EEG sequences of 38 seconds. The PSD
gether. Specifically, MultiHead(·, ·, ·) has learnable param-             features were extracted every 2 seconds so that features of
      n                oh                                  M              19 EEG signal segments were fed into the network at a
eters WiQ , WiK , WiV       , where WiQ , WiK ∈ Rdk ×dk ,                 time for each channel. Since EEG data typically fluctuates
                  M
                            i=1      M
WiV ∈ Rdv ×dv , W O ∈ Rhdv ×d ; dM     k   and dMv   are the              rapidly, predictions based on a relatively longer period of
dimensions of keys and values of a single head, respectively;             time tend to be more robust. Furthermore, we observed that
and d is the dimension of the output of Multihead(·, ·, ·). In            certain segments of the EEG signal have greater importance
this study, we set dM           M
                    k = dk /h, dv = dv /h following Lee et                for prediction than others, and the specific order in which these
al. [6].                                                                  segments are inputted is less relevant. Thus, we utilized a
   In Set Transformer, a Multihead Attention Block (MAB)                  Set Transformer in the first stage to assign attention to the
is designed to process permutation invariant inputs. In the               temporal features and merge them by introducing a temporal
attention of MAB, the inputs of keys are the same as the                  kernel:
inputs of values:
                                                                             F eaturechanneli = MAB(Kerneltemp , P SDchanneli )              (8)
       MultiHeadMAB (X, Y )                                               where Kerneltemp ∈ R         1×dimtemporal
                                                                                                                  is a randomly initialized
                                                                   (6)
    = MultiHead(ConvQ (X), ConvK (Y ), ConvV (Y ))                        tensor which is trainable, and dimtemporal is the dimension of
                                                                          the temporal kernel tensor. P SDchanneli ∈ RT ×dimPSD is the
  After adding feed-forward layers, the MAB can be com-
                                                                          band power features of channel i. T is the number of EEG
puted as:
                                                                          signal segments fed into the network at one time and was 19
  MAB(X, Y ) = LayerNorm (H + Relu(ConvH (H)))                     (7)    in this study, and dimPSD is the dimension of the PSD features
                                                                          and was 44 as described in Section III-B. F eaturechanneli ∈
where H = LayerNorm(X + MultiHeadMAB (X, Y )). The                        Rdimtemporal is the output feature of the i th channel.
architecture of MAB is illustrated in Figure 3.                              3) Channel-Aware Set Transformer: In the second stage, the
   The Set Transformer’s inherent permutation invariance                  temporally merged features from all channels were further
property aligns with our observation that certain segments of             processed by a channel-aware Set Transformer:
the EEG signal and certain channels hold greater predictive                           F eatureoutput
importance than others, and the specific order in which they                                                                                 (9)
are arranged is less significant. It allows us to input features                    = MABCHAW (Kernelchannel , F eaturechannel )
from different time points simultaneously in the temporal Set             where MABCHAW is the channel-aware Set Transformer;
Transformer at the first stage, without the need for individual           Kernelchannel ∈ R1×dimoutput is a randomly initialized tensor
position encoding for each input. Similarly, in the second                which is trainable; F eaturechannel ∈ RC×dimtemporal is the output
stage, features from different EEG electrode channels can be              feature of the first stage, and C represents the number of
processed without the need for order encoding.                            electrode channels and was 18 in this study; F eatureoutput ∈
   The overall architecture of the two-stage channel-aware Set            Rdimoutput is the output of the second stage and will be inputted
Transformer is illustrated in Figure 4.                                   to a fully connected layer to get the final predictive results.

6                                                                                                    GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025


                                                                                                              Channel Aggregation
                                                                                                                                      FC Layer
                  Channel features                                          Value tensors
                  [N, C, dimtemporal]           Convolution Layer          [N, C, dimvalue]          Convolution Layer
                                                                                                                                      Prediction
                                              Transpose                                             Channel merged features             results
                 Convolution Layer
                                                                                                         [N, dimvalue]
                                                                            Attention tensors
                     Key tensors                       Kernel tensors
                                                                                [N, 1, C]
                    [N, C, dimkey]                      [1, dimkey]

                    Kernel tensors                                                                       Channel Selection
                     [1, dimkernel]                 Convolution Layer

                                                                                                               Accumulation
                                                                                  Inference?                                                  Finished?
                        : Data flow of standard Set Transformer                                                   Layer
                        : Data flow added for channel selection                                                ∑Attention tensors                   Yes
                                                                             After training, the
                       : Feed-forward connection                                                     The Attention tensors for each channel         All the
                                                                             model is employed to                                                   sequences
                 N: batch size                                                                       at different time point are summed up
                                                                             conduct inference on                                                   have been
                 C: number of electrode channels                             input EEG sequences                                                    processed
                    : matrix multiplication operation                        of a patient
                                                                                                                     Selected
                                                                                                                                              Softmax
                 dimtemporal , dimkey , dimkernel , dimvalue : Dimension                                             channels
                 of input, key, kernel, and value tensors, respectively.

Fig. 5. The data flow of the channel-aware Set Transformer.


   The attentions assigned to different channels fluctuate                            A. Settings and Metrics
fiercely among different batches during training and inference.                          Experiments were conducted on the EEG recordings of
As a result, an accumulation layer was supplemented to a                              22 patients from the CHB-MIT scalp EEG dataset. Adjacent
Set Transformer to form the channel-aware Set Transformer,                            seizures with an interval of less than one hour were merged
MABCHAW . This layer accumulated the attention values batch                           as one seizure. Eighteen channels shared by the patients were
by batch during inference, and the accumulations were fed to                          selected as input channels: FP1-F7, F7-T7, T7-P7, P7-O1,
a Softmax function to conduct channel selection after finishing                       P3-O1, C3-P3, F3-C3, FP1-F3, FZ-CZ, CZ-PZ, P4-O2, C4-
the inference for all inputs:                                                         P4, F4-C4, FP2-F4, FP2-F8, F8-T8, T8-P8, and P8-O2, which
                                 PNbatch PN                 !                         were indexed from 0 to 17, respectively.
                                              Attentionseq                               In our study, one-hour data before or after seizures were
   Attentionacc = Softmax
                                        Nbatch × N                                    excluded from the analysis. The SPH and SOP were set to 3
                                                           (10)                       minutes and 30 minutes, respectively. A refractory period of
where Attentionseq ∈ R1×C represents the attention distri-                            30 minutes was established to prevent continuous triggering
bution of a single input; N is the batch size, and the input                          of alarms within a short timeframe. Some studies [12], [13]
EEG sequence is divided into Nbatch batches; Attentionacc ∈                           employed a k-of-n approach to mitigate the impact of isolated
R1×C represents the attention among channels after the accu-                          false-positive predictions during interictal periods. Specifically,
mulation.                                                                             an alarm would be triggered if at least k positive predictions
   The data flow of the channel-aware Set Transformer is                              occurred within n consecutive windows. In our study, an alarm
illustrated in Figure 5.                                                              would be activated if positive predictions continued for a
   Patient-specific channel selection can be realized if the                          certain duration without any interjected negative predictions.
prediction results of a patient are dominated by a few channels.                      A threshold of approximately 4 minutes was suitable for most
On the other hand, the channel selection is to fail if no dom-                        patients in our study, while a threshold of 1 or 2 minutes
inant channels appear. If the attentions of channels succeed                          worked better for several patients.
to converge, channels with the most significant attentions will                          Existing seizure prediction tasks are classified into two
be chosen as the dominant channels. Reducing the number of                            categories: segment-based and event-based. Our study em-
electrode channels can lead to smaller, less energy-consuming                         ployed event-based prediction. Sensitivity (Sen) and false
EEG-collecting devices, increasing their acceptance among                             predicting rate (FPR) were chosen as the primary metrics
epilepsy patients.                                                                    for evaluating model performance. Sensitivity refers to the
   After the channel selection, only EEG signals from those                           percentage of seizures correctly predicted, and false predicting
dominant channels were fed to our two-stage Set Transformer                           rate represents the average number of false alarms raised in
again as inputs. Retraining was needed after channel selection                        one hour.
because of the change of input data. Given the architecture                                            Sen = TP/(FN + TP) × 100%                    (11)
of the Set Transformer, no modification was needed for the
network to process inputs with fewer channels.
                                                                                                                  FPR = FP/Lengthinterictal                     (12)

                             IV. R ESULTS                                             where TP is the number of correctly predicted seizures, FN is
                                                                                      the number of seizures models fail to predict, FP is the number

AUTHOR et al.: PREPARATION OF PAPERS FOR IEEE TRANSACTIONS AND JOURNALS (JULY 2023)                                                                          7


Fig. 6. Visualization of outputs of the predictor during interictal and preictal periods for Patient 01 and Patient 05. Most false-positive predictions
during interictal periods can be filtered because they do not last long.


of wrong alarms raised during interictal, and Lengthinterictal                                             TABLE II
means the total length of interictal EEG signals.                               T HE LENGTH OF INTERICTAL AND PREICTAL BEFORE EACH SEIZURE IN
                                                                                                      CHB-MIT DATASET
   Experiments were conducted on both the even division and
the seizure-independent division.                                                 ID     Period      S0      S1     S2     S3      S4     S5      ...
                                                                                         Interictal  1.8     9.1    0.2    0.4     3.4
                                                                                          Preictal   0.5     0.5    0.5    0.4     0.5
                           TABLE I                                                       Interictal  14.0    0.0    1.1
 T HE PREDICTING RESULTS WHEN THE EVEN DIVISION IS CONDUCTED                              Preictal   0.5     0.5    0.5
                                                                                         Interictal  0.0     0.0    0.0    28.4    0.0    0.0     ...
                 All channel                   After channel selection             3
    ID                                                                                    Preictal   0.1     0.5    0.5    0.5     0.5    0.5     ...
                                         Selected                                        Interictal  4.1     5.2    1.3    0.0     2.9
            FPR/h      Sensitivity                      FPR/h     Sensitivity      5
                                        channel(s)                                        Preictal   0.5     0.5    0.5    0.5     0.5
     01       0.14      100.0%             12,14         0.07       100.0%               Interictal  0.0     0.0    0.0    6.3     0.0    19.4    ...
     02       0.13       66.7%             9,12          0.07       100.0%         6
                                                                                          Preictal   0.5     0.5    0.5    0.5     0.5    0.5     ...
     03       0.25       80.0%              6,9          0.00        60.0%               Interictal  0.0     1.0    0.8    0.0     5.9
     04       0.09       66.7%             3,5,9         0.05        33.3%         8
                                                                                          Preictal   0.5     0.5    0.5    0.5     0.5
     05       0.00      100.0%            8,9,10         0.00       100.0%
                                                                                         Interictal  32.0    0.0    0.0
     06       0.10       70.0%           3,9,13,17       0.10        70.0%        11
                                                                                          Preictal   0.1     0.5    0.4
     07       0.03       33.3%         12,13,16,17       0.06        33.3%
                                                                                         Interictal  15.6    0.0    5.8    1.0     0.3    0.0     ...
     08       0.00       80.0%             3,14          0.00        80.0%        13
                                                                                          Preictal   0.5     0.3    0.5    0.1     0.5    0.5     ...
     09       0.18        0.0%            3,11,17        0.20        66.7%
     10       0.06       83.3%              4,9          0.03        83.3%               Interictal  1.6     0.0    0.5    3.4     5.8
     11       0.06      100.0%            0,4,10         0.03       100.0%                Preictal   0.5     0.5    0.5    0.5     0.5
     12       0.00      100.0%            8,9,16         0.25       100.0%               Interictal  8.6     1.2    0.0
     13       0.00       75.0%               6           0.00        75.0%                Preictal   0.5     0.5    0.5
     14       0.19       60.0%            4,5,8,9        0.74       100.0%               Interictal  28.0    0.0    0.0    2.0     0.0
     15       0.00      100.0%             2,3,7         0.11       100.0%                Preictal   0.5     0.5    0.5    0.5     0.1
     16       0.14      100.0%                         Failed                            Interictal  27.0    0.0    0.0
     17       0.16      100.0%           3,4,8,17        0.32       100.0%                Preictal   0.1     0.5    0.5
     18       0.00       50.0%              1,6          0.00        50.0%               Interictal  8.0     0.0    0.0    12.4
     19       0.07      100.0%         2,6,8,16,17       0.00       100.0%                Preictal   0.5     0.5    0.5    0.4
     20       0.15       75.0%             8,14          0.05        75.0%               Interictal  17.4    0.0    0.0    0.0
     21       0.06       75.0%               8           0.12        75.0%                Preictal   0.5     0.5    0.5    0.5
     22       0.30       66.7%                         Failed                            Interictal  15.9    2.9    4.1
   Mean       0.09       76.4%        2.8 channels       0.11        80.1%                Preictal   0.5     0.5    0.4
    All       0.09       76.1%          in average       0.07        79.3%        ID: The index of patients. If an ID is in bold, the patient was included
   Mean: The metric of every patient is calculated individually. After            in the experiment of seizure-independent division.
   that, an average of all patients is computed.                                  Si: The index of seizures.
   All: Seizures from different patients are grouped together to calculate        The unit of the length is hour.
   the metrics.

B. Prediction Results on Even Division
   To assess the prediction and channel selection capabilities                  channel attentions of Patient 16 and Patient 22 failed to
of the two-stage channel-aware Set Transformer, experiments                     converge. For the 20 patients, the mean sensitivity was 80.1%
were carried out on the even division for 22 patients. The                      with an FPR of 0.11 per hour. The overall sensitivity was
results are presented in Table I.                                               79.3% with a false predicting rate of 0.07 per hour. The
   Before channel selection, the mean sensitivity and mean                      seizures of 9 patients were all accurately predicted. Patient 04
false predicting rate of the patients were 76.4% and 0.09                       and Patient 07 had the lowest sensitivity of 33.3%. The average
per hour, respectively. The overall sensitivity was 76.1% with                  number of selected channels was reduced to 2.8 from 18,
a false predicting rate of 0.09 per hour. Perfect sensitivity                   which would allow EEG collecting devices to be smaller and
rates of 100% were achieved for 8 patients, and the lowest                      consume less power, thus increasing their accessibility among
sensitivity was zero for Patient 09.                                            epilepsy patients. A single dominant channel was sufficient
   After introducing channel selection, dominant channels                       for two (10.0%) patients, seven (35.0%) patients required two
emerged in 20 out of the 22 patients. In other words, the                       channels, three channels were needed for six (30.0%) patients,

8                                                                                     GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025


                                                                      TABLE III
                                                           C OMPARISON WITH OTHER STUDIES

                                                                                      Excluded length
                                                     Channel selection    Number of                     Channel   Sen
                        Works                                                         before/after                        FPR
                                                     method               patients                      number    /%
                                                                                      seizures
                  Truong et al. [12]             No channel selection        13            4 hour         All     81.2    0.16/h
                  Zhang et al.∗ [13]             No channel selection        13            4 hour         18      79.5    0.26/h
              Shu et al. [23] without DA                                     13                           All     90.7   0.103/h
                                                 No channel selection                        -
                 Shu et al. with DA                                          13                           All     95.4   0.062/h
                       Our work               Two-stage Set Transformer      13           1 hour         2.8#     95.3   0.129/h
                                                                                                          All     89.8    2.20/h
                Birjandtalab et al. [34]       Random Forest ranking         23              -
                                                                                                           3      80.9    2.50/h
                                                 Neural network with                                      23      68.6    0.30/h
                Abir Affes et al. [10]                                       23           1 hour
                                                 attention mechanism                                      2#      78.9    0.35/h
                                                                             22                           18      76.4   0.088/h
                       Our work               Two-stage Set Transformer                   1 hour
                                                                             20                          2.8#     80.1   0.107/h
              ∗ : It is a domain adaptation study.
              # : The average number of the selected channels.
              DA: data augmentation.

four (20.0%) patients demanded four channels, and Patient 19               seizures to create interictal datasets, likely making their data
(5.0%) required the maximum number of five channels.                       more distinguishable than ours, which excluded only one hour.
                                                                           Despite this, our sensitivity post-channel selection remains
                                                                           better with lower FPR. Besides, our results outperform Shu
C. Prediction Results on the Seizure-Independent
                                                                           et al. [23] before data augmentation and remain competitive
Division
                                                                           afterward, despite using significantly fewer channels, and our
   Following Zhang et al. [17], only patients with a daily                 performance could be further improved after introducing data
seizure frequency of more than 2 and less than 10 were                     augmentation methods.
included in the seizure-independent division. As shown in                     Birjandtalab et al. [34] and Affes et al. [10] also introduced
Table II, several patients have only one or two independent                channel selection methods. Birjandtalab et al. achieved the
interictal periods. Given that the seizure-independent divi-               highest sensitivity with the maximum false predicting rate, but
sion is more rigorous and the length of interictal periods                 its performance declined significantly after channel selection.
for different seizures varies drastically, only seven patients             Affes et al. utilized fewer channels than ours after selection
with three or more seizure-independent interictal periods were             and can be generalized to all patients. Nevertheless, our
analyzed. Before channel selection, the mean sensitivity and               sensitivity and FPR outperformed those of Affes et al.
mean false predicting rate of the patients were 72.6% and
0.08 per hour, respectively.After channel selection, the mean
                                                                           E. Ablation study
sensitivities remained the same, while the mean FPR increased
to 0.10 per hour. The predictive outputs for Patient 01 and                   Ablation studies were conducted to assess the contribution
Patient 05 are visualized in Figure 6 by concatenating the                 of different modules, and the results are presented in Table
outputs during interictal and preictal periods.                            IV. It would be unfair to compare channel selection methods
   The mean sensitivity for the same patients in the even                  that differ in their preceding stages or inputs. Therefore, we
division before channel selection was 79.3% with an FPR of                 implemented Solution 1 of which the inputs and temporal
0.11 per hour. The sensitivity was 6.7% higher than the results            stage resembled those of Affes et al. [10]. Thereafter, the
in the seizure-independent division. As channel selection failed           primary difference between Solution 1 and Affes et al. lay
for Patient 22 in the even division, the metrics after channel             in the channel selection stage, enabling a relatively fair
selection were computed among the remaining six patients,                  comparison. Subsequently, Solution 1 was evaluated under
and the mean sensitivity in the even division was 88.1% with               the even division. The mean sensitivity of Solution 1 was
an FPR of 0.15 per hour. The discrepancies between the two                 close to that of Affes et al., but its FPR was significantly
division methods underscore our concerns about the traditional             lower, suggesting the effectiveness of our channel-aware Set
even division.                                                             Transformer module. Additionally, when compared to Solution
                                                                           1, the original solution (Solution 3) achieved higher mean
                                                                           sensitivity with lower FPR, supporting the advantages of our
D. Comparison with Other Studies                                           selection regarding input features and temporal stages.
   Table III provides a comparison between our channel selec-                 Furthermore, in Solution 4, we replaced the original tempo-
tion method for epileptic seizure prediction and some previous             ral stage with an LSTM network to evaluate the contribution
studies that used the same dataset. The discussion is limited to           of the Set Transformer in the first stage. The solution was
results from the even division, as there are few studies, to our           evaluated under the seizure-independent division, and it was
knowledge, that have performed seizure-independent divisions               outperformed by the original solution (Solution 5). Never-
other than ours.                                                           theless, the performance metrics of the two solutions were
   Among studies without channel selection, Truong et al. [12]             close with each other, inferring the superiority of the Set
and Zhang et al. [13] excluded four-hour EEG data around                   Transformer in the first stage may not be significant.

AUTHOR et al.: PREPARATION OF PAPERS FOR IEEE TRANSACTIONS AND JOURNALS (JULY 2023)                                                                       9


                                                                    TABLE IV
                                                         R ESULTS OF THE ABLATION STUDY
                                                                                               Metrics before                   Metrics after
  Solu-      Division          Input                      Network type
                                                                                              channel selection               channel selection
   tion      method           features
                                            Temporal stage     Channel selection stage   Mean Sen/%     Mean FPR/h       Mean Sen/%     Mean FPR/h
                                              Depth-wise           Channel-aware
    1                                                                                        74.8             0.11            78.5            0.14
                           Spectrograms         CNN*              Set Transformer
               Even
                                              Depth-wise
  2 [10]      division                                           CAtt-MLP + GRU              68.6             0.30            78.9            0.35
                                                CNN
                           Band power                                 Channel-aware
 3(Ours)                                   Set Transformer                                  76.4           0.09              80.1              0.11
                            features                                 Set Transformer
                                                                      Channel-aware
    4          Seizure-    Band power             LSTM                                      70.2           0.11              70.2              0.10
                                                                     Set Transformer
            independent      features
                                                                      Channel-aware
 5(Ours)       division                      Set Transformer                                72.6           0.08              72.6              0.10
                                                                     Set Transformer
 *: Because the code of Affes et al. [10] has not been released, the Depth-wise CNN was implemented by ourselves. Thus, it is to be different from that
 of Affes et al.


F. Model Complexity and Computational Time                                   may be attributed to the limited feasibility of the selected
   Our model only contains 37.4K parameters, and 8.23M                       features for these two patients.
floating point operations are needed to conduct an inference.                   Moreover, the number of patients is limited due to the
590M GPU memory was occupied when the batch size was set                     lack of more publicly available datasets that include long-
to 16. The server we used for this study was equipped with                   duration scalp EEG signals, so statistical analysis has not been
a ”GeForce GTX 1080 Ti” GPU and an ”Intel(R) Xeon(R)                         conducted.
CPU E5-2640 v4 @ 2.40GHz” CPU. It took approximately
23.5 milliseconds (ms) to preprocess an EEG segment of                                                 VI. C ONCLUSION
two-second length. Following the preprocessing, our network                     In this study, a novel two-stage channel-aware Set
required about 10.0 ms to process the resulting features. In                 Transformer Network was proposed to conduct seizure
total, the solution took about 33.5 ms to handle an input                    prediction and channel selection concurrently. After
EEG signal segment arriving every second. This signifies that                implementing channel selection, a mean sensitivity of
our algorithm can process incoming EEG data in real-time,                    80.1% with 0.11 false alarms per hour was achieved in
allowing for continuous monitoring and rapid response.                       the even division. Additionally, the number of electrode
   However, considering the limitations of hardware capabili-                channels required for prediction decreased to an average
ties in wearable devices, it is infeasible to run our algorithm              of 2.8, effectively increasing the feasibility and acceptance
directly on them. Instead, a more practical approach is to                   of predictive devices among epilepsy patients. A more
utilize a remote computation framework in which the wearable                 rigorous seizure-independent division of EEG data, which
devices are primarily responsible for collecting the EEG                     can avoid the adjacency of training and test data, was
signals and transmitting them to a remote server.                            conducted and evaluated, and the experimental results
                                                                             support our concerns about the traditional even division.
                          V. L IMITATIONS                                    In summary, our work in channel selection, seizure onset
                                                                             prediction, and data division methods contributed to
   In this section, we will discuss the limitations of our                   epileptic seizure prediction. The code of this study has
study. Following the seizure-independent division, the training              been released at “https://github.com/RuifengZheng/Two-
data for some seizures becomes limited, while data for other                 stage Set Transformer”.
seizures becomes abundant. It is challenging to assess how
the imbalance in the training data may affect the training                   Declaration of Competing Interest
results. Therefore, the seizure-independent division may not
be feasible for patients with limited and imbalanced seizure                 None.
data, and ample EEG data is crucial for implementing seizure-
independent division in clinical practice. Beside, we have
                                                                                                            R EFERENCES
not yet determined why the channel selection method failed
for Patient 22 in the even division, but succeeded under the                  [1] W. H. Organization et al., “Epilepsy: a public health imperative,” WHO,
                                                                                  2019.
seizure-independent division.                                                 [2] D. J. Thurman, E. Beghi, C. E. Begley, A. T. Berg, J. R. Buchhalter,
   Additionally, the features and configurations we selected                      D. Ding, D. C. Hesdorffer, W. A. Hauser, L. Kazis, R. Kobau et al.,
for prediction may not be the optimal solution. We have                           “Standards for epidemiologic studies and surveillance of epilepsy,”
                                                                                  Epilepsia, vol. 52, pp. 2–26, 2011.
not exhausted all possible time and spectral features or their                [3] R. Chen, D. C. Spencer, J. Weston, and S. J. Nolan, “Transcranial
combinations, and we simply set the length of EEG signal                          magnetic stimulation for the treatment of epilepsy,” Cochrane Database
segment according to the configuration of previous studies.                       of Systematic Reviews, no. 8, 2016.
                                                                              [4] J. Yan, J. Li, H. Xu, Y. Yu, and T. Xu, “Seizure prediction based
After introducing channel selection, Patient 04 and Patient 07                    on transformer using scalp electroencephalogram,” Applied Sciences,
had the lowest sensitivity of 33.3%. This reduced sensitivity                     vol. 12, no. 9, p. 4158, 2022.

10                                                                                             GENERIC COLORIZED JOURNAL, VOL. XX, NO. XX, XXXX 2025


 [5] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez,          in seizure prediction through transfer learning,” Scientific Reports,
     Ł. Kaiser, and I. Polosukhin, “Attention is all you need,” Advances in           vol. 14, no. 1, p. 14169, 2024.
     neural information processing systems, vol. 30, 2017.                       [26] D. E. Rumelhart, G. E. Hinton, and R. J. Williams, “Learning repre-
 [6] J. Lee, Y. Lee, J. Kim, A. Kosiorek, S. Choi, and Y. W. Teh, “Set trans-         sentations by back-propagating errors,” nature, vol. 323, no. 6088, pp.
     former: A framework for attention-based permutation-invariant neural             533–536, 1986.
     networks,” in International conference on machine learning. PMLR,           [27] K. Cho, B. Van Merriënboer, C. Gulcehre, D. Bahdanau, F. Bougares,
     2019, pp. 3744–3753.                                                             H. Schwenk, and Y. Bengio, “Learning phrase representations using
 [7] A. H. Shoeb, “Application of machine learning to epileptic seizure onset         rnn encoder-decoder for statistical machine translation,” arXiv preprint
     detection and treatment,” Ph.D. dissertation, Massachusetts Institute of         arXiv:1406.1078, 2014.
     Technology, 2009.                                                           [28] S. Hu, J. Liu, R. Yang, Y. Wang, A. Wang, K. Li, W. Liu, and
 [8] J. Craley, E. Johnson, and A. Venkataraman, “Integrating convolutional           C. Yang, “Exploring the applicability of transfer learning and feature
     neural networks and probabilistic graphical modeling for epileptic               engineering in epilepsy prediction using hybrid transformer model,”
     seizure detection in multichannel eeg,” in Information Processing in             IEEE Transactions on Neural Systems and Rehabilitation Engineering,
     Medical Imaging: 26th International Conference, IPMI 2019, Hong                  vol. 31, pp. 1321–1332, 2023.
     Kong, China, June 2–7, 2019, Proceedings 26. Springer, 2019, pp.            [29] R. Hussein, S. Lee, and R. Ward, “Multi-channel vision transformer for
     291–303.                                                                         epileptic seizure prediction,” Biomedicines, vol. 10, no. 7, p. 1551, 2022.
 [9] K. M. Tsiouris, V. C. Pezoulas, M. Zervakis, S. Konitsiotis, D. D.          [30] P. Koutsouvelis, B. Chybowski, A. Gonzalez-Sulser, S. Abdullateef,
     Koutsouris, and D. I. Fotiadis, “A long short-term memory deep learning          and J. Escudero, “Preictal period optimization for deep learning-based
     network for the prediction of epileptic seizures using eeg signals,”             epileptic seizure prediction,” Journal of neural engineering, vol. 21,
     Computers in biology and medicine, vol. 99, pp. 24–37, 2018.                     no. 6, p. 066040, 2024.
[10] A. Affes, A. Mdhaffar, C. Triki, M. Jmaiel, and B. Freisleben, “Per-        [31] Y. Zhao, C. Dong, G. Zhang, Y. Wang, X. Chen, W. Jia, Q. Yuan,
     sonalized attention-based eeg channel selection for epileptic seizure            F. Xu, and Y. Zheng, “Eeg-based seizure detection using linear graph
     prediction,” Expert Systems with Applications, vol. 206, p. 117733, 2022.        convolution network with focal loss,” Computer methods and programs
[11] C. Li, X. Huang, R. Song, R. Qian, X. Liu, and X. Chen, “Eeg-based               in biomedicine, vol. 208, p. 106277, 2021.
     seizure prediction via transformer guided cnn,” Measurement, vol. 203,      [32] J. Bruna, W. Zaremba, A. Szlam, and Y. LeCun, “Spectral networks and
     p. 111948, 2022.                                                                 locally connected networks on graphs,” arXiv preprint arXiv:1312.6203,
[12] N. D. Truong, A. D. Nguyen, L. Kuhlmann, M. R. Bonyadi, J. Yang,                 2013.
     S. Ippolito, and O. Kavehei, “Convolutional neural networks for seizure     [33] M. Defferrard, X. Bresson, and P. Vandergheynst, “Convolutional neural
     prediction using intracranial and scalp electroencephalogram,” Neural            networks on graphs with fast localized spectral filtering,” Advances in
     Networks, vol. 105, pp. 104–111, 2018.                                           neural information processing systems, vol. 29, 2016.
[13] Z. Zhang, A. Liu, Y. Gao, X. Cui, R. Qian, and X. Chen, “Distilling         [34] J. Birjandtalab, M. B. Pouyan, D. Cogan, M. Nourani, and J. Harvey,
     invariant representations with domain adversarial learning for cross-            “Automated seizure detection using limited-channel eeg and non-linear
     subject children seizure prediction,” IEEE Transactions on Cognitive             dimension reduction,” Computers in biology and medicine, vol. 82, pp.
     and Developmental Systems, 2023.                                                 49–58, 2017.
[14] J. Cao, J. Zhu, W. Hu, and A. Kummert, “Epileptic signal classification     [35] H. Daoud and M. A. Bayoumi, “Efficient epileptic seizure prediction
     with deep eeg features by stacked cnns,” IEEE Transactions on Cognitive          based on deep learning,” IEEE transactions on biomedical circuits and
     and Developmental Systems, vol. 12, no. 4, pp. 709–722, 2019.                    systems, vol. 13, no. 5, pp. 804–813, 2019.
[15] Y. Yuan, G. Xun, F. Ma, Q. Suo, H. Xue, K. Jia, and A. Zhang,               [36] M. R. Karimi and H. Kassiri, “A multi-feature nonlinear-svm seizure
     “A novel channel-aware attention framework for multi-channel eeg                 detection algorithm with patient-specific channel selection and feature
     seizure detection via multi-view deep learning,” in 2018 IEEE EMBS               customization,” in 2020 IEEE International Symposium on Circuits and
     international conference on biomedical & health informatics (BHI).               Systems (ISCAS). IEEE, 2020, pp. 1–5.
     IEEE, 2018, pp. 206–209.                                                    [37] A. A. Ein Shoka, M. H. Alkinani, A. El-Sherbeny, A. El-Sayed, and
[16] Y. Yuan, G. Xun, K. Jia, and A. Zhang, “A multi-view deep learning               M. M. Dessouky, “Automated seizure diagnosis system based on feature
     framework for eeg seizure detection,” IEEE journal of biomedical and             extraction and channel selection using eeg signals,” Brain Informatics,
     health informatics, vol. 23, no. 1, pp. 83–94, 2018.                             vol. 8, no. 1, pp. 1–16, 2021.
[17] Z. Zhang and K. K. Parhi, “Low-complexity seizure prediction from           [38] Y. Yuan, G. Xun, K. Jia, and A. Zhang, “A multi-view deep learning
     ieeg/seeg using spectral power and ratios of spectral power,” IEEE               method for epileptic seizure detection using short-time fourier trans-
     transactions on biomedical circuits and systems, vol. 10, no. 3, pp. 693–        form,” in Proceedings of the 8th ACM international conference on
     706, 2015.                                                                       bioinformatics, computational biology, and health informatics, 2017, pp.
[18] K. Singh and J. Malhotra, “Two-layer lstm network-based prediction of            213–222.
     epileptic seizures using eeg spectral features,” Complex & Intelligent      [39] J. N. Acharya, A. J. Hani, J. Cheek, P. Thirumala, and T. N. Tsuchida,
     Systems, vol. 8, no. 3, pp. 2405–2418, 2022.                                     “American clinical neurophysiology society guideline 2: guidelines for
[19] D. Zeng, K. Huang, C. Xu, H. Shen, and Z. Chen, “Hierarchy graph                 standard electrode position nomenclature,” The Neurodiagnostic Journal,
     convolution network and tree classification for epileptic detection on           vol. 56, no. 4, pp. 245–252, 2016.
     electroencephalography signals,” IEEE transactions on cognitive and         [40] T. Maiwald, M. Winterhalder, R. Aschenbrenner-Scheibe, H. U. Voss,
     developmental systems, vol. 13, no. 4, pp. 955–968, 2020.                        A. Schulze-Bonhage, and J. Timmer, “Comparison of three nonlinear
[20] Y. Li, Y. Liu, W.-G. Cui, Y.-Z. Guo, H. Huang, and Z.-Y. Hu, “Epilep-            seizure prediction methods by means of the seizure prediction character-
     tic seizure detection in eeg signals using a unified temporal-spectral           istic,” Physica D: nonlinear phenomena, vol. 194, no. 3-4, pp. 357–368,
     squeeze-and-excitation network,” IEEE Transactions on Neural Systems             2004.
     and Rehabilitation Engineering, vol. 28, no. 4, pp. 782–794, 2020.          [41] P. Welch, “The use of fast fourier transform for the estimation of power
[21] C. Li, Z. Deng, R. Song, X. Liu, R. Qian, and X. Chen, “Eeg-based                spectra: a method based on time averaging over short, modified peri-
     seizure prediction via model uncertainty learning,” IEEE Transactions            odograms,” IEEE Transactions on audio and electroacoustics, vol. 15,
     on Neural Systems and Rehabilitation Engineering, vol. 31, pp. 180–              no. 2, pp. 70–73, 1967.
     191, 2022.                                                                  [42] W. Wu, Y. Zhang, J. Jiang, M. V. Lucas, G. A. Fonzo, C. E. Rolle,
[22] H. Li, J. Liao, H. Wang, A. Z. Chang’an, and F. Yang, “Eeg power                 C. Cooper, C. Chin-Fatt, N. Krepel, C. A. Cornelssen et al., “An
     spectra parameterization and adaptive channel selection towards semi-            electroencephalographic signature predicts antidepressant response in
     supervised seizure prediction,” Computers in Biology and Medicine, vol.          major depression,” Nature biotechnology, vol. 38, no. 4, pp. 439–447,
     175, p. 108510, 2024.                                                            2020.
[23] K. Shu, L. Wu, Y. Zhao, A. Liu, R. Qian, and X. Chen, “Data                 [43] K. K. Parhi and Z. Zhang, “Seizure prediction using ratio of spectral
     augmentation for seizure prediction with generative diffusion model,”            power from single eeg electrode,” in Proc. of 6th International Workshop
     IEEE Transactions on Cognitive and Developmental Systems, 2024.                  on Seizure Prediction (IWSP6), 2013, p. 39.
[24] F. Lopes, A. Leal, M. F. Pinto, A. Dourado, A. Schulze-Bonhage,
     M. Dümpelmann, and C. Teixeira, “Removing artefacts and periodi-
     cally retraining improve performance of neural network-based seizure
     prediction models,” Scientific Reports, vol. 13, no. 1, p. 5918, 2023.
[25] F. Lopes, M. F. Pinto, A. Dourado, A. Schulze-Bonhage,
     M. Dümpelmann, and C. Teixeira, “Addressing data limitations
```
