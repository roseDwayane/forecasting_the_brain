---
citation_key: "MahdiBaghdadi2026"
paper_id: "paper_216"
title: "Epileptic Seizure Prediction Using Patient-Adaptive Transformer Networks"
authors: "Mohamed Mahdi; Asma Baghdadi"
year: 2026
doi: ""
source: "arxiv (2603.26821)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2603.26821"
tier: 1
composite: 4.5
---

# Epileptic Seizure Prediction Using Patient-Adaptive Transformer Networks

**Citation:** `MahdiBaghdadi2026` · **Tier:** 1 · **Composite:** 4.5

**Source PDF:** `full_pdf/Mohamed2026.pdf`

## Abstract

Epileptic seizure prediction from electroencephalo- feature engineering and show limited robustness. Deep graphic (EEG) recordings remains challenging due to strong learning models, including CNNs on EEG spectrograms inter-patient variability and the complex temporal structure of [5] and recurrent networks such as LSTMs [6], improved neural signals. This paper presents a patient-adaptive trans- former framework for short-horizon seizure forecasting. The automation in feature extraction but often struggle with proposed approach employs a two-stage training strategy: self- long-range temporal dependencies. Transformer architectures supervised pretraining is first used to learn general EEG tem- address this limitation through self-attention mechanisms poral representations through autoregressive sequence modeling, that efficiently model long-term relationships in sequential followed by patient-specific fine-tuning for binary prediction of data [7]. Generative Pre-trained Transformers (GPTs) [8], seizure onset within a 30-second horizon. To enable transformer- based sequence learning, multichannel EEG signals are processed have demonstrated strong performance in time-series and using noise-aware preprocessing and discretized into tokenized biomedical signal analysis due to transferable pretrained temporal sequences. Experiments conducted on subjects from representations [7]. the TUH EEG dataset demonstrate that the proposed method achieves validation accuracies above 90% and F1 scores exceed- In this work, we propose a patient-specific seizure ing 0.80 across evaluated patients, supporting the effectiveness of combining self-supervised representation learning with patient- prediction framework based on a pretrained and fine-tuned specific adaptation for individualized seizure prediction. GPT model trained on TUH EEG recordings. The model

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Epileptic Seizure Prediction Using Patient-Adaptive
                                                        Transformer Networks
                                                                     Mohamed MAHDI                                                   Asma BAGHDADI
                                                               ICT Engineering Student                                        REGIM-Lab, University of Sfax,
                                                Information and Communication Engineering Department                    National Engineering School of Sfax (ENIS),
                                                          National Engineering School of Tunis                                 BP 1173, Sfax, 3038, Tunisia
                                                               Tunis El Manar University                                   National Engineering School of Tunis
                                                          mohamed.mahdi@etudiant-enit.utm.tn                                     Tunis El Manar University
                                                                                                                                asma.baghdadi@enit.utm.tn


arXiv:2603.26821v1 [cs.LG] 26 Mar 2026
                                            Abstract—Epileptic seizure prediction from electroencephalo-       feature engineering and show limited robustness. Deep
                                         graphic (EEG) recordings remains challenging due to strong            learning models, including CNNs on EEG spectrograms
                                         inter-patient variability and the complex temporal structure of       [5] and recurrent networks such as LSTMs [6], improved
                                         neural signals. This paper presents a patient-adaptive trans-
                                         former framework for short-horizon seizure forecasting. The           automation in feature extraction but often struggle with
                                         proposed approach employs a two-stage training strategy: self-        long-range temporal dependencies. Transformer architectures
                                         supervised pretraining is first used to learn general EEG tem-        address this limitation through self-attention mechanisms
                                         poral representations through autoregressive sequence modeling,       that efficiently model long-term relationships in sequential
                                         followed by patient-specific fine-tuning for binary prediction of     data [7]. Generative Pre-trained Transformers (GPTs) [8],
                                         seizure onset within a 30-second horizon. To enable transformer-
                                         based sequence learning, multichannel EEG signals are processed       have demonstrated strong performance in time-series and
                                         using noise-aware preprocessing and discretized into tokenized        biomedical signal analysis due to transferable pretrained
                                         temporal sequences. Experiments conducted on subjects from            representations [7].
                                         the TUH EEG dataset demonstrate that the proposed method
                                         achieves validation accuracies above 90% and F1 scores exceed-           In this work, we propose a patient-specific seizure
                                         ing 0.80 across evaluated patients, supporting the effectiveness of
                                         combining self-supervised representation learning with patient-       prediction framework based on a pretrained and fine-tuned
                                         specific adaptation for individualized seizure prediction.            GPT model trained on TUH EEG recordings. The model
                                            Index Terms—Seizure prediction, EEG, transformer, self-            first learns general EEG temporal dynamics through self-
                                         supervised learning, patient-specific, deep learning, pre-ictal       supervised pretraining, then adapts to individualized pre-ictal
                                         detection, time series.                                               patterns via patient-specific fine-tuning. This personalization
                                                                                                               directly addresses inter-patient variability and aligns with
                                                                I. I NTRODUCTION                               recent adaptive prediction strategies [9]. Our contributions
                                            Epilepsy affects more than 50 million people worldwide             are threefold: (1) a GPT-based architecture for EEG seizure
                                         and is characterized by recurrent, unpredictable seizures             forecasting, (2) validation of patient-specific fine-tuning on
                                         that severely impact patient safety and quality of life               TUH EEG data, and (3) evidence that transformer attention
                                         [1], [2]. Because seizures occur without warning, patients            captures meaningful pre-ictal temporal structures for early
                                         face risks of injury, psychological stress, and long-term             prediction.
                                         lifestyle restrictions. Current clinical systems remain largely
                                         reactive, focusing on seizure detection rather than prevention.          The remainder of this paper is organized as follows: Section
                                         Reliable early prediction would represent a major clinical            II reviews related work, Section III details the methodology,
                                         advance, enabling timely intervention and adaptive therapies.         Section IV presents experiments and results, and Section V
                                         Electroencephalogram (EEG) signals are the primary modality           concludes the paper.
                                         for seizure analysis; however, they are highly non-stationary,
                                         noisy, and strongly patient-dependent, making prediction              The complete source code is publicly available at:
                                         a complex time-series modeling challenge [2]. Public                  github.com/Mahdyy02/gpt-eeg-transformer.
                                         resources such as the CHB-MIT and TUH EEG datasets have
                                         accelerated research while highlighting strong inter-patient                             II. RELATED WORK
                                         variability [3].                                                        Recent advances in EEG analysis have been driven by
                                                                                                               deep learning and self-supervised representation learning,
                                            Early approaches relied on handcrafted temporal and                particularly for seizure-related tasks. It is important, however,
                                         spectral features combined with classical machine learning            to distinguish between seizure events and epilepsy as a
                                         classifiers [4]. While useful, these methods require intensive        chronic disorder. Seizures may result from acute causes

such as fever or trauma, whereas epilepsy is defined by            from continuous clinical recordings and reflects the spatial–
recurrent, unprovoked seizures supported by clinical and EEG       temporal evolution of neural activity across the scalp.
evidence. Several studies leverage self-supervised learning
to improve EEG representations. BioSerenity-E1 employs             Given an input EEG segment X, the model outputs a binary
spectral tokenization and masked prediction to model temporal      prediction:
dependencies in EEG spectrograms [10], achieving strong
results in seizure detection and abnormality classification                                  y ∈ {0, 1}                         (2)
but focusing on event-level analysis rather than prediction.
                                                                   where:
GMAEEG models EEG channels as graph nodes and applies
masked graph autoencoding to learn spatiotemporal dynamics           • y = 1 → A seizure will occur within the next 30 seconds

[11], though its applications remain population-oriented.            • y = 0 → No seizure will occur within this horizon

Masked autoencoder approaches have also been explored;
Zhou and Liu reconstruct randomly masked EEG segments              This formulation casts seizure prediction as a supervised
to learn representations useful for cognitive tasks [12].          binary classification task operating on short temporal horizons.
EEG2Rep further refines masking in latent space using              To construct training labels, EEG recordings are partitioned
semantic subsequence preservation, improving robustness            into two primary states:
across EEG tasks [13]. However, these frameworks remain               • Pre-ictal segments: EEG windows preceding seizure
largely task-agnostic and do not explicitly address patient-            onset within a fixed 30-second prediction horizon.
specific seizure prediction. A common trend across this               • Non-pre-ictal segments: Inter-ictal or background EEG
literature is the use of self-supervised pretraining followed           windows temporally distant from any seizure event.
by task-specific fine-tuning, underlining the importance of
representation learning in EEG analysis [14]. Yet most                This distinction allows the model to learn discriminative
works focus on seizure detection or classification rather          patterns that arise before seizure onset rather than features
than forecasting future seizures. Moreover, evaluations are        of the seizure itself. A patient-specific setting is adopted,
typically population-based, despite strong clinical variability    where each model is trained and evaluated on a single sub-
in seizure signatures. Clinical observations confirm that          ject. This reflects clinical evidence that seizure signatures,
EEG-based prediction is rarely used in practice, partly due        spatial propagation, and spectral characteristics vary signif-
to this heterogeneity. Public datasets such as CHB-MIT and         icantly across individuals, making personalization essential
TUH EEG illustrate the challenge, where seizure activity may       for capturing subject-dependent pre-ictal biomarkers. The 30-
be highly localized to specific channels, especially in focal      second prediction horizon is clinically motivated, balancing
epilepsy.                                                          early warning capability with prediction reliability. Longer
                                                                   horizons introduce uncertainty in pre-ictal boundaries, while
   In contrast, our work targets patient-specific seizure pre-     very short horizons approach seizure detection instead of
diction. By combining transformer architectures with self-         true forecasting. Within this framework, the system learns
supervised learning, we model long-range temporal depen-           patient-specific mappings from multichannel EEG dynamics
dencies and individualized pre-ictal dynamics. This approach       to imminent seizure risk, enabling actionable early warnings
complements existing representation-learning methods while         within clinically meaningful timeframes.
aligning with the clinical reality of epilepsy as a personalized
and recurrent condition.                                           B. Proposed Methodology Overview
                                                                      Figure 1 below illustrates the overall architecture of the
           III. PROPOSED METHODOLOGY                               proposed seizure prediction framework, which is designed as
A. Problem Definition                                              a multi-stage pipeline combining noise-aware preprocessing,
  Epileptic seizure prediction from electroencephalographic        self-supervised representation learning, and task-specific
(EEG) signals is formulated in this work as a patient-specific,    fine-tuning.
short-horizon forecasting problem. The objective is not merely
to detect ongoing seizures, but to anticipate their imminent          The pipeline begins with continuous multichannel scalp
onset by identifying subtle pre-ictal dynamics embedded in         EEG recordings acquired from clinical monitoring sessions.
multichannel brain activity.                                       These raw signals contain rich neurophysiological information
                                                                   but are also affected by various sources of spectral noise
Let the EEG input be defined as:                                   and acquisition artifacts. To ensure that the downstream
                                                                   learning stages focus on meaningful brain dynamics, the
                         X ∈ RC×T                            (1)   raw EEG first undergoes a dedicated preprocessing stage. In
                                                                   the first step, patient EEG recordings are transformed into
denote a segment of scalp EEG, where C represents the              the frequency domain using power spectral density (PSD)
number of recording channels and T the temporal samples            analysis. This transformation enables the identification of
within an observation window. Each segment is extracted            frequency components that exhibit abnormally high power

                                  Preprocessing


   EEG Signal        FFT                Noise               Adaptive                   Clean
   X ∈ RC×T          PSD               Detection             Filter                    EEG


                                                         Tokenization

                                       Tokenize             Quantize                   Z-score
                                     Z = [z1 ...zT ]        L = 512                     Norm


                              Self-Supervised                    Fine-tuning
                              • 4 layers, 4 heads
                                                       weights
                                                                 • Patient-specific
                                                                                                                                   Predict         y = 1:
                              • Embed: 128                       • 30s segments                     Global         Classify
                              • Block: 512                       • Weighted CE
                                                                                                                                      y            Seizure
                              • Next-token                       • LR: 3e−5
                                                                                                     Pool          Softmax
                                                                                                                                                    in 30s
                              LCE + 0.1LM SE                     • 5000 steps


                                        Pre-train                          Fine-tune

Fig. 1: Overall architecture of the proposed patient-specific seizure prediction framework. The pipeline consists of four main
stages: (1) Noise-aware preprocessing using adaptive FFT-based filtering, (2) EEG tokenization with z-score normalization and
quantization into 512 discrete levels, (3) Self-supervised GPT pre-training using next-token prediction with dual loss, and (4)
Patient-specific supervised fine-tuning for 30-second horizon seizure prediction.


combined with low variability across channels. Such spectral                              alarms or intervention systems within actionable timeframes.
patterns typically correspond to uniform noise sources,
including power-line interference and device-related artifacts.                              Overall, the methodology integrates adaptive signal process-
                                                                                          ing with large-scale sequence modeling. By coupling noise-
    Unlike conventional preprocessing pipelines that apply                                aware preprocessing with transformer-based representation
fixed notch filters at predetermined frequencies, the proposed                            learning, the framework aims to maximize sensitivity to pre-
framework performs adaptive noise detection, allowing the                                 ictal dynamics while maintaining robustness to real-world
filtering process to be tailored to each recording session.                               EEG noise conditions.
Once noisy frequency bands are identified, adaptive notch
filtering is applied selectively to remove these components                               C. Noise-Aware EEG Preprocessing
while preserving physiologically relevant EEG rhythms. The                                    Clinical EEG recordings are often contaminated by noise
output of this stage is a filtered EEG signal that retains                                that can mask subtle pre-ictal dynamics. Common artifacts in-
spatial, temporal brain activity while minimizing uniform                                 clude broadband spectral noise, power-line interference (50/60
spectral contamination. Following preprocessing, the cleaned                              Hz), and device-related disturbances from electrodes or am-
EEG signal is used to train a transformer-based foundation                                plifiers. These sources typically appear as high-power, low-
model in a self-supervised manner. At this stage, the model                               variance frequency components shared across channels and
is not yet trained for seizure prediction. Instead, it learns                             can degrade seizure prediction performance if not addressed.
general representations of brain dynamics directly from the                               To mitigate this effect, the preprocessing pipeline incorporates
filtered raw waveform. By modeling long-range temporal                                    automatic noise detection. Power spectral density is used to es-
dependencies across EEG sequences, the transformer develops                               timate frequency energy, while cross-channel variability helps
an intrinsic understanding of normal and abnormal neural                                  distinguish neural activity from uniform noise. Components
patterns without relying on explicit seizure labels. After                                showing both high power and low variance are flagged for
this representation learning phase, the pretrained transformer                            filtering. Instead of applying fixed notch filters, the framework
is fine-tuned for the downstream clinical task. Annotated                                 employs adaptive notch filtering, targeting only the identified
EEG segments are introduced, where each window is                                         contaminated frequencies. This selective approach preserves
labeled according to whether a seizure will occur within the                              physiologically meaningful low-frequency activity critical for
predefined 30-second prediction horizon. A classification head                            pre-ictal pattern recognition. By suppressing uniform spectral
is attached to the pretrained backbone, enabling the network                              artifacts while retaining relevant neural dynamics, the prepro-
to map learned EEG representations to binary seizure risk                                 cessing stage improves EEG signal quality and supports more
decisions. During fine-tuning, the model adapts its internal                              reliable short-horizon seizure forecasting.
features to emphasize pre-ictal biomarkers. Because the
backbone has already learned general EEG structure, the                                   D. Tokenization and EEG Sequence Representation
fine-tuning stage converges more efficiently.                                               To enable transformer-based learning on electroencephalo-
                                                                                          graphic signals, the continuous EEG waveform is reformulated
   The final output of the pipeline is a binary prediction                                as a discrete temporal token sequence. Instead of relying on
indicating imminent seizure risk. This prediction is generated                            handcrafted spectral or statistical features, the proposed ap-
for each EEG segment and can be used to trigger clinical                                  proach models raw neural activity directly at the sample level,

allowing the architecture to learn representations end-to-end          Hyperparameter Summary (Tokenization & Sequence Mod-
from the signal itself. Let X our EEG segment, for sequence         eling): Table I summarizes the key hyperparameters used
modeling, the multichannel recordings are first flattened into      for tokenization and sequence modeling. The quantization
a one-dimensional temporal stream by concatenating all chan-        levels determine the number of discrete amplitude bins, where
nels for each time step in order. Each individual sample is then    higher values preserve waveform precision but increase model
treated as an atomic observation unit to be converted into a        complexity. The block size sets the context window length
token. Because transformers operate on discrete vocabularies,       processed by the transformer, controlling how much temporal
amplitude values must be normalized and quantized prior to          history the model can attend to. Z-score normalization stabi-
tokenization. The raw signal is first standardized using z-score    lizes gradients and training convergence, while the clipping
normalization:                                                      factor limits extreme values to prevent outliers from dominat-
                                                                    ing quantization. Each EEG sample is tokenized individually,
                                 X −µ                               preserving full temporal resolution, and embedded into vectors
                       Xnorm =                                (3)
                                    σ                               of dimension 128. Learned positional embeddings encode
where µ and σ denote the global mean and standard deviation         temporal order for sequence awareness. Gradient accumulation
of the EEG recording. This step removes amplitude scaling           simulates a larger batch size to improve training stability under
differences across sessions and stabilizes training. To limit the   memory constraints. Finally, the dual loss weight balances
influence of extreme outliers, the normalized signal is clipped     waveform reconstruction and encourages physiologically re-
within a bounded interval:                                          alistic outputs.

                Xclip = clip(Xnorm , −kσ, +kσ)               (4)    TABLE I: Hyperparameters for Tokenization and Sequence
                                                                    Modeling
where k is a clipping factor (set to 5 in this work). The clipped
                                                                                  Hyperparameter               Value
values are then linearly mapped into the unit interval:
                                                                                  Quantization Levels (L)      512
                                                                                  Block Size                   512 samples
                            Xclip + kσ                                            Normalization                Z-score
                      X01 =                                (5)
                                2kσ                                               Clipping Factor (k)          5
                                                                                  Token per Sample             1
  This bounded representation is subsequently discretized into                    Embedding Dimension          128
L quantization levels:                                                            Positional Embeddings        Learned
                                                                                  Gradient Accumulation        8 steps
                                                                                  Dual Loss Weight (MSE)       0.1
                  Token = ⌊X01 × (L − 1)⌋                    (6)
where L denotes the vocabulary size (i.e., the number of dis-
                                                                    E. Self-Supervised Transformer Pretraining
crete amplitude bins). Each EEG sample is therefore converted
into a single integer token in the range [0, L − 1]. This design       To learn intrinsic electroencephalographic dynamics prior
establishes a one-token-per-sample representation, enabling         to seizure prediction, a self-supervised pretraining stage is
the EEG waveform to be processed analogously to a language          introduced. This phase aims to model the temporal structure
sequence. Long temporal dependencies can thus be captured           of EEG signals without relying on seizure annotations,
through transformer self-attention without requiring manual         allowing the architecture to acquire generalizable neural
feature engineering. Unlike conventional EEG pipelines that         representations directly from raw brain activity.
rely on spectrograms, wavelets, or band-power statistics, the
proposed tokenization preserves the raw temporal resolution           Following tokenization, the EEG waveform is represented
of the signal. This allows the model to learn both micro-           as a discrete sequence of amplitude tokens:
scale waveform morphology and macro-scale temporal struc-
ture within large context windows. Positional embeddings are                             Z = [z1 , z2 , . . . , zT ]             (7)
added to the token embeddings to encode temporal order-
                                                                    where each token corresponds to a quantized EEG sample.
ing, ensuring that the model distinguishes early from late
                                                                    The transformer is trained using an autoregressive next-sample
samples within each observation window. Consequently, the
                                                                    prediction objective. Given a context window of length B, the
transformer learns joint amplitude–temporal representations
                                                                    model receives:
directly from quantized neural dynamics. To further constrain
reconstruction fidelity, training is guided by a dual-objective
loss combining categorical prediction and waveform regres-                              [zt , zt+1 , . . . , zt+B−1 ]            (8)
sion. In addition to cross-entropy over token classes, a mean-      and learns to predict the subsequent token:
squared error term is computed after dequantizing predicted
token probabilities back into waveform space. This auxiliary                                       zt+B                          (9)
supervision encourages the model to preserve physiologically
meaningful signal morphology rather than only discrete token         These transitions encode neural rhythms, waveform
accuracy.                                                           morphology, and temporal dependencies spanning multiple

physiological time scales.                                         F. Fine-Tuning Strategy
                                                                      Following self-supervised pretraining, the transformer
   The core optimization objective is based on categorical         backbone is adapted to the clinical task of imminent seizure
cross-entropy loss applied to the predicted token distribution.    forecasting through supervised fine-tuning. The objective
Let p̂t denote the predicted probability vector over the vocab-    of this stage is to map learned neural representations to
ulary at time step t, and zt the true token. The primary loss      short-horizon seizure risk, enabling actionable early warning
is defined as:                                                     in real clinical settings.
                              X
                    LCE = −      log p̂t (zt )             (10)      Given a multichannel EEG segment, the model predicts
                                  t
                                                                   whether a seizure will occur within the immediate future. Let:
  Minimizing this objective encourages the transformer to
accurately model discrete amplitude transitions and learn the
                                                                                             X ∈ RC×T                       (15)
generative structure of EEG waveforms.
                                                                   denote a 30-second EEG window, where C represents the
   However, discrete token prediction alone may not guarantee      number of scalp channels and T the number of temporal
faithful reconstruction of the underlying continuous signal. To    samples. After preprocessing and normalization, this segment
preserve waveform fidelity, an auxiliary regression objective      is forwarded through the pretrained transformer encoder to
is introduced. After computing the softmax probabilities, the      obtain a latent representation:
expected quantized amplitude level is estimated as:
                             X                                                         H = Transformer(X)                   (16)
                       êt =     p̂t (k) · k               (11)
                              k                                    where H ∈ RT ×d captures temporal dependencies and
where k indexes quantization levels. This expected level is        cross-channel interactions learned during pretraining.
then dequantized back into waveform space using the inverse
normalization mapping:                                               To perform seizure prediction, a classification head is ap-
                                                                   pended to the backbone. Temporal features are first aggregated
                     x̂t = Dequantize(êt )                (12)    using global average pooling:
   The reconstructed waveform is compared with the ground-                                       1X
truth signal xt using mean squared error:                                                 h̄ =       Ht                     (17)
                                                                                                 T t
                             1X                                       This pooled embedding summarizes the global neural state
                  LMSE =         (x̂t − xt )2              (13)
                             T t                                   of the observation window. It is subsequently passed through
  The final training objective combines discrete and continu-      a feed-forward classification module producing logits:
ous supervision:
                                                                                         ŷ = Classifier(h̄)                (18)
                   Ltotal = LCE + λ · LMSE                 (14)
                                                                     The final output is a probability score:
where λ is a weighting coefficient controlling the contribution
of waveform reconstruction. In our implementation, λ = 0.1.                              p = Softmax(ŷ)                    (19)

   This dual-loss formulation enables the model to learn both      where p ∈ [0, 1]2 encodes the likelihood of imminent seizure
symbolic token transitions and physiologically meaningful          occurrence. A positive label (y = 1) indicates that a seizure
waveform morphology. The pretraining transformer consists          begins within the next 30 seconds, whereas a negative label
of stacked self-attention blocks with learned token and po-        (y = 0) denotes the absence of seizure activity within that
sitional embeddings, allowing latent representations to pre-       prediction horizon.
serve temporal ordering. Through multi-head self-attention,
the model captures long-range EEG dependencies, including             1) Temporal Windowing and Label Construction: Training
oscillatory rhythms, transient events, and pre-ictal trends. To    samples are generated using a sliding-window segmentation
stabilize training on long recordings, signals are processed       strategy applied to continuous EEG recordings. Each 30-
using fixed-length context windows (block size = 512), with        second segment is extracted with 50% overlap to increase
gradient accumulation and mixed-precision training applied to      dataset density and capture transitional neural dynamics.
address GPU memory constraints and accelerate optimization.
Pretraining is conducted in a patient-specific setting, enabling     Let tend denote the end time of a segment. The associated
the transformer to learn individualized neural dynamics and        prediction window is defined as:
develop rich representations that are later specialized for
seizure prediction during supervised fine-tuning.                                        [tend , tend + 30 s]               (20)

   If any clinically annotated seizure onset falls within this       same length, defining the input context and forecast window.
interval, the segment is labeled positive. Otherwise, it is          EEG signals are resampled at 250 Hz, producing sequence
labeled negative. This labeling strategy ensures that the            lengths of 7,500 samples for transformer input. The batch
model learns pre-ictal signatures rather than ictal seizure          size is set to 16, with gradient accumulation over 4 steps
morphology. Clinical annotations are parsed from expert-             to optimize memory usage and maintain training stability. A
reviewed EEG reports, and seizure intervals are merged               learning rate of 3×10−5 is used to prevent catastrophic forget-
across channels to form unified onset windows. This prevents         ting during fine-tuning. The transformer encoder comprises 4
redundant labeling when seizures propagate spatially across          layers with 4 attention heads and embeddings of dimension
electrodes.                                                          128, enabling rich temporal representation. Dropout of 0.2
                                                                     helps reduce overfitting, while the weighted cross-entropy loss
   2) Transfer Learning and Backbone Reuse: Fine-tuning              addresses class imbalance and improves sensitivity. Backbone
leverages the pretrained transformer weights obtained during         freezing can be optionally applied to control feature adap-
the self-supervised stage. Token embeddings and positional           tation, and mixed-precision (FP16) training is enabled for
encodings are transferred directly, while the encoder layers         computational efficiency.
retain learned temporal attention patterns. New components
are introduced to adapt the model to supervised prediction.                    TABLE II: Fine-Tuning Hyperparameters
First, a linear projection maps multichannel EEG inputs into                   Hyperparameter          Value
the embedding dimension. Second, a classification head com-                    Segment Duration        30 s
                                                                               Prediction Horizon      30 s
posed of LayerNorm, GELU activation, dropout regularization,                   Sampling Rate           250 Hz
and fully connected layers produces binary logits. Depending                   Sequence Length         7,500 samples
on the experimental configuration, the transformer backbone                    Batch Size              16
                                                                               Gradient Accumulation   4 steps
may be either frozen (feature extraction mode) or fully train-                 Learning Rate           3 × 10−5
able (end-to-end fine-tuning). In this work, full fine-tuning                  Transformer Layers      4
is adopted to allow seizure-specific adaptation of attention                   Attention Heads         4
                                                                               Embedding Dimension     128
weights. Optimization is performed using weighted cross-                       Dropout                 0.2
entropy loss to address class imbalance between pre-ictal and                  Loss Function           Weighted Cross-Entropy
non-pre-ictal segments:                                                        Backbone Freezing       Optional
                                                                               Mixed Precision         Enabled

          L = −w1 y log(p) − w0 (1 − y) log(1 − p)           (21)
                                                                                  IV. EXPERIMENTAL RESULTS
  where w1 and w0 are inverse-frequency class weights                   This section presents dataset statistics, training behavior,
computed from the training distribution.                             and seizure prediction performance in a patient-specific set-
                                                                     ting, where each model is trained and evaluated on a single
   3) Patient-Specific Training Paradigm: A strictly patient-        subject. These experiments are designed as a proof-of-concept
specific training strategy is employed throughout this study.        rather than a large population study. The goal is to show
Models are trained and evaluated independently for each              that the proposed framework, combining self-supervised pre-
subject using only their own EEG recordings. No cross-               training and patient-specific fine-tuning, can work effectively
patient data mixing or transfer is performed during supervised       on EEG data. Self-supervised pretraining was conducted for
learning. This design prevents information leakage and               5,000 epochs, followed by supervised fine-tuning for 5,000
ensures that reported performance reflects realistic clinical        optimization steps. We report per-patient results to reflect
deployment conditions. The rationale for patient-specific            the strong variability between individuals in EEG signals. We
modeling is grounded in neurophysiological variability.              present dataset characteristics, training curves, and prediction
Seizure onset patterns differ substantially across individuals       results, along with representative alarm timelines.
in terms of spectral content, spatial propagation pathways,
and pre-ictal duration. Population-level models often fail to        A. Dataset characteristics
capture these idiosyncratic biomarkers, leading to degraded             Table III, Table IV, and Table V summarize the recordings
prediction reliability. By contrast, patient-specific transformers   used in our experiments. The tables report the number of
learn subject-dependent neural signatures, enabling more             sessions per patient, total recording hours, annotated seizure
precise anticipation of seizure transitions. This paradigm also      counts, number of 30-second segments generated (50% overlap
aligns with clinical practice, where prediction systems are          for training split generation or 75% overlap for inference),
calibrated per patient following individualized monitoring           fraction of segments labeled pre-ictal, the sampling frequency
sessions.                                                            used after resampling, and the standardized channel count for
                                                                     each patient. The table shows heterogeneity in data volume and
  4) Fine-Tuning Hyperparameters: Table II lists the fine-           class balance across patients. Some folders contained only a
tuning hyperparameters used for seizure prediction. Each EEG         few sessions and few seizures, while others (e.g., s005_2006
segment spans 30 seconds, with a prediction horizon of the           and s002_2004) include more annotated events and a larger

proportion of pre-ictal segments. This variability motivates the
patient-specific training strategy described in Section III-A.
B. Training behaviour and convergence
   All pretraining and fine-tuning runs used the transformer
backbone described in Section III-F. Figure 2 displays the
training and validation curves (loss and accuracy) for the
three main experimental runs. Curves show rapid decrease of
training loss and steady validation performance after a few
hundred to a few thousand steps.                                                         (a) Patient aaaaaaac


                     (a) Patient aaaaaaac
                                                                                         (b) Patient aaaaabnn


                     (b) Patient aaaaabnn


                                                                                         (c) Patient aaaaadpj
                                                                    Fig. 3: Representative alarm timeline and confidence curve
                                                                    – Top: binary alarms (red) vs non-alarm (green) over time
                                                                    with ground-truth seizure windows highlighted in orange.
                                                                    Bottom: model seizure probability (confidence) over the same
                                                                    recording. Vertical axis shows probability in [0,1]; dashed line
                     (c) Patient aaaaadpj
                                                                    indicates decision threshold.
Fig. 2: Training convergence — Training and validation
loss/accuracy curves for three patient-specific fine-tuning runs.
Both pretraining and fine-tuning were run for 5,000 steps;
                                                                    0.94–0.97) and robust F1 scores (0.82–0.91), while detecting
gradient accumulation and mixed precision were used to
                                                                    all seizure events. False alarm rates varied across subjects,
maximize effective batch size.
                                                                    remaining very low for two patients and higher for the
                                                                    third. This is partly due to the short prediction horizon and
C. Seizure-prediction performance and alarm behaviour               the overlapping evaluation windows, which increase temporal
   Continuous recordings were segmented into overlapping 30-        resolution but can produce multiple alarms for the same
second windows (75% overlap during inference), producing a          preictal transition. Prediction delays ranged from a few sec-
time series of seizure probabilities and binary alarms (thresh-     onds up to 30 seconds, reflecting the constraints of short
old = 0.5). Representative prediction timelines are shown in        recording durations. It should be emphasized that this study
Figure 3.                                                           was designed as a proof-of-concept demonstration rather than
                                                                    a benchmark comparison. No baseline models were included;
D. Discussion                                                       the focus is on evaluating the feasibility of a self-supervised
   The experimental results indicate that our proposed frame-       pretrained transformer that can adapt to individual patient
work can effectively capture short-term predictive patterns         dynamics and provide a flexible foundation for EEG-based
in EEG signals, even with substantial inter-patient variability     predictions. Despite the small cohort and limited data, these
and limited annotated pre-ictal segments. Across the three pa-      results suggest that transformer-based models are capable
tients, the model achieved high validation accuracies (around       of learning complex temporal dependencies in EEG signals

                                            TABLE III: Dataset summary for patient aaaaaaac
            Patient aaaaaaac     Sessions     Recording Hours     Seizures    Segments      Pre-ictal %     Sampling Freq (Hz)        Channels
            s001 2002               2               0.15              2          29            89.66               250                  33
            s002 2002               1               0.07              1          14            92.86               250                  33
            s004 2002               2               0.26              0          56             0.0                250                  33
            s005 2002               4               0.35              0          71             0.0                250                  33

                                            TABLE IV: Dataset summary for patient aaaaabnn
           patient aaaaabnn      Sessions     Recording Hours     Seizures    Segments      Pre-ictal %     Sampling Freq (Hz)        Channels
           s001 2004                1               0.33              0          75             0.0                250                   33
           s002 2004                6               0.35              4          68            54.41               250                  128
           s003 2004                2               0.25              0          53             0.0                250                   32
           s004 2004                4               0.35              0          70             0.0                250                   32

                                            TABLE V: Dataset summary for patient aaaaadpj
            Patient aaaaadpj     Sessions     Recording Hours     Seizures    Segments      Pre-ictal %     Sampling Freq (Hz)        Channels
            s003 2006               1               0.37              0          84             0.0                250                  41
            s005 2006               6               0.42              7          81            27.16               250                  32

                                        TABLE VI: Patient-specific seizure prediction performance
                      Patient     Train Acc     Val Acc     Precision    Recall      F1      FAR (h-1 )    Pdelay (s)     Sens. (%)
                      aaaaaaac     1.0000        0.9706      1.0000      0.8333    0.9091       0.00          6.89          100.0
                      aaaaabnn     1.0000        0.9444      0.8750      0.7778    0.8235      0.00          12.55          100.0
                      aaaaadpj     1.0000        0.9394      0.7500      1.0000    0.8571      13.82         30.00          100.0


and delivering clinically meaningful short-horizon forecasts.                  [3] R. Mourad, A. Diab, Z. Merhi, M. Khalil, and R. L. B. Jeannès,
The observations motivate further studies on larger datasets                       “Machine and deep learning methods for epileptic seizure recognition
                                                                                   using eeg data: A systematic review,” Brain research, vol. 1864, p.
with longer pre-ictal recordings, as well as strategies such                       149797, 2025.
as threshold tuning and temporal aggregation to reduce false                   [4] S. M. Usman, M. Usman, and S. Fong, “Epileptic seizures prediction
alarms without compromising early detection performance.                           using machine learning methods,” Computational and mathematical
                                                                                   methods in medicine, vol. 2017, no. 1, p. 9074759, 2017.
                                                                               [5] R. Hussein, S. Lee, R. Ward, and M. J. McKeown, “Epileptic seizure
                        V. CONCLUSION                                              prediction: A semi-dilated convolutional neural network architecture,”
                                                                                   in 2020 25th International Conference on Pattern Recognition (ICPR).
   Epileptic seizures remain highly unpredictable, posing a ma-                    IEEE, 2021, pp. 5436–5443.
                                                                               [6] X. Wu, Z. Yang, T. Zhang, L. Zhang, and L. Qiao, “An end-to-end
jor burden for patients. This work shows that seizure onset can                    seizure prediction approach using long short-term memory network,”
be anticipated by modeling EEG signals as structured temporal                      Frontiers in Human Neuroscience, vol. 17, p. 1187794, 2023.
sequences rather than noisy recordings. Using transformer-                     [7] G. Zerveas, S. Jayaraman, D. Patel, A. Bhamidipaty, and C. Eickhoff, “A
                                                                                   transformer-based framework for multivariate time series representation
based architectures, the proposed patient-specific framework                       learning,” in Proceedings of the 27th ACM SIGKDD conference on
combines self-supervised pretraining with individualized fine-                     knowledge discovery & data mining, 2021, pp. 2114–2124.
tuning, enabling the model to learn general brain dynamics                     [8] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez,
                                                                                   Ł. Kaiser, and I. Polosukhin, “Attention is all you need,” Advances in
before specializing in patient-dependent pre-ictal patterns. This                  neural information processing systems, vol. 30, 2017.
strategy achieved validation accuracies above 90% and F1                       [9] J. Zhang, S. Zheng, W. Chen, G. Du, Q. Fu, and H. Jiang, “A scheme
scores exceeding 0.80 across subjects. Beyond quantitative                         combining feature fusion and hybrid deep learning models for epileptic
                                                                                   seizure detection and prediction,” Scientific Reports, vol. 14, no. 1, p.
performance, results indicate that transformers effectively cap-                   16916, 2024.
ture long-range temporal dependencies preceding seizures,                     [10] R. G. Bettinardi, M. Rahmouni, and U. Gimenez, “Bioserenity-e1: a
generating probability trajectories and alarms within a 30-                        self-supervised eeg model for medical applications,” arXiv preprint
                                                                                   arXiv:2503.10362, 2025.
second prediction horizon. Such capability supports a shift                   [11] Z. Fu, H. Zhu, Y. Zhao, R. Huan, Y. Zhang, S. Chen, and Y. Pan,
from reactive seizure detection to proactive risk mitigation.                      “Gmaeeg: A self-supervised graph masked autoencoder for eeg repre-
Future work should focus on large-scale validation, optimizing                     sentation learning,” IEEE Journal of Biomedical and Health Informatics,
                                                                                   vol. 28, no. 11, pp. 6486–6497, 2024.
the sensitivity–false alarm trade-off, and integrating wearable               [12] Y. Zhou and S. Liu, “Enhancing representation learning of eeg data
EEG systems for real-time monitoring.                                              with masked autoencoders,” in International Conference on Human-
                                                                                   Computer Interaction. Springer, 2024, pp. 88–100.
                                                                              [13] N. Mohammadi Foumani, G. Mackellar, S. Ghane, S. Irtza, N. Nguyen,
                             R EFERENCES                                           and M. Salehi, “Eeg2rep: enhancing self-supervised eeg representation
                                                                                   through informative masked inputs,” in Proceedings of the 30th ACM
 [1] World Health Organization, “Epilepsy: Key facts,” https://www.who.int/        SIGKDD Conference on Knowledge Discovery and Data Mining, 2024,
     news-room/fact-sheets/detail/epilepsy, 2024, accessed: Feb. 2025.             pp. 5544–5555.
 [2] X. Zhang, X. Zhang, Q. Huang, and F. Chen, “A review of epilepsy         [14] W. Weng, Y. Gu, S. Guo, Y. Ma, Z. Yang, Y. Liu, and Y. Chen, “Self-
     detection and prediction methods based on eeg signal processing and           supervised learning for electroencephalogram: A systematic survey,”
     deep learning,” Frontiers in Neuroscience, vol. 18, p. 1468967, 2024.         ACM Computing Surveys, vol. 57, no. 12, pp. 1–38, 2025.
```
