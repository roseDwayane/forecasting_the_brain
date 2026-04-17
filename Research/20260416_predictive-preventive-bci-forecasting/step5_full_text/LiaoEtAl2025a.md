---
citation_key: "LiaoEtAl2025a"
paper_id: "paper_154"
title: "An EEG-Based Seizure Prediction Model Encoding Brain Network Temporal Dynamics."
authors: "Jiahui Liao; Yiyi Chen; Yihang He; Kai Zhang; Ting Ma; Yilong Wang; Xiaoqiu Shao"
year: 2025
doi: "10.1109/jbhi.2025.3584861"
source: "publisher-pdf (doi: 10.1109/jbhi.2025.3584861)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# An EEG-Based Seizure Prediction Model Encoding Brain Network Temporal Dynamics.

**Citation:** `LiaoEtAl2025a` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/jbhi.2025.3584861](https://doi.org/10.1109/jbhi.2025.3584861)
**Source PDF:** `full_pdf/Jiahui2025.pdf`

## Abstract

EEG-based seizure prediction enables timely latent representation, endowed with physiological priors, is treatment for patients, but its performance is limited by ultimately utilized for patient-independent seizure predic- the difficulty in effectively characterizing the temporal dy- tion. We evaluate our method on two publicly available and namics of epileptic brain networks. Metastability, which de- one clinical scalp EEG datasets. Compared to the existing scribes recurring topographical patterns of spontaneous methods, our method has improved AUC, sensitivity, and neural activity over time, provides a unique perspective specificity on CHB-MIT dataset by approximately 9%, 5%, for capturing the dynamic evolution before seizure onset. and 5%, respectively. Our method shows that combining In this study, we propose a seizure prediction model that brain network-based physiological prior with deep learning fuses consistent epileptic network processes across sub- for EEG representation learning is a brand-new strategy jects into a higher-order latent space. Specifically, we first for associating seizures with complex brain network varia- construct metastable transition patterns to identify the re- tions, enabling reliable patient-independent seizure predic- current network states over time. Through adversarial fea- tion. ture learning, we then impose the metastability prior on the latent embedding space encoded via a variational autoen-

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025                                   8059


       An EEG-Based Seizure Prediction Model
      Encoding Brain Network Temporal Dynamics
     Jiahui Liao , Yiyi Chen , Yihang He , Kai Zhang , Ting Ma , Member, IEEE, Yilong Wang ,
                                         and Xiaoqiu Shao


   Abstract—EEG-based seizure prediction enables timely                          latent representation, endowed with physiological priors, is
treatment for patients, but its performance is limited by                        ultimately utilized for patient-independent seizure predic-
the difficulty in effectively characterizing the temporal dy-                    tion. We evaluate our method on two publicly available and
namics of epileptic brain networks. Metastability, which de-                     one clinical scalp EEG datasets. Compared to the existing
scribes recurring topographical patterns of spontaneous                          methods, our method has improved AUC, sensitivity, and
neural activity over time, provides a unique perspective                         specificity on CHB-MIT dataset by approximately 9%, 5%,
for capturing the dynamic evolution before seizure onset.                        and 5%, respectively. Our method shows that combining
In this study, we propose a seizure prediction model that                        brain network-based physiological prior with deep learning
fuses consistent epileptic network processes across sub-                         for EEG representation learning is a brand-new strategy
jects into a higher-order latent space. Specifically, we first                   for associating seizures with complex brain network varia-
construct metastable transition patterns to identify the re-                     tions, enabling reliable patient-independent seizure predic-
current network states over time. Through adversarial fea-                       tion.
ture learning, we then impose the metastability prior on the
latent embedding space encoded via a variational autoen-                           Index Terms—Adversarial inference, electroencephal-
coder (VAE), while leveraging the maximum mean discrep-                          ogram (EEG), metastability analysis, seizure prediction.
ancy measure (MMD) to further mitigate the patient gap. The


   Received 24 January 2025; revised 17 May 2025; accepted 21 June                                           I. INTRODUCTION
2025. Date of publication 2 July 2025; date of current version 7 Novem-
                                                                                       PILEPSY is a disorder of brain networks caused by abnor-
ber 2025. This work was supported in part by the National Natural
Science Foundation of China under Grant 62276081, Grant 82271495,
and Grant 82425101, and in part by the Noncommunicable Chronic
                                                                                 E     mal, hyper-synchronous, and paroxysmal neuronal activity
                                                                                 [1], [2]. The scalp electroencephalogram (EEG) is one of the
Diseases-National Science and Technology Major Project under Grant
2023ZD0504800. (Jiahui Liao and Yiyi Chen are co-first authors.) (Cor-           most versatile tools for clinical diagnosis and retrospective
responding authors: Ting Ma; Yilong Wang; Xiaoqiu Shao.)                         analysis of epilepsy [3]. In this case, effectively utilizing EEG
   This work involved human subjects or animals in its research. Ap-             data to characterize the evolution of epileptic networks is crucial
proval of all ethical and experimental procedures and protocols was
granted by Beijing Tiantan Hospital Institutional Review Board under Ap-         for accurate seizure prediction.
plication No. KY2023-079-01, and performed in line with the declaration             Considerable research has demonstrated the feasibility of
of Helsinki.                                                                     modeling epileptic dynamic transitions from a global network
   Jiahui Liao and Yihang He are with the School of Informa-
tion Science and Technology, Harbin Institute of Technology (Shen-               perspective [4], [5], [6]. For example, altered patterns of β- and
zhen), Shenzhen 518055, China (e-mail: 23B952013@stu.hit.edu.cn;                 γ-band brain network connectivity are potential biomarkers for
23B952009@stu.hit.edu.cn).                                                       monitoring seizure cycles in West syndrome [7]. The interictal
   Yiyi Chen is with the Department of Neurology, Beijing Tiantan Hos-
pital, Capital Medical University, Beijing 100070, China, also with the          suppression hypothesis in focal epilepsy has gained network-
National Center for Neurological Disorders, Beijing 100070, China, and           level supporting evidence [8]. However, traditional statistical
also with the China National Clinical Research Center for Neurological           tools or machine learning used in these approaches are often
Diseases, Beijing 100070, China (e-mail: cyeeyeee@163.com).
   Kai Zhang is with the Department of Neurosurgery, Beijing Tiantan             deficient in modeling high order nonlinear intrinsic, limiting
Hospital, Capital Medical University, Beijing 100070, China (e-mail:             their performance. Graph convolutional network (GCN) models,
zhangkai62035@sina.com).                                                         which capture the structural information within feature interac-
   Ting Ma is with the School of Biomedical Engineering, Harbin
Institute of Technology (Shenzhen), Shenzhen 518055, China, and                  tions in the graph domain, have been widely used for associating
also with Peng Cheng Laboratory, Shenzhen 518066, China (e-mail:                 seizure disorders with complex brain network variations [9],
tma@hit.edu.cn).                                                                 [10], [11]. Given that seizure-related brain regions are not stably
   Yilong Wang is with the Department of Neurology, Beijing Tiantan
Hospital, Capital Medical University, Beijing 100070, China, also with           uniformly distributed in the whole-brain network, conventional
the Chinese Institute for Brain Research, Beijing 100070, China, and             graph learning approaches, mostly based on fixed graphs, are
also with the Advanced Innovation Center for Human Brain Protec-                 incapable of fully modeling the dynamics transition during the
tion, Capital Medical University, Beijing 100070, China (e-mail: yi-
long528@aliyun.com).                                                             seizure-related periods.
   Xiaoqiu Shao is with the Department of Neurology, Beijing Tiantan                Originally attributed to constant coupling and decoupling of
Hospital, Capital Medical University, Beijing 100070, China, and also            neural populations [12], metastability serves as a mechanism to
with the China National Clinical Research Center for Neurological Dis-
eases, Beijing 100070, China (e-mail: shaoxiaoqiu2000@aliyun.com).               describe the dynamic, self-organizing neural process [13], [14],
   Digital Object Identifier 10.1109/JBHI.2025.3584861                           [15], [16]. The metastable substates are transient, quasi-stable
2168-2194 © 2025 IEEE. All rights reserved, including rights for text and data mining, and training of artificial intelligence and similar technologies.
   Personal use is permitted, but republication/redistribution requires IEEE permission. See https://www.ieee.org/publications/rights/index.html
                                                                 for more information.

         Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8060                                                        IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


neural coupling patterns that recur sequentially over time within               after a seizure), and interictal (the interval between post-ictal
EEG recordings. It has been utilized to explore the dynamic                     and pre-ictal) [26], [27]. Seizure prediction, therefore, depends
brain states during anesthesia [17], as well as neurodegener-                   on the accurate classification of pre- and interictal EEG signals.
ative diseases modulated by temporal dependencies, such as                         The schematic representation of our proposed MaDin is
amyotrophic lateral sclerosis [18] and Alzheimer’s disease [19].                shown in Fig. 1. MaDin is evaluated with reference to actual
Metastability analysis has the potential to provide new insights                clinical patient inclusion. As shown in Fig. 1(a), each subject
into the temporal dynamics within functional brain networks in                  in the datasets will be specified as the newly admitted patient
epilepsy.                                                                       (target patient). Only one seizure of the target patient is exploited
   Integrating established domain knowledge with data-driven                    for training together with the samples of other subjects, while
deep learning, known as knowledge-augmented [20] and model-                     the remaining target seizures served as the testing set. After
based deep learning [21] paradigms, is one of an increasing                     obtaining the raw epileptic EEG signals, the model constructs
focus in artificial intelligence, aiming to create more robust                  metastability prior and encodes latent representation with VAE
and interpretable models. In patient-independent seizure pre-                   simultaneously. The latent representation is then incorporated
diction, existing studies have attempted to introduce knowledge                 into the brain state information through adversarial inference
priors based on general statistical properties like the Laplace                 and generalized across subjects through MMD measure. Sec-
distribution [22], or the geometric structures of EEG signal                    tions II-A–II-D describe the details of these steps.
[23], to overcome the significant variability and noise in EEG
signals. Inspired by the principles of incorporating domain                     A. Dataset Description
knowledge to guide data-driven models, in this study, we pro-
                                                                                   This study evaluates performance using two publicly available
pose a patient-independent seizure prediction model, MaDin,
                                                                                scalp EEG datasets and one clinical dataset. The CHB-MIT scalp
which explicitly encodes the metastable properties of epilep-
                                                                                EEG database includes recordings from 23 pediatric patients
tic networks, a physiologically-grounded prior, within a deep
                                                                                off anti-epileptic drugs within a few days, sourced on Phys-
learning framework. Specifically, this work introduces a novel
                                                                                ioNet (https://physionet.org/content/chbmit/1.0.0/) [24]. Most
prior based on metastability analysis. To preserve higher-order
                                                                                data are collected through 22 channels with a sampling rate
nonlinear information and generalize better on the target patient,
                                                                                of 256 Hz, including 844 hours of continuous EEG record-
a variational autoencoder (VAE) is then employed to learn a
                                                                                ing. The Siena dataset contains scalp EEG recordings of 14
latent embedding space that approximates a normal distribution.
                                                                                adults off anti-epileptic drugs, accessible on PhysioNet (https://
The aggregated posterior of the latent space is matched with the
                                                                                physionet.org/content/siena-scalp-eeg/1.0.0/) [25]. Continuous
metastability prior through adversarial feature learning, while
                                                                                EEG recordings are collected through 29 channels at a sampling
the maximum mean discrepancy (MMD) measure is used to
                                                                                rate of 512 Hz.
align the distribution across subjects. This approach ensures that
                                                                                   The clinical dataset includes EEG recordings of seven
the learned latent representation captures both subject-invariant
                                                                                epilepsy patients recruited at the outpatient ward of Beijing
information and disease-related neural features, enabling reli-
                                                                                Tiantan Hospital, Capital Medical University. The long-term
able patient-independent seizure prediction. We have evaluated
                                                                                EEG recordings are collected for pre-operative assessment
our method on CHB-MIT [24], Siena epilepsy datasets [25], and
                                                                                through 21 channels with a sampling rate of 250 Hz. The study
a clinical dataset. Our contributions are summarized below:
                                                                                protocol has received approval from the Beijing Tiantan Hospital
    1) We propose a patient-independent seizure prediction
                                                                                Institutional Review Board (KY2023-079-01). All patients are
        model, MaDin, that fuses metastability prior to latent
                                                                                provided with written informed consent before participation.
        representations through adversarial inference. The learnt
                                                                                   The pre-ictal period is set at 30 minutes, consistent with
        epileptic representations are encoded with brain network
                                                                                previous studies [26]. Patients with well-defined seizure types
        temporal dynamics and sufficient in high-order nonlinear
                                                                                (focal/generalized, if focal: temporal/frontal/occipital) are in-
        intrinsic attributes.
                                                                                cluded. Accordingly, this study utilizes the EEG data of ten
    2) For the first time, we characterize metastable properties
                                                                                qualified patients from the CHB-MIT dataset, six from Siena,
        to investigate the temporal dynamics of brain networks
                                                                                and seven from the clinical dataset. Relevant information is
        during seizure evolution. Consistent metastable patterns
                                                                                presented in Tables V– VII.
        across patients reflect common epileptic network be-
        haviors, which are key to achieving reliable prediction
        performance.                                                            B. EEG Preprocessing
    3) Our MaDin demonstrates promising prediction per-                             For the public available datasets (i.e., CHB-MIT and Siena
        formance on two publicly available and one clinical                     datasets), the EEG data is filtered using a zero-phase high-pass
        scalp EEG datasets, outperforming existing patient-                     filter (−3 dB cutoff frequency at 0.5 Hz) and a low-pass filter
        independent models on the CHB-MIT dataset.                              (−3 dB cutoff frequency at 45 Hz), which excludes the DC
                                                                                component and power line interference, while preserving the
                                                                                major frequency components of epileptic EEG signals [28].
                            II. METHODS
                                                                                For the clinical dataset, interpolation of the bad channels, and
   In computer-aided epilepsy studies, the long-term EEG signal                 exclusion of the bad segments are followed after filtering.
is typically divided into four states: pre-ictal (the period before             Independent component analysis (ICA) is performed to identify
a seizure), ictal (during a seizure), post-ictal (the short period              and remove artifactual components related to eye movements,
       Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                  8061


Fig. 1. The schematic representation of our proposed patient-independent seizure prediction model. (a) We begin by dividing the subjects, each
of whom will be specified as the newly admitted patient (target subject) and then perform segmentation. (b) We construct metastability prior
through four main steps: phase coherence of EEG signal for function connectivity estimation, leading eigenvector generation, modified K-means
clustering for metastable substate definition, and brain state descriptions through substate characteristics. (c) A variation autoencoder (VAE) is
employed to learn the latent representation in a low-dimensional space while simultaneously preserving the high-order nonlinear information. The
network architecture of the encoder consists of convolution layers followed by batch normalization and leaky ReLU activation. The decoder consists
of the deconvolution layers followed by batch normalization and ReLU activation. (d) Feature fusion between the learnt latent space and the
metastability prior is achieved through adversarial inference, and MMD regularization term Rmmd is used to reduce the between-subjects variance.
(e) Classification network is connected to the subject-invariant feature space for seizure prediction.


muscle activity, and other non-neural sources. The EEG dataset                   between multiple recurrent metastable substates and quantifies
is finally re-referenced by the average reference. The EEG data is               brain states from the probabilistic metastable substate (PMS)
preprocessed with the EEGLAB toolbox (version 2022.0) [29],                      space.
[30].                                                                               Following [31], we utilized instantaneous phase locking to
    The data is then partitioned into pre- and inter-ictal segments              construct the dynamic functional brain network. The phase of
based on expert annotations provided with the datasets. The                      EEG signals in all channels θ(ni , t) is firstly computed using
inter-ictal period is much longer than the pre-ictal period, leading             Hilbert transform [33]. The instantaneous phase locking be-
to an imbalanced data problem. This study thus performs random                   tween each pair of brain regions ni and nj at each timepoint
subsampling on the inter-ictal sample to make an equal quantity                  t was estimated as the cosine of the relative phase difference as
of sample distribution. By setting the sliding window of t-second                follows:
with 0.5 overlaps, each t-sec EEG segment is represented as a
                                                                                              iP L (n, p, t) = cos( θ (ni , t) − θ (nj , t))              (1)
matrix of dimension (C, f × t), where C denotes the number of
channels and f represents the sampling rate, t is set to 20 for all              phase-locking at a given timepoint ranges from -1 (low phase
three datasets.                                                                  synchronization) and 1 (high phase synchronization). For each
                                                                                 EEG segment, the corresponding iPL is a three-dimensional
                                                                                 tensor of size (C, C, T), where C is the number of channels,
C. Metastability Analysis
                                                                                 and T is the number of time points.
   To explore the temporal dynamics in the brain network during                     The leading eigenvector V1 (t) of each iP L(t) is a C × 1 vec-
seizure evolution, a novel framework—leading eigenvector dy-                     tor, obtained from the eigenvector corresponding to the largest
namics analysis (LEiDA) [31], [32]—is exploited to analyze the                   eigenvalue of the matrix. It reflects the dominant functional
metastability properties of brain networks as shown in Fig. 1(b).                connectivity (FC) pattern at timepoint t, which can be recon-
LEiDA characterizes brain states as non-random transitions                       structed using the outer product V1 (t)V1 (t)T . Each element
         Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8062                                                        IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


in V1 (t) represents the projection of the EEG phase of each                      Algorithm 1: Metastability Prior Construction.
channel into the leading eigenvector, with positive and negative
                                                                                    Input: Raw multichannel EEG segments X ∈ RN ×C×T
signs indicating the orientation of the EEG signal. In this regard,
                                                                                    Output: Subject-invariant metastable representation
the whole brain regions are naturally divided into two clusters,
                                                                                     P ∈ RN ×16
representing the emergence of local sub-networks during the
                                                                                     1: Calculate instantaneous phase locking iP L ∈ RC×C×t
dynamic changes in the brain networks.
                                                                                       according to (1).
   To identify recurrent FC patterns across subjects and states, a
                                                                                     2: Eigenvalue decomposition for each iP L(·, ti ) to obtain
modified K-means clustering algorithm [34] is applied to divide
                                                                                       the leading eigenvector V1 (ti ) ∈ RC×1 .
the set of all eigenvectors of both pre- and inter-ictal states into a
                                                                                     3: for number of clusters k = 3 → 10 do
predefined number of clusters k. The returned k cluster centroid
                                                                                     4: Apply modified K-means clustering algorithm to map
vectors VC with the shape of C × 1 represent the repetitive
                                                                                         all eigenvectors V1 (t) into k clusters to generate
substates. All leading eigenvectors at each time point will be
                                                                                         discrete state sequence.
assigned to the specific cluster through cosine distance measure,
                                                                                     5: Cross validation to obtain the optimal k = 5, the
generating a discrete state sequence. The optimal number of
                                                                                         cluster centroid vectors VC ∈ RC×1 represent the
clusters, meant to metastable substates Si ∈ {S1 , S2 , . . . , Sk },
                                                                                         repetitive metastable substates Si ∈ {S1 , S2 , . . . , Sk }.
is selected using a cross-validation approach on a subset of 3–10
                                                                                     6: end for
phase-locking patterns. In this study, k = 5.
                                                                                     7: Calculate the four main metastable metrics for each
                                                                                       discrete state sequence according to (2)-(5).
D. The Proposed Patient-independent Seizure                                          8: The most significant sixteen metastable matrices are
Prediction Model (MaDin)                                                               selected as metastability prior P ∈ RN ×16 based
   1) Metastability prior construction: To quantify common dif-                        Permutation-based paired t-test with a 10% adaptive
ferences in the functional network from PMS space between pre-                         FDR.
and inter-ictal states across subjects, network-level metastable
features of discrete state sequence are screened down based
on the statistical analysis. Specifically, the sub-sequence cor-                substates (S1, S2, S3, S4, and S5, respectively). The sixteen
responding to each t-sec EEG segment is derived from the                        most significant parameters are finally selected to construct the
discrete state sequence obtained via LEiDA. For metastable                      metastability prior, Pm . The overall algorithm of metastability
substatesSi ∈ {S1 , S2 , . . . , Sk }, tSi and nSi represent the total          prior construction is described in Algorithm 1.
duration and the number of the occurrence of Si , respectively.                     2) Latent Coding Space with Adversarial VAE:
nSi ,Sj is the number of transitions from Si to Sj . Four main                      a) Notation: Suppose there are M-1 existing subjects an
metastable metrics are calculated for each sub-sequence as                             one target patient in total. The input EEG samples from
follows.                                                                               M subjects are denoted by Xi = [xi1 , xi2 , . . . , xiNi ]T ,
   Duration: The average duration after each state occurs.                             where i ∈ {1, . . . , M }, xiNi ∈ RC×T , and Ni is the
                                       tS i                                            number of the subject i. The one-hot encoding vectors
                             DS i =                                      (2)           about labels are denoted by Yi = [yi1 , yi2 , . . . , yiNi ]T ,
                                       nSi
                                                                                       where yiNi ∈ Rd×1 , and d = 2 is the number of classes
  Occurrence: The average number of occurrences of each                                corresponding to the pre-ictal and ictal state. The metasta-
                                                                                                                                                    m T
substate per second.                                                                   bility prior is denoted by Pm               m m
                                                                                                                          i = [pi1 , pi2 , . . . , piNi ] ,
                               nS                                                      where pmiNi ∈ R
                                                                                                        r×1
                     OS i =  k i                    (3)                                                     , and r is set to 16 corresponding to the
                              m=1 tSm
                                                                                       sixteen most significant metastable parameters described
                                                                                       in Section II-D-1. The latent code vectors encoded by
  Coverage: The proportion of the occurrence time of each
                                                                                       the VAE are denoted by Zi = [zi1 , zi2 , . . . , ziNi ]T , where
substate to the total duration of the sample.
                                                                                       ziNi ∈ Rr×1 , and r is the dimension of each latent unit
                                       tS i                                            equal with the sixteen metastability prior.
                         CSi =  k                                       (4)
                                     m=1 tSm                                        b) VAE: The VAE, specializing in probabilistic modeling,
                                                                                       enforces the latent variables toward a Gaussian distribu-
  Transition probability: The probability of transition between
                                                                                       tion for sufficient regularization, enabling the model to
each state.
                                   nS ,S                                               generalize better to previously unseen samples [36]. Thus,
               T P (Si , Sj ) = k i j                       (5)                       the adversarial VAE serves as the foundational framework
                                  m=1 nSi ,Sm                                          for MaDin.
   In this regard, forty metastable parameters are obtained, in-                   VAEs typically consist of probabilistic encoder-decoder pairs.
cluding five coverage parameters, five occurrence parameters,                   The encoder, an inference model Qenc (x), maps a given input x
five duration parameters, and 25 transition probability parame-                 into the hidden latent variables z as follows:
ters. Permutation-based paired t-test is performed on each pa-
                                                                                                               z =μ+σ                                 (6)
rameter to identify significant differences between groups (pre-
ictal/interictal). A 10% adaptive False Discovery Rate (FDR)                    where  ∼ N (0, 1) is an auxiliary noise variable, and 
correction based on [35] is used to account for the five metastable             indicates the Hadamard product, the mean μ and the standard
       Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                 8063


deviation (STD) σ of multivariate Gaussian distribution are                     aggregated posterior distribution q(z) on the latent code vector
generated by the encoder.                                                       is as follows:
   Subsequently, the decoder network Pdec (z) decompresses the
                                                                                                     q (z) = ∫ x q (z | x) pd (x) dx                     (12)
original data—referred to as the reconstructed data x̃—from
the latent representation z with the minimum error. The ob-                     where q(z|x) is the encoding function of the VAE, pd (x) is the
jective loss of VAE is formulated with two parts as (7): the                    marginal distribution of data.
reconstruction loss and the regularization term, given by the                      The objective loss of the adversarial neural network in this
Kullback-Leibler (KL) divergence, to force the hidden latent                    work replaces the log-likelihood terms by the least-squared term
variables approximating the prior Gaussian distribution.                        to relieve the issue of non-convergence [43] as follows:
                                                                                                                                          
       Lvae = E x − x̃2 + DKL (qφ (z | x)  pg (z))        (7)                   LGAN = Ez∼pm log D(z)2 +Ex∼pd log (1 − D (G (x)))2
where qφ (z | x) is the latent distribution generated by encoder,                                                                            (13)
pg (z) is the prior distribution following a Gaussian distribution                  3) Patient-Independent Seizure Prediction: According to
in the latent space, and DKL represents the KL divergence. The                  Sections II-D-1 and II-D-2, the EEG-based metastability
reparameterization trick in [37], [38] is employed for estimating               prior, representing the epileptic characteristics, is first de-
DKL as follows:                                                                 veloped. Then, the generalized learnt latent coding space
                                                                                fused with the metastable properties is obtained through
                       1                         
                          Z
          DKL ≃ −            1 + log σz2 − μ2z − σz2                     (8)    VAE, MMD regularization item and adversarial feature
                       2 z=1                                                    learning. The learned epileptic representations are finally
                                                                                used for seizure prediction, that is the classification
where Z = 16 is the dimension of latent space.
                                                                                for preictal and interictal state. The classification proce-
  a) MMD-based regularization: The maximum mean dis-
                                                                                dure employs the cross-entropy loss function, denoted as
      crepancy (MMD) measure is to learn a feature space
                                                                                follows:
      shared across patients by minimizing the distribution vari-
      ance among them. For two arbitrary hidden vectors zi and                                      1  1 
                                                                                                       M        Ni              
      zj from two unseen distributions Pi and Pj (also meant                            Lcla = −                     yini · log p yini
                                                                                                   M i=1 Ni n = 1
      to from two patients here), respectively, the instance is                                                 i
                                                                                                                          
      mapped to a reproducing kernel Hilbert space (RKHS)                                      + 1 − yini · log 1 − p yini                   (14)
      H by adopting the kernel embedding technique [39]. The
      corresponding mean value in RKHS is given as:                             where yini represents the one-hot encoding vector about label
                          μ (P ) = Ez∼P [h (z, ·)]                       (9)    information for supervised learning, and p (yini ) here denotes
                                                                                the predicted class probability.
  where μ(·) is the mean map operation. h(z, ·) is the kernel                      In sum, MaDin that jointly trains different components is
function included by the feature map in H. In this work, the                    defined as:
RBF kernel is adopted following the MMD-AAE model [40],
[41].                                                                           minQenc ,Pdec ,C maxD Lcla + λ0 LV AE + λ1 Rmmd + λ2 LGAN
                                                                                                                                              (15)
                 mmd (Z i , Z j ) = μPi − μPj H                        (10)     Where λ0 , λ1 , and λ2 represent the trade-off positive parameters,
   In this regard, a mmd-based regularization term is given as                  and C is the classifier.
follows to optimize the hyperparameters in the neural network.                    The training procedure of MaDin consists of two main steps:
                                                                               1) Training the discriminator to distinguish between hidden
                           1
  Rmmd Z 1 , . . . , Z M = 2             mmd (Z i , Z j ) (11)                  codes sampled from the metastability prior and those generated
                            M                                                   by the encoder, achieved by maximizing the objective (15);
                                       1≤i,j≤M
                                                                                and 2) training the VAE to update the encoder and decoder
    a) Adversarial feature learning: VAE combined with MMD                      by minimizing input reconstruction error, inter-subject distance,
       regularization effectively extracts subject-invariant fea-               and classification error, achieved by optimizing the encoder
       ture vectors with complex, high-order nonlinear at-                      Qenc , decoder Pdec and classifier C with the same objective.
       tributes. To further infuse the underlying epileptic physi-              The overall algorithm of MaDin is described in Algorithm 2.
       ological information into the latent space, an adversarial
       training procedure is utilized to match the aggregated                                                III. EXPERIMENT
       posterior distribution q(z) of the hidden latent codes with
       the metastability prior Pm .                                             A. Evaluation Metrics
   To be specific, both the latent representation Zi and the                       The seizure occurrence period (SOP) and the seizure predic-
metastable properties Pm  i are input into the discriminator D(·).              tion horizon (SPH) need to be defined [44] before evaluating
After adversarial inference, the encoder (a generative model)                   prediction performance. SOP is the period in which a seizure
is refreshed by imposing the metastable properties on the                       is predicted, while SPH is the duration between a seizure alarm
data space. The aggregated posterior distribution can fool the                  and the start of SOP. False alarm arises If an alert is received
discriminator into thinking that the latent representation q(z)                 during SPH but no seizure. In this work, SOP and SPH are set to
originates from the metastability prior. According to [42], the                 30 min and 5 min respectively [45], [46]. We evaluate prediction
        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8064                                                        IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


 Algorithm 2: Description of the Proposed Patient-                              conjured by parameter tuning are set λ0 = 0.03, λ1 = 0.03,
 Independent Seizure Prediction (MaDin).                                        and λ2 = 0.01. The batch size is set to 32, and the maximum
  Input: Raw multichannel EEG segments                                          of epochs is set to 50. The experiments are carried out with the
   X = {X1 , X2 , . . . , XM }, one-hot encoding vectors of                     Python library and Tensorflow framework on a server equipped
   corresponding labels Y = {Y1 , Y2 , . . . , YM }, initialized                with NVIDIA Tesla V100 with 32 GB memory.
   parameters Qenc , Pdec , C, and D.
  Output: Learned parameters Q∗enc , Pdec ∗
                                            , C ∗ and D ∗ , and                                                IV. RESULTS
   the prediction result of the model.                                             Our results are based on the analysis of two publicly available
   1: Construct the metastability prior Pm for X                                scalp EEG datasets and one clinical dataset described in the
   2: while Stopping criterion is not met do                                    Methodology section. We first present the representative results
   3: Sample a minibatch Xb and Yb from X and Y,                                of metastability analysis, then the evaluation of model prediction
       respectively.                                                            performance with alation studies of different components, and
   4: Sample the corresponding metastable properties Pm      b                  finally the comparison with other strategies for subject-invariant
       from Pm .                                                                representation.
   5: Compute the gradient of (15) w.r.t. D on Xb
   6: Take a gradient step to update D to maximize (15).                        A. Metastability Analysis
   7: Compute the gradient of (15) w.r.t. Qenc , Pdec , C on
       Xb , respectively.                                                           1) Metastability prior evaluation: To characterize the com-
   8: Take a gradient step to update Qenc , Pdec , C to                         mon metastable patterns, subjects with different seizure types or
       minimize (15), alternatingly.                                            localizations are analyzed based on the discrete state sequence
   9: end while                                                                 obtained from LEiDA analysis (described in Section II-C-2).
                                                                                As shown in Fig. 2, there are significant differences for lots of
                                                                                metastable parameters between pre- and inter-ictal states in all
performances in terms of sensitivity (SEN), specificity (SPE)                   three datasets. Specifically, the duration matrices (corresponding
and area under the curve (AUC).                                                 to the first row in Fig. 2) for pre-ictal states are significantly
   As the physiological mechanisms underlying epilepsy remain                   lower than that of the inter-ictal. The occurrence matrices (cor-
under active investigation, completely excluding the target pa-                 responding to the second row in Fig. 2) for pre-ictal states, on
tient from training is not feasible. To simulate clinical scenarios,            the contrary, are significantly higher than that of inter-ictal. The
this study incorporates one seizure from the target subject into                three datasets share the same tendency. It is reasonable to infer
the training set alongside data from existing subjects, while                   that the brain network level during the pre-ictal states tends
the remaining seizures from the target subject are reserved for                 to be irregular and abnormally active. The coverage matrices
testing. Of the available data, 80% is allocated to the training                (corresponding to the third row in Fig. 2) depend on the total
set, and the remaining 20% is used for validation to monitor                    duration of the EEG recording, which varies for each seizure
overfitting.                                                                    file. The transition probability matrices (corresponding to the
                                                                                fourth row in Fig. 2) indicate the tendency in the transition of
                                                                                brain states to a specific state. Despite statistical significance
B. Experiment Setup                                                             for most of the four metastable matrices across datasets, both
   The specific network structures of VAE sub-network in                        the coverage and transition probability matrices in two states
Fig. 1(c), adversarial sub-network in Fig. 1(d) and the classi-                 show no consistency probably because of the diversity of seizure
fication sub-network in Fig. 1(e) are summarized in Table I. The                types and the differences in the number of each type in the
architecture design of the VAE draws inspiration from the highly                dataset.
effective DeepConvNet [47]. The encoder configuration incor-                       2) Metastability findings for patients with specific seizure
porates temporal convolutions followed by spatial filters, result-              types: To better analyze the coverage and transition probabilities
ing in effective dimensionality reduction. On the other hand, the               matrices between these two stages, we conduct group-level
decoder comprises the corresponding deconvolution layers to                     analysis for patients with specific seizure types in the dataset.
reconstruct the original data. The batch normalization and leaky                The transition probability matrices for pre- and inter-ictal states
ReLU are applied over the convolution and deconvolution layers.                 are shown in Fig. 3(a) and (b). The transitions with statistical
Both the discriminator and the classifier consist of two dense                  significance are further characterized in Fig. 3(c) and (d). The
layers that connect the hidden layer to the output categories.                  coverage matrices for pre- and inter-ictal states are shown in
To obtain a stable and deterministic input representation, during               Fig. 3(e) and (f).
the test (prediction) phase, the latent representation (z) fed into                Transition probability reflects the patterns of constant cou-
classifier is the deterministic mean vector (μ) produced by the                 pling and decoupling of the brain network, that is, transitions
trained encoder given the input test EEG segment x test [48],                   between different metastable substates (coupling modes). A
that is, z test = μ(x test ).                                                   higher transfer probability indicates that the current brain state is
   This work applies the Adam optimizer to update the param-                    more inclined to transition to this coupling pattern. Specifically,
eters of the four modules in (16), where the learning rate is set               there is a significant decrease in the transition probability from
to 5e-5, and the weight decay is set to 1e-4. The trade-off items               other metastable substates to S1, while a significant increase to

       Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                 8065


                                                                     TABLE I
                                                   SPECIFIC NETWORK PARAMETERS OF MADIN MODEL


                                                                    TABLE II
                                                  ABLATION EXPERIMENT OF DIFFERENT COMPONENTS


S3 in patients with temporal lobe seizures. Coverage matrices                   B. Prediction Performance Evaluation
reflect the current dominant metastable substate to some extent,                   To explore the effect of different components in MaDin on
calculating the proportion of the occurrence time of each sub-                  the prediction results, comprehensive ablation experiments on
state to the total duration. S1 and S3 are the lowest and the                   three datasets are performed. For brevity, Table II summarizes
highest in coverage shown in Fig. 3(e), respectively. Moreover,                 the average results for all patients. To rigorously evaluate the
the brain network topology of S1 exhibits stronger functional                   contribution of each component, Wilcoxon signed-rank test is
connectivity/synchronization levels in the temporal lobe brain                  conducted based on AUC metrics as shown in Fig. 4(a).
regions, whereas S3 with stronger functional connectivity in                       Firstly, the effectiveness of metastability prior is initially ex-
frontal lobe brain regions (shown in Fig. 3(c)). It may suggest                 amined using metastable features combined with an SVM classi-
that there is some degree of disconnection between the functional               fier as a traditional machine learning method without alignment
brain network of epileptogenic brain regions and other regions                  across subjects. Despite the large inter-individual variability,
during seizure evolution. A similar situation has been found in                 patient-independent prediction using only metastable features
patients with frontal lobe seizures. During the pre-ictal state, the            can exceed 60% on sensitivity metric, showing the advantage in
transition probability both from S1 to S4, and S5 to S4 were                    identifying the epileptic characteristic. This implies the feasibil-
significantly decreased (shown in Fig. 3(b)). The coverage of                   ity of further introducing deep learning techniques for a more
S4 is the lowest shown in Fig. 3(f). The brain network topology                 effective patient-independent seizure prediction model. Besides,
of S4 exhibits strong functional connectivity in the frontal lobe,              our full MaDin model achieves statistically significantly higher
indicating a disconnection between the functional brain network                 AUC compared to this baseline across all three datasets (p <
of frontal brain regions and other regions (Fig. 3(d)).                         0.0001 for all three datasets).


        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8066                                                         IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


Fig. 2. Distribution of specific characteristics for the metastable substates (S1-S5) for pre- and inter-ictal classes. The first three rows are the
metastable matrices of duration, occurrence, and coverage, respectively. The last row is the metastable matric of transition probability. (a)–(c) are
the CHB-MIT, Siena, and clinical datasets, respectively. Benjamini and Krieger FDR, q < 0.1, is applied. ∗P <0.05; ∗∗P <0.01.


   Secondly, each component of the objective function of MaDin                   significant on the Siena (p = 0.0344) and Clinical (p = 0.0342)
described in (16) is examined. From the experimental results,                    datasets. It implies that VAE not only has the advantage of pre-
removing each component leads to performance degradation                         serving informative and nonlinear attributes epileptic attributes
for all three datasets. Removing the adversarial training part                   in a highly compressed dimension but also generalizing better
(No LGAN ) causes the most severe performance degradation                        to target patient for its extra generative ability compared to AE.
in both the sensitivity and specificity metrics. The performance                    Removing MMD regularization term (No Rmmd ) causes
difference in AUC compared to the full MaDin model is sta-                       slight performance degradation in both the sensitivity and speci-
tistically significant on the Siena (p = 0.0219) and Clinical                    ficity metrics in both CHB-MIT and clinical datasets. Statisti-
(p = 0.0416) datasets though with no significance on the                         cally, the AUC difference between MaDin and the model without
CHB-MIT dataset (p = 0.3119). This underscores the criti-                        MMD is significant only on the Siena dataset (p = 0.0012),
cal role of integrating the metastability prior via adversarial                  while not significant on CHB-MIT (p = 0.6238) or Clinical (p =
 learning.                                                                       0.7168) datasets. This suggests that combining adversarial VAE
   Replacing VAE with a pure autoencoder (AE) (No LV AE ) for                    and metastability prior for latent representation encoding, using
the latent representation encoding also results in performance                   only a small amount of target patient, has already equipped the
degradation, especially in the sensitivity metric. Similarly, the                prediction model with both generalization and discrimination
degradation in AUC when replacing VAE with AE is statistically                   ability.


        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                  8067


Fig. 3. Transition patterns and coverage matrices for patients with specific seizure types. (a) and (b) represent the transition probability matrices
for pre- and inter-ictal states in patients with temporal and frontal lobe seizure types, respectively. The matrices indicate the probability of the
transition from a particular substate (row) to any other substate (column). (c) and (d) represent significant transitions (∗P <0.05) in patients with
temporal and frontal lobe seizure types, respectively. Solid arrows indicate an increased tendency in the transition of brain states to a specific state
Si in the pre-ictal phase, whereas dashed arrows indicate a decreased tendency. (e) and (f) represent coverage matrices for patients with temporal
and frontal lobe seizure types, respectively.


C. Comparison With Other Strategies for                                             DAN uses a multi-kernel MMD (MK-MMD) to replace the
Subject-invariant Representation                                                 original single-kernel MMD for image classification, which
                                                                                 aims to solve the problem of the restricted kernel function of
   Patient-independent seizure prediction studies have referred
                                                                                 MMD [51].
domain adaptation or generalization techniques to address the
                                                                                    SIDA learns invariant representations via adversarial learn-
inter-subject variability, enabling prediction models to adapt
                                                                                 ing for motor imagery tasks [52]. Adversarial representation
from existing subjects (source domain) to a newly admit-
                                                                                 learning in this work is viewed as simultaneously learning to
ted patient (target domain) [23], [40], [49], [50]. This study
                                                                                 predict a dependent variable from a representation while ex-
further compares three main strategies for subject-invariant
                                                                                 ploiting an adaptive dependence measure between these two to
representation. All the experiments are conducted in a unified
                                                                                 also learn the representation itself such that this dependence is
setting. A detailed description of these methods is presented
                                                                                 minimized.
below.


         Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8068                                                         IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


                                                                                    Compared with the three methods, MaDin achieves the best
                                                                                 performance in both sensitivity and specificity metrics on almost
                                                                                 all three datasets. Statistical analysis of the AUC metric further
                                                                                 confirms the superiority of MaDin, showing significantly bet-
                                                                                 ter performance than DAN across all datasets (p < 0.05) and
                                                                                 significant advantages over SIDA and MMD-AAE specifically
                                                                                 on the Siena dataset (p < 0.05). Though AUC improvement of
                                                                                 MaDin over SIDA and MMD-AAE has not reached significance
                                                                                 on CHB-MIT and Clinical datasets, MaDin exhibits greater
                                                                                 performance stability across individual subjects. We have not
                                                                                 observed the severe prediction failures seen with comparison
                                                                                 methods in certain cases, such as the sensitivity/specificity of
                                                                                 SIDA for subject chb02 (40% /90%) or MMD-AAE for sub-
                                                                                 ject chb18 (44% /97%) on the CHB-MIT dataset, suggesting
                                                                                 a potential lack of capability in recognizing pre-ictal features
                                                                                 for these specific instances by the comparison models. Similar
                                                                                 instances of inconsistent performance for SIDA and MMD-AAE
                                                                                 are observed on the clinical dataset as well. The consistent per-
                                                                                 formance of MaDin across subjects suggests higher reliability,
Fig. 4. Wilcoxon signed-rank test between pairing methods based                  an important factor for clinical translation.
on AUC metric in the three datasets at the significance level of 0.05.
(a) Statistics results for ablation experiments. (b) Statistics results for
different subject-invariant representation methods. Statistical difference                                     V. DISCUSSION
is significant if p < 0.05 shaded with gray.
                                                                                    In this study, we develop an EEG-based epileptic representa-
                                                                                 tion by fusing the underlying neurological process of epileptic
                           TABLE III                                             brain network with the latent coding space, enabling reliable
 PREDICTION PERFORMANCE COMPARISON WITH EXISTING METHODS FOR                     patient-independent seizure prediction. Our results have demon-
               SUBJECT-INVARIANT REPRESENTATION
                                                                                 strated that our prediction model, MaDin, achieved the best
                                                                                 prediction performance among other state-of-the-art patient-
                                                                                 independent seizure prediction algorithms with the same subject
                                                                                 division for validation. The brain-network-inspired correspon-
                                                                                 dence and reliable prediction performance show the advantages
                                                                                 of our invariant representation integrated with network temporal
                                                                                 dynamics.

                                                                                 A. Investigation of EEG-based Metastability Findings
                                                                                    The spiking during the inter-ictal state indicates a more deter-
                                                                                 ministic activity, while the ictal state or the pre-ictal state tends
                                                                                 to be a more complex and chaotic activity, and spectral chirps
   MMD-AAE first extends adversarial autoencoders for object                     in EEG [54]. Moreover, when seizure approaches, fluctuation in
recognition by imposing the MMD measure to align the dis-                        neural signals near the seizure onset area, far from equilibrium,
tributions among different domains and matching the aligned                      exhibits synchronized instabilities in avalanche dynamics [55].
distribution to an artificial Laplace prior distribution through                 Comparably, as described in Section IV-A-1, we first observed
adversarial feature learning [41].                                               that compared to the inter-ictal states, the occurrence of five
   For brevity, Table III summarizes the average results for                     metastable substates increased in the pre-ictal states, while their
all patients. The patient-by-patient results are summarized in                   corresponding durations decreased, reflecting a highly disor-
Tables VIII–X. The Wilcoxon signed-rank test is conducted                        dered state of irregular transitions between different metastable
based on AUC metrics as shown in Fig. 4(b). DAN gives                            substates in the pre-ictal state (up to 30 minutes before epileptic
the worst results compared to other methods, only focusing                       seizures).
on the alignment of domain marginal distribution via MK-                            Based on the mentioned above, we may naturally expect to
MMD. The alignment potentially destroys the discriminative                       further analyze whether the differences in metastable patterns
hyperplane of the features due to the excessive gap between                      between the pre- and inter-ictal can be observed in the different
different patient domains, resulting in poor prediction perfor-                  seizure types. To this end, we further conduct a detailed analysis
mance. Both SIDA and MMD-AAE significantly outperform                            for the patients with specific seizure types as shown in Fig. 3.
DAN and achieve comparable performance. SIDA verifies the                           Seizures destabilize the brain networks. A critical transition
effectiveness of adversarial training on generalizability. Though                arises from normal brain activities to the ictal states [56]. “Criti-
MMD-AAE constructs an artificial Laplace prior, the perfor-                      cal slowing down” is considered as a typical phenomenon when
mance is not significantly improved as expected.                                 approaching the critical transition [57]. Additionally, epileptic
        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                  8069


                            TABLE IV                                             only on the CHB-MIT dataset. As shown in Table IV, MMD-
        PREDICTION PERFORMANCE COMPARISON WITH EXISTING
        PATIENT-INDEPENDENT METHODS ON CHB-MIT DATASET
                                                                                 AAE-SP and MAAE first explored this challenging issue [23],
                                                                                 [40]. MMD-AAE-SP, derived from MMD-AAE [41], prepro-
                                                                                 cessed the raw EEG signals with a short-time Fourier transform,
                                                                                 essentially converting epileptic EEG signal classification into an
                                                                                 image classification problem. Both MMD-AAE-SP and MAAE
                                                                                 followed the learning strategy of autoencoder to map the input
                                                                                 data into high-dimensional embeddings. To generalize well on
                                                                                 the target patient, the artificial prior, such as Laplace prior or
                                                                                 Riemannian manifold-based prior, is imposed to the aligned
                                                                                 latent space through adversarial feature learning. Riemannian
                                                                                 manifold-based prior outperforms by capturing spatially corre-
                                                                                 lated features from EEG compared to artificial Laplace priors
                                                                                 without task-specific information. Both Riemannian manifold-
                                                                                 based prior and our proposed metastability prior serve as feature
                                                                                 extraction for raw EEG signals [60]. When combined with an
                                                                                 AE for latent space encoding, MAAE incorporates information
                                                                                 from only a single seizure event of the target subject into the
                                                                                 encoding process. However, it is less able to effectively mitigate
                                                                                 overfitting on the existing subject data without additional gen-
                                                                                 eralization techniques. This is the key factor why we employ
                                                                                 a VAE instead of AE to generate the latent space. Nor have
network shows transiently disrupted balance with long-range                      MAAE defined SPH for adequate clinical interventions. To
connectivity with other networks [58], which is an important                     further improve cross-subject generalizability, feature alignment
process for the generation of epileptic activity. In this study,                 strategies that minimize the embedding distribution disparity
while analyzing the patients with temporal lobe seizures as                      between every two patients, and semi-supervised techniques
shown in Fig. 3(c), if the topological structure distribution of                 that utilize the unlabeled data of target patients for finetune,
specific metastable substates primarily involves the temporal                    have also been explored [49], [50]. These studies have had little
lobe structures, the transition “slowing” of these subnetworks                   or no effect on performance improvement, which suggests that
into other substates will occur when impending seizure onset,                    directly adopting classical domain-related strategies in image
alternatively seen as “being functional isolated”. The corre-                    classification and speech recognition cannot further adapt to
sponding phenomenon still exists in frontal lobe epilepsy shown                  EEG representation learning.
in Fig. 3(d).                                                                       The basic idea of the above studies is to identify robust com-
   Taken together, (i) metastable substates overlapping with the                 mon representation across subjects. Our proposed framework,
seizure onset regions exhibit decreased transition probabilities in              MaDin, first characterizes the temporal dynamics of epileptic
the pre-ictal states; (ii) in contrast, for those sub-states whose pri-          brain networks through metastability analysis. The character-
mary spatial domain does not involve the seizure onset regions,                  istics of the metastability prior, which show consistency with
its coverage matric plays a predominant role in the pre-ictal peri-              the physiological mechanism of epilepsy, provide a physiolog-
ods shown in Fig. 3(e) and (f). According to the variations among                ically grounded foundation for representation learning, moving
metastable substates existing in the pre- and inter-ictal states, we             beyond purely statistical pattern matching or the use of task-
infer that decreased transitions towards the substates associated                agnostic priors. By utilizing the generative capability of VAE
with focal seizure areas, and the increased reorganization with                  and adversarial training, the domain knowledge is integrated
substates that are distant from seizure sources, may reflect a                   into the latent space, further regularized by MMD regularization.
progressive loss of the ability to maintain regional stability, and              This knowledge-guided idea ensures that the learned subject-
also an increase in the spread of coupling to other regions before               invariant representation preserves not only feature discriminabil-
catastrophic events [59].                                                        ity for prediction but also generalization across both existing
                                                                                 subjects and the target subject (the newly admitted patient).
                                                                                 Compared with existing methods, MaDin obtains a benefit on
B. The Advantages of MaDin for Patient-independent                               the CHB-MIT dataset of AUC, sensitivity, and specificity by
Seizure Prediction                                                               about 9%, 5%, and 5%, respectively.
   Table IV summarizes all the studies for patient-independent                      Finally, beyond the advantages in predictive accuracy and
seizure prediction. All studies were validated in the same way as                robust representation learning, MaDin demonstrates significant
ours. The training set includes the data of existing subjects and                practical advantages in terms of computational efficiency. As
one seizure from the target subject, while the remaining seizures                shown in Fig. 5, our analysis revealed very low inference times
of the target subject are only for testing. There are still rela-                (sub-second for processing batches of 120 samples, translat-
tively few studies under such validation for patient-independent                 ing to millisecond-level per-segment speed) which are statisti-
seizure prediction due to the well-acknowledged inter-patient                    cally consistent across all tested datasets (Kruskal-Wallis, p >
variability. Most of these studies have validated their methods                  0.05). This high efficiency strongly supports the feasibility of
         Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8070                                                         IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


                                                                                 dynamics, enabling reliable patient-independent seizure predic-
                                                                                 tion. The generalization ability and prediction performance of
                                                                                 our proposed MaDin have been evaluated on the two publicly
                                                                                 available scalp EEG datasets and one clinical dataset. Owing
                                                                                 to the promising experimental results of MaDin, the integration
                                                                                 of metastable properties with deep learning techniques deserves
                                                                                 further in-depth investigation to achieve better interpretability
                                                                                 and more accurate patient-independent seizure prediction.

                                                                                                                  APPENDIX
                                                                                                                TABLE V
                                                                                                DETAILED DESCRIPTION OF CHA-MIT DATASET


Fig. 5. Inference time for the three datasets. Each scatter represents a
subject. No significant difference among the three datasets with Kruskal-
Wallis H test (p >0.05).


deploying MaDin for real-time clinical applications [61], com-
plementing its state-of-the-art predictive performance.

C. Limitations and Future Work
   While our MaDin model demonstrates promising patient-
independent seizure prediction by integrating a metastability
prior, we acknowledge limitations and outline future directions.
The current validation is based on specific pediatric and adult
scalp EEG datasets; broader validation across larger populations,                                              TABLE VI
                                                                                                  DETAILED DESCRIPTION OF SIENA DATASET
diverse seizure types, and multi-center data are necessary. Our
focus on segment-based evaluation metrics, while fundamen-
tal, requires developing post-processing techniques, especially
parameter-free, to assess event-based clinical metrics like false
positive rate per hour (FPR/h) within the defined SPH framework
in the future. Besides, detailed failure case analysis, which
is crucial for understanding model weaknesses, has not been
included.
   Future research will prioritize these aspects: performing
broader validation, developing event-based evaluation proto-
cols with post-processing techniques, and conducting in-depth
failure analyses. Additionally, we aim to explore more adap-
tive methods for capturing pre-ictal dynamics and investigate
deeper integration of physiological knowledge to further en-
hance model robustness, generalizability, and interpretability.
Addressing residual inter-subject heterogeneity and optimizing                                                  TABLE VII
                                                                                                 DETAILED DESCRIPTION OF CLINICAL DATASET
clinical parameters like SPH/SOP also remain important con-
siderations for translating this work towards reliable clinical
application.

                           VI. CONCLUSION
   Exploring effective integration between the underlying neural
processes specific to epilepsy, and the deep learning models
commonly criticized for black-box problems, is one of the most
challenging tasks in computer-aided epilepsy studies. To this
end, we propose a metastability-based deep learning framework
to construct epileptic representations with network temporal
        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

LIAO et al.: EEG-BASED SEIZURE PREDICTION MODEL ENCODING BRAIN NETWORK TEMPORAL DYNAMICS                                                                     8071


                           TABLE VIII                                            [2] N. T. Cohen et al., “Networks underlie temporal onset of dysplasia-related
 PREDICTION PERFORMANCE COMPARISON WITH EXISTING METHODS FOR                         epilepsy: A MELD study,” Ann. Neurol, vol. 92, no. 3, pp. 503–511,
     SUBJECT-INVARIANT REPRESENTATION ON CHB-MIT DATABASE                            Jun. 2022.
                                                                                 [3] A. Shoeibi et al., “An overview of deep learning techniques for epilep-
                                                                                     tic seizures detection and prediction based on neuroimaging modalities:
                                                                                     Methods, challenges, and future works,” Comput. Biol. Med., vol. 149,
                                                                                     Oct. 2022, Art. no. 106053.
                                                                                 [4] N. T. Cohen, H. Xie, T. Gholipour, and W. D. Gaillard, “A scoping review
                                                                                     of the functional magnetic resonance imaging-based functional connectiv-
                                                                                     ity of focal cortical dysplasia-related epilepsy,” Epilepsia, vol. 64, no. 12,
                                                                                     pp. 3130–3142, Sep. 2023.
                                                                                 [5] W. Liu, M. Lin, Q. Yue, Q. Gong, D. Zhou, and X. Wu, “Brain functional
                                                                                     connectivity patterns in focal cortical dysplasia related epilepsy,” Seizure,
                                                                                     vol. 87, pp. 1–6, Feb. 2021.
                                                                                 [6] S. Tavakol et al., “Neuroimaging and connectomics of drug-resistant
                                                                                     epilepsy at multiple scales: From focal lesions to macroscale networks,”
                                                                                     Epilepsia, vol. 60, no. 4, pp. 593–604, Mar. 2019.
                                                                                 [7] R. Zheng et al., “Scalp EEG functional connection and brain network
                                                                                     in infants with west syndrome,” Neural Networks, vol. 153, pp. 76–86,
                                                                                     May 2022.
                                                                                 [8] G. W. Johnson et al., “The interictal suppression hypothesis in focal
                                                                                     epilepsy: Network-level supporting evidence,” Brain, vol. 146, no. 7,
                                                                                     pp. 2828–2845, Jul. 2023.
                                                                                 [9] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C. Fookes,
                                                                                     “Geometric deep learning for subject independent epileptic seizure pre-
                                                                                     diction using scalp EEG signals,” IEEE J. Biomed. Health Inform., vol. 26,
                            TABLE IX                                                 no. 2, pp. 527–538, Jul. 2021.
 PREDICTION PERFORMANCE COMPARISON WITH EXISTING METHODS FOR                    [10] L. Guo, T. Yu, S. Zhao, X. Li, X. Liao, and Y. Li, “Clep: Contrastive
       SUBJECT-INVARIANT REPRESENTATION ON SIENA DATABASE                            learning for epileptic seizure prediction using a spatio-temporal-spectral
                                                                                     network,” IEEE Trans. Neural Syst. Rehabil. Eng., vol. 31, pp. 3915–3926,
                                                                                     2023.
                                                                                [11] Y. Li, Y. Liu, Y.-Z. Guo, X.-F. Liao, B. Hu, and T. Yu, “Spatio-temporal-
                                                                                     spectral hierarchical graph convolutional network with semisupervised ac-
                                                                                     tive learning for patient-specific seizure prediction,” IEEE Trans. Cybern.,
                                                                                     vol. 52, no. 11, pp. 12189–12204, May 2021.
                                                                                [12] E. Tognoli and J. S. Kelso, “The metastable brain,” Neuron, vol. 81, no. 1,
                                                                                     pp. 35–48, Jan. 2014.
                                                                                [13] S. Das and S. D. Puthankattil, “EEG-based metastability in mild cog-
                                                                                     nitive impairment Alzheimer’s disease,” Brain Connect., vol. 14, no. 3,
                                                                                     pp. 198–207, Apr. 2024.
                                                                                [14] W. J. Freeman and M. D. Holmes, “Metastability, instability, and state
                                                                                     transition in neocortex,” Neural Netw., vol. 18, no. 5-6, pp. 497–504, Jul.–
                                                                                     Aug. 2005.
                                                                                [15] E. Tognoli and J. S. Kelso, “Brain coordination dynamics: True and false
                                                                                     faces of phase synchrony and metastability,” Prog. Neurobiol., vol. 87,
                                                                                     no. 1, pp. 31–40, Jan. 2009.
                           TABLE X                                              [16] A. Tozzi, J. F. Peters, A. A. Fingelkurts, A. A. Fingelkurts, and P. C.
 PREDICTION PERFORMANCE COMPARISON WITH EXISTING METHODS FOR                         Marijuán, “Topodynamics of metastable brains,” Phys. Life Rev., vol. 21,
     SUBJECT-INVARIANT REPRESENTATION ON CLINICAL DATABASE                           pp. 1–20, Jul. 2017.
                                                                                [17] D. Li, P. E. Vlisides, and G. A. Mashour, “Dynamic reconfiguration
                                                                                     of frequency-specific cortical coactivation patterns during psychedelic
                                                                                     and anesthetized states induced by ketamine,” Neuroimage, vol. 249,
                                                                                     Apr. 2022, Art. no. 118891.
                                                                                [18] M. Metzger et al., “Functional network dynamics revealed by EEG mi-
                                                                                     crostates reflect cognitive decline in amyotrophic lateral sclerosis,” Hum.
                                                                                     Brain Mapping, vol. 45, no. 1, Dec. 2023, Art. no. e26536.
                                                                                [19] K. Nishida et al., “EEG microstates associated with salience and
                                                                                     frontoparietal networks in frontotemporal dementia, schizophrenia and
                                                                                     Alzheimer’s disease,” Clin. Neurophysiol., vol. 124, no. 6, pp. 1106–1114,
                                                                                     Feb. 2013.
                                                                                [20] Z. Cui, T. Gao, K. Talamadupula, and Q. Ji, “Knowledge-augmented deep
                                                                                     learning and its applications: A survey,” IEEE Trans. Neural Netw. Learn.
                                                                                     Syst., vol. 36, no. 2, pp. 2133–2153, Feb. 2025.
                                                                                [21] N. Shlezinger, J. Whang, Y. C. Eldar, and A. G. Dimakis, “Model-based
                                                                                     deep learning,” Proc. IEEE, vol. 111, no. 5, pp. 465–499, 2023.
                                                                                [22] P. Peng, Y. Song, L. Yang, and H. Wei, “Seizure prediction in EEG signals
                                                                                     using STFT and domain adaptation,” Front. Neurosci., vol. 15, 2022,
                                                                                     Art. no. 825434.
                                                                                [23] P. Peng, L. Xie, K. Zhang, J. Zhang, L. Yang, and H. Wei, “Domain
                                                                                     adaptation for epileptic EEG classification using adversarial learning
                               REFERENCES                                            and riemannian manifold,” Biomed. Signal Process. Control, vol. 75,
                                                                                     May 2022, Art. no. 103555.
[1] J. P. Andrews, S. Ammanuel, J. Kleen, A. N. Khambhati, R. Knowlton,         [24] A. H. Shoeb, Application of Machine Learning to Epileptic
    and E. F. Chang, “Early seizure spread and epilepsy surgery: A systematic        Seizure Onset Detection and Treatment, Massachusetts Inst. Technol.,
    review,” Epilepsia, vol. 61, no. 10, pp. 2163–2172, Sep. 2020.                   2009.


        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.

8072                                                             IEEE JOURNAL OF BIOMEDICAL AND HEALTH INFORMATICS, VOL. 29, NO. 11, NOVEMBER 2025


[25] P. Detti, “Siena scalp EEG database,” PhysioNet., vol. 10, Aug. 2020,            [45] &Kgr;. &Mgr;. Tsiouris, V. C. Pezoulas, M. Zervakis, S. Konitsiotis, D.
     Art. no. 493.                                                                         D. Koutsouris, and D. I. Fotiadis, “A long short-term memory deep learn-
[26] E. B. Assi, D. K. Nguyen, S. Rihana, and M. Sawan, “Towards accurate                  ing network for the prediction of epileptic seizures using EEG signals,”
     prediction of epileptic seizures: A review,” Biomed. Signal Process. Con-             Comput. Biol. Med., vol. 99, pp. 24–37, Aug. 2018.
     trol., vol. 34, pp. 144–157, Apr. 2017.                                          [46] G. Wang et al., “Seizure prediction using directed transfer function and
[27] K. Rasheed et al., “Machine learning for predicting epileptic seizures using          convolution neural network on intracranial EEG,” IEEE Trans. Neural
     EEG signals: A review,” IEEE Rev. Biomed. Eng., vol. 14, pp. 139–155,                 Syst. Rehabil. Eng., vol. 28, no. 12, pp. 2711–2720, Nov. 2020.
     Jul. 2020.                                                                       [47] R. T. Schirrmeister et al., “Deep learning with convolutional neural net-
[28] U. R. Acharya, S. V. Sree, G. Swapna, R. J. Martis, and J. S. Suri,                   works for EEG decoding and visualization,” Hum. Brain Mapping, vol. 38,
     “Automated EEG analysis of epilepsy: A review,” Knowl.-Based Syst.,                   no. 11, pp. 5391–5420, Aug. 2017.
     vol. 45, pp. 147–165, 2013.                                                      [48] L. Bonheme and M. Grzes, “Be more active! understanding the differences
[29] A. Al Fahoum and A. a. Zyout, “Wavelet transform, reconstructed phase                 between mean and sampled representations of variational autoencoders,”
     space, and deep learning neural networks for EEG-based schizophrenia                  J. Mach. Learn. Res., vol. 24, no. 324, pp. 1–30, 2023.
     detection,” Int. J. Neural Syst., vol. 34, no. 9, 2024, Art. no. 2450046.        [49] D. Liang, A. Liu, Y. Gao, C. Li, R. Qian, and X. Chen, “Semi-supervised
[30] A. Al Fahoum and A. a. Zyout, “Early detection of neurological abnor-                 domain-adaptive seizure prediction via feature alignment and consis-
     malities using a combined phase space reconstruction and deep learning                tency regularization,” IEEE Instrum. Meas. Mag., vol. 72, Mar. 2023,
     approach,” Intell.-Based Med., vol. 8, 2023, Art. no. 100123.                         Art. no. 4003512.
[31] J. Cabral et al., “Cognitive performance in healthy older adults relates to      [50] Z. Zhang, A. Liu, Y. Gao, X. Cui, R. Qian, and X. Chen, “Distilling in-
     spontaneous switching between states of functional connectivity during                variant representations with domain adversarial learning for cross-subject
     rest,” Sci. Reports, vol. 7, no. 1, Jul. 2017, Art. no. 5135.                         children seizure prediction,” IEEE Trans. Cogn. Develop. Syst., vol. 16,
[32] L.-D. Lord et al., “Dynamical exploration of the repertoire of brain                  no. 1, pp. 202–211, Feb. 2024.
     networks at rest is modulated by psilocybin,” NeuroImage, vol. 199,              [51] M. Long, Y. Cao, J. Wang, and M. Jordan, “Learning transferable fea-
     pp. 127–142, May 2019.                                                                tures with deep adaptation networks,” in Proc. Int. Conf. Mach. Learn.,
[33] D. Gabor, “Communication theory and physics,” IRE Trans. Inf. Theory,                 Feb. 2015, pp. 97–105.
     vol. 1, no. 1, pp. 48–59, Apr. 2003.                                             [52] O. Özdenizci, Y. Wang, T. Koike-Akino, and D. Erdoğmuş, “Learning in-
[34] R. D. Pascual-Marqui, C. M. Michel, and D. Lehmann, “Segmentation of                  variant representations from EEG via adversarial inference,” IEEE Access,
     brain electrical activity into microstates: Model estimation and validation,”         vol. 8, pp. 27074–27085, 2020.
     IEEE Trans. Biomed. Eng., vol. 42, no. 7, pp. 658–665, Jul. 1995.                [53] H. Li, S. J. Pan, S. Wang, and A. C. Kot, “Domain generalization with
[35] Y. Benjamini, A. M. Krieger, and D. Yekutieli, “Adaptive linear step-up               adversarial feature learning,” in Proc. IEEE Conf. Comput. Vis. Pattern
     procedures that control the false discovery rate,” Biometrika, vol. 93, no. 3,        Recognit., 2018, pp. 5400–5409.
     pp. 491–507, Sep. 2006.                                                          [54] N. S. Araújo et al., “Chaotic and stochastic dynamics of epileptiform-like
[36] H. W. Ng and C. Guan, “Deep unsupervised representation learning                      activities in sclerotic hippocampus resected from patients with pharma-
     for feature-informed EEG domain extraction,” IEEE Trans. Neural Syst.                 coresistant epilepsy,” PLoS Comput. Biol., vol. 18, no. 4, Apr. 2022,
     Rehabil. Eng., vol. 31, pp. 4882–4894, 2023.                                          Art. no. e1010027.
[37] B. Abdi-Sargezeh, S. Shirani, A. Valentin, G. Alarcon, and S. Sanei,             [55] V. Zimmern, “Why brain criticality is clinically relevant: A scoping
     “EEG-to-EEG: Scalp-to-intracranial EEG translation using a combination                review,” Front. Neural Circuits, vol. 14, Aug. 2020, Art. no. 565335.
     of variational autoencoder and generative adversarial networks,” Sensors,        [56] E. Negahbani, D. A. Steyn-Ross, M. L. Steyn-Ross, M. T. Wilson, and J.
     vol. 25, no. 2, p. 494, 2025.                                                         W. Sleigh, “Noise-induced precursors of state transitions in the stochastic
[38] D. P. Kingma and M. Welling, “Auto-encoding variational bayes,”                       Wilson–Cowan model,” J. Math. Neurosci., vol. 5, pp. 1–27, Apr. 2015.
     Dec. 2013, arXiv:1312.6114.                                                      [57] D. R. Freestone, P. J. Karoly, and M. J. Cook, “A forward-looking review
[39] A. Smola, A. Gretton, L. Song, and B. Schölkopf, “A hilbert space em-                 of seizure prediction,” Curr. Opin. Neurol., vol. 30, no. 2, pp. 167–173,
     bedding for distributions,” in Proc. Int. Conf. Algorithmic Learn. Theory,            Apr. 2017.
     2007, pp. 13–31.                                                                 [58] E. Bou Assi, Y. Zerouali, M. Robert, F. Lesage, P. Pouliot, and D.
[40] P. Peng, Y. Song, L. Yang, and H. Wei, “Seizure prediction in EEG signals             K. Nguyen, “Large-scale desynchronization during interictal epileptic
     using STFT and domain adaptation,” Front. Neurosci., vol. 15, Jan. 2022,              discharges recorded with intracranial EEG,” Front. Neurol., vol. 11,
     Art. no. 825434.                                                                      Dec. 2020, Art. no. 529460.
[41] H. Li, S. J. Pan, S. Wang, and A. C. Kot, “Domain generalization with            [59] M. I. Maturana et al., “Critical slowing down as a biomarker for seizure
     adversarial feature learning,” in Proc. IEEE Conf. Comput. Vis. Pattern               susceptibility,” Nat. Commun., vol. 11, no. 1, May 2020, Art. no. 2172.
     Recognit., Dec. 2018, pp. 5400–5409.                                             [60] K. Samiee, P. Kovács, and M. Gabbouj, “Epileptic seizure detection in
[42] A. Makhzani, J. Shlens, N. Jaitly, I. Goodfellow, and B. Frey, “Adversarial           long-term EEG records using sparse rational decomposition and local
     autoencoders,” Nov. 2015, arXiv:1511.05644.                                           Gabor binary patterns feature extraction,” Knowl.-Based Syst., vol. 118,
[43] X. Mao, Q. Li, H. Xie, R. Y. Lau, Z. Wang, and S. Paul Smolley, “Least                pp. 228–240, 2017.
     squares generative adversarial networks,” in Proc. IEEE Int. Conf. Comput.       [61] A. Al Fahoum, “Complex wavelet-enhanced convolutional neural net-
     Vis., Apr. 2017, pp. 2794–2802.                                                       works for electrocardiogram-based detection of paroxysmal atrial fibrilla-
[44] T. Maiwald, M. Winterhalder, R. Aschenbrenner-Scheibe, H. U. Voss, A.                 tion,” Adv. Signal Process Artif. Intell., vol. 158, 2024, Art. no. 2450046.
     Schulze-Bonhage, and J. Timmer, “Comparison of three nonlinear seizure
     prediction methods by means of the seizure prediction characteristic,”
     Physica D, vol. 194, no. 3-4, pp. 357–368, Apr. 2004.


         Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:35:45 UTC from IEEE Xplore. Restrictions apply.
```
