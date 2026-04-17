---
citation_key: "ZhangEtAl2026"
paper_id: "paper_231"
title: "HCFT: Hierarchical Convolutional Fusion Transformer for EEG Decoding"
authors: "Haodong Zhang; Jiapeng Zhu; Yitong Chen; Hongqi Li"
year: 2026
doi: ""
source: "arxiv (2601.12279)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2601.12279"
tier: 1
composite: 4.8
---

# HCFT: Hierarchical Convolutional Fusion Transformer for EEG Decoding

**Citation:** `ZhangEtAl2026` · **Tier:** 1 · **Composite:** 4.8

**Source PDF:** `full_pdf/Zhang2026.pdf`

## Abstract

Electroencephalography (EEG) decoding re- dependencies that are crucial for accurate neural representa- quires models that can effectively extract and integrate tion. Instead, the recent advent of the Transformer model, with complex temporal, spectral, and spatial features from mul- arXiv:2601.12279v1 [cs.HC] 18 Jan 2026 its powerful self-attention mechanism, offers a promising alter- tichannel signals. To address this challenge, we propose a lightweight and generalizable decoding framework named native for modeling these complex spatiotemporal dynamics. Hierarchical Convolutional Fusion Transformer (HCFT), Specifically, Transformer-based architectures offer strong which combines dual-branch convolutional encoders and capabilities for modeling long-range dependencies from se- hierarchical Transformer blocks for multi-scale EEG rep- quential data, and thus numerous studies have applied them resentation learning. Specifically, the model first captures to EEG decoding [5]. Typically, Wang et al. [6] proposed a local temporal and spatiotemporal dynamics through time- domain and time-space convolutional branches, and then Transformer-based architecture that hierarchically learns dis- aligns these features via a cross-attention mechanism that criminative spatial information to enhance the capture of EEG enables interaction between branches at each stage. Sub- spatial dependencies, achieving favorable results in emotion sequently, a hierarchical Transformer fusion structure is recognition tasks. Xie et al. [7] designed five categories of employed to encode global dependencies across all feature Transformer-based models for different EEG scenarios based stages, while a customized Dynamic Tanh normalization module is introduced to replace traditional Layer Normal- on the importance of spatiotemporal dependencies between ization in order to enhance training stability and reduce different channels for accurate classification. The developed redundancy. Extensive experiments are

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
IEEE TRANSACTIONS AND JOURNALS TEMPLATE               1


                                                    HCFT: Hierarchical Convolutional Fusion
                                                       Transformer for EEG Decoding
                                                               Haodong Zhang, Jiapeng Zhu, Yitong Chen, Hongqi Li*, Member, IEEE


                                            Abstract— Electroencephalography (EEG) decoding re-                 dependencies that are crucial for accurate neural representa-
                                         quires models that can effectively extract and integrate               tion. Instead, the recent advent of the Transformer model, with
                                         complex temporal, spectral, and spatial features from mul-


arXiv:2601.12279v1 [cs.HC] 18 Jan 2026
                                                                                                                its powerful self-attention mechanism, offers a promising alter-
                                         tichannel signals. To address this challenge, we propose a
                                         lightweight and generalizable decoding framework named                 native for modeling these complex spatiotemporal dynamics.
                                         Hierarchical Convolutional Fusion Transformer (HCFT),                     Specifically, Transformer-based architectures offer strong
                                         which combines dual-branch convolutional encoders and                  capabilities for modeling long-range dependencies from se-
                                         hierarchical Transformer blocks for multi-scale EEG rep-               quential data, and thus numerous studies have applied them
                                         resentation learning. Specifically, the model first captures           to EEG decoding [5]. Typically, Wang et al. [6] proposed a
                                         local temporal and spatiotemporal dynamics through time-
                                         domain and time-space convolutional branches, and then                 Transformer-based architecture that hierarchically learns dis-
                                         aligns these features via a cross-attention mechanism that             criminative spatial information to enhance the capture of EEG
                                         enables interaction between branches at each stage. Sub-               spatial dependencies, achieving favorable results in emotion
                                         sequently, a hierarchical Transformer fusion structure is              recognition tasks. Xie et al. [7] designed five categories of
                                         employed to encode global dependencies across all feature              Transformer-based models for different EEG scenarios based
                                         stages, while a customized Dynamic Tanh normalization
                                         module is introduced to replace traditional Layer Normal-              on the importance of spatiotemporal dependencies between
                                         ization in order to enhance training stability and reduce              different channels for accurate classification. The developed
                                         redundancy. Extensive experiments are conducted on two                 models incorporated positional encoding into the Transformer,
                                         representative benchmark datasets, BCI Competition IV-                 improving the classification performance and performing well
                                         2b and CHB-MIT, covering both event-related cross-subject              in cross-subject validation. Song et al [8] designed a model
                                         classification and continuous seizure prediction tasks. Re-
                                         sults show that HCFT achieves 80.83% average accuracy                  called EEG Conformer to decode EEG signals by CNN to
                                         and a Cohen’s kappa of 0.6165 on BCI IV-2b, as well as                 extract local features and Transformer to capture the global
                                         99.10% sensitivity, 0.0236 false positives per hour, and               features, demonstrating excellent performance on the tasks
                                         98.82% specificity on CHB-MIT, consistently outperforming              of motor imagery (MI) classification and emotion recogni-
                                         over ten state-of-the-art baseline methods. Ablation stud-             tion. Similarly, ACTNN [9] cascades CNN and Transformer,
                                         ies confirm that each core component of the proposed
                                         framework contributes significantly to the overall decoding            integrating crucial spatial, spectral, and temporal EEG in-
                                         performance, demonstrating HCFT’s effectiveness in cap-                formation effectively, achieving outstanding performance on
                                         turing EEG dynamics and its potential for real-world BCI               two public emotion recognition datasets. Furthermore, Wei
                                         applications.                                                          et al. [10] designed a model named TC-Net that employed
                                           Index Terms— EEG decoding, feature fusion, trans-                    the Transformer module to capture the global features of
                                         former, convolutional neural network, signal processing.               EEG, and a new strategy of EEG-PM was used to merge
                                                                                                                the neighboring patches and better extract local features. It
                                                                                                                performs well in the subject-dependent scenario of emotion
                                                                I. I NTRODUCTION
                                                                                                                recognition task, while obtaining relatively low performance

                                         E    LECTROENCEPHALOGRAM decoding is a critical
                                              component of modern brain-computer interfaces (BCIs),
                                         enabling applications in medical rehabilitation, affective com-
                                                                                                                in the cross-subject recognition task. Siddhad et al. [11] also
                                                                                                                achieved excellent classification results using Transformer net-
                                                                                                                work on raw EEG data without feature extraction, indicating
                                         puting, and human-machine interaction [1]–[4]. While deep              the Transformer-based deep learning network can abate the
                                         learning has markedly advanced the field, models based on              need for heavy feature-extraction of EEG data. Zheng and
                                         Convolutional Neural Networks (CNNs) and Recurrent Neural              Pan [12] designed STS-Transformer for multi-channel EEG
                                         Networks (RNNs) are inherently constrained by their local              without data preprocessing to extract spatio-temporal features
                                         receptive fields, struggling to capture the long-range, global         automatically, achieving remarkable performance in emotion
                                                                                                                recognition tasks. A most recently proposed framework of
                                            Manuscript received Nov 12, 2025. This work was supported in part
                                         by the Natural Science Basic Research Program of Shaanxi Province      Dual-TSST fully incorporate CNN and Transformer to ex-
                                         under Grant 2024JC-YBQN-0659 (Corresponding author: Hongqi Li.)        tract comprehensive spatio-frequency features through a dual-
                                            H. Zhang, J. Zhu, Y. Chen, and H. Li are with the School of         branch architecture, demonstrating remarkable performance in
                                         Software, Northwestern Polytechnical University, Xi’an 710072, China
                                         (e-mail: zhang haodong@mail.nwpu.edu.cn, zhujp@mail.nwpu.edu.cn,       various EEG decoding [13].
                                         chenyt@mail.nwpu.edu.cn, lihongqi@nwpu.edu.cn).                           Despite these promising developments, several key limita-

2                                                                                         IEEE TRANSACTIONS AND JOURNALS TEMPLATE


tions persist. A predominant challenge is the limited general-       to as CFT Blocks, enabling the whole network to abstract
ization capability of these models in cross-subject validation       EEG representations from low-level fluctuations to high-level
scenarios, indicating a reliance on subject-specific character-      cognitive patterns. Within each block, separable convolutions
istics. Moreover, existing architectures often feature consider-     are used to capture temporal, spatial, and spectral information,
able structural complexity, leading to high computational costs.     while self-attention and cross-attention mechanisms facilitate
Most critically, there is a frequent lack of effective synergy and   long-range and inter-branch interactions.
explicit modeling of the interrelation-ships between temporal,          Between stages, temporal resolution is reduced through
spatial, and spectral features. These limitations highlight the      average pooling, and channel dimensions are adjusted via
need for novel decoding frameworks that can simultane-               pointwise convolutions (see the DownSampling module), fa-
ously capture fine-grained temporal rhythms, spatial patterns        cilitating effective hierarchical representation learning. This
across electrodes, and multi-scale global dependencies, while        pyramidal architecture, inspired by designs such as the Swin
maintaining parameter efficiency and ensuring stable training        Transformer, supports efficient multi-scale modeling while
dynamics.                                                            retaining both fine-grained local cues and global contextual
   To address the aforementioned limitations, we introduce           information. The outputs from all stages are concatenated
the Hierarchical Convolutional Fusion Transformer (HCFT),            along the token dimension and passed through a final multi-
a novel EEG decoding framework. Inspired by the Pyramid              head attention layer, which refines global interactions before
Vision Transformer (PVT) [14], HCFT uses a hierarchical              feeding into the classification head.
structure that downsamples feature maps to manage com-                  To further enhance training stability and improve temporal
putational complexity. The architecture is guided by three           sensitivity, HCFT integrates learnable positional embeddings
core principles: (i) local feature extraction with cross-modal       and optionally incorporates a lightweight normalization strat-
guidance, (ii) modular stacking enhanced for depth stability,        egy known as Dynamic Tanh Normalization. DyT serves as
and (iii) one-shot multi-scale token fusion.                         a task-adaptive alternative to conventional LayerNorm, intro-
   The model first processes EEG signals through a dual-             ducing a learnable nonlinear transformation that can stabilize
branch depthwise separable convolutional encoder. One branch         information propagation across deep layers without increasing
extracts one-dimensional temporal features, while the other          inference overhead. In practice, either DyT or LayerNorm can
captures two-dimensional spatiotemporal patterns. A condi-           be selected depending on the characteristics of the dataset,
tional cross-attention mechanism then uses the temporal fea-         allowing the framework to balance generalization and stability
tures as queries to guide the spatiotemporal branch, explicitly      across diverse decoding scenarios.
aligning fine-grained temporal rhythms with spatial patterns in
a computationally efficient manner.
   These features are processed by a unified Convolutional           B. CFT Block
Fusion Transformer (CFT) Block, which integrates Multi-                 The core innovation of the HCFT architecture lies in its
Head Self-Attention (MHSA), Multi-Head Cross-Attention               modular unit, termed the CFT Block, which comprises two
(MHCA), and an expanded feed-forward network. To ensure              integrated components: a dual-branch convolutional feature
stable training in deep stacks, we optionally incorporate a          extractor and an attention-based fusion module. This design
Dynamic Tanh Normalization (DyT) module [15], which im-              enables the model to capture complementary fine-grained local
proves convergence without incurring inference overhead.             patterns and long-range global dependencies from EEG signals
   Finally, a pyramidal encoder facilitates multi-scale fusion.      across multiple semantic levels.
Tokens from different hierarchical stages are concatenated              1) Dual-Branch Convolutional Feature Extractor: To extract
and integrated via self-attention. A subsequent long-context         EEG features from distinct perspectives, we construct a par-
pooling operation condenses this information into a compact          allel dual-branch structure. Given an input EEG tensor X ∈
representation, enabling the one-shot integration of high-           R 𝐻 ×𝑊 ×𝐶 , where B denotes the batch size, C the number of
resolution local features and long-range global dependencies.        channels, and T the temporal length, two feature extraction
   The remainder of this paper is organized as follows. Section      pathways are applied in parallel:
II presents the architecture and implementation details of the          Temporal Convolution Branch (1D): This branch treats the
HCFT model. Section III reports dataset and experimental             EEG input as a multi-channel time series data and employs
setups. Section IV provides the detailed results with ablation       depthwise separable 1D convolutions to capture temporal
analyses. Finally, section V discusses and concludes the study,      dynamics at the channel level. Specifically, a depthwise con-
with future directions outlined.                                     volution filters each channel independently, followed by a
                                                                     pointwise convolution to enable inter-channel fusion and di-
                     II. M ETHODOLOGY                                mensional projection. Batch normalization, GELU activation,
A. Overall Model Architechture                                       and dropout are applied for regularization and stability. The
                                                                     computation can be expressed as: ‘
   As demonstrated in Fig.1, HCFT adopts a multi-stage hier-
archical encoder, which is grouped into progressively deeper                      T1 = GELU(BN(DWConv1D(X)))                      (1)
semantic stages (i.e., Stage 1, Stage 2, Stage 3, Stage 4)
and each stage contains a different number (N1, N2, N3,
N4) of cascaded convolution-attention fusion blocks, referred                  Y1 = T1 = GELU(BN(PWConv1D(T1 )))                  (2)

AUTHOR zhang et al.: HCFT: HIERARCHICAL CONVOLUTIONAL FUSION TRANSFORMER FOR EEG DECODING                                            3


        Fig. 1: The proposed HCFT framework, include Multiple Stage design with different number of CFT Blocks


  where P is the number of patches and D is the embedding           main modality representations. Following this principle, we
dimension.                                                          treat the output of the temporal branch as the conditioning
  Spatiotemporal Convolution Branch (2D): This branch               signal and the output of the spatiotemporal branch as the
considers EEG as a 2D array X′ ∈ R 𝐵×1×𝐶 ×𝑇 in treating             main representation, enabling temporal cues to guide spatial-
channels and time jointly. First, a temporal convolution with       contextual feature refinement. We assume the outputs are
kernel shape scans along the time axis across all channels:         equal-length sequences: Z𝑐𝑜𝑛𝑑 , Z𝑚𝑎𝑖𝑛 ∈ R 𝐵×𝑃×𝐷 .
                                                                       Self-Attention Enhancement: To enable long-range tem-
                                                      ′             poral dependencies within the spatiotemporal branch, a stan-
       TS1 = GELU(BN(Conv2D(X))) ∈ R 𝐵×𝐹 ×𝐶 ×𝑇                (3)   dard MHSA mechanism is applied. A Pre-Norm structure is
  Next, a depthwise spatial convolution (kernel size ) is           adopted, where the normalization layer can be configured as
applied to compress the channel dimension:                          either Dynamic Tanh Normalization (DyT) or conventional
                                                                    LayerNorm, depending on the task setting. In this work, we
                                                          ′
                                                                    explore both variants across datasets, allowing the model to
   TS2 = GELU(BN(DWConv2D(X))) ∈ R 𝐵×𝐹 ×𝐶 ×𝑇                  (4)   flexibly balance stability and generalization.
   Then, a pointwise convolution reshapes the output to match
                                                                              Z̃main = Norm(Zmain ),     Norm = DyT/LN              (6)
the temporal branch format.
                                                                    Then we project to query, key, and value:
                                             𝐵×𝐹 ×𝐶 ×𝑇 ′
   TS2 = GELU(BN(DWConv2D(X))) ∈ R                            (5)      Q𝑠 = W𝑞(𝑠) Z̃main , K𝑠 = W 𝑘(𝑠) Z̃main , V𝑠 = W𝑣(𝑠) Z̃main   (7)
   Finally, the 4D tensor is rearranged and flattened to match        The self-attention result is:
the temporal branch output format:Y2 ∈ R 𝐵× 𝑃×𝐷 , with D
consistent with the other branch and format:T′ = P.
                                                                    Aself = MHSA(Q𝑠 , K𝑠 , V𝑠 ) ∈ R 𝐵×𝑃×𝐷 ,    Z1 = Aself + Zmain
   2) Attention-based Fusion Module: This module receives the
                                                                                                                              (8)
outputs Y2 ∈ R 𝐵× 𝑃×𝐷 from both branches and processes them
                                                                       Cross-Attention Fusion: The temporal branch captures
through three steps: Self-Attention Enhancement, Cross-
                                                                    local dynamics while the spatiotemporal branch encodes struc-
Attention Fusion, and Feedforward Network (FFN). The
                                                                    tural and contextual information. After normalization:
design is inspired by conditional attention mechanisms used
in DiT, where low-dimensional signals guide the modeling of                                  Z̃1 = DyT(Z1 )                         (9)

4                                                                                            IEEE TRANSACTIONS AND JOURNALS TEMPLATE


  We project the temporal branch as query and the main                 A. Datasets and Preprocessing
branch as key and value:                                                  Dataset I—BCI Competition IV 2b: This dataset comprises
    Qc = W𝑞(𝑐) Zcond , Kc = Wk(𝑐) Zcond , Vc = Wv(𝑐) Zcond ,    (10)   2-second EEG trials of left- and right-hand motor imagery
                                                                       from nine healthy subjects, recorded at 250 Hz using three
Then compute with the cross-attention (CSA) operation:                 electrodes (C3, Cz, and C4). To evaluate cross-subject gener-
       Across = CSA(Q𝑐 , K𝑐 , V𝑐 ),          Z2 = Across + Z1   (11)   alization, we adopt a leave-one-subject-out (LOSO) protocol:
                                                                       in each of the nine folds, data from eight subjects are used for
Feedforward and Final Integration: An FFN is applied, and              training, and the held-out subject is used for testing. All trials
residual and conditional inputs are integrated:                        are z-score normalized on a per-channel basis, and fixed-length
                                                                       2-second segments are used as model input. Final performance
                 Z = FFN(DyT(Z2 ) + Z2 + Zcond                  (12)
                                                                       is reported as the average accuracy and Cohen’s kappa across
Position Encoding and DyT: A learnable positional encoding             the nine folds.
is added in the main branch to encode sequence order. DyT                 Dataset II—CHB-MIT Scalp EEG: The CHB-MIT dataset
(Dynamic Tanh) replaces LayerNorm to improve training                  comprises continuous, multi-channel intracranial EEG record-
stability. It scales the input with a learnable factor 𝛼:              ings from pediatric subjects with epilepsy, sampled at 256 Hz.
                                                                       We adhere to the preprocessing pipeline established in [16],
                      DyT(𝑥) = tanh(𝛼 · 𝑥) + Z1                 (13)
                                                                       which involves channel selection, bandpass filtering, and data
                                                                       segmentation for a seizure prediction task. From the original
C. Multi-Scale Aggregation and Final Classification                    23 channels, we retain 18 standardized bipolar channels. The
   Within each stage, multiple CFT Blocks are stacked to               study includes data from 20 subjects, having excluded subjects
expand the model’s effective receptive field while maintaining         04, 12, 13, and 24 due to excessive recording durations,
consistent patch length and embedding dimension. Between               inconsistent channel configurations, or inadequate interictal
stages, average pooling is applied along the temporal axis to          data. The continuous EEG is segmented into 5-second epochs.
progressively reduce resolution, and pointwise convolution is          The preictal class is defined as epochs occurring within the 30-
used to align the channel dimensions across scales:                    minute window preceding a seizure onset. Interictal samples
                                                                       are drawn from seizure-free periods, with explicit exclusion
               S𝑖+1 = AvgPooling((S𝑖 ), 𝑖 = 1, 2, 3, 4          (14)   of ictal activity, a 4-hour buffer zone around each seizure,
Each stage output is projected to the final dimension space            and a 30-second postictal window to prevent transitional
and concatenated:                                                      contamination. All data segments are subsequently z-score
                                                                       normalized per channel.
                  Zfinal = Concat(S1′ , S2′ , . . . , S′𝑛 )     (15)      Noise artifacts are suppressed using a sixth-order Butter-
A final MHSA module is applied to globally refine the                  worth band-stop filter targeting powerline harmonics (57–63
fused representation, followed by normalization (LayerNorm             Hz and 117–123 Hz), followed by a 1 Hz high-pass filter to
or DyT), global average pooling, and a fully connected layer           eliminate baseline drift. The original 256 Hz sampling rate
for classification (trained using cross-entropy loss):                 is preserved throughout preprocessing. A subject-wise 70/30
                                                                       split is used for training and testing, respectively.
               𝑦 = FC(GAP(Norm(MHA(Zfinal )))                   (16)
In summary, the proposed hierarchical convolutional fusion             B. Experiment Setting
Transformer HCFT is a specialized deep learning framework                 1) Performance Metrics: To ensure a comprehensive evalua-
for EEG decoding. It harnesses a dual-branch convolutional             tion across diverse EEG decoding scenarios, we employ a suite
encoder to capture complementary fine-grained temporal and             of established metrics tailored to each task’s specific require-
spatiotemporal features. These features are dynamically in-            ments. For general classification tasks, we report Accuracy,
tegrated by the cross-attention and hierarchically aggregated          the standard deviation (Std) of accuracy across subjects, and
within a multi-stage encoder, which employs a shared patch             Cohen’s Kappa coefficient (Kappa). Accuracy quantifies the
structure and a multi-scale fusion strategy. Consequently, the         proportion of correctly classified samples, and Std measures
architecture successfully models global long-range dependen-           cross-subject performance consistency. Kappa further assesses
cies while simultaneously preserving critical local details.           inter-rater reliability by accounting for chance agreement,
                                                                       making it robust to class imbalance.
      III. DATASET AND EXPERIMENTAL SETUP                                 In seizure detection tasks using the CHB-MIT dataset, we
   To comprehensively evaluate the modeling capacity and               adopt domain-specific metrics: Sensitivity (Sens), Specificity
architectural effectiveness of the proposed HCFT framework,            (Spec), the False Positive Rate per hour (FPR/h), and the
we conduct empirical studies on two widely used and repre-             Area Under the ROC Curve (AUC). Sensitivity and Specificity
sentative EEG datasets: BCI Competition IV-2b for MI classi-           evaluate the model’s precision in identifying seizure and non-
fication and CHB-MIT for seizure prediction. These datasets            seizure events, respectively. The FPR/h is a critical clinical
differ significantly in task setting, subject population, and          indicator quantifying hourly false alarms, while the AUC pro-
signal characteristics, thereby providing a rigorous testbed for       vides a holistic view of the model’s discriminative capability
assessing the generalizability and robustness of our method.           across all classification thresholds.

AUTHOR zhang et al.: HCFT: HIERARCHICAL CONVOLUTIONAL FUSION TRANSFORMER FOR EEG DECODING                                                   5


   2) Implementation Details: To ensure robust training and fair             captures the multi scale spatiotemporal dependencies inherent
cross-dataset comparisons, the proposed HCFT model was im-                   in EEG data.
plemented in Python 3.11 using PyTorch 2.0. All experiments
were conducted on a single NVIDIA GeForce RTX 4090 GPU.
                                                                                                    IV. RESULTS
The model was trained using the AdamW optimizer with an
initial learning rate of 0.001 and a weight decay of 0.00125. A                 This section presents a comprehensive evaluation of the
cosine annealing scheduler with a maximum cycle length of 32                 proposed HCFT. We first benchmark its performance against
epochs was used for learning rate adjustment. The optimizer’s                state-of-the-art (SOTA) methods on two public EEG datasets.
momentum coefficients were set to (0.675, 0.999). Training                   Subsequently, we perform ablation studies to isolate and
was conducted for up to 250 epochs with early stopping based                 quantify the contribution of each core component. Finally,
on validation performance. A batch size of 64 was used for                   we provide visual analyses to offer interpretable insights that
all experiments.                                                             substantiate the model’s design rationale.

C. Model Parameters                                                          A. Head-to-head Comparison Results
   TABLE I lists the detailed model parameters. Specifically,
                                                                                TABLE II summarizes the cross subject performance of the
the internal structure of HCFT is designed to match the
                                                                             proposed model and 15 representative baselines on Dataset
temporal and spectral characteristics of EEG. Both the 1D
                                                                             I. Overall, the proposed HCFT attains a mean accuracy of
temporal branch and the 2D spatiotemporal branch use con-
                                                                             80.83%, which is the highest among all contenders with
volutional kernels of length 15, effectively covering the 8–30
                                                                             small standard deviations. The performance advantage of
Hz 𝛼/𝛽 rhythm band that is critical for cognitive decoding.
                                                                             HCFT is consistent and statistically significant. It outperforms
Depthwise separable convolutions are applied independently
                                                                             canonical CNN baselines with ConvNet by 10.18% (p¡0.01),
across EEG channels to extract localized rhythms, followed by
                                                                             EEGNet by 7.38% (p¡0.05), and MSNN by 5.81% (p¡0.05),
1×1 pointwise convolutions that perform cross-channel fusion
                                                                             respectively. A further comparison with the CNN Transformer
and projection into a unified embedding space with dimension
                                                                             hybrids(Hybrid-s/t CViT) shows that the gains increase to
D.
                                                                             16.39% and 14.04% (both p ¡ 0.01). Furthermore, HCFT
       TABLE I: Module and Parameters of the Model                           always maintains a 4 6% accuracy advantage over recent
                                                                             Transformer-based models like CTNet, ConTraNet, EEGPT,
      Module           Input Shape     Output Shape     Kernel    Stride     and MSCFormer. More specifically for the individual, while
      2D Conv             (C, T)        (N, C, T)        (1,15)    (1,1)     HCFT was marginally outperformed on subjects S3, S5, and
   2D DW Conv           (N, C, T)       (N, C, T’)        (C,1)    (1,1)     S6 by EEGNet, CTNet, and MSNN respectively, it secured
   2D Pw Conv           (N, C, T’)        (P, D)          (1,1)    (1,1)
   1D Dw Conv             (C, T)          (N, T)           15        1       the top accuracy on six out of nine subjects (S1, S2, S4, S7,
   1D Pw Conv             (N, T)          (P, D)            1        1       S8, S9). Overall, HCFT demonstrated a clear and compre-
  Pooling (S1∼S3)         (P, D)         (P’, D)        (1, 10)    (1,2)     hensive performance lead, surpassing all 15 contenders and
    Pooling (S4)          (P, D)         (P”, D)          (1,4)    (1,2)
 Pooling (S-Concat)       (P, D)        (𝑃final , D)     (1,75)   (1,15)     outperforming five models (MSHCNN, Conformer, EEGCCT,
                                                                             Hybrid EEGNet, MSVTNet) on every single subject.
   *C: EEG channel count, T: original time steps, N indicates intermediate
   feature channels, P represents patch numbers (token number), and D is        In terms of the robustness, HCFT demonstrates superior
   the embedding dimension.                                                  stability with a cross-subject standard deviation of 7.61%.
                                                                             This is markedly lower than models like SCNN (over 12%)
   Between hierarchical stages, we introduce staged average                  and represents a 2-3% improvement over other contenders,
pooling to progressively adjust the temporal resolution. Stages              indicating that HCFT is less sensitive to inter-individual
1–3 (i.e., S1 S3 in TABLE I apply average pooling with a                     variability and delivers more consistent performance. Further,
kernel of (1, 10) and a stride of (1, 2), halving the sequence               regarding classification agreement, HCFT achieves a Cohen’s
length at each stage to expand the receptive field while                     𝜅 of 0.6165, signifying substantial agreement and surpassing
preserving essential temporal details. Stage 4 (i.e., S4) further               the best values reported by CTNet (0.5252). It is important
compresses the representation using a kernel of (1, 4) and                   to note that although we reproduced the published code for
stride of (1, 2). After concatenating the outputs of all stages,             ConvNet, EEGNet, Conformer, EEGCCT, CTNet, MSVTNet,
a long context pooling operation with a kernel of (1, 75) and                EEGPT, and MSCFormer to obtain 𝜅, such the metric was not
stride of (1, 15) uniformly compresses the multi scale sequence              reported in other compared literatures, thus limiting a more
into a fixed length, thereby satisfying the input requirements               comprehensive benchmark.
of subsequent attention modules and the classification head.                    We further evaluate HCFT on the Dataset II and compare
   Finally, the embedding dimension D and the number of                      it with a series of SOTA seizure prediction methods reported
attention heads are chosen to balance representational capacity              from 2018 to date. The comparative results, as summarized in
and computational efficiency. We set D = 32 and employ two                   TABLE III, include well-known baselines such as CNN, TTT,
attention heads, which in small token scenarios allows for par-              TGCNN, BSDCNN, MAAE, and more recent frameworks
allel modeling of diverse patterns while keeping computational               including DRSN-GRU, MCNN, ASRU-RW, DWT, STCNN,
overhead within acceptable bounds. Through these carefully                   HviT-DUL, M-d-C, MTLG, B2-ViT, MSAN and NSFA-Net.
calibrated parameter choices, HCFT remains efficient, yet fully              These methods vary widely in terms of protocol design, such

6                                                                                                                     IEEE TRANSACTIONS AND JOURNALS TEMPLATE


                                                                          TABLE II:
Classification Accuracy And Kappa Values of Different Methods on Dataset I [Avg Acc: The Average Accuracy (%); S1 S9 Means Subject 1 9 Involved in
                     The Dataset I; ‘-’ Indicates that the exact values were not reported by the original paper; *: P<0.05, **: P<0.01.]

    Year           Methods               S1         S2      S3          S4         S5          S6          S7         S8         S9        Avg Acc         Std      Kappa
    2017        ConvNet [17]           64.19       62.9   67.58        72.06      75.87       72.01       81.51      79.02      60.68      70.65**        7.33       0.4134
    2019        EEGNet [18]            66.15      71.08   72.01        56.48      80.24       78.78       85.03      79.54      71.74      73.45**       8.64        0.4684
    2019         MSNN [19]             74.72      65.29   57.63        91.21      74.72       85.55       72.91      76.57      76.66       75.02*        9.88          -
    2020     Hybrid s-CViT [20]        68.47      56.91   50.42        81.08      60.68       61.67       62.22      70.00      68.47      64.44**        8.81          -
    2021     Hybrid t-CViT [20]        66.39      55.74   52.36         82.7      72.57       63.89       68.89      65.92      72.64      66.79**        9.12          -
    2022       MSHCNN [21]             76.80      66.32   57.36        91.75      79.59       82.63       74.16      80.13      75.55      76.03**        9.79          -
    2023       Conformer [8]           65.89      64.43   67.45        84.45      72.24       76.56       77.86      69.23      74.87       76.4**        6.51       0.4521
    2024       EEGCCT [22]             68.75       59.6    59.9        89.21      73.44       75.39        76.3      75.76      77.73      73.26**       9.21        0.4587
    2024     Hybrid EEGNet [23]        71.53      65.00   58.75        84.86      78.78       77.50       77.92      73.68      75.41      73.72**        7.82          -
    2025         CTNet [24]            76.25      71.03   66.39        81.76      83.11       77.22       79.17      73.56      77.92       76.27*        5.26       0.5252
    2025        EEGPT [25]             72.22      69.71   61.53        78.78      81.08       70.42       83.89      83.82      70.83      74.70**       7.61        0.4936
    2025         SCNN [27]               -          -       -            -          -           -           -          -          -          79.38       14.17          -
    2025      MSCFormer [28]           76.11      71.18   62.36        81.35      81.08       74.72       78.89      76.18      75.42      75.25**        5.80       0.5051
    2025       ConTraNet [29]          72.92      72.94   63.75        83.51      82.70       80.69       84.44      77.37      70.83      76.57**        6.97          -
    2025           HCFT                78.62      73.23   67.71        93.92      82.72       82.68       86.17      84.47      77.94       80.83        7.61        0.6165

     TABLE III: Comparison Results of Different Methods on Dataset II for Seizure Prediction (SOP: Seizure Occurrence Period; SPH: Seizure Prediction
                Horizon; EP: Excluded Patients; LOOCV: Leave-One-Out Cross-Validation; “–” Indicates Values Not Reported by the Paper)

    Year      Method                          Results                   SOP & SPH (Minutes)                                             Notes
    2018      CNN [30]               SENS: 81.20%, FPR:0.16/h                     30 & 5                                 EP: 04, 06 08, 11, 12, 15 17, 22
    2022       TTT [16]             SENS: 96.01%; FPR: 0.047/h                    30 & 3                                          EP: 12, 13, 15
    2022     TGCNN [31]        SENS: 91.5%; FPR: 0.145/h; AUC: 0.935              30 & 5                                   EP: 04, 06, 07, 11, 12, 15, 22
    2022    BSDCNN [32]         SENS: 94.69; FPR: 0.095/h; AUC:0.970           30 (PIL) & 5                                 With 01, 05, 08, 10, 14, 22
    2022     MAAE [33]         SENS: 82.20%; FPR: 0.13/h; AUC: 0.940                 -                LODO (Leave-One-Domain-Out), with 01, 03, 05, 06, 08, 10, 13, 14, 18, 20
    2023   DRSN-GRU [33]       SENS: 90.54%; FPR: 0.11/h; AUC: 0.880              30 & 5                                   LOOCV, with 01, 02, 03, 16
    2023     MCNN [35]              SENS: 82.00%; FPR:0.058/h                        -                                              All patients
    2023   ASRU-RW [36]              SENS: 98.96; FPR: 0.048/h                    30 & 5               LOOCV (based on the subject-specific, 80% train, 20% test), EP: 12, 15
    2023      DWT [37]                SENS: 91.7%; FPR: 0/h                       25 & 5                       EP: 12, 13, 24 17 for train, 4 for test (04, 10, 06, 19)
    2023     STCNN [38]      SENS: 92.94%; FPR: 0.073/h; AUC: 0.9596                 -                                              All Patients
    2023   HviT-DUL [39]     SENS: 87.90%; FPR: 0.056/h; AUC: 0.9370              30 & 1                                      EP: 04, 06, 07, 12, 15
    2024      M-d-C [40]      SENS: 97.80%; FPR: 0.059/h AUC: 0.9350                 -                                                LOOCV
    2024      MTLG [41]             SENS: 98.24%; FPR: 0.033/h                    30 & 5                                        EP: 04, 12, 13, 24
    2024     B2-ViT [41]     SENS: 93.30%; FPR: 0.057/h; AUC: 0.9230              30 & 5                            EP: 04, 06, 07, 08, 11, 12, 15, 16, 17, 22
    2025     MSAN [43]          SENS:96.27%; FPR: 0/h; AUC:0.9300                 60 & 5                                        EP: 04, 12, 15, 19
    2025    NSFA-Net [44]     SENS: 98.68%; FPR: 0.038/h; AUC:0.9060              30 & 5                                        EP: 04, 12, 15, 19
    2025        HCFT        SENS: 99.10%; FPR: 0.0236/h;SPEC: 98.82%              30 & 3                                        EP: 04, 12, 13, 24


as the number of selected patients, evaluation strategies (e.g.,                        identifies the optimal configuration for key hyperparame-
LOSO, subject-specific splits), and employed metrics.                                   ters, including encoder depth, embedding dimension, and
   Despite these diversities, HCFT achieves the highest overall                         the number of attention heads. Second, to assess cross-task
performance, attaining a sensitivity of 99.10%, a false positive                        adaptability, this optimal configuration is directly transferred
rate of only 0.0236/h, and a specificity of 98.82%, while
being evaluated on all available patients under a leave-one-out
scheme. This performance surpasses most previous models,
including the recent ASRU-RW in 2023 (98.96%, 0.048/h),
MTLG in 2024 (98.24% sensitivity, 0.033/h FPR), and NSFA-
Net in 2025 (98.68%, 0.038/h), which often excluded specific
patient subsets or relied on partial data splits.
   Taken together, these results demonstrate that HCFT offers
superior performance in the challenging cross subject, long-
sequence EEG decoding task, thereby underscoring its strong
potential for BCI applications.

B. Structural and Task Adaptability Analysis
   The effectiveness of architectural choices and parameters in
EEG decoding can vary significantly across different tasks. To
rigorously evaluate the robustness and generalizability of the
proposed HCFT model under such heterogeneous conditions,
we conduct extensive parameter sensitivity and module-level
ablation studies on two representative datasets.
   This evaluation is structured in two phases: First, a sys-                           Fig. 2: Accuracy effect of embedding dimension and number
tematic sensitivity analysis on Dataset I (MI classification)                           of heads.

AUTHOR zhang et al.: HCFT: HIERARCHICAL CONVOLUTIONAL FUSION TRANSFORMER FOR EEG DECODING                                            7


to Dataset II (epileptic seizure prediction), where targeted       depth enhances the model’s capacity to capture complex long-
ablation experiments quantify the contribution of each core        range interactions and inter-channel relationships. In fact,
structural component.                                              experimental results confirm that deeper configurations yield
   1) Parameter Sensitivity Analysis : To examine the role         consistent performance gains. The model stage layer from
of dimensionality and multi-head configurations, a sensitivity     N1 N4 in Fig. 1 being 1-1-4-1 structure achieved the highest
analysis on the embedding dimension (D) and the number             accuracy and Kappa score (see in Fig. 3), demonstrating that
of attention heads (H), increasing D from 32 to 64 while           a moderate increase in depth at this critical stage effectively
adjusting H to maintain a consistent per-head dimension. Since     strengthens the model’s ability to learn hierarchical represen-
the dimension-to-heads ratio must be an integer, configurations    tations without inducing overfitting.
with dimensions of 32 or 64 are incompatible with 3 heads and         Normalization is critical for ensuring training stability and
thus being excluded. As illustrated in Fig. 2, the configuration   generalization in Transformer-based models. To evaluate the
with D = 48 and H = 3 achieved the optimal results, deliver-       task-specific efficacy of our proposed Dynamic Tanh Norma-
ing the highest accuracy with reduced performance variance.        lization of DyT, we compared it against traditional LayerNorm
However, while increasing D provided marginal gains, it            across two distinct EEG decoding paradigms.
incurred a substantial increase in model complexity. Indeed,          The results reveal a clear task-dependent performance trade-
as concluded in TABLE IV, with increasing in the embedding         off. On the motor imagery classification task (Dataset I), DyT
dimension D and the number heads H, both the model size            achieved a +2.01% higher average accuracy than LayerNorm
(#Param) and FLOPs significantly increase. Therefore, for an       (TABLE V). We attribute this advantage to DyT’s dynamic,
optimal balance of performance and computational efficiency,       learnable scaling followed by a saturating nonlinearity and thus
we selected D = 32 with H = 2 as the default configuration.        exceling at highlighting transient, event-driven features in non-
                                                                   stationary MI-EEG signals, unlike LayerNorm’s reliance on
TABLE IV: Computational Efficiency for Specific Dim (D) and        global statistics.
Head (H) Configuration with Model Stage Layer N of 1-1-2-1            Conversely, LayerNorm proved more effective for the
on Dataset I                                                       seizure prediction task (Dataset II). This task involves signals
                                                                   with higher continuity, stronger rhythmicity, and more pro-
  D     H     Performance Metric       #Param       FLOPs
                                                                   nounced long-range dependencies, where LayerNorm’s global
  32    2      Avg Acc: 79.40%         88.987K     72.880M         statistical stabilization better handles session-wise variability
  48    3      Avg Acc: 79.40%        194.123K     161.039M        and ensures robust training. While DyT resulted in a slight
  64    4      Avg Acc: 79.74%        339.707K     283.700M        performance decrease in this context, it consistently reduced
                                                                   model size (#Param) and computational cost (FLOPs), under-
   To investigate the impact of model depth, we systematically     scoring its value for lightweight deployment.
varied the number of encoder layers while maintaining the             Consequently, we adopt DyT for Dataset I and retain
above default configuration. We focused depth adjustments          LayerNorm for Dataset II. This selective configuration aligns
on Stage 3 of the architecture, as this stage is responsible       the normalization strategy with the intrinsic statistical prop-
for integrating spatiotemporal features from earlier layers and    erties and temporal dynamics of each specific EEG decoding
modeling higher-level semantic dependencies. Increasing its        paradigm.

                                                                            TABLE V: Evaluation of Parameter Complexity
                                                                    Strategy    Dataset   Performance Metric   #Param      FLOPs
                                                                      LN           I       Avg Acc: 78.82% ±   88.987K    72.880M
                                                                                                   7.13
                                                                      LN          II      SENS: 99.1%; SPEC:   194.123K   161.039M
                                                                                              98.82%; FPR:
                                                                                                0.0236/h
                                                                      DyT          I       Avg Acc: 80.83% ±   339.707K   283.700M
                                                                                                   7.61
                                                                      DyT         II         SENS: 96.34%;     339.707K   283.700M
                                                                                          SPEC: 98.42%; FPR:
                                                                                                0.0268/h


                                                                      2) Ablation Experiment: : To quantitatively assess the contri-
                                                                   butions of the core components in the proposed HCFT model,
                                                                   we conducted systematic ablation studies on both Dataset I
                                                                   and Dataset II. The experiments evaluate four critical modules:
                                                                   the self-attention mechanism, the conditional cross-attention
                                                                   module, the stage-wise feature concatenation, and the final
                                                                   multi-head attention layer. As listed in TABLE VI, ablation
Fig. 3: Influence of number of Stage 3 layers on model             results on Dataset I confirm that each architectural component
performance.                                                       is integral to HCFT’s performance, as the removal of any

8                                                                                       IEEE TRANSACTIONS AND JOURNALS TEMPLATE


                 TABLE VI: Ablation Results and Performance Impact of Key HCFT Components on Dataset I and II

    Self-Attn.    Cross-Attn.   Stages Concat   Final MHA   Dataset I Avg Acc (%)              Dataset II Performance
        ×             ✓              ✓             ✓              79.60±7.96          SENS: 98.31%; FPR:0.025/h; SPEC:98.47%
        ✓             ×              ✓             ✓              79.10±7.97          SENS: 98.84%; FPR:0.0240/h; SPEC:97.0%
        ✓             ✓              ×             ✓              79.75±8.39         SENS: 98.78%; FPR:0.0280/h; SPEC:98.30%
        ✓             ✓              ✓             ✓              79.63±7.76         SENS: 98.73%; FPR:0.02512/h; SPEC:98.86%
        ✓             ✓              ✓             ✓              80.83±7.61         SENS: 99.10%; FPR:0.0236/h; SPEC:98.82%


single module induces consistent degradation. The most sub-       of structural redundancy within HCFT for long-range EEG
stantial performance drop occurred when the cross-attention          tasks such as seizure prediction. The distinct, pronounced
mechanism was disabled (79.10% ± 7.97), highlighting its          patterns characteristic of preictal activity appear to be captured
critical role in fusing class-discriminative information from     effectively by the core spatiotemporal modeling, even when
the temporal and spatiotemporal branches. Removing self-          specific components are disabled. This property is highly
attention also caused a notable decline (79.60% ± 7.96), under-   advantageous for clinical deployment, as it suggests the model
scoring its necessity for modeling global temporal dynamics,      can be adapted to various computational constraints without
particularly in 𝜇- and 𝛽-rhythms. Similarly, omitting stage-      compromising critical detection performance. Moreover, the
wise concatenation led to reduced accuracy (79.75% ± 8.39),       minor contributions of components like DyT or the final
affirming the importance of multi-scale hierarchical features     MHA in this context may become more critical in noisier
for robust decoding.                                              environments, pointing to a pathway for future optimization
                                                                  targeted at challenging real-world scenarios.
   For Dataset II, we similarly performed ablation experiments
by sequentially removing the self-attention, cross-attention,
stage concatenation, and final MHSA modules. The results          C. Visualization
exhibited marginal fluctuations in performance, where the           To interpret internal decision-making of the proposed
sensitivity remained consistently high (> 98%) with a false       HCFT, we visualized the channel-wise attention distributions
positive rate below 0.03/h. This robustness indicates a degree    across hierarchical stages on four representative subjects. As


            Fig. 4: The proposed HCFT framework, include Multiple Stage design with different number of CFT Blocks

AUTHOR zhang et al.: HCFT: HIERARCHICAL CONVOLUTIONAL FUSION TRANSFORMER FOR EEG DECODING                                           9


illustrated in Fig. 4, each heatmap presents the normalized         S4, S5, S7, S8), the t-SNE visualization revealed two well-
attention weights assigned by the model to channels and token       separated clusters (see in Fig. 5). It demonstrates that the
at each processing stage (Stage 1 4), offering a dynamic per-       extracted features exhibit notable intra-class compactness and
spective on how spatial representations evolve hierarchically       inter-class separability, validating the model’s ability to dis-
throughout the network. For these selected subjects (S2, S4,        criminate between different categories in the latent space.
S5, S6), a clear pattern emerges: early stages (e.g., Stage 1)      When combined with the channel-wise token activation maps,
display a diffuse attention pattern, reflecting an initial, broad   a complementary trend emerges: for the subjects S4 and
exploratory phase across all input channels. As processing          S5 with high performance, attention intensifies progressively
advances to deeper stages (Stages 3-4), attention sharpens          across stages, culminating in distinct spatial localization during
dramatically, converging onto a sparse set of critical channels     Stage 3 and 4. This hierarchical refinement implies that
and tokens. This progression from exploration to specialization     the HCFT leverages successive attention layers to suppress
suggests the model hierarchically refines its spatial focus to      irrelevant noise and reinforce salient spatial representations.
isolate the most discriminative, task-relevant neural signatures       In summary, these above presented analyses, including
for motor imagery task of Dataset I.                                ablation studies, parameter sensitivity evaluations, attention-
   This observed sharpening of attention is not merely a            and feature-based visualizations, collectively confirm the ef-
result of deeper network compression, but rather reflects the       fectiveness and interpretability of the HCFT architecture.
coordinated interaction between stacked convolutional filters
and the model’s attention mechanisms. While early layers                     V. DISCUSSION AND CONCLUSION
Combining the heatmap and TABLE II, four cases (S2, S4, S5,
S6) show structured multi-stage attention concentration and            In this study, we proposed the Hierarchical Convolutional
are able to learn effective features in the shallow stages and      Fusion Transformer (HCFT), a novel decoding architecture
key features in the deeper stages, reflecting advanced decoding     that addresses the inherent non-stationarity and subject vari-
performance.                                                        ability of EEG signals through a unified spatiotemporal mod-
   provide spatially localized receptive fields, the self- and      eling framework. Inspired by the classical deep learning
cross-attention modules progressively integrate information         pipeline of hierarchical feature extraction and multi-scale
across spatial dimensions and across processing stages. This        integration, HCFT incorporates dual-branch convolutions to
leads to a reconstruction of more abstract spatial represen-        encode diverse frequency-temporal patterns and employs a
tations that are tuned to class-specific neural dynamics, ulti-     hierarchical multi-stage Transformer structure to progressively
mately yielding stronger decoding performance.                      fuse representations across temporal and spatial dimensions.
   To further investigate the model’s capability to capture         The attention-based fusion mechanism enhances inter-branch
inter-subject variability, we visualized the features for each      communication, while the inclusion of normalization variants
individual subject. Among the representative subjects (e.g.,        with Dynamic Tanh (DyT) further supports flexibility across
                                                                    tasks with differing signal properties.
                                                                       The effectiveness of HCFT has been verified on two funda-
                                                                    mentally distinct EEG tasks, supporting its applicability across
                                                                    both event-related (i.e., Dataset I) and continuous monitoring
                                                                    (i.e., Dataset II) scenarios. From a structural perspective, the
                                                                    combination of local convolutional priors and global attention-
                                                                    based modeling enables the network to capture both short-term
                                                                    discriminative patterns and long-range dependencies, a design
                                                                    that aligns well with the intrinsic hierarchical organization
                                                                    of neural signals. Moreover, the use of modular stages with
                                                                    shared token structures facilitates deeper feature abstraction
                                                                    while maintaining computational tractability. Attention visu-
                                                                    alizations further reveal that the model learns to prioritize
                                                                    semantically meaningful channels and time points, offering a
                                                                    degree of interpretability that is often lacking in current deep
                                                                    EEG models [5], [13].
                                                                       In summary, HCFT demonstrates highly competitive per-
                                                                    formance and robust cross-subject generalization, a capability
                                                                    we attribute to its integrated spatiotemporal feature extraction
                                                                    and synergistic use of self-attention and cross-attention mecha-
                                                                    nisms. This design fosters rich interactions between temporal
                                                                    and spatial representations while effectively balancing local
                                                                    feature extraction with global dependency modeling. Despite
                                                                    this overall strength, HCFT was marginally outperformed on
Fig. 5: The features for subjects ((a)-S4, (b)-S5, (c)-S7, (d)-     subjects S3, S5, and S6 in Dataset I by specialized archi-
S8) of Dataset I by t-SNE visualization.                            tectures. EEGNet’s efficiency in capturing canonical EEG

10                                                                                          IEEE TRANSACTIONS AND JOURNALS TEMPLATE


features [18], CTNet’s enhanced local detail extraction [24],       In conclusion, HCFT offers a principled and extensible
and MSNN’s multi-scale representational capacity [19] each        approach to EEG decoding by combining structural hierarchy,
conferred a subject-specific advantage. These cases highlight     dynamic fusion, and attention-based abstraction. It provides
that while HCFT provides a powerful generalized framework,        not only empirical effectiveness across diverse tasks but also
the optimal architecture may still vary with individual neuro-    a conceptual framework that bridges handcrafted priors and
physiological characteristics.                                    deep representations. As research moves toward more scalable,
   Meanwhile, the proposed HCFT framework faces some              adaptive, and multimodal decoding systems, HCFT lays a
other open challenges that warrant further investigation. A       solid foundation for both theoretical exploration and practical
primary limitation is its reliance on dataset-specific hyperpa-   advancement in neural signal processing.
rameter tuning for components like the normalization strategy
and stage depth, which could impede seamless generaliza-
                                                                                                  R EFERENCES
tion to novel datasets or subject cohorts. Future work could
explore meta-learning or adaptive reparameterization tech-
niques to enable subject-agnostic configuration. Furthermore,
the model’s development is constrained by the limited scale        [1] H. Hu et al., “A survey on brain-computer interface-inspired communi-
                                                                       cations: opportunities and challenges,” IEEE Commun. Surv. Tutorials,
and diversity of existing public EEG datasets, which hinders           vol. 27, no. 1, pp. 108-139, Feb. 2025.
the pursuit of true cross-population robustness. Addressing        [2] H. Li, X. Li and J. R. d. Millán, “Noninvasive EEG-based intelligent
this fundamental issue will likely require the creation of             mobile robots: A systematic review,” IEEE Trans. Autom. Sci. Eng., vol.
                                                                       22, pp. 6291-6315, 2025.
large-scale, multi-center EEG corpora, potentially facilitated     [3] S. M. Alarcão and M. J. Fonseca, “Emotions recognition using EEG
by federated learning frameworks or cross-institutional col-           signals: a survey,” IEEE Trans. Affect. Comput., vol. 10, no. 3, pp. 374-
laboration frameworks. Finally, while HCFT is designed to              393, Jun. 2017.
                                                                   [4] H. Li, L. Bi, and H. Shi, “Modeling of human operator behavior
be efficient, the computational demands of its multi-stage             for brain-actuated mobile robots steering,” IEEE Trans. Neural. Syst.
attention mechanisms remain non-trivial for real-time edge             Rehabil. Eng., vol. 28, no. 9, pp. 2063-2072, Sep. 2020.
deployment. Future research should prioritize strategies such      [5] H. Zhang and H. Li, “Transformer-base EEG decoding: A survey,” 2025,
                                                                       arXiv: 2507.02320.
as hybrid quantization, knowledge distillation, or neural ar-      [6] Z. Wang, Y. Wang, C. Hu, Z. Yin, and Y. Song, “Transformers for EEG-
chitecture search to achieve a more optimal balance between            based emotion recognition: A hierarchical spatial information learning
performance and practical efficiency [5].                              model,” IEEE Sens. J., vol. 22, no. 5, pp. 4359–4368, Mar. 2022.
                                                                   [7] J. Xie et al., “A Transformer-based approach combining deep learning
   Importantly, HCFT is designed with high extensibility in            network and spatial-temporal information for raw EEG classification,”
mind. Despite its compact configuration in the current imple-          IEEE Trans. Neural Syst. Rehabil. Eng., vol. 30, pp. 2126–2136, 2022.
mentation, the architecture supports straightforward scaling in    [8] Y. Song, Q. Zheng, B. Liu, and X. Gao, “EEG Conformer: convolutional
                                                                       Transformer for EEG decoding and visualization,” IEEE Trans. Neural
both depth and width, making it well-suited for future inte-           Syst. Rehabil. Eng., vol. 31, pp. 710–719, 2023.
gration with large-scale pretraining paradigms. This provides      [9] L. Gong, M. Li, T. Zhang, and W. Chen, “EEG emotion recognition us-
a promising foundation for developing EEG-based foundation             ing attention-based convolutional transformer neural network,” Biomed.
models, where massive cross-task or cross-subject data can             Signal Process. Control, vol. 84, p. 104835, July 2023.
                                                                  [10] Y. Wei, Y. Liu, C. Li, J. Cheng, R. Song, and X. Chen, “TC-Net:
be leveraged to build generalizable neural decoders through            A Transformer capsule network for EEG-based emotion recognition,”
contrastive learning, masked modeling, or instruction-based            Comput. Biol. Med., vol. 152, p. 106463, Jan. 2023.
pretraining. As the demand grows for flexible and general-        [11] G. Siddhad, A. Gupta, D. P. Dogra, and P. P. Roy, “Efficacy of
                                                                       transformer networks for classification of EEG data,” Biomed. Signal
purpose neuro intelligent systems, the capacity of HCFT to             Process. Control, vol. 87, p. 105488, Jan. 2024.
scale up offers new avenues for robust representation learning    [12] W. Zheng and B. Pan, “A spatiotemporal symmetrical transformer struc-
and semantic-level EEG interpretation.                                 ture for EEG emotion recognition,” Biomed. Signal Process. Control,
                                                                       vol. 87, p. 105487, Jan. 2024.
   Looking ahead, the integration of HCFT with emerging           [13] H. Li, H. Zhang, and Y. Chen, “Dual-TSST: A dual-branch temporal-
foundation models offers exciting opportunities for the next           spectral-spatial Transformer model for EEG decoding,” IEEE J. Biomed.
generation of brain decoding frameworks. Recent develop-               Health Inform., vol. 29, no. 9, pp. 6524–6537, Sept. 2025.
                                                                  [14] W. Wang et al., “Pyramid vision Transformer: A versatile backbone for
ments in large-scale pretrained language and vision mod-               dense prediction without convolutions,” in Proc. IEEE/CVF Int. Conf.
els have demonstrated remarkable capacity for generalization           Comput. Vis. (ICCV), Montreal, QC, Canada, 2021, pp. 548-558.
under limited supervision. Applying similar paradigms to          [15] J. Zhu, X. Chen, K. He, Y. LeCun, and Z. Liu, “Transformers without
                                                                       Normalization”, in Proc. IEEE/CVF Conf. Comput. Vis. Pattern Recog-
EEG, such as prompt-based tuning, semantic alignment across            nit., (CVPR), 2025, pp. 14901-14911.
modalities, or context-aware reasoning, may enable models         [16] J. Yan et al., “Seizure prediction based on transformer using scalp
that go beyond classification to interpret intention, emotion,         electroencephalogram,” Appl. Sci., vol. 12, no. 9, pp. 4158, 2022.
                                                                  [17] R. T. Schirrmeister et al., “Deep learning with convolutional neural
or cognition in a more naturalistic manner [45]. Moreover,             networks for EEG decoding and visualization,” Human Brain Mapping,
expanding the decoding framework to incorporate multimodal             vol. 38, no. 11, pp. 5391–5420, 2017.
biosignals such as EMG, eye tracking, or speech could unlock      [18] V. J Lawhern et al., “EEGNet: a compact convolutional neural network
richer representations of human intent and state, bridging the         for EEG-based brain-computer interfaces,” J. Neural Eng., vol. 15, no.
                                                                       5, Jul. 2018, Art. no. 056013.
gap between neuroscience and embodied artificial intelligence.    [19] W. Ko, E. Jeon, S. Jeong, and H.-I. Suk, “Multi-scale neural network
These directions will further promote the transformation of            for EEG representation learning in BCI,” IEEE Comput. Intell. Mag.,
EEG decoding from a task-specific pipeline to a flexible,              vol. 16, no. 2, pp. 31–45, May. 2021.
                                                                  [20] A. Keutayeva and B. Abibullaev, “Exploring the potential of attention
interpretable, and general-purpose neuro-symbolic modeling             mechanism-based deep learning for robust subject-independent motor-
paradigm.                                                              imagery based BCIs,” IEEE Access, vol. 11, pp. 107562-107580, 2023.

AUTHOR zhang et al.: HCFT: HIERARCHICAL CONVOLUTIONAL FUSION TRANSFORMER FOR EEG DECODING                                                           11


[21] X. Tang, et al., “Motor imagery EEG decoding based on multi-scale             [45] H. Li, Y. Chen, Y. Wang, W. Ni, H. Zhang, “Foundation mod-
     hybrid networks and feature enhancement,” IEEE Trans. Neural Syst.                 els for cross-domain EEG analysis application: A survey,” 2025,
     Rehabil. Eng., vol. 31, pp. 1208-1218, 2023.                                       arXiv:2508.15716.
[22] A. Keutayeva et al., “Compact convolutional transformer for subject-
     independent motor imagery EEG-based BCIs,” Sci. Rep., vol. 14, no. 1,
     p. 25775, Oct. 2024.
[23] C. Olvera, O. M. Ross, and Y. Rubio, “EEG-based motor imagery
     classification with quantum algorithms,” Expert Syst. Appl., vol. 247,
     p. 123354, Aug. 2024.
[24] W. Zhao et al., “CTNet: a convolutional transformer network for EEG-
     based motor imagery classification,” Sci. Rep., vol. 14, no. 1, p. 20237,
     Aug. 2024.
[25] K. Liu et al., “MSVTNet: Multi-scale vision Transformer neural network
     for EEG-based motor imagery decoding,” IEEE J. Biomed. Health
     Inform., vol. 28, no. 12, pp. 7126-7137, Dec. 2024.
[26] G. Wang et al., “EEGPT: Pretrained Transformer for Universal and
     Reliable Representation of EEG Signals,” in Proc. 38th Conf. Neural
     Inform. Process. Syst. (NeurIPS), 2024, pp. 39249-39280.
[27] H. Kashefi Amiri, M. Zarei, and M. R. Daliri, “Motor imagery elec-
     troencephalography channel selection based on deep learning: A shallow
     convolutional neural network,” Eng. Appl. Artif. Intell., vol. 136, p.
     108879, Oct. 2024.
[28] W. Zhao et al., “Multi-scale convolutional transformer network for motor
     imagery brain-computer interface,” Sci. Rep., vol. 15, no. 1, p. 12935,
     Apr. 2025.
[29] O. Ali et al., “ConTraNet: A hybrid network for improving the classi-
     fication of EEG and EMG signals with limited training data,” Comput.
     Biol. Med., vol. 168, p. 107649, Jan. 2024.
[30] N. D. Truong et al., “Convolutional neural networks for seizure predic-
     tion using intracranial and scalp electroencephalogram,” Neural Netw.,
     vol. 105, pp. 104–111, Sep. 2018.
[31] C. Li et al., “EEG-based seizure prediction via Transformer guided
     CNN,” Measurement, vol. 203, p. 111948, Nov. 2022.
[32] S. Zhao, J. Yang, Y. Xu, and M. Sawan, “Binary single-dimensional
     convolutional neural network for seizure prediction’, in Proc. IEEE Int.
     Symp. Circuits Syst. (ISCAS), Oct. 2020, pp. 1–5.
[33] P. Peng, L. Xie, K. Zhang, J. Zhang, L. Yang, and H. Wei, “Domain
     adaptation for epileptic EEG classification using adversarial learning
     and Riemannian manifold”, Biomed. Signal Process. Control, vol. 75,
     p. 103555, May 2022.
[34] X. Xu, Y. Zhang, R. Zhang, and T. Xu, “Patient-specific method for
     predicting epileptic seizures based on DRSN-GRU,” Biomed. Signal
     Process. Control, vol. 81, p. 104449, Mar. 2023.
[35] A. K. Ibrahim, H. Zhuang, E. Tognoli, A. Muhamed Ali, and N. Erdol,
     “Epileptic seizure prediction based on multiresolution convolutional
     neural networks,” Front. Signal Process., vol. 3, May 2023.
[36] Z. Shi, Z. Liao, and H. Tabata, “Enhancing performance of convolu-
     tional neural network-based epileptic electroencephalogram diagnosis by
     asymmetric stochastic resonance,” IEEE J. Biomed. Health Inform., vol.
     27, no. 9, pp. 4228–4239, Sep. 2023.
[37] S. Hu et al., “Exploring the applicability of Transfer Learning and
     feature engineering in epilepsy prediction using hybrid Transformer
     model,” IEEE Trans. Neural Syst. Rehabil. Eng., vol. 31, pp. 1321–1332,
     2023.
[38] Y. Zhang et al., “Hybrid network for patient-specific seizure prediction
     from EEG data,” Int. J. Neur. Syst., vol. 33, no. 11, p. 2350056, Nov.
     2023.
[39] Z. Deng et al., “EEG-based seizure prediction via hybrid vision trans-
     former and data uncertainty learning,” Eng. Appl. Artif. Intell., vol. 123,
     p. 106401, Aug. 2023.
[40] Y. Wang et al., “Dynamic multi-graph convolution-based channel
     weighted transformer feature fusion network for epileptic seizure predic-
     tion,” IEEE Trans. Neural Syst. Rehabil. Eng., vol. 31, pp. 4266-4277,
     2023.
[41] R. Zhu, W. Pan, J. Liu, and J. Shang, “Epileptic seizure prediction via
     multidimensional transformer and recurrent neural network fusion,” J.
     Transl. Med., vol. 22, no. 1, p. 895, Oct. 2024.
[42] S. Shi and W. Liu, “B2-ViT Net: Broad vision Transformer network
     with broad attention for seizure prediction,” IEEE Trans. Neural Syst.
     Rehabil. Eng., vol. 32, pp. 178–188, 2024.
[43] Q. Dong, H. Zhang, J. Xiao, and J. Sun, “Multi-scale spatio-temporal
     attention network for epileptic seizure prediction,” IEEE J. Biomed.
     Health Inform., vol. 29, no. 7, pp. 4784–4795, July 2025.
[44] Q. Dong, Z. Wang, and M. Gao, “Noise-aware epileptic seizure pre-
     diction network via self-attention feature alignment,” IEEE J. Biomed.
     Health Inform., pp. 1–13, 2025.
```
