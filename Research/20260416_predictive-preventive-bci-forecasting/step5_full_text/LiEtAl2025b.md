---
citation_key: "LiEtAl2025b"
paper_id: "paper_298"
title: "Spatio-Temporal Attention Network for Epileptic Seizure Prediction"
authors: "Zan Li; Kyongmin Yeo; Wesley Gifford; Lara Marcuse; Madeline Fields; Bülent Yener"
year: 2025
doi: ""
source: "arxiv (2511.02846)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2511.02846"
tier: 1
composite: 4.5
---

# Spatio-Temporal Attention Network for Epileptic Seizure Prediction

**Citation:** `LiEtAl2025b` · **Tier:** 1 · **Composite:** 4.5

**Source PDF:** `full_pdf/Zan2025.pdf`

## Abstract

Recent advances in deep learning techniques have revolu- arXiv:2511.02846v1 [eess.SP] 24 Oct 2025 tionized seizure prediction. Transformer-based architectures In this study, we present a deep learning framework that learns demonstrate remarkable effectiveness in capturing long-range complex spatio-temporal correlation structures of EEG sig- temporal dependencies. Zhu et al. [20] recently achieved nals through a Spatio-Temporal Attention Network (STAN) 98% sensitivity using multidimensional transformer fusion for accurate predictions of onset of seizures for Epilepsy with recurrent networks. Graph neural networks (GNNs) have patients. Unlike existing methods, which rely on feature emerged as powerful tools for modeling dynamic brain con- engineering and/or assume fixed preictal durations, our ap- nectivity patterns during seizure propagation [9, 12]. Notably, proach simultaneously models spatio-temporal correlations Xiang et al. [18] demonstrated state-of-the-art performance through STAN and employs an adversarial discriminator to using synchronization-based graph spatio-temporal attention. distinguish preictal from interictal attention patterns, enabling Self-supervised approaches like AFTA [1] address limited la- patient-specific learning. Evaluation on CHB-MIT and MSSM beled data challenges. datasets demonstrates 96.6% sensitivity with 0.011/h false de- Despite these advances, several limitations persist. Most tection rate on CHB-MIT, and 94.2% sensitivity with 0.063/h methods assume fixed preictal durations across all patients, FDR on MSSM, significantly outperforming state-of-the-art failing to account for inter- and intra-patient variability [16]. methods. The framework reliably detects preictal states at least Current architectures process spatial and temporal features 15 minutes before an onset, with patient-specific windows ex- separately before fusion [17], potentially missing crucial tending to 45 minutes, providing sufficient intervention time cross-modal

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Spatio-Temporal Attention Network for Epileptic Seizure Prediction

                                                   Zan Li1 , Kyongmin Yeo2 , Wesley Gifford2 , Lara Marcuse3 , Madeline Fields3 , Bülent Yener1

                                                                            Department of Computer Science, Rensselaer Polytechnic Institute, Troy, NY, USA
                                                                                        IBM T.J. Watson Research Center, Yorktown Heights, NY, USA
                                                                      Department of Neurology, Icahn School of Medicine at Mount Sinai, New York, NY, USA


                                           Abstract                                                                       Recent advances in deep learning techniques have revolu-


arXiv:2511.02846v1 [eess.SP] 24 Oct 2025
                                                                                                                       tionized seizure prediction. Transformer-based architectures
                                           In this study, we present a deep learning framework that learns             demonstrate remarkable effectiveness in capturing long-range
                                           complex spatio-temporal correlation structures of EEG sig-                  temporal dependencies. Zhu et al. [20] recently achieved
                                           nals through a Spatio-Temporal Attention Network (STAN)                     98% sensitivity using multidimensional transformer fusion
                                           for accurate predictions of onset of seizures for Epilepsy                  with recurrent networks. Graph neural networks (GNNs) have
                                           patients. Unlike existing methods, which rely on feature                    emerged as powerful tools for modeling dynamic brain con-
                                           engineering and/or assume fixed preictal durations, our ap-                 nectivity patterns during seizure propagation [9, 12]. Notably,
                                           proach simultaneously models spatio-temporal correlations                   Xiang et al. [18] demonstrated state-of-the-art performance
                                           through STAN and employs an adversarial discriminator to                    using synchronization-based graph spatio-temporal attention.
                                           distinguish preictal from interictal attention patterns, enabling           Self-supervised approaches like AFTA [1] address limited la-
                                           patient-specific learning. Evaluation on CHB-MIT and MSSM                   beled data challenges.
                                           datasets demonstrates 96.6% sensitivity with 0.011/h false de-                 Despite these advances, several limitations persist. Most
                                           tection rate on CHB-MIT, and 94.2% sensitivity with 0.063/h                 methods assume fixed preictal durations across all patients,
                                           FDR on MSSM, significantly outperforming state-of-the-art                   failing to account for inter- and intra-patient variability [16].
                                           methods. The framework reliably detects preictal states at least            Current architectures process spatial and temporal features
                                           15 minutes before an onset, with patient-specific windows ex-               separately before fusion [17], potentially missing crucial
                                           tending to 45 minutes, providing sufficient intervention time               cross-modal interactions.
                                           for clinical applications.
                                           Keywords: Epilepsy prediction, deep learning, spatio-                  Our work addresses these gaps through three key innova-
                                           temporal attention, adversarial networks, patient-specific          tions: (1) Joint spatio-temporal attention modeling via STAN’s
                                           learning                                                            alternating modules that capture bidirectional dependencies;
                                                                                                               (2) Adversarial discrimination with gradient penalty distin-
                                                                                                               guishing preictal/interictal attention distributions; (3) Patient-
                                                                                                               specific preictal learning through incomplete supervision, al-
                                           1 Introduction                                                      lowing automatic inference of optimal preictal durations. This
                                                                                                               unified framework design, rather than simple component com-
                                           Epilepsy affects approximately 50 million people worldwide, bination, enables comprehensive capture of seizure dynamics
                                           constituting one of the most prevalent neurological disorders crucial for clinical application.
                                           [13]. The unpredictable nature of seizures significantly im-
                                           pacts patients’ daily life. Accurate seizure prediction enables
                                           timely interventions, such as medication administration, elec-
                                           trical stimulation, or alerting caregivers, that can prevent in-
                                           juries and improve quality of life.                                 2 Methodology
                                              EEG recordings classify brain activity into four states: pre-
                                           ictal, ictal, postictal, and interictal [7]. The seizure prediction
                                           problem involves distinguishing subtle preictal changes from 2.1 Problem Formulation
                                           interictal activity, occurring minutes to hours before clinical
                                           manifestation [4]. However, it is an open challenge how to Given multivariate time series x1:T = {x1 , . . . , xT } where T
                                           identify discriminative preictal features.                          is the window length and xt ∈ Rn represents the n-channel
                                              Traditional approaches extract handcrafted features using EEG signal at time t, our objective is to generate an anomaly
                                           time-domain statistics, frequency-domain spectral analysis, score yi ∈ [0, 1] for the i-th input window xi1:T , indicating the
                                           and nonlinear dynamics measures [6,8]. However, these meth- likelihood of being in a preictal state. The score approaches 0
                                           ods struggle to capture complex spatio-temporal patterns in for preictal states and 1 for interictal states, enabling real-time
                                           multi-channel EEG recordings.                                       monitoring of seizure risk.


2.2   Attention Mechanism                                              attention with H = 4 heads. This design captures how seizure
                                                                       activity spreads across different brain regions.
Our multi-head attention mechanism processes n nodes
                                                                          Temporal attention module complements spatial process-
{v1 , . . . , vn } where vi ∈ Rh . The attention map Ak for head
                                                                       ing by treating timestamps as graph nodes, modeling the tem-
k is computed via softmax over alignment scores:
                                                                       poral evolution of brain states. The spatial encoder, also im-
                         k
                   exp(Mij )                                           plemented as 1D CNN but with output dimension 100 and ker-
          Akij = PL             ,     k = 1, . . . , H      (1)        nel size 2, processes features across channels before applying
                             k
                  l=1 exp(Mil )                                        multi-head attention. This captures both instantaneous spatial
where H denotes the number of attention heads and L repre-             patterns and their temporal dynamics. Each of the M = 3 cas-
sents the neighborhood size. The alignment scores are com-             caded networks produces both spatial and temporal attention
puted using quadratic form:                                            maps, totaling 3 spatial and 3 temporal representations that
                                                                       comprehensively characterize input segments.
                        k
                       Mij = ziT WM
                                  k
                                    zj                      (2)           STAN is trained using Adam optimizer (lr=0.001) with
                                                                       MSE loss. The attention modules incorporate residual con-
where WM  k
             ∈ Rne ×ne are learnable weight matrices and zi            nections and layer normalization (Fig. 2) to facilitate stable
represents the encoded features. The final output aggregates           training and effective gradient flow through the deep architec-
information across all attention heads:                                ture.
                                             
                            H
                           XX   L
                 zi = σ           αk Akij vj           (3)
                           k=1 j=1

                         PH
where αk = exp(ak )/ l=1 exp(al ) are learnable weights
computed using softmax, and σ(·) is a nonlinear activation
function.

2.3   Spatio-Temporal             Attention          Network
      (STAN)


                                                                       Figure 2: Detailed architecture of spatial and temporal atten-
                                                                       tion modules. Both employ 1D CNN encoders followed by
                                                                       multi-head attention (H=4) and include residual connections
                                                                       with layer normalization for training stability.
Figure 1: Architecture of STAN showing three cascaded atten-
tion networks processing raw EEG input. Each network con-
tains spatial and temporal attention modules with H=4 atten-
tion heads. The resulting M=3 spatial and temporal attention
                                                                 2.4 Discriminator with Adversarial Training
maps are aggregated via MLP and passed to the discriminator The discriminator (Fig. 3) learns to distinguish preictal atten-
for adversarial training.                                        tion patterns from interictal ones through adversarial training.
                                                                 The architecture processes concatenated spatial and temporal
   STAN serves as a self-supervised feature extractor that re- attention maps from all M = 3 networks via a 2-layer MLP
constructs input EEG segments while simultaneously learning with hidden dimension 150 and ReLU activation, followed by
discriminative spatio-temporal representations. As shown in sigmoid output producing anomaly score yi ∈ [0, 1].
Fig. 1, the architecture consists of three consecutive attention    Given generator G (STAN) and discriminator D, our adver-
blocks and each attention block contains spatial and temporal sarial objective with gradient penalty is:
attention modules, which are sequentially connected. The raw
EEG signal flows through these networks, enabling hierarchi-            LD =Ex∼ppre [D(G(x))] − Ex∼pinter [D(G(x))]
cal abstraction of seizure patterns.                                                                                          (4)
                                                                               + λEx̂∼px̂ [(∥∇x̂ D(G(x̂))∥2 − 1)2 ]
   Spatial attention module processes the input sequence
v1:T where vt ∈ Rn represents the n-channel EEG at time where ppre and pinter denote preictal and interictal distribu-
t. Each spatial module treats EEG channels as nodes in a com- tions, px̂ represents uniformly sampled points along straight
plete graph, where edges represent inter-channel relationships lines between preictal and interictal attention patterns, and
critical for understanding seizure propagation. The temporal λ = 10 controls gradient penalty strength. The gradient
encoder zt = fte (vt ) = σ(Wte vt + bet ) is implemented as a penalty stabilizes training and prevents mode collapse.
1D CNN with kernel size 2 and output dimension 50, extract-         The discriminator loss LD is minimized while STAN’s gen-
ing temporal features that are then processed by multi-head erator loss LG = −Ex∼ppre [D(G(x))] encourages preictal


                                                                       1 hour before seizure as preictal and segments at least 4 hours
                                                                       from any seizure as interictal.
                                                                          MSSM Intracranial EEG Dataset [11]: This dataset con-
                                                                       tains recordings from 4 adult patients with drug-resistant
                                                                       epilepsy at Mount Sinai Hospital. The intracranial EEG
                                                                       (iEEG) is sampled at 512 Hz with 64-128 channels per pa-
                                                                       tient depending on electrode placement. The dataset includes
                                                                       104 total seizures with recording durations of 3-7 days per pa-
                                                                       tient. We apply identical preprocessing and labeling schemes
                                                                       as CHB-MIT to enable fair cross-modality comparison.
                                                                          Baselines: We compare against representative methods
                                                                       spanning different paradigms: (1) BFB+SVM [2, 19]: Tradi-
                                                                       tional feature engineering with bivariate frequency-based fea-
                                                                       tures and support vector machines; (2) CNN [3, 14]: Convo-
                                                                       lutional neural networks for automatic feature learning; (3)
Figure 3: Discriminator architecture employing MLPs to pro-
                                                                       Transformer [20]: State-of-the-art transformer-based architec-
cess aggregated attention patterns. Trained adversarially with
                                                                       ture with recurrent fusion; (4) STS-HGCN [10]: Advanced
gradient penalty to distinguish preictal from interictal states,
                                                                       spatio-temporal-spectral hierarchical graph convolutional net-
generating anomaly scores for real-time seizure prediction.
                                                                       work.
                                                                          Evaluation Metrics: Following clinical standards, we re-
patterns to be indistinguishable from interictal ones. This ad-        port sensitivity (Sn) as the percentage of correctly predicted
versarial learning creates a robust decision boundary enabling         seizures, requiring at least one alarm in the 5-50 minute win-
reliable preictal state detection. Training employs Adam opti-         dow before onset. False detection rate (FDR) measures false
mizer (lr=0.0001) for 100 epochs with batch size 32.                   alarms per hour during interictal periods. A prediction is
                                                                       considered successful if the alarm occurs 5-50 minutes be-
                                                                       fore seizure onset, providing adequate intervention time while
2.5   Patient-Specific Learning with Incomplete                        avoiding overly early warnings.
      Supervision                                                         Implementation Details: Our framework is implemented
                                                                       in PyTorch. STAN uses 3 cascaded attention networks (M =
Our framework addresses inter-patient variability through in-          3) with 4 attention heads (H = 4) each. Spatial encoders have
complete supervision that automatically learns optimal preic-          output dimension 50 while temporal encoders use dimension
tal durations. During training, segments are labeled as preictal       100. The discriminator employs a 2-layer MLP with hidden di-
only if they occur within 1 hour before seizure onset, avoiding        mension 150. Training uses Adam optimizer with learning rate
rigid duration assumptions. The discriminator learns patient-          0.001 for STAN and 0.0001 for discriminator, batch size 32,
specific patterns by observing the natural transition from inter-      for 100 epochs. All experiments are conducted on NVIDIA
ictal to preictal states, implicitly discovering individual preic-     V100 GPUs. Patient-specific 5-fold cross-validation is per-
tal characteristics without explicit duration specification.           formed where training/validation splits exclude test seizures
   At inference, we apply a 5-minute moving average filter to          and their surrounding periods.
discriminator scores, eliminating transient fluctuations while
preserving genuine state transitions. When the smoothed score
crosses threshold τ = 0.5 (optimized via validation), a preictal 3.2 Comparative Results
alarm triggers. This adaptive approach accommodates the 15-
                                                                   Table 1 shows our framework achieves 96.6% sensitivity with
45 minute range of detection times observed across patients,
                                                                   0.011/h false detection rate on CHB-MIT. This represents 40-
providing personalized prediction windows that balance sensi-
                                                                   fold reduction compared to BFB+SVM and 6-fold improve-
tivity with intervention time.
                                                                   ment over STS-HGCN. While Transformer achieves 95.8%
                                                                   sensitivity, its FDR (0.085/h) is 7.7× higher. Five patients
                                                                   achieve perfect sensitivity with zero false alarms.
3 Experiments                                                         MSSM results (Table 2) validate generalizability across
                                                                   recording modalities. The 94.2% sensitivity with 0.063/h
3.1 Datasets and Implementation                                    FDR confirms our spatio-temporal attention effectively cap-
                                                                   tures seizure dynamics.
CHB-MIT Scalp EEG Dataset [5, 15]: We evaluate on 8 pe-
diatric patients from PhysioNet database with 138 seizures to-
tal. The scalp EEG recordings are sampled at 256 Hz across 3.3 Real-time Prediction Analysis
23 channels, spanning continuous monitoring periods of 9-
42 hours per patient. We follow standard protocols using 5- Fig. 4 illustrates discriminator scores before seizures. The
second windows with 50% overlap, treating segments within consistent transition patterns emerge at least 15 minutes before


                                        Table 1: Performance Comparison on CHB-MIT Scalp EEG Dataset
                        BFB+SVM                       CNN                CNN+LSTM                 Transformer     STS-HGCN            Ours
         Patient
                      Sn(%) FDR/h                 Sn(%) FDR/h           Sn(%) FDR/h             Sn(%) FDR/h     Sn(%) FDR/h       Sn(%) FDR/h
         chb01         89.2       0.413           100       0.029        100         0.000      100     0.116    100      0.072    100     0.000
         chb05         87.2       0.379           100       0.209        80.0        0.262      80.0    0.157    95.0     0.095    100     0.000
         chb06         82.5       0.418           85.7      0.259        85.7        0.356      85.7    0.356    100      0.081    100     0.000
         chb08         92.3       0.482           100       0.087        100         0.000      100     0.174    100      0.067    100     0.000
         chb10         79.1       0.372           83.3      0.478        83.3        0.410      66.7    0.478    91.7     0.122    86.4    0.000
         chb13         76.4       0.513           85.7      0.328        85.7        0.219      85.7    0.219    92.9     0.091    88.7    0.043
         chb14         89.1       0.321           100       0.417        100         0.104      100     0.313    96.0     0.078    97.5    0.017
         chb22         88.8       0.612           100       0.435        100         0.000      100     0.261    91.0     0.074    100     0.030
         Avg           85.6       0.438           94.3      0.258        91.8        0.169      89.8    0.259    95.8     0.085    96.6    0.011


                                                                                          cascaded architecture shows progressive improvement with
 Table 2: Performance on MSSM Intracranial EEG Dataset
      Patient
                   BFB+SVM        Transformer        STS-HGCN            Ours             depth: single network achieves 93.1% sensitivity, two net-
                Sn(%)   FDR/h   Sn(%)     FDR/h    Sn(%)   FDR/h   Sn(%)    FDR/h
      TP         91.2   0.376    94.5     0.142     89.1   0.106    100      0.000        works reach 95.2%, and three networks achieve the full 96.6%
      IP         85.9   0.092    92.1     0.098     83.7   0.172    96.3     0.000
      PS         83.2   0.129    89.7     0.165     87.1   0.211    95.0     0.150
                                                                                          with corresponding FDR reductions from 0.037/h to 0.011/h.
      ZF
      Avg
                 66.8
                 81.8
                        0.452
                        0.262
                                 85.3
                                 90.4
                                          0.187
                                          0.148
                                                    81.1
                                                    85.3
                                                           0.118
                                                           0.152
                                                                    85.6
                                                                    94.2
                                                                             0.102
                                                                             0.063
                                                                                          Using spatial or temporal attention alone yields only 91.4%
                                                                                          and 92.7% sensitivity respectively with higher FDR (0.048/h
                                                                                          and 0.041/h), confirming that joint modeling provides essen-
                                                                                          tial gains for optimal performance.

                                                                                          3.5    Comparative Analysis and Clinical Impact
                                                                                          Our unified modeling outperforms baselines with statistical
                                                                                          significance (Wilcoxon signed-rank test, p < 0.01). The
Figure 4: Real-time seizure prediction showing discrimina-                                key advantage over transformers lies in balanced perfor-
tor scores 90 minutes before onset. Recording 03 (top) and                                mance—maintaining high sensitivity (96.6% vs 95.8%) while
Recording 26 (bottom) demonstrate consistent gradual shift                                reducing FDR by 7.7× (0.011/h vs 0.085/h), critical for avoid-
from interictal to preictal states, providing at least 15 minutes                         ing alarm fatigue.
of intervention time.                                                                        Patient-specific learning adapts preictal durations (15-45
                                                                                          minutes), accommodating inter-patient variability. The 15+
onset, with detection times varying from 20-45 minutes across                             minute detection window provides sufficient time for inter-
patients, providing sufficient intervention time.                                         ventions including medication administration or neurostimu-
                                                                                          lation activation, making the framework clinically viable for
                                                                                          both hospital and home monitoring.
3.4         Ablation Studies

                                                                                          4     Conclusion
Table 3: Ablation Study Results on CHB-MIT (Average of 8
patients)                                                     We introduced a unified seizure prediction framework that ad-
        Configuration             Sn(%) FDR(/h)               vances the state-of-the-art through joint spatio-temporal atten-
                                                              tion with adversarial learning. Our approach achieves superior
        Full Model                 96.6       0.011
                                                              performance on both scalp (96.6% sensitivity, 0.011/h FDR)
        Without adversarial        96.3       0.024
                                                              and intracranial (94.2% sensitivity, 0.063/h FDR) EEG, with
        Without gradient penalty   96.5       0.019
                                                              statistical significance over existing methods including recent
        M=1 (single network)       93.1       0.037
                                                              transformer approaches.
        M=2 (two networks)         95.2       0.021
                                                                 The framework’s patient-specific learning adapts preictal
        M=3 (three networks)       96.6       0.011
                                                              durations (15-45 minutes across patients) while maintaining
        Spatial only               91.4       0.048
                                                              robust performance, representing significant advancement to-
        Temporal only              92.7       0.041
                                                              ward personalized epilepsy management. Our system reliably
                                                              detects preictal states at least 15 minutes before seizure on-
   Table 3 demonstrates that each component contributes in- set, with many cases showing detection up to 20-45 minutes in
crementally to overall performance across all 8 patients. Re- advance, providing sufficient time for clinical intervention.
moving adversarial training increases FDR from 0.011/h to        This work establishes new benchmarks for seizure predic-
0.024/h while slightly reducing sensitivity to 96.3%. The tion and provides practical solutions for real-world deploy-


ment. Future research will explore cross-dataset generaliza- [11] Chenqi Li et al. Seizure detection and prediction by par-
tion, attention pattern interpretation, and edge device opti-     allel memristive convolutional neural networks. Fron-
mization.                                                         tiers in Neurology, 12:705119, 2021.

                                                                      [12] J. Lian et al. Epileptic EEG classification via graph trans-
References                                                                 former network. International Journal of Neural Sys-
                                                                           tems, 33(8):2350042, 2023.
 [1] T. Xiao, Z. Wang, Y. Zhang, S. Wang, H. Feng, [13] S. Mallick and V. Baths. Novel deep learning framework
     and Y. Zhao. Self-supervised learning with adaptive            for detection of epileptic seizures using EEG signals.
     frequency-time attention transformer for seizure predic-       Frontiers in Computational Neuroscience, 18:1340251,
     tion and classification. Biomedical Signal Processing          2024.
     and Control, 87:105464, 2024.
                                                               [14] R. T. Schirrmeister, J. T. Springenberg, L. D. J. Fiederer,
 [2] V. Bajaj and R. B. Pachori. Classification of seizure and      M. Glasstetter, K. Eggensperger, M. Tangermann, F. Hut-
     nonseizure EEG signals using empirical mode decompo-           ter, W. Burgard, and T. Ball. Deep learning with convolu-
     sition. IEEE Transactions on Information Technology in         tional neural networks for EEG decoding and visualiza-
     Biomedicine, 16(6):1135–1142, 2012.                            tion. Human Brain Mapping, 38(11):5391–5420, 2017.
 [3] H. Daoud and M. Bayoumi. Efficient epileptic seizure [15] A. H. Shoeb. Application of Machine Learning to Epilep-
     prediction based on deep learning. IEEE Transactions on   tic Seizure Onset Detection and Treatment. PhD thesis,
     Biomedical Circuits and Systems, 13(5):804–813, 2019.     Massachusetts Institute of Technology, 2009.

 [4] M. Esmaeilpour et al. Deep learning-based seizure pre- [16] N. D. Truong et al. Deep learning for epilepsy: A com-
     diction using EEG signals: A comparative analysis of        prehensive review. Frontiers in Neuroscience, 17, 2023.
     classification methods on the CHB-MIT dataset. Engi-
                                                            [17] B. Wang, Y. Xu, S. Peng, H. Wang, and F. Li. Detec-
     neering Reports, 2024.
                                                                 tion method of epileptic seizures using a neural network
 [5] A. L. Goldberger, L. A. Amaral, L. Glass, J. M. Haus-       model based on multimodal dual-stream networks. Sen-
     dorff, P. C. Ivanov, R. G. Mark, J. E. Mietus, G. B.        sors, 24:3360, 2024.
     Moody, C. K. Peng, and H. E. Stanley. PhysioBank, [18] J. Xiang, Y. Li, X. Wu, Y. Dong, X. Wen, and Y. Niu.
     PhysioToolkit, and PhysioNet: Components of a new re-   Synchronization-based graph spatio-temporal attention
     search resource for complex physiologic signals. Circu- network for seizure prediction.    Scientific Reports,
     lation, 101(23):e215–e220, 2000.                        15:4080, 2025.
 [6] L. D. Iasemidis, J. C. Sackellares, H. P. Zaveri, and W. J. [19] Z. Zhang and K. K. Parhi. Low-complexity seizure pre-
     Williams. Phase space topography and the Lyapunov ex-            diction from iEEG/sEEG using spectral power and ratios
     ponent of electrocorticograms in partial seizures. Brain         of spectral power. IEEE Transactions on Biomedical Cir-
     Topography, 2(3):187–201, 1990.                                  cuits and Systems, 10(4):693–706, 2016.
 [7] T. W. Kjaer and H. B. D. Sorensen. A real-time system [20] R. Zhu, W.-X. Pan, J.-X. Liu, and J.-L. Shang. Epileptic
     for detection of epileptic seizures in EEG. IEEE Trans-    seizure prediction via multidimensional transformer and
     actions on Biomedical Engineering, 64(12):2876–2887,       recurrent neural network fusion. Journal of Translational
     2017.                                                      Medicine, 22:895, 2024.

 [8] M. Le Van Quyen, J. Martinerie, M. Baulac, and
     F. Varela. Anticipating epileptic seizures in real time by
     a non-linear analysis of similarity between EEG record-
     ings. Neuroreport, 10(10):2149–2155, 1999.

 [9] Z. Li, K. Hwang, K. Li, J. Wu, and T. Ji. Graph-
     generative neural network for EEG-based epileptic
     seizure detection via discovery of dynamic brain func-
     tional connectivity. Scientific Reports, 12:23656, 2022.

[10] Y. Li, Y. Liu, Y.-Z. Guo, X.-F. Liao, B. Hu, and
     T. Yu. Spatio-temporal-spectral hierarchical graph con-
     volutional network with semisupervised active learning
     for patient-specific seizure prediction. IEEE Transac-
     tions on Cybernetics, 52(11):12189–12204, 2022.
```
