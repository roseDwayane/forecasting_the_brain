---
citation_key: "QiEtAl2025"
paper_id: "paper_127"
title: "A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures Using EEG Signals."
authors: "Longfei Qi; Shasha Yuan; Feng Li; Junliang Shang; Juan Wang; Shihan Wang"
year: 2025
doi: "10.1142/s0129065725500509"
source: "publisher-pdf (doi: 10.1142/s0129065725500509)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures Using EEG Signals.

**Citation:** `QiEtAl2025` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1142/s0129065725500509](https://doi.org/10.1142/s0129065725500509)
**Source PDF:** `full_pdf/Longfei2025.pdf`

## Abstract

The models used to predict epileptic seizures based on electroencephalogram (EEG) signals often encounter substantial challenges due to the requirement for large, labeled datasets and the inherent complexity of EEG data, which hinders their robustness and generalization capability. This study proposes CLResNet, a framework for predicting epileptic seizures, which combines contrastive self-supervised learning with a modified deep residual neural network to address the above challenges. In contrast to traditional models, CLResNet uses unlabeled EEG data for pre-training to extract robust feature representations. It is then fine-tuned on a smaller labeled dataset to significantly reduce its reliance on labeled data while improving its efficiency and predictive accuracy. The contrastive learning (CL) framework enhances the ability of the model to distinguish between preictal and interictal states, thus improving its robustness and generalizability. The architecture of CLResNet contains residual connections that enable it to learn deep features of the data and ensure an efficient gradient flow. The results of the evaluation of the model on the CHB-MIT dataset showed that it outperformed prevalent methods in the field, with an accuracy of 92.97%, sensitivity of 94.18%, and false-positive rate of 0.043/h. On the Siena dataset, the model also achieved competitive performance, with an accuracy of 92.79%, a sensitivity of 91.47%, and a false-positive rate of 0.041/h. These results confirm the effectiveness of CLResNet in addressing variations in EEG data, and show that contrastive self-supervised learning is a robust and accurate approach for predicting seizures.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
OPEN ACCESS
                                                                                                                                           International Journal of Neural Systems, Vol. 35, No. 10 (2025) 2550050 (16 pages)
                                                                                                                                           .
                                                                                                                                           # The Author(s)
                                                                                                                                            c
                                                                                                                                           DOI: 10.1142/S0129065725500509


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                       A Contrastive Learning-Enhanced Residual Network for Predicting
                                                                                                                                                                     Epileptic Seizures Using EEG Signals

                                                                                                                                                    Longfei Qi , Shasha Yuan *, Feng Li , Junliang Shang , Juan Wang and Shihan Wang
                                                                                                                                                                        School of Computer Science, Qufu Normal University,
                                                                                                                                                                                    Rizhao 276826, P. R. China
                                                                                                                                                                                        *jiayouyss@126.com


                                                                                                                                                                                              Received 22 January 2025
                                                                                                                                                                                               Accepted 18 June 2025
                                                                                                                                                                                            Published Online 16 July 2025


                                                                                                                                                    The models used to predict epileptic seizures based on electroencephalogram (EEG) signals often encounter
                                                                                                                                                    substantial challenges due to the requirement for large, labeled datasets and the inherent complexity of EEG
                                                                                                                                                    data, which hinders their robustness and generalization capability. This study proposes CLResNet,
                                                                                                                                                    a framework for predicting epileptic seizures, which combines contrastive self-supervised learning with a
                                                                                                                                                    modi¯ed deep residual neural network to address the above challenges. In contrast to traditional models,
                                                                                                                                                    CLResNet uses unlabeled EEG data for pre-training to extract robust feature representations. It is then ¯ne-
                                                                                                                                                    tuned on a smaller labeled dataset to signi¯cantly reduce its reliance on labeled data while improving its


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                    e±ciency and predictive accuracy. The contrastive learning (CL) framework enhances the ability of the model
                                                                                                                                                    to distinguish between preictal and interictal states, thus improving its robustness and generalizability. The
                                                                                                                                                    architecture of CLResNet contains residual connections that enable it to learn deep features of the data and
                                                                                                                                                    ensure an e±cient gradient °ow. The results of the evaluation of the model on the CHB-MIT dataset showed
                                                                                                                                                    that it outperformed prevalent methods in the ¯eld, with an accuracy of 92.97%, sensitivity of 94.18%, and
                                                                                                                                                    false-positive rate of 0.043/h. On the Siena dataset, the model also achieved competitive performance, with an
                                                                                                                                                    accuracy of 92.79%, a sensitivity of 91.47%, and a false-positive rate of 0.041/h. These results con¯rm the
                                                                                                                                                    e®ectiveness of CLResNet in addressing variations in EEG data, and show that contrastive self-supervised
                                                                                                                                                    learning is a robust and accurate approach for predicting seizures.

                                                                                                                                                    Keywords: Epileptic seizure prediction; EEG; contrastive learning; improved ResNet.


                                                                                                                                           1. Introduction                                                            one-third of them remain resistant to currently
                                                                                                                                           Epilepsy is a common neurological disorder that is                         available treatments, this highlights the critical need
                                                                                                                                           characterized by abnormal neuronal ¯rings that lead to                     for alternative approaches.2 The early prediction of
                                                                                                                                           recurrent seizures that are often unpredictable. These                     seizures provides the opportunity for timely interven-
                                                                                                                                           episodes not only compromise the patients' quality of                      tions through preventive measures to mitigate their
                                                                                                                                           life, but also pose serious, and sometimes life-threat-                    physical, psychological, and social consequences.
                                                                                                                                           ening, risks.1 While medical and surgical interventions                        Recent advances in Computer Science and Bio-
                                                                                                                                           can control seizures in many patients, approximately                       medical Engineering have accelerated research on

                                                                                                                                           * Corresponding author.

                                                                                                                                           This is an Open Access article published by World Scienti¯c Publishing Company. It is distributed under the terms of the
                                                                                                                                           Creative Commons Attribution 4.0 (CC BY) License, which permits use, distribution and reproduction in any medium,
                                                                                                                                           provided the original work is properly cited.

                                                                                                                                                                                                          2550050-1

                                                                                                                                           L. Qi et al.


                                                                                                                                           the prediction of seizures based on electroencepha-                  information related to epilepsy seizures.16,17 Shanir
                                                                                                                                           logram (EEG) technology. EEG, which records real-                    et al. developed a seizure detection method using 1D-
                                                                                                                                           time brain activity, provides a valuable platform for                LBP and KNN,18 whereas Nogay and Adeli
                                                                                                                                           identifying the precursory patterns that precede                     employed transfer learning with a pre-trained Alex-
                                                                                                                                           seizures.3 However, the inherent complexity and                      Net on EEG-derived spectrograms.19 ResNet is a


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           inter-individual variability of EEG signals pose                     robust alternative to the CNN that can ensure a
                                                                                                                                           signi¯cant challenges to such identi¯cation. Tradi-                  stable gradient °ow and improved predictive per-
                                                                                                                                           tional methods of signal processing often struggle to                formance by the model.20
                                                                                                                                           manage these complexities, which underscores the                         Originally designed for image classi¯cation,
                                                                                                                                           need for methods that can ensure high predictive                     ResNet has been successfully adapted to such domains
                                                                                                                                           accuracy and robustness. Machine learning (ML)                       as medical signal processing.21 Its use of residual
                                                                                                                                           and deep learning (DL) have lately emerged as                        connections enables e±cient feature extraction across
                                                                                                                                           transformative tools in this domain,4 as they enable                 layers, thus making it ideal for application to high-
                                                                                                                                           automated feature extraction from large-scale EEG                    dimensional time-series data, like EEG data. More-
                                                                                                                                           data to facilitate the development of sophisticated                  over, the performance of ResNet improves with the
                                                                                                                                           predictive models.5 Gu and Adeli proposed an EEG-                    size of the dataset, which allows it to fully exploit the
                                                                                                                                           based automated model for assessing the risk of                      growing availability of digitized EEG data. Singh and
                                                                                                                                           sudden unexpected death in epilepsy (SUDEP).6                        Lobiyal suggested a hybrid ResNet50-LSTM model
                                                                                                                                           Perez-Sanchez et al. developed a seizure prediction                  for predicting seizures,22 while Jiang et al. developed
                                                                                                                                           model leveraging ECG signals, expanding the scope                    TASM ResNet by integrating a temporal attention
                                                                                                                                           beyond conventional EEG-based approaches.7 Such                      module with a pre-trained ResNet.23 Both models
                                                                                                                                           approaches excel in terms of handling high-dimen-                    achieved high accuracy on intracranial EEG signals to
                                                                                                                                           sional data, identifying intricate patterns, and cap-                highlight the potential of ResNet in this ¯eld.
                                                                                                                                           turing EEG Signal complexity and dynamics.                               Contrastive learning (CL) has gained signi¯cant


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           Despite their potential, however, the issues of data                 attention in recent research. Along with other self-
                                                                                                                                           imbalance, variations in EEG signals across patients,                supervised learning methods, it has become a preva-
                                                                                                                                           and the computational demands of real-time pro-                      lent approach across ¯elds ranging from computer
                                                                                                                                           cessing pose signi¯cant challenges to such approa-                   vision and natural language processing to medical
                                                                                                                                           ches, and addressing them requires further research                  signal analysis.24 CL outperforms supervised learning
                                                                                                                                           and methodological re¯nement.8                                       in extracting the features of EEG data against the
                                                                                                                                               Advancements in computational algorithms have                    backdrop of representation learning. Feng et al. pro-
                                                                                                                                           been largely driven by deep neural networks.9,10 DL                  posed a semantically attentive CL strategy (C-SCL)
                                                                                                                                           methods can reduce the need for manual interven-                     to address discrepancies between EEG signals and
                                                                                                                                           tions and accurately extract features from complex                   their textual representations.25 Chang et al. devel-
                                                                                                                                           EEG signals to predict epileptic seizures. Many                      oped DSSNet to generate meaningful multi-view
                                                                                                                                           studies on seizure prediction have used CNN meth-                    representations to reduce dependence on labeled data
                                                                                                                                           ods.11,12 Truong et al. proposed a three-block CNN                   while enhancing the accuracy of automatic sleep
                                                                                                                                           structure containing normalization, convolutional,                   staging.26 Zhao et al. enhanced the classi¯cation ac-
                                                                                                                                           and max-pooling layers,13 while Ozcan et al. spatially               curacy of epileptic seizures by employing a model that
                                                                                                                                           arranged electrode channels from the CHB-MIT                         incorporated supervised contrastive loss at the pro-
                                                                                                                                           dataset to construct 3D inputs that were processed                   jection layer alongside cross-entropy loss at the clas-
                                                                                                                                           through four convolutional and three fully-connected                 si¯cation layer.27 Similarly, Guo et al. leveraged CL
                                                                                                                                           layers.14 However, the traditional CNN frequently                    to integrate cross-subject EEG features and improve
                                                                                                                                           fail to model extended data correlations,15 and is                   the accuracy of prediction of seizures.28 However,
                                                                                                                                           susceptible to the problem of the vanishing gradient                 these methods rely on supervised CL based on labeled
                                                                                                                                           that a®licts deep networks. In recent years, Zhang                   data, which makes seizure prediction problematic in
                                                                                                                                           et al. proposed that the combination of Transformer                  scenarios in which labeled data are scarce or alto-
                                                                                                                                           and convolutional networks can e®ectively extract                    gether unavailable.


                                                                                                                                                                                                    2550050-2

                                                                                                                                                                                      A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                               This study proposes a model for epileptic seizure                          Sec. 5 summarizes the key ¯ndings and suggests
                                                                                                                                           prediction, named CLResNet, which integrates CL                                potential directions for future research.
                                                                                                                                           with residual networks. CL is used to construct
                                                                                                                                           similar and dissimilar pairs of samples to accurately
                                                                                                                                                                                                                          2. EEG Datasets
                                                                                                                                           learn the features of the data without requiring an


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           extensive labeled dataset. It can capture subtle dif-                          The CHB-MIT Scalp EEG Database and the Siena
                                                                                                                                           ferences between normal and abnormal patterns of                               scalp EEG database were used in this study. The
                                                                                                                                           EEG activity even with a limited number of labeled                             CHB-MIT Scalp EEG Database is a publicly avail-
                                                                                                                                           samples, where this enhances both the discriminative                           able dataset, which is a widely recognized resource for
                                                                                                                                           capability and generalizability of the model. Owing                            seizure detection and prediction research.3 Therefore,
                                                                                                                                           to their deep architecture and robust capability of                            this study primarily conducts experiments using this
                                                                                                                                           feature extraction, residual networks enable the                               dataset. The dataset comprises EEG recordings from
                                                                                                                                           precise identi¯cation of critical features in complex,                         23 epilepsy patients. The recordings were collected
                                                                                                                                           temporal EEG signals. By combining the strength of                             following the international 10–20 system for electrode
                                                                                                                                           self-supervised CL with the capabilities of deep re-                           placement, with signals digitized at a sampling rate of
                                                                                                                                           presentation of residual networks, CLResNet sur-                               256 Hz. In addition, the Siena Scalp EEG dataset is
                                                                                                                                           passes baseline models in terms of the accuracy of its                         also applied to further demonstrate the generaliz-
                                                                                                                                           predictions of epileptic seizures.                                             ability of the proposed method, which includes EEG
                                                                                                                                               The structure of this paper is as follows: Section 2                       recordings from 14 epilepsy patients. The EEG sig-
                                                                                                                                           introduces the database and methodology utilized in                            nals were recorded using the international 10–20
                                                                                                                                           this study. Section 3 presents the experimental                                electrode system with a sampling rate of 512 Hz. In
                                                                                                                                           results, comparing the proposed method with exist-                             total, we conducted seizure prediction experiments
                                                                                                                                           ing approaches in the ¯eld. In Sec. 4, the perfor-                             on 181 seizure events and over 500 ho of EEG
                                                                                                                                           mance of the proposed model is analyzed and                                    recordings from both datasets.


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           discussed in relation to previous studies. Lastly,                                 As shown in Fig. 1, the preictal period is de¯ned as
                                                                                                                                                                                                                          the 30 min preceding seizure onset, while the interictal
                                                                                                                                                                                                                          period refers to the remaining time period excluding
                                                                                                                                                                                                                          the ictal and preictal interval. For some patients,
                                                                                                                                                                                                                          some seizures occurred in close succession with the
                                                                                                                                                                                                                          preictal data being less than 30 min, and thus adja-
                                                                                                                                                                                                                          cent seizure events were merged into one seizure event
                                                                                                                                                                                                                          for analysis. The speci¯cs of the two EEG datasets
                                                                                                                                           Fig. 1.   De¯nitions of preictal, ictal, and interictal periods.               utilized in this research are outlined in Table 1.

                                                                                                                                                                   Table 1.     Details of the CHB-MIT dataset and Siena dataset used in this study.

                                                                                                                                                       Dataset        Patient     Duration of interictal (h)       Duration of preictal (h)    Number of used seizures

                                                                                                                                                       CHB-MIT         chb01                 22.80                              3.50                        7
                                                                                                                                                                       chb02                  6.71                              1.50                        3
                                                                                                                                                                       chb03                  6.00                              3.00                        7
                                                                                                                                                                       chb04                 22.25                              2.00                        4
                                                                                                                                                                       chb05                 18.06                              2.50                        5
                                                                                                                                                                       chb06                 40.35                              3.96                        9
                                                                                                                                                                       chb07                 14.25                              1.50                        3
                                                                                                                                                                       chb08                 19.66                              2.50                        5
                                                                                                                                                                       chb09                 16.78                              1.50                        4
                                                                                                                                                                       chb10                 20.57                              3.37                        7
                                                                                                                                                                       chb11                  1.80                              0.89                        3
                                                                                                                                                                       chb12                 14.03                              3.25                        7
                                                                                                                                                                       chb13                 14.73                              3.00                        8


                                                                                                                                                                                                              2550050-3

                                                                                                                                           L. Qi et al.


                                                                                                                                                                                                Table 1.   (Continued )

                                                                                                                                                          Dataset   Patient   Duration of interictal (h)    Duration of preictal (h)   Number of used seizures

                                                                                                                                                                    chb14               16.15                          3.74                       8


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                    chb15               22.67                          3.50                       7
                                                                                                                                                                    chb16                9.42                          1.59                       6
                                                                                                                                                                    chb17                6.85                          1.50                       5
                                                                                                                                                                    chb18                5.47                          2.48                       6
                                                                                                                                                                    chb19                1.92                          1.08                       3
                                                                                                                                                                    chb20                3.62                          3.53                       8
                                                                                                                                                                    chb21                7.48                          2.00                       4
                                                                                                                                                                    chb22               12.58                          1.35                       3
                                                                                                                                                                    chb23                9.08                          3.28                       5
                                                                                                                                                                    chb24               13.13                          7.00                       8
                                                                                                                                                                    Total              326.36                         63.52                     135
                                                                                                                                                          Siena     PN00                 1.28                          1.21                       4
                                                                                                                                                                    PN01                10.35                          1.00                       2
                                                                                                                                                                    PN03                15.00                          1.00                       2
                                                                                                                                                                    PN05                 4.48                          1.50                       3
                                                                                                                                                                    PN06                 9.53                          2.50                       5
                                                                                                                                                                    PN07                 5.08                          0.50                       1
                                                                                                                                                                    PN09                 5.33                          1.50                       3
                                                                                                                                                                    PN10                16.85                          5.00                      10
                                                                                                                                                                    PN11                 1.90                          0.50                       1
                                                                                                                                                                    PN12                 3.42                          1.58                       4
                                                                                                                                                                    PN13                 7.15                          1.50                       3
                                                                                                                                                                    PN14                14.80                          2.00                       4


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                                    PN16                 3.82                          1.00                       2
                                                                                                                                                                    PN17                 4.10                          1.00                       2
                                                                                                                                                                    Total              103.09                         21.79                      46


                                                                                                                                           3. Method                                                              high-pass ¯lter was implemented to remove
                                                                                                                                           The proposed method comprises three key compo-                         low-frequency elements, such as baseline drift and
                                                                                                                                           nents: pre-processing, the proposed CLResNet                           DC o®sets. This process focused on high-frequency
                                                                                                                                           model, and post-processing. We describe each com-                      variations, which are more relevant when detecting
                                                                                                                                           ponent in detail in the following sections.                            epileptic seizures because low-frequency variations
                                                                                                                                                                                                                  are typically not correlated with seizure-related
                                                                                                                                                                                                                  neural activity.
                                                                                                                                           3.1. Pre-processing                                                        A major challenge in predicting epileptic seizures
                                                                                                                                           Two bandstop ¯lters were used to reduce interfer-                      is data imbalance, as seizure durations in the dataset
                                                                                                                                           ence in speci¯c frequency ranges due to noise from                     are often considerably shorter than the interictal
                                                                                                                                           the power supply and other artifacts. The ¯rst ¯lter                   periods, resulting in a substantial disparity in the
                                                                                                                                           targeted frequencies in the range of 117–123 Hz,                       number of data points across categories. This can
                                                                                                                                           while the second targeted those in the range of 57–                    adversely a®ect predictive performance. To address
                                                                                                                                           63 Hz, and this reduced noise from power sources                       the issue, we employed continuous and overlapping
                                                                                                                                           operating at 60 Hz. These frequency ranges were se-                    sampling techniques. Let L represent the size of the
                                                                                                                                           lected to suppress the power line interference and its                 window for overlapping samples, M represent pre-
                                                                                                                                           ¯rst harmonic, which commonly appear in EEG                            ictal signal duration, while N represents interictal
                                                                                                                                           signals recorded in regions with 60 Hz electricity. The                signal duration. The number of segments generated
                                                                                                                                           slightly wider bandstop design helps eliminate spec-                   for the preictal period after oversampling can then be
                                                                                                                                           tral leakage and improves overall signal quality. To                   calculated as ðM  LÞ=L þ 1, while that for the
                                                                                                                                           further enhance the quality of the signals, a 1 Hz                     corresponding interictal period is ðN  LÞ=L þ 1.

                                                                                                                                                                                                      2550050-4

                                                                                                                                                                                 A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                           We set L ¼ 4 s in this experiment. If the interictal                    enhanced performance and reliability in the context
                                                                                                                                           data still outweighed the preictal data during the                      of seizure prediction by integrating CL with
                                                                                                                                           training of the model, a portion of the former was                      ¯ne-tuning.
                                                                                                                                           randomly discarded to ensure a balanced ratio be-
                                                                                                                                           tween the categories.


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                                                                   3.2.1. Data augmentation
                                                                                                                                                                                                                   Data augmentation plays a central role in CL, and
                                                                                                                                           3.2. CLResNet                                                           enables the model to identify intrinsic data struc-
                                                                                                                                           The proposed CLResNet framework for seizure pre-                        tures without labels by creating diverse \views" of
                                                                                                                                           diction, illustrated in Fig. 2, comprises three key                     each sample. The classic method of CL, SimCLR,
                                                                                                                                           stages: Pre-training, ¯ne-tuning, and testing. During                   focuses on transformations such as color adjustments
                                                                                                                                           the pre-training stage, raw EEG signals are aug-                        and °ipping in image-related data to generate pairs
                                                                                                                                           mented to generate diverse representations that are                     of positive samples from di®erent perspectives.29 By
                                                                                                                                           then processed by an improved ResNet-based feature                      contrast, Qin et al. introduced the spatial variation
                                                                                                                                           extractor to learn high-dimensional embeddings. The                     generation algorithm, which improves data diversity
                                                                                                                                           model is optimized based on contrastive loss by en-                     by enhancing the density of sample neighborhoods,
                                                                                                                                           abling it to distinguish between positive and nega-                     thereby improving the robustness of models used to
                                                                                                                                           tive pairs of samples to extract meaningful and                         classify motor imagery.30 The spatial variation gen-
                                                                                                                                           robust features. During the ¯ne-tuning stage, the                       eration approach is better suited to capture spatial
                                                                                                                                           model undergoes additional training using labeled                       structural variations in EEG signals. It enables ac-
                                                                                                                                           EEG data to classify the interictal and preictal states                 curate simulations of subtle changes in electrode
                                                                                                                                           by minimizing cross-entropy loss and ensuring task-                     placement and the process of signal acquisition. In
                                                                                                                                           speci¯c feature re¯nement. In the testing stage, the                    light of the characteristics of EEG data, we propose
                                                                                                                                           ¯ne-tuned and improved ResNet processes EEG                             the following data augmentation strategies. Figure 3


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           signals to extract the features, which are subse-                       presents sample transformed signals.
                                                                                                                                           quently analyzed by a post-processing module to                            Rotation: Random rotations involve applying
                                                                                                                                           generate probability distributions of seizures over                     random angular transformations to EEG signals in
                                                                                                                                           time. If a seizure is predicted, an alarm is triggered to               the time domain to simulate signal variations caused
                                                                                                                                           enable timely intervention. This framework achieves                     by changes in head posture or electrode orientation.


                                                                                                                                                                                       Fig. 2.   The proposed CLResNet.


                                                                                                                                                                                                       2550050-5

                                                                                                                                           L. Qi et al.


                                                                                                                                                                                                                        Flipping: Flipping augmentation is performed
                                                                                                                                                                                                                     by randomly mirroring EEG signals along the
                                                                                                                                                                                                                     channel dimension to simulate spatial distortions
                                                                                                                                                                                                                     caused by minor electrode placement shifts, which
                                                                                                                                                                                                                     are commonly observed in real-world EEG record-


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                                                                     ings. This operation introduces spatial variability
                                                                                                                                                                                                                     while preserving the underlying seizure-related pat-
                                                                                                                                                                                                                     terns, thereby maintaining semantic consistency es-
                                                                                                                                                                                                                     sential for CL. By increasing data diversity and
                                                                                                                                                                                                                     enriching the construction of positive and negative
                                                                                                                                                                                                                     pairs within the CL framework, this augmentation
                                                                                                                                                                                                                     enhances the quality of learned representations and
                                                                                                                                                                                                                     improves the model's generalization performance.
                                                                                                                                                                                                                        Pairs of positive samples are generated during
                                                                                                                                                                                                                     training to represent diverse perspectives by ran-
                                                                                                                                                                                                                     domly applying the above strategies for data
                                                                                                                                           Fig. 3. Visual comparison of EEG signal augmentation
                                                                                                                                                                                                                     augmentation. Pairs of negative samples are
                                                                                                                                           method: (a) Original EEG signal, (b) rotation, (c) Scaling,
                                                                                                                                           (d) distortion, and (e) °ipping.                                          constructed by randomly selecting other samples
                                                                                                                                                                                                                     from the batch.
                                                                                                                                           The rotation angles are sampled from a normal
                                                                                                                                           distribution with a mean of 0 and a standard devi-                        3.2.2. Contrastive loss function
                                                                                                                                           ation of 0.1, and are respectively applied to sine and
                                                                                                                                                                                                                     The contrastive loss is utilized to optimize the
                                                                                                                                           cosine transformation terms. This allows the aug-
                                                                                                                                                                                                                     model's capability for feature extraction during
                                                                                                                                           mented signals to exhibit variations in both ampli-


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                                                                                     training. This loss function aims to bring the repre-
                                                                                                                                           tude and phase within a reasonable range. This
                                                                                                                                                                                                                     sentations of augmented views of the same signal
                                                                                                                                           strategy introduces diverse signal morphologies,
                                                                                                                                                                                                                     closer together while pushing those of di®erent sig-
                                                                                                                                           thereby enhancing the model's robustness to spatial
                                                                                                                                                                                                                     nals farther apart. Before calculating the similarity
                                                                                                                                           variations and electrode placement inconsistencies.
                                                                                                                                                                                                                     between the signal representations, we standardize
                                                                                                                                              Scaling: Signal scaling aims to simulate ampli-
                                                                                                                                                                                                                     the input signals to guarantee that the magnitude of
                                                                                                                                           tude °uctuations in EEG signals resulting from dif-
                                                                                                                                                                                                                     each feature vector is normalized to one. This elim-
                                                                                                                                           ferences in sampling frequency or physiological
                                                                                                                                                                                                                     inates the in°uence of the scale of the features on the
                                                                                                                                           variations across subjects. During augmentation,
                                                                                                                                                                                                                     calculation of similarity. We compute the cosine
                                                                                                                                           each signal is multiplied by a randomly sampled
                                                                                                                                                                                                                     similarity of each pair of samples (positive or nega-
                                                                                                                                           scaling factor within the range of [0.7,1.3], generating
                                                                                                                                                                                                                     tive). The cosine similarity of two input representa-
                                                                                                                                           new samples that vary in amplitude while preserving                               ð1Þ      ð2Þ
                                                                                                                                                                                                                     tions x i and x j is expressed as follows:
                                                                                                                                           their temporal structure. This enhances the model's
                                                                                                                                                                                                                                                       ð1Þ     ð2Þ
                                                                                                                                           ability to generalize across signals with di®ering                                          ð1Þ   ð2Þ     xi  xj
                                                                                                                                           amplitude distributions.                                                             simðx i ; x j Þ ¼      ð1Þ     ð2Þ
                                                                                                                                                                                                                                                                       :   ð1Þ
                                                                                                                                                                                                                                                    jjx i jjjjx j jj
                                                                                                                                              Distortion: The method is implemented by in-
                                                                                                                                           troducing Gaussian noise with a mean of 0 and a                              Cosine similarity measures how similar two vec-
                                                                                                                                           standard deviation ranging from 0.01 to 0.05 into the                     tors are by calculating the angle between them.
                                                                                                                                           original signals. This simulates common types of in-                      Greater similarity scores indicate proximity in fea-
                                                                                                                                           terference encountered during EEG acquisition, such                       ture space between compared signals. To prevent the
                                                                                                                                           as electromyographic noise, power line interference,                      model from comparing a sample with itself during
                                                                                                                                           and electrode contact artifacts. This augmentation                        training, we introduce a mask, with values of one on
                                                                                                                                           improves the model's robustness in low signal-to-                         the diagonal and zero elsewhere, to ensure that each
                                                                                                                                           noise ratio conditions and helps maintain predictive                      sample is compared only to other samples. The loss
                                                                                                                                           accuracy when processing noisy inputs.                                    function enhances the model's performance by


                                                                                                                                                                                                         2550050-6

                                                                                                                                                                                           A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                           utilizing cross-entropy loss:                                                           accurately capture the features of EEG signals to
                                                                                                                                                                                          ð1Þ   ð2Þ
                                                                                                                                                                                                                                  ensure a high accuracy of classi¯cation and robust-
                                                                                                                                                                                    simðx i ;x j Þ
                                                                                                                                                        X
                                                                                                                                                        N                 exp                                                     ness. The details are shown in Fig. 4(a).
                                                                                                                                            Loss ¼          log 2N                                          ; ð2Þ                  The input and feature extraction layer processes
                                                                                                                                                     N i¼1       P                               ð1Þ   ð2Þ
                                                                                                                                                                                           simðx i ;x j Þ
                                                                                                                                                                         l½k6¼i exp                                               multi-channel EEG signals to extract local temporal


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                                                 
                                                                                                                                                                   j¼1
                                                                                                                                                                                                                                   features from them by using a convolutional layer
                                                                                                                                                   ð1Þ     ð2Þ
                                                                                                                                           where x i and x j represent two enhanced views of                                       that is optimized for time-series data. This layer is
                                                                                                                                           signal i, sim ( ) signi¯es the cosine similarity,                                      succeeded by batch normalization and ReLU acti-
                                                                                                                                           denotes temperature, modulating distribution                                            vation, which stabilize the training process and en-
                                                                                                                                           smoothness within CL frameworks. The numerator                                          hance the expressiveness of the extracted features.
                                                                                                                                           in the above formula represents the similarity be-                                      This design lays the foundation for the subsequent
                                                                                                                                           tween pairs of positive samples, while the denomi-                                      modules by preserving crucial patterns in the signals
                                                                                                                                           nator captures the similarity values across all pairs.                                  while reducing computational complexity.
                                                                                                                                           The aim of optimizing the loss function is to enhance                                      At the heart of the model lies the residual module,
                                                                                                                                           the similarity of positive sample pairs while increas-                                  which comprises four layers, each containing two
                                                                                                                                           ing the separation between negative sample pairs.                                       residual blocks, as illustrated in Fig. 4(b). These
                                                                                                                                           This allows the model to really get a handle on the                                     blocks contain multi-scale convolutional kernels that
                                                                                                                                           underlying signal representations.                                                      enable the model to capture diverse spatiotemporal
                                                                                                                                                                                                                                   features at various resolutions. Table 2 presents the
                                                                                                                                                                                                                                   speci¯cs concerning the model's variables. The
                                                                                                                                           3.2.3. ResNet architecture
                                                                                                                                                                                                                                   parameters used in the proposed model was deter-
                                                                                                                                           An advanced DL model based on an improved                                               mined based on a combination of empirical tuning
                                                                                                                                           ResNet architecture is introduced, which in turn is                                     and insights from previous studies in EEG-based DL.
                                                                                                                                           based on the ResNet model developed by Hannun                                           The kernel sizes, strides, and paddings for each


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           et al.31 The model is designed with four main com-                                      convolutional layer were selected according to stan-
                                                                                                                                           ponents: An input and feature extraction layer, a                                       dard practices commonly adopted in related re-
                                                                                                                                           residual module, a CL module, and a classi¯cation                                       search. The residual connections solve the problem of
                                                                                                                                           module. By leveraging multi-scale convolutional                                         the vanishing gradient and enable the e®ective
                                                                                                                                           kernels, residual connections, and CL strategies, can                                   training of the network even as its depth increases.


                                                                                                                                                                                                                          (a)


                                                                                                                                                                                                                          (b)

                                                                                                                                                      Fig. 4.   (a) The structure of the proposed ResNet model. (b) Details of the proposed Residual Block.


                                                                                                                                                                                                                       2550050-7

                                                                                                                                           L. Qi et al.


                                                                                                                                                                     Table 2.   Key parameters and the size of output of each model block.

                                                                                                                                                             Block name             Output size                          Parameters

                                                                                                                                                             Input layer           1  18  1024              k ¼ ð1; 9Þ, s ¼ ð1; 2Þ, p ¼ ð0; 4Þ
                                                                                                                                                             Residual layer 1      16  64  32      k1 ¼ ð1; 15Þ, k2 ¼ ð15; 1Þ, s1 ¼ ð1; 2Þ, s2 ¼ ð2; 1Þ


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                             Residual layer 2      32  32  16      k1 ¼ ð1; 11Þ, k2 ¼ ð11; 1Þ, s1 ¼ ð1; 2Þ, s2 ¼ ð2; 1Þ
                                                                                                                                                             Residual layer 3       64  16  8             k1 ¼ ð1; 7Þ, k2 ¼ ð3; 1Þ, s1 ¼ ð1; 2Þ
                                                                                                                                                             Residual layer 4       128  8  4             k1 ¼ ð1; 3Þ, k2 ¼ ð5; 5Þ, s1 ¼ ð1; 2Þ
                                                                                                                                                             Adaptive AvgPool           128                       Global average pooling
                                                                                                                                                             Contrastive module         256           MLP: Linear (128 ! 256), Dropout (p ¼ 0:2)
                                                                                                                                                             Classi¯cation               2             MLP: Linear (128 ! 2), Dropout (p ¼ 0:2)

                                                                                                                                                             Notes: \Output Size" represents the dimensions of the map of the features output by
                                                                                                                                                             each module. The parameters include the kernel size (k), stride (s), and padding (p).


                                                                                                                                           As the features pass through the layers of the model,                 enhances their interpretability and reliability for
                                                                                                                                           their number of dimensions decreases while the                        subsequent analysis.
                                                                                                                                           number of channels increases. This enables the ex-
                                                                                                                                           traction of abstract and high-level features.
                                                                                                                                               After passing through the residual module, the                    4. Experiments and Results
                                                                                                                                           extracted features are split into two paths. The ¯rst                 4.1. Experimental settings
                                                                                                                                           path leads to the CL module, which enhances the
                                                                                                                                                                                                                 To evaluate the performance and generalization ca-
                                                                                                                                           discriminative power of the feature representations.
                                                                                                                                                                                                                 pability of the proposed framework, experiments
                                                                                                                                           This module uses a series of fully connected layers
                                                                                                                                                                                                                 were carried out using Python 3.7, and PyTorch
                                                                                                                                           and CL to distinguish between similar but distinct


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                                                                                 1.10.0. A leave-one-out cross-validation (LOOCV)
                                                                                                                                           samples. The model achieves robust feature embed-
                                                                                                                                                                                                                 approach was employed for this assessment. It was
                                                                                                                                           dings by maximizing positive pair relatedness while
                                                                                                                                                                                                                 used to validate the model against all possible com-
                                                                                                                                           reducing negative pair relatedness. The second path
                                                                                                                                                                                                                 binations of the training set to ensure a robust as-
                                                                                                                                           connects to the classi¯cation module, which uses
                                                                                                                                                                                                                 sessment of its performance. The Adam optimizer
                                                                                                                                           fully connected layers to re¯ne the features for bi-
                                                                                                                                                                                                                 was used for parameter optimization. All experi-
                                                                                                                                           nary classi¯cation. Dropout regularization is applied
                                                                                                                                                                                                                 ments were conducted on a workstation equipped
                                                                                                                                           to prevent over¯tting, and the ¯nal layer outputs
                                                                                                                                                                                                                 with a 12th Gen Intel Core i7-12700K CPU
                                                                                                                                           the predicted probabilities of the occurrence and
                                                                                                                                                                                                                 (3.61 GHz), 64 GB RAM, and an NVIDIA GeForce
                                                                                                                                           nonoccurrence of a seizure by using a softmax
                                                                                                                                                                                                                 RTX 3080 Ti GPU.
                                                                                                                                           function.


                                                                                                                                           3.3. Post-processing                                                  4.2. Evaluation indicators
                                                                                                                                           A moving average-based method was applied to                          In this work, two kinds of evaluation metrics were
                                                                                                                                           smooth the one-dimensional time-series data, re-                      utilized to thoroughly evaluate the performance of
                                                                                                                                           ducing noise and short-term °uctuations. This                         the model: The segment-based metrics and the
                                                                                                                                           method involves sliding a window of a speci¯ed size                   event-based metrics.
                                                                                                                                           over the data and computing the average value to                         The ¯rst type of evaluation metrics based on the
                                                                                                                                           generate a smoothened output. At its core, the pro-                   predicted segments consisted of a stringent set of
                                                                                                                                           cess uses a convolution operation for averaging the                   metrics with accuracy (ACC), sensitivity (Sen), area
                                                                                                                                           data within the sliding window. To address edge                       under the curve (AUC), and p-value. ACC indicates
                                                                                                                                           e®ects, whereby the window cannot fully cover the                     the proportion of accurate predictions generated by
                                                                                                                                           data along the boundaries, a cumulative sum method                    the model, while Sen evaluates its ability to correctly
                                                                                                                                           is used along the boundaries to reduce distortion.                    identify the positive class of samples. The AUC
                                                                                                                                           This e®ectively reduces noise, stabilizes the data, and               re°ects its overall performance across threshold

                                                                                                                                                                                                     2550050-8

                                                                                                                                                                                A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                           settings, while the p-value evaluates the statistical                 prediction event.13 Thus, a correctly predicted
                                                                                                                                           signi¯cance of the model's outcomes. These metrics                    seizure event means that the prediction event is
                                                                                                                                           were calculated by using the following formulae:                      identi¯ed and the seizure indeed occurs after the
                                                                                                                                                               TP þ TN                                           SPH and within the SOP. Otherwise, it is regarded
                                                                                                                                                  ACC ¼                      100%;           ð3Þ                as a false prediction event. Based on these state-


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                          TP þ FP þ FN þ TN
                                                                                                                                                                                                                 ments, the event-based evaluation metric contains
                                                                                                                                                                   TP
                                                                                                                                                         Sen ¼           100%;               ð4Þ                three indicators: Event-based sensitivity (Sn ), false
                                                                                                                                                                TP þ FN
                                                                                                                                                                   0 1                                           prediction rate (FPR), and average prediction time.
                                                                                                                                                               X i                                               Sn is calculated as the proportion of correctly pre-
                                                                                                                                                   P -values ¼     @ AP i ð1  P Þ mi :      ð5Þ                dicted seizure events, that is, the number of correctly
                                                                                                                                                               im  m                                            predicted seizure events divide by the total number
                                                                                                                                               Here, each segment is independently classi¯ed as                  of seizures as shown in formulae (6). FPR is mea-
                                                                                                                                           either preictal or interictal. True positive (TP)                     sured as the number of false prediction event per
                                                                                                                                           occurs when a preictal segment is correctly identi¯ed                 hour. The average prediction time refers to the av-
                                                                                                                                           as preictal by the model, while false negative (FN)                   erage time interval of the alarm prior to the begin-
                                                                                                                                           refers to a preictal segment incorrectly classi¯ed as                 ning of seizure onset, which re°ects the model's
                                                                                                                                           interictal by model. Conversely, true negative (TN)                   ability to provide early warning.
                                                                                                                                           denotes a correctly identi¯ed interictal segment, and                         The number of correctly predicted seizures
                                                                                                                                                                                                                  Sn ¼
                                                                                                                                           false positive (FP) indicates an interictal segment                                 The total number of seizures
                                                                                                                                           mistakenly predicted as preictal.
                                                                                                                                                                                                                          100%;
                                                                                                                                               The event-based evaluation metric is a measure to
                                                                                                                                           better represent the performance of the prediction                                                                       ð6Þ
                                                                                                                                           algorithm for clinical application. The evaluation                               The number of false prediction events
                                                                                                                                                                                                                   FPR ¼                                          :
                                                                                                                                           followed the de¯nitions of the seizure occurrence                                      The hours of interictal


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           period (SOP) and seizure prediction horizon (SPH)                                                                      ð7Þ
                                                                                                                                           proposed by Maiwald et al.,32 as shown in Fig. 5.
                                                                                                                                           After a prediction alarm, if a seizure event does not                 4.3. Overall performance
                                                                                                                                           occur during the SPH, but during the SOP, the
                                                                                                                                                                                                                 The proposed model was evaluated on two widely
                                                                                                                                           alarm is considered to be a valid prediction alarm. In
                                                                                                                                                                                                                 used datasets: CHB-MIT and Siena. The experi-
                                                                                                                                           clinical practice, the SPH represents the interval
                                                                                                                                                                                                                 mental results are summarized in Table 3, which
                                                                                                                                           during which clinicians can intervene and implement
                                                                                                                                                                                                                 includes both segment-based and event-based per-
                                                                                                                                           preventive measures to mitigate seizures. Also, ex-
                                                                                                                                                                                                                 formance metrics. The model achieved an average
                                                                                                                                           cessively long and SOP and SPH may cause unnec-
                                                                                                                                                                                                                 ACC of 92.97% and a Sen of 89.01% on the CHB-
                                                                                                                                           essary anxiety and tension for the patient. Based on
                                                                                                                                                                                                                 MIT dataset. These results demonstrate robust per-
                                                                                                                                           this consideration, the SPH was set to 1 min, and the
                                                                                                                                                                                                                 formance in predicting seizure events at the segment
                                                                                                                                           SOP was set to 30 min in our experiments.
                                                                                                                                                                                                                 level, with an AUC of 0.927. In terms of event-based
                                                                                                                                               In this work, when eight or more consecutive
                                                                                                                                                                                                                 performance, the model achieved an average Sn of
                                                                                                                                           segments are classi¯ed as preictal by the model, we
                                                                                                                                                                                                                 94.18%, along with a low FPR of 0.043, indicating
                                                                                                                                           de¯ne this consecutive time interval as a de¯nite
                                                                                                                                                                                                                 high precision and e®ectiveness in detecting true
                                                                                                                                                                                                                 seizure events while minimizing false alarms. The
                                                                                                                                                                                                                 prediction time averaged 19.62 min, showcasing the
                                                                                                                                                                                                                 model's e±ciency in real-time applications.
                                                                                                                                                                                                                    On the Siena dataset, the model achieved an av-
                                                                                                                                                                                                                 erage ACC of 92.79%, with a Sen of 91.47%, and an
                                                                                                                                                                                                                 AUC of 0.922 at the segment level. Event-based
                                                                                                                                                                                                                 results showed an average Sn of 91.19%, with a lower
                                                                                                                                           Fig. 5. A correct seizure event alarm based on the de¯-               FPR of 0.041 compared to the CHB-MIT dataset,
                                                                                                                                           nitions of the SPH and SOP.                                           and a prediction time of 18.41 min. The Siena

                                                                                                                                                                                                     2550050-9

                                                                                                                                           L. Qi et al.


                                                                                                                                                                     Table 3.   Experimental results on the CHB-MIT dataset and Siena dataset.

                                                                                                                                                                                 Segment-based level                                Event-based level

                                                                                                                                           Dataset        Patient   ACC (%)       Sen (%)        AUC         P-value    Sn (%)       FPR/h       Prediction time (min)


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           CHB-MIT         chb01     99.59        98.28         0.999     < 0:001    100           0.000                   22.89
                                                                                                                                                           chb02     90.44        75.91         0.867     < 0:001     66.67        0.012                   18.58
                                                                                                                                                           chb03     93.17        86.1          0.964       0.004     83.33        0.265                   19.39
                                                                                                                                                           chb04     89.82        79.44         0.881       0.011    100           0.000                   28.63
                                                                                                                                                           chb05     93.53        83.29         0.948     < 0:001    100           0.000                   13.77
                                                                                                                                                           chb06     88.92        82.31         0.879       0.029     88.89        0.188                   16.24
                                                                                                                                                           chb07     92.00        81.40         0.914       0.032    100           0.000                   23.97
                                                                                                                                                           chb08     99.67        99.11         0.998     < 0:001    100           0.000                   29.23
                                                                                                                                                           chb09     92.99        87.33         0.916       0.005     75           0.121                   15.84
                                                                                                                                                           chb10     94.13        90.62         0.966     < 0:001    100           0.000                   26.56
                                                                                                                                                           chb11     93.39        94.35         0.947     < 0:001    100           0.000                    9.13
                                                                                                                                                           chb12     91.37        91.07         0.906     < 0:001     85.71        0.000                   14.93
                                                                                                                                                           chb13     94.33        96.08         0.935     < 0:001    100           0.003                   18.58
                                                                                                                                                           chb14     91.81        89.70         0.895     < 0:001    100           0.008                   15.67
                                                                                                                                                           chb15     89.24        88.50         0.876     < 0:001     85.71        0.021                   12.50
                                                                                                                                                           chb16     84.54        79.88         0.851       0.011    100           0.000                   19.42
                                                                                                                                                           chb17     99.76        99.01         0.999       0.011    100           0.000                   28.68
                                                                                                                                                           chb18     91.51        94.51         0.923     < 0:001    100           0.138                   11.93
                                                                                                                                                           chb19     91.02        90.78         0.918       0.036    100           0.000                   19.59
                                                                                                                                                           chb20     95.45        88.77         0.952     < 0:001     87.5         0.082                   24.43
                                                                                                                                                           chb21     91.34        84.82         0.899       0.021    100           0.000                   14.35
                                                                                                                                                           chb22     99.79        93.07         0.995       0.027    100           0.000                   26.14
                                                                                                                                                           chb23     98.45        98.69         0.975     < 0:001    100           0.000                   22.15


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                           chb24     85.16        83.28         0.843     < 0:001     87.5         0.201                   18.36
                                                                                                                                                          Average 92:97  4:24 89:01  6:79 0:927  0:048   —     94:18  9:43 0:043  0:078            19:62  5:73
                                                                                                                                           Siena           PN00      85.67        83.71         0.846       0.013     75            0.076                  12.63
                                                                                                                                                           PN01      89.15        84.52         0.867       0.024    100            0.059                  15.28
                                                                                                                                                           PN03      95.67        94.38         0.952     < 0:001    100            0.033                  25.21
                                                                                                                                                           PN05      86.95        86.29         0.873     < 0:001     66.67         0.043                  18.10
                                                                                                                                                           PN06      91.44        91.78         0.923       0.009     80            0.081                  13.65
                                                                                                                                                           PN07      98.34        98.86         0.982     < 0:001    100            0.024                  28.22
                                                                                                                                                           PN09      86.72        90.66         0.884       0.032    100            0.069                  17.83
                                                                                                                                                           PN10      96.35        94.52         0.945       0.020     80            0.036                  16.58
                                                                                                                                                           PN11      97.53        96.57         0.973     < 0:001    100            0.028                  23.41
                                                                                                                                                           PN12      93.49        94.35         0.926     < 0:001    100            0.012                  13.16
                                                                                                                                                           PN13      94.36        93.93         0.927       0.006    100            0.026                  12.36
                                                                                                                                                           PN14      94.86        86.92         0.958     < 0:001     75            0.045                  19.34
                                                                                                                                                           PN16      92.60        91.08         0.904       0.009    100            0.000                  25.35
                                                                                                                                                           PN17      95.94        93.07         0.949       0.003    100            0.045                  16.61
                                                                                                                                                          Average 92:79  4:03 91:47  4:41 0:922  0:040   —     91:19  12:17 0:041  0:023           18:41  5:02


                                                                                                                                           dataset results indicate that the model performs                     without CL. The results are presented in Fig. 6 and
                                                                                                                                           consistently across di®erent datasets.                               Table 4, which show the performance di®erences in
                                                                                                                                                                                                                terms of ACC, AUC, Sen, FPR, and prediction time
                                                                                                                                                                                                                at both the segment-based and event-based levels.
                                                                                                                                           4.4. Impact of contrastive learning strategy                            At the segment-based level, the model with CL
                                                                                                                                           To evaluate the contribution of CL to the perfor-                    outperforms the model without CL in terms of all
                                                                                                                                           mance of this seizure prediction model, an ablation                  major metrics. Speci¯cally, the ACC increased from
                                                                                                                                           study was conducted comparing the model with and                     90.80% to 92.97%, and the AUC improved from

                                                                                                                                                                                                       2550050-10

                                                                                                                                                                                  A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                                 (a)                                         (b)

                                                                                                                                                 Fig. 6.   Comparison between models with and without CL on the CHB-MIT dataset. (a) ACC and (b) AUC.


                                                                                                                                                                     Table 4.    Comparative results of using CL on the CHB-MIT dataset.

                                                                                                                                                                         Segment-based level                                  Event-based level

                                                                                                                                              Method           ACC (%)          Sen (%)        AUC              Sn (%)        FPR/h          Prediction time (min)

                                                                                                                                              Without CL      90:80  5:23   87:30  7:29   0:908  0:054   89:43  13:49   0:056  0:095         18:46  5:88
                                                                                                                                              With CL         92:97  4:24   89:01  6:79   0:927  0:048   94:18  9:43    0:043  0:078         19:62  5:73


                                                                                                                                           0.908 to 0.927. The Sen also showed a noticeable
                                                                                                                                           improvement, rising from 87.30% to 89.01%.
                                                                                                                                               At the event-based level, the model with CL
                                                                                                                                           achieved a higher Sn of 94.18% compared to the
                                                                                                                                           model without CL, which had a Sn of 89.43%, indi-


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           cating more precise detection of seizure events. Ad-
                                                                                                                                           ditionally, the FPR was lower for the model with CL
                                                                                                                                           at 0.043, compared to the model without CL at
                                                                                                                                           0.056, re°ecting an improved ability to minimize
                                                                                                                                           false alarms. Furthermore, its prediction time, which
                                                                                                                                           represents the temporal window preceding the pre-
                                                                                                                                           diction of a seizure, increased from 18.46 min to
                                                                                                                                           19.62 min. This provides the patient and their med-
                                                                                                                                           ical team with more time to respond, and to imple-
                                                                                                                                           ment interventions to mitigate or prevent the e®ects
                                                                                                                                           of the seizure.                                                                             (a)


                                                                                                                                           4.5. Apply contrastive learning to other
                                                                                                                                                baseline models
                                                                                                                                           To comprehensively evaluate the performance of the
                                                                                                                                           proposed model in seizure prediction tasks, four
                                                                                                                                           representative neural network architectures were
                                                                                                                                           selected for comparison: EEGNet, AdderNet, CNN-                                             (b)
                                                                                                                                           RNN, and Transformer. These models re°ect recent
                                                                                                                                           advancements in temporal modeling, lightweight                   Fig. 7. Assessment of the proposed CLResNet in com-
                                                                                                                                                                                                            parison with EEGNet, AdderNet, CNN-RNN, and Trans-
                                                                                                                                           architectures, and attention mechanisms. Detailed
                                                                                                                                                                                                            former on CHB-MIT dataset. (a) The three panels
                                                                                                                                           results for each patient are presented in Fig. 7.                illustrate values of the ACC, AUC, and Sen of the three
                                                                                                                                              In terms of overall average performance, the                  models for each patient (b). The three panels show their
                                                                                                                                           CLResNet model achieved the best results across all              average values of ACC, AUC, and Sn .

                                                                                                                                                                                                   2550050-11

                                                                                                                                           L. Qi et al.


                                                                                                                                           three metrics, with an average ACC of 92.97%, an                and 0.3. The selection of these speci¯c  values was
                                                                                                                                           AUC of 0.927, and a Sen of 94.18%. This demon-                  guided by prior works in CL such as SimCLR29 and
                                                                                                                                           strates that the deep residual structure of CLResNet            MoCo,33 where  typically ranges between 0.05 and
                                                                                                                                           is e®ective in capturing complex EEG features. The              0.3. Based on these references, representative values
                                                                                                                                           Transformer model followed closely, with an average             within this interval were chosen to evaluate the


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           ACC of 91.97% and Sn of 93.21%, indicating its                  sensitivity of the model under di®erent temperature
                                                                                                                                           strong ability to model long-range temporal depen-              settings. The evaluation focused on three key
                                                                                                                                           dencies through global attention mechanisms.                    metrics: ACC, AUC, and prediction time.
                                                                                                                                               EEGNet and AdderNet showed comparable per-                     In seizure prediction experiments based on CL,
                                                                                                                                           formance, with average accuracies of 90.83% and                  ¼ 0:1 was found to yield the best overall perfor-
                                                                                                                                           90.27%, respectively, and Sn of 92.24% and 93.31%.              mance. As shown in Fig. 8(a), the highest ACC of
                                                                                                                                           EEGNet, as a classic lightweight model for EEG                  91.14% was achieved at  ¼ 0:1, while lower ACC
                                                                                                                                           processing, balances computational e±ciency and                 were observed at  ¼ 0:05, 0.2, and 0.3, corre-
                                                                                                                                           accuracy. AdderNet replaces traditional multiplica-             sponding to 90.94%, 90.62%, and 90.01%, respec-
                                                                                                                                           tion operations with addition, signi¯cantly reducing            tively. Similarly, Fig. 8(b) shows the highest AUC of
                                                                                                                                           computational cost while maintaining high accuracy.             0.904 at  ¼ 0:1, with reduced values at other set-
                                                                                                                                           The CNN-RNN model achieved a slightly lower av-                 tings. Figure 8(c) indicates that the prediction time
                                                                                                                                           erage ACC of 91.39% but maintained a Sn of 93.07%,              was longest at  ¼ 0:1, reaching 22.2 min. Although
                                                                                                                                           suggesting strong recall capability in seizure predic-          a slight increase was observed at  ¼ 0:3, the pre-
                                                                                                                                           tion. This indicates that combining convolutional               diction time remained shorter than at  ¼ 0:1. These
                                                                                                                                           feature extraction with recurrent temporal modeling             ¯ndings suggest that  exerts a nonlinear e®ect on
                                                                                                                                           remains e®ective in EEG analysis.                               model performance: Smaller values impair feature
                                                                                                                                                                                                           discrimination, while larger values reduce sensitivity
                                                                                                                                                                                                           to ¯ne-grained patterns.


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           4.6. E®ects of temperature
                                                                                                                                           The e®ect of the temperature-related parameter  on
                                                                                                                                                                                                           5. Discussions
                                                                                                                                           the e®ectiveness of CL was examined. Experimental
                                                                                                                                           data were collected from three randomly selected                5.1. T-SNE visualization
                                                                                                                                           patients, and the average results were used for                 T-SNE was used for visualization, taking patient
                                                                                                                                           analysis. Four values of  were tested: 0.05, 0.1, 0.2,         chb02's data as an example, as shown in Fig. 9.


                                                                                                                                                                        (a)                          (b)                         (c)

                                                                                                                                           Fig. 8. Comparison of ACC, AUC, and prediction time with di®erent temperature parameters (). (a) Average ACC (%) at
                                                                                                                                           di®erent . (b) Average AUC at di®erent . (c) Average prediction time at di®erent .


                                                                                                                                           Fig. 9. T-SNE visualization of EEG data from patient 02: (a) Original data, (b) augmented data, (c) data used for pre-
                                                                                                                                           training, and (d) data used for ¯ne-tuning.

                                                                                                                                                                                                 2550050-12

                                                                                                                                                                                   A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                           The signi¯cant overlap between the interictal                        e±ciency, and latency. For this reason, CLResNet
                                                                                                                                           (orange) and preictal (blue) states in the raw EEG                   was selected as the ¯nal model, as it meets the
                                                                                                                                           signals indicates that distinguishing between these                  practical demands of real-time seizure prediction
                                                                                                                                           signals was challenging without feature optimiza-                    while maintaining strong predictive performance.
                                                                                                                                           tion. A partial separation between the interictal and


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           preictal data emerged after data augmentation,
                                                                                                                                                                                                                5.3. Comparison of performance
                                                                                                                                           which shows that augmentation helped the model
                                                                                                                                                                                                                     with di®erent methods
                                                                                                                                           extract more discriminating features than before.
                                                                                                                                           Following pre-training based on CL, the distinction                  Table 6 compares the proposed CLResNet model
                                                                                                                                           between these two states became clearer owing to a                   with several recently developed models of seizure
                                                                                                                                           reduced overlap and better clustering. This demon-                   prediction. The ¯ndings underscore the exceptional
                                                                                                                                           strates the improved ability of the model to identify                performance of CLResNet, which leverages a con-
                                                                                                                                           pre-seizure states. Finally, training it on the speci¯c              trastive self-supervised approach to learning. Unlike
                                                                                                                                           task led to a nearly complete separation, highlighting               the other models, CLResNet was pre-trained on un-
                                                                                                                                           its strong classi¯cation performance as well as its                  labeled data, and this enabled it to learn robust
                                                                                                                                           potential for reducing FPs and missed seizures. This                 feature representations. This was followed by its ¯ne-
                                                                                                                                           progressive enhancement, achieved through data                       tuning with a smaller amount of labeled data, which
                                                                                                                                           augmentation and CL, signi¯cantly strengthened the                   allowed the model to achieve high predictive per-
                                                                                                                                           capability of the model to predict seizures, such that               formance with few labeled samples — a signi¯cant
                                                                                                                                           it can provide valuable early warning for patients                   advantage over traditional approaches based on su-
                                                                                                                                           and healthcare providers.                                            pervised learning. Compared with previous studies,
                                                                                                                                                                                                                the proposed CLResNet achieved better performance
                                                                                                                                                                                                                on both the CHB-MIT and Siena datasets.
                                                                                                                                           5.2. E±cacy comparison of                                                The proposed model achieved an average AUC of
                                                                                                                                                di®erent models


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                                                                                0.927, a sensitivity of 94.18%, and the lowest FPR
                                                                                                                                           Table 5 compares the compactness and e±ciency of                     among all compared models, at 0.043/h. Although
                                                                                                                                           several models in terms of parameters, FLOPs, con-                   FB-CapsNet38 recorded a slightly higher AUC of
                                                                                                                                           volution energy, and inference time. Among them,                     0.948 and sensitivity of 95.7%, its FPR was signi¯-
                                                                                                                                           EEGNet is the most lightweight, with a low pa-                       cantly higher at 0.087. A low FPR is crucial for re-
                                                                                                                                           rameter count and fast inference speed. AdderNet                     ducing false alarms in practical applications.
                                                                                                                                           shows the lowest energy consumption but su®ers                       Similarly, AddNet-SCL27 attained comparable per-
                                                                                                                                           from high latency. CNN-RNN and Transformer                           formance, with an AUC of 0.929 and a sensitivity of
                                                                                                                                           models have high complexity and long inference                       93%, but exhibited a higher FPR of 0.094. These
                                                                                                                                           times, making them less suitable for real-time tasks.                results demonstrate the capability of CLResNet to
                                                                                                                                              Although CLResNet has a relatively large num-                     e®ectively balance accuracy and reliability.
                                                                                                                                           ber of parameters, it achieves the fastest inference                     Furthermore, the use of contrastive self-super-
                                                                                                                                           time and maintains acceptable energy consumption.                    vised learning in CLResNet enhanced its generali-
                                                                                                                                           Compared to other high-performance models,                           zation ability across diverse patient data,
                                                                                                                                           CLResNet o®ers a better balance between accuracy,                    outperforming CNN-based approaches proposed in


                                                                                                                                                                                   Table 5.   Comparison of model compactness.

                                                                                                                                                      Method        Parameters (10 4 )       Flops (10 6 )   Convolution energy (mJ)   Inference time (ms)

                                                                                                                                                      EEGNet                4.55                  33.89                 0.228                   2.82
                                                                                                                                                      AdderNet             11.91                  79.04                 0.117                  33.44
                                                                                                                                                      CNN-RNN              46.61                 408.14                 0.112                   5.77
                                                                                                                                                      Transformer          54.81                 543.44                 0.194                  68.38
                                                                                                                                                      CLResNet             49.80                 153.67                 0.298                   2.78


                                                                                                                                                                                                      2550050-13

                                                                                                                                           L. Qi et al.


                                                                                                                                           Table 6.       Comparison between the proposed model and prevalent methods of seizure prediction on the CHB-MIT and Siena
                                                                                                                                           dataset.

                                                                                                                                                                                            Window       Preictal     No. of
                                                                                                                                           Author                  Method        Dataset   length (s) interval (min) patients ACC (%) AUC Sen (%) FPR (/h)


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                           Usman et al.34          SVM          CHB-MIT        30            —           24         —       —       92.7      —
                                                                                                                                           Yang et al.35         RDANet         CHB-MIT         5            30          13       92.07    0.893    91.3      —
                                                                                                                                           Zhao et al.27        AddNet-SCL      CHB-MIT         4            30          19         —      0.929    93.0     0.094
                                                                                                                                           Jemal et al.36       CNN inspired    CHB-MIT         5            30          23        90.9    0.918    96.1     0.04
                                                                                                                                                                  by FBCSP
                                                                                                                                           Liang et al.37          CNN          CHB-MIT        30            30          13         —       —       88.3     0.04
                                                                                                                                           Li et al.38          FB-CapsNet      CHB-MIT          4           60          19         —      0.948    95.7     0.087
                                                                                                                                           Guo et al.28        CLEP-STS-Net     CHB-MIT          5           15          19         —      0.918    96.7     0.072
                                                                                                                                           Assali et al.39         CNN          CHB-MIT          2           30          17        90.1    0.928     —        —
                                                                                                                                           Jiang et al.40      Random forest     Siena         30            30          12       85.71     —        —        —
                                                                                                                                           Li et al.41           Bi-LSTM         Siena      1 and 8          —           6          —      0.906   83.54      —
                                                                                                                                           This work             CLResNet       CHB-MIT         4            30          24       92.97    0.927   94.18     0.043
                                                                                                                                                                                 Siena                                   8        91.58    0.914   90.38     0.046


                                                                                                                                           previous studies. For example, the model by Liang                   model achieved commendable results in reducing the
                                                                                                                                           et al. resulted in a notably higher FPR of 0.3, while               FPR, it requires further improvements. Future work
                                                                                                                                           the method by Assali et al. showed inconsistent                     should prioritize minimizing FPs while enhancing
                                                                                                                                           performance across patients due to its reliance on                  their capabilities of generalization across diverse
                                                                                                                                           supervised training.37,39 While Jemal et al. achieved               scenarios and environments.
                                                                                                                                           a slightly higher sensitivity and a marginally lower


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           FPR,36 their model yielded lower accuracy and AUC
                                                                                                                                           compared to ours. Additionally, our study was con-                  6. Conclusion
                                                                                                                                           ducted using data from all 24 patient cases, o®ering a              This paper presents a seizure prediction method
                                                                                                                                           more extensive and comprehensive evaluation.                        using CL and a deep residual network to enhance
                                                                                                                                           Moreover, based on the analysis of the computa-                     accuracy by extracting multi-dimensional EEG fea-
                                                                                                                                           tional e±ciency of our model, our model provides a                  tures. Experiments demonstrate that the proposed
                                                                                                                                           favorable trade-o® among predictive performance,                    model outperforms existing methods in accuracy,
                                                                                                                                           computational e±ciency and universality, which is                   sensitivity, and FPR. A key advantage of our ap-
                                                                                                                                           quite competitive.                                                  proach lies in its use of contrastive self-supervised
                                                                                                                                                                                                               learning, which enables the model to leverage unla-
                                                                                                                                                                                                               beled EEG data for pre-training. This signi¯cantly
                                                                                                                                           5.4. Limitations and future directions                              reduces its reliance on labeled data while improving
                                                                                                                                           The experimental results showcase that the proposed                 its robustness and generalizability across patients.
                                                                                                                                           model can perform well on data from di®erent                        The application of CL enables the model to identify
                                                                                                                                           patients, and excels in particular in terms of its                  crucial distinctions between the preictal and inter-
                                                                                                                                           sensitivity and FPR compared with prevalent                         ictal states, thus ensuring e±cient feature extraction
                                                                                                                                           methods. Employing CL boosts its robustness in                      and sound predictive performance. Furthermore,
                                                                                                                                           managing physiological di®erences among patients,                   this self-supervised approach to learning enhances
                                                                                                                                           which is important for clinical applications. Howev-                the adaptability of the model, making it more e®ec-
                                                                                                                                           er, it's crucial to mention that its predictive perfor-             tive in handling EEG signal variability. Future re-
                                                                                                                                           mance may be in°uenced by patient-speci¯c factors                   search in the area should focus on further optimizing
                                                                                                                                           and patterns of seizures. This highlights the need for              the strategy for individualized modeling and reduc-
                                                                                                                                           future research to further re¯ne individualized                     ing the FP rate of our model so that it can achieve
                                                                                                                                           strategies for modeling. Moreover, although our                     even higher precision in clinical applications. These

                                                                                                                                                                                                      2550050-14

                                                                                                                                                                                 A Contrastive Learning-Enhanced Residual Network for Predicting Epileptic Seizures


                                                                                                                                           advances will pave the way for more reliable and                  6. B. Gu and H. Adeli, Toward automated prediction of
                                                                                                                                           practical systems to predict seizures that can                       sudden unexpected death in epilepsy, Rev. Neurosci.
                                                                                                                                                                                                                33(8) (2022) 877–887.
                                                                                                                                           improve clinical outcomes.
                                                                                                                                                                                                             7. A. V. Perez-Sanchez, J. P. Amezquita-Sanchez, M.
                                                                                                                                                                                                                Valtierra-Rodriguez and H. Adeli, A new epileptic


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                                                                                seizure prediction model based on maximal overlap
                                                                                                                                           Acknowledgments                                                      discrete wavelet packet transform, homogeneity
                                                                                                                                           This work was supported by the Natural Science                       index, and machine learning using ECG signals,
                                                                                                                                                                                                                Biomed. Signal Process. Control 88 (2024) 105659.
                                                                                                                                           Foundation of Shandong Province (ZR2024MF059)
                                                                                                                                                                                                             8. K. M. Tsiouris, V. C. Pezoulas, M. Zervakis, S.
                                                                                                                                           and the Program for Youth Innovative Research                        Konitsiotis, D. D. Koutsouris and D. I. Fotiadis, A
                                                                                                                                           Team at the University of Shandong Province in                       long short-term memory deep learning network for the
                                                                                                                                           China (No. 2022KJ179), jointly supported by the                      prediction of epileptic seizures using EEG signals,
                                                                                                                                           Natural Science Foundation of Shandong Province                      Comput. Biol. Med. 99 (2018) 24–37.
                                                                                                                                                                                                             9. Y. LeCun, Y. Bengio and G. Hinton, Deep learning,
                                                                                                                                           (ZR2024QF009) and the National Natural Science
                                                                                                                                                                                                                Nature 521(7553) (2015) 436–444.
                                                                                                                                           Foundation of China (No. 62472250).                              10. P. Peng, L. Xie and H. Wei, A deep Fourier neural
                                                                                                                                                                                                                network for seizure prediction using convolutional
                                                                                                                                                                                                                neural network and ratios of spectral power, Int. J.
                                                                                                                                           ORCID                                                                Neural Syst. 31(08) (2021) 2150022.
                                                                                                                                                                                                            11. X. Wang, G. Zhang, Y. Wang, L. Yang, Z. Liang and
                                                                                                                                           Longfei Qi https://orcid.org/0009-0008-6533-3988
                                                                                                                                                                                                                F. Cong, One-dimensional convolutional neural net-
                                                                                                                                           Shasha Yuan      https://orcid.org/0000-0003-4792-                   works combined with channel selection strategy for
                                                                                                                                           9880                                                                 seizure prediction using long-term intracranial EEG,
                                                                                                                                           Feng Li   https://orcid.org/0000-0002-5556-3789                      Int. J. Neural Syst. 32(2) (2022) 2150048.
                                                                                                                                           Junliang Shang        https://orcid.org/0000-0002-               12. D. Ji, L. He, X. Dong, H. Li, X. Zhong, G. Liu and W.
                                                                                                                                                                                                                Zhou, Epileptic seizure prediction using spatiotem-
                                                                                                                                           8488-2228
                                                                                                                                                                                                                poral feature fusion on EEG, Int. J. Neural Syst.
                                                                                                                                           Juan Wang        https://orcid.org/0000-0003-3934-


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                                                                                                34(8) (2024) 2450041.
                                                                                                                                           0435                                                             13. N. D. Truong, A. D. Nguyen, L. Kuhlmann, M. R.
                                                                                                                                           Shihan Wang      https://orcid.org/0009-0009-3325-                   Bonyadi, J. Yang, S. Ippolito and O. Kavehei, Con-
                                                                                                                                           0202                                                                 volutional neural networks for seizure prediction using
                                                                                                                                                                                                                intracranial and scalp electroencephalogram, Neural
                                                                                                                                                                                                                Netw. 105 (2018) 104–111.
                                                                                                                                                                                                            14. A. R. Ozcan and S. Erturk, Seizure prediction in scalp
                                                                                                                                           References
                                                                                                                                                                                                                EEG using 3D convolutional neural networks with an
                                                                                                                                           1. R. S. Fisher, C. Acevedo, A. Arzimanoglou, A.                     image-based approach, IEEE Trans. Neural Syst.
                                                                                                                                              Bogacz, J. H. Cross, C. E. Elger, J. Engel Jr., L.                Rehabil. Eng. 27(11) (2019) 2284–2293.
                                                                                                                                              Forsgren, J. A. French, M. Glynn, D. C. Hesdor®er, B.         15. D. Kalita, S. Dash and K. B. Mirza, EPINET: An
                                                                                                                                              I. Lee, G. W. Mathern, S. L. Moshe, E. Perucca, I. E.            optimized, resource e±cient deep GRU-LSTM net-
                                                                                                                                              Sche®er, T. Tomson, M. Watanabe and S. Wiebe,                     work for epileptic seizure prediction, Biomed. Eng.
                                                                                                                                              ILAE o±cial report: A practical clinical de¯nition of             Appl. Basis Commun. 36(4) (2024) 2450021.
                                                                                                                                              epilepsy, Epilepsia 55(4) (2014) 475–482.                     16. A. Bhattacharya, T. Baweja and S. P. K. Karri, Ep-
                                                                                                                                           2. P. Kwan and M. J. Brodie, Early identi¯cation of                  ileptic seizure prediction using deep transformer
                                                                                                                                              refractory epilepsy, N. Engl. J. Med. 342(5) (2000)               model, Int. J. Neural Syst. 32(2) (2022) 2150058.
                                                                                                                                              314–319.                                                      17. Y. Zhang, T. Xiao, Z. Wang, H. Lv, S. Wang, H.
                                                                                                                                           3. A. H. Shoeb, Application of machine learning to epi-              Feng, S. Zhao and Y. Zhao, Hybrid network for pa-
                                                                                                                                              leptic seizure onset detection and treatment, Doctoral            tient-speci¯c seizure prediction from EEG data, Int. J.
                                                                                                                                              dissertation, Massachusetts Institute of Technology               Neural Syst. 33(11) (2023) 2350056.
                                                                                                                                              (2009).                                                       18. P. M. Shanir, K. A. Khan, Y. U. Khan, O. Farooq and
                                                                                                                                           4. U. R. Raghavendra, U. R. Acharya and H. Adeli,                    H. Adeli, Automatic seizure detection based on mor-
                                                                                                                                              Arti¯cial intelligence techniques for automated diag-             phological features using one-dimensional local binary
                                                                                                                                              nosis of neurological disorders, Eur. Neurol. 82(1–3)             pattern on long-term EEG, Clin. EEG Neurosci.
                                                                                                                                              (2020) 41–64.                                                     49(5) (2018) 351–362.
                                                                                                                                           5. U. R. Acharya, Y. Hagiwara and H. Adeli, Automated            19. H. S. Nogay and H. Adeli, Detection of epileptic sei-
                                                                                                                                              seizure prediction, Epilepsy Behav. 88 (2018) 251–261.            zure using pretrained deep convolutional neural


                                                                                                                                                                                                   2550050-15

                                                                                                                                           L. Qi et al.


                                                                                                                                                 network and transfer learning, Eur. Neurol. 83(6)              31. A. Y. Hannun, P. Rajpurkar, M. Haghpanahi, G. H.
                                                                                                                                                 (2021) 602–614.                                                    Tison, C. Bourn, M. P. Turakhia and A. Y. Ng,
                                                                                                                                           20.   K. He, X. Zhang, S. Ren and J. Sun, Deep residual                  Cardiologist-level arrhythmia detection and classi¯-
                                                                                                                                                 learning for image recognition, Proc. IEEE Conf.                   cation in ambulatory electrocardiograms using a deep
                                                                                                                                                 Comput. Vision Pattern Recognit., 27–30 June 2016,                 neural network, Nat. Med. 25(1) (2019) 65–79.


                            Int. J. Neur. Syst. 2025.35. Downloaded from www.worldscientific.com
                                                                                                                                                 Las Vegas, Nevada, pp. 770–778.                                32. T. Maiwald, M. Winterhalder, R. Aschenbrenner-
                                                                                                                                           21.   D. Ravi, C. Wong, B. Lo and G. Z. Yang,                            Scheibe, H. U. Voss, A. Schulze-Bonhage and J.
                                                                                                                                                 Deep learning for human activity recognition: A re-                Timmer, Comparison of three nonlinear seizure pre-
                                                                                                                                                 source e±cient implementation on low-power                         diction methods by means of the seizure prediction
                                                                                                                                                 devices, in Proc. IEEE 13th Int. Conf. Wearable Im-                characteristic, Physica D 194(3–4) (2004) 357–368.
                                                                                                                                                 plantable Body Sensor Netw. (BSN) (IEEE, 2016),                33. K. He, H. Fan, Y. Wu, S. Xie and R. Girshick, Mo-
                                                                                                                                                 pp. 71–76.                                                         mentum contrast for unsupervised visual representa-
                                                                                                                                           22.   Y. P. Singh and D. K. Lobiyal, Automatic prediction                tion learning, in Proc. IEEE/CVF Conf. Comput.
                                                                                                                                                 of epileptic seizure using hybrid deep ResNet-LSTM                 Vision Pattern Recognit. (IEEE Computer Society,
                                                                                                                                                 model, AI Commun. 36(1) (2023) 57–72.                              2020), pp. 9729–9738.
                                                                                                                                           23.   Y. Jiang, Y. Lu and L. Yang, An epileptic seizure              34. S. M. Usman, S. Khalid and M. H. Aslam, Epileptic
                                                                                                                                                 prediction model based on a time-wise attention                    seizures prediction using deep learning techniques,
                                                                                                                                                 simulation module and a pretrained ResNet, Methods                 IEEE Access 8 (2020) 39998–40007.
                                                                                                                                                 202 (2022) 117–126.                                            35. X. Yang, J. Zhao, Q. Sun, J. Lu and X. Ma, An ef-
                                                                                                                                           24.   M. H. Ra¯ei, L. V. Gauthier, H. Adeli and D. Takabi,               fective dual self-attention residual network for seizure
                                                                                                                                                 Self-supervised learning for electroencephalography,               prediction, IEEE Trans. Neural Syst. Rehabil. Eng.
                                                                                                                                                 IEEE Trans. Neural Netw. Learn. Syst. 35(2) (2022)                 29 (2021) 1604–1613.
                                                                                                                                                 1457–1471.                                                     36. I. Jemal, N. Mezghani, L. Abou-Abbas and A.
                                                                                                                                           25.   X. Feng, X. Feng, B. Qin and T. Liu, Aligning se-                  Mitiche, An interpretable deep learning classi¯er for
                                                                                                                                                 mantic in brain and language: A curriculum contras-                epileptic seizure prediction using EEG data, IEEE
                                                                                                                                                 tive method for electroencephalography-to-text                     Access 10 (2022) 60141–60150.
                                                                                                                                                 generation, IEEE Trans. Neural Syst. Rehabil. Eng.             37. D. Liang, A. Liu, C. Li, J. Liu and X. Chen, A novel
                                                                                                                                                 31 (2023) 3874–3883.                                               consistency-based training strategy for seizure pre-


by UNIVERSITY OF CALIFORNIA @ SAN DIEGO on 04/16/26. Re-use and distribution is strictly not permitted, except for Open Access articles.
                                                                                                                                           26.   S. Chang, Z. Yang, Y. You and X. Guo, DSSNet: A                    diction, J. Neurosci. Methods 372 (2022) 109557.
                                                                                                                                                 deep sequential sleep network for self-supervised re-          38. C. Li, Y. Zhao, R. Song, X. Liu, R. Qian and X. Chen,
                                                                                                                                                 presentation learning based on single-channel EEG,                 Patient-speci¯c seizure prediction from electroen-
                                                                                                                                                 IEEE Signal Process. Lett. 29 (2022) 2143–2147.                    cephalogram signal via multichannel feedback capsule
                                                                                                                                           27.   Y. Zhao, C. Li, X. Liu, R. Qian, R. Song and X. Chen,              network, IEEE Trans. Cogn. Dev. Syst. 15(3) (2022)
                                                                                                                                                 Patient-speci¯c seizure prediction via adder network               1360–1370.
                                                                                                                                                 and supervised contrastive learning, IEEE Trans.               39. I. Assali, A. G. Blaiech, A. B. Abdallah, K. B. Khalifa,
                                                                                                                                                 Neural Syst. Rehabil. Eng. 30 (2022) 1536–1547.                    M. Carrere and M. H. Bedoui, CNN-based classi¯ca-
                                                                                                                                           28.   L. Guo, T. Yu, S. Zhao, X. Li, X. Liao and Y. Li, Clep:            tion of epileptic states for seizure prediction using
                                                                                                                                                 Contrastive learning for epileptic seizure prediction              combined temporal and spectral features, Biomed.
                                                                                                                                                 using a spatio-temporal-spectral network, IEEE Trans.              Signal Process. Control 82 (2023) 104519.
                                                                                                                                                 Neural Syst. Rehabil. Eng. 31 (2023) 3915–3926.                40. X. Jiang, X. Liu, Y. Liu, Q. Wang, B. Li and L.
                                                                                                                                           29.   T. Chen, S. Kornblith, M. Norouzi and G. Hinton, A                 Zhang, Epileptic seizures detection and the analysis of
                                                                                                                                                 simple framework for contrastive learning of visual                optimal seizure prediction horizon based on frequency
                                                                                                                                                 representations, in Proceedings of the 37th Interna-               and phase analysis, Front. Neurosci. 17 (2023)
                                                                                                                                                 tional Conference on Machine Learning, Vol. 119                    1191683.
                                                                                                                                                 (PMLR, 2020), pp. 1597–1607.                                   41. H. Li, J. Liao, H. Wang, C. A. A. Zhan and F. Yang,
                                                                                                                                           30.   C. Qin, R. Yang, M. Huang, W. Liu and Z. Wang,                     EEG power spectra parameterization and adaptive
                                                                                                                                                 Spatial variation generation algorithm for motor im-               channel selection towards semi-supervised seizure
                                                                                                                                                 agery data augmentation: Increasing the density of                 prediction, Comput. Biol. Med. 175 (2024) 108510.
                                                                                                                                                 sample vicinity, IEEE Trans. Neural Syst. Rehabil.
                                                                                                                                                 Eng. 31 (2023) 251–260.


                                                                                                                                                                                                       2550050-16
```
