---
citation_key: "PhamTran2026"
paper_id: "paper_202"
title: "EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and Neural Memory"
authors: "Tien-Dat Pham; Xuan-The Tran"
year: 2026
doi: ""
source: "arxiv (2601.13748)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2601.13748"
tier: 1
composite: 4.5
---

# EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and Neural Memory

**Citation:** `PhamTran2026` · **Tier:** 1 · **Composite:** 4.5

**Source PDF:** `full_pdf/Tien2026.pdf`

## Abstract

ings during the pre-ictal period (typically 5–30 minutes be- arXiv:2601.13748v1 [cs.LG] 20 Jan 2026 fore seizure onset) is widely regarded as a key clinical objec- Accurate epileptic seizure prediction from elec- tive in epilepsy management Mormann et al. [2007]. Such a troencephalography (EEG) remains challenging system could enable patients to seek a safer environment and because pre-ictal dynamics may span long time support timely interventions, including medication adminis- horizons while clinically relevant signatures can be tration, when appropriate Cook et al. [2013]. subtle and transient. Many deep learning models Despite decades of progress, forecasting seizures from face a persistent trade-off between capturing local EEG remains exceptionally challenging. In contrast to the spatiotemporal patterns and maintaining informa- pronounced morphological signatures observed during ictal tive long-range context when operating on ultra- events, pre-ictal biomarkers are often subtle, non-stationary, long sequences. We propose EEG-Titans, a dual- and may evolve gradually over extended durations Truong et branch architecture that incorporates a modern neu- al. [2018]. This characteristic implies that effective mod- ral memory mechanism for long-context model- els must capture and integrate information across long time ing. The model combines sliding-window atten- horizons, i.e., long-term dependencies, rather than relying tion to capture short-term anomalies with a recur- solely on local patterns Hochreiter and Schmidhuber [1997]. rent memory pathway that summarizes slower, pro- Over the past decade, deep learning has achieved notable ad- gressive trends over time. On the CHB-MIT scalp vances in seizure prediction; however, widely used architec- EEG dataset, evaluated under a chronological hold- tures still face fundamental limitations in jointly modeling out protocol, EEG-Titans achieves 99.46% aver- local discriminative features and long-range temporal con- age segme

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
EEG-Titans: Long-Horizon Seizure Forecasting via Dual-Branch Attention and
                                                                         Neural Memory

                                                                              Tien-Dat Pham1 , Xuan-The Tran2∗
                                                               HAI-Smartlink Research Lab, Anchi STE Company, Haiphong, Vietnam
                                                        School of Mechanical Engineering, Vietnam Maritime University, Haiphong, Vietnam †


                                                                     Abstract                                    ings during the pre-ictal period (typically 5–30 minutes be-


arXiv:2601.13748v1 [cs.LG] 20 Jan 2026
                                                                                                                 fore seizure onset) is widely regarded as a key clinical objec-
                                                 Accurate epileptic seizure prediction from elec-                tive in epilepsy management Mormann et al. [2007]. Such a
                                                 troencephalography (EEG) remains challenging                    system could enable patients to seek a safer environment and
                                                 because pre-ictal dynamics may span long time                   support timely interventions, including medication adminis-
                                                 horizons while clinically relevant signatures can be            tration, when appropriate Cook et al. [2013].
                                                 subtle and transient. Many deep learning models                    Despite decades of progress, forecasting seizures from
                                                 face a persistent trade-off between capturing local             EEG remains exceptionally challenging. In contrast to the
                                                 spatiotemporal patterns and maintaining informa-                pronounced morphological signatures observed during ictal
                                                 tive long-range context when operating on ultra-                events, pre-ictal biomarkers are often subtle, non-stationary,
                                                 long sequences. We propose EEG-Titans, a dual-                  and may evolve gradually over extended durations Truong et
                                                 branch architecture that incorporates a modern neu-             al. [2018]. This characteristic implies that effective mod-
                                                 ral memory mechanism for long-context model-                    els must capture and integrate information across long time
                                                 ing. The model combines sliding-window atten-                   horizons, i.e., long-term dependencies, rather than relying
                                                 tion to capture short-term anomalies with a recur-              solely on local patterns Hochreiter and Schmidhuber [1997].
                                                 rent memory pathway that summarizes slower, pro-                Over the past decade, deep learning has achieved notable ad-
                                                 gressive trends over time. On the CHB-MIT scalp                 vances in seizure prediction; however, widely used architec-
                                                 EEG dataset, evaluated under a chronological hold-              tures still face fundamental limitations in jointly modeling
                                                 out protocol, EEG-Titans achieves 99.46% aver-                  local discriminative features and long-range temporal con-
                                                 age segment-level sensitivity across 18 subjects.               text under practical computational constraints. Convolutional
                                                 We further analyze safety-first operating points on             neural networks (CNNs) excel at extracting local morphol-
                                                 artifact-prone recordings and show that a hierarchi-            ogy (e.g., spikes and sharp waves) but are inherently con-
                                                 cal context strategy extending the receptive field              strained in representing long-term temporal structure due to
                                                 for high-noise subjects can markedly reduce false               limited receptive fields Truong et al. [2018]. Recurrent archi-
                                                 alarms (down to 0.00 FPR/h in an extreme outlier)               tectures such as LSTMs are designed for sequential modeling,
                                                 without sacrificing sensitivity. These results indi-            yet in practice they can struggle to preserve informative con-
                                                 cate that memory-augmented long-context model-                  text over very long sequences, which may lead to degraded
                                                 ing can provide robust seizure forecasting under                performance when pre-ictal dynamics span thousands of time
                                                 clinically constrained evaluation.                              steps Hochreiter and Schmidhuber [1997]. Transformer-
                                                                                                                 based self-attention alleviates the global-context bottleneck,
                                                                                                                 but its quadratic complexity O(N 2 ) becomes prohibitive for
                                         1       Introduction                                                    long observation windows and resource-constrained settings
                                         Epilepsy is among the most prevalent chronic neurological               such as wearable devices Vaswani et al. [2017]; Hussein et
                                         disorders, affecting approximately 50 million people world-             al. [2022].
                                         wide World Health Organization [2019]; Fiest et al. [2017].                Motivated by these challenges and inspired by Titans, a re-
                                         The stochastic and unpredictable nature of seizures not only            cent advance in long-context modeling via test-time memory
                                         increases the risk of physical injury but also imposes a per-           mechanisms Behrouz et al. [2024], we propose EEG-Titans, a
                                         sistent psychological burden, substantially reducing patients’          specialized framework for seizure prediction. The main con-
                                         quality of life Mormann et al. [2007]. Accordingly, develop-            tributions of this work are summarized as follows:
                                         ing an accurate forecasting system that can issue early warn-
                                                                                                                   • Dual-branch architecture with neural memory: We
                                             ∗
                                               Corresponding Author                                                  propose a dual-stream design in which one branch em-
                                             †
                                               Preprint notice: This work has been submitted for possible pub-       phasizes instantaneous anomalies, while the other incor-
                                         lication. Copyright may be transferred without notice, after which          porates a neural memory module to accumulate and up-
                                         this version may no longer be accessible.                                   date latent brain states over time. This enables modeling

      long-term pre-ictal evolution with substantially lower       not provide at least two valid seizure clusters necessary for
      computational overhead than applying full self-attention     splitting the first N −1 clusters for training and the final clus-
      over long sequences.                                         ter for testing; or if their summary files lacked reliable time-
    • Safety-first, causal evaluation protocol: We adopt           line metadata needed to define pre-ictal windows and safety
      a safety-first perspective that prioritizes high sensitiv-   margins.
      ity and avoids retrospective protocols that may weaken          Applying these criteria, 6 subjects were removed from the
      temporal causality. Concretely, we replace commonly          original cohort. CHB12 was excluded due to marked montage
      used leave-one-out cross-validation with a chronological     heterogeneity relative to the standard 10–20 configuration,
      hold-out strategy that preserves temporal order between      which would undermine spatial feature alignment. CHB24
      training and testing data.                                   was excluded because the timing information required to es-
                                                                   tablish the pre-ictal window and safety margins was not avail-
    • Transparent outlier and failure-mode analysis: Be-           able. In addition, CHB11, CHB17, CHB19, and CHB23 were
      yond reporting peak performance, we provide an ex-           excluded because they did not contain a sufficient number of
      plicit analysis of challenging cases, including artifact-    seizure clusters to support the proposed chronological train–
      heavy recordings and pediatric subjects. This clarifies      test split. The final study cohort therefore comprises 18 sub-
      the trade-off between long-context memory capacity and       jects. The sampling rate for all recordings was 256 Hz, which
      noise sensitivity, and motivates future directions toward    we retain throughout to ensure spectral consistency.
      personalized forecasting systems.
                                                                   Table 1: Statistics of selected CHB-MIT subjects Shoeb [2009].
2     Methodology                                                  Bold values indicate seizures excluded due to artifacts or insuffi-
                                                                   cient pre-ictal margins.
2.1    Dataset and Preprocessing
Dataset Description and Subject Selection                                                Original      Selected     Duration
                                                                          Subject ID
This study uses the CHB-MIT Scalp EEG database, a                                        Seizures      Seizures     (Hours)
widely used benchmark for seizure prediction research Shoeb               CHB01               7            7          40.55
[2009]. The recordings were collected at Boston Chil-                     CHB02               3            3          35.30
dren’s Hospital and are publicly distributed through Phys-
                                                                          CHB03               7            7          38.00
ioNet (Massachusetts Institute of Technology). The dataset
contains long-term EEG recordings from 24 pediatric sub-                  CHB04               4            4         155.90
jects (chb01–chb23; chb21 and chb01 correspond to the same                CHB05               5            5          39.00
individual recorded approximately 1.5 years apart) Shoeb                  CHB06              10           10          66.70
[2009]. Subjects (5 males, 17 females; age range 1.5–19                   CHB07               3            3          68.10
years) were diagnosed with intractable epilepsy and under-                CHB08               5            5          20.00
went inpatient video-EEG monitoring for pre-surgical assess-              CHB09               4            4          67.80
ment. Anti-epileptic drugs were reduced or withdrawn during               CHB10               7            7          50.00
monitoring to increase the likelihood of capturing seizures for           CHB13              12           11          33.00
clinical evaluation.                                                      CHB14               8            8          26.00
   CHB-MIT includes over 980 hours of continuous EEG
                                                                          CHB15              20           17          40.00
and 198 seizure events annotated by clinical experts Shoeb
[2009], providing sufficient scale for training models that               CHB16              10            9          19.00
require extended temporal context. EEG was recorded at                    CHB18               6            6          36.00
256 Hz with 16-bit resolution, preserving activity across stan-           CHB20               8            8          29.00
dard physiological bands. Recordings follow the interna-                  CHB21               4            4          33.00
tional 10–20 electrode placement system; however, the num-                CHB22               3            3          31.00
ber of channels varies across subjects (typically 23–26). To
ensure a fixed input dimensionality and consistent spatial
alignment, we restrict analysis to 18 bipolar channels that        Seizure Clustering and Labeling Strategy
are common across all subjects, following established prac-        As illustrated in Fig. 1, seizures in long-term monitoring of-
tice in prior work Truong et al. [2018]. Data are provided         ten occur in temporal clusters. Forecasting seizures that oc-
as .edf files, typically segmented into approximately one-         cur shortly after a preceding event offers limited practical
hour recordings, and are freely available for research use via     value and can confound labeling due to overlapping peri-ictal
PhysioNet.                                                         effects. Following the seizure clustering strategy in prior
   To satisfy the requirements of our sequential simulation        work Truong et al. [2018], we group seizures separated by
strategy and maintain strict input consistency, we applied         less than 30 minutes into a single cluster, and define the onset
a screening procedure to exclude subjects that do not sup-         of the lead seizure as the reference time for label construction.
port reliable chronological evaluation or standardized channel        Specifically, the pre-ictal phase (Label 1) is defined as the
configurations. Specifically, subjects were excluded if their      interval from 35 to 5 minutes prior to the onset of the lead
recordings exhibited substantial montage changes or lacked         seizure (Fig. 1). The final 5 minutes before onset corre-
channels required for the fixed 18-channel input; if they did      spond to the Seizure Prediction Horizon (SPH) Mormann et

al. [2007] and are excluded from training to emulate a clin-         architecture can be viewed as a trainable approximation of
ically realistic buffer time for warning and response. The           classical pipelines such as Filter Bank Common Spatial Pat-
inter-ictal phase (Label 0) represents baseline EEG far from         terns (FBCSP), enabling end-to-end learning of spatial pro-
seizure activity. To reduce contamination by post-ictal effects      jections and band-specific activity without manual feature en-
and potential early physiological drifts near seizure onset, we      gineering.
enforce a safety margin of 1.5 hours around each seizure clus-          Technical details: Let an input EEG segment be X ∈
ter Bandarabadi et al. [2015]. Specifically, all EEG within 1.5      RC×T , where C is the number of channels and T is the num-
hours before and after a cluster is discarded, yielding a con-       ber of time samples. The tokenizer is implemented as a se-
servative inter-ictal set intended to minimize label leakage.        quence of transformations that parallels common EEG pro-
Signal Processing and Data Augmentation                              cessing steps:
Raw EEG is notch-filtered at 60 Hz to attenuate power-line             • Temporal convolution: A temporal convolution ex-
interference, and then band-pass filtered from 0.5 to 100 Hz             tracts frequency-related patterns using a kernel of size
to retain physiologically relevant activity. Continuous record-          (1, Kt ) with Kt = 40. With sampling rate fs = 256 Hz,
ings are segmented into 5-second windows (1280 samples).                 this corresponds to a temporal window of approximately
Given the pronounced class imbalance in seizure forecast-                156 ms. This layer can be interpreted as a learnable tem-
ing, we adopt a differential windowing strategy inspired by              poral filtering stage:
prior work Tsiouris et al. [2018]. Inter-ictal segments are ex-
tracted using non-overlapping windows to limit redundancy                              Ztemp = X ∗ Wtemp + btemp ,              (1)
and computational overhead. For pre-ictal segments, we ap-
ply a targeted overlap strategy during training, using 50%                where Wtemp denotes the temporal filter weights. The
overlap between adjacent windows to increase the number                   relatively large kernel supports capturing low-frequency
of positive samples and improve exposure to rare pre-ictal                rhythms that are often relevant to pre-ictal dynam-
patterns. In validation and testing, we use strictly non-                 ics Mormann et al. [2007].
overlapping windows for both classes to ensure a conserva-
                                                                       • Spatial convolution: The temporal features are then
tive and realistic evaluation and to prevent artificially inflated
                                                                         projected across channels using a spatial convolution
performance due to near-duplicate samples.
                                                                         with kernel size (C, 1), producing a set of learned spatial
2.2   EEG-Titans Architecture                                            mixtures (virtual channels):
This section describes EEG-Titans, a deep learning frame-                                         C
work designed for epileptic seizure prediction from multi-                                (j)            (i)         (i,j)
                                                                                                  X
                                                                                        Zspat =         Ztemp · Wspat .         (2)
channel scalp EEG. As illustrated in Fig. 2, the model consists                                   i=1
of two main stages: a spatial feature extraction and tokeniza-
tion module, followed by a long-context temporal backbone                 This operation is analogous to learning spatial projec-
with neural memory, and a final classification head that out-             tion matrices as in CSP-based approaches, emphasizing
puts a seizure probability.                                               informative channel combinations while suppressing ir-
   EEG-Titans operates as a sequential pipeline that maps raw             relevant activity Schirrmeister et al. [2017].
EEG segments to seizure probabilities:
                                                                       • Log-variance activation (square and log-pooling):
   • Input: Multi-channel EEG segments are partitioned into              Unlike conventional CNNs that use ReLU, ShallowCon-
     fixed-length sub-windows to form the input stream.                  vNet employs a nonlinearity designed to approximate
   • Spatial Tokenizer (ShallowConvNet): A task-specific                 signal power. The sequence includes squaring, average
     feature extractor that learns spatial and spectral filters          pooling over a window of length W , and logarithmic
     and encodes each sub-window into a sequence of feature              compression:
     tokens Schirrmeister et al. [2017].                                                                     !
                                                                                                        W
   • Temporal Backbone (Titans): A neural-memory-                                                   1 X 2
                                                                                       f (x) = log         xk .            (3)
     based sequence model that integrates short-range                                              W
                                                                                                               k=1
     and long-range temporal context over the token se-
     quence Behrouz et al. [2024].                                        This yields a log-power representation, which is closely
   • Output: A classification layer produces the predicted                related to spectral power features commonly used in
     seizure probability for each time step (or window) in the            EEG analysis and seizure prediction Bandarabadi et al.
     sequence.                                                            [2015]. The logarithm also stabilizes variance and miti-
                                                                          gates dynamic-range effects.
Spatial Tokenizer - ShallowConvNet
We adopt ShallowConvNet as the spatial tokenizer because               • Tokenization: The resulting features are projected to
EEG signals are characterized by oscillatory activity dis-               the model dimension dmodel using a 1 × 1 convolution
tributed across a structured sensor topology Schirrmeister et            (Conv1d). The output is then arranged as a sequence of
al. [2017]. In contrast to deep CNN backbones originally op-             latent vectors (tokens), each representing the estimated
timized for static images, ShallowConvNet is explicitly de-              brain state over a short sub-interval, and passed to the
signed to capture spectral–spatial patterns. Conceptually, this          temporal backbone.

Figure 1: Schematic of the seizure prediction protocol. The pre-ictal interval (Label 1) is defined as a 30-minute window prior to seizure
onset and is separated from onset by a 5-minute Seizure Prediction Horizon (SPH). A 1.5-hour safety margin is removed between inter-ictal
(Label 0) and seizure-related periods to reduce label leakage and contamination.


MAG Temporal Backbone                                                  MAG Block At each time step t, MAG computes two
After spatial tokenization, the feature sequence X =                   complementary representations and fuses them via a data-
{x1 , x2 , . . . , xT } is processed by the temporal backbone. We      dependent gate:
use the Titans architecture, specifically the Memory-as-a-                • Local branch (causal sliding-window attention): The
Gate (MAG) variant, to combine efficient long-term memory                   local branch models short-range dependencies using at-
with local attention-based modeling Behrouz et al. [2024].                  tention restricted to a causal neighborhood Nt . To
Rationale Seizure forecasting requires modeling both tran-                  enforce autoregressive processing (no access to future
sient anomalies and longer-term pre-ictal evolution. Standard               steps), a causal mask M ∈ RS×S is applied:
Transformers capture rich local interactions but are costly for                                    
long sequences due to the quadratic self-attention complex-                                          0     if j ≤ i,
                                                                                             Mij =                             (5)
ity O(N 2 ) Vaswani et al. [2017]. Recurrent models such                                             −∞ if j > i.
as LSTMs have linear complexity O(N ) and are suitable for
streaming settings, yet their effective ability to retain and re-           The attention output is:
trieve information can degrade over very long horizons, mak-                                                  ⊤
                                                                                                                         !
ing it difficult to link early pre-ictal changes to later seizure                     (t)                 Qt KN
                                                                                     zattn = Softmax       √ t +M            VNt .    (6)
onset Hochreiter and Schmidhuber [1997]. Titans addresses                                                    dk
this trade-off by augmenting attention with a compact neu-
ral memory that can store long-range information with fixed                 This formulation prevents information leakage from fu-
per-step computation Behrouz et al. [2024].                                 ture time steps during sequential simulation.
Neural Memory Module The neural memory maintains a                        • Global branch (neural memory): In parallel, the
persistent latent state ht updated at each time step via an                 global branch summarizes long-range context through
adaptive decay mechanism Behrouz et al. [2024]:                             the updated memory state ht (Eq. 4) and a linear pro-
            ht = σ(θ) ⊙ ht−1 + (1 − σ(θ)) ⊙ K(xt ),            (4)          jection:
                                                                                           (t)
                        dmodel                                                           zmem  = Wmem ht + bmem ,             (7)
where ht−1 ∈ R                 is the previous memory state, xt is
the current token, ⊙ denotes element-wise multiplication, and               where Wmem and bmem are trainable parameters. This
σ(θ) is a learnable decay gate with parameters θ ∈ Rdmodel .                representation is intended to capture slowly varying
Compared to fixed-rate exponential moving averages, the                     background context over extended periods.
learnable θ allows the model to adjust retention per fea-                 • Soft gating fusion: The two branches are fused using a
ture dimension, which can help attenuate transient artifacts                learned gate:
while preserving informative pre-ictal trends over long hori-
zons Mormann et al. [2007].                                                              gt = σ(Wg [zattn ∥ zmem ] + bg ) ,           (8)

Figure 2: Overall architecture of EEG-Titans. Raw multi-channel EEG is processed by (1) a Spatial Tokenizer based on ShallowConvNet
to extract spectro-spatial features and produce a token sequence; (2) a Temporal Backbone based on Titans (Memory-as-a-Gate) to model
long-term dependencies via complementary local (attention) and global (memory) pathways; and (3) a classification head that outputs the
seizure probability P (t).


      where [ · ∥ · ] denotes concatenation. The fused output           • Patient-specific threshold selection: Because EEG
      is:                                                                 amplitude distributions and baseline activity differ sub-
                yt = gt ⊙ zattn + (1 − gt ) ⊙ zmem .      (9)             stantially across subjects, a single global threshold is
                                                                          often suboptimal. We therefore select τ separately for
      This gating mechanism allows the model to adaptively                each subject by grid search on the validation set over
      balance short-term patterns and long-term context de-               τ ∈ [0.10, 0.95] with step size 0.05. The selected τ max-
      pending on the current signal characteristics.                      imizes sensitivity while keeping the false-positive rate
                                                                          within acceptable limits.
Classification Head
The final representation produced by the Titans backbone is             • Refractory period: To prevent repeated alarms trig-
passed to a linear classification layer to yield p ∈ [0, 1], rep-         gered by a single prolonged event or artifact, we enforce
resenting the predicted probability of an upcoming seizure                a 30-minute refractory period Mormann et al. [2007].
within the target horizon.                                                After an alarm occurs, subsequent threshold crossings
                                                                          within the next 30 minutes are ignored. This constraint
2.3    Post-processing and Evaluation Strategy                            ensures that a single episode contributes at most one
                                                                          alarm event, reducing redundant alerts and preventing
Soft Fusion Top-K and Decision Rule                                       inflation of false-positive counts.
To improve prediction stability in the presence of transient ar-
                                                                     Evaluation Strategy: Sensitivity-Oriented Validation
tifacts, we adopt a window-based soft decision scheme rather
than applying an instantaneous hard threshold to each seg-           Many seizure prediction studies optimize a balance between
ment Lu et al. [2023].                                               sensitivity and false-positive rate using composite criteria
   Let PW = {pt−W +1 , . . . , pt } denote the set of predicted      (e.g., AUC or Youden index). In contrast, we adopt a
probabilities within a sliding window of length W ending at          sensitivity-oriented evaluation aligned with safety-first clini-
time step t. We compute an alarm score St as the mean of the         cal use. Specifically, we treat high sensitivity as a prerequisite
K largest probabilities within PW :                                  and then minimize false positives subject to that requirement.
                                                                        • Sensitivity as a primary requirement: Rather than op-
                          1       X
                   St =                      p.             (10)          timizing sensitivity and false positives symmetrically,
                          K                                               we aim to operate near maximal sensitivity and reduce
                              p∈top-K(PW )
                                                                          the false-positive rate under this constraint. This for-
An alarm is triggered when St > τ . Two additional mecha-                 mulation reflects the practical cost of missed seizures
nisms are used to support clinical practicality and reduce spu-           in safety-critical settings and discourages improvements
rious alerts.                                                             driven primarily by conservative thresholding.

Figure 3: Titans: Memory-as-a-Gate (MAG) module. The module combines a local branch (causal sliding-window attention) that captures
short-range patterns and a global branch (neural memory) that maintains long-range context. A learnable gate gt fuses the two representations
into a context-aware output.


   • Assessment of long-context utilization: Operating at                      Here, T Pseg denotes the number of segments within
     very high sensitivity typically increases susceptibility to               the pre-ictal interval correctly classified as pre-ictal, and
     noise, which often manifests as elevated false-positive                   F Nseg denotes the number of pre-ictal segments mis-
     rates. If EEG-Titans maintains a low false-positive rate                  classified as inter-ictal. High segment-based sensitivity
     at such operating points, it provides supporting evidence                 indicates sustained warning coverage rather than spo-
     that the neural memory branch contributes meaning-                        radic detections.
     ful long-term context, enabling the model to differen-                  • False positive rate per hour (FPR/h): We measure us-
     tiate progressive pre-ictal evolution from transient back-                ability using the false positive rate per hour, computed
     ground fluctuations, rather than achieving performance                    over inter-ictal data:
     mainly via threshold tuning.
                                                                                                                 NFP
Quantitative Metrics                                                                              FPR/h =                  ,            (12)
                                                                                                              Tinter-ictal
We adopt the standard forecasting definitions based on two
clinically motivated parameters Mormann et al. [2007]: the                     where Tinter-ictal is the total inter-ictal duration in hours
Seizure Prediction Horizon (SPH) and the Seizure Occur-                        and NFP is the number of false alarm events. To re-
rence Period (SOP). We set SPH = 5 minutes as the inter-                       flect user experience and avoid double-counting when
val immediately preceding seizure onset during which an ef-                    sustained artifacts produce repeated threshold crossings,
fective response is unlikely, and SOP = 30 minutes as the                      false alarms occurring within the 30-minute refractory
time window after an alarm within which a seizure is ex-                       period are merged and counted as a single event Mor-
pected. Accordingly, the target pre-ictal interval is defined                  mann et al. [2007]. Maintaining a low FPR/h is essential
as [Tonset − 35, Tonset − 5] minutes.                                          to reduce alarm fatigue and support long-term adherence
                                                                               to a forecasting system.
   • Segment-based sensitivity: Seizure forecasting per-
     formance is commonly evaluated using event-based or                 3     Results
     segment-based criteria. Event-based evaluation counts
     a seizure as correctly predicted if at least one alarm              Table 2 summarizes the forecasting performance of EEG-
     occurs within the SOP, whereas segment-based evalua-                Titans on the test set. Consistent with our sensitivity-oriented
     tion assesses the classification of each segment indepen-           evaluation strategy, we analyze results by separating subjects
     dently. In this study, we report segment-based sensitivity          with stable behavior from a small number of challenging
     to quantify whether the model consistently recognizes               cases that motivate patient-specific adaptation.
     pre-ictal activity across the entire pre-ictal interval:            3.1    Stable Cohort
                                     T Pseg                              For the majority of subjects (16 out of 18; 89% of the co-
                  Sensitivity =                 .              (11)      hort), EEG-Titans achieves 100% segment-level sensitivity
                                T Pseg + F Nseg

Table 2: Baseline forecasting performance. The “standard 60 s con-   ment yields a marked improvement.
text” follows windowing conventions commonly adopted in prior           Analysis: The improvement to 0.00 FPR/h indicates that
benchmarks Truong et al. [2018]. Shaded rows indicate subjects
                                                                     extending the local context can substantially enhance robust-
with elevated false positive rates before adaptation.
                                                                     ness under heavy artifact contamination. A plausible interpre-
                                                                     tation is that a wider sliding-window attention span enables
        Subject ID            Sensitivity (%)         FPR/h          the local branch to model temporal consistency over several
                                                                     minutes and to down-weight discontinuous artifact bursts that
          CHB01                    100.00             0.0618
                                                                     lack coherent evolution. In turn, this reduces the likelihood
          CHB02                    100.00             0.0686         that short-lived artifacts are propagated into the global mem-
          CHB03                    100.00             0.0000         ory pathway, improving both specificity and sensitivity in this
          CHB04                    100.00             0.0000         subject.
          CHB05                    100.00             0.3582         Potential vs. Integrity CHB06 achieves 100% sensitivity
          CHB06                    100.00             0.9034         but exhibits an elevated false positive rate (0.90/h). This pat-
          CHB07                    100.00             0.1846         tern likely reflects subject-specific and demographic factors
                                                                     in the dataset. First, CHB06 is the youngest subject in the
          CHB08                    100.00             0.1303         cohort (approximately 1.5 years old), and pediatric EEG can
          CHB09                    100.00             0.0834         be highly non-stationary with developmental dynamics that
          CHB10                    100.00             0.0000         differ substantially from older children and adults. Second,
          CHB13                    100.00             0.0663         the seizures in this subject are relatively brief (on the order
          CHB14                    100.00             0.0983         of ∼15 seconds), which can bias the operating point toward
                                                                     higher sensitivity and thereby increase susceptibility to spuri-
          CHB15                     90.34             3.8710         ous fluctuations.
          CHB16                    100.00             0.1229            While additional calibration or adaptation (e.g., frequency-
          CHB18                    100.00             0.5000         weighted filtering or subject-specific regularization) may re-
          CHB20                    100.00             0.0831         duce false alarms in CHB06, we intentionally report the base-
          CHB21                    100.00             0.0000         line performance to reflect the genuine heterogeneity present
                                                                     in CHB-MIT. This case motivates the need for a dedicated pe-
          CHB22                    100.00             0.1527         diatric calibration protocol in future deployments, rather than
      Baseline Average              99.46             0.3713         relying on retrospective optimization that may mask clini-
                                                                     cally important variability.
                                                                     3.3   Benchmarking Against Prior CHB-MIT
while maintaining a low false positive rate (typically < 0.2
alarms/hour). This consistent behavior suggests that, for
                                                                           Results
standard-quality recordings, the model learns a stable and dis-      Table 4 positions EEG-Titans (standard configuration)
criminative mapping between pre-ictal dynamics and inter-            against representative state-of-the-art (SOTA) methods re-
ictal baseline activity. In particular, the Titans backbone ap-      ported on the CHB-MIT dataset.
pears able to leverage long-context information to reduce sen-          Several recent methods report sensitivities above 99.8%
sitivity to transient fluctuations while preserving high detec-      (e.g. Hussein et al. [2022]). Under the baseline setting,
tion coverage, in line with the intended role of the neural          EEG-Titans attains an average sensitivity of 99.46%, indi-
memory pathway Behrouz et al. [2024].                                cating that the proposed memory-augmented backbone is
                                                                     competitive with strong CNN and Transformer baselines.
3.2    Adaptive Capability and Outlier Analysis                      Notably, multiple SOTA approaches rely on explicit time–
                                                                     frequency transformations (e.g., STFT or CWT), whereas
Although performance is stable for most subjects, two cases-
                                                                     EEG-Titans operates on tokens extracted from minimally
CHB15 and CHB06-exhibit elevated false positive rates un-
                                                                     processed EEG via the ShallowConvNet tokenizer. This
der the baseline configuration. Rather than treating these as
                                                                     suggests that learned spectro-spatial tokenization combined
purely statistical anomalies, we interpret them as clinically
                                                                     with memory-augmented temporal modeling can provide suf-
relevant edge cases that highlight the need for patient-specific
                                                                     ficient representational capacity for high-coverage seizure
adaptation strategies.
                                                                     forecasting in this setting.
Demonstrated Adaptation CHB15 shows the highest                         Within the hybrid category, EEG-Titans substantially im-
baseline false positive rate (3.87/h), which is consistent with      proves upon a recent CNN+LSTM pipeline Lu et al. [2023],
dense high-amplitude muscle artifacts in the recordings. Un-         increasing sensitivity from 98.40% to 99.46%. This gain is
der the baseline configuration using a 60-second context (con-       consistent with the hypothesis that the Memory-as-a-Gate
sistent with common protocols Truong et al. [2018]), the             mechanism preserves and integrates long-range information
model is more likely to confuse recurrent artifact patterns          more effectively than standard recurrent units, whose effec-
with sustained pre-ictal energy accumulation.                        tive memory can degrade over extended horizons Hochreiter
   To examine the model’s adaptability, we apply the hierar-         and Schmidhuber [1997]; Behrouz et al. [2024].
chical input strategy by extending the context window from              EEG-Titans yields a baseline of 0.371 FPR/h. While
60 s to 300 s (5 minutes). As reported in Table 3, this adjust-      this value is higher than the ultra-low FPR/h reported by

                                         Table 3: Effect of context extension for subject CHB15.

                               Setting                  Context Window           Sen (%)           FPR/h
                               Baseline                     60 s (1 min)           90.34           3.87
                               Adaptive (New)              300 s (5 min)           99.86           0.00

                       Table 4: Performance comparison with state-of-the-art methods on the CHB-MIT dataset.

      Category     Study / Model                       Year     Methodology                                 Sen (%)     FPR/h
      Transformer-based
                 Yan et al. [2022]                     2022     3-Tower Transformer + STFT                   96.01       0.047
                 Hu et al. [2023]                      2023     Hybrid Transformer + Wavelet                 91.70       0.000
                 Zheng et al. [2025]                   2024     Two-stage Set Transformer                    80.10       0.110
                 Hussein et al. [2022]                 2022     Multi-channel ViT + CWT                      99.80       0.004
      TCN & Hybrid
                Huang and et al. [2024]                2024     TCN + Self-Attention                         97.37        N/A
                Lu et al. [2023]                       2023     CBAM-3D CNN + BiLSTM (STFT)                  98.40       0.017
      Proposed Approach
                 Ours (Memory)                         2025     Titans + Sliding Attention                   99.46       0.371


some efficiency-oriented CNN approaches, it should be in-             the role of the Memory-as-a-Gate design in suppressing iso-
terpreted in the context of our sensitivity-oriented threshold        lated high-confidence predictions that are inconsistent with
selection and cohort heterogeneity. A non-trivial fraction            longer-term context. The dual-branch structure maintains re-
of false alarms is concentrated in a small number of chal-            sponsiveness through the local attention pathway while us-
lenging subjects (notably CHB15 and CHB06), making the                ing the memory pathway as a slower-varying contextual ref-
cohort-average FPR/h sensitive to artifact burden and demo-           erence to down-weight transient deviations.
graphic variability. Importantly, the CHB15 analysis shows               A practical question is whether EEG-Titans’s gains arise
that subject-specific adaptation through context extension can        from the memory mechanism itself or simply from increased
reduce false alarms without compromising sensitivity, indi-           model capacity. Although parameter-matched controls would
cating a practical pathway for improving FPR/h beyond the             be required for definitive attribution, the observed results and
baseline configuration.                                               architectural properties are consistent with the neural memory
                                                                      pathway providing functional benefits beyond passive capac-
3.4   Ablation Study                                                  ity scaling.
To better attribute performance to architectural components,
                                                                      Long-horizon retention: Titans memory versus LSTM
we compare EEG-Titans with simplified temporal backbones.
                                                                      recurrence
Table 5 reports average results across 18 subjects.
                                                                      LSTMs reduce vanishing gradients relative to earlier
Tokenizer-driven separability across temporal backbones               RNNs Hochreiter and Schmidhuber [1997], but their effec-
All variants achieve high sensitivity (> 98%), indicating that        tive ability to retain and retrieve information can still weaken
the ShallowConvNet-based spatial tokenizer produces dis-              as sequence length increases. Titans maintains a persis-
criminative spectro-spatial representations Schirrmeister et          tent memory state updated by an adaptive retention mecha-
al. [2017]. This behavior is consistent with the tokenizer            nism Behrouz et al. [2024], designed to preserve salient infor-
acting as a learnable filtering stage that emphasizes informa-        mation over long horizons with fixed per-step computation.
tive power patterns and spatial projections commonly used in          The consistent FPR/h reduction relative to the LSTM tempo-
EEG decoding. Under this interpretation, the temporal back-           ral baseline (Table 5) is compatible with the view that neural
bone primarily enforces temporal consistency and helps reject         memory provides a more reliable long-context reference for
spurious activations rather than discovering seizure-related          rejecting transient artifact-driven activations.
features from scratch.
                                                                      Selective context gating rather than passive smoothing
Neural memory reduces false alarms under the same                     A concern is that neural memory might act mainly as a
tokenizer                                                             smoothing operator. Pure smoothing would typically sup-
While sensitivity is high across baselines, EEG-Titans                press rapid changes and could increase false negatives for
achieves the lowest FPR/h, improving upon the attention-only          brief events. In CHB06, which contains very short seizures
temporal baseline (0.371 vs. 0.522). This reduction supports          (∼15 s), EEG-Titans maintains 100% sensitivity (Section 3),

                                    Table 5: Ablation study: average performance across 18 subjects.

                           Model Configuration                       Avg. Sensitivity (%)      Avg. FPR/h
                           Proposed (EEG-Titans)                             99.46                0.371
                           Baseline 1: LSTM (Temporal Only)                  98.70                0.395
                           Baseline 2: Attention (Spatial Only)              98.41                0.522


suggesting that the model does not simply flatten fast dynam-         seizure onset under long horizons Hochreiter and Schmidhu-
ics. Instead, the data-dependent gating in the MAG block              ber [1997]. Transformers alleviate local context limitations
provides a plausible mechanism for selectively amplifying in-         but incur quadratic cost with sequence length, which becomes
formative short-term patterns while using longer-term context         prohibitive for very long windows and resource-constrained
to suppress non-coherent fluctuations Behrouz et al. [2024],          devices Vaswani et al. [2017]. EEG-Titans leverages the Ti-
consistent with an active, context-conditioned memory rather          tans Memory-as-a-Gate design to maintain a persistent long-
than passive smoothing.                                               context state with fixed per-step computation, enabling the
                                                                      model to preserve salient long-range information while re-
4     Discussion                                                      taining responsiveness to local anomalies. The ablation re-
                                                                      sults support this motivation: when the tokenizer is held
This work investigates whether modern neural memory can               constant, the memory-augmented temporal backbone reduces
improve EEG-based seizure forecasting under long-horizon,             FPR/h relative to attention-only and LSTM-based baselines,
sequential evaluation, where subtle pre-ictal changes must            suggesting that memory provides a stabilizing reference for
be detected without violating temporal causality. Across 18           rejecting transient, non-coherent activations.
CHB-MIT subjects, EEG-Titans achieves high segment-level
sensitivity under a chronological hold-out protocol, while            4.3    Tokenizer–backbone synergy and EEG-specific
revealing interpretable failure modes in artifact-heavy and                  inductive bias
highly non-stationary recordings. Below we discuss the im-
                                                                      All temporal variants achieve high sensitivity, indicating
plications of these findings for long-context modeling, clini-
                                                                      that the ShallowConvNet tokenizer provides strong spectro-
cal deployment, and future extensions.
                                                                      spatial representations from minimally processed EEG. This
4.1    Clinical perspective: sensitivity-first operation              aligns with established EEG decoding practice in which spa-
                                                                      tial filtering and power-related features capture discriminative
       under causal evaluation                                        neural signatures Bandarabadi et al. [2015]; Schirrmeister et
Seizure forecasting is a safety-critical task in which missed         al. [2017]. Under this view, the temporal backbone’s pri-
events can have severe consequences for patients; thus, it is         mary role shifts from feature discovery to enforcing temporal
clinically reasonable to treat high sensitivity as a primary con-     consistency and artifact rejection. The MAG fusion in EEG-
straint rather than a tunable trade-off Mormann et al. [2007];        Titans is well matched to this requirement: the local atten-
Cook et al. [2013]. In contrast to retrospective protocols that       tion stream can react quickly to candidate signatures, while
risk temporal leakage, our chronological hold-out design bet-         the memory stream contextualizes those signatures against
ter reflects the real deployment scenario in which the model          longer-term trends, reducing spurious alarms when local evi-
must generalize from earlier history to future seizure clus-          dence is not supported by sustained evolution Behrouz et al.
ters Truong et al. [2018]. Importantly, this sequential setting       [2024].
makes false alarm control more challenging, because operat-
ing near maximal sensitivity typically amplifies the impact of        4.4    Subject heterogeneity and context as a control
non-stationarity and artifacts. The observed concentration of                knob for artifact rejection
false alarms in a small subset of subjects reinforces the view        The CHB-MIT cohort includes substantial variability in age,
that patient heterogeneity and recording conditions dominate          seizure morphology, and recording artifacts Shoeb [2009].
practical performance in long-term EEG monitoring Shoeb               Two observations are particularly informative. First, the
[2009]; Mormann et al. [2007].                                        CHB15 case suggests that false alarms driven by muscle
                                                                      artifacts can be suppressed by extending temporal context,
4.2    Why neural memory matters for long-horizon                     which enables the model to discriminate temporally inco-
       pre-ictal dynamics                                             herent bursts from progressively evolving pre-ictal trajecto-
A core motivation of EEG-Titans is that pre-ictal biomark-            ries. Second, the CHB06 case highlights biological non-
ers are often subtle, non-stationary, and unfold gradually over       stationarity in very young subjects, where brief seizures and
extended durations, requiring models to integrate information         developmental EEG dynamics can induce hypersensitivity
across distant time points Truong et al. [2018]; Mormann et           and elevated false positives even when sensitivity remains
al. [2007]. Classical recurrent units, including LSTMs, can           high. Together, these results support a practical conclusion:
degrade in effective memory as sequence length grows, mak-            temporal context size is a clinically meaningful tuning axis
ing it difficult to reliably link early pre-ictal changes to later    for balancing robustness and responsiveness under safety-first

operation. An important next step is to replace manual adap-        For example, studies on perceptual decision-making have
tation with an automated policy (e.g., uncertainty- or artifact-    shown that EEG correlates of evidence accumulation (e.g.,
aware context selection) that can adjust context length online      the centroparietal positivity) evolve continuously prior to
without violating causality Mormann et al. [2007]; Truong et        overt responses, supporting the need for models that integrate
al. [2018].                                                         information over time rather than rely on isolated window-
                                                                    level snapshots Tran et al. [2023]; O’Connell et al. [2012];
4.5   Long-sequence modeling, early anticipation,                   Kelly and O’Connell [2013]; Tagliabue et al. [2019]. Simi-
      and trustworthy deployment                                    larly, work on post-choice dynamics suggests that decision-
EEG-Titans relates to three converging directions in modern         related neural variables can continue to evolve after initial
EEG modeling: (i) efficient long-sequence representation, (ii)      commitment, reinforcing the value of architectures that main-
early anticipation under weak and slowly evolving biomark-          tain and update context across extended horizons Murphy et
ers, and (iii) trustworthy deployment under strong subject het-     al. [2015]. In a related vein, multimodal forecasting of human
erogeneity and safety constraints. We discuss each aspect be-       decision performance highlights that anticipatory cues are of-
low and position the present study within the broader litera-       ten progressive and benefit from temporal integration Tran et
ture.                                                               al. [2024a].
                                                                       From this viewpoint, EEG-Titans’s dual-branch design re-
Efficient long-horizon sequence modeling in EEG                     flects a general anticipation strategy: a responsive pathway
A central challenge in seizure forecasting is that pre-ictal sig-   that detects local anomalies, coupled with a stabilizing path-
natures may unfold over tens of minutes and can be inter-           way that integrates longer-term context to validate whether
leaved with non-stationary artifacts, requiring models to inte-     local deviations are consistent with a true state transition.
grate information over long horizons while remaining com-           This perspective is consistent with prior seizure prediction
putationally feasible Mormann et al. [2007]; Truong et al.          findings that models capable of accumulating evidence over
[2018]. Classical recurrent architectures (e.g., LSTMs) were        longer horizons can be more resilient than approaches oper-
introduced to mitigate vanishing gradients, yet their effec-        ating on short independent segments.
tive memory can still degrade on ultra-long sequences in
practice Hochreiter and Schmidhuber [1997]. Transformer-            Trustworthy forecasting: interpretability, fairness, and
style self-attention improves global context modeling, but          patient-level reliability
its quadratic cost with sequence length constrains scalability      Real-world deployment of seizure forecasting systems de-
for long observation windows and resource-limited deploy-           pends not only on average performance but also on trust:
ment Vaswani et al. [2017]. As a result, several recent seizure     clinicians and users must understand when and why alarms
prediction pipelines rely on limited context windows and/or         occur, and the system must behave reliably across heteroge-
explicit time–frequency transformations (e.g., STFT/CWT)            neous patients and recording conditions Shoeb [2009]; Mor-
coupled with heavier backbones Yan et al. [2022]; Hussein           mann et al. [2007]. The concentration of false alarms in
et al. [2022].                                                      artifact-heavy or highly non-stationary subjects underscores
   Beyond attention and recurrence, efficient sequence mod-         that cohort-level averages can mask clinically important fail-
eling families such as state-space models (SSMs) have re-           ure modes. This motivates evaluation beyond aggregate met-
cently gained traction for long-context learning due to their       rics, including subject-level stratification and safety-first op-
favorable scaling and stable dynamics Gu and Dao [2024].            erating points, as well as explicit analyses of challenging sub-
In EEG/ECG applications, SSM-based designs have been ex-            groups.
plored for clinical classification and representation learning         In parallel clinical domains, fairness-aware evaluation
under long recordings, emphasizing efficient long-range tem-        frameworks have been proposed to assess whether model
poral modeling and robustness to temporal variability Tran et       behavior remains consistent across demographic strata and
al. [2024b]; Nguyen and Tran [2025]. In this context, EEG-          recording variations, particularly when explainability is used
Titans provides an alternative route to long-horizon model-         to support clinical plausibility checks Nguyen et al. [2024].
ing by using a neural memory mechanism with fixed per-step          Although originally studied in Alzheimer’s disease detection,
computation. Conceptually, memory-augmented models and              the same principle applies to seizure forecasting: systematic
SSMs share the objective of scalable long-context processing,       over-alarming in specific subgroups (e.g., very young sub-
suggesting that future EEG forecasting systems may benefit          jects or recordings with frequent muscle artifacts) may be
from hybrid designs that combine structured latent dynamics         unacceptable despite strong mean sensitivity. Furthermore,
with adaptive memory gating.                                        contrastive learning has been used to improve EEG repre-
Early anticipation as a shared paradigm across EEG                  sentation robustness by promoting invariant structure across
applications                                                        conditions or modalities, which can improve calibration un-
Seizure forecasting is fundamentally an anticipation prob-          der distribution shifts and reduce spurious activations in noisy
lem: the system must recognize subtle, gradually evolv-             settings Tran et al. [2024b].
ing dynamics before the overt ictal transition, under strict
temporal causality and with limited tolerance for missed            4.6   Limitations and future directions
events Mormann et al. [2007]; Cook et al. [2013]. This antic-       Several limitations should be acknowledged. First, CHB-
ipatory framing is shared by other EEG tasks where discrimi-        MIT is a pediatric cohort with specific hospital recording
native neural signatures emerge before observable outcomes.         characteristics; external validation on additional datasets and

prospective evaluation are needed to assess generalization            and incidence of epilepsy: A systematic review and meta-
in ambulatory settings. Second, although the chronological            analysis of international studies. Neurology, 88(3):296–
protocol mitigates leakage, patient-specific thresholding and         303, 2017.
context adaptation remain important; future work should for-        Albert Gu and Tri Dao. Mamba: Linear-time sequence mod-
malize calibration policies that are efficient and clinically in-     eling with selective state spaces. In First conference on
terpretable, potentially guided by artifact detection and uncer-      language modeling, 2024.
tainty estimation. Third, interpretability is not explicitly ad-
dressed in the current model; incorporating explanation tools       Sepp Hochreiter and Jürgen Schmidhuber. Long short-term
(e.g. token-/channel-level attribution aligned with seizure           memory. Neural Computation, 9(8):1735–1780, 1997.
onset zones) and evaluating fairness across age/sex strata          Yifan Hu, Harish Kulanayagam, Catherine Maher, Levin
would strengthen clinical readiness. Finally, while EEG-              Kuhlmann, and Mohammad A. Armin. Exploring the ap-
Titans uses minimally processed signals, integrating comple-          plicability of transfer learning and feature engineering in
mentary modalities (e.g., ECG or wearable context signals)            epilepsy prediction using hybrid transformer model. IEEE
and leveraging representation learning (e.g., contrastive pre-        Transactions on Neural Systems and Rehabilitation Engi-
training) may further improve robustness under real-world             neering, 31:1321–1332, 2023.
noise and non-stationarity.                                         Leen Huang and et al. Automatic detection of epilepsy from
                                                                      eegs using a temporal convolutional network with a self-
5   Conclusion                                                        attention layer. BioMedical Engineering OnLine, 23:50,
This work presented EEG-Titans, a seizure prediction frame-           2024.
work that combines ShallowConvNet tokenization with a Ti-
                                                                    Ramy Hussein, Mohamed Osama Ahmed, Rabab Ward,
tans Memory-as-a-Gate backbone to model long-range pre-
                                                                      Z. Jane Wang, Levin Kuhlmann, and Yi Guo. Multi-
ictal dynamics while remaining sensitive to short-term abnor-
                                                                      channel vision transformer with continuous wavelet trans-
malities. On CHB-MIT with chronological hold-out eval-
                                                                      form for epileptic seizure prediction.     Biomedicines,
uation, the model achieved 99.46% average segment-level
                                                                      10(7):1551, 2022.
sensitivity with 0.371 FPR/h, and showed stable behavior
for 16/18 subjects (100% sensitivity with low false-alarm           Simon P. Kelly and Redmond G. O’Connell. Internal and
rates). The two challenging cases (CHB15, CHB06) high-                external influences on the rate of sensory evidence accu-
light the impact of artifacts and pediatric non-stationarity un-      mulation in the human brain. Journal of Neuroscience,
der a sensitivity-first operating point. Importantly, CHB15           33(50):19434–19441, 2013.
demonstrates that false-alarm control is tightly linked to tem-     Xiang Lu, Anhao Wen, Lei Sun, Hao Wang, Yinjing Guo, and
poral context - extending the context from 60 s to 300 s re-          Yande Ren. An epileptic seizure prediction method based
duced FPR/h from 3.87 to 0.00 while increasing sensitiv-              on cbam-3d cnn-lstm model. IEEE Journal of Transla-
ity from 90.34% to 99.86%. These results support neural-              tional Engineering in Health and Medicine, 11:417–423,
memory-based backbones as a practical approach for long-              2023.
context EEG forecasting and motivate future work on patient-
specific calibration for robust deployment.                         Florian Mormann, Ralph G. Andrzejak, Christian E. Elger,
                                                                      and Klaus Lehnertz. Seizure prediction: the long and wind-
                                                                      ing road. Brain, 130(2):314–333, 2007.
References
M. Bandarabadi, C. A. Teixeira, J. Rasekhi, and A. Dourado.         Patrick R. Murphy, Ian H. Robertson, Susan Harty, and Red-
  Epileptic seizure prediction using relative spectral power          mond G. O’Connell. Neural evidence accumulation per-
  features.     Clinical Neurophysiology, 126(2):237–248,             sists after choice to inform metacognitive judgments. eLife,
  2015.                                                               4:e11946, 2015.
Ali Behrouz, Peilin Zhong, and Vahab Mirrokni. Titans:              Hai Duong Nguyen and Xuan-The Tran.          Ecg-ramba:
  Learning to memorize at test time, 2024.                            Zero-shot ecg generalization by morphology-rhythm dis-
                                                                      entanglement and long-range modeling. arXiv preprint
Mark J. Cook, Terence J. O’Brien, Samuel F. Berkovic,                 arXiv:2512.23347, 2025.
  Mike Murphy, Andrew Morokoff, George Fabinyi, Wendyl
  D’Souza, Ramesh Yerra, James Archer, L. Litewka, Scott            Quoc-Toan Nguyen, Linh Le, Xuan-The Tran, Thomas Do,
  Hosking, Paul Lightfoot, Vanessa Ruedebusch, W. D.                  and Chin-Teng Lin. Fairad-xai: Evaluation framework
  Sheffield, David Snyder, Kirsten Leyde, and David Himes.            for explainable ai methods in alzheimer’s disease detec-
  Prediction of seizure likelihood with a long-term, im-              tion with fairness-in-the-loop. In Companion of the 2024
  planted seizure advisory system in patients with drug-              on ACM International Joint Conference on Pervasive and
  resistant epilepsy: a first-in-man study. The Lancet Neu-           Ubiquitous Computing, pages 870–876, 2024.
  rology, 12(6):563–571, 2013.                                      Redmond G. O’Connell, Paul M. Dockree, and Simon P.
Kirsten M. Fiest, Khara M. Sauro, Samuel Wiebe, Scott B.              Kelly. A supramodal accumulation-to-bound signal that
  Patten, Churl-Su Kwon, Jessica Dykeman, Tamara Pring-               determines perceptual decisions in humans. Nature Neuro-
  sheim, Diane L. Lorenzetti, and Nathalie Jetté. Prevalence         science, 15(12):1729–1735, 2012.

Robin Tibor Schirrmeister, Jost Tobias Springenberg, Lukas      Nghia D. Truong, Anh D. Nguyen, Levin Kuhlmann, Mo-
  Dominic Jakob Fiederer, Martin Glasstetter, Katharina           hammad R. Bonyadi, Jing Yang, Simon Ippolito, and Omid
  Eggensperger, Michael Tangermann, Frank Hutter, Wol-            Kavehei. Generalised seizure prediction with convolu-
  fram Burgard, and Tonio Ball. Deep learning with convolu-       tional neural networks for intracranial and scalp electroen-
  tional neural networks for eeg decoding and visualization.      cephalogram data. IEEE Access, 6:33947–33959, 2018.
  Human Brain Mapping, 38(11):5391–5420, 2017.                  Konstantinos M. Tsiouris, Vasileios C. Pezoulas, Dimitrios
Ali H. Shoeb. Application of Machine Learning to Epileptic        Zafeiriou, Spyridon Konitsiotis, Dimitrios D. Koutsouris,
  Seizure Onset Detection and Treatment. PhD thesis, Mas-         and Dimitrios I. Fotiadis. A long short-term memory deep
  sachusetts Institute of Technology, Cambridge, MA, USA,         learning network for the prediction of epileptic seizures
  2009. Ph.D. dissertation.                                       using eeg signals. Computers in Biology and Medicine,
Chiara F. Tagliabue, Domenica Veniero, Christopher S. Y.          99:24–37, 2018.
  Benwell, Roberto Cecere, and Gregor Thut. The eeg sig-        Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkor-
  nature of sensory evidence accumulation during decision         eit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, and Illia
  formation closely tracks subjective perceptual experience.      Polosukhin. Attention is all you need. In Advances in Neu-
  Scientific Reports, 9(1):4949, 2019.                            ral Information Processing Systems (NeurIPS), volume 30,
Xuan-The Tran, Thomas Tien-Thong Do, and Chin-Teng Lin.           2017.
  Early detection of human decision-making in concealed         World Health Organization. Epilepsy: a public health imper-
  object visual searching tasks: An eeg-bilstm study. In 2023    ative. World Health Organization, Geneva, Switzerland,
  45th Annual International Conference of the IEEE Engi-         2019.
  neering in Medicine & Biology Society (EMBC), pages 1–
  4. IEEE, 2023.                                                Jie Yan, Yufan Li, Yankun Xu, Mingze Jiang, and Heming
                                                                   Wu. Seizure prediction based on transformer using scalp
Xuan-The Tran, Thomas Do, Nikhil R Pal, Tzyy-Ping Jung,            electroencephalogram.   Applied Sciences, 12(9):4158,
  and Chin-Teng Lin. Multimodal fusion for anticipat-              2022.
  ing human decision performance. Scientific Reports,
  14(1):13217, 2024.                                            Ruifeng Zheng, Cong Chen, Shuang Wang, Yiming Liu, Lin
                                                                  You, Jindong Lu, Ruizhe Zhu, Guodao Zhang, and Ke-
Xuan-The Tran, Linh Le, Quoc Toan Nguyen, Thomas Do,              jie Huang. Eeg-based epileptic prediction via a two-stage
  and Chin-Teng Lin. Eeg-ssm: leveraging state-space model        channel-aware set transformer network, 2025.
  for dementia detection. arXiv preprint arXiv:2407.17801,
  2024.
```
