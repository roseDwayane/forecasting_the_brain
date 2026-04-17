---
citation_key: "SunkaraRajakumari2023"
paper_id: "paper_115"
title: "Prediction of the epileptic seizure through deep learning techniques using electroencephalography"
authors: "Mounika Sunkara; Reeja Sundaran Rajakumari"
year: 2023
doi: "10.11591/ijeecs.v32.i2.pp1123-1133"
source: "publisher-pdf (doi: 10.11591/ijeecs.v32.i2.pp1123-1133)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Prediction of the epileptic seizure through deep learning techniques using electroencephalography

**Citation:** `SunkaraRajakumari2023` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.11591/ijeecs.v32.i2.pp1123-1133](https://doi.org/10.11591/ijeecs.v32.i2.pp1123-1133)
**Source PDF:** `full_pdf/Sunkara2023.pdf`

## Abstract

Electroencephalography (EEG) is a widely used and significant technique for aiding in epilepsy diagnosis and investigating the electrical patterns of the human brain. Due to the non-stationary nature of EEG signals, seizure patterns will vary across different recording sessions for individual patients. In this study, a new deep learning long short-term memory (LSTM) model is implemented for the detection of brain tumors and seizures. The process consists of four key steps: EEG signal pre-processing, preictal feature extraction, hyper optimization using grey wolf optimization (GWO), and LSTM-based classification. The evaluation makes use of long-term EEG recordings from the EEG and ABIDE fMRI datasets. By experimenting with various modules and layers of memory units, a pre-analysis is first conducted to determine the best LSTM network architecture. The LSTM model makes use of numerous retrieved features, including temporal and frequency domain information between EEG channels that were extracted before classification. The discovery of the implemented methodology revealed significant advantages in accurately predicting seizures while minimizing false alarms. The implemented LSTM method achieves a 99% accuracy rate, 98% precision, 99% recall, and 98% f1-measure which is better when compared with cross sub-pattern correlation-based principal component analysis (SUBXPCA) and gradient-boosting decision tree (GBDT) methods.

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
Indonesian Journal of Electrical Engineering and Computer Science
Vol. 32, No. 2, November 2023, pp. 1123~1133
ISSN: 2502-4752, DOI: 10.11591/ijeecs.v32.i2.pp1123-1133                                                           1123

       Prediction of the epileptic seizure through deep learning
              techniques using electroencephalography

                               Mounika Sunkara, Reeja Sundaran Rajakumari
                      School of Computer Science and Engineering, VIT-AP University, Amaravati, India


 Article Info                              ABSTRACT
 Article history:                          Electroencephalography (EEG) is a widely used and significant technique for
                                           aiding in epilepsy diagnosis and investigating the electrical patterns of the
 Received Jul 4, 2023                      human brain. Due to the non-stationary nature of EEG signals, seizure patterns
 Revised Aug 3, 2023                       will vary across different recording sessions for individual patients. In this
 Accepted Aug 17, 2023                     study, a new deep learning long short-term memory (LSTM) model is
                                           implemented for the detection of brain tumors and seizures. The process
                                           consists of four key steps: EEG signal pre-processing, preictal feature
 Keywords:                                 extraction, hyper optimization using grey wolf optimization (GWO), and
                                           LSTM-based classification. The evaluation makes use of long-term EEG
 Deep learning                             recordings from the EEG and ABIDE fMRI datasets. By experimenting with
 Epilepsy                                  various modules and layers of memory units, a pre-analysis is first conducted
 Electroencephalogram                      to determine the best LSTM network architecture. The LSTM model makes
 LSTM model                                use of numerous retrieved features, including temporal and frequency domain
 Seizure prediction                        information between EEG channels that were extracted before classification.
                                           The discovery of the implemented methodology revealed significant
                                           advantages in accurately predicting seizures while minimizing false alarms.
                                           The implemented LSTM method achieves a 99% accuracy rate, 98%
                                           precision, 99% recall, and 98% f1-measure which is better when compared
                                           with cross sub-pattern correlation-based principal component analysis
                                           (SUBXPCA) and gradient-boosting decision tree (GBDT) methods.
                                                              This is an open access article under the CC BY-SA license.


 Corresponding Author:
 Mounika Sunkara
 School of Computer Science and Engineering, VIT-AP University
 Amaravati, Andhra Pradesh, India
 Email: mounikasunkara9179@gmail.com


1.    INTRODUCTION
          Epilepsy is a chronic brain disease caused by the sudden abnormal discharge of neurons in the brain
resulting in temporary impairment of brain function [1], [2]. One of the most prevalent neurological non-
communicable illnesses is epilepsy. An abnormality in the brain’s electrical activity, which can be classed as
focal, generalized, or undetermined, is what causes epileptic seizures [3], [4]. Electroencephalography (EEG)
signals are electrical impulses generated by biological brain activity in humans. Disabled or elderly people can
utilize a particular wearable EEG device to collect EEG data and generate control signals for motor imaging,
allowing for remote control [5]. With the aid of an EEG device, electrodes can be placed on the scalp in a non-
invasive way to detect brain activity [6]. To analyze variations in brain activity and to distinguish between
normal and abnormal processes occurring in the human brain, EEG is frequently utilized. EEG is also quite
inexpensive, which makes it the best test for epilepsy sufferers [7]. When used on EEG recordings, common
spatial pattern filters, and optimized spatial pattern filters also offer a higher signal-to-noise ratio [8]. Accurate
prediction is made possible by spatial attention, which also realizes adaptive learning of feature characteristics
[9]. The convolutional neural network (CNN) deep learning model’s main input type is a single domain input,

Journal homepage: http://ijeecs.iaescore.com

1124                                                                                         ISSN: 2502-4752

including feature signals or EEG signals, according to the most recent EEG research [10]. The creation of an
automatic seizure detection system is beneficial for reducing workload and monitoring epilepsy for medical
staff [11]. The simplest method for diagnosing epilepsy is to utilize non-invasive EEG to record the voltage of
brain fluctuations [12]. EEG monitors continuous brain activity by inserting many electrodes at various
locations across the brain and detecting voltage variations [13]. Even for highly skilled neurologists, proper
diagnosis of EEG is time-consuming and challenging despite its great temporal resolution. The development
of intelligent EEG diagnostic technologies enables doctors to handle more patients while providing high-
quality EEG diagnoses [14]. Many wearable and implantable systems and circuits have been created recently
to detect or forecast the appearance of seizures, allowing time for emergency preparation in high-risk situations
without medical assistance, such as operating heavy machinery and driving [15]. Various epileptic seizure
states can be classified based on when the epileptic seizure occurs. Three steps make up a common seizure
prediction approach, they are pre-processing, feature extraction, and classification [16], [17]. Finally, the
network’s input is the raw EEG signal, which has not been subjected to any feature pre-processing. Data-driven
concepts and DL approaches both benefit better from automatically extracting characteristics from data [18].
           Zubair et al. [19] implemented cross-sub-pattern correlation-based principal component analysis
(SUBXPCA) and sub-pattern-based principal component analysis (SPPCA) techniques of dimensionality
reduction to improve the different machine learning models of classification accuracy. Correlating function
dimensionality reduction methods include SPPCA and SUBXPCA. The various features that are obtained after
executing discrete wavelet transform (DWT) and EEG signals, to choose the most notable aspects and maintain
their attributes. The implemented techniques accurately identify seizures while reducing the dimensionality of
the features with decreased computational complexity. However, the accuracy of seizure identification was
affected by the compression or discarding of EEG signals during dimensionality reduction. Lopes et al. [20]
implemented an EEG artifact removal model based on a deep convolutional neural network. The implemented
method was tested using long-term recordings of EEG made by epileptic patients and made accessible in the
database of EPILEPSIAE. Deep convolutional neural networks (DCNNs) were used to create the implemented
method quickly and automatically remove errors from EEG segments. The amount of time needed for manual
artifact removal was decreased by using DCCN-based artifact removal methods, which analyzed EEG data in
real-time or close to real-time. However, EEG data was subject to noise and artifacts, which impaired seizure
detection precision. Jana and Mukherjee [21] implemented a CNN with channel minimization which was
employed to provide an effective seizure prediction technique. CNN has been used to automatically classify
the states of epilepsy patients and extract feature information. This method provides a reliable seizure
prediction system based on unprocessed EEG signals that notify epilepsy patients or dependents to take
protective measures to reduce undesired life risks. The implemented method was utilized to decrease the rate
of overfitting during training, lower the computational overhead, reduce power consumption, and increase the
time efficiency. However, the implemented method was developed as a patient-specific seizure prediction,
making it ineffective for predicting seizures for other epilepsy patients. Usman et al. [22] implemented a deep
learning-based ensemble learning method to predict epileptic seizures. This method involves preprocessing
EEG signals with empirical mode decomposition and bandpass filtering to remove noise. The implemented
method decreases the impact of class imbalance issues and predict epileptic seizures with improved sensitivity
and a low false positive rate. However, using deep learning techniques of seizure prediction and EEG signals
processing of applications was restricted.
           Prathaban and Balasubramanian [23] implemented an adaptive optimization approach employing the
gradient technique of non-linear conjugate. In collaboration with the fletcher reeves (FR) algorithm-based
three-dimensional optimized convolutional neural network (3D OCNN) classifier and the sparsity-based EEG
reconstruction (SER) technique. A sparsity-based method was used to eliminate artifacts, a lightweight neural
network architecture was used to extract and classify seizure data, and a predictor was used to correctly predict
future seizures. However, the implemented model’s success depends on the availability of substantial and
varied EEG datasets, which was difficult due to privacy issues. Jemal et al. [24] implemented an interpretable
deep learning model architecture that considered the kind of lengthy continuous EEG data. The CNN based on
filter bank common spatial pattern (FBCSP) paradigm was implemented and its layers were mapped to well-
known signal processing operations including spatial sub-frequency band. The Children’s Hospital Boston and
the Massachusetts Institute of Technology (CHBMIT) dataset was used to assess the architecture’s
performance for the patient-specific prediction task. The highest sensitivity was attained with the lowest false
alarm rate using the implemented architecture and accuracy prediction was attained high. However, training
models of interpretable deep learning frequently need a lot of annotated data.
           Xu et al. [25] implemented a gradient-boosting decision tree (GBDT) method based on nonlinear EEG
signal features for epilepsy seizures early prediction. Utilizing EEG data from the CHB-MIT Scalp EEG
Database, the implemented method was determined using data from 13 individuals. The result of the
implemented method shows that this method was to forecast seizures with a low fast alarm rate and effectively

Indonesian J Elec Eng & Comp Sci, Vol. 32, No. 2, November 2023: 1123-1133

Indonesian J Elec Eng & Comp Sci               ISSN: 2502-4752                                               1125

identify EEG signals. However, the model has several issues, it depends on annotations concerning seizures
and it was still unclear the way InT affects the model. Seizure identification's accuracy was affected by
compression, representing a constraint in using deep learning for predicting epileptic seizures from EEG
signals. The model's effectiveness relies on having substantial data available, and training interpretable deep
learning models usually demands a vast amount of annotated data. Due to EEG signals being complicated and
non-linear, it is difficult to identify important features that capture the underlying patterns connected to seizure
activity. The class imbalance harms the prediction model’s performance. To create a deep learning algorithm
that is trained on a large dataset of epilepsy patients to effectively predict epileptic seizures using EEG signals.
The contributions of this work are given below,
-     Here, in this research, LSTM models are employed to categorize the encoded EEG signals to achieve the
      principles of stability among time consumption, accuracy, trust, and categorization accuracy of encoded
      spectrogram EEG signals.
-     According to experimental data, the implemented technique has a higher detection accuracy and a shorter
      execution time. The EEG and fMRI datasets are used as benchmark datasets for the prediction of epileptic
      seizures.
           This research paper is structured as: Section 2 presents proposed methodology. Section 3 explains the
process of long short-term memory based classification. Section 4 gives the result discussion and its
comparison. Section 5 describes the conclusion.


2.    PROPOSED METHOD
          The five main steps of the implemented method are the collection of the EEG, autism brain imaging
data exchange (ABIDE) fMRI datasets, pre-processing, feature extraction, hyperparameter optimization, and
classification. Patients and healthy subjects provide raw EEG, and ABIDE fMRI data, which is then processed
to eliminate noise and extract 20 eigenvalues as features. The optimal characteristics that efficiently offer
enough data to distinguish between EEG records of normal and patient are then selected from the feature
extraction. Finally, the EEG is then classified using an LSTM classifier. The overview of the implemented
method is represented in Figure 1.


                              Figure 1. The implemented method’s block diagram


2.1. Dataset
2.1.1. EEG dataset
         Children’s Hospital Boston and the Massachusetts Institute of Technology worked to gather the
datasets of EEG for patients suffering from uncontrollable epileptic seizures. This dataset includes scalp EEG
recordings from 22 epilepsy patients. Twenty-two patients 5 men and 17 women were observed over days
without receiving any medicine. EEG signals were captured for one hour utilizing the 10-20 standard electrode
placement technique. All EEG recordings were stored as files in European data format (EDF). The dataset for
the onset of the seizure and the end of the seizure has been defined in each file containing data in which a
seizure occurred. The majority of EEG sessions use 23 electrodes and 256 Hz to record data.

             Prediction of the epileptic seizure through deep learning techniques using … (Mounika Sunkara)

1126                                                                                           ISSN: 2502-4752

2.1.2. ABIDE fMRI dataset
          Autism brain imaging data exchange is a multisite platform that collects functional and structural
brain imaging information from 17 laboratories all over the world. ABIDE includes 1,112 datasets and there
are 539 people with autism spectrum disorder (ASD) and 573 typically developing (TD) controls. These
datasets of 1,112 contain structural and resting state functional magnetic resonance imaging (FMRI) data
together with the associated phenotypic data. From these subjects, 1,112, and 1,035 are chosen for further
screening as qualified candidates since these subjects have full data of phenotypic. The 505 ASD and 530 TD
patients, including 157 females and 878 men, make up these 1,035 subjects. The purpose of integrating EEG
and ABIDE fMRI data is that the signals measured in each modality have complementary features, and the
combined evaluation of those signals tells about the functions of the brain.

2.2. Pre-processing
          For deep learning (DL) network applications, the preprocessing includes two steps: removal of noise,
and normalization. Empirical mode decomposition (EMD) is used for noise removal from signals of EEG and
to enhance the signal to noise ratio (SNR) of EEG signals. Then normalization is carried out through different
techniques, such as the Z-score technique. Normalization of the Z-score is a technique of processing signals
that is commonly utilized to ensure accurate analysis of the data. Large trends typically dominate small trends
in signals and expand the signal of dynamic amplitude range. All features are made to follow a normal Gaussian
distribution based on (1),
               𝑥− 𝜇
          𝑥=                                                                                               (1)
                 𝜎


where 𝜇 – mean of zero
        𝜎 – standard deviation of 1

2.3. Feature extraction using discrete fourier transform
         Dominant frequency (DF), and spectral entropy (SE) are two frequency variables of the domain. First,
the signal in the time domain must be converted into the domain frequency utilizing discrete fourier transform
(DFT) as expressed in (2) to obtain the features of the frequency domain. According to (2) is described in,
                                  2𝜋
                             −𝑗 𝑘𝑛
          𝑆 (𝑘) = ∑𝑁−1
                   𝑛=0 𝑠[𝑛 ]𝑒 𝑁                                                                            (2)

-      Dominant drequency: A sub-domain maximum peak frequency is referred to as the dominant frequency.
       Due to its improved results, this feature is particularly helpful in the epilepsy identification process.
-      Spectral entropy: For every sub-pattern, the 𝑆𝐸 is determined among two frequencies, 𝑓1 and 𝑓2 . It can be
       expressed as shown in (3). The 𝑆𝐸 is divided by 𝑙𝑜𝑔(𝑁), yielding the normalized spectral entropy (NSE)
       which is defined in (4). In feature extraction, the EEG dataset contains 4,509 features that are extracted.
       As well as ABIDE fMRI dataset contains 5,983 features that are extracted in the dataset of ABIDE fMRI
       by using the DFT.

                     𝑓                     1
          𝑆𝐸 = ∑𝑓2𝑖 =𝑓1 𝑃𝑛 (𝑓𝑖 )𝑥 𝑙𝑜𝑔(𝑃 (𝑓 ))                                                              (3)
                                       𝑛       𝑖

                         𝑆𝐸
          𝑁𝑆𝐸 = 𝑙𝑜𝑔(𝑁)                                                                                     (4)

where 𝑓𝑖 – range of frequency between 𝑓1 and 𝑓2
   𝑃𝑛 (𝑓𝑖 ) – normalized power spectrum component at frequency 𝑓𝑖

2.4. Hyperparameter using grey wolf optimization
         Grey wolf optimization (GWO) is a metaheuristic search technique that draws its inspiration from
nature and ensembles the identification of the ideal response to the problem. This method is employed to
determine the ideal hyperparameter namely: the hidden layers number, window size, and the number of cells
per layer to be considered for the network of LSTM. To determine the exact position, the method resembles
the social behavior and mechanism of hunting of grey wolves. Grey wolves are classified into four different
subspecies: alpha, delta, beta, and omega. The most dominant wolves in the team are the few often one or two
alpha wolves. They are in charge of making decisions and leading the hunt. The beta wolves support the alpha
wolf’s judgment and other tasks. These are less numerous than delta and omega wolves but more numerous
than alpha wolves. The two wolves with the most experience in the teams are alpha and beta. While dominating

Indonesian J Elec Eng & Comp Sci, Vol. 32, No. 2, November 2023: 1123-1133

Indonesian J Elec Eng & Comp Sci                     ISSN: 2502-4752                                         1127

the omega wolves, delta wolves support the alpha and beta wolves. Omega wolves, the least dominant category
are mostly baby-sitters. To represent the social behaviour of grey wolves statistically, the candidate is fittest in
the population of size N consider alpha (∝), followed by the 2nd and 3rd fittest candidates as delta (𝛿) and beta
(𝛽). The alternative potential results are classified as omega (𝜔). The process of hunting is directed and the
prey is mathematically encircled using (5) and (6),

         𝐿⃗ = |𝐾
               ⃗ . ⃗⃗⃗⃗
                   𝑋𝑝 (𝑡) − 𝑋 (𝑡)|                                                                           (5)

                     ⃗⃗⃗⃗𝑝 (𝑡) − ⃗𝐻 . ⃗𝐿
         𝑋 (𝑡 + 1) = 𝑋                                                                                       (6)

where 𝑡 = iteration number of current.
𝐻⃗ ,𝐾⃗ = coefficient vectors.
⃗⃗⃗⃗
𝑋𝑝 = prey position.
𝑋 = position of the grey wolf .
The 𝐻  ⃗ and ⃗⃗⃗𝐾 vectors are expressed in (7) and (8).

         ⃗𝐻 = 2. ⃗ℎ. 𝑟⃗⃗⃗1 − ⃗ℎ                                                                              (7)

         ⃗𝐾 = 2. 𝑟⃗⃗⃗2 𝐼                                                                                     (8)

         During hunting, it is considered that the candidates of gamma, alpha, and beta, have a superior
understanding of the prey area and direct the entire search process to the ideal solution. The candidates’ position
is updated during each iteration based on the candidate’s top three positions. The Evolution technique is used
to update the values if they are outside the solution space, or if the window size is altered to a negative integer.
The formula for updating the wolves’ positions is provided in (9)-(15).

         ⃗⃗⃗⃗𝛼 = |𝐾
         𝐿        ⃗⃗⃗⃗1 . 𝑋
                          ⃗⃗⃗⃗𝛼 − 𝑋|                                                                         (9)

         ⃗⃗⃗⃗𝛽 = |𝐾
         𝐿        ⃗⃗⃗⃗2 . 𝑋
                          ⃗⃗⃗⃗𝛽 − 𝑋|                                                                        (10)

         ⃗⃗⃗⃗𝛿 = |𝐾
         𝐿        ⃗⃗⃗⃗3 . 𝑋
                          ⃗⃗⃗⃗𝛿 − 𝑋|                                                                        (11)

         ⃗⃗⃗⃗1 = 𝑋
         𝑋       ⃗⃗⃗⃗𝛼 − 𝐻
                         ⃗⃗⃗⃗1 . (𝐿
                                  ⃗⃗⃗⃗𝛼 )                                                                   (12)

         ⃗⃗⃗⃗
         𝑋2 = ⃗⃗⃗⃗ ⃗⃗⃗⃗2 . (𝐿
              𝑋𝛽 − 𝐻        ⃗⃗⃗⃗𝛽 )                                                                         (13)

         ⃗⃗⃗⃗3 = 𝑋
         𝑋       ⃗⃗⃗⃗𝛿 − 𝐻
                         ⃗⃗⃗⃗3 . (𝐿
                                  ⃗⃗⃗⃗𝛿 )                                                                   (14)

                            ⃗⃗⃗⃗⃗1 +𝑋
                            𝑋       ⃗⃗⃗⃗⃗2 +𝑋
                                            ⃗⃗⃗⃗⃗3
         𝑋 (𝑡 + 1) =                                                                                        (15)

          The range (0.1) contains random selections for the values of 𝑟1 and 𝑟2 . This enables the wolves to
reach the prey from any position. H takes values from the interval [−ℎ, ℎ], and ℎ is selected from the range [0, 2].
The wolves can utilize the space solution, when |𝐻| < 1, which means they can get closer to the prey. The
wolves can explore the space of solution, when |𝐻| > 1 which means they can move the prey away and
investigate the space of search. 𝐾 and 𝐻 also allow leaving wolves their local maxima or minima. Finally, the
optimal solution for the fittest candidate is returned at the end of the last iteration. Pseudocode 1 for GWO
hyperparameter optimization for LSTM is given:

Pseudocode 1. GWO hyperparameter optimization for LSTM
Begin
Initialize hyperparameters of LSTM like number of neurons, number of layers and learning rate
Initialize the parameters 𝑝𝑜𝑝𝑠𝑖𝑧𝑒, 𝑚𝑎𝑥𝑖𝑡𝑒𝑟, 𝑢𝑏 and 𝑙𝑏
𝑝𝑜𝑝𝑠𝑖𝑧𝑒: size of population,
𝑚𝑎𝑥𝑖𝑡𝑒𝑟: maximum number of iterations,
𝑢𝑏: upper bound(s) of the variables,
𝑙𝑏: lower bound(s) of the variables;
Generate the initial positions of grey wolves with 𝑢𝑏 and 𝑙𝑏;

               Prediction of the epileptic seizure through deep learning techniques using … (Mounika Sunkara)

1128                                                                                          ISSN: 2502-4752

Initialize 𝑎, 𝐴 and 𝐶
Calculate the fitness of each grey wolf;
𝑎𝑙𝑝ℎ𝑎 = the grey wolf with the first maximum fitness;
𝑏𝑒𝑡𝑎 = the grey wolf with the second maximum fitness;
𝑑𝑒𝑙𝑡𝑎 = the grey wolf with the third maximum fitness;
While 𝑘 < 𝑚𝑎𝑥𝑖𝑡𝑒𝑟
      for 𝑖 = 1: 𝑝𝑜𝑝𝑠𝑖𝑧𝑒
         Update the position of the current grey wolf by Eq. (14);
      end for
      Update 𝑎, 𝐴 and 𝐶
      Calculate the fitness of all grey wolves;
      Update 𝑎𝑙𝑝ℎ𝑎, 𝑏𝑒𝑡𝑎, and 𝑑𝑒𝑙𝑡𝑎;
      𝑘 =𝑘+1
end while
Return the optimal set of hyperparameters;
End


3.    LONG SHORT-TERM MEMORY BASED CLASSIFICATION
          The term “long short-term memory” (LSTM) refers to a specific type of recurrent neural network
(RNN), that is capable of learning effectively in long-term dependencies in given sequences of data by learning
the details for a longer time, hence avoiding the problems associated with RNN vanishing gradient. LSTM has
the advantage of not having an overfitting problem when compared to another classifier because the top layer
is fed with characteristics that can improve the features. The LSTM has multiplicative units, which are made
up of different characteristics, that manage the data stream in the memory block, and multiplicative cells that
are gathered from the temporal data. LSTM networks are frequently employed to classify issues involving time
series data, text, audio, biomedical signals, and speech. A simple LSTM cell is shown in Figure 2, which has
3 gates for regulating the information flow from the state of one cell to another and serves as the basis for the
architecture of LSTM.


                                                 Figure 2. LSTM Cell


          The input gate, forget gate, and output gate are some of these gates. All 3 gates use activation of
sigmoid 𝜎 to provide a determination and regulate the flow of information. In a given data sample, determines
the forget gate whether a particular information piece must be forgotten or maintained. It interprets the present
input signal 𝑋𝑡 and the sequences of prior output 𝑦𝑡−1 In the cell state 𝐶𝑡−1 as providing outcome 𝑓𝑡 in the
range of 1 and 0, where 1 denotes completely remembering the information, and 0 denotes fully forgetting the
information. The output multiplying with the output 𝐶𝑡 of the activation layer tanh, the input gate determines
the information that is contained in the current cell state 𝐶𝑡 . Similar to this, combining the output of the LSTM
cell with another activation layer tanh output, determines the output gate flow of the proportion of details 𝑦𝑡 in
𝐶𝑡 at the cell’s outcome. According to (16)-(21) mathematically denote the LSTM cell of three gates operations
to produce the outcome 𝑦𝑡 in state of the cell 𝐶𝑡 .

         𝑓1 = 𝜎 (𝑊𝑓 . [𝑦𝑡−1 , 𝑥𝑡 ] + 𝑏𝑓 )                                                                (16)

              𝑖𝑡 = 𝜎 (𝑊𝑖 . [𝑦𝑡−1 , 𝑥𝑡 ] + 𝑏𝑖 )                                                           (17)

Indonesian J Elec Eng & Comp Sci, Vol. 32, No. 2, November 2023: 1123-1133

Indonesian J Elec Eng & Comp Sci                ISSN: 2502-4752                                              1129

         𝐶̃𝑡 = 𝑡𝑎𝑛ℎ(𝑊𝑐 . [𝑦𝑡−1 , 𝑥𝑡 ] + 𝑏𝑐 )                                                                (18)

         𝐶𝑡 = 𝑓𝑡 ∗ 𝐶𝑡−1 + 𝑖𝑖 ∗ 𝐶̃𝑡                                                                          (19)

         𝑂𝑡 = 𝜎 (𝑊𝑜 . [𝑦𝑡−1 , 𝑥𝑡 ] + 𝑏𝑜 )                                                                   (20)

         𝑦𝑡 = 𝑂𝑡 ∗ 𝑡𝑎𝑛ℎ 𝐶𝑡                                                                                  (21)

where w – weight matrices
       b – bias factor for various LSTM cell gates
         It additionally considers decision tree (DT), random forest (RF), Naïve Bayes (NB), support vector
machine (SVM), and k- nearest neighbor (KNN) classifiers for seizure activity prediction in addition to the
LSTM models. For the hyper-tuning for various parameters, these classifiers have features with grid search-
based parameter estimation. The spectral properties of various EEG channels have been concatenated to alter
the input map of features for these classifiers.


4.    RESULT
         In this experiment, Anaconda Navigator 3.5.2.0 and Python 3.7 are used to simulate the epileptic
seizure prediction utilizing EEG signals. The following are the system requirements for the implemented
research project: Windows 10 (64-bit) operating system, intel core i7 processor, and 16 GB of RAM. The
effectiveness of the implemented model is examined here in precision, f-measure, and categorization accuracy.

4.1. Evaluation parameters
          Accuracy: The correctness of an image is a percentage based on the image classification that displays
the total amount of accurately classified pixels relative to the total number of pixels in the image. It analyses
all of the correctly arranged pixels in an image. It is expressed in (22).
                             𝑇𝑃+𝑇𝑁
         𝐴𝑐𝑐𝑢𝑟𝑎𝑐𝑦 = (𝑇𝑃+𝑇𝑁+𝐹𝑃+𝐹𝑁)                                                                           (22)

         Precision: Positive prediction’s accuracy is gauged by a static called precision. It is equated to the
overall accurate forecasts divided by the sum of accurate predictions and false positive predictions. It expressed
in (23).
                            𝑇𝑃
         𝑃𝑟𝑒𝑐𝑖𝑠𝑖𝑜𝑛 = (𝑇𝑃+𝐹𝑃)                                                                                (23)

         Recall: The wide range of positive predictions is measured by the recall. It is equated to the number
of true positive predictions divided by the number of false negative predictions plus true positive predictions.
It expressed in (24).
                       𝑇𝑃
         𝑟𝑒𝑐𝑎𝑙𝑙 = (𝑇𝑃+𝐹𝑁)                                                                                   (24)

       F1-measure: F1- measure is also known as F1-score. It is a single metric that captures both features
by combining precision and recall. It expressed in (25).

                             (2∗𝑃𝑟𝑒𝑐𝑖𝑠𝑖𝑜𝑛∗𝑅𝑒𝑐𝑎𝑙𝑙)
         𝐹1 − 𝑚𝑒𝑎𝑠𝑢𝑟𝑒 = (𝑃𝑟𝑒𝑐𝑖𝑠𝑖𝑜𝑛+𝑅𝑒𝑐𝑎𝑙𝑙)                                                                  (25)

        The proposed model’s performance has been tested by using the accuracy, precision, recall, and f1-
measure of parameters. The implemented model is to compare the current approaches that are in this
comparison study. Table 1 shows it in terms of precision, accuracy, f1-measure, and recall. The implemented
model outperformed all other models, including RNN, logistic regression, KNN, and SVM. When the LSTM
implemented model is measured with the prior model, the presentation of the implemented model’s
performance is high, and it gives a better result of the effective prediction of epileptic seizure using EEG signal.
        Accuracy, precision, recall, and f1-measure are evaluated based on the epileptic features. For LSTM
methods by utilizing different methods such as RNN, logistic regression, SVM, and KNN obtaining outcomes
which are shown in Table 1. LSTM classification method achieved the best performance, showing a precision
of 98%, accuracy of 99%, f1-measure of 98%, and recall of 99%.

             Prediction of the epileptic seizure through deep learning techniques using … (Mounika Sunkara)

1130                                                                                                    ISSN: 2502-4752

          Table 1 compares the precision, accuracy, f1-measure, and recall of the implemented method with
RNN, logistic regression, KNN, and SVM of existing methods. It demonstrates the comparison of the
implemented approach outperforms by producing improved prediction accuracy and a lower false alarm rate.
A model must be trained using many parameters, and deep learning algorithms are often used in feature
extraction and/or classification to increase processing. State-of-the-art seizure prediction techniques are
contrasted with the outcomes of the implemented strategy in Figure 3. It has been found that the implemented
LSTM method for predicting epileptic seizures performs better than the existing methods such as RNN, logistic
regression, KNN, and SVM concerning precision, accuracy, f1-measure, and recall. According to observations,
the implemented LSTM offers epileptic patients effective seizure prediction because it achieves high true
positive rates with little false alarms.


                                          Table 1. Classification model metrics
                        Classifiers         Accuracy (%)   Precision (%)   Recall (%)   F1-Measure (%)
                       RNN Model                 95              92           94             93
                    Logistic Regression          66              55           57             55
                           KNN                   92              95           81             86
                           SVM                   97              97           94             95
                          LSTM                   99              98           99             98


          A confusion matrix also known as an error matrix, is a specific table structure that allows performance
visualization of an algorithm. Frequently supervised learning (in the learning of unsupervised, it is typically
referred to as a matching matrix) in the field of deep learning and more specifically the issue of statistical
classification shown in Figure 4. Each row represents a case in the real class, and each column denotes
occurrences in the predicted class in both matrix versions. In the confusion matrix, 0 indicates normal patients
and 1 indicates the seizure patients. This section displays the model’s findings and details which the LSTM
model performed in terms of seizure detection. This is the problem of binary classification, either seizure or
non-seizure events were classified in input samples. The confusion matrix from the best model (LSTM) is
shown in Figure 4.


                      Figure 3. Graphical representation of classification model metrics


         The classification of training accuracy and training loss is shown in Figure 5, in that 50 epochs were
used and the accuracy varies from 0.2 to 0.8. The training loss is indicated in green color and the training
accuracy is indicated in blue color. The validation loss and validation accuracy of the LSTM model are shown
in Figure 6. In validation loss and validation accuracy, 50 epochs are used and the accuracy varies from 0.2 to
0.7. The validation loss is indicated in blue and validation accuracy is indicated in black color. A training
accuracy of 99.04% is achieved.
         Both, the ABIDE fMRI dataset, which has 5,983 features that are extracted. The EEG dataset
comprises 4,509 features that are extracted and specified 3,742 amounts of features were selected. The number
of features extracted and selected from EEG and ABIDE fMRI datasets are shown in Table 2.


Indonesian J Elec Eng & Comp Sci, Vol. 32, No. 2, November 2023: 1123-1133

Indonesian J Elec Eng & Comp Sci                   ISSN: 2502-4752                                                     1131


                               Figure 4. Confusion matrix from LSTM classification


  Figure 5. Graphical representation of training loss           Figure 6. Graphical representation of validation loss
                    and accuracy                                                   and accuracy


                         Table 2. Number of features extracted and selected from datasets
                                        Datasets    Extracted features   Feature selection
                                         EEG              4,509               3,742
                                      ABIDE fMRI          5,983               4,620


4.2. Comparative analysis
        The implemented method compares with the existing method concerning the precision, accuracy, f1-
measure, and recall. Compared to other existing methods, the implemented LSTM method achieve high values.
The comparative analysis of existing methods with implemented method is shown in Table 3.


                       Table 3. Comparative analysis of existing and implemented methods
               Authors                     Methods             Accuracy (%)     Precision (%)   Recall (%)   F1-measure (%)
           Zubair et al. [19]         SUBXPCA and SPPCA            90.9             88.5          96.1            91.9
       Jana and Mukherjee [21]              CNN                   98.47                -          97.83             -
 Prathaban and Balasubramanian [23]       3D OCNN                 98.86                -          98.52             -
           Jemal et al. [24]           CNN based FBCSP             90.9             84.7          96.1              -
             Xu et al. [25]                GBDT                   92.50                -          91.90          92.37
           Proposed model                   LSTM                    99               98            99              98


              Prediction of the epileptic seizure through deep learning techniques using … (Mounika Sunkara)

1132                                                                                                                  ISSN: 2502-4752

4.3. Discussion
          This section provides a discussion about the proposed LSTM method and compares those results with
existing methods such as SUBXPCA and SPPCA [19], CNN [21], 3D OCNN [23], CNN based ilter bank common
spatial pattern (FBCSP) [24], and GBDT [25]. The major aim of this study is to predict the epileptic seizure using
EEG signals. Better classification results have been achieved using LSTM, and the implemented method reduces
the false alarm rate and improves prediction accuracy. LSTM models are employed to classify the encrypted
signals of EEG to achieve the principles of stability between time consumption and accuracy, trust, and
classification accuracy of encrypted spectrogram EEG data. Experimental data show that the implemented method
has better detection accuracy and a faster execution time. The dataset of EEG is employed as a benchmark dataset
for epileptic seizure detection. Assuming that the deep LSTM model employed is intended to handle the
complexity of the EEG input. The experiment was successful since it was able to accurately anticipate the patients’
preictal states with a 99% accuracy rate. This model is more appropriate for real-time applications than others
because it is based on feature extraction techniques that demand a high level of expertise and evaluation of
epileptic seizures.


5.    CONCLUSION
          Deep learning has been used to develop a system for anticipating epileptic seizures. If seizure
frequency and duration are correctly predicted, epilepsy patients can live a healthy and risk-free life. This
experiment implemented a method for the prediction and detection of seizures with long short-term memory
utilizing an EEG signal. The implemented method combines feature extraction and classification using LSTM
to obtain more precision, accuracy, f1-measure, and recall compared to other methods. The LSTM model is
employed to categorize the encoded EEG signals to achieve the principles of stability among time consumption,
accuracy, trust, and categorization accuracy of encoded spectrogram EEG signals. This experiment detects
seizures with a 99% accuracy rate. If epilepsy is identified, it is essential to help persons who are having
seizures identify them, so they can take the appropriate precautions in advance. LSTM has the benefit of not
having an overfitting issue because the top layer is fed with characteristics that can improve the features. The
LSTM has multiplicative units, which are made up of different characteristics, that manage the data stream in
the memory block, and multiplicative cells that are gathered from the temporal data. The experiment was
successful since it was able to accurately anticipate the patients’ preictal states with a 99% accuracy rate. When
using deep learning algorithms for the extraction feature and/or classification, a large number of parameters
must be learned. In the future, an advanced optimization technique will be used to improve seizure prediction
performance.


REFERENCES
[1]    S. Hu et al., “Exploring the applicability of transfer learning and feature engineering in epilepsy prediction using hybrid transformer
       model,” IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 31, pp. 1321–1332, 2023, doi:
       10.1109/TNSRE.2023.3244045.
[2]    Z. Yu et al., “Epileptic seizure prediction based on local mean decomposition and deep convolutional neural network,” Journal of
       Supercomputing, vol. 76, no. 5, pp. 3462–3476, May 2020, doi: 10.1007/s11227-018-2600-6.
[3]    S. Raghu, N. Sriraam, Y. Temel, S. V. Rao, and P. L. Kubben, “EEG based multi-class seizure type classification using
       convolutional neural network and transfer learning,” Neural Networks, vol. 124, pp. 202–212, Apr. 2020, doi:
       10.1016/j.neunet.2020.01.017.
[4]    X. Xu, Y. Zhang, R. Zhang, and T. Xu, “Patient-specific method for predicting epileptic seizures based on DRSN-GRU,”
       Biomedical Signal Processing and Control, vol. 81, p. 104449, Mar. 2023, doi: 10.1016/j.bspc.2022.104449.
[5]    A. A. E. Shoka, M. M. Dessouky, A. El-Sayed, and E. El-Din Hemdan, “An efficient CNN based epileptic seizures detection
       framework using encrypted EEG signals for secure telemedicine applications,” Alexandria Engineering Journal, vol. 65, pp. 399–
       412, Feb. 2023, doi: 10.1016/j.aej.2022.10.014.
[6]    M. Savadkoohi, T. Oladunni, and L. Thompson, “A machine learning approach to epileptic seizure prediction using
       electroencephalogram (EEG) signal,” Biocybernetics and Biomedical Engineering, vol. 40, no. 3, pp. 1328–1341, Jul. 2020, doi:
       10.1016/j.bbe.2020.07.004.
[7]    Y. Zhao, C. Li, X. Liu, R. Qian, R. Song, and X. Chen, “Patient-specific seizure prediction via adder network and supervised
       contrastive learning,” IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 30, pp. 1536–1547, 2022, doi:
       10.1109/TNSRE.2022.3180155.
[8]    S. M. Usman, S. Khalid, and Z. Bashir, “Epileptic seizure prediction using scalp electroencephalogram signals,” Biocybernetics
       and Biomedical Engineering, vol. 41, no. 1, pp. 211–220, Jan. 2021, doi: 10.1016/j.bbe.2021.01.001.
[9]    M. Ma et al., “Early prediction of epileptic seizure based on the BNLSTM-CASA model,” IEEE Access, vol. 9, pp. 79600–79610,
       2021, doi: 10.1109/ACCESS.2021.3084635.
[10]   B. Sun et al., “Seizure prediction in scalp EEG based channel attention dual-input convolutional neural network,” Physica A:
       Statistical Mechanics and its Applications, vol. 584, p. 126376, Dec. 2021, doi: 10.1016/j.physa.2021.126376.
[11]   R. R. Borhade and M. S. Nagmode, “Modified atom search optimization-based deep recurrent neural network for epileptic seizure
       prediction using electroencephalogram signals,” Biocybernetics and Biomedical Engineering, vol. 40, no. 4, pp. 1638–1653, Oct.
       2020, doi: 10.1016/j.bbe.2020.10.001.


Indonesian J Elec Eng & Comp Sci, Vol. 32, No. 2, November 2023: 1123-1133

Indonesian J Elec Eng & Comp Sci                        ISSN: 2502-4752                                                          1133

[12]   Y. Ma et al., “A multi-channel feature fusion CNN-Bi-LSTM epilepsy EEG classification and prediction model based on attention
       mechanism,” IEEE Access, vol. 11, pp. 62855–62864, 2023, doi: 10.1109/ACCESS.2023.3287927.
[13]   H. Niknazar, A. M. Nasrabadi, and M. B. Shamsollahi, “A new blind source separation approach based on dynamical similarity and
       its application on epileptic seizure prediction,” Signal Processing, vol. 183, p. 108045, Jun. 2021, doi:
       10.1016/j.sigpro.2021.108045.
[14]   Z. Shi, Z. Liao, and H. Tabata, “Enhancing performance of convolutional neural network-based epileptic electroencephalogram
       diagnosis by asymmetric stochastic resonance,” IEEE Journal of Biomedical and Health Informatics, pp. 1–12, 2023, doi:
       10.1109/JBHI.2023.3282251.
[15]   D. Wu, Y. Shi, Z. Wang, J. Yang, and M. Sawan, “C2SP-Net: Joint compression and classification network for epilepsy seizure
       prediction,” IEEE Transactions on Neural Systems and Rehabilitation Engineering, vol. 31, pp. 841–850, 2023, doi:
       10.1109/TNSRE.2023.3235390.
[16]   S. M. Usman, S. Khalid, and M. H. Aslam, “Epileptic seizures prediction using deep learning techniques,” IEEE Access, vol. 8,
       pp. 39998–40007, 2020, doi: 10.1109/ACCESS.2020.2976866.
[17]   L. Abou-Abbas, K. Henni, I. Jemal, A. Mitiche, and N. Mezghani, “Patient-independent epileptic seizure detection by stable feature
       selection,” Expert Systems with Applications, vol. 232, p. 120585, Dec. 2023, doi: 10.1016/j.eswa.2023.120585.
[18]   T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C. Fookes, “Deep learning for patient-independent epileptic seizure
       prediction using scalp EEG signals,” IEEE Sensors Journal, vol. 21, no. 7, pp. 9377–9388, Apr. 2021, doi:
       10.1109/JSEN.2021.3057076.
[19]   M. Zubair et al., “Detection of epileptic seizures from EEG signals by combining dimensionality reduction algorithms with machine
       learning models,” IEEE Sensors Journal, vol. 21, no. 15, pp. 16861–16869, Aug. 2021, doi: 10.1109/JSEN.2021.3077578.
[20]   F. Lopes et al., “Automatic electroencephalogram artifact removal using deep convolutional neural networks,” IEEE Access,
       vol. 9, pp. 149955–149970, 2021, doi: 10.1109/ACCESS.2021.3125728.
[21]   R. Jana and I. Mukherjee, “Deep learning based efficient epileptic seizure prediction with EEG channel optimization,” Biomedical
       Signal Processing and Control, vol. 68, p. 102767, Jul. 2021, doi: 10.1016/j.bspc.2021.102767.
[22]   S. M. Usman, S. Khalid, and S. Bashir, “A deep learning based ensemble learning method for epileptic seizure prediction,”
       Computers in Biology and Medicine, vol. 136, p. 104710, Sep. 2021, doi: 10.1016/j.compbiomed.2021.104710.
[23]   B. P. Prathaban and R. Balasubramanian, “Dynamic learning framework for epileptic seizure prediction using sparsity based EEG
       Reconstruction with Optimized CNN classifier,” Expert Systems with Applications, vol. 170, p. 114533, May 2021, doi:
       10.1016/j.eswa.2020.114533.
[24]   I. Jemal, N. Mezghani, L. Abou-Abbas, and A. Mitiche, “An Interpretable deep learning classifier for epileptic seizure prediction
       using EEG data,” IEEE Access, vol. 10, pp. 60141–60150, 2022, doi: 10.1109/ACCESS.2022.3176367.
[25]   X. Xu, M. Lin, and T. Xu, “Epilepsy seizures prediction based on nonlinear features of EEG signal and gradient boosting decision
       tree,” International Journal of Environmental Research and Public Health, vol. 19, no. 18, p. 11326, Sep. 2022, doi:
       10.3390/ijerph191811326.


BIOGRAPHIES OF AUTHORS

                               Mounika Sunkara                       earned her undergraduate degree from Nimra Woman’s
                               College of Engineering, Vijayawada, JNTUK, and her Master’s degree in Computer Science
                               and Engineering from Nimra Institute of Science and Technology, Vijayawada, JNTUK,
                               Andhra Pradesh. She is having six years of experience in teaching and presently she is
                               pursuing a Ph.D. degree at the School of Computer Science and Engineering (SCOPE),
                               Vellore Institute of Technology, Andra Pradesh (VIT-AP University). Her current research
                               interests are in the area of deep learning, digital image processing, and machine learning. She
                               can be contacted at email: mounikasunkara9179@gmail.com.


                               Reeja Sundaran Rajakumari                    Professor and Programme chair of Five Year
                               Integrated MTech in Software Engineering, Vellore Institute of Technology, Andra Pradesh
                               (VIT-AP University). Her research area is Artificial Intelligent, High-Performance
                               Computing, Digital Image Processing, and Computer Vision. She earned her Ph.D. in
                               Computer Science and Engineering from Visvesvaraya Technological University (VTU),
                               Govt. of Karnataka for her thesis real-time video denoising. She has 18 years of teaching
                               experience in various engineering colleges as well as Universities with 12 years of research
                               experience in the concerned field. She has published in many SCOPUS journals, National
                               and international journals, Book Chapter Publications, International conferences, and
                               National conferences. She has received many awards- Meritorious alumni award (BTech),
                               Best Paper Award, Best student award during MTech, and Best outgoing student Award
                               during M. Tech and School level Kalathilakam in 10 th standard. She has also a programme
                               committee member, reviewer, and session chair for the various national and international
                               conference and seminars. She can be contacted at email: reeja.sr@vitap.ac.in.


                Prediction of the epileptic seizure through deep learning techniques using … (Mounika Sunkara)
```
