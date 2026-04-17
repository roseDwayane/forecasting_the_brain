---
citation_key: "BaryMacq2024"
paper_id: "paper_192"
title: "Designing Pre-training Datasets from Unlabeled Data for EEG Classification with Transformers"
authors: "Tim Bary; Benoit Macq"
year: 2024
doi: "10.1109/melecon56669.2024.10608657"
source: "publisher-pdf (doi: 10.1109/melecon56669.2024.10608657); arxiv (2410.07190)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
arxiv_id: "2410.07190"
tier: 1
composite: 4.5
---

# Designing Pre-training Datasets from Unlabeled Data for EEG Classification with Transformers

**Citation:** `BaryMacq2024` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/melecon56669.2024.10608657](https://doi.org/10.1109/melecon56669.2024.10608657)
**Source PDF:** `full_pdf/Bary2024.pdf`

## Abstract

Transformer neural networks require a large is then pre-trained on this “self-labeled” data, enabling it to arXiv:2410.07190v1 [eess.SP] 23 Sep 2024 amount of labeled data to train effectively. Such data is often acquire some fundamental data representation. Subsequently, scarce in electroencephalography, as annotations made by medi- these pre-trained models can be fine-tuned for specific appli- cal experts are costly. This is why self-supervised training, using unlabeled data, has to be performed beforehand. In this paper, we cations using a small sample of labeled data, outperforming present a way to design several labeled datasets from unlabeled their non-pre-trained counterparts [9]–[11]. electroencephalogram (EEG) data. These can then be used to In this article, we present a methodology to exploit the pre-train transformers to learn representations of EEG signals. huge amount of unlabeled EEG data available by designing We tested this method on an epileptic seizure forecasting task on three intuitive and interpretable pre-training tasks. We bench- the Temple University Seizure Detection Corpus using a Multi- channel Vision Transformer. Our results suggest that 1) Models mark these pre-trainings by comparing their contributions to pre-trained using our approach demonstrate significantly faster the performances of Hussein et al.’s Multi-channel Vision training times, reducing fine-tuning duration by more than 50% Transformer (MViT) [7] on an eyes open/eyes closed (EO/EC) for the specific task, and 2) Pre-trained models exhibit improved classification dataset. Finally, we test the performance im- accuracy, with an increase from 90.93% to 92.16%, as well as provement of the best pre-training on an epileptic seizure a higher AUC, rising from 0.9648 to 0.9702 when compared to non-pre-trained models. forecasting task, leveraging the Temple University Hospital

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Designing Pre-training Datasets from Unlabeled
                                                Data for EEG Classification with Transformers
                                                                                                 Tim Bary, Benoı̂t Macq
                                                                                            Université catholique de Louvain
                                                                                                    ICTEAM, ELEN
                                                                                               Louvain-la-Neuve, Belgium
                                                                                         {tim.bary}{benoit.macq}@uclouvain.be


                                              Abstract—Transformer neural networks require a large               is then pre-trained on this “self-labeled” data, enabling it to


arXiv:2410.07190v1 [eess.SP] 23 Sep 2024
                                           amount of labeled data to train effectively. Such data is often       acquire some fundamental data representation. Subsequently,
                                           scarce in electroencephalography, as annotations made by medi-        these pre-trained models can be fine-tuned for specific appli-
                                           cal experts are costly. This is why self-supervised training, using
                                           unlabeled data, has to be performed beforehand. In this paper, we     cations using a small sample of labeled data, outperforming
                                           present a way to design several labeled datasets from unlabeled       their non-pre-trained counterparts [9]–[11].
                                           electroencephalogram (EEG) data. These can then be used to               In this article, we present a methodology to exploit the
                                           pre-train transformers to learn representations of EEG signals.       huge amount of unlabeled EEG data available by designing
                                           We tested this method on an epileptic seizure forecasting task on     three intuitive and interpretable pre-training tasks. We bench-
                                           the Temple University Seizure Detection Corpus using a Multi-
                                           channel Vision Transformer. Our results suggest that 1) Models        mark these pre-trainings by comparing their contributions to
                                           pre-trained using our approach demonstrate significantly faster       the performances of Hussein et al.’s Multi-channel Vision
                                           training times, reducing fine-tuning duration by more than 50%        Transformer (MViT) [7] on an eyes open/eyes closed (EO/EC)
                                           for the specific task, and 2) Pre-trained models exhibit improved     classification dataset. Finally, we test the performance im-
                                           accuracy, with an increase from 90.93% to 92.16%, as well as          provement of the best pre-training on an epileptic seizure
                                           a higher AUC, rising from 0.9648 to 0.9702 when compared to
                                           non-pre-trained models.                                               forecasting task, leveraging the Temple University Hospital
                                              Index Terms—self-supervised learning, electroencephalogram,        Seizure Detection Corpus (TUSZ) [12].
                                           pre-training datasets, transformers, epileptic seizure forecasting.
                                                                                                                                 II. P RE - TRAINING DATASETS
                                                                  I. I NTRODUCTION                                  We collected two datasets to demonstrate the capabilities
                                              Transformer neural networks distinguish themselves from            of the proposed methods. Their specifications are described in
                                           other deep learning architectures thanks to their self-attention      subsection II-A. The main contribution of this article, namely
                                           mechanism. This feature allows these networks to focus on             the processes by which unlabeled data from these datasets
                                           different parts of the input sequence as they process it, facili-     is converted into useful pre-training data, is described in
                                           tating the capture of long-range dependencies and contextual          subsection II-B.
                                           relationships. On top of this, this type of network also operates
                                           on the entire sequence of input data at once, allowing for            A. The initial datasets
                                           parallelization and improved efficiency. These traits however            1) The EO/EC dataset: This dataset features a healthy male
                                           come at a price: transformer-based models require a substantial       subject in the 20-25 age category. It includes an 11 minutes, 32
                                           amount of annotated data during training to avoid overfitting         channels EEG signal recorded at 1 kHz. Annotations comprise
                                           [1,2].                                                                two labels: EO when the subject has his eyes open while his
                                              While transformers have primarily found their footing in           EEG is being recorded, EC when his eyes are closed. Given
                                           Natural Language Processing (NLP) [1] and Computer Vision             its small size and the simplicity of the task, the EO/EC dataset
                                           (CV) [3], researchers have recently started extending their           was used for experimenting with the different pre-training
                                           capabilities to electroencephalogram (EEG) applications, in-          methods to identify the most effective one with statistically
                                           cluding emotion recognition [4], motor imagery [5,6], and             significant results.
                                           epileptic seizure forecasting [7,8]. However, unlike for NLP             2) The TUSZ dataset: The TUSZ database is part of a
                                           and CV, which have a lot of labeled data available to train their     larger EEG corpus created to facilitate EEG processing tool
                                           models, quality annotated data in the medical field is scarce         development [13]. TUSZ comprises EEG signals from 579
                                           and has a high acquisition cost, since it requires an expertise       patients in 1175 sessions, including 352 sessions with seizures.
                                           exclusive to medical practitioners.                                   Annotations exploited in this paper consist of the start and
                                              To address this challenge, Self-Supervised Learning (SSL)          end times of seizures during the session, although more
                                           emerges as a pivotal approach. SSL harnesses the available            detailed information is available. Specifically, we leveraged
                                           unlabeled data in a specific field and generates pseudo-labels        these elements to generate our classification labels, that is, PI
                                           for it through some of its intrinsic characteristics. The model       for pre-ictal, and II for inter-ictal. The first label designates

                                                                Input real EEG signal                            Second input real EEG signal


                 White noise
                 replacement                                            Shuffling                                              Mixing


        Altered EEG signal #1                                 Altered EEG signal #2                                 Altered EEG signal #3

Fig. 1. Visualisation of the three EEG signals alterations for the proposed pre-training tasks. Alteration #1 replaces channels of the EEG with white noise,
alteration #2 shuffles the order of the channels, and alteration #3 mixes two randomly paired EEG samples together by replacing the channels of the first
sample by the channels of the second one and vice versa.


EEG signals present from a few minutes to a few seconds                           1) White noise replacement: In this first type of modifi-
before a seizure, while the second is used to describe patterns                cation, n random channels of the original EEG are replaced
that do not immediately precede or follow a seizure. Being able                with Gaussian white noise. The number of replaced channels
to segregate both labels therefore allows to forecast epileptic                n is a random integer varying uniformly between 1 and
seizures.                                                                      hyperparameter N for each sample generated. It is expected
   Four unipolar EEG montages were employed in the dataset,                    that a higher number of channels affected leads to more ease
two using an average reference and the other two including                     for the model at recognizing the ”non-EEG” samples. N
earlobe-referenced electrodes. Half of the montages use 19                     therefore controls the ”difficulty” of the task (the closer N
electrodes, and the rest use 21, all following the 10-20 system                is to 1, the harder the classification becomes), and a value
[14]. In this paper, the TUSZ corpus is employed for bench-                    of 5 has been arbitrarily selected. The intuition behind this
marking against a literature-standard task and evaluating the                  modification is that, unlike with EEG signals that have a power
impact of pre-training on model performances in a practical                    spectral density which tends to decrease with the frequency
scenario.                                                                      [15], the spectral density of white noise remains constant
   To simulate the scarcity of labeled data, we randomly                       across all frequencies. Being able to part between white noise
excluded 70% of the labels on both datasets. This share of                     and EEG frequency behaviors therefore implies that the model
unlabeled data is the one used to generate the pre-training                    has integrated such behaviors.
datasets. The remaining 30% of labeled data is reserved for                      2) Shuffling: In this modification, all the channels are
fine-tuning on the respective specific tasks.                                  conserved, but their positions are permuted. This operation
B. Altering the EEG signals                                                    amounts to shuffling the locations of the different EEG
   As previously explained, the goal of a pre-training task is to              probes for the model, and it therefore has to learn the inter-
draw the model to already internalize some key features of the                 dependencies between the channels to classify the data as
kind of data it is being trained on. Doing so allows the initial               shuffled or not. Channels in EEG are correlated proportionally
weights of the model to be closer to the ones minimizing the                   to the distance between them. That is, the further they are
loss function when training on the useful task, saving time and                located from one another, the less correlated they are [16].
increasing performances [10,11]. Keeping this idea in mind,                       3) Mixing: This third method takes two EEG samples as
we came up with three different ways to teach EEG properties                   input and selects n ∈ [1, N ] channels from the first input
to a deep learning model.                                                      to replace channels in the second input and vice versa. The
   All three proposed methods can be summarized as binary                      objective is to have channels that are not correlated to any
classification tasks, distinguishing between ”EEG” and ”non-                   other channel, although having the same behavior as normal
EEG” multi-channels signals. More specifically, we collected                   EEG signals. Like with channel shuffling, this classification
unlabeled EEG data that we split in two halves, keeping one                    task aims at teaching the channels correlations to the model.
part as the control, real EEG, and altering the other part to                  Once again, the hyperparameter N has arbitrarily been set to 5
become the ”non-EEG” signal. Three relevant alterations have                   (in this case, the further away N is from nchannels /2 = 16 for
been designed so far, characterizing the three methods depicted                EO/EC and 10 for TUSZ, the more difficult the task becomes,
underneath and illustrated in Fig. 1.                                          as less uncorrelated channels are potentially identifiable).

                 III. D ESIGN OF THE MODEL                                                             Class
A. Transformer architecture
                                                                                        Multi-Layer Perceptron (MLP)
   We selected the Multi-channel Vision Transformer (MViT)
architecture from Hussein et al. [7] to benchmark our pre-
trainings. This architecture, designed specifically for EEG                              Features fusion/aggregation
                                                                                                                                             xN
classification, was adopted because its configuration makes                                                                                        +
it more parameter extensive than a majority of the other                                           Parallel encoder
approaches, meaning that this model would benefit the most                       Encoder                …….              Encoder                  MLP

from our contribution compared to less bulky models. The
                                                                                                                                                  Norm
MViT relies on Dosovitskiy et al.’s Vision Transformer [3],                 Linear projection of                    Linear projection of
                                                                                                                                                   +
which performs image classification by partitioning an image                patches + positional                    patches + positional
                                                                                 encoding                                encoding
into non-overlapping patches, flattening them, and feeding                                                                                     Multi-head
                                                                                                                                               Attention
them through an encoder after positional embedding. The
encoder output is then processed by a Multi-Layer Perceptron                         …….                                     …….
                                                                                                                                                  Norm
(MLP) to classify the image.                                                            Patching                                Patching
   The MViT operates in a similar manner, except that the sin-
gle encoder is replaced by an array of independent encoders,
                                                                                                        …….
each dedicated to process one of the EEG channel. After these
encoders have performed their individual tasks, their outputs
are concatenated together before passing through the MLP
classifier. As this model only works with two-dimensional             Scalogram of EEG channel 1               Scalogram of EEG channel N
data, the 1D EEG signal must be converted. This transforma-
tion is achieved in [7] using the Continuous Wavelet Transform       Fig. 2. Schematic representation of the MViT architecture for EEG classifi-
                                                                     cation. The model ingests scalograms of individual EEG channels, processes
(CWT), a mathematical technique that decomposes the signal           them through parallel encoders, and fuses their features for final classification
into its various frequency components at different time scales       via a MLP. Scalograms are generated using the CWT to provide a time-
[17]. This results in a time-frequency (2D) representation of        frequency representation of the EEG data.
the EEG data. Fig. 2 provides a visual representation of the
MViT architecture, where EEG scalograms (i.e., the output                                        TABLE I
of the CWT) serve as input, and the model predicts their             H YPER - PARAMETERS RELATED TO THE MODEL ARCHITECTURE AND THE
                                                                                NUMBER OF WEIGHTS THIS CONFIGURATION YIELDS .
respective classes.

B. Model specifications                                                Hyper-parameter                                          EO/EC         TUSZ

   1) Scales: To adapt to the size and purpose of each                 Input tensor shape                                    [32, 25, 8]    [20, 25, 40]
                                                                       # encoders in parallel                                    32              20
dataset, we designed two models of different scales from the
                                                                       # transformer layers in encoder                            1               8
architecture previously described. Their parametrizations are          # attention heads per layer                                2               4
summarized in Table I. The EO/EC model was designed to be              Size of hidden and output layers
                                                                                                                                [16, 8]      [80, 40]
considerably smaller than its TUSZ counterpart for two rea-            (Transformer MLP)
                                                                       Size of hidden layers (Decision head)                  [128, 64]     [512, 256]
sons. First, reducing the model size allows to train more copies
of it in a limited amount of time, resulting in the possibility to     Weights                                                  EO/EC         TUSZ
achieve significance testing on its performances. The task of          # trainable weights in parallel encoder                  28 160       5 248 000
eyes open and eyes closed classification is also rather simple         # trainable weights in decision head                    827 665      10 372 177
and performed on a limited dataset, such that training a more          # total trainable weights                               855 825      15 620 177
consequent model would induce more overfitting.
   2) Optimizer and regularization: Both models underwent
training using an AdamW optimizer [18] set with parameters           the dataset’s small size, we conducted our experiment 17
β1 = 0.9, β2 = 0.999, weight decay λweights = 10−4 ,                 times, starting with a different seed for each occurrence. This
and fixed learning rate lr = 10−4 . Further regularization was       repetition allowed us to establish the significance of the results
applied in the form of dropout with a rate of 0.5 in the decision    through statistical testings.
head and 0.1 inside the encoders.                                       In each experiment, we employed three versions of the same
             IV. P ERFORMANCES ASSESSMENT                            model, all initialized with identical random weights. Each
                                                                     model was pre-trained on one of the three datasets created
A. Benchmarking the pre-trainings                                    with the data alterations for 40 epochs. Subsequently, fine-
   To identify the most effective data alteration method among       tuning for the EO/EC classification task continued for an
the three discussed in Section II-B, we utilized each of them to     additional 40 epochs. We introduced a control model that
pre-train our MViT model on the EO/EC dataset. Leveraging            underwent no pre-training, only fine-tuning for 40 epochs,

                         Pre-training         Fine-tuning                             Model performances on the EO/EC task after different pre-
                                                                                                            trainings
                                                                                                                      ****
                                                                                                                 ns                    ****
                    40 epochs: white noise
   Untrained
  models with                                  40 epochs          Trained
                     40 epochs: shuffling
  same initial                                 EO/EC task         models
    weights
                      40 epochs: mixing

                   20 epochs:    20 epochs:
                   white noise    shuffling


Fig. 3. Pre-training performances assessment methodology on the designed
pre-training datasets. Starting with five copies of a same untrained model,
four of them are pre-trained separately with one of the proposed method for
40 epochs, while the fifth model is not pre-trained. All models are then fine-
tuned on the specific task. This operation is repeated N times (in this paper,                                          *
N = 17) to account for the variability between the experiments.


commencing with the same initial weights as the other models.
Additionally, we examined a fifth model with hybrid pre-
training, consisting of 20 epochs of training on the dataset with
white noise alteration, followed by 20 epochs on the dataset
with channel shuffling alteration. We hypothesized that this
hybrid pre-training would impart a broader range of features
to the model, as white noise replacement focuses on teaching
frequency content, while channel shuffling emphasizes channel
correlations. A schematic representation of the pre-training
performance assessment methodology is presented in Fig. 3.
   Four performance metrics were extracted at the end of                         Fig. 4. Box plots of the EOC (top) and the minimum validation loss (bottom)
                                                                                 for each of the proposed pre-training methods. The significance levels are:
each experiment, following model fine-tuning. These metrics                      p < 0.05 (*), p < 0.01 (**), p < 10−3 (***), and p < 10−4 (****) (not
include 1) the epoch of convergence (EOC), which denotes                         all relations of significance are shown).
the epoch with the lowest validation loss; 2) the minimum
validation loss; 3) the validation accuracy at the EOC; and 4)
the validation area under the curve (AUC) at the EOC.                            IV-A, we evaluate both models using four performance met-
                                                                                 rics: validation loss, validation accuracy, and validation AUC,
B. Performances comparison in practical scenario                                 all measured at the EOC, plus the EOC itself. Additionally,
   Following the determination of the best pre-training method                   we measure the loss, accuracy, and AUC of both models on
detailed in the previous section, our next step is to assess its                 the test split, resulting in a total of 7 performance metrics.
effectiveness in a practical scenario, specifically, forecasting
                                                                                                   V. R ESULTS AND DISCUSSION
epileptic seizures. The objective here is to train our algorithm
to distinguish between pre-ictal EEG patterns (revealing an im-                  A. Benchmarking the pre-trainings
minent seizure) and inter-ictal EEG patterns (i.e., no imminent                     Fig. 4 displays a box plot showing the distribution of the
seizure) recorded from epileptic patients.                                       EOC and the minimum validation loss across all pre-training
   To assess the performance gains attributed to our proposed                    methods. Additionally, Table II provides a summary of the
pre-training, we undertake a comparison between two identical                    previously selected performance metrics, including means and
models, each initialized with different weight configurations.                   standard deviations, for each pre-training approach.
The first model, referred to as ”NPT” for ”Non-Pre-Trained,”                        To assess the statistical significance of eventual differences
begins with random weights initialization. The second model,                     in performances, we conducted two-tailed Welch’s t-tests [19]
termed ”PT” for ”Pre-Trained,” undergoes pre-training on the                     on each pair of pre-training methods. This test was selected
most performant of our designed datasets. The weights from                       based on the assumption that the experimental results can
the model’s epoch of convergence (EOC) during pre-training                       be considered independent and identically distributed (iid)
are then adopted as the initial weights for the primary task.                    random variables, and that the true variances of the samples
   Both models are fine-tuned using the same training and                        differ. The summary of the significance testing is added to
validation data splits from the TUSZ dataset, and we employ                      Table II.
an early stopping mechanism with a patience of 5 epochs to                          When comparing the pooled pre-training performances with
ensure that the loss of both models converges. As in section                     the ones of the model without pre-training, we observed no

                               TABLE II                                                                          TABLE III
   M EAN PERFORMANCES FOR EACH TYPE OF PRE - TRAINING ON THE                            S LOPES AND R2 SCORES OF THE LINEAR REGRESSIONS FITTING THE
   EO/EC DATASET. VALUES IN PARENTHESES ARE THE STANDARD                               EOC- MINIMUM VALIDATION LOSS RELATION . T HE PRE - TRAININGS ARE
DEVIATIONS . T HE SIGNIFICANCE OF THE PERFORMANCE IMPROVEMENT                                    RANKED FROM THE LOWEST TO THE HIGHEST R2 .
  WITH REGARDS TO THE NON - PRE - TRAINED MODEL WAS TESTED AT
 p < 0.05 (*), p < 0.01 (**), p < 10−3 (***), AND p < 10−4 (****).
                                                                                             Pre-training       Slope [loss increase/epoch]        R2
 Pre-training           EOC          Min val. loss    Val. acc. [%]    Val. AUC              Mixing                    1.049 × 10−3              0.0194
 White noise        27.4 (9.58)**    0.497 (0.053)     76.8 (4.92)    0.847 (0.036)
                                                                                             Shuffling                −0.488 × 10−3              0.0399
 Shuffling         17.0 (12.0)****   0.500 (0.029)*    77.4 (2.74)    0.839 (0.026)          No pre-training          −1.637 × 10−3              0.0763
 Mixing             31.4 (5.37)**    0.496 (0.040)     77.8 (4.78)    0.843 (0.035)          White noise              −2.459 × 10−3              0.1985
 Hybrid            17.2 (10.9)****   0.507 (0.050)     78.3 (4.35)    0.828 (0.032)          Hybrid                   −2.351 × 10−3              0.2581
 Pooled            23.2 (11.6)****   0.500 (0.044)*    77.6 (4.32)    0.839 (0.033)
 No pre-training     36.1 (4.27)     0.520 (0.025)     75.7 (4.36)    0.825 (0.025)
                                                                                                                TABLE IV
                                                                                       C OMPILATION TIME OF BOTH MODELS FOR THE DIFFERENT TRAINING
                                                                                                                 PHASES .
significant improvements in terms of validation accuracy and
validation AUC at the EOC, as indicated by p-values exceeding                          Training phase       Time/epoch (avg.) [s]   EOC       Tot. train. time [h]
0.05 (p-values: 0.1419 and 0.0661, respectively). However, we                          Pre-training (PT)           11 117            9                27.8
observed highly significant improvements in EOC (p-value <                             Fine-tuning (PT)             5 288            4                5.88
                                                                                       Fine-tuning (NPT)            5 698            8               12.66
10−5 ) and significant improvements in minimum validation
loss (p-value = 0.0197) with pre-training.
   Among the pre-training methods, only the shuffling alter-
ation demonstrated a significant improvement in minimum                               simultaneously or mixing multiple datasets, could therefore
validation loss compared to the non-pre-trained model (p-value                        be an avenue for future research.
= 0.0441). While the statistical tests indicated a trend for                          B. Performances comparison in practical scenario
other alteration types (p-values: 0.0530 for channel mixing and
                                                                                         Building upon the insights gained in the previous section
0.1329 for white noise replacement), these trends did not cross
                                                                                      and following the protocol established in section IV-B, we
the significance threshold α = 0.05. The hybrid pre-training
                                                                                      initiated the pre-training of our larger transformer model using
approach showed the least significant difference in this metric,
                                                                                      a dataset generated by means of the shuffling alteration,
with a p-value of 0.3474.
                                                                                      applied to a portion of the TUSZ data.
   When examining the EOC, both the shuffling alteration and                             When comparing the time necessary for the Pre-Trained
the hybrid pre-training approach exhibited highly significant                         (PT) and Non-Pre-Trained (NPT) models to converge to a local
improvements compared to the non-pre-trained model (p-value                           validation loss minimum (Table IV), it clearly appears that pre-
< 10−5 for both). Moreover, they were shown to perform                                training allows for a much faster fine tuning, as the number
significantly better than channel mixing (p-values: 0.0024 for                        of epochs required to find a minimum is halved (going down
shuffling and 0.0011 for hybrid) and white noise replacement                          from 8 epochs to 4) when the only difference between the
(p-values: 0.0132 for shuffling and 0.0088 for hybrid). How-                          models is whether the starting weights are random or issued
ever, it is worth noting that the standard deviation of the EOC                       from pre-training. To put it differently, once the initial cost
for these two pre-training methods is higher than that of the                         of pre-training the model on an important amount of data
other alterations.                                                                    is incurred, it will serve as a foundational point for various
   To investigate a potential trade-off between the speed of                          related tasks, thereby reducing their fine-tuning duration.
convergence (determined by the EOC) during pre-training and                              Turning our attention towards model performance, the eval-
the minimum validation loss, we conducted a linear regres-                            uation of PT and NPT, summarized in Table V, reveals
sion analysis. The results (Table III) revealed that the EOC                          improvements in all assessed metrics when employing our pre-
explained only a small portion of the variance in the minimum                         training method before fine-tuning. In particular, the test loss
validation loss, with the highest R2 -score being slightly above                      reduces from 0.1939 in the absence of pre-training to 0.1748
0.25. This led to the conclusion that earlier convergence during                      when initializing with pre-trained weights. This reduction has
pre-training did not compromise the validation loss.                                  a positive cascading effect on test accuracy and AUC.
   Based on the gathered results, datasets with the shuffling                            Taken together, these findings indicate that the pre-training
alteration proved to be the most effective for pre-training,                          datasets developed in this study not only accelerate model
significantly improving both EOC and minimum validation                               convergence during task-specific training but also contribute to
loss. Therefore, a dataset with this alteration pre-trained the                       the creation of models with better classification performance
model in the seizure forecasting task.                                                compared to models lacking pre-training.
   The hybrid pre-training approach, although significantly
reducing the EOC, did not exhibit a significant improvement                                      VI. C ONCLUSION AND FUTURE WORKS
in the minimum validation loss. Exploring alternative methods                            In this study, we devised three distinct methods for pre-
of hybrid pre-training, such as applying multiple alterations                         training deep learning models on EEG tasks using unlabeled

                           TABLE V                                                                 R EFERENCES
   C OMPARISON OF THE MODEL PERFORMANCES AFTER FINE - TUNING
       DEPENDING ON WHETHER IT WAS PRE - TRAINED OR NOT.             [1] A. Vaswani, N. Shazeer, N. Parmar, J. Uszkoreit, L. Jones, A. N. Gomez,
                                                                         L. u. Kaiser, and I. Polosukhin, “Attention is all you need,” in Advances
                                                                         in Neural Information Processing Systems, vol. 30. Curran Associates,
       Metric                             PT       NPT                   Inc., 2017.
                                                                     [2] J. Vig, “A multiscale visualization of attention in the transformer model,”
       Validation loss at EOC            0.1689   0.2035                 2019.
       Validation accuracy at EOC [%]     92.15    90.43             [3] A. Dosovitskiy, L. Beyer, A. Kolesnikov, D. Weissenborn, X. Zhai,
       Validation AUC at EOC             0.9719   0.9630                 T. Unterthiner, M. Dehghani, M. Minderer, G. Heigold, S. Gelly,
                                                                         J. Uszkoreit, and N. Houlsby, “An image is worth 16x16 words:
       Test loss                         0.1748   0.1939                 Transformers for image recognition at scale,” 2021.
       Test accuracy [%]                  92.16    90.93             [4] Z. Wang, Y. Wang, C. Hu, Z. Yin, and Y. Song, “Transformers for eeg-
       Test AUC                          0.9702   0.9648                 based emotion recognition: A hierarchical spatial information learning
                                                                         model,” IEEE Sensors Journal, vol. 22, no. 5, pp. 4359–4368, 2022.
                                                                     [5] Y. Song, Q. Zheng, B. Liu, and X. Gao, “Eeg conformer: Convolutional
                                                                         transformer for eeg decoding and visualization,” IEEE Transactions on
                                                                         Neural Systems and Rehabilitation Engineering, 2022.
data. These techniques all revolve around the core task of           [6] J. Xie, J. Zhang, J. Sun, Z. Ma, L. Qin, G. Li, H. Zhou, and Y. Zhan,
EEG identification within a variety of multi-channel signals,            “A transformer-based approach combining deep learning network and
aiming to impart the model with essential intrinsic properties           spatial-temporal information for raw eeg classification,” IEEE Transac-
                                                                         tions on Neural Systems and Rehabilitation Engineering, vol. 30, pp.
of EEG, such as its characteristic frequency behavior and                2126–2136, 2022.
channel correlations.                                                [7] R. Hussein, S. Lee, and R. Ward, “Multi-channel vision transformer for
   Our findings demonstrate a consistent and significant im-             epileptic seizure prediction,” Biomedicines, vol. 10, no. 7, p. 1551, 2022.
                                                                     [8] J. Yan, J. Li, H. Xu, Y. Yu, and T. Xu, “Seizure prediction based
provement in training time for models pre-trained with any               on transformer using scalp electroencephalogram,” Applied Sciences,
of the designed pre-training methods compared to models                  vol. 12, no. 9, p. 4158, 2022.
initialized with random weights. Additionally, one specific pre-     [9] T. Zhang, “The value of unlabeled data for classification problems,” in
                                                                         Proceedings of the Seventeenth International Conference on Machine
training approach, involving the shuffling of EEG channels               Learning,(Langley, P., ed.), vol. 20. Citeseer, 2000.
and training the model to distinguish shuffled from unaltered       [10] L. Torrey and J. Shavlik, “Transfer learning,” in Handbook of research
EEG data, stands out by substantially enhancing minimum                  on machine learning applications and trends: algorithms, methods, and
                                                                         techniques. IGI global, 2010, pp. 242–264.
validation loss when compared to non-pre-trained models.            [11] D. Spathis, I. Perez-Pozuelo, L. Marques-Fernandez, and C. Mascolo,
   The applicability of this specific pre-training method was            “Breaking away from labels: The promise of self-supervised machine
further validated in the context of a seizure forecasting task,          learning in intelligent health,” Patterns, vol. 3, no. 2, 2022.
                                                                    [12] V. Shah, E. Von Weltin, S. Lopez, J. R. McHugh, L. Veloso, M. Gol-
leveraging the Temple University Seizure Detection Corpus. In            mohammadi, I. Obeid, and J. Picone, “The temple university hospital
this task, the pre-trained model not only exhibited significantly        seizure detection corpus,” Frontiers in neuroinformatics, vol. 12, p. 83,
faster training, converging to optimal performance in less than          2018.
                                                                    [13] I. Obeid and J. Picone, “The temple university hospital eeg data corpus,”
half the epochs required by an identical non-pre-trained model,          Frontiers in neuroscience, vol. 10, p. 196, 2016.
but also achieved superior results in terms of loss, accuracy,      [14] H. H. Jasper, “Report of the committee on methods of clinical ex-
and AUC for both the validation and test sets.                           amination in electroencephalography: 1957,” Electroencephalogr Clin
                                                                         Neurophysiol, vol. 10, pp. 370–375, 1958.
   Moving forward, future researches building upon the results      [15] H. Namazi and V. V. Kulish, “Mathematical modeling of human brain
of this study should explore the performances of the proposed            neuronal activity in the absence of external stimuli,” Journal of Medical
pre-training techniques on a broader range of EEG datasets               Imaging and Health Informatics, vol. 2, no. 4, pp. 400–407, 2012.
                                                                    [16] R. Bhavsar, Y. Sun, N. Helian, N. Davey, D. Mayor, and T. Steffert,
and applications. In particular, there’s a need to assess the ef-        “The correlation between eeg signals as measured in different positions
fectiveness of these pre-training methods for different models           on scalp varying with distance,” Procedia computer science, vol. 123,
and architectures, with a focus on the less data-greedy ones.            pp. 92–97, 2018.
                                                                    [17] S. Mallat, Time meets frequency. Elsevier, 1999, ch. 4, pp. 102–115.
   In conclusion, our research underscores the significance         [18] I. Loshchilov and F. Hutter, “Decoupled weight decay regularization,”
of pre-training in the context of EEG signal analysis, while             2019.
also exploiting more easily accessible and otherwise useless        [19] B. L. Welch, “The generalization of ‘student’s’problem when several
                                                                         different population varlances are involved,” Biometrika, vol. 34, no.
unlabeled data. These findings open doors to the exploitation            1-2, pp. 28–35, 1947.
of more data-greedy architectures in the field of EEG classifi-
cation and allows to build general models whose weights can
serve as a basis for many specific task requiring EEG analysis.
                     C ODE AVAILABILITY
   The code developed to generate the pre-training datasets
from unlabeled data is available at the following GitHub
repository: https://github.com/tbary/EEGPreTrainingDatasets.
Researchers can access and utilize this code for further in-
vestigation and experimentation.
```
