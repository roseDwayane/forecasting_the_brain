---
citation_key: "AbbasiEtAl2025"
paper_id: "paper_210"
title: "Edge-Enabled Pre-Ictal Activity Prediction Framework Using Geometric Deep Learning."
authors: "Humza F Abbasi; Faizan Hamayat; Rana F Ahmad; Syed M Anwar"
year: 2025
doi: "10.1109/embc58623.2025.11253214"
source: "publisher-pdf (doi: 10.1109/embc58623.2025.11253214)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Edge-Enabled Pre-Ictal Activity Prediction Framework Using Geometric Deep Learning.

**Citation:** `AbbasiEtAl2025` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/embc58623.2025.11253214](https://doi.org/10.1109/embc58623.2025.11253214)
**Source PDF:** `full_pdf/Humza2025.pdf`

## Abstract

We present an edge-enabled pre-ictal phase pre- in brain activity, which may be detectable through advanced diction framework for the epileptic seizure geometric deep monitoring techniques like EEG (electroencephalography). learning technique. In particular, we utilized the Brain Network Identifying this state is critical for predicting seizures and Transformer (BNT) for the EEG signals based pre-ictal activity prediction. The model analyzes EEG-based brain connectivity implementing timely interventions [3], [4]. to detect pre-ictal state, offering an interpretable approach Recent advancements in EEG technology such as wearable compared to traditional deep learning techniques. We present a devices, have made continuous monitoring more feasible. performance comparative analysis of BNT with various existing These devices enable long-term tracking of brain activity techniques. Experimental results prove that BNT outperforms in real-world settings, which is essential for detecting pre- existing techniques. In particular, the BNT was evaluated on the CHB-MIT dataset and achieved an average and median ictal states [5]. Conventional methods such as visual EEG accuracy score of 97.17% and 98.51%, respectively on test data inspection or simplistic rule-driven systems often lack objec- with an average area under the receiver operating curve score of tivity, require significant time, and are error-prone. To over- 0.99. Additionally, we benchmark the computational efficiency come these limitations, researchers have turned to advanced on an Nvidia Jetson Xavier NX edge device, where it has a computational approaches, including machine learning and mean inference time of 9.978 ms demonstrating suitability for real-time deployment on edge devices. The results highlight the deep learning algorithms. These techniques can analyze potential of BNT for practical seizure prediction, improving EEG signals and detect pre-ictal patterns. However, they patient outcomes through timely interv

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
2025 47th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC) | 979-8-3315-8618-8/25/$31.00 ©2025 IEEE | DOI: 10.1109/EMBC58623.2025.11253214
                                                                                                                                                                                           Edge-Enabled Pre-ictal Activity Prediction Framework Using Geometric
                                                                                                                                                                                                                       Deep Learning
                                                                                                                                                                                                                Humza F. Abbasi1 , Faizan Hamayat 1,2 , Rana F. Ahmad 1 and Syed M. Anwar3,4


                                                                                                                                                                                              Abstract— We present an edge-enabled pre-ictal phase pre-                     in brain activity, which may be detectable through advanced
                                                                                                                                                                                           diction framework for the epileptic seizure geometric deep                       monitoring techniques like EEG (electroencephalography).
                                                                                                                                                                                           learning technique. In particular, we utilized the Brain Network                 Identifying this state is critical for predicting seizures and
                                                                                                                                                                                           Transformer (BNT) for the EEG signals based pre-ictal activity
                                                                                                                                                                                           prediction. The model analyzes EEG-based brain connectivity                      implementing timely interventions [3], [4].
                                                                                                                                                                                           to detect pre-ictal state, offering an interpretable approach                       Recent advancements in EEG technology such as wearable
                                                                                                                                                                                           compared to traditional deep learning techniques. We present a                   devices, have made continuous monitoring more feasible.
                                                                                                                                                                                           performance comparative analysis of BNT with various existing                    These devices enable long-term tracking of brain activity
                                                                                                                                                                                           techniques. Experimental results prove that BNT outperforms                      in real-world settings, which is essential for detecting pre-
                                                                                                                                                                                           existing techniques. In particular, the BNT was evaluated on
                                                                                                                                                                                           the CHB-MIT dataset and achieved an average and median                           ictal states [5]. Conventional methods such as visual EEG
                                                                                                                                                                                           accuracy score of 97.17% and 98.51%, respectively on test data                   inspection or simplistic rule-driven systems often lack objec-
                                                                                                                                                                                           with an average area under the receiver operating curve score of                 tivity, require significant time, and are error-prone. To over-
                                                                                                                                                                                           0.99. Additionally, we benchmark the computational efficiency                    come these limitations, researchers have turned to advanced
                                                                                                                                                                                           on an Nvidia Jetson Xavier NX edge device, where it has a                        computational approaches, including machine learning and
                                                                                                                                                                                           mean inference time of 9.978 ms demonstrating suitability for
                                                                                                                                                                                           real-time deployment on edge devices. The results highlight the                  deep learning algorithms. These techniques can analyze
                                                                                                                                                                                           potential of BNT for practical seizure prediction, improving                     EEG signals and detect pre-ictal patterns. However, they
                                                                                                                                                                                           patient outcomes through timely intervention.                                    lack explainability and thus, limited clinical potential for
                                                                                                                                                                                              Clinical relevance— This study presents an efficient, real-                   prognosis. On the other hand, using a graph-based techniques
                                                                                                                                                                                           time pre-ictal phase of epileptic seizure prediction system using                provides a level of explainability which is necessary for
                                                                                                                                                                                           the Brain Network Transformer, enabling early intervention
                                                                                                                                                                                           through EEG-based brain connectivity analysis. With high                         medical applications as they can offer insights into brain
                                                                                                                                                                                           accuracy and edge-device compatibility, it enhances patient                      activity in terms of connectivity before a seizure event occurs
                                                                                                                                                                                           care by facilitating timely seizure prediction, improving quality                [6], [7].
                                                                                                                                                                                           of life, and supporting practical deployment in clinical and                        In this study, we explore the potential of the brain network
                                                                                                                                                                                           wearable monitoring systems.                                                     transformer (BNT) to analyze brain connectivity from EEG
                                                                                                                                                                                                                  I. INTRODUCTION                                           data for seizure prediction. We also compare the performance
                                                                                                                                                                                                                                                                            of BNT with previously proposed techniques. Furthermore,
                                                                                                                                                                                              Epilepsy is a disorder of the nervous system, defined
                                                                                                                                                                                                                                                                            we benchmark the computational efficiency of BNT on an
                                                                                                                                                                                           by the occurrence of recurrent seizures that arise without
                                                                                                                                                                                                                                                                            Nvidia Jetson platform, assessing its suitability for deploy-
                                                                                                                                                                                           provocation due to atypical brain activity [1]. It is among the
                                                                                                                                                                                                                                                                            ment on resource-constrained edge computing devices.
                                                                                                                                                                                           most widespread neurological conditions globally, affecting
                                                                                                                                                                                           more than 50 million individuals worldwide. It can affect                                                II. R ELATED W ORK
                                                                                                                                                                                           the patient’s quality of life due to its chronic nature and
                                                                                                                                                                                                                                                                               Detecting epileptic seizures using EEG signals has been
                                                                                                                                                                                           the associated stigmas [2]. One of the major challenges in
                                                                                                                                                                                                                                                                            a focus of research for many years. Early studies focused
                                                                                                                                                                                           managing epilepsy is predicting seizures before they occur
                                                                                                                                                                                                                                                                            on the analysis of EEG signals using traditional signal
                                                                                                                                                                                           (pre-ictal state). This early prediction can drastically improve
                                                                                                                                                                                                                                                                            processing techniques [8], [9], [10], [11], [12]. While signal
                                                                                                                                                                                           a patient’s quality of life by allowing preemptive actions and
                                                                                                                                                                                                                                                                            analysis based techniques provided valuable insights, they
                                                                                                                                                                                           treatment. The pre-ictal state refers to the period just before
                                                                                                                                                                                                                                                                            face significant shortcomings. They often required extensive
                                                                                                                                                                                           a seizure occurs. It is often characterized by subtle changes
                                                                                                                                                                                                                                                                            domain expertise for feature engineering. They also struggle
                                                                                                                                                                                              *This work was supported in-kind by the Center of Excellence Artificial       with generalizing across diverse datasets due to their reliance
                                                                                                                                                                                           Intelligence Technology Center, National Center for Physics, Islamabad,          on handcrafted features. Additionally, these techniques have
                                                                                                                                                                                           Pakistan; Children’s National Hospital, Washington, D.C., USA; and The
                                                                                                                                                                                           George Washington University, Washington, D.C., USA.
                                                                                                                                                                                                                                                                            been unable to adapt dynamically to the non-stationary nature
                                                                                                                                                                                              1 Humza F. Abbasi, 1 Faizan Hamayat and 1 Rana F. Ahmad are with              of EEG signals. These factors have limited the predictive
                                                                                                                                                                                           Center of Excellence AI Technology Center, National Center for Physics,          robustness of classical signal analysis based techniques [8].
                                                                                                                                                                                           Islamabad, Pakistan, and 2 Faizan Hamayat is with Shenzhen AiMall                With the recent advancess in artificial intelligence, deep
                                                                                                                                                                                           Technology Co. Ltd., International Innovation Valley, Shenzhen, Mainland
                                                                                                                                                                                           China abbasihumzafazal@gmail.com; faizan.hamayat@ncp.edu.pk;                     learning and machine learning algorithms are developed
                                                                                                                                                                                           fayyaz.ahmad@ncp.edu.pk                                                          for epilepsy prediction. Early methods combined Recurrent
                                                                                                                                                                                              3,4 Syed M. Anwar is with the Children’s National Hospital, Wash-
                                                                                                                                                                                                                                                                            Neural Networks (RNNs) with wavelet decomposition to
                                                                                                                                                                                           ington, D.C., USA, and the School of Medicine and Health Sci-
                                                                                                                                                                                           ences, George Washington University, Washington, D.C. 20037, USA                 predict seizures from raw EEG signals [13]. This was fol-
                                                                                                                                                                                           sanwar@childrensnational.org                                                     lowed by the application of machine learning techniques like


                                                                                                                                                                                           979-8-3315-8618-8/25/$31.00
                                                                                                                                                                                                  Authorized licensed use©2025
                                                                                                                                                                                                                          limited IEEE
                                                                                                                                                                                                                                  to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.

Support Vector Machines (SVMs), L1-regularized logistic                        A. Node-level Representation Learning
regression, and Convolution Neural Networks (CNNs), often                         Unlike other deep learning and Geometric Deep Learning-
combined with novel EGG pre-processing for inter- and pre-                     based methods that leverage a myriad signal processing-
ictal classification [14], [15], [16], [17], [18], [19]. Further               based or AI based methods to generate the initial embed-
advancements resulted in deep learning models such as                          dings, we used the connection profile of each embedding of
Multi-Layer Perceptron’s (MLPs), Deep Convolution Neural                       the nodes as their initial embeddings. Connection profiles
Networks (DCNNs), and hybrid CNN-LSTM architectures                            are the row vectors x from the correlation matrix X N×N .
bypassing preprocessing by using raw EEG signals directly                      Using the connection profile as the initial embeddings further
[20], [21]. Generative adversarial networks were also em-                      allowed us to not use positional embeddings as the diagonal
ployed to address class imbalance and were paired with CNN                     element, representing self connection, is always 1. This
and LSTM for classification [22], [23]. A CBAM-3D CNN-                         allows unique node identity in the fully connected graph.
LSTM model using Short-Time Fourier Transform (STFT)                           However, we set the diagonal of the connectivity matrix to 0
spectrograms, denoising filters, and attention mechanisms                      as it helps in focusing the analysis on the actual functional
was also developed for accurate seizure prediction [24].                       relationships while still allowing unique node identity. The
Although traditional deep learning and machine learning                        core of BNT’s node-level learning lies in its multi-head
techniques achieve low error rates, their ”black box” nature                   self-attention layers. These layers dynamically refine node
limits their applicability in medical settings. This makes them                representations by modeling interactions across the entire
unsuitable for prognosis or understanding the underlying                       network. For each layer l and attention head m.
causes of diseases [25], [26]. Geometric Deep Learning
                                                                                  • The input node features Z 0 (initialized as X) are linearly
(GDL) addresses these shortcomings by leveraging graph-
                                                                                     projected into queries, keys, and values using learnable
based representations. These representations align with the
                                                                                     matrices
structure of biological brain data and allow for both accurate
                                                                                  • Pairwise attention scores are computed for queries and
predictions as well as deeper analysis of disease mechanisms
                                                                                     keys.
[27]. In recent times, a lot of progress has been made
                                                                                  • The pairwise attention weights are multiplied with the
in developing sophisticated GDL based methods. Multiple
                                                                                     value vectors.
studies have explored the potential of Graph Attention Net-
works (GATs) and Graph Convolutional Networks (GCNs)                              Outputs from all M attention heads are concatenated and
in combination with innovative graph generation techniques                     linearly projected to generate the final node representations
for seizure prediction [28], [29], [30], [31]. In this work, we                for layer l. This mechanism is represented by (1).
                                                                                                   
assess the performance of BNT on scalp EEG data for seizure                                    M
on-set prediction and explore it’s potential applicability in                       Zl =          h l,m  W lO ,
edge computing environments.                                                                 m=1
                                                                                                                                     (1)
                                                                                                     l,m l−1     l,m l−1 ⊤
                                                                                                   W    Z    (W     Z   )
                                                                                  h l,m = Softmax  Q      q K                l,m
                                                                                                                            W Z l−1 ,
                                                                                                                              V
                                                                                                               l,m
                      III. M ETHODOLOGY                                                                       dK
                                                                               where || presents concatenation, M is the number of attention
   In this study we leveraged the BNT [32], originally                         heads, WQl,m ,WKl,m ,WVl,m are learnable query/key/value matri-
designed for imaging data, for epileptic seizure on-set pre-
                                                                                        q
                                                                                             (l,m)
                                                                               ces and dK          is the scaling factor.
diction using EEG. BNT is an advanced deep learning
architecture designed to model and analyze complex inter-                      B. Graph-level Representation Learning
actions within brain networks. The high level architecture of
                                                                                  Graph-level embeddings are generated by aggregating the
the proposed algorithm is graphically illustrated in Fig. 1.
                                                                               previously generated node-level embeddings using OCRead .
It utilizes the extraordinary encoding capabilities of trans-
                                                                               The OCRead module consists of two stages: (a) orthonormal
former models, originally developed for natural language
                                                                               initialization of cluster centers and (b) soft assignment of
processing (NLP), to encode Brain Networks. We generated
                                                                               nodes to clusters. Firstly, cluster centers are randomly initial-
brain networks from electroencephalography (EEG) where
                                                                               ized using Xavier uniform initialization [33]. These centers
each electrode in the EEG senor represents a node in the
                                                                               are then ortho-normalized using the Gram-Schmidt process
brain network. Edges are established based on the Pearson
                                                                               to ensure they are mutually independent. The Gram-Schmidt
correlation between the nodes representing the functional
                                                                               normalization of the initialized vectors is represented in (2).
connectivity. The BNT functions by generating node-level
                                                                                                          k−1
embeddings for all nodes within the network. These node                                                       ⟨uu j ,C
                                                                                                                     Ck ⟩                 uk
embeddings are then aggregated using the graph pooling                                      uk = C k − ∑                   u j,   Ek =          ,      (2)
                                                                                                          j=1 ⟨u j , u j ⟩               ∥u k ∥
operator called orthonormal clustering readout (OCRead ) to
produce graph level embeddings. Finally, these graph-level                     where Ck represents kth initial cluster with center , uk is the
embeddings are then processed by a fully connected neural                      intermediate orthogonal vector for kth cluster, u j intermediate
network (FCN) for classification.                                              orthogonal vector from previous iterations, ⟨·, ·⟩ presents


      Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.

                        Fig. 1.   The architecture of our proposed work predicting pre-ictal phase seizures using EEG signals.


inner product and Ek represents kth orthonormal cluster                        includes both seizure and non-seizure (interictal) data. The
center.                                                                        seizure events were annotated by clinical experts. In our
   After the clusters have been initialized, nodes are assigned                study, we only used the recordings with 22 unique channels.
probabilistically to one or more clusters. This soft assignment                Each channel was treated as a node in the brain network.
is based on the similarity between the node’s embedding and                    To define the edges between these nodes, we calculated
the cluster centers. A soft assignment matrix P is calculated                  the Pearson correlation coefficients between the time series
based on formula given in (3).                                                 recordings of each pair of channels. This allowed us to
                            exp ⟨Z Li , E k ⟩
                                                                              capture the functional connectivity between different regions
                 Pik = K                         ,          (3)               of the brain. While the ictal data was already annotated,
                        ∑k′ =1 exp ⟨Z Li , E k′ ⟩                              we used the technique employed in [28], [34] to annotate
where Ek is the kth cluster center, ZiL is the ith node of the                 the pre-ictal and inter-ictal period. Specifically, the EEG
final MHSA Layer L and Pik the probability of assigning                        recordings from 1 hour prior to the ictal period were labeled
node i to cluster k.                                                           as the pre-ictal, while recordings from 4 hours before and
   The graph-level embeddings are then obtained by aggre-                      after the seizure were labeled as inter-ictal. These continuous
gating the node embeddings ZL with transpose of the soft                       recordings were then segmented into 10-second samples.
assignment matrix P. This is expressed in (4). The graph-                      We used a 5-second overlap between consecutive pre-ictal
level embeddings thus generated are passed on to a FCN                         samples to deal with the class imbalance.
that is used to classify the pre-ictal state.
                                                                               B. Detailed Performance Evaluation of Brain Network
                            Z G = P⊤Z L,                               (4)     Transformer for Epileptic Seizure Prediction
where ZG are the graph-level embeddings.                                          To evaluate the performance of the proposed technique, we
                                                                               tested it using several metrics namely specificity, sensitivity,
             IV. E XPERIMENTS AND R ESULTS
                                                                               accuracy, and the area under the curve (AUC). Table I
A. Dataset and Preprocessing                                                   presents the performance metrics of the proposed approach
   We used the CHB-MIT scalp EEG dataset [37] to assess                        across individual subjects in dataset. Patients 24 and 12
the potential of BNT for predicting epileptic seizures. This                   were left out because they didn’t have a pre-ictal state, as
open-source dataset contains EEG recordings from 24 partic-                    defined by [28], [34]. The proposed method performed very
ipants affected by epilepsy. The age of these subjects range                   well across all metrics, with a mean accuracy of 97.1%
from 1.5 to 22 years. The dataset contains continuous, long-                   and a median accuracy of 98.5%. All patients except 3
term EEG recordings and is sampled at 256 Hz. The dataset                      achieved an accuracy score of over 96%. Our suggested


      Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.

                                                          TABLE I
 R ESULTS OF PERFORMANCE EVALUATION METRICS FOR EACH PATIENT USING OUR PROPOSED BRAIN NETWORK TRANSFORMER BASED METHOD .

           Model for                                             Performance Evaluation Metrics
            Patient      Test Accuracy      Train Accuracy      Test Loss Train Loss    Test Sensitivity        Test Specificity    Test AUC
            chb01           99.7549             99.9540          0.2344      0.0447         0.9958                  0.9983           0.9999
            chb02           99.2417             99.9287          0.7194      0.0703         0.9748                  0.9947           0.9996
            chb03           97.2842             97.9815          1.8387      1.5232         0.9695                  0.9733           0.9947
            chb04           98.3107             98.5580          1.5677      1.1798         0.9306                  0.9911           0.9966
            chb05           95.3596             97.0058          3.8349      2.6147         0.9441                  0.9603           0.9914
            chb06           89.5225             89.8393          8.1949      7.5093         0.8897                  0.9000           0.9605
            chb07           99.1296             99.2833          0.6776      0.6826         0.9665                  0.9943           0.9992
            chb08           96.5015             98.2353          3.2873      1.4860         0.9805                  0.8333           0.9847
            chb09           98.7519             99.2062          1.2541      0.6991         0.9733                  0.9904           0.9880
            chb10           94.6133             96.4606          4.6280      2.9546         0.9572                  0.9387           0.9881
            chb11           99.4611             99.8167          0.6307      0.1599         0.9864                  0.9957           0.9994
            chb13           99.1803            100.0000          0.4887      0.0710         0.9800                  1.0000           1.0000
            chb14           89.1641             91.4062          8.3775      6.4952         0.8951                  0.8889           0.9587
            chb15           99.2509             99.8106          1.3706      0.1602         0.9957                  0.9722           0.9972
            chb16           97.5610             98.0634          2.9692      1.9633         0.9583                  0.9814           0.9919
            chb17           97.9167             99.3924          2.5584      0.5301         0.9722                  0.9815           0.9957
            chb18           99.8930             99.8793          0.1741      0.0939         1.0000                  0.9988           0.9999
            chb19           98.7254             98.9971          1.0076      0.8011         0.9014                  0.9949           0.9982
            chb20           99.3252             99.8311          0.7756      0.1146         0.9600                  0.9984           0.9997
            chb21           96.2180             97.6144          3.1076      2.0342         0.8310                  0.9734           0.9812
            chb22           94.6970             95.6913          4.6242      3.1732         0.9175                  0.9536           0.9810
            chb23           98.8764             99.3845          1.9476      0.4814         0.9726                  0.9948           0.9973
           Average          97.1696             98.3914          1.4258      0.0700         0.9639                  0.9661           0.9978
            Median            98.51              99.10           1.7032     0.07500         0.9679                  0.9859           0.9969


algorithm also had high Sensitivity, Specificity, and AUC                      D. Runtime Inference on Edge Device
scores, with averages of 0.9639, 0.9661, and 0.9978 across                        The computational efficiency of our proposed framework
the 22 subjects. This shows that the model works well even                     was assessed through runtime analysis on the Nvidia Xavier
with imbalanced datasets, as was the case with numerous                        NX. This would allow us to assess its feasibility for real-time
subjects. These results are encouraging, especially since no                   seizure prediction. To ensure reliable results, we repeated the
major signal processing steps were involved.                                   inference process five times and obtained a mean inference
                                                                               time of 9.978 ms. For comparison, we also measured infer-
                                                                               ence speed on a GPU-enabled system with an RTX 4070 Ti,
C. Comparative Analysis of Brain Network Transformer with                      where the model achieved a mean inference time of 5.728
Existing Techniques for Epileptic Seizure Prediction                           ms. The low inference time on both devices can be attributed
                                                                               to the model’s efficient architecture. It eliminates the need
   A comparative analysis was conducted between our                            for extensive preprocessing and avoids the complexity of
method and other techniques as illustrated in Table II.                        multiple deep learning or geometric deep learning models
Experimental results demonstrate that the proposed technique                   often used in other approaches. These results highlight the
outperforms numerous existing methods in pre-ictal state                       potential of deploying the BNT-based algorithm on edge
recognition. For example, we achieves a test accuracy of                       devices for real-time seizure prediction with minimal latency.
97.1696%, which is higher than the 91.14% accuracy of                          Fig. 2 compares the average inference time on the Jetson
the Multitask CNN with Transfer Learning [34]. In terms                        Xavier NX with the GPU-enabled system.
of AUC, we achieve the score of 0.9908, outperforming
                                                                                                           V. D ISCUSSION
methods like Wavelet Transform with CNN [18] (0.8850),
CNN [21] (0.9880), and Model Agnostic Meta Learning                               This study validates the effectiveness of our proposed
[23] (0.9680). Our proposed approach also shows higher                         method in recognizing the pre-ictal state based on scalp
sensitivity (0.9639) compared to [17] (0.9223), CNN-LSTM                       EEG data. In particular, BNT’s ability to achieve high
[22] (0.9300), and Multitask CNN with Transfer Learning                        accuracy (97.1696%) and AUC (0.9908) without extensive
[34] (0.9245). Similarly, its specificity (0.9661) is better than              signal preprocessing highlights its robustness and general-
the techniques proposed in [17] (0.9338), [22] (0.9250), and                   izability. Furthermore, the BNT’s high sensitivity (0.9639)
[34] (0.8994). While methods proposed in [35] and [36] also                    and specificity (0.9661) indicate its ability to handle im-
show good sensitivity (0.9651 and 0.9550, respectively), they                  balanced datasets effectively. These results are particularly
fall short in other metrics. Overall, our suggested method                     important given the non-stationary nature of EEG signals and
consistently outperforms other techniques across all key                       the class imbalance common in seizure prediction datasets.
measures, making it a strong model for seizure prediction.                     Unlike traditional deep learning models, which are often


      Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.

                                                                TABLE II
                           P ERFORMANCE COMPARATIVE ANALYSIS OF OUR PROPOSED METHOD WITH EXISTING TECHNIQUES .

                                    Techniques                        Test Accuracy      Test AUC       Test Sensitivity    Test Specificity
                                 EMD+SVM [17]                                -                -             0.9223              0.9338
                         Wavelet Transform with CNN [18]                     -            0.8850               -                   -
                                     CNN [21]                                -            0.9880            0.9880                 -
                                 CNN-LSTM [22]                               -                -             0.9300              0.9250
                     Multitask CNN with Transfer Learning [34]             91.14          0.9694            0.9245              0.8994
                        Model Agnostic Meta Learning [23]                    -                -             0.9680              0.9550
                                     GCN [35]                                -              0.92            0.9651                 -
                                STS-HGCN-AL [36]                             -             0.938             0.955                 -
                                     Proposed                            97.1696          0.9908            0.9639              0.9661


criticized for their ”black-box” nature, the suggested method                      device confirms its feasibility for real-time use. Although the
leverages graph-based representations to provide insights into                     results are promising, in future research, we will test BNT on
brain connectivity patterns. It offers a more interpretable                        diverse datasets and optimize it for different edge platforms.
framework for predicting the pre-ictal brain activity. This                        Additionally, further analysis of brain connectivity patterns
explainability is crucial for medical applications, as it en-                      identified by BNT could provide deeper insight into seizure
ables clinicians to trust and validate the model’s predictions.                    mechanisms. This work contributes to advance the prediction
BNT’s performance was also benchmarked on an Nvidia                                of pre-ictal seizures and improve patient care through early
Jetson platform. This is very important for real-time seizure                      intervention, paving the way for more accessible and reliable
prediction, as it allows for continuous monitoring of patients                     wearable monitoring systems.
using wearable EEG devices. Processing data efficiently on
edge devices also reduces delay. This can allow for early                                                ACKNOWLEDGMENT
interventions.                                                                        This research was a collaborative effort between the Center
   Despite the promising results, this study has some limita-                      of Excellence Artificial Intelligence Technology Center at the
tions. First, BNT was evaluated on a single dataset (CHB-                          National Center for Physics, Islamabad, Pakistan; Children’s
MIT). Subsequent research could validate the model across                          National Hospital, Washington, D.C., USA; and The George
more heterogeneous datasets to assess generalizability. Sec-                       Washington University, Washington, D.C., USA.
ond, while our BNT-based approach provides explainabil-
ity through graph-based representations, further research is                                                     R EFERENCES
needed to interpret the specific brain connectivity patterns                        [1] Beghi, E. (2020). The epidemiology of epilepsy. Neuroepidemiology,
associated with pre-ictal states. Additionally, the computa-                            54(2), 185-191.
tional efficiency of BNT was assessed only on an Nvidia                             [2] Hu, C., Zhao, Y., & Xiao, Z. (2024). Effects of stigma on the quality
                                                                                        of life in patients with epilepsy. Acta Epileptologica, 6(1), 10.
Jetson Xavier NX. Its performance on other edge devices is                          [3] Scaramelli, A., Braga, P., Avellanal, A., Bogacz, A., Camejo, C., Rega,
yet to be explored. Future work could investigate the model’s                           I., ... & Arciere, B. (2009). Prodromal symptoms in epileptic patients:
adaptability to other edge platforms.                                                   clinical characterization of the pre-ictal phase. Seizure, 18(4), 246-250.
                                                                                    [4] Batista, J., Pinto, M. F., Tavares, M., Lopes, F., Oliveira, A., & Teix-
                                                                                        eira, C. (2024). EEG epilepsy seizure prediction: the post-processing
                                                                                        stage as a chronology. Scientific Reports, 14(1), 407.
                                                                                    [5] A. J. Casson, “Wearable EEG and beyond,” Biomedical En-
                                                                                        gineering Letters, vol. 9, no. 1, pp. 53–71, Jan. 2019, doi:
                                                                                        https://doi.org/10.1007/s13534-018-00093-6
                                                                                    [6] J. Kakkad, J. Jannu, K. Sharma, C. Aggarwal, and S. Medya, “A
                                                                                        Survey on Explainability of Graph Neural Networks,” arXiv.org, Jun.
                                                                                        02, 2023. doi: https://doi.org/10.48550/arXiv.2306.01958. Available:
                                                                                        https://arxiv.org/abs/2306.01958. [Accessed: Feb. 27, 2024]
                                                                                    [7] M. Bugueño, R. Biswas, and G. de Melo, ”Graph-Based Explainable
                                                                                        AI: A Comprehensive Survey,” 2024. Available: https://hal.science/hal-
                                                                                        04660442v1/document
                                                                                    [8] D. Qin, B. Houchins, M. E. Parten, N. Parker, R. Homan and A.
Fig. 2.    Inference time analysis of BNT on GPU system and edge device.                Petrosian, ”A comparison of techniques for the prediction of epilep-
                                                                                        tic seizures,” Proceedings Eighth IEEE Symposium on Computer-
                                                                                        Based Medical Systems, Lubbock, TX, USA, 1995, pp. 151-158, doi:
                                                                                        10.1109/CBMS.1995.465436.
                            VI. C ONCLUSION                                         [9] Y. Salant, I. Gath, and O. Henriksen, “Prediction of epileptic
  This study demonstrates the effectiveness of our edge-                                seizures from two-channel EEG,” Medical & Biological Engineer-
                                                                                        ing & Computing, vol. 36, no. 5, pp. 549–556, Sep. 1998, doi:
enabled geometric deep learning based framework for the                                 https://doi.org/10.1007/bf02524422.
prei-ctal state prediction of epileptic seizures using EEG                         [10] H. R. Moser, B. Weber, H. G. Wieser, and P. F. Meier, “Elec-
data. The proposed BNT-based methodology achieves high                                  troencephalograms in epilepsy: analysis and seizure prediction
                                                                                        within the framework of Lyapunov theory,” Physica D: Nonlin-
accuracy in comparison to existing techniques, making it                                ear Phenomena, vol. 130, no. 3–4, pp. 291–305, Jun. 1999, doi:
suitable for medical applications. Benchmarking on an edge                              https://doi.org/10.1016/s0167-2789(99)00043-3.


          Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.

[11] L. D. Iasemidis et al., ”Adaptive epileptic seizure prediction system,”          nal of Biomedical and Health Informatics, pp. 1–1, 2021, doi:
     in IEEE Transactions on Biomedical Engineering, vol. 50, no. 5, pp.              https://doi.org/10.1109/jbhi.2021.3100297
     616-627, May 2003, doi: 10.1109/TBME.2003.810689.                           [29] Y. Wang et al., “A Spatiotemporal Graph Attention Network Based
[12] K. Lehnertz et al., “Seizure prediction by nonlinear EEG                         on Synchronization for Epileptic Seizure Prediction,” IEEE Journal of
     analysis,” IEEE Engineering in Medicine and Biology                              Biomedical and Health Informatics, vol. 27, no. 2, pp. 900–911, Feb.
     Magazine, vol. 22, no. 1, pp. 57–63, Jan. 2003, doi:                             2023, doi: https://doi.org/10.1109/jbhi.2022.3221211
     https://doi.org/10.1109/memb.2003.1191451.                                  [30] B. Wei, L. Xu, and J. Zhang, “A Compact Graph Con-
[13] A. Petrosian, D. Prokhorov, R. Homan, R. Dasheiff, and D. Wunsch,                volutional Network With Adaptive Functional Connectivity for
     “Recurrent neural network based prediction of epileptic seizures                 Seizure Prediction,” IEEE Transactions on Neural Systems and
     in intra- and extracranial EEG,” Neurocomputing, vol. 30, no.                    Rehabilitation Engineering, vol. 32, pp. 3531–3542, 2024, doi:
     1–4, pp. 201–218, Jan. 2000, doi: https://doi.org/10.1016/s0925-                 https://doi.org/10.1109/tnsre.2024.3460348
     2312(99)00126-5.                                                            [31] B. Wei, L. Xu, and J. Zhang, “A self-supervised graph network with
[14] P. W. Mirowski, Y. LeCun, D. Madhavan and R. Kuzniecky, ”Compar-                 time-varying functional connectivity for seizure prediction,” Biomedi-
     ing SVM and convolutional networks for epileptic seizure prediction              cal Signal Processing and Control, vol. 102, pp. 107375–107375, Dec.
     from intracranial EEG,” 2008 IEEE Workshop on Machine Learning                   2024, doi: https://doi.org/10.1016/j.bspc.2024.107375
     for Signal Processing, Cancun, Mexico, 2008, pp. 244-249, doi:              [32] Kan, X., Dai, W., Cui, H., Zhang, Z., Guo, Y., & Yang, C. (2022).
     10.1109/MLSP.2008.4685487.                                                       Brain network transformer. Advances in Neural Information Process-
[15] N. Wang and M. R. Lyu, “Extracting and Selecting Distinctive EEG                 ing Systems, 35, 25586-25599.
     Features for Efficient Epileptic Seizure Prediction,” IEEE Journal of       [33] Glorot, X.,& Bengio, Y. (2010, March). Understanding the difficulty
     Biomedical and Health Informatics, vol. 19, no. 5, pp. 1648–1659,                of training deep feedforward neural networks. In Proceedings of
     Sep. 2015, doi: https://doi.org/10.1109/jbhi.2014.2358640                        the thirteenth international conference on artificial intelligence and
                                                                                      statistics (pp. 249-256). JMLR Workshop and Conference Proceedings.
[16] M. Bandarabadi, C. A. Teixeira, J. Rasekhi, and A. Dourado, “Epilep-
                                                                                 [34] Dissanayake, T., Fernando, T., Denman, S., Sridharan, S., & Fookes,
     tic seizure prediction using relative spectral power features,” Clinical
                                                                                      C. (2021). Deep learning for patient-independent epileptic seizure
     Neurophysiology, vol. 126, no. 2, pp. 237–248, Feb. 2015, doi:
                                                                                      prediction using scalp EEG signals. IEEE Sensors Journal, 21(7),
     https://doi.org/10.1016/j.clinph.2014.05.022.
                                                                                      9377-9388.
[17] S. M. Usman, M. Usman, and S. Fong, “Epileptic Seizures Predic-             [35] Jia, M., Liu, W., Duan, J., Chen, L., Chen, C. P., Wang, Q., & Zhou, Z.
     tion Using Machine Learning Methods,” Computational and Math-                    (2022). Efficient graph convolutional networks for seizure prediction
     ematical Methods in Medicine, vol. 2017, pp. 1–10, 2017, doi:                    using scalp EEG. Frontiers in Neuroscience, 16, 967116.)
     https://doi.org/10.1155/2017/9074759.                                       [36] Li, Y., Liu, Y., Guo, Y. Z., Liao, X. F., Hu, B., & Yu, T. (2021).
[18] H. Khan, L. Marcuse, M. Fields, K. Swann, and B. Yener, “Focal Onset             Spatio-temporal-spectral hierarchical graph convolutional network
     Seizure Prediction Using Convolutional Networks,” IEEE Transactions              with semisupervised active learning for patient-specific seizure pre-
     on Biomedical Engineering, vol. 65, no. 9, pp. 2109–2118, Sep. 2018,             diction. IEEE transactions on cybernetics, 52(11), 12189-12204.)
     doi: https://doi.org/10.1109/tbme.2017.2785401.                             [37] Guttag, J. (2010). CHB-MIT Scalp EEG Database (version 1.0.0).
[19] U. R. Acharya, Y. Hagiwara, and H. Adeli, “Automated seizure                     PhysioNet. https://doi.org/10.13026/C2K01R
     prediction,” Epilepsy & Behavior, vol. 88, pp. 251–261, Nov.
     2018, doi: https://doi.org/10.1016/j.yebeh.2018.09.030. Available:
     https://www.sciencedirect.com/science/article/pii/S1525505018305791.
[20] H. Daoud and M. A. Bayoumi, ”Efficient Epileptic Seizure Prediction
     Based on Deep Learning,” in IEEE Transactions on Biomedical
     Circuits and Systems, vol. 13, no. 5, pp. 804-813, Oct. 2019, doi:
     10.1109/TBCAS.2019.2929053.
[21] Y. Xu, J. Yang, S. Zhao, H. Wu and M. Sawan, ”An End-to-End
     Deep Learning Approach for Epileptic Seizure Prediction,” 2020
     2nd IEEE International Conference on Artificial Intelligence Cir-
     cuits and Systems (AICAS), Genova, Italy, 2020, pp. 266-270, doi:
     10.1109/AICAS48895.2020.9073988.
[22] S. M. Usman, S. Khalid, and Z. Bashir, “Epileptic seizure predic-
     tion using scalp electroencephalogram signals,” Biocybernetics and
     Biomedical Engineering, vol. 41, no. 1, pp. 211–220, Jan. 2021, doi:
     https://doi.org/10.1016/j.bbe.2021.01.001.
[23] S. Muhammad Usman, S. Khalid, and S. Bashir, “A deep learning
     based ensemble learning method for epileptic seizure prediction,”
     Computers in Biology and Medicine, vol. 136, p. 104710, Sep. 2021,
     doi: https://doi.org/10.1016/j.compbiomed.2021.104710.
[24] X. Lu, A. Wen, L. Sun, H. Wang, Y. Guo, and Y. Ren,
     “An Epileptic Seizure Prediction Method Based on CBAM-3D
     CNN-LSTM Model,” IEEE Journal of Translational Engineering
     in Health and Medicine, vol. 11, pp. 417–423, Jan. 2023, doi:
     https://doi.org/10.1109/jtehm.2023.3290036.
[25] G. Yang, Q. Ye, and J. Xia, “Unbox the black-box for the medical
     explainable AI via multi-modal and multi-centre data fusion: A mini-
     review, two showcases and beyond,” Information Fusion, vol. 77, pp.
     29–52, Jan. 2022, doi: https://doi.org/10.1016/j.inffus.2021.07.016
[26] Muhammad, D., & Bendechache, M. (2024). Unveiling the black box:
     A systematic review of explainable artificial intelligence in medical
     image analysis. Computational and structural biotechnology journal.
[27] Cui, H., Dai, W., Zhu, Y., Li, X., He, L., & Yang, C. (2022,
     September). Interpretable graph neural networks for connectome-based
     brain disorder analysis. In International Conference on Medical Image
     Computing and Computer-Assisted Intervention (pp. 375-385). Cham:
     Springer Nature Switzerland.
[28] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C.
     Fookes, “Geometric Deep Learning for Subject-Independent Epilep-
     tic Seizure Prediction using Scalp EEG Signals,” IEEE Jour-


        Authorized licensed use limited to: Univ of Calif San Diego. Downloaded on April 17,2026 at 01:37:35 UTC from IEEE Xplore. Restrictions apply.
```
