---
citation_key: "GuoEtAl2023"
paper_id: "paper_058"
title: "CLEP: Contrastive Learning for Epileptic Seizure Prediction Using a Spatio-Temporal-Spectral Network"
authors: "Lianghui Guo; Tao Yu; Shijie Zhao; Xiaoli Li; Xiaofeng Liao; Yang Li"
year: 2023
doi: "10.1109/tnsre.2023.3322275"
source: "publisher-pdf (doi: 10.1109/tnsre.2023.3322275)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# CLEP: Contrastive Learning for Epileptic Seizure Prediction Using a Spatio-Temporal-Spectral Network

**Citation:** `GuoEtAl2023` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/tnsre.2023.3322275](https://doi.org/10.1109/tnsre.2023.3322275)
**Source PDF:** `full_pdf/Guo2023.pdf`

## Abstract

Seizure prediction of epileptic preictal period sitivity of 96.7% and a false prediction rate of 0.072/h through electroencephalogram (EEG) signals is impor- on the CHB-MIT scalp EEG database. We also validate tant for clinical epilepsy diagnosis. However, recent deep the proposed method on clinical intracranial EEG (iEEG) learning-based methods commonly employ intra-subject database from our Xuanwu Hospital of Capital Medical training strategy and need sufficient data, which are labo- University, and the predicting system yielded a sensitivity rious and time-consuming for a practical system and of 95%, a false prediction rate of 0.087/h. The experimental pose a great challenge for seizure predicting. Besides, results outperform the state-of-the-art studies which vali- multi-domain characterizations, including spatio-temporal- date the efficacy of our method. Our code is available at spectral dependencies in an epileptic brain are generally https://github.com/LianghuiGuo/CLEP-STS-Net. neglected or not considered simultaneously in current approaches, and this insufficiency commonly leads to

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023                                               3915


            CLEP: Contrastive Learning for Epileptic
                  Seizure Prediction Using a
              Spatio-Temporal-Spectral Network
       Lianghui Guo, Tao Yu , Shijie Zhao , Member, IEEE, Xiaoli Li , Xiaofeng Liao , Fellow, IEEE,
                                    and Yang Li , Senior Member, IEEE

   Abstract— Seizure prediction of epileptic preictal period                 sitivity of 96.7% and a false prediction rate of 0.072/h
through electroencephalogram (EEG) signals is impor-                         on the CHB-MIT scalp EEG database. We also validate
tant for clinical epilepsy diagnosis. However, recent deep                   the proposed method on clinical intracranial EEG (iEEG)
learning-based methods commonly employ intra-subject                         database from our Xuanwu Hospital of Capital Medical
training strategy and need sufficient data, which are labo-                  University, and the predicting system yielded a sensitivity
rious and time-consuming for a practical system and                          of 95%, a false prediction rate of 0.087/h. The experimental
pose a great challenge for seizure predicting. Besides,                      results outperform the state-of-the-art studies which vali-
multi-domain characterizations, including spatio-temporal-                   date the efficacy of our method. Our code is available at
spectral dependencies in an epileptic brain are generally                    https://github.com/LianghuiGuo/CLEP-STS-Net.
neglected or not considered simultaneously in current
approaches, and this insufficiency commonly leads to                           Index Terms— EEG, contrastive learning,                   spatio-
suboptimal seizure prediction performance. To tackle the                     temporal-spectral      dependencies,      dynamic            graph
above issues, in this paper, we propose Contrastive                          convolution, triple attention, seizure prediction.
Learning for Epileptic seizure Prediction (CLEP) using a
Spatio-Temporal-Spectral Network (STS-Net). Specifically,                                            I. I NTRODUCTION
the CLEP learns intrinsic epileptic EEG patterns across                            PILEPSY is one of the most common brain functional
subjects by contrastive learning. The STS-Net extracts
multi-scale temporal and spectral representations under
                                                                             E     diseases, which is caused by sudden neurological dis-
                                                                             orders [1] and affects more than 40 million people in the
different rhythms from raw EEG signals. Then, a novel
triple attention layer (TAL) is employed to construct                        world [2]. It is estimated that approximately 25% of patients
inter-dimensional interaction among multi-domain features.                   have no suitable treatments to alleviate seizure symptoms
Moreover, a spatio dynamic graph convolution network                         [3], and the epilepsy surgery remains challenging because of
(sdGCN) is proposed to dynamically model the spatial                         multiple seizure foci, poor localization of seizure focus [4].
relationships between electrodes and aggregate spatial
information. The proposed CLEP-STS-Net achieves a sen-                       Especially, patients whose seizures arisen from important brain
                                                                             functional regions are not candidates for resection surgery,
   Manuscript received 7 March 2023; revised 12 August 2023;                 since it may cause the decline of brain functions such as motor
accepted 26 September 2023. Date of publication 5 October 2023;              and language [5]. Therefore, the study of epileptic seizure
date of current version 11 October 2023. This work was supported
in part by the National Natural Science Foundation of China under            predicting, which can provide early warning of the incoming
Grant 62325301 and Grant 62201023, in part by the Beijing Natu-              seizure, is becoming increasingly important. The majority of
ral Science Foundation under Grant Z220017, in part by the Beijing           previous seizure prediction methods made the assumption that
Municipal Education Commission-Natural Science Foundation under
Grant KZ202110025036, in part by the China Post-Doctoral Science             epileptic EEG signals can be divided into four consecutive
Foundation under Grant 2023M730175, and in part by the Beijing United        brain activity states: interictal, preictal, ictal and postictal [2].
Imaging Research Institute of Intelligent Imaging Foundation under           The goal of a seizure prediction method is to accurately
Grant CRIBJQY202103. (Corresponding author: Yang Li.)
   Lianghui Guo is with the Department of Automation Sciences and            classify interictal and preictal states and warn the patients
Electrical Engineering, Beihang University, Beijing 100083, China            before the seizure onset.
(e-mail: guolianghuibuaa@buaa.edu.cn).                                          Recently many deep learning-based approaches are studied
   Tao Yu is with the Beijing Institute of Functional Neurosurgery, Xuanwu
Hospital, Capital Medical University, Beijing 100053, China (e-mail:         for automatic EEG seizure prediction. Most of these methods
yutaoly@sina.com).                                                           have been proposed for EEG feature extracting in time domain
   Shijie Zhao is with the School of Automation, Northwestern Polytechni-    [2], [6], [7], [8], frequency domain [9], [10], [11], [12] and
cal University, Xi’an 710072, China (e-mail: shijiezhao666@gmail.com).
   Xiaoli Li is with the National Key Laboratory of Cognitive Neuroscience   spatial domain [13], [14], [15], [16]. However, most studies
and Learning, Beijing Normal University, Beijing 100875, China (e-mail:      mainly focused on intra-subject EEG pattern learning, which
xiaoli@bnu.edu.cn).                                                          require a collection of sufficient data within one subject. For
   Xiaofeng Liao is with the College of Computer Science, Chongqing
University, Chongqing 400715, China (e-mail: xfliao@cqu.edu.cn).             instance, convolution neural network (CNN) was commonly
   Yang Li is with the Department of Automation Sciences and Electrical      applied on the wavelet transformation of EEG which learned
Engineering and the State Key Laboratory of Virtual Reality Technol-         quantitative signatures for EEG classification [6], [11]. The
ogy and Systems, Beihang University, Beijing 100083, China (e-mail:
liyang@buaa.edu.cn).                                                         short-time Fourier transform (STFT) was used to capture
   Digital Object Identifier 10.1109/TNSRE.2023.3322275                      time-frequency characteristics from EEG signals and CNN was

                          © 2023 The Authors. This work is licensed under a Creative Commons Attribution 4.0 License.
                                    For more information, see https://creativecommons.org/licenses/by/4.0/

3916                                              IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


adopted for classification [12], [17]. Ozcan et al. [2] further      by associating signals’ spatial and temporal properties with
investigated 3D CNN for evaluating the spatio-temporal cor-          graph nodes and edges [27], and then fed into the GCN
relations in EEG classification. In addition, recurrent neural       for feature extraction. For example, Wang et al. [28] applied
network (RNN) was also introduced in many recent studies             the phase locking value (PLV) to capture spatial information
[18]. The above approaches are time-consuming during train-          between EEG channels. Variational Instance-adaptive graph
ing process which becomes a major obstacle for the clinical          (V-IAG) was used to characterize the dependencies among
use of EEG-based seizure predicting system. Therefore, devel-        EEG channels [22]. Zhong et al. [29] adopted the differential
oping the good cross-subject generalization ability is desirable     entropy (DE) to represent temporal correlations in EEG signals
for a practical seizure prediction application especially in the     and build graph nodes. However, these methods merely relied
cases of new patients. Therefore, the substantial inter-subject      on handcrafted features to represent EEG graphs, and the
variabilities of epilepsy-related EEG activities should be con-      priori indicators probably ignored the heterogeneities between
sidered. Recently, contrastive learning for the EEG feature          different epileptic patients, which affected the generalization
extraction has found that contrastive objectives can learn better    ability of the GCN. Thus, in this study, we focus on building
representations than the supervised learning [19]. For example,      a dynamic GCN framework which can infer a patient-specific
Shen et al. [20] used contrastive learning to maximize the           EEG graph and extract spatio-temporal responses with the
similarity in EEG representations for cross-subject emotion          graph convolution jointly.
recognition. Banville et al. [21] further utilized the contrastive      In summary, to deal with the above issues, in this paper,
learning in EEG-based sleep staging and pathology and out-           we propose Contrastive Learning for Epileptic seizure Pre-
performed the supervised learning. Therefore, we explore             diction (CLEP) using a Spatio-Temporal-Spectral Network
contrastive pretraining for seizure predicting, which learns         (STS-Net). Specifically, our CLEP strategy pretrained the
generic representations of epileptic EEG from source subjects        EEG Encoder using the contrastive learning, which optimizes
and can be easily adapted to a target subject.                       an EEG contrastive (EC) loss to learn generic EEG repre-
   Additionally, in order to extract supplementary information       sentations. Then, the proposed STS-Net serves as the EEG
in temporal-spectral domain for the seizure prediction, some         Encoder and includes three subnets as follows. The pyramid
recent studies introduced attention mechanisms into the feature      convolution net first captures multi-scale temporal-spectral
extraction. Specifically, Li et al. [15] used the squeeze-and-       evolutions from raw EEG signals under five rhythms. Second,
excitation network (SENet) to capture correlations between           the triple attention fusion net is followed, including fives
EEG channels. Similarly, an additional branch was used to            parallel branches, each of which takes a certain group of
generate individual dependencies among EEG channels [22].            temporal-spectral evolutions as inputs and fuses the features
Moreover, Yang et al. [17] adopted attentions in both spectral       by consecutive triple attention layers (TAL). Third, the spatial
and channel domain, which built global dependencies on               embedded net is applied which embeds spatial information
spectrums and interdependence on EEG channels. The above             between electrodes into the refined feature maps through the
attention methods have been proved helpful in boosting the           proposed spatio dynamic graph convolution network (sdGCN).
seizure prediction performance. However, most of them mainly         Experiment results on two epileptic EEG datasets show that
focused on building the channel attention of EEG signals,            our CLEP-STS-Net can predict seizures accurately and the
where the spatial attention was not considered. We take              performance is better than the state-of-the-art studies.
inspiration from the Convolutional Block Attention Module               The main contributions of this study are summarized below:
(CBAM) [23], which successfully demonstrated the impor-                 1) A novel CLEP-STS-Net scheme is proposed for the
tance of building spatial attention along with the channel                  seizure prediction, which explores multi-scale spatio-
attention. However, the attention method in CBAM did not                    temporal-spectral features from EEG signals through
account for the cross-dimension interaction, which ignored the              our STS-Net. Besides, the contrastive learning strat-
relation between channel dimension and spatial dimension,                   egy CLEP is proposed to minimize the similarity of
and thus may degrade the performance. Motivated by this,                    inter-class epileptic EEG patterns and maximize the
we attempt to introduce a comprehensive attention mecha-                    similarity of inner-class patterns across subjects, which
nism to capture the cross-dimension interaction, which can                  improves the generalization ability and benefits the
characterize both inter-channel and spatial dependencies while              patient-specific seizure predicting;
building inter-dimensional interaction between channel and              2) A triple attention layer (TAL) is introduced for build-
spatial attentions.                                                         ing inter-dimensional interaction between input feature
   It should be noticed that, although the CNN has shown the                maps, which encodes inter-channel and spatial depen-
promising performance in EEG classification tasks [24], it can              dencies through a triplet attention structure;
only captured the spatial information between EEG channels              3) We propose a spatio dynamic graph convolution net
in a short range due to its regular operation and the local                 (sdGCN) to better capture the preictal transitions in
receptive field [25]. Moreover, the non-Euclidean structure of              EEG, which embeds channel-information into temporal-
EEG electrodes cannot be fully represented by the standard                  spectral features under different rhythms dynamically by
convolution operation [26]. Therefore, in order to mitigate                 using the graph convolution;
the above disadvantages of the CNN, a graph convolutional
network (GCN) was investigated, which viewed the EEG                                    II. M ETHODOLOGY
signals as graph representations and captured spatio-temporal          The proposed seizure prediction framework is shown in
features from EEG [25]. Specifically, EEG graphs were built          Fig. 1, and summarized as follows: (1) The proposed CLEP

GUO et al.: CLEP USING A SPATIO-TEMPORAL-SPECTRAL NETWORK                                                                                 3917


Fig. 1. The illustration of the proposed CLEP-STS-Net, where the proposed EEG Encoder: STS-Net can be found in Section II-B.

strategy is applied to pretrain EEG Encoder on the source              X eeg = {(X i , yi )|i = 1, 2, . . . ,N }, where X i ∈ R 1×T is the
subjects using the contrastive learning; (2) The proposed              i-th EEG representation with a feature vector length of T , N
STS-Net contains three modular subnets, i.e., the pyramid              is the batch size. yi is the corresponding label of X i , either
convolution net, the triple attention fusion net, the spatio           preictal or interictal. The cosine similarity score of two input
embedded net, performs as the EEG encoder and is fine-tuned            representations X A and X B is given by:
on target subject; (3) The optimized CLEP-STS-Net is then                                                       X A ·X B
transformed into a practical seizure warning system through a                             sim(X A , X B ) =                                (1)
                                                                                                              ∥X A ∥∥X B ∥
post-processing scheme.
                                                                       where X A ·X B is the inner product of X A and X B . The EC
A. CLEP: Contrastive Learning for Epileptic Seizure                    loss is calculated by the following formula:
Prediction
                                                                                               j=1 1[yi =y j ] exp(sim(X i , X j )/τ )
                                                                                              PN
                                                                             EC        1
   Deep-Learning-based seizure prediction methods commonly                 Li = −         log    PN                                    (2)
                                                                                                   k=1 exp(sim(X i , X k )/τ )
need sufficient data and train the model in a patient-specific                       N yi
way, which means that extensive EEG signals are required for           where N yi is the number of samples that have the same label as
one patient for seizure prediction. However, it usually takes a        yi in a batch. 1[yi =y j ] ∈ {0, 1} is an indicator function which is
long time and cost to prepare enough data clinically. Besides,         set to 1 if yi = y j . τ is the temperature and controls the range
the patient-specific model has little generalization ability due       of the softmax, which is directly optimized during training to
to heterogeneities among patients. Therefore, to overcome              avoid turning as a hyperparameter. By minimizing EC loss
the challenges of data insufficiency and low generalization            in Eq. (2), the model will increase the similarities between
ability, the proposed CLEP performs contrastive pretraining            representations that come from the same class and reduce
on source subjects and fine-tunes the model on the target              the similarities between preictal and interictal representations.
subject, which transfers relevant epileptic EEG patterns to            During pretraining, the CLEP also uses the supervised learning
help the learning task for a new patient. The proposed CLEP            as a supplement, which predicts whether an EEG representa-
framework is shown in Fig. 1, which includes the following             tion is preictal or interictal, and this is implemented by the
steps. First, the CLEP pretrains the EEG encoder on the source         cross-entropy loss:
subjects using both the contrastive learning and the supervised
                                                                                     1 XN
learning. Given a batch of N EEG trial, suppose there are                 LC E = −                [yi log ( pi ) + (1 − yi ) log (1 − pi )] (3)
m preictal representations and n interictal representations in                       N       i=1

a batch. We decide that every two preictal representations             where pi is the predicted probability of preictal and yi is the
form a matched pair, every two interictal representations form         label. By combing the contrastive learning and the supervised
a matched pair. Therefore, we get m 2 + n 2 matched pairs              learning, the CLEP is pretrained by using the hybrid loss
and 2×m×n incorrect pairs in each batch. In the contrastive            function:
learning, the CLEP is trained to predict which of the N × N
                                                                                           L = αL EC + (1 − α) L C E                       (4)
possible pairs match and which do not match. Therefore,
the CLEP trains the EEG Encoder to maximize the cosine                 where α is a hyperparameter and set to 0.5. When pretrain-
similarity of the m 2 + n 2 matched representation pairs in the        ing is done on the source subjects, the CLEP finetunes the
batch while minimizing the cosine similarity of the 2×m × n            EEG Encoder on the target subject to eliminate interdomain
incorrect representation pairs.                                        differences. The EEG Encoder is then trained by using the
   We optimize a new EEG contrastive (EC) loss over these              supervised learning which adapts the extracted representa-
cosine similarity scores. Given the input EEG representations          tions to the target domain. Finally, our CLEP-STS-Net is

3918                                               IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


Fig. 2. The structure of the proposed EEG Encoder: Spatio-Temporal-Spectral Network (STS-Net).

well-trained to serve as a real-time seizure prediction system,       where u and v denote the approximation filter and the detail
which is able to perform inference on unlabeled EEG signals           filter, respectively. x A and x D are approximation coefficients
from target subject.                                                  and detail coefficients. r and s refer to the kernel size and
                                                                      stride, set to 8 and 2, both of which are consistent with
B. STS-Net: Spatio-Temporal-Spectral Network                          the order of Db4 wavelet filter [35]. The approximation
   In this subsection, we describe how the proposed                   coefficients x A is then fed into the next waveConv layer, and
EEG Encoder: STS-Net is built in details, which extracts              the consecutive waveConv layers perform spectral analysis
temporal-spectral features from different rhythms while               iteratively through L pyramid level,   where L is defined by the
                                                                      signal sampling rate f s : L = log2 ( f s ) − 3, and ⌊·⌋ is the
                                                                                                       
embedding dynamic spatial information to generate classifica-
tion results of epileptic EEG signals. Fig. 2 shows the structure     rounding-down operation [30]. Through the above hierarchical
of STS-Net, which is demonstrated as follows:                         waveConv layers, the frequency boundaries of x A and x D of
                                                                      the l-th pyramid level are (0, f s /2l+1 ) and ( f s /2(l+1) , f s /2l ),
C. Design of the Pyramid Convolution Net                              respectively, where l=1, 2, . . . , L. Moreover, since we set
   EEG signals contain abundant temporal, spatial and spec-           the strider to 2 in each layer, we get spectral feature map of
tral features, which are difficult to define manually [30],           shape ((E + 1) @ C× T /2l ) from the l-th pyramid level. As a
[31]. In order to capture significant temporal and spectral           result, a set of pyramid spectral features under five standard
responses from epileptic EEG, the pyramid convolution net             physiological subbands are captured. Note that the waveConv
is implemented by two separate pyramids: spectral pyramid             involves no learnable parameters, whose weights are preloaded
and temporal pyramid, extracting multi-level spectral features        from Db4 wavelet filter.
and multi-scale temporal features, respectively. The structure            The pyramid spectral analysis is essential for EEG feature
of the pyramid convolution net is shown in Fig. 2.                    extraction [36], the previous studies was also proved to be
   Since neural activities in an epileptic seizures may be            helpful by using temporal patterns for EEG classification
of different frequencies, the spectral pyramid is designed to         [37], a temporal pyramid net is thus implemented through
obtain spectral feature responses under different scales, which       several parallel temporal convolution layers. Specifically, the
also correspond to the clinical frequency subbands: δ rhythm          pyramid level is set to 5 in order to generate temporal
(0-4Hz), θ rhythm (4-8Hz), α rhythm (8-13Hz), β rhythm (13-           representations consistent with 5 pyramid spectral features
30Hz), γ rhythm (30-50Hz) [32]. Specifically, the spectral            [35]. The kernel sizes and strides are empirically set to {k/8,
pyramid net consists of hierarchical wavelet convolutions             k/4, k/2, k, k}, where k = 2 L , to get pyramid temporal
(waveConv), which implements wavelet decomposition on the             features with the consistent sizes as pyramid spectral features
input EEG sample through the convolution layer. Inspired by           above. Note that each temporal convolution layer is followed
the Daubechies order-4 (Db4) wavelet, which is useful in              by batch normalization and exponential linear unit (ELU).
spectral analysis due to its high correlation coefficients with       Next, in order to combine the above spectral and temporal
the epileptic spikes [33], [34], Db4 is applied in the waveConv       analysis, the pyramid spectral features and temporal features
in this study. Specifically, for a given input EEG representation     are concatenated channel-wisely, resulting in five groups of
x at time sample t, the waveConv performs in a way analogous          temporal-spectral features.
to the discrete wavelet transform, and is defined by:
                        XR                                            D. Design of the Triple Attention Fusion Net
              x A (t) =          x (s × t − k) × u (r )                 Although abundant feature extraction is proved helpful in
                            r =0
                        XR                                            EEG classification, inappropriate fusion method may involve
              x D (t) =          x (s × t − k) × v (r )       (5)
                           r =0                                       redundant information and produce a poor performance.

GUO et al.: CLEP USING A SPATIO-TEMPORAL-SPECTRAL NETWORK                                                                        3919


                                                                      Fig. 4. A schematic illustration of the sdGCN.
Fig. 3. The architecture of the triple attention layer (TAL).
                                                                      into X C W ∈ R H ×C×W , which aims at capturing dependencies
Therefore, the triple attention fusion net is employed to empha-      between (C, W) dimensions. Moreover, another permuting
size the most discriminative representations by the proposed          operation at the end of the second branch transforms the
triple attention layer (TAL), which is shown in Fig. 2. Unlike        tensor into the original input shape. The third branch is built
SENet [38] and CBAM [23] which required a certain amount              in the same way, and the first permuting operation outputs
of learnable parameters, the goal of TAL is to model channel          the tensor X H C ∈ R W ×H ×C to build dependencies between
attention and spatial attention cheaply but effectively while not     (H , C) dimensions. The outputs of the three branches are
involving dimension reduction.                                        then aggregated by averaging to generate the refined feature.
   The channel attention in SENet focuses the model to                In summary, to obtain the refined feature X r e f from an input
learn more on certain channels, while the CBAM introduced             tensor X in ∈ R C×H ×W , the operation of the proposed TAL
a spatial attention as a complementary module telling the             can be represented by:
model which channel should be emphasized. However, the                            1
channel attention and the spatial attention are considered               Xr e f =   (X H W ⊙ X w
                                                                                                  + XCW ⊙ Xw  2 +X
                                                                                                                    HC ⊙ Xw)
                                                                                                                            3     (7)
separately, and the relation between channel dimension and
spatial dimension is ignored. Motivated by the above attention        where X H W equals to the input tensor X in , X C W and X H C
                                                                      are the permuted results from X in , X wi (i = 1, 2, 3) is the
mechanism, for the input tensor X in ∈ R C×H ×W , a cross-
dimension attention is considered, named triple attention layer,      attention weighs generated from the i-th attention branch, ⊙
which uses three branches to capture dependencies between             is the broadcast element-wise multiplication, −−− denotes the
(H , W ), (C, W ) and (H , C) dimensions of the input tensor,         permuting operation.
respectively.                                                            As a result, the triple attention fusion net branches into
   The structure of the proposed TAL is given in Fig. 3. Con-         five subnets, and the five groups of temporal-spectral features
sidering the existing of heterogeneity between multi-domain           are fed into the subnets respectively. Each subnet adopts
feature maps, the TAL first applies group convolution on the          consecutive TAL operations to generate coarser representations
input temporal-spectral features X in ∈ R C×H ×W . The parame-        from multi-domain and refine the feature maps through triple
ter group is set to 2, which reduces the computational cost [39]      attention. The outputs of five subnets are then passed into an
and the alleviates aliasing effect as well [40]. Next, the feature    average pooling layer and the fused temporal-spectral feature
maps are passed into three branches respectively, and the first       U = [µγ , µβ , µα , µθ , µδ ] is obtained, where µi ∈ R E×F ,
branch is designed to capture interaction between (H , W)             and F is the length of feature vector under each rhythm.
dimensions and performed on X H W ∈ R C×H ×W . At the
beginning, the channel-wise max-pooling and average-pooling           E. Design of the Spatio Embedded Net
are applied to reduce the channel dimension and then the                 From the above subnets, multi-scale temporal-spectral fea-
pooled features are concatenated. This shrinks the feature maps       tures are captured from the EEG signals and refined, but
to make further computation lightweight and results in a rich         the interdependencies between different electrodes have not
representation X pool , which is defined by:                          been considered yet. Therefore, we build EEG graphs by
                                                                      using a proposed sdGCN, which explicitly explores spatial
          X pool = Max Pool(X H W )©Avg Pool(X H W )            (6)
                                                                      relationships between EEG channels through dynamic graph
where X pool ∈ R 2×H ×W is the pooled feature, Max Pool (·)           convolution. The structure of the proposed sdGCN is given in
and Avg Pool (·) refer to the channel-wise max-pooling and            Fig. 4.
average-pooling, © is the channel-wise concatenating. X pool is          Previous studies commonly use 2D position projection of
then fed into a standard convolution with kernel of 7 × 7 and         electrodes to build EEG graph [41]. However, the 2D pro-
a sigmoid activation layer, which provides the intermediate           jection of EEG electrodes was merely a rough approximation
attention weights X w ∈ R 1×H ×W . The generated attention            which partially represented the EEG graph but ignored precise
weights are then applied to the input X H W through element-          distance measurement [26]. Considering this, we propose
wise multiplication. The second branch acts similarly, and            a position embedding method to represent the correlation
a permuting operation is added to permute the input tensor            between two electrodes using 3D position. First, we define

3920                                             IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


a set including distance between any two EEG electrodes                                        TABLE I
by: Dis = {di j |i, j ∈ (1, E) , i ̸ = j, where di j denotes the         DATA I NFORMATION OF THE P UBLIC CHB-MIT DATABASE
Euclidean distance of node i and node j, E is the number of
electrodes. The distance can be acquired from the international
10-20 system. Then we define two electrodes are neighbors
if the distance di j is smaller than the average value of Dis .
Moreover, the distance between an electrode and itself is
defined as the average distance of all neighboring electrodes
to this electrode. In summary, we embedded 3D positions into
adjacent matrix A ∈ R E×E through the proposed position
embedding methods, which is defined by:
         
         
                                       i f di j < M(Dis )
          di j
         
         
  Ai j = 0                              i f di j ≥ M(Dis )   (8)
         
                       1
                                        if i = j
         
         
            M({diq |diq < M(Dis )})
         

where M (Dis ) is the mean value of distance set Dis . However,
the above position embedding method is subject-independent,
and the spatial information embedded in electrodes is captured     Finally, consecutive fully connected (FC) layers at the end of
in a fixed mode, which is not able to precisely model the          the spatio embedded net map the multi-domain feature into
heterogeneity among different subjects. Therefore, the pro-        the seizure predicting results.
posed sdGCN further applies a self-gating method on the
adjacent matrix A. Specifically, the self-gating method forms      F. Post-Processing and Implementing Details
a bottleneck with two fully-connected (FC) layers to perform
                                                                      In this section, the optimized CLEP-STS-Net is translated
the squeeze-and-excitation on the adjacent matrix A, where
                                                                   into a practical seizure warning system through a persistent
the first FC layer applies dimensionality-reduction and the
                                                                   post-processing scheme [42]. First, the proposed CLEP-STS-
second FC layer is for dimensionality-increasing. A rectified
                                                                   Net generates probability series P(i) from the input EEG
linear unit (ReLU) is further followed to prune negative
                                                                   signals, where P(i) denotes the probability the input signal
correlations in A. Namely, the combination of the FC layers
                                                                   belongs to preictal from the i-th EEG sample. Then a moving
and ReLU nonlinearities turns A into a learnable dynamic
                                                                   average filter is applied on P(i) to alleviate the oscillation and
matrix adapted to different subjects, which dynamically model
                                                                   get the smoothed probability series Ps (i) [2], [15]. The lengths
the dependencies between electrodes. The self-gating method
                                                                   of the moving average filter are set to 15s for CHB-MIT
is defined by:
                                                                   and 25s for Xuanwu dataset, which will be discussed in
                    Ãd = σ (W2 δ(W1 ( Ã)))                 (9)   Section IV-H.
                                                                      Next, when Ps (i) exceeds a pre-defined threshold ω,
where Ã ∈ R (E×E)×1 is reshaped from A, W1 ∈                      a trigger Tr (i) of duration τω will start to warn the patient
R ((E×E)/r )×(E×E) and W2 ∈ R (E×E)×((E×E)/r ) are weight          for an imminent seizure. The threshold ω for CHB-MIT
matrixes of the first and second FC layer, r denotes the reduc-    and Xuanwu is set to 0.6, whose influence will be dis-
tion ratio, whose influence will be discussed in Section IV-F.     cussed in Section IV-H. τω is the persistence parameter and
δ (·) is the ELU activation function and σ (·) is the ReLU         is equal to the preictal period length [42]. For a true warning,
activation function, which is adopted to get a sparse graph and    Tr (i) should start at least τω0 prior to the seizure onset, and
suppress negative values. As results, a dynamic adjacent matrix    remain activated until the seizure onset, otherwise it becomes
Ad is obtained by reshaping Ãd ∈ R (E×E)×1 into R E×E .           a false warning. τω0 is the detection interval, which ensures the
Once the connection relationship between electrodes is built,      patient to be prepared for the incoming seizure [42]. Recent
the sdGCN applies graph convolution on the temporal-spectral       studies commonly define τω0 less than 1-minute [2], [15], and
feature U and the dynamic adjacent matrix Ad by:                   we set τω0 to 30-second in this study. At last, the seizure warn-
                                                                   ing system is produced through the proposed CLEP-STS-Net.
                 G i = δ(D −1 Ad δ(µi 21 )22 )              (10)

where G i ∈ R E×F is the dynamic EEG graph underPthe i-                            III. E XPERIMENTAL R ESULTS
                                                            ij
th rhythm, δ is the ELU activation function, D ii =      j Ad      A. Dataset Description
is the degree matrix of Ad , µi ∈ R E×F is the fused                  The effectiveness of the proposed CLEP-STS-Net is evalu-
temporal-spectral feature under the i-th rhythm, where i = 1,      ated on two epileptic datasets described in this section.
2,. . . , 5. 21 ∈ R F×F and 22 ∈ R F×F are the weight matrixes        1) CHB-MIT scalp EEG Dataset [43]: The CHB-MIT dataset
of convolution kernels in the first and second 1 × 1 convolu-      consists of scalp EEG recordings from 23 pediatric patients,
tion layer. Therefore, the spatial information is dynamically      sampled at 256Hz from 18 common electrodes. Details
embedded into temporal-spectral feature under five rhythms.        about CHB-MIT dataset can be found in Table I, including

GUO et al.: CLEP USING A SPATIO-TEMPORAL-SPECTRAL NETWORK                                                                            3921


                            TABLE II                                    value. The p-value is used to evaluate the significance of the
          DATA I NFORMATION OF O UR X UANWU DATABASE                    improvement over a chance predictor [2], [42].

                                                                        C. Overall Performance
                                                                           The proposed CLEP-STS-Net is a more competitive method
                                                                        in the presence of the pyramid convolution net, the triple
                                                                        attention fusion net and the spatio embedded net. In this
                                                                        section, the patient-specific overall performance of the pro-
                                                                        posed CLEP-STS-Net is evaluated by comparing with the
                                                                        following baseline methods. All these methods are retested
115 seizures in total. In this paper, patients with at least two        on two datasets.
seizures and three-hour interictal recordings are included for             1) DCNN+Bi-LSTM [8]: This method used deep con-
the seizure predicting evaluation [2]. Data within two-hour                    volutional network for EEG spatial feature extraction
after a seizure are removed in order to eliminate effect                       and applies a bidirectional LSTM to capture temporal
of postictal period [15]. For the seizure prediction, we are                   features and perform the classification, which is a typical
interested in whether our proposed method can predict the                      deep learning strategy for seizure predicting.
leading seizure. Therefore, in the case where several seizures             2) STFT+CNN [12]: This method first used short-time
cluster within two-hour period, only the first seizure is used                 Fourier transform to generate spectrograms from EEG
[12], [17], [42]. Finally, due to the above criterion, 99 out of               and CNN was adopted for further feature extraction and
115 seizures are used in this paper.                                           classification, which becomes the backbone architecture
   2) Xuanwu iEEG Dataset: The Xuanwu dataset was                              of many seizure predicting model.
recorded by the Xuanwu Hospital of Capital Medical Univer-                 3) CE-stSENet [35]: This method introduced attention
sity, Beijing, China. It contains multi-channel iEEG recordings                mechanism into epileptic seizure classification task,
from 5 patients. Totally there are 19 seizures and each patient                which adopted squeeze-and-excitation attention to model
has at least 2 seizures. The total duration of recordings is                   the dependency between EEG channels and improved
about 42 hours. The start time and end time of each seizure                    the classification performance.
were labeled clearly according to expert judgments. All the
                                                                           Note that the above baseline methods conduct experiments
experimental protocols have been approved by the Ethics
                                                                        using 8, 13 and 19 patients from CHB-MIT dataset in their
Committee of Xuanwu Hospital, and informed consent was
                                                                        original paper, respectively. For a fair and comprehensive
obtained from all patients participated in our study. Details
                                                                        comparison, all these methods are retested under the same
about Xuanwu dataset can be found in Table II.
                                                                        environment and use 19 patients from CHB-MIT dataset. From
   Deep learning-based seizure predicting methods usually
                                                                        Table III, the proposed CLEP-STS-Net yields an average AUC
crop EEG signals into clips through a sliding window ranging
                                                                        of 0.918, while other baseline methods only get average AUC
from 1s to 5s [2], [6], [10], [15]. In this study, for both datasets,
                                                                        of 0.856, 0.886 and 0.857 respectively, which shows the robust
the EEG signals are sampled into 5-second clips before fed
                                                                        classification ability of our proposed method. Especially, AUC
into the proposed CLEP-STS-Net [15]. Moreover, previous
                                                                        values from patient 1, 23 are greater than 0.99, indicating that
studies commonly define the preictal period varying from 15 to
                                                                        our method is capable of distinguishing preictal EEG signals
30 minutes [2], [15], [17]. Inspired by this, we define the 15-
                                                                        from interictal ones. Moreover, our seizure predicting system
minute period before seizure onset as the preictal period, and
                                                                        warns total 96 out of 99 seizures, which also outperforms
define the interictal period at least 2-hour away before seizure
                                                                        all other methods. Meanwhile, the average FPR/h of our
onset and after seizure ending [12], [15].
                                                                        method is 0.072/h, which is lower than the baseline methods.
                                                                        Additionally, the p-values of our predicting system are less
B. Experimental Settings and Evaluation Metrics                         than 0.05 for all patients, which proves the robustness of
                                                                        the proposed CLEP-STS-Net. The comparisons on Xuanwu
   In order to balance the interictal and preictal data, the
                                                                        dataset are given in the Table IV.
interictal clips are randomly sampled to the same number
of preictal clips [8]. Moreover, patient-specific leave-one-out
cross-validation (LOOCV) is used to evaluate the performance            D. Influence of the Contrastive Pretraining Strategy
of the proposed method. Specifically, suppose there are total N            In order to measure how the contrastive pretraining strategy
seizures for a specific patient, N -1 seizures are used for train-      contributes to the model, we remove the CLEP and retest
ing and the left one is for testing. This procedure is repeated         our STS-Net on each patient. From Table V, our CLEP-STS-
for N times, which ensures that all the N seizures are covered          Net achieves a higher Sn of 2.4% on CHB-MIT comparing
in testing. The performance for the specific patient is averaged        to the STS-Net. Moreover, with the CLEP, the FPR/h values
across N times, and the overall performance is averaged across          gets 0.055 and 0.06 lower in two datasets. These increases
all patients. The performance of the proposed CLEP-STS-Net              show that the proposed contrastive learning can effectively
is evaluated by using four metrics: Area under curve (AUC),             benefits the seizure predicting model. In addition, Fig. 5(a)
Sensitivity (Sn , the ratio of truly predicted seizures to the total    and Fig. 5(b) shows the comparing results on two datasets.
number of seizures), False Predicting Rate (FPR/h), and p-              We can see that AUC of all patients are boosted with the

3922                                              IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


                                                             TABLE III
                               T HE OVERALL C OMPARISON OF THE P ERFORMANCE ON CHB-MIT DATABASE


                                                            TABLE IV
                             T HE OVERALL C OMPARISON OF THE P ERFORMANCE ON O UR X UANWU DATABASE


                                                                     Fig. 6. Performance comparison with baseline methods under different
                                                                     amount of training samples per class in the fine-tuning step on CHB-MIT
Fig. 5.  (a) Comparison with and without the CLEP on CHB-MIT;        dataset. “all data” means the model is trained using all available data.
(b) Comparison with and without the CLEP on our Xuanwu dataset;
(c) Comparison between the different reduction ratio r.
                                                                        In addition, we illustrate that our CLEP facilitates the
                                                                     training process of seizure prediction. In Fig. 6, we compare
CLEP involved, which shows the effectiveness of the CLEP             the performance of our CLEP-STS-Net with STS-Net and
in learning general representations for the seizure prediction.      three baseline methods using different amount of the fine-
Especially, benefitting from the contrastive learning, a max-        tuning data. While it is intuitive to expect model with less
imum AUC increasement of 0.01 is reached on the patient              data to underperform model with more data, we instead find
2 from CHB-MIT, and this indicates that the learned represen-        that our CLEP-STS-Net fine-tuned with 450 samples per
tations are not only invariant to subjects but also generalizable    class almost matches the performance of the STS-Net fine-
to different epileptic patterns. Besides, the decrease in standard   tuned with 900 samples per class, and outperforms all other
deviation (Std) among all patients indicate that the CLEP can        methods with 900 samples per class. This is likely due to the
combat the heterogeneity between different patients.                 important pretrained representations generated from the CLEP.

GUO et al.: CLEP USING A SPATIO-TEMPORAL-SPECTRAL NETWORK                                                                        3923


                            TABLE V                                 features and temporal features generated from pyramid con-
              A BLATION S TUDIES ON T WO DATASETS                   volution. In this section, we exploit the advantage of using
                                                                    TAL in the training of seizure predicting model. We first
                                                                    evaluate the performance of our CLEP-STS-Net with or with-
                                                                    out TAL, and show the average AUC, Sn and FPR/h on two
                                                                    datasets in Table V. Concretely, our CLEP-STS-Net achieves
                                                                    a higher AUC of 0.004 and 0.005 comparing to the model
                                                                    without TAL. Moreover, the FPR/h values gets 0.044 and
                                                                    0.011 lower in two datasets with TAL. These increases show
                                                                    that the proposed triple attention fusion method is able to
                                                                    fuse the temporal-spectral features under the preictal transition,
                                                                    which combats the heterogeneity between different patients
                                                                    and effectively benefits the seizure predicting model.
The contrastive pretraining strategy allows for EEG features to
                                                                    G. The Performance of the Spatio Dynamic Graph
be general which facilitates the fine-tuning step. By contrast,
                                                                    Convolution Network
normal supervised learning must train from scratch which
do not utilize any pretrained knowledge [44]. Besides, from            In order to embed spatial epileptic activities into the
Fig. 6, we can observe that, benefited by the contrastive           temporal-spectral responses, the sdGCN is adopted to dynami-
pretraining, our CLEP-STS-Net fine-tuned with 2250 samples          cally model the relationships between electrodes and aggregate
per class matches the performance of the STS-Net trained            spatial information. We further compare the classification
with all data, which reduces the amount of data required for        performance between our CLEP-STS-Net and a simplifier
training to achieve the same seizure predicting performance.        one without sdGCN, and Table V shows the results. We can
Specifically, for CHB-MIT dataset, each patient has an average      see that with sdGCN, AUC and Sn are 0.035 and 1.3%
of 3800 samples for training in this paper. Therefore, an aver-     higher on CHB-MIT, and AUC also gets improvements of
age amount of 2250 samples are required on each patient for         0.015 on Xuanwu dataset. Moreover, the FPR/h declines by
the fine-tuning of CLEP-STS-Net, which is able to match the         0.06 and 0.159 on two datasets. These improvements show
performance of model without the contrastive pretraining, and       that the proposed sdGCN algorithm actually contributes to the
outperforms three baseline methods.                                 seizure predicting, and this is probably due to its learnable
                                                                    transformation which turns the static electrode position into
                                                                    dynamic spatial graph. Next, the reduction ratio r has influence
E. Impact of the Pyramid Convolution Net
                                                                    on the sparsity of the dynamic adjacent matrix Ad , which
   In this subsection, we evaluate the effectiveness of the pyra-   allows us to vary the capacity and computational cost of the
mid convolution net by comparing our CLEP-STS-Net with              sdGCN. The best hyperparameters are subjective and vary
two simplified models: (1) model without spectral pyramid           for each dataset, since the amount of data and the number
net; (2) model without temporal pyramid net. The seizure            of patients are different. To investigate this influence, we set
predicting performances on both datasets are given in Table V       r with the range from 1 to 32 to evaluate the classification
with average AUC, Sn and FPR/h. First, with the waveConv            performance. From Fig. 5(c), we can observe that with r = 8,
layers extracting multi-level spectral features, our CLEP-STS-      it reached the best performance on the Xuanwu datasets; with
Net gains higher AUC than the model without spectral pyramid        r = 16, it achieved the highest AUC for CHB-MIT dataset.
on two datasets, and gains increases of 0.006 and 0.014,               We further investigate how the dynamic adjacent matrix
respectively. Also, the Sn shows increases of 3.2% and 11.7%        Ad changes during training process, and Fig. 7 shows the
and the FPR/h declines by 0.398 and 0.404, which further            transitions from the original adjacent matrix A to the final
demonstrate that the waveConv layers contribute to the seizure      Ad in the training process. We can observe that the zero value
predicting abilities. Moreover, comparing to the model without      in A are replaced by the learned values in the Ad , and this
temporal pyramid, which only captures spectral features from        indicates that certain spatial correlations are built between
EEG, our CLEP-STS-Net yields higher AUC of 0.011 and                the corresponding electrode pairs. Moreover, the original A
0.001, higher Sn of 2.8% and 1.2%, and lower FPR/h of               is transformed from a symmetric matrix into an asymmetric
0.2 and 0.601. These improvements show that extracting only         directed matrix. From the perspective of the causal interaction,
spectral representations may omit important temporal feature        the direction of the information flow between brain regions
responses, which also proves the efficiency of Temporal Pyra-       can reveal more information about brain interactions [45].
mid in extracting multi-scale temporal features. In summary,        Therefore, this directed graph provides more precise infor-
we can learn that the proposed CLEP-STS-Net outperforms             mation than simpler undirected graphs [46], which makes the
the two simplified models on two datasets, which intuitively        sdGCN to learn more diverse information from the electrode
demonstrates the effectiveness of the spectral pyramid net and      position embeddings. Fig. 7 also presents the visualization
temporal pyramid net.                                               of Ad on scalp topologies, which clearly shows how the
                                                                    electrode correlation is built during the training of the sdGCN.
F. The Influence of the Triple Attention Layer                      In addition, we can see that our sdGCN learns a patient-
   Our next attempt is to adopt the triple attention fusion net     specific Ad . If we use the static position embedding method
which helps to alleviate the differences between the spectral       which all patients share the same adjacent matrix, the het-

3924                                                   IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


                            TABLE VI
            T HE C OMPARISON OF M ODEL C OMPACTNESS


                                                                            Fig. 8. (a) The seizure prediction results on one seizure from the typical
Fig. 7. Transitions of the dynamic adjacent matrix Ad during the training   patient 1 of CHB-MIT, where the results are shown one-hour before the
process of the patient 8 from CHB-MIT. (a) the values of Ad ; (b) the 2D    seizure onset; (b) patient-specific seizure prediction time.
visualization of Ad on scalp topologies.
                                                                            due to the lack of temporal and spatial EEG pattern in their
erogeneity of individuals is ignored and not precise enough                 method. In comparison with Ozcan et al. [2] and Zhang et
for a patient-specific seizure prediction method. In summary,               al. [6] which extract features from the frequency and time
compared to the static position embedding method, our sdGCN                 domain, our proposed method considers the spatio-temporal-
learns the dynamic correlations among different EEG channels                spectral representation of EEG and yields 9.7%, 4.71% higher
and embeds the spatial relationships into feature maps, which               in Sn and 0.024, 0.048 lower in FPR/h. Also, compared
boosts the classification performance.                                      with Gao et al. [13] which used a dilated CNN for spatial
                                                                            pattern extraction, our CLEP-STS-Net applies sdGCN to build
                       IV. D ISCUSSIONS                                     patient-specific EEG graphs and embeds spatial information
A. Efficacy of Model Compactness                                            into the temporal-spectral feature maps, and gains a higher Sn
   In order to evaluate the compactness of our CLEP-STS-Net,                of 3.41%. Moreover, compared with our LOOCV validation
we compare the number of parameters with baseline methods                   scheme which does not break the continuity of signals when
in Table VI. The proposed CLEP-STS-Net involves 2.85×105                    testing, 10-fold CV in [11] and [14] shuffles EEG signals and
parameters which is less complex than the DCNN+BiLSTM                       ignores the continuous variation inside seizures. As results,
and similar with the previous CE-stSENet. Although the                      our CLEP-STS-Net achieves more promising Sn and FPR/h
network in STFT+CNN contains less parameters, it is not an                  against most of the recent studies.
end-to-end seizure predicting method and additional computa-
tion cost is spent in building the spectrums before the network.
                                                                            C. Analysis of Seizure Predicting Time
In addition, we evaluate the inference time which starts from
the input of EEG sample and ends with output probability.                      To further evaluate the ability of predicting in time, the
We perform all experiments on Pytorch framework with Intel                  seizure prediction time of each patient is shown in Fig. 8.
Core i7-4790 3.60GHz CPU and the NVIDIA V-100 GPU with                      We use the filter length of 15 for CHB-MIT and 25 for
32GB. Although our proposed CLEP-STS-Net method takes                       Xuanwu, and threshold of 0.6 for both datasets, which are
longer time than the STFT+CNN methods, our inference time                   optimized in Section IV-H. Fig. 8(a) is an example of the pre-
(689.1µs) is much less than the length of an input EEG sample               diction generated by our method on one seizure of the patient
(5s), which is suitable enough for real-time seizure prediction             1 from CHB-MIT. Fig. 8(b) shows the patient-specific seizure
tasks.                                                                      predicting time on two datasets. The proposed CLEP-STS-Net
                                                                            yields average prediction time of 12.62 min on CHB-MIT and
                                                                            11.45 min on Xuanwu, respectively. Especially, for the patient
B. Performance Comparison of Different Methods
                                                                            23 from CHB-MIT, our proposed method advances seizure
  Table VII lists the state-of-the-art methods in seizure pre-              onset with an average prediction time of 14.89 min, which is
diction on CHB-MIT. It is difficult to decide which is the best             early enough for the patient to get prepared for the incoming
approach since each method used a limited set of selected                   seizure.
data according to the pre-defined preictal and interictal inter-
val. For example, Truong et al. [12] and Yang et al. [17]
combined the STFT with CNN and tested their approaches                      D. Visualization Interpretation of Our CLEP-STS-Net
on 13 patients, which resulted in suboptimal performance                      The proposed CLEP-STS-Net can produce robust seizure
compared with our proposed CLEP-STS-Net. This is probably                   prediction results using the epileptic EEG signals. However,

GUO et al.: CLEP USING A SPATIO-TEMPORAL-SPECTRAL NETWORK                                                                                            3925


Fig. 9. Grad-CAM visualization results based on five outputs of the pyramid convolution net, where the EEG data is from the typical patient 1 of
CHB-MIT, the brighter parts are the regions which the model pays more attention to the corresponding class, the top row is the results for interictal
class, and the bottom row is the results for preictal class, respectively.


                                                            TABLE VII
             E XPERIMENTAL S ETTINGS AND THE P ERFORMANCE C OMPARISON OF THE S TATE - OF - THE -A RT M ETHODS ON CHB-MIT


it is hard for human to distinguish between interictal EEG and              Then, the proposed sdGCN is applied to dynamically construct
preictal EEG, so we wonder how the model is able to classify                the spatial correlations between EEG electrodes. Finally, the
the EEG samples. Therefore, we adopt the Gradient-weighted                  contrastive learning strategy CLEP learns the intrinsic epileptic
Class Activation Mapping (Grad-CAM) to visualize how our                    patterns from source subjects and improves the generalization
CLEP-STS-Net learns from the interictal and preictal EEG                    ability. Seizure prediction performance is evaluated on mul-
signals. We concatenate one interictal sample and one preictal              tiple patients with both scalp EEG and iEEG signals. Our
sample as input and use the five outputs of the pyramid                     proposed CLEP-STS-Net yields promising results in AUC,
convolution net for the visualization, where each represents                Sn and FPR/h, which outperform all the compared baseline
a certain rhythm. Fig. 9 shows the activation maps generated                methods. Moreover, we evaluate the effectiveness of the CLEP,
by Grad-CAM, and we can see that when the input EEG is                      pyramid convolution net, TAL and sdGCN through ablation
labeled with interictal class, the activation maps are brighter             studies. Additionally, the visualization investigation shows that
in the interictal period. Also, when the input is labeled with              our proposed method is able to extract spatio-temporal-spectral
preictal class, the model focuses mainly on the preictal period.            features related to different rhythms from epileptic EEG
The different regions of interests in temporal period indicates             signals. Experimental results demonstrate that the proposed
that our CLEP-STS-Net is sensitive to the temporal transitions              CLEP-STS-Net can predict the incoming seizures accurately
of epileptic EEG. In addition, from Fig. 9, we can see that                 and further facilitate epileptic patients’ daily life.
this difference is more distinct in δ and θ rhythms, where
we can observe a clear transition of the f region of interests                                              R EFERENCES
from interictal class to preictal class. This indicates that the             [1] L. Xie, Z. Deng, P. Xu, K.-S. Choi, and S. Wang, “Generalized hidden-
                                                                                 mapping transductive transfer learning for recognition of epileptic
preictal EEG tends to activate our CLEP-STS-Net especially                       electroencephalogram signals,” IEEE Trans. Cybern., vol. 49, no. 6,
in δ and θ rhythms, which is in line with the previous studies                   pp. 2200–2214, Jun. 2019.
that the propagation of seizure causes a shifting from higher                [2] A. R. Ozcan and S. Erturk, “Seizure prediction in scalp EEG using 3D
                                                                                 convolutional neural networks with an image-based approach,” IEEE
rhythm activities in a focal region to slower rhythms across                     Trans. Neural Syst. Rehabil. Eng., vol. 27, no. 11, pp. 2284–2293,
widespread areas [15].                                                           Nov. 2019.
                                                                             [3] G. Wang et al., “Seizure prediction using directed transfer function and
                                                                                 convolution neural network on intracranial EEG,” IEEE Trans. Neural
                      V. C ONCLUSION                                             Syst. Rehabil. Eng., vol. 28, no. 12, pp. 2711–2720, Dec. 2020.
  In this paper, a novel epileptic seizure prediction system is              [4] T. Yu et al., “High-frequency stimulation of anterior nucleus of tha-
                                                                                 lamus desynchronizes epileptic network in humans,” Brain, vol. 141,
built by using the proposed CLEP-STS-Net. Specifically, our                      pp. 2631–2643, Jul. 2018.
STS-Net first extracts multi-scale temporal-spectral features                [5] P. Jin, D. Wu, X. Li, L. Ren, and Y. Wang, “Towards precision medicine
under different rhythms through the pyramid convolution net.                     in epilepsy surgery,” Ann. Transl. Med., vol. 4, no. 2, p. 24, Jan. 2016.
Meanwhile, an attention mechanism called TAL is adopted                      [6] Y. Zhang, Y. Guo, P. Yang, W. Chen, and B. Lo, “Epilepsy seizure
                                                                                 prediction on EEG using common spatial pattern and convolutional
to construct inter-dimensional dependencies among feature                        neural network,” IEEE J. Biomed. Health Informat., vol. 24, no. 2,
maps and effectively fused the temporal-spectral features.                       pp. 465–474, Feb. 2020.

3926                                                       IEEE TRANSACTIONS ON NEURAL SYSTEMS AND REHABILITATION ENGINEERING, VOL. 31, 2023


 [7] K. M. Tsiouris, V. C. Pezoulas, M. Zervakis, S. Konitsiotis,                [27] S. Jang, S.-E. Moon, and J.-S. Lee, “Eeg-based video identification using
     D. D. Koutsouris, and D. I. Fotiadis, “A long short-term Memory deep             graph signal modeling and graph convolutional neural network,” in Proc.
     learning network for the prediction of epileptic seizures using EEG              IEEE Int. Conf. Acoust., Speech Signal Process. (ICASSP), Apr. 2018,
     signals,” Comput. Biol. Med., vol. 99, pp. 24–37, Aug. 2018.                     pp. 3066–3070.
 [8] H. Daoud and M. A. Bayoumi, “Efficient epileptic seizure prediction         [28] M. Wang, H. El-Fiqi, J. Hu, and H. A. Abbass, “Convolutional neural
     based on deep learning,” IEEE Trans. Biomed. Circuits Syst., vol. 13,            networks using dynamic functional connectivity for EEG-based person
     no. 5, pp. 804–813, Oct. 2019.                                                   identification in diverse human states,” IEEE Trans. Inf. Forensics
 [9] C. Li et al., “Seizure onset detection using empirical mode decompo-             Security, vol. 14, no. 12, pp. 3259–3272, Dec. 2019.
     sition and common spatial pattern,” IEEE Trans. Neural Syst. Rehabil.       [29] P. Zhong, D. Wang, and C. Miao, “EEG-based emotion recognition
     Eng., vol. 29, pp. 458–467, 2021.                                                using regularized graph neural networks,” IEEE Trans. Affect. Comput.,
[10] T. Liu, N. D. Truong, A. Nikpour, L. Zhou, and O. Kavehei, “Epileptic            vol. 13, no. 3, pp. 1290–1301, Jul. 2022.
     seizure classification with symmetric and hybrid bilinear models,” IEEE     [30] Y. Li, L. Guo, Y. Liu, J. Liu, and F. Meng, “A temporal-spectral-
     J. Biomed. Health Informat., vol. 24, no. 10, pp. 2844–2851, Oct. 2020.          based squeeze-and- excitation feature fusion network for motor imagery
[11] H. Khan, L. Marcuse, M. Fields, K. Swann, and B. Yener, “Focal onset             EEG decoding,” IEEE Trans. Neural Syst. Rehabil. Eng., vol. 29,
     seizure prediction using convolutional networks,” IEEE Trans. Biomed.            pp. 1534–1545, 2021.
     Eng., vol. 65, no. 9, pp. 2109–2118, Sep. 2018.                             [31] D. Freer and G.-Z. Yang, “Data augmentation for self-paced motor
[12] N. D. Truong et al., “Convolutional neural networks for seizure predic-          imagery classification with C-LSTM,” J. Neural Eng., vol. 17, no. 1,
     tion using intracranial and scalp electroencephalogram,” Neural Netw.,           Feb. 2020, Art. no. 016041.
     vol. 105, pp. 104–111, Sep. 2018.                                           [32] Y. Li, X.-D. Wang, M.-L. Luo, K. Li, X.-F. Yang, and Q. Guo, “Epileptic
[13] Y. Gao et al., “Pediatric seizure prediction in scalp EEG using a multi-         seizure classification of EEGs using time–frequency analysis based
     scale neural network with dilated convolutions,” IEEE J. Transl. Eng.            multiscale radial basis functions,” IEEE J. Biomed. Health Informat.,
     Health Med., vol. 10, 2022, Art. no. 4900209.                                    vol. 22, no. 2, pp. 386–397, Mar. 2018.
[14] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C. Fookes,        [33] K. P. Indiradevi, E. Elias, P. S. Sathidevi, S. D. Nayak, and
     “Geometric deep learning for subject independent epileptic seizure               K. Radhakrishnan, “A multi-level wavelet approach for automatic detec-
     prediction using scalp EEG signals,” IEEE J. Biomed. Health Informat.,           tion of epileptic spikes in the electroencephalogram,” Comput. Biol.
     vol. 26, no. 2, pp. 527–538, Feb. 2022.                                          Med., vol. 38, no. 7, pp. 805–816, Jul. 2008.
[15] Y. Li, Y. Liu, Y.-Z. Guo, X.-F. Liao, B. Hu, and T. Yu, “Spatio-temporal-   [34] L. Wang et al., “Automatic epileptic seizure detection in EEG signals
     spectral hierarchical graph convolutional network with semisupervised            using multi-domain feature extraction and nonlinear analysis,” Entropy,
     active learning for patient-specific seizure prediction,” IEEE Trans.            vol. 19, no. 6, p. 222, May 2017.
     Cybern., vol. 52, no. 11, pp. 12189–12204, Nov. 2022.                       [35] Y. Li, Y. Liu, W.-G. Cui, Y.-Z. Guo, H. Huang, and Z.-Y. Hu, “Epileptic
[16] J.-S. Bang, M.-H. Lee, S. Fazli, C. Guan, and S.-W. Lee, “Spatio-                seizure detection in EEG signals using a unified temporal-spectral
     spectral feature representation for motor imagery classification using           squeeze-and-excitation network,” IEEE Trans. Neural Syst. Rehabil.
     convolutional neural networks,” IEEE Trans. Neural Netw. Learn. Syst.,           Eng., vol. 28, no. 4, pp. 782–794, Apr. 2020.
     vol. 33, no. 7, pp. 3038–3049, Jul. 2022.                                   [36] Q. Lian, Y. Qi, G. Pan, and Y. Wang, “Learning graph in graph
[17] X. Yang, J. Zhao, Q. Sun, J. Lu, and X. Ma, “An effective dual self-             convolutional neural networks for robust seizure prediction,” J. Neural
     attention residual network for seizure prediction,” IEEE Trans. Neural           Eng., vol. 17, no. 3, Jun. 2020, Art. no. 035004.
     Syst. Rehabil. Eng., vol. 29, pp. 1604–1613, 2021.                          [37] Y. Li, X.-R. Zhang, B. Zhang, M.-Y. Lei, W.-G. Cui, and Y.-Z. Guo,
[18] L. S. Vidyaratne, M. Alam, A. M. Glandon, A. Shabalina, C. Tennant,              “A channel-projection mixed-scale convolutional neural network for
     and K. M. Iftekharuddin, “Deep cellular recurrent network for efficient          motor imagery EEG decoding,” IEEE Trans. Neural Syst. Rehabil. Eng.,
     analysis of time-series data with spatial information,” IEEE Trans.              vol. 27, no. 6, pp. 1170–1180, Jun. 2019.
     Neural Netw. Learn. Syst., vol. 33, no. 11, pp. 6215–6225, Nov. 2022.       [38] J. Hu, L. Shen, S. Albanie, G. Sun, and E. Wu, “Squeeze-and-excitation
[19] Y. Zhao, C. Li, X. Liu, R. Qian, R. Song, and X. Chen, “Patient-specific         networks,” IEEE Trans. Pattern Anal. Mach. Intell., vol. 42, no. 8,
     seizure prediction via adder network and supervised contrastive learn-           pp. 2011–2023, Aug. 2020.
     ing,” IEEE Trans. Neural Syst. Rehabil. Eng., vol. 30, pp. 1536–1547,       [39] X. Li, W. Wang, X. Hu, and J. Yang, “Selective kernel networks,”
     2022.                                                                            in Proc. IEEE/CVF Conf. Comput. Vis. Pattern Recognit. (CVPR),
[20] X. Shen, X. Liu, X. Hu, D. Zhang, and S. Song, “Contrastive learning of          Jun. 2019, pp. 510–519.
     subject-invariant EEG representations for cross-subject emotion recog-      [40] T.-Y. Lin, P. Dollár, R. Girshick, K. He, B. Hariharan, and S. Belongie,
     nition,” IEEE Trans. Affect. Comput., vol. 14, no. 3, pp. 2496–2511,             “Feature pyramid networks for object detection,” in Proc. IEEE Conf.
     Jul. 2023, doi: 10.1109/TAFFC.2022.3164516.                                      Comput. Vis. Pattern Recognit. (CVPR), Jul. 2017, pp. 936–944.
[21] H. Banville, O. Chehab, A. Hyvärinen, D.-A. Engemann, and                   [41] D. Zhang, L. Yao, K. Chen, S. Wang, X. Chang, and Y. Liu, “Mak-
     A. Gramfort, “Uncovering the structure of clinical EEG signals with              ing sense of spatio-temporal preserving representations for EEG-based
     self-supervised learning,” J. Neural Eng., vol. 18, no. 4, Mar. 2021,            human intention recognition,” IEEE Trans. Cybern., vol. 50, no. 7,
     Art. no. 046020.                                                                 pp. 3033–3044, Jul. 2020.
[22] T. Song et al., “Variational instance-adaptive graph for EEG emotion        [42] D. E. Snyder, J. Echauz, D. B. Grimes, and B. Litt, “The statistics
     recognition,” IEEE Trans. Affect. Comput., vol. 14, no. 1, pp. 343–356,          of a practical seizure warning system,” J. Neural Eng., vol. 5, no. 4,
     Jan. 2023.                                                                       pp. 392–401, Dec. 2008.
[23] S. Woo, J. Park, J. Y. Lee, and I. S. Kweon, “CBAM: Convolutional           [43] A. H. Shoeb, “Application of machine learning to epileptic seizure onset
     block attention module,” in Proc. Eur. Conf. Comput. Vis. (ECCV).                detection and treatment,” Ph.D. dissertation, Harvard-MIT Health Sci.
     Cham, Switzerland: Springer, 2018, pp. 3–19.                                     Technol., Massachusetts Inst. Technol., Cambridge, MA, USA, 2009.
[24] T. Zhang, W. Zheng, Z. Cui, Y. Zong, and Y. Li, “Spatial–temporal           [44] A. Radford et al., “Learning transferable visual models from natural
     recurrent neural network for emotion recognition,” IEEE Trans. Cybern.,          language supervision,” in Proc. 38th Int. Conf. Mach. Learn., vol. 139,
     vol. 49, no. 3, pp. 839–847, Mar. 2019.                                          2021, pp. 8748–8763.
[25] T. Zhang, X. Wang, X. Xu, and C. L. P. Chen, “GCB-Net: Graph                [45] M. Lobier, F. Siebenhühner, S. Palva, and J. M. Palva, “Phase transfer
     convolutional broad network and its application in emotion recognition,”         entropy: A novel phase-based measure for directed connectivity in
     IEEE Trans. Affect. Comput., vol. 13, no. 1, pp. 379–388, Jan. 2022.             networks coupled by oscillatory interactions,” NeuroImage, vol. 85,
[26] D. Zhang, L. Yao, K. Chen, S. Wang, P. D. Haghighi, and C. Sullivan,             pp. 853–872, Jan. 2014.
     “A graph-based hierarchical attention model for movement intention          [46] F. Hasanzadeh, M. Mohebbi, and R. Rostami, “Graph theory analysis of
     detection from EEG signals,” IEEE Trans. Neural Syst. Rehabil. Eng.,             directed functional brain networks in major depressive disorder based on
     vol. 27, no. 11, pp. 2247–2253, Nov. 2019.                                       EEG signal,” J. Neural Eng., vol. 17, no. 2, Mar. 2020, Art. no. 026010.
```
