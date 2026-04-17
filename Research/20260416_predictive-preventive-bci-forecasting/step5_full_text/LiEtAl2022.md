---
citation_key: "LiEtAl2022"
paper_id: "paper_064"
title: "Seizure Detection and Prediction by Parallel Memristive Convolutional Neural Networks"
authors: "Chenqi Li; Corey Lammie; Xuening Dong; Amirali Amirsoleimani; Mostafa Rahimi Azghadi; Roman Genov"
year: 2022
doi: "10.1109/tbcas.2022.3185584"
source: "publisher-pdf (doi: 10.1109/tbcas.2022.3185584)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Seizure Detection and Prediction by Parallel Memristive Convolutional Neural Networks

**Citation:** `LiEtAl2022` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.1109/tbcas.2022.3185584](https://doi.org/10.1109/tbcas.2022.3185584)
**Source PDF:** `full_pdf/Chenqi2022.pdf`

## Abstract

During the past two decades, epileptic seizure de- tection and prediction algorithms have evolved rapidly. How- arXiv:2206.09951v1 [cs.ET] 20 Jun 2022 ever, despite significant performance improvements, their hard- ware implementation using conventional technologies, such as Complementary Metal–Oxide–Semiconductor (CMOS), in power and area-constrained settings remains a challenging task; espe- cially when many recording channels are used. In this paper, we propose a novel low-latency parallel Convolutional Neural Network (CNN) architecture that has between 2-2,800x fewer network parameters compared to State-Of-The-Art (SOTA) CNN architectures and achieves 5-fold cross validation accuracy of 99.84% for epileptic seizure detection, and 99.01% and 97.54% for epileptic seizure prediction, when evaluated using the Uni- versity of Bonn Electroencephalogram (EEG), CHB-MIT and SWEC-ETHZ seizure datasets, respectively. We subsequently implement our network onto analog crossbar arrays comprising Resistive Random-Access Memory (RRAM) devices, and provide Fig. 1. An overview of a typical epileptic seizure detection and prediction a comprehensive benchmark by simulating, laying out, and system. Acquired EEG signals are sampled and processed near-sensor using determining hardware requirements of the CNN component of an Analog Front End (AFE), prior to being sent wirelessly to edge device(s) our system. To the best of our knowledge, we are the first to for real-time pre-processing and feature extraction. Features can then be fed parallelize the execution of convolution layer kernels on separate into ML and/or DL architectures, residing either on the IoT edge or in the analog crossbars to enable 2 orders of magnitude reduction IoT cloud, which perform epileptic seizure detection and prediction. in latency compared to SOTA hybrid Memristive-CMOS Deep Learning (DL) accelerators. Furthermore, we investigate the ef- fects of non-idealities on our system and investigate Quantization I. 

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                        1


                                                     Seizure Detection and Prediction by Parallel
                                                     Memristive Convolutional Neural Networks
                                              Chenqi Li† , Student Member, IEEE, Corey Lammie† , Student Member, IEEE, Xuening Dong, Student
                                            Member, IEEE, Amirali Amirsoleimani , Member, IEEE, Mostafa Rahimi Azghadi , Senior Member, IEEE,
                                                                           and Roman Genov , Senior Member, IEEE


                                            Abstract—During the past two decades, epileptic seizure de-
                                         tection and prediction algorithms have evolved rapidly. How-


arXiv:2206.09951v1 [cs.ET] 20 Jun 2022
                                         ever, despite significant performance improvements, their hard-
                                         ware implementation using conventional technologies, such as
                                         Complementary Metal–Oxide–Semiconductor (CMOS), in power
                                         and area-constrained settings remains a challenging task; espe-
                                         cially when many recording channels are used. In this paper,
                                         we propose a novel low-latency parallel Convolutional Neural
                                         Network (CNN) architecture that has between 2-2,800x fewer
                                         network parameters compared to State-Of-The-Art (SOTA) CNN
                                         architectures and achieves 5-fold cross validation accuracy of
                                         99.84% for epileptic seizure detection, and 99.01% and 97.54%
                                         for epileptic seizure prediction, when evaluated using the Uni-
                                         versity of Bonn Electroencephalogram (EEG), CHB-MIT and
                                         SWEC-ETHZ seizure datasets, respectively. We subsequently
                                         implement our network onto analog crossbar arrays comprising
                                         Resistive Random-Access Memory (RRAM) devices, and provide                         Fig. 1. An overview of a typical epileptic seizure detection and prediction
                                         a comprehensive benchmark by simulating, laying out, and                           system. Acquired EEG signals are sampled and processed near-sensor using
                                         determining hardware requirements of the CNN component of                          an Analog Front End (AFE), prior to being sent wirelessly to edge device(s)
                                         our system. To the best of our knowledge, we are the first to                      for real-time pre-processing and feature extraction. Features can then be fed
                                         parallelize the execution of convolution layer kernels on separate                 into ML and/or DL architectures, residing either on the IoT edge or in the
                                         analog crossbars to enable 2 orders of magnitude reduction                         IoT cloud, which perform epileptic seizure detection and prediction.
                                         in latency compared to SOTA hybrid Memristive-CMOS Deep
                                         Learning (DL) accelerators. Furthermore, we investigate the ef-
                                         fects of non-idealities on our system and investigate Quantization                                           I. I NTRODUCTION
                                         Aware Training (QAT) to mitigate the performance degradation
                                         due to low Analog-to-Digital Converter (ADC)/Digital-to-Analog
                                         Converter (DAC) resolution. Finally, we propose a stuck weight
                                         offsetting methodology to mitigate performance degradation due
                                         to stuck RON /ROFF memristor weights, recovering up to 32%
                                                                                                                            E     PILEPSY is a common neurological disorder that affects
                                                                                                                                  approximately 1% of the world’s population [1]. A
                                                                                                                            seizure is characterized by excessive firing of neurons in the
                                         accuracy, without requiring retraining. The CNN component of                       brain, while epilepsy is a medical condition that involves re-
                                         our platform is estimated to consume approximately 2.791W of                       current seizures [2]. As the underlying occurrence mechanism
                                         power while occupying an area of 31.255mm2 in a 22nm FDSOI                         of epilepsy is not well understood [3]–[5], it requires exper-
                                         CMOS process.                                                                      imental methods of treatment that rely on accurate detection
                                           Index Terms—CNN, Seizure Detection, Seizure Prediction,                          and prediction systems, as depicted in Fig. 1.
                                         EEG, RRAM, Memristive Crossbar Array                                                  EEG is the most common method used to monitor the
                                                                                                                            electrical activities of the brain, and can be used to detect and
                                                                                                                            predict seizures. There have been numerous applications of
                                         © 2022 IEEE. Personal use of this material is permitted. Permission from           traditional ML algorithms, such as Support Vector Machines
                                         IEEE must be obtained for all other uses, in any current or future media,          (SVMs), k-Nearest Neighbor (kNN), and Random Forest (RF)
                                         including reprinting/republishing this material for advertising or promotional
                                         purposes, creating new collective works, for resale or redistribution to servers   classifiers to classify ictal (seizure), preictal (prior to a seizure)
                                         or lists, or reuse of any copyrighted component of this work in other works.       and non-ictal (non-seizure) signals using EEG recordings. De-
                                           † These authors contributed equally.
                                                                                                                            spite being able to achieve high accuracies, these approaches
                                           Corresponding authors: M. Rahimi Azghadi and A. Amirsoleimani.
                                           Chenqi Li, Xuening Dong, and Roman Genov are with the Department                 require the manual extraction and selection of features in the
                                         of Electrical and Computer Engineering, University of Toronto, Toronto,            time- or frequency-domain [6]. The optimal choice of such
                                         Canada. email: chenqi.li@mail.utoronto.ca, xuening.dong@mail.utoronto.ca,          feature extractions are largely unknown, experimental, and
                                         roman@eecg.utoronto.ca
                                           Corey Lammie and M. Rahimi Azghadi are with the College of Science               dependant on specific patient signatures, such that there is no
                                         and Engineering, James Cook University, QLD 4811, Australia. e-mail:               one-fit-all solution.
                                         corey.lammie@jcu.edu.au, mostafa.rahimiazghadi@jcu.edu.au                             Compared to traditional seizure classification algorithms,
                                           Amirali Amirsoleimani is with the Department of Electrical Engineering
                                         and Computer Science, York University, Toronto, Canada. e-mail: amir-              DL-based algorithms have more advantages in complex EEG
                                         sol@yorku.ca                                                                       signal feature extraction, as they do not require feature

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                  2


engineering, and are capable of outperforming traditional              of epileptic seizures using EEG and Intracranial Electroen-
ML algorithms for epileptic seizure detection and prediction           cephalography (iEEG) signals.
tasks [7]. However, when these DL systems are implemented
using CMOS, there are problems such as large scale, high               A. Parallel CNNs
calculation energy consumption and high delay, which hinder
                                                                          Parallel CNNs are composed of one or many convolutional
their efficacy; especially in resource-constrained environments.
                                                                       layers, which are executed in parallel and have been previously
   In order to solve this kind of problem, this paper proposes
                                                                       used in many applications. For example, in the ResNeXt [12]
a neuromorphic calculation strategy based on a novel In-
                                                                       family of architectures, parallel blocks containing convolu-
Memory Computing (IMC) RRAM architecture, which uti-
                                                                       tional layers were used to increase network width, which can
lizes analog crossbars. Computer designers have tradition-
                                                                       decrease the time required to train a CNN [13]. When perform-
ally separated the role of storage and compute units. The
                                                                       ing multi-modal DL, parallel convolutional layers can be used
IMC paradigm blurs this distinction, and imposes the dual
                                                                       to process different inputs in parallel [14], in order to improve
responsibility on memory substrates: storing and computing
                                                                       network throughput. Specifically for epileptic seizure detection
on data for massively parallel computing [8]. By exploiting
                                                                       and prediction tasks, parallel convolutional layers have been
the physical characteristics of emerging analog device tech-
                                                                       used to learn high-level representations simultaneously [15].
nologies, analog crossbars can be used to perform Vector-
                                                                       By parallelizing convolutional operations, inference time is
Matrix Multiplications (VMMs), the most dominant operation
                                                                       greatly reduced compared to current SOTA architecture that
in CNNs, in as little as O(1) [9], [10], significantly reducing
                                                                       rely on sequential convolution layers, as convolution layers
the computational complexity during inference operations. Our
                                                                       form the bottleneck of CNN inference.
specific contributions are as follows:
   1) To the best of our knowledge, we are the first to
       parallelize the execution of convolution layer kernels on       B. Traditional EEG-based Seizure Detection and Prediction
       separate analog crossbars to address the computational          Algorithms
       bottleneck of CNNs, enabling 2 orders of magnitude                 As early as 1996, initial attempts were made to detect
       reduction in latency compared to current SOTA hybrid            seizures using EEG signals and traditional ML approaches.
       Memristive-CMOS DL accelerators;                                Using a combination of Artifical Neural Networks (ANNs)
   2) We reduce the number of required parameters by 2-                and wavelet transforms, sensitivity values of 76% [16] and
       1,600x and 5-2,800x for epileptic seizure detection and         97% [17], were reported using standardized datasets. In the
       prediction tasks using deep learning models, while still        late 2000s and early 2010s, SVMs encountered growing
       achieving SOTA performance;                                     interest. Namely, when using SVMs in combination with
   3) We provide a comprehensive benchmark for hardware                feature extraction methods such as high-order spectra analysis,
       memristor-based seizure prediction/detection systems by         wavelet transforms, Fast Fourier Transforms (FFTs), wavelet
       simulating, laying out, and determining hardware re-            decomposition and least-squares parameter estimators [18]–
       quirements of the CNN component of our system;                  [27], promising sensitivity, specificity, and accuracy values
   4) We propose a simplified stuck weight offsetting method-          ≥98.5% were achieved. More recently, advances in the DL
       ology for mitigating severe degradation of system per-          domain using CNNs and Recurrent Neural Networks (RNNs),
       formance due to stuck RON /ROFF memristor weights.              have further benefited seizure detection algorithms. Current
       We demonstrate that our method is capable of achieving          SOTA models are capable of achieving accuracy ranging from
       up to 32% performance recovery, without requiring               95-100% [28]–[31] across multiple datasets.
       retraining, while incurring minimal hardware and com-              Early efforts for seizure prediction started in 1970s, where
       putational overhead.                                            seizure warning systems were designed with logic circuitry to
To promote reproducible research, all of our simulation codes          classify extracted features from a series of filters and analog
are made publicly accessible1 . The rest of the paper is struc-        circuitry [32], [33]. To varying degrees of success, a variety of
tured as follows: In Section II, we overview and discuss related       methods have been proposed, including a rule-based method
work. In Section III, we present our epileptic seizure detection       using univariate measures [34], spike rate analysis [35], posi-
and prediction system. In Section IV, we overview and discuss          tive zero-crossing intervals analysis [36], statistical dispersion
our software methodology. In Section V, we overview and                measures [37], multidimensional probability evolution [38],
discuss our hardware simulation methodology. In Section VI,            circadian concepts via probabilistic forecasting [39], and a
we present and discuss our results. Finally, we conclude the           combination of reinforcement learning, online monitoring
paper in Section VII.                                                  and adaptive control theory [40]. Similarly to seizure detec-
                                                                       tion, many DL techniques have also been applied. Notable
                        II. R ELATED W ORK                             contributions include the combination of CNNs and RNNs,
                                                                       capable of achieving 99.6% accuracy and a False Positive
  In this section, we present an overview of related work using        Rate (FPR) of 0.004 per hour [41]. Moreover, supervised
parallel CNNs and related work using traditional and neu-              deep convolutional autoencoder and bidirectional long short-
romorphic ML architectures for the detection and prediction            term memory networks have been used to achieve accuracy,
  1 https://github.com/coreylammie/Memristive-Seizure-Detection-and-   sensitivity, specificity, and precision values between 98-99%,
Prediction-by-Parallel-Convolutional-Neural-Networks                   with F1-values ≥0.98. More recently, augmented DL network

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                                                                     3


   (a)                                (b)                                     (c)                               (d)                                                                          (e)
   Raw EEG Signals                    Sampled EEG Signals                     Features                          Accelerator                                                                  Prediction
                                                                                                                  WL0


                                                                                                                                                                           Post Processing
                                                                              mean                                      g00         g01         g02          g0N
                                                                              variance                            WL1
                                                                              skewness

                                                                  Feature
                                                                              kurtosis
                                                                                                                                                                                                 Ictal
                                                                                                                        g10         g11         g12          g1N

                                                                              coefficient of variation            WL2


                                                                                                          DAC
                                                                              median absolute
                                ADC                                                                                                                                                            Preictal
                                                                                                                        g20         g21         g22          g2N
                                                                              deviation

                                                                 Extraction
                                                                              root mean square
                                                                              amplitude
                                                                              shanon entropy
                                                                                                                                                                                              Interictal
                                                                                                                  WLM


                                                                                                                        gM0         gM1         gM2          gMN


                                                                                                                              BL0         BL1         BL2          BLN


     (f)
     Extracted Features       Parallel                                    Average Pooling                       Flatten                                     Fully Connected Layers
       x0             conv1   Convolutional
       x1             k=32    Layers
       x2                                                                                                                                                                fc1
                      s=1                                                                                                                                                M=8
       x3             p=1, f=32
      x4                                                                                                 pool1
      x5                                                                                                 k=2
      x6
      x7
                                                                                                                                                                                                 fc2
      x8                                                                                                                                                                                         M=2
      x9
      x10                                                                                                                                                                                    2
      x11
      x12
                       32x33                   conv2
      x13                                      k=30
                                               s=1                                         32x34
      x63                                      p=1, f=30                                                                                                           8
         64                            32x35                            32x68

Fig. 2. A high-level system architecture overview. (a) Raw EEG signals are sampled and digitized using ADCs. (b) Features are extracted from sampled
EEG signals. (c) Extracted features are fed into a memristive DL accelerator. (d) Accelerator outputs are processed. Fig. 3 depicts the detailed hardware
implementation of the accelerator. (e) Processed accelerator outputs are used to determine interictal, preictal, and ictal states. (f) The novel neural network
architecture used consists of two parallel 1d-convolutional layers, one average pooling layer, and two fully connected (dense) layers. N is used to denote the
batch size, i.e., the number of batches presented to the network in parallel. f denotes the number of filter. k determines the filter size. s denotes the stride
length. p denotes the padding. M denotes the number of output neurons for each fully connected layer. Parts of this figure are derived from [11].


architectures have been used to reduce computational com-                                 Recent works by Liu et al. implemented Finite Impulse
plexity for operation in resource-constrained environments.                            Response (FIR) filter bank on memristive crossbar array
One such approach, which employs CNNs with minimizing                                  to achieve 93.46% seizure detection accuracy and obtained
channels, is capable of achieving 99.47% accuracy, 97.83%                              95% accuracy by using a memristive crossbar based signal-
sensitivity, 92.36% specificity, with a FPR of 0.0764 [42].                            processing stage combined with linear discriminant classi-
Finally, Siamese models have been used to achieve 88-91%                               fier [50]. Lammie et al. pioneered the implementation of
accuracy on the CHB-MIT dataset [43]. We refer the reader                              CNNs for seizure prediction using memristor arrays, achieving
to [44] for a comprehensive survey of EEG seizure detection                            77.4% sensitivity and 0.85 Area Under the Receiver Operating
and prediction algorithms.                                                             Characteristic Curve (AUROC) on the CHB-MIT dataset [11].

C. Hardware Implementations of EEG-based Seizure Detec-                                   Seizure is a chronic, recurring condition that can mostly be
tion and Prediction Algorithms                                                         prevented through medication before onset [51], but even with
   Many hardware implementations of epileptic seizure detec-                           the best medications, 30% of the patients are drug-resistant
tion and prediction algorithms have been reported using a va-                          [52]. Closed-loop brain stimulation has been found to mitigate
riety of technologies; namely Field Programmable Gate Array                            and even improve symptoms [53], [54], but unpredictability of
(FPGA), CMOS and Very-large-scale Integration (VLSI) [45],                             seizure requires a closed-loop prediction system to provide ac-
[46]. Complementing traditional hardware implementations,                              curate warning with adequate preparation time for stimulation
IMC architectures, which use memristive crossbar arrays to                             [55]. This calls for the need for fast, low-latency computations,
perform repetitive operations in-memory, have gained increas-                          as the changes within the patients can be noticed early-on, in
ing popularity in recent years. Kudithipudi et al. implemented                         order to start treatments early to improve safety and quality of
a neuromemristive reservoir computing architecture to achieve                          life [56]. In doing so, symptoms and subsequent effects can
90% accuracy and Merkel et al. achieved 85% accuracy [47],                             be minimized, including anxiety and social exposition [57].
[48]. Nature-inspired memristive Cellular Automata (CA) was                            The major limiting factor of seizure detection and prediction
implemented by Karamani et al. to emulate epilepsy-related                             algorithms is the reliance on patient specific features, leading
phenomena in the brain [49].                                                           to undesirable results when generalized to other patients in the

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                          4


real world [58]. With energy efficient computations, it enables   Algorithm 1 Model Search and Selection Methodology
the deployment of such systems within wearable devices, so        Input: Fixed modular crossbar tile size (m × n), O BJmax ,
that it can be coupled with the stimulation system, as well as      objectives to minimize, O BJmin , additional hardware design
allowing data for a patient to be collected in the long-term to     constraints, w.
further improve model’s predictions by fine tuning the model      Output: Optimized network architecture (L, D, α, β), where
to better recognize patient-specific signatures [59].               L is the number of convolutional layer blocks, D is the
   It is known that convolutional layers are the bottlenecks        number of fully connected layers, α is a vector containing
of CNNs. According to Cong et al., convolutions make up             the sizes of the first kernel for each convolutional layer
more than 90% of CNN inference [60]. Therefore, accelerating        when parallel convolutional layer execution is performed,
convolution is pivotal to efficient CNNs for future seizure         and β is a vector containing the number of output neurons
detection/prediction systems. Note that all existing hardware       for each fully connected layer
implementations of CNN memristive accelerators focus on             minimize O BJ(m, n, L, D, α, β) subject to w.
sequential CNNs. Memristive crossbar acceleration of paral-         procedure N ETWORK A RCHITECTURE(m, n, L, D, α, β)
lelized convolution layers and blocks, found in many CNN               for l = 0 to L − 1 do . For each convolutional layer
architectures such as ResNeXt [12], are explored in this work              Cinl = m                            . Input channels
to further reduce inference latency.                                       Coutl = floor(n / 2)               . Output channels
                                                                           if parallel convolutional layer execution then
   III. S EIZURE D ETECTION AND P REDICTION S YSTEM                            kl0 = αl , kl1 = m − 2 − αl . Set kernel sizes
   In this section, we present our seizure detection and pre-              else
diction system. As shown in Fig. 2, our system comprises of                    kl = m − 1                      . Set kernel size
five stages, depicted using Fig. 2(a)-(e). As the same network             end if
architecture, depicted in Fig. 2(f), is used for both detection        end for
and prediction, and networks are bench-marked using multiple           for d = 0 to D − 2 do . For each fully connected layer
datasets, our proposed system can be reconfigured for both                 md = β l             . Set number of output neurons
epileptic seizure and prediction tasks. While we briefly detail        end for
and discuss signal acquisition and pre- and post-processing            mD−1 = 2                                     . Last layer
stages, here-on-in, the scope of this paper will be largely         end procedure
confined to the accelerator step described in Fig. 2(d). We         function O BJ(m, n, L, D, α, β, w)
leave a detailed hardware description and evaluation of other            maximize E VAL(Net) and minimize PARAMS(Net), .
stages to future work.                                              i.e., determine L, D, α, and β, where E VAL determines
                                                                    the validation accuracy, and PARAMS determines the total
A. Parallel Convolutional Neural Network Architecture               number of network parameters
                                                                         where,
   The primary constraint put on our design was a fixed                  Net = N ETWORK A RCHITECTURE(m, n, L, D, α, β)
modular tile size of 64×64. Practically, passive memristor-         return O BJmin (Net)
based analog crossbar tiles of sizes up to 128×64 have been         end function
used to perform VMMs [9], however such designs have only
been demonstrated using pseudo-crossbars having micron-size
electrodes. Such limitations in the maximum viable size are a
                                                                  parallel CNNs, convolution layers can be processed simultane-
serious computational scalability challenge with electrodes in
                                                                  ously, enabling the use of multiple crossbars at the same time.
the tenth of nanometer range that would prevent sinking large
                                                                  In addition, parallel convolution layers with different kernel
currents through them [61]. Recently, a 4K memristor analog-
                                                                  sizes enable the network to extract features of varying recep-
grade passive crossbar circuit has been fabricated [62], which
                                                                  tive fields, providing the fully connected layers a diverse and
comprises several modular 64 x 64 passive crossbar tiles with
                                                                  yet compact representation of the features for classification;
99% functional nonvolatile metal-oxide memristors. From an
                                                                  enabling a reduction in network parameters required.
original exploratory investigation, it was determined that for
the RRAM device being modelled, the largest feasible modular         As shown in Fig. 2, our proposed CNN architecture consists
tile size which is able to be programmed using a write-verify     of two parallel convolution kernels. Algorithm 1 formalizes
scheme was 64×64. Consequently, this fixed modular tile size      the methodology used to search for and select the employed
was used in our designs to minimize the power and area            model. For our selected model, latency was minimized us-
overhead of peripheral circuits and tile interconnects, which     ing O BJmin . L, D, and β were fixed to values determined
are much larger when smaller fixed modular tiles are used.        empirically using a preliminary exploratory analysis, and α
                                                                  was optimized as per Algorithm 1. The following additional
                                                                  hardware design constraints were imposed for our design: all
B. Model Search and Selection                                     convolutional layers must be capable of fitting onto one mod-
   Most current state-of-the-art CNNs employ sequential con-      ular crossbar tile, and the total number of required modular
volution layers, whereby subsequent convolution operations        crossbar tiles must not exceed 8.
are dependent on results from previous layers. However, in           As the convolution operation bottlenecks CNN inference,

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                    5


the size of kernels used in parallel convolution layers need to
be carefully considered to optimize both network performance
and latency. In our proposed architecture, shown in Fig. 2(f),
we have two parallel convolution layers and one average pool-
ing layer, comprising one convolutional block. To parallelize
the two convolution layers, it would be necessary to map the
weights of the two convolution layers onto two separate cross-
bars. As a design choice, we wanted to retain the flexibility
of mapping both convolution layers onto the same crossbar, if
space complexity is prioritized over latency. Therefore, during
the kernel size search, we imposed a constraint of 62, i.e.,
m − 2, for the sum of convolution kernels, as 2 additional
rows are designated for implementing the bias for both parallel
convolution layers.


   When denoting the kernel size of the first parallel con-
volutional layer as α, the kernel size of the second parallel
convolutional layer can be expressed as 62 − α. To determine
                                                                   Fig. 3. Architecture hierarchy of our memristive DL accelerator with (a)
the optimal network architecture, the University of Bonn’s         TDM and (b) Parallelized Implementation.
EEG seizure dataset [63] was used. Specifically, a 80:20 train
validation split was employed, and E VAL(Net) was used to
determine the 5-fold cross validation accuracy. Seed values        C. Hardware Architecture Hierarchy
of 32 and 8 were arbitrarily set for the network architecture         In Fig 3, we present our hardware architecture hierarchy.
search, to ensure reproducibility of results, and to reduce bias   The processing engines comprises 7 memristive crossbar array
between search and validation.                                     tiles, as well as I/O registers, eDRAM buffers, and peripheral
                                                                   circuits for ReLU, subtract, and average pooling. We present
   Empirically, L = 1, D = 2, and β=[8,] achieved substantial      two configurations for our tile, Time-Division Multiplexing
performance. For the single convolutional block, α0 was            (TDM), and parallelized. In the TDM case, each tile contained
varied between 31 and 60. A validation accuracy of 100%            a S+H and an ADC for reading out column currents, and one
was achieved for all values of α0 , except for α0 = 60, which      DAC per row for reading inputs in parallel, as shown in Fig.
achieved an optimal validation accuracy of 99.375%. This           3(a). In the parallelized case, each tile contains 64 ADCs, as
is not surprising, as the window size of input data is only        shown in Fig. 3(b).
64. Therefore, convolution kernel sizes of 60 and 2 provides
                                                                                  IV. S OFTWARE M ETHODOLOGY
two extreme and dramatically different receptive fields. In
particular, a kernel size of 2, which corresponds to around           To train and evaluate our epileptic seizure detection and
10ms of data at 173.61Hz, is likely insufficient to capture        prediction system, we benchmarked our system using one
local correlation and learn seizure characteristics. The final     epileptic seizure detection task and two epileptic seizure
model was chosen using Occam’s razor principle, whereby            prediction tasks. For epileptic seizure detection, the University
the simplest model is the best model. Consequently, a kernel       of Bonn’s EEG seizure dataset [63] was used. For epileptic
size of 32 was selected, as a kernel size 31 would be the          seizure prediction, the CHB-MIT Scalp EEG [64], and the
simplest to implement due to symmetric convolution kernel          long-term SWEC-ETHZ iEEG [65] datasets were used.
sizes; however 32 provides a more diverse receptive field.            To perform epileptic seizure detection and prediction, EEG
To further demonstrate the advantage of varied kernel size,        and iEEG samples can be categorized as either ictal, interictal
a 5-fold cross-validation was performed using a) 64 filters        or preictal. Ictal samples indicate the presence of a seizure,
of kernel size 31 b) two parallel convolution layers each          interictal samples are periods between seizures, and preictal
with 32 filters of kernel size 30 and 32 (see Fig. 2). It was      samples can be used to detect the onset of a seizure. For
observed that both networks are capable of achieving accuracy      epileptic seizure detection, binary classification is performed
varying between 99.61% to 99.83%, but varied kernel size           between ictal and interictal samples. For epileptic seizure
leads to +0.03%, -0.01%, +0.02% change in performance              prediction, binary classification is performed between preictal
on Bonn, SWEC-ETHZ and CHBMIT datasets, respectively,              and interictal samples. For both epileptic seizure detection
compared to using 64 filters of kernel size 31. Although a         and prediction tasks, on account of unbalanced classes, 5-fold
small degradation in performance is observed for SWEC-             cross validation was used to train and validate our network
ETHZ dataset, improvements are observed for both Bonn              architecture.
and CHBMIT dataset. A net improvement is observed for
both seizure detection and prediction using a varied kernel        A. Training and Evaluation Methodologies
size, while both experiments employ an identical number of           1) Epileptic Seizure Detection: The University of Bonn’s
weights.                                                           EEG seizure dataset is comprised of 5 sets (A-E), where set

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                                                                         6


                           TABLE I                                                                                                              with 16-bit resolution, using 26-100 electrodes. During data
OVERVIEW OF CASES USED TO PERFORM EPILEPTIC SEIZURE PREDICTION                                                                                  acquisition, after analog-to-digital conversion, a digital band-
 FROM THE CHB-MIT S CALP EEG (CHB-MIT) AND THE LONG - TERM
          SWEC-ETHZ I EEG (SWEC-ETHZ) DATASETS .                                                                                                pass filter was used to filter signals between 0.5 and 150Hz
                                                                                                                                                using a fourth-order Butterworth filter. Moreover, forward and
 Patient    Seizures       Interictal Hrs.∗       Preictal Hrs.∗        Interical Smp.†    Preictal Smp.   Synthetic Preictal Smp.            backward filtering was applied to minimize phase distortion.
                                                                      CHB-MIT
 1                   7                33.74                    0.43                1,898              24                                   42
                                                                                                                                                   Due to computation burden of crossbar simulation, we
                                      32.85
                                      30.86
                                                               0.14
                                                               0.39
                                                                                   1,848
                                                                                   1,736
                                                                                                                                           37   report the performance using the first 5 viable cases of the
 5                   5                33.85                    0.30                1,904              17                                   30
 8                   5                14.93                    0.36                  840              20                                    3   the CHB-MIT Scalp EEG and long-term SWEC-ETHZ iEEG
                                                                 SWEC-ETHZ
                                                                                                                                                datasets, reducing the computation required, similar to [15],
 1                   2                19.91                    1.00                1,120              56                                  108
                                      19.91
                                      29.87
                                                               1.00
                                                               1.99
                                                                                   1,129
                                                                                   1,680
                                                                                                                                                [66]. In Table I, we present an overview of all cases used
                                      29.87
                                      69.69
                                                               1.99
                                                               3.48
                                                                                   1,680
                                                                                   3,920
                                                                                                                                                to perform binary classification between preictal and interictal
     ∗ Hours. † Samples.                                                                                                                        samples. A case was categorized as viable if it contained valid
                                                                                                                                                labels (namely time-stamps) and data files (i.e., no recording
     (a) Continuous Preictal Segment
                                                                                                                                                files were missing or corrupt). For both datasets, the first 22
     0m
                  Synthetic Samples
                                                              30m                                                                               channels of each patient were extracted and used. All signals
                                                                        (b)
                                                                                                                                                were down-sampled to 256Hz, and a window size (batch size)

                                                                                                                          Seizure Event
           Sample 1
                  Sample 2
                         Sample 3
                                                                         SPH                      SOP                                           of 64s was used when extracting samples. After discarding
                                    Sample n-2
                                           Sample n-1
                                                                                                                                                seizures that occur in the first 20-minute monitoring period,
            64s                                                               5m                    30m
                                                   Sample n
                                                                                                                                                a Seizure Occurance Period (SOP) of 30m and a Seizure
                                                                                                                                                Prediction Horizon (SPH) of 5m were used to extract and label
Fig. 4. Depiction of (a) our adopted overlapped sampling technique extracting                                                                   preictal samples for all cases; both of which have previously
n samples from a continuous preictal segment, and (b) the SPH and SOP
terms. As can be seen, continuous preictal segments are extracted during the                                                                    demonstrated significant performance [66]. These terms are
SPH. All preictal samples that occur during the SOP period are discarded.                                                                       defined visually in Fig. 4. Interictal samples were extracted
                                                                                                                                                from one hour recording segments containing no seizures (ictal
                                                                                                                                                samples) to reduce class inbalance during training.
A is normal with open eyes, set B is normal with closed eyes,                                                                                      Next, 176 features per sample were extracted (8 per channel
set C and D is seizure free intervals, and set E is seizure                                                                                     per window/batch interval): the mean, variance, skewness,
only activities. Each set contains 100 single-channel EEG time                                                                                  kurtosis, coefficient of variation, median absolute deviation of
series of 23.6 seconds, with 4,096 samples in each time series.                                                                                 EEG amplitude and Root Mean Square Amplitude (RMSA),
All data were collected at 173.61 Hz, at a resolution of 12 bits.                                                                               and the shannon entropy. Since the input size of the proposed
To perform binary classification between ictal and interictal                                                                                   network is 64, the dimensionality of the input data needed to
samples, all samples from sets A and E were used.                                                                                               be reduced. A correlation analysis was first performed across
   Both sets (A and E) were divided into samples of 64 seconds                                                                                  the 176 extracted features, but no particular channel could be
periods and randomly shuffled. No augmentation and pre-                                                                                         removed as no strongly correlated channels were discovered.
processing techniques, such as normalization, were performed,                                                                                   Using Principal Component Analysis (PCA), linear dimen-
as CNNs are capable of automatic feature extraction from                                                                                        sionality reduction via Singular Value Decomposition (SVD)
time-series data and are robust to noise. The lack of need                                                                                      enabled the projection of data to lower dimensional space of 64
for pre-processing steps implies reduced hardware complexity                                                                                    principal axes. During training, synthetic preictal samples were
to perform such operations. Using the network model (with                                                                                       generated using an overlapped sampling technique inspired
optimal kernel sizes determined in Section III-B), a 5-fold                                                                                     by [44], by sliding a 64s window with a stride of 32s across
cross-validation strategy was used to determine network’s                                                                                       continuous preictal segments extracted during the SPH period,
performance. To determine performance, the mean of left out                                                                                     as depicted in Fig. 4. The same cross-validation training and
set accuracy, sensitivity, specificity, false-positive rate and the                                                                             evaluation strategy and metrics as described in Section IV-A1
AUROC across folds of 5-fold cross-validation were reported.                                                                                    was employed.
   2) Epileptic Seizure Prediction: The CHB-MIT Scalp EEG,
and the long-term SWEC-ETHZ iEEG datasets were used.                                                                                                          V. H ARDWARE M ETHODOLOGY
The CHB-MIT Scalp EEG dataset comprises of 23 cases,
                                                                                                                                                   In this section, we discuss our device technology selec-
which were collected from 22 subjects (5 males, ages 3–22;
                                                                                                                                                tion, memristor crossbar array implementations of CNNs, and
and 17 females, ages 1.5–19). The last case was obtained 1.5
                                                                                                                                                present our adopted hardware simulation methodology.
years after the first, from one of the female subjects [64]. All
signals were sampled at 256Hz with 16-bit resolution, using
23-26 electrodes. During data acquisition, no augmentation                                                                                      A. Device Technology Selection
steps were performed.                                                                                                                              Computing with charge-based computing devices is attrac-
   The long-term SWEC-ETHZ iEEG dataset comprises of 18                                                                                         tive due to their technological maturity, even though they have
patients with pharmaco-resistant epilepsy, who were evaluated                                                                                   a relatively large area footprint even at advanced technology
for surgery at the Sleep-Wake-Epilepsy-Center (SWEC) of                                                                                         nodes and face severe scaling challenges [67]. Resistance-
the University Department of Neurology at the Inselspital                                                                                       based memory, in contrast, can be scaled to the nanometer
Bern [65]. All signals were sampled at either 512Hz or 1025Hz                                                                                   scale, and has the potential of forming cross-point structures

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                                                                                     7


(a)                               (b)                                                (c)                       nker                               Tile 1                    Tile 2                       Tiles 3-6
Input                             x0         Input                                                 x0
                                  x1    x0
x0                                                                                                 x1
                                  x2    x1   x0                                                           kernel 3
                                                                                                                       kernel j
x1               kernel 2                                                                          x2
x2            kernel 2            x3    x2   x1   x0                                       nin            kernel 2                lker
           kernel 2               x4    x3   x2   x1
x3      kernel 2                                       kernel 2                                           kernel 1
                                  x5    x4   x3   x2
x4               kernel 1
              kernel 1            x6    x5   x4   x3   kernel 1                                    xi
x5
           kernel 1               x7    x6   x5   x4
x6
x7
        kernel 1                        x7   x6   x5                                 (d)         if nin-lker > nker:
                                             x7   x6


                                                                  Output
                                                       x 0 x0              (at t1)

        x0 x1 x2 x3 x0 x1 x2 x3
                                                  x7
                                                       x 1 x1              (at t2)                       Use scheme (a)
                                  t4    t3   t2   t1   x 2 x2              (at t3)               else:
                  Output                               x 3 x3              (at t4)
                                                                                                         Use scheme (b)

                                                                                                                                                  Tile 7                                  Legend

Fig. 5. A comparison of possible mapping schemes. (a) visualizes the
staggering mapping of convolution weights, which is commonly adopted due                                                                                              First Convolutional Layer
                                                                                                                                                                      Weights | conv1            First Fully Connected Layer
to its ability to produce all results within a single pass through the crossbar                                                                                       First Convolutional Layer
                                                                                                                                                                                                 Weights | fc1
array. (b) visualizes our proposed mapping scheme, without staggering of                                                                                              Biases | conv1             Second Fully Connected Layer
                                                                                                                                                                                                 Weights | fc2
convolution weights and sparsity in crossbar, at the cost of increased read/write                                                                                     Second Convolutional Layer
operations. (c) provides a comparison of methods (a) and (b), visualizing when                                                                                        Weights | conv2            Unused Devices
one method should be chosen over the other.                                                                                                                           Second Convolutional Layer
                                                                                                                                                                      Biases | conv2


without using access devices, achieving ultra high density.
RRAM devices are used in our design, as they are widely
                                                                                                                                         Fig. 6. The crossbar parameter mapping layout adopted. Seven 64 × 64
considered to be the most promising emerging resistance-                                                                                 modular crossbar tiles are utilized. Bias terms of fully connected layers,
based memory technology- they operate faster than Phase-                                                                                 and the single pooling layer, pool1, are computed using additional digital
Change Memory (PCM), have a simpler and smaller cell struc-                                                                              circuitry. To reduce the number of unused devices, parameters of different
                                                                                                                                         layers are shared between tiles.
ture than Magnetoresistive Random-Access Memory (MRAM)
and Conductive Bridging Random-Access Memory (CBRAM)
devices, and are made of materials that are common in
semiconductor manufacturing [67].                                                                                                        in Fig. 5(a). This naive approach is extremely space demand-
                                                                                                                                         ing, as the kernels are staggered multiple times throughout
                                                                                                                                         the crossbar array, rendering a lot of memristive cells unused.
B. Memristor Crossbar Array Implementations of Parallel
                                                                                                                                         To reduce the space requirement of mapping scheme (a), one
CNNs
                                                                                                                                         possible approach is to build upon the input-stationary concept.
   Consider the conductance values of a crossbar array as a                                                                              One may remap the crossbar weights during inference and
matrix and input voltages to a crossbar as a vector. The output                                                                          replace them with different kernel weights, while reusing the
current from the crossbar, determined using Kirchoff’s and                                                                               input fetched from memory.
Ohm’s Law represents the result of the VMM. Such operations                                                                                 On the other hand, one may build upon the weight-stationary
form the core of CNNs. Being able to accelerate and paral-                                                                               concept, as depicted in Fig. 5(b). In this scheme, convolution
lelize them would facilitate the real-time operation of deeper                                                                           kernels can be mapped without staggering before inference.
and heavier neural networks for epileptic seziure detection and                                                                          For kernels to convolve against different parts of the signal, the
prediction in resource-constrained hardware [68].                                                                                        input signal slides. The bottleneck of this approach now lies
   To represent signed weight matrices on memristive crossbar                                                                            within fetching input data, requiring additional read/write op-
arrays, as negative conductance values cannot be expressed us-                                                                           erations on the peripheral of the crossbar compared to mapping
ing analog memristive devices, a differential mapping scheme                                                                             scheme (a). The weight-stationary approach is more efficient
was adopted, where two columns of memristors are chosen                                                                                  compared to the input-stationary approach, as crossbar weight
to represent positive and negative weights, respectively. The                                                                            writes can be very time and energy consuming, compared to
signed output is thus the arithmetic difference of current from                                                                          fetching of inputs and staggering them with shifting circuitry.
both columns. In the case of 1D CNNs, fully connected                                                                                    Fig. 5(c) provides visualization of when one scheme should
and convolutional layers can be decomposed into a series                                                                                 be adopted over the other.
of dot products between inputs, represented as voltages, and
                                                                                                                                            A comparison of the naive approach and our proposed
weights, represented as memristive conductance. For convo-
                                                                                                                                         weight-stationary approach is performed for our network ar-
lutional layers, the im2col algorithm [69] can be used to
                                                                                                                                         chitecture in Table II. As can be observed, the number of
map convolutional kernels onto separate crossbar columns.
                                                                                                                                         memristor cells required for scheme (b) (depicted in Fig. 5
With a single pass, m 1D convolutions can be performed
                                                                                                                                         (b)) is significantly smaller, due to the compact nature of the
simultaneously, where m represents the number of columns.
                                                                                                                                         mapping. This comes, however, at the cost of 33x increase
Average pooling and ReLU operations are performed using
                                                                                                                                         in computation. When taking sparsity, i.e. unused memristors
additional digital circuitry.
                                                                                                                                         depicted by the gray background in Fig. 5 (a), into considera-
                                                                                                                                         tion, scheme (b) demonstrates even more significant reduction,
C. Hardware Simulation Methodology                                                                                                       i.e. 63x-73x fewer memristors required, while the computation
   Based on existing literature from Section II-C, all mapping                                                                           increase remains constant. Unlike convolutional layers, fully
of convolution kernels onto crossbars are sparse, whereby the                                                                            connected layers do not involve sliding of signals, so VMMs
convolution kernels form a sparse diagonal matrix, as depicted                                                                           for fully connected layers were implemented using the naive

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                                                       8


                                                                 TABLE II
                    C ROSSBAR MAPPING COMPARISON FOR SPACE AND COMPUTATION TRADE - OFF USING SCHEMES ( A ) AND ( B ) IN F IG . 5.


                                  Number of Memristor Cell Required                                               Number of Memristor Cell Required Inc. Sparsity
 Layer
               Scheme (a)      Scheme (b)       Area Reduction         Computation Increase          Scheme (a)        Scheme (b)        Area Reduction        Computation Increase
 conv1              69,696            2,112                    33x                            33x           133,184           2,112                   63x                           33x
 conv2              69,440            1,984                    35x                            35x           145,600           1,984                   73x                           35x
 fc1                17,424           17,424                   None                           None            17,424          17,424                  None                          None
 fc2                    36               36                   None                           None                36              36                  None                          None


                                                                     TABLE III
               5-F OLD CROSS - VALIDATION RESULT FOR EPILEPTIC SEIZURE DETECTION AND PREDICTION USING OUR NETWORK ARCHITECTURE .

 Dataset           Bonn                                        CHB-MIT                                                                       SWEC-ETHZ
 Partition       Set A vs. E      Patient 1       Patient 2       Patient 3      Patient 5      Patient 8        Patient 1       Patient 2       Patient 3       Patient 5       Patient 6
 Accuracy       99.84 ± 0.37   99.50 ± 0.89    99.95 ± 0.11    99.95 ± 0.13   99.73 ± 0.57   98.96 ± 2.33    100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00    99.86 ± 0.22   100.00 ± 0.00
 Sensitivity    99.87 ± 0.28   98.64 ± 2.79   100.00 ± 0.00   100.00 ± 0.00   99.62 ± 0.70   99.76 ± 0.54    100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00
 Specificity    99.80 ± 0.45   99.73 ± 0.37   100.00 ± 0.00    99.93 ± 0.15   99.77 ± 0.52   97.38 ± 5.85    100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00    99.77 ± 0.39   100.00 ± 0.00
 FP per Hour            N/A     0.13 ± 0.17     0.00 ± 0.00     0.03 ± 0.07    0.10 ± 0.22    0.53 ± 1.19      0.00 ± 0.00     0.00 ± 0.00     0.00 ± 0.00     0.08 ± 0.13     0.00 ± 0.00
 AUROC          99.84 ± 0.37   99.31 ± 1.06   100.00 ± 0.00    99.82 ± 0.39   99.63 ± 0.79   99.04 ± 2.15    100.00 ± 0.00   100.00 ± 0.00   100.00 ± 0.00    99.84 ± 0.25   100.00 ± 0.00


scheme (a). Using scheme (b), we mapped convolutional                                          demonstrated to severely impact the performance of mem-
kernels within our trained network onto crossbars tiles of                                     ristive DL accelerators [70]. Consequently, they should be
64×64. While scheme (b) was chosen for our hardware design,                                    comprehensively simulated prior to circuit-level realization.
if scheme (a) were chosen with different nker and lker values,                                 In this paper, preliminary simulations were performed using
or the added space complexity is not of concern, the staggered                                 the MemTorch [71] simulation framework, and comprehen-
weights of scheme (a) would enable all rows of the crossbars to                                sive simulations of the system using passive crossbar arrays
be employed simultaneously. By choosing the input size of our                                  were performed using the crossbar array model provided
network to be 64, we maintain the flexibility of mapping with                                  by [72]. Non-idealities considered include input and output
scheme (a) to make use of all crossbar rows simultaneously.                                    resolutions, weight write resolution, weight write deviation,
   As Fig. 6 demonstrates, for parallel convolution layers to                                  stuck RON /ROFF devices, line and source resistance, and
be accelerated simultaneously, it was necessary to map the                                     conductance range variation.
weights of the conv1 and conv2 onto two separate crossbar                                         Other memristive phenomena, such as the dynamic behav-
tiles. The weight of the fc1 layer is a matrix of 1088×8, and                                  ior of switched memristive neural networks after program-
using a differential weight scheme, would require 1088×16                                      ming [73], and read disturbance [74], are not accounted for,
memristors. The weight matrix can be further divided into 17                                   as practical metal-oxide memristors are endurance-limited,
sections of 64×16 weights. To maximize the usage of each                                       during programming a write-verify scheme is used, and during
64×64 crossbar array, 4 sections of 64×16 weights can be                                       inference, all Bit Line (BL) voltages are constrained to have
stacked horizontally onto each crossbar, requiring a total of 5                                a maximum absolute amplitude of 0.3V [74].
crossbar tiles.
   Since there are unused memristors on the convolution tiles
                                                                                               E. Stuck Weight Offsetting Methodology
and fc2 layer operations are not performed immediately after
convolution operations, we decided to map the weights of fc2                                      Stuck RON /ROFF weights are known to cause significant
onto the convolution layer tile, instead of using another tile.                                network performance degradation in memristive crossbar ar-
Note that since the simulation serves as a validation for proof-                               rays. Existing works have demonstrated performance recovery
of-concept, we decided to use the same dimensions for all                                      through a variety of techniques. In 2014, Kannan et al. took
7 crossbar tiles. We do recognize that tile 1, 2 and 7 have                                    inspiration from SRAM/DRAM technologies and repaired
many unused memristor devices, as a result, performing small                                   crossbar defects using redundant rows and columns [75].
VMMs on a large switch matrix. This leads to large power                                       In 2017, Liu et al. proposed to identify significant weights
overhead due to high amortized ADC/DAC power over a small                                      before applying a retraining and remapping algorithm [76].
matrix and charge/discharge of long row and column wires                                       In 2018, Xia et al. proposed a mapping algorithm with inner
without using full length for computation. To address such                                     fault tolerance to leverage the differential mapping scheme
problem in a real medical device, instead of using square tiles,                               of crossbar arrays to tolerate faults [77]. In 2019, Zhang et
tile 1, 2 and 7 can be easily mapped onto rectangular tiles of                                 al. proposed the use of matrix transformations to reduce the
the exact required dimensions.                                                                 magnitude of error introduced by stuck-at-fault devices [78].
                                                                                               Also in 2019, Yeo et al. modified conventional transimpedance
                                                                                               amplifiers to detect when abnormal current is detected at a
D. Impact of Device and Crossbar Non-Idealities                                                particular column due to stuck-at-fault devices and repair by
  Memristors and memristive crossbar arrays are prone to                                       retraining the network with the known defects [79]. Among
numerous device and circuit non-idealities which have been                                     those works, significant hardware or software overhead is

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                             9


                           TABLE IV                                                                  quantized, while intermediate outputs remained not quantized.
C OMPARISON OF OUR BASELINE SOFTWARE MODEL AGAINST SOTA FOR                                          Network architecture and other training parameters remained
   S EIZURE D ETECTION USING THE U NIVERSITY OF B ONN DATASET
                                                                                                     unchanged.
 Paper                       Pre-processing   Method   Parallelization   Parameters   Accuracy (%)
 Ullah et al. (2018)
 We et al. (2018)
                                              1D-CNN
                                              1D-CNN
                                                                             21,436
                                                                         16,778,144
                                                                                             99.90
                                                                                             92.00
                                                                                                                   VI. R ESULTS AND D ISCUSSION
 Abdelhameed et al. (2018)         3          2D-CNN         7              106,388          98.00
 Liu et al. (2019)                 3          2D-CNN         7                N/R∗           99.60      Prior to the investigation of device and crossbar non-
 Turk et al. (2019)                3          2D-CNN         7            1,603,080          99.45
 Abdelhameed et al. (2021)         3          2D-CNN         7           10,304,467         100.00   idealities, we report baseline software results for epileptic
 Ours                              7          1D-CNN         3               10,778          99.84   seizure detection and prediction using our network archi-
    ∗ Not reported.                                                                                  tecture, in Table III. 5-fold cross-validation was performed
                                                                                                     using a different seed to eliminate bias on the first fold.
                                                                                                     To demonstrate the generalizability of the designed network
introduced through rewriting and tuning of weights, retraining                                       to different domains and patients, the same architecture was
of networks or using additional circuitry.                                                           applied for seizure detection and prediction. Unlike the Bonn
   To minimize the overhead, we propose stuck weight offset-                                         dataset, both the CHB-MIT and SWEC-ETHZ datasets are
ting, which improves upon the inner fault tolerance method.                                          multi-channel EEG datasets with larger memory and com-
Inner fault tolerance first identifies all available (non stuck-at-                                  putation requirements within the time domain. In order to
fault) devices and initializes them to default values. Then, the                                     reduce the time and memory complexity, pre-processing steps
scheme goes through all available devices and adjusts each                                           as described in Section IV-A2 were applied to transform the
value such that the represented values cannot be made any                                            dataset into frequency domain. The shown results suggest that
closer to the target matrix parameter. Intuitively, this serves to                                   the proposed network is sufficient and can generalize well for
minimize the incorrect contribution of the RON /ROFF weight.                                         both detection and prediction.
We propose to bypass the initialization of available devices
to default values and to focus on the complementary weight                                           A. Comparisons Against SOTA Software Implementations
of stuck-at-fault devices only. Before writing any weights to
                                                                                                        In Tables IV and V, we compare our baseline software
the crossbar, all stuck-at-fault devices are identified. For each
                                                                                                     implementations that use full precision (32-bit) floating-point
stuck-at-fault device, if the complementary weight is not stuck-
                                                                                                     parameters against other software implementations in literature
at-fault, we calculate its complementary weight to minimize
                                                                                                     for epileptic seizure detection and prediction, respectively.
the difference between represented value and target value. All
                                                                                                     As shown in the Tables, for epileptic seizure detection we
calculated values, along with normal weights, are then written
                                                                                                     achieve SOTA performance in 3/4 criteria, while for prediction
onto the crossbar. This modification reduces overhead by two
                                                                                                     we obtain SOTA performance in 3/6 criteria. Specifically,
means. First, all crossbar weights are only required to be
                                                                                                     for detection, our network architecture is able to achieve
written once, as opposed to twice in the inner fault tolerance
                                                                                                     an accuracy of 99.84% across all samples without any pre-
method (from default to adjusted). Second, our method focuses
                                                                                                     processing steps, while requiring only 10,778 parameters. This
on complementary weights for stuck-at-fault devices only, as
                                                                                                     is ∼2x fewer parameters than the smallest model in [28],
opposed to all available devices for all target parameters. This
                                                                                                     which achieved a slightly higher accuracy of 99.90%, while
method incurs minimum additional computational cost, and
                                                                                                     employing various pre-processing steps. Except for the model
does not require retraining.
                                                                                                     used in [87], which achieves a 100% accuracy, but requires
                                                                                                     over 10M parameters, all the other models shown in Table IV,
F. Quantization Aware Training for Lower Resolution Systems                                          achieve lower accuracy values despite significantly higher
   A high resolution system is often not feasible to deploy on                                       number of network parameters.
edge devices, given power consumption constraints and sam-                                              For epileptic seizure prediction, pre-processing is per-
pling frequency requirements, which are fundamental tradeoffs                                        formed. Across both datasets, our network architecture
for resolution in DACs and ADCs. However, lower resolution                                           achieves the highest sensitivity while requiring the fewest
systems with improved power and frequency performance can                                            number of parameters. We report close specificity and accu-
exhibit performance degradation. This effect was observed for                                        racy values to [15], which has also used a 1D-CNN archi-
some patients, and more details can be found in Section VI-C.                                        tecture with parallelization, but needs ∼10x more parameters.
For significant performance degradation (a degradation of 5%                                         Finally, we report the highest FPR across both datasets, how-
or more compared to full resolution system), we propose to                                           ever, unlike previous works, we performed no post-processing
perform Quantization Aware Training (QAT) prior to mapping                                           steps, which may cause this. Also, only two out of the nine
the weights onto memristive crossbar arrays [86]. During                                             previous works have reported their FPR, which makes the
QAT, we quantized the convolutional and fully connected                                              comparison incomplete. When mapping trained parameters to
layers of the network to the resolution equivalent to or even                                        ideal crossbars with fully analog devices without any device
lower than that of the resolution of the crossbar weights                                            or circuit non-idealities, the same results were achieved.
and ADC/DAC resolution. Quantized layers are implemented
using the Brevitas library [86], which provides PyTorch-                                             B. Generalization Between Datasets
compatible convolution and fully connected layers of specified                                         To determine whether or not our trained networks have
weight resolutions. In addition, inputs to the network were                                          the ability to generalize, we evaluated the performance of

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                        10


                                                                TABLE V
                     C OMPARISON AGAINST SOTA FOR S EIZURE P REDICTION USING THE SWEC-ETHZ AND CHB-MIT DATASETS


                 Paper         Method         Parallelized    Parameters      Sensitivity (%)     Specificity (%)     Accuracy (%)       FPR†
                                                                          CHB-MIT
                  [66]        2D-CNN               7                 N/R                81.20              N/R               N/R       0.16
                  [80] *      2D-CNN               7                N/R                 N/R               N/R               92.00     N/R
                  [81]        2D-CNN               7               49,560                82.71              88.21              98.19     N/R
                  [82] *      2D-CNN               7                N/R                 88.80              88.60              88.70     N/R
                  [83] *      3D-CNN               7           28,459,615                96.66              99.14              98.33     N/R
                  [84] *      2D-CNN               7            9,695,012                84.00              99.00              99.00       0.2
                  [15]        1D-CNN               3              105,538                95.55              99.68              99.64     N/R
                 Ours         1D-CNN               3               10,778                99.24              98.68              99.01       0.47
                                                                        SWEC-ETHZ
                  [85] *    Ensemble HD            7                N/R                 96.38              97.31              96.85     N/R
                  [15]        1D-CNN               3              105,538                94.57              99.86              99.81     N/R
                 Ours         1D-CNN               3               10,778                98.22              97.02              97.54       0.99

   *Indicates the results are reported across the entire dataset and patient-wise performance was not reported. † False positive rate (per hour).  Not reported.


Fig. 7. The ability of our trained networks to generalize between different datasets when performing epileptic seizure prediction. The cross validation accuracy
is reported for networks which have not been retrained, and for networks that have been retrained after 1 and 10 training epochs, respectively, when transfer
learning was performed. In addition, the standard evaluation accuracy is reported for each dataset and patient, to facilitate comparisons.


networks trained using the CHB-MIT dataset on the SWEC-                           is structured differently.
ETHZ dataset, and vice-versa in Fig. 7. In addition, we
report the cross validation accuracy for networks which have                      C. Quantization-Aware Training
been retrained using transfer learning. To perform transfer                         To demonstrate the effectiveness of QAT, we evaluated the
learning, parameters were frozen for all layers except the                        performance of our network architecture when trained with
last two fully connected layers, and the weights and biases                       and without QAT. Comparisons are made in Fig. 9. During
of the last two fully connected layers were re-trained using                      QAT training, inputs and network weights were reduced to
the training set of the evaluation dataset. Direct evaluations                    6-bit resolution, while network architecture and other training
to/from either of these datasets and the University of Bonn                       parameters were held constant, as described in Fig. 2(f). The
dataset were not made, as the University of Bonn dataset is                       accuracy, sensitivity, specificity, AUROC, and FPR metrics
used for epileptic seizure detection and not prediction, and it                   were all reported and compared. When using 6-bit ADCs and

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                               11


     (a)                                  (b)                                   (c)                                   (d)


     (e)                                   (f)                                  (g)                                  (h)


                             University of Bonn                         CHB-MIT                            SWEC-ETHZ
                            Averaged Across Seeds                Averaged Across Patients             Averaged Across Patients


Fig. 8. The impact of all (a-g) non-idealities on the University of Bonn, CHB-MIT, and SWEC-ETHZ datasets. (h) summarizes performance recovery by
applying our proposed stuck weight offsetting to address the performance degradation of stuck-at fault devices. For the University of Bonn dataset, each
data-point shows the mean and standard deviation across five arbitrary seed values: 5, 6, 7, 8, and 9.


DACs, it can be observed that for all patients and metrics,                  above, system performance can drop below 50% accuracy,
except for specificity of patient 5 from the CHB-MIT dataset,                rendering the system ineffective. In response to such degrada-
QAT network yields significant performance improvements.                     tion, we apply our proposed simplified stuck weight offsetting
                                                                             method. Comparing Fig. 8(h) against (d), it is evident that the
                                                                             stuck weight offsetting method improves the average accuracy
D. Effects of Non-Idealities on System Performance
                                                                             across all stuck device percentages and datasets. At 1% stuck-
   Fig. 8 provides a summary of the impact of non-idealities                 at fault, the average accuracy improved by as much as 20%
on our system for epileptic detection and prediction. For the                for the Bonn dataset and more than 10% for SWEC-ETHZ
University of Bonn dataset, as samples between patients are                  and CHB-MIT. The largest improvement was found for the
not explicitly distinguished, the mean and standard deviation                CHB-MIT dataset at 5% stuck-at fault, improving accuracy by
of test set accuracy is reported across samples using five                   32.11%. At higher stuck device percentages, reduced accuracy
arbitrarily chosen seed values. For the CHB-MIT and SWEC-                    recovery is observed. This can be explained by the fact that at
ETHZ datasets, the mean and standard deviation of test set                   higher stuck device percentages, more network information
accuracy is reported across samples for the first five viable                cannot be recovered. Minimizing the contribution of stuck
patients of each dataset, respectively. Across datasets, some                weight cannot fully retrieve the missing information, thereby
patients were observed to be more robust to non-idealities                   leading to reduced accuracy recovery. In addition, the proposed
than others. This was observed in our investigations for                     method greatly reduces the standard deviation across patients
patients 1, 2, 3 from the SWEC-ETHZ dataset, and patient                     and seeds, thanks to reduced contribution of stuck RON /ROFF
2 from the CHB-MIT dataset, for which non-idealities have                    devices to final output.
minimal impact. For the rest of the patients, however, no
clear pattern was established with regards to robustness against                The limitation of this method lies within its inability to
non-idealities. We attribute the varying degree of effectiveness             deal with both elements of the complementary weight being
between patients to underlying patient specific signatures.                  stuck RON and ROFF simultaneously. If a positive (negative)
                                                                             weight is stuck RON and negative (positive) weight is stuck
                                                                             ROFF , stuck weight offsetting cannot provide any further
E. Stuck Weight Offsetting                                                   adjustment to minimize the error. Meanwhile, if both weights
   As observed in Fig. 8(d), stuck RON /ROFF devices lead                    are stuck RON or ROFF , the lost weights cannot be recovered,
to severe performance degradation. At 1% stuck-at fault and                  contributing nothing to the final output.

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                                                        12


(a)                                   (b)                                   (c)                                        (d)                                    (e)


                                                                                      Without QAT         With QAT


Fig. 9. The impact of QAT on our network architecture tasked for epileptic seizure prediction (a-e) evaluated using the CHB-MIT and SWEC-ETHZ datasets
when network parameters are quantized to 6-bit fixed-point resolution. Only patients that exhibited a degradation of 5% or more when quantized to 6-bit
fixed-point resolution (from full-precision floating-point) were investigated.

                                                                 TABLE VI
      P OWER , AREA , AND LATENCY METRICS FOR THE SIMULATED MEMRISTIVE DL ACCELERATOR USING A 22 NM CMOS PROCESS . U SING OUR TDM
      ARCHITECTURE , VMM S ARE PERFORMED IN O(n), WHERE n IS THE NUMBER OF COLUMNS OF THE OUTPUT VECTOR . U SING OUR PARALLELIZED
                                                ARCHITECTURE , VMM S ARE PERFORMED IN O(1).


                                                        Time-Division Multiplexing (TDM)                                                            Parallelized
 Component         Params.
                                                       Area     Power    Latency      Total Latency        Energy                        Area     Power     Latency   Total Latency     Energy
                                   Specification                                                                     Specification
                                                     (mm2 )     (mW)       (us)*                (us)         (uJ)                      (mm2 )     (mW)        (us)*             (us)      (uJ)
                   Resolution         6 bits                                                                            6 bits
 DAC                                               2.58E+01   2.69E+03   8.00E-04          2.15E+00    5.78E+00                      2.58E+01   2.69E+03   8.00E-04        3.36E-02    9.03E-02
                    Number            7x64                                                                              7x64
                   Resolution         6 bits                                                                            6 bits
 ADC                Number              7          4.62E+00   7.00E+01   1.00E-01          2.69E+02    1.88E+01         7x64         2.96E+02   4.48E+03   1.00E-01        6.00E-01    2.69E+00
                   Frequency         10MHz                                                                             10MHz
 ReLU                Number             2          9.60E-03   3.28E-02   9.80E-02          9.80E-02       3.22E-06        2          9.60E-03   3.28E-02   9.80E-02        9.80E-02    3.22E-06
 Average Pool        Number             1          3.83E-04   1.59E+00   8.49E-05          8.49E-05       1.35E-07        1          3.83E-04   1.59E+00   8.49E-05        8.49E-05    1.35E-07
 Adder               Number             10         5.34E-03   1.74E-02   3.06E-04          6.13E-04       1.06E-08        10         5.34E-03   1.74E-02   3.06E-04        6.13E-04    1.06E-08
 Subtractor          Number             7          2.46E-04   2.87E-01   3.34E-04          1.28E-01       3.69E-05       7x32        7.88E-03   9.20E+00   3.34E-04        2.01E-03    1.85E-05
 S+H†                Number            7x64        8.98E-06   3.81E-03   8.33E-04          5.00E-03       1.90E-08       7x64        8.98E-06   3.81E-03   8.33E-04        5.00E-03    1.90E-08
                     Size              2KB                                                                               2KB
 eDRAM Buffer                                      4.72E-03   1.81E+01   1.15E-04          2.30E-04       4.17E-06                   4.72E-03   1.81E+01   1.15E-04        2.30E-04    4.17E-06
                   Bus Width           128                                                                               128
 eDRAM-Tile Bus      Number            192         4.50E-03    3.5E+00   9.02E-05          9.02E-05       3.16E-07       192         4.50E-03    3.5E+00   9.02E-05        9.02E-05    3.16E-07
 IR†                   Size            1KB         8.10E-01   6.74E-01   8.21E-05          1.64E-04       1.11E-07       1KB         8.10E-01   6.74E-01   8.21E-05        1.64E-04    1.11E-07
 OR†                   Size           512B         8.70E-04   4.18E-01   8.21E-05          1.64E-04       6.87E-08      512B         8.70E-04   4.18E-01   8.21E-05        1.64E-04    6.87E-08
                                                                                         Scenario: R¯ON
                     Number              7                                                                                7
 Crossbar              Size           64x64        2.87E-04   8.67E+00   2.03E-03          5.82E+01       5.06E-01      64x64        2.87E-04   8.69E+00   2.03E-03        1.30E-01    1.13E-03
                   Bits per cell        32                                                                               32
 Total                                             3.13E+01   2.79E+03                     3.29E+02    9.19E+02                      3.22E+02   7.21E+03                   8.70E-01    6.27E+00
                                                                                    Scenario: (R¯ON + ROFF
                                                                                                       ¯ )/2

                     Number              7                                                                                7
 Crossbar              Size           64x64        2.87E-04   4.35E+00   6.07E-03          1.74E+02       7.58E-01      64x64        2.87E-04   4.35E+00   6.07E-03        3.88E-01    1.69E-03
                   Bits per cell        32                                                                               32
 Total                                             3.13E+01   2.79E+03                     4.45E+02    1.24E+03                      3.22E+02   7.21E+03                  1.13E+00     8.12E+00

      ∗ The latency is listed as individual element. † S+H = Sample and Hold, IR = Input Register, OR = Output Register.


F. Power, Area, and Latency Requirements                                                            power consumption of 6 mW and a device area of 0.0576
                                                                                                    mm2 [107]. Other peripheral circuitry with different purposes,
   The following assumptions, all supported by SOTA DL                                              including the activation function [108], average pooling layer
accelerators, are made when estimating the power, area and                                          made up from 4-to-1 multiplexers [109], [110], Sample and
latency requirements of our proposed memristive DL acceler-                                         Hold (S+H) [111], subtractor [112], and adder [113] circuits,
ator depicted in Fig. 3, targeting a 22nm CMOS process with                                         were listed with more detail in Table VI.
device integration at the Back-End-Of-The-Line (BEOL). A
memristive device has a fixed area of 100 × 100 nm2 [103],                                            All the peripheral components are scaled to 22nm technol-
[104] and the device read latency is 6 ns [105]. An ADC oper-                                       ogy by factors introduced in [114] and all buffers with their
ating frequency is 10 MHz [105], with a power consumption                                           associated connections have energy, area and latency estimated
of 10 mW [105] and a device area of 1.1 × 0.6 mm2 [104],                                            by CACTI 7.0 [115]. For all calculations, the source resistance
[106]. A DAC operating frequency is 1.25 GHz, with per unit                                         and line resistance of 20 Ω and 2 Ω are used respectively.

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                          13


                                                         TABLE VII
         P ERFORMANCE SUMMARY AND COMPARISON OF OUR SIMULATED SYSTEM AND EXISTING SEIZURE DETECTION / PREDICTION SYSTEM
                                             IMPLEMENTATIONS IN THE LITERATURE .


                                                        No.          Analog      Feature      Area   Latency    Power    Energy                         Eval.
 Paper          Technology           Algorithm(s)                                                                                 Pred.
                                                      Channels     Front-End∗   Extract.†   (mm2 )        (s)   (mW)       (uJ)                       Task(s)
                                                                 ML-Based
                                     BPF,
 [88]           CMOS (180nm)                              8            3           3         25.00      2.00     N/R◦     N/R◦      7              CHB-MIT
                                     LSVM
 [89]           CMOS (180nm)         BPF, NL−SVM          8            3           3         25.00      2.00     N/R◦     N/R◦      7              CHB-MIT
 [90]           CMOS (130nm)         NL−SVM              18            7           3         N/R◦       4.80     N/R◦     N/R◦      7              CHB-MIT
                                     FFT,
                                                                                                                          2.24E
 [91]           CMOS (180nm)         ApEn,                8            3           3         13.47        0.8     2.80              7                 In Vivo
                                                                                                                            +03
                                     LLS
                                     BPF,
 [92]           CMOS (180nm)                             16            3           3          25.0        1.0    N/R◦     N/R◦      7              CHB-MIT
                                     D2 A−LSVM
                                     BPF,
 [93]           CMOS (180nm)                              8            3           3          25.0        2.0     0.23   460.00     7              CHB-MIT
                                     NL−SVM
 [46]           CMOS (130nm)         FIR, PLV            64            3           3          3.86     N/R◦       1.07    N/R◦      3                 In Vivo
                                     FIR, PLV/
 [94]           CMOS (130nm)                             32            3           3          7.59      0.25      0.71   177.50     3                 In Vivo
                                     SE/CFC
                                     DWT,
 [95]           CMOS (180nm)         KDE,                 8            3           3          5.83     N/R◦       0.67    N/R◦      3              CHB-MIT
                                     SVM
                                     FFT,                                                                                 1.35E
 [96]           CMOS (40nm)                              14            7           3          4.50      0.71      1.90              7              CHB-MIT
                                     NL−SVM                                                                                 +03
                                     CHT,
 [97]           CMOS (65nm)                              16            3           3          0.38     N/R◦       0.40    N/R◦      7      CHB-MIT, iEEG.org
                                     XGBoost−DT
 [98]           CMOS (180nm)         FFT                  1            3           3         N/R◦      N/R◦      7.89     N/R◦      7              CHB-MIT
                                                                                                                8.16E
 [99]           CMOS (90nm)          ICA                  8            7           3           0.4        0.1              8.16     7                 In Vivo
                                                                                                                   -02
                                                                                                                2.86E
 [72]           CMOS (180nm)         LLS                  1            3           3         10.41      0.72              20.59     7                 In Vivo
                                                                                                                   -02
                                                                 DL-Based
 [100]          CMOS (65nm)          RNN                  8            7           7         10.15     N/R◦     17.80     N/R◦      7                   N/R◦
                FPGA
 [101]                               MLP                  1            7           3         N/R◦      N/R◦     159.70    N/R◦      7                   Bonn
                (M2GL 025-VF256)
                                                                                                      64.98E    5.40E
 [102]          CMOS (180nm)         SNN                  1            7           3          0.15                         0.35     3                 In Vivo
                                                                                                          -03      -03
                                                                                                       4.45E    2.79E     1.24E
 Ours (TDM)     CMOS (22nm)/         Manual feature                                          31.25                                                   Bonn,
                                                         22            7           7                      -04     +03       +03
                RRAM (BEOL)          extraction,                                                                                                  CHB-MIT,
                                     CNN                                                               1.13E    7.20E                               ETHZ-
 Ours (Par.)                                                                                322.31                         8.12                     SWEC
                                                                                                          -06     +03
   ∗ Reported power, area, and latency requirements include the analog front end/signal acquisition component. † Reported power, area, and latency requirements
   include feature extraction component(s).  Denotes whether systems are able to perform epileptic detection and/or prediction. ◦ Not reported.


To account for RC delays within crossbars when signals are                       circuit area consumption was computed as the summation of
propagated, the methodology presented in [116] was used,                         all individual elements. Both ADCs and DACs were assumed
with CSA , Tsettling , and Cwrite parameters from [117]. The                     to operate at 6-bit resolution, as stated in Section VI-C, for
largest total device latency was used for all devices.                           the best performance with QAT.
   In Table VI, four scenarios are considered: two where                            As can be observed in Table VI, TDM implementations
the resistance of all active (utilized) devices was fixed to                     consume significantly less power than parallelized implemen-
R¯ON ≈ 10 kΩ, while considering either TDM or parallel use                       tations due to the smaller number of required ADCs. For the
of ADC, and two where the average resistance of all active                       worst case TDM scenario, i.e, when all active devices are
                                                                                                    −
devices was assumed to be (R¯ON +ROFF
                                    ¯ )/2 ≈ 55 kΩ, again for                     programmed to RON     with a constant 0.3V read voltage, our
either TDM or parallelized ADC. These resistance values are                      proposed memristive DL accelerator has a latency of 445.22
representative of two weight distributions: uniform, where all                   µs, and consumes approximately 2.79W and 31.255 mm2 of
weights are zero, and normal, where all weights are centered                     power and area. This is fairly low power consumption for a
around zero. The first distribution was used to report the                       DL accelerator to reside on a separate chip from the neural
maximum possible power consumption of our system, and the                        implant, whereby the implant uses thermal energy to wirelessly
second distribution was used to report the power consumption                     communicate with the accelerator [118], for reduced latency.
of a typical CNN trained using L2-regularization. Considering                       It is noted that we have chosen to optimize the latency
the marginal impact on total power consumption, ( 0.16% and                      of our system at the cost of higher power consumption for
0.06% for TDM and parallelized configurations, respectively),                    multiple reasons. Firstly, analog crossbars which are used to
the power of each individual trained CNN was not determined                      perform IMC operations, in particular VMMs, require periph-
or reported.                                                                     eral circuitry which is power- and area-hungry. Consequently,
  For all scenarios, constant operation at 0.3V per cell [74]                    independent of the latency of the system, when inference is
was assumed. Neither RRAM crossbar tiles nor peripheral cir-                     being performed, a large proportion of the total system’s area
cuitry was assumed to be stacked vertically. Consequently, the                   and power is consumed by peripheral circuitry, registers, and

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                            14


buffers. While TDM ADCs can be used to reduce the total               we demonstrated, through comprehensive simulations, that
power consumption by increasing latency, other peripheral             our memristive DL accelerator is capable of performing real-
circuits, registers, and buffers, are still required for operation.   time operation, and consuming reasonable power in real-world
Counterintuitively, in certain instances, the energy of the           conditions. We also proposed and investigated a new simplified
system can be reduced by minimizing system latency during             stuck weight offsetting method to improve the robustness of
active operation. In other instances, the performance of the          our system to non-idealities. This paper sets a clear path
system can greatly be improved at the cost of increased power         towards the eventual circuit-level realization of a memristive
consumption.                                                          epileptic seizure detection and prediction system.
   Secondly, RRAM devices suffer from conductance drift
induced by read disturbances, which may aggregate, as the
                                                                                              ACKNOWLEDGMENT
analog current is summed up along each Word Line (WL)
during inference [74]. To mitigate this behavior, we have               C. Lammie acknowledges the JCU DRTPS and IBM PhD
constrained the absolute amplitude of BL voltages to 0.3V and         Fellowship Program. M. Rahimi Azghadi acknowledges a JCU
minimized the duration in which a voltage is applied to each          Rising Start ECR Fellowship. R. Genov and A. Amirsoleimani
device, i.e., latency is minimized to avoid read disturbances,        acknowledge the NSERC. In addition, R. Genov acknowledges
and to prolong the lifespan of RRAM devices, at the cost of           the CIHR. We thank the handling editor and reviewers’ for
increased power consumption. Lastly, as RRAM devices are              their constructive feedback. In particular, we acknowledge
non-volatile, gating circuitry can be used to reduce the energy       the second reviewer, who provided advice on simplifying our
consumption of both TDM and parallelized architectures, as            proposed stuck weight mitigation strategy.
both of our architectures have a critical delay path which
is much shorter than typical signal acquisition sampling rate
periods. This also allows for input buffering to be performed,                                     R EFERENCES
so that constant operation is not required.                            [1] E. Beghi, G. Giussani, E. Nichols, F. Abd-Allah, J. Abdela, A. Ab-
                                                                           delalim, H. N. Abraha, M. G. Adib, S. Agrawal, F. Alahdab et al.,
                                                                           “Global, regional, and national burden of epilepsy, 1990–2016: a
G. Comparison to Existing Hardware Implementations                         systematic analysis for the global burden of disease study 2016,” The
                                                                           Lancet Neurology, vol. 18, no. 4, pp. 357–375, 2019.
   In Table VII, we compare the performance of hardware                [2] C. E. Stafstrom and L. Carmant, “Seizures and epilepsy: An overview
implementations of notable epileptic seizure detection and/or              for neuroscientists,” Cold Spring Harbor Perspectives in Medicine,
prediction hardware systems in the literature. As many differ-             vol. 5, no. 6, 2015.
ent evaluation tasks were used, we did not report performance          [3] D. C. Patel, B. P. Tewari, L. Chaunsali, and H. Sontheimer, “Neuron-
                                                                           glia interactions in the pathophysiology of epilepsy,” Nature Reviews
metrics. Hardware implementations are broadly categorized as               Neuroscience, vol. 20, no. 5, pp. 282–297, May 2019.
either ML- or DL-based. As can be observed, both of our                [4] G. P. Brennan and D. C. Henshall, “micrornas in the pathophysiology
implementations (reported for the (R¯ON + ROFF ¯ )/2 scenario              of epilepsy,” Neuroscience Letters, vol. 667, pp. 47–52, 2018, epilepsy:
                                                                           Advances in Genetics and Pathophysiology.
in Table VI) have significantly reduced inference latency, at          [5] S. Gasparini, E. Ferlazzo, C. Sueri, V. Cianci, M. Ascoli, S. M.
the cost of higher power consumption, compared to traditional              Cavalli, E. Beghi, V. Belcastro, A. Bianchi, P. Benna, R. Cantello,
CMOS and FPGA-based implementations. It is worth noting                    D. Consoli, F. A. De Falco, G. Di Gennaro, A. Gambardella, G. L.
                                                                           Gigli, A. Iudice, A. Labate, R. Michelucci, M. Paciaroni, P. Palumbo,
that, most of the previous designs have not reported a com-                A. Primavera, F. Sartucci, P. Striano, F. Villani, E. Russo, G. De Sarro,
plete power consumption analysis, are not capable of seizure               U. Aguglia, and O. behalf of the Epilepsy Study Group of the Italian
prediction, and use fewer channels, which can lead to lower                Neurological Society, “Hypertension, seizures, and epilepsy: a review
                                                                           on pathophysiology and management,” Neurological Sciences, vol. 40,
power consumption and silicon area.                                        no. 9, pp. 1775–1783, Sep. 2019.
   While our proposed system is not currently competitive              [6] M. K. Siddiqui, R. Morales-Menendez, X. Huang, and N. Hussain, “A
in resource-constrained environments, it is intended to be                 review of epileptic seizure detection using machine learning classifiers,”
                                                                           Brain informatics, vol. 7, no. 1, pp. 5–5, May 2020, publisher: Springer
used as a reference design for future works implement-                     Berlin Heidelberg.
ing epileptic seizure detection and prediction systems using           [7] F. E. Ibrahim, H. M. Emara, W. El-Shafai, M. Elwekeil, M. Rihan,
CMOS and memristors. Using analog Static Random-Access                     I. M. Eldokany, T. E. Taha, A. S. El-Fishawy, E.-S. M. El-Rabaie,
                                                                           E. Abdellatef, and F. E. Abd El-Samie, “Deep Learning-based Seizure
Memory (SRAM), vertical stacking of crossbars and CMOS                     Detection and Prediction from EEG Signals,” International journal for
components, and partial sensing approaches, the power and                  numerical methods in biomedical engineering, p. e3573, Jan 2022.
area requirements of our simulated system could be greatly             [8] R. Das, “Special Issue on In-Memory Computing,” IEEE Micro,
                                                                           vol. 42, no. 1, pp. 87–88, 2022.
reduced. We aim to investigate these in our future research.           [9] C. Li, M. Hu, Y. Li, H. Jiang, N. Ge, E. Montgomery, J. Zhang,
                                                                           W. Song, N. Dávila, C. E. Graves, Z. Li, J. P. Strachan, P. Lin, Z. Wang,
                      VII. C ONCLUSION                                     M. Barnell, Q. Wu, R. S. Williams, J. J. Yang, and Q. Xia, “Analogue
                                                                           signal and image processing with large memristor crossbars,” Nature
   We proposed a parallel CNN architecture that can be used                Electronics, vol. 1, no. 1, pp. 52–59, Jan. 2018.
to perform both epileptic seizure detection and prediction            [10] C. Lammie, O. Krestinskaya, A. James, and M. R. Azghadi, “Variation-
                                                                           aware Binarized Memristive Networks,” in 2019 26th IEEE Interna-
rapidly. Compared to other works in literate, our architec-                tional Conference on Electronics, Circuits and Systems (ICECS), 2019,
ture requires significantly fewer parameters, and demonstrates             pp. 490–493.
competitive performance on the University of Bonn, CHB-               [11] C. Lammie, W. Xiang, and M. R. Azghadi, “Towards Memristive Deep
                                                                           Learning Systems for Real-Time Mobile Epileptic Seizure Prediction,”
MIT, and SWEC-ETHZ datasets. Using emerging memristive                     in 2021 IEEE International Symposium on Circuits and Systems
devices and software-hardware optimization methodologies,                  (ISCAS), 2021.

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                         15


[12] S. Xie, R. Girshick, P. Dollár, Z. Tu, and K. He, “Aggregated Residual      [32] S. Liss, “Method and apparatus for monitoring and counteracting
     Transformations for Deep Neural Networks,” in 2017 IEEE Conference                excess brain electrical energy to prevent epileptic seizures and the like,”
     on Computer Vision and Pattern Recognition (CVPR), 2017, pp. 5987–                US3850161A, 1973.
     5995.                                                                        [33] S. Viglione, V. Ordon, W. Martin, and C. Kesler, “Epileptic seizure
[13] S. Zagoruyko and N. Komodakis, “Wide Residual Networks,” CoRR,                    warning system,” US3863625A, 1973.
     vol. abs/1605.07146, 2016. [Online]. Available: http://arxiv.org/abs/        [34] A. Aarabi and B. He, “A rule-based seizure prediction method for
     1605.07146                                                                        focal neocortical epilepsy,” Clinical Neurophysiology, vol. 123, no. 6,
[14] J. Ngiam, A. Khosla, M. Kim, J. Nam, H. Lee, and A. Y. Ng,                        pp. 1111–1122, 2012.
     “Multimodal Deep Learning,” in Proceedings of the 28th International         [35] S. Li, W. Zhou, Q. Yuan, and Y. Liu, “Seizure prediction using spike
     Conference on International Conference on Machine Learning, ser.                  rate of intracranial eeg,” IEEE transactions on neural systems and
     ICML’11. Madison, WI, USA: Omnipress, 2011, p. 689–696.                           rehabilitation engineering, vol. 21, no. 6, pp. 880–886, 2013.
[15] X. Wang, X. Wang, W. Liu, Z. Chang, T. Kärkkäinen, and F. Cong,            [36] A. S. Zandi, R. Tafreshi, M. Javidan, and G. A. Dumont, “Predicting
     “One dimensional convolutional neural networks for seizure onset                  epileptic seizures in scalp eeg based on a variational bayesian gaus-
     detection using long-term scalp and intracranial eeg,” Neurocomputing,            sian mixture model of zero-crossing intervals,” IEEE Transactions on
     vol. 459, pp. 212–222, 2021.                                                      Biomedical Engineering, vol. 60, no. 5, pp. 1401–1413, 2013.
[16] W. Webber, R. P. Lesser, R. T. Richardson, and K. Wilson, “An                [37] M. Bedeeuzzaman, T. Fathima, Y. U. Khan, and O. Farooq, “Seizure
     approach to seizure detection using an artificial neural network (ann),”          prediction using statistical dispersion measures of intracranial eeg,”
     Electroencephalography and clinical Neurophysiology, vol. 98, no. 4,              Biomedical Signal Processing and Control, vol. 10, pp. 338–341, 2014.
     pp. 250–272, 1996.                                                           [38] P. E. McSharry, T. He, L. A. Smith, and L. Tarassenko, “Linear and
[17] N. Pradhan, P. Sadasivan, and G. Arunodaya, “Detection of seizure                 non-linear methods for automatic seizure detection in scalp electro-
     activity in eeg by an artificial neural network: A preliminary study,”            encephalogram recordings,” Medical and Biological Engineering and
     Computers and Biomedical Research, vol. 29, no. 4, pp. 303–313, 1996.             Computing, vol. 40, no. 4, pp. 447–461, 2002.
[18] A. M. Chan, F. T. Sun, E. H. Boto, and B. M. Wingeier, “Automated            [39] B. Schelter, H. Feldwisch-Drentrup, M. Ihle, A. Schulze-Bonhage, and
     seizure onset detection for accurate onset time determination in in-              J. Timmer, “Seizure prediction in epilepsy: From circadian concepts
     tracranial eeg,” Clinical Neurophysiology, vol. 119, no. 12, pp. 2687–            via probabilistic forecasting to statistical evaluation,” in 2011 Annual
     2696, 2008.                                                                       International Conference of the IEEE Engineering in Medicine and
[19] T. Netoff, Y. Park, and K. Parhi, “Seizure prediction using cost-sensitive        Biology Society. IEEE, 2011, pp. 1624–1627.
     support vector machine,” in 2009 Annual International Conference of          [40] S. Wang, W. A. Chaovalitwongse, and S. Wong, “A novel reinforcement
     the IEEE Engineering in Medicine and Biology Society. IEEE, 2009,                 learning framework for online adaptive seizure prediction,” in 2010
     pp. 3322–3325.                                                                    IEEE International Conference on Bioinformatics and Biomedicine
[20] K. Chua, V. Chandran, U. R. Acharya, and C. Lim, “Automatic                       (BIBM). IEEE, 2010, pp. 499–504.
     identification of epileptic electroencephalography signals using higher-
                                                                                  [41] H. Daoud and M. A. Bayoumi, “Efficient epileptic seizure prediction
     order spectra,” Proceedings of the Institution of Mechanical Engineers,
                                                                                       based on deep learning,” IEEE transactions on biomedical circuits and
     Part H: Journal of Engineering in Medicine, vol. 223, no. 4, pp. 485–
                                                                                       systems, vol. 13, no. 5, pp. 804–813, 2019.
     495, 2009.
                                                                                  [42] R. Jana and I. Mukherjee, “Deep learning based efficient epileptic
[21] T. L. Sorensen, U. L. Olsen, I. Conradsen, J. Henriksen, T. W. Kjaer,
                                                                                       seizure prediction with eeg channel optimization,” Biomedical Signal
     C. E. Thomsen, and H. B. Sorensen, “Automatic epileptic seizure
                                                                                       Processing and Control, vol. 68, p. 102767, 2021.
     onset detection using matching pursuit: a case study,” in 2010 Annual
                                                                                  [43] T. Dissanayake, T. Fernando, S. Denman, S. Sridharan, and C. Fookes,
     International Conference of the IEEE Engineering in Medicine and
                                                                                       “Patient-independent epileptic seizure prediction using deep learning
     Biology. IEEE, 2010, pp. 3277–3280.
                                                                                       models,” arXiv preprint arXiv:2011.09581, 2020.
[22] L. Chisci, A. Mavino, G. Perferi, M. Sciandrone, C. Anile, G. Colic-
     chio, and F. Fuggetta, “Real-time epileptic seizure prediction using ar      [44] T. N. Alotaiby, S. A. Alshebeili, T. Alshawi, I. Ahmad, and F. E. Abd
     models and support vector machines,” IEEE Transactions on Biomed-                 El-Samie, “Eeg seizure detection and prediction algorithms: a survey,”
     ical Engineering, vol. 57, no. 5, pp. 1124–1132, 2010.                            EURASIP Journal on Advances in Signal Processing, vol. 2014, no. 1,
[23] E. B. Petersen, J. Duun-Henriksen, A. Mazzaretto, T. W. Kjær, C. E.               p. 183, Dec. 2014.
     Thomsen, and H. B. Sorensen, “Generic single-channel detection of            [45] M. R. Azghadi, C. Lammie, J. K. Eshraghian, M. Payvand, E. Donati,
     absence seizures,” in 2011 Annual International Conference of the                 B. Linares-Barranco, and G. Indiveri, “Hardware implementation of
     IEEE Engineering in Medicine and Biology Society. IEEE, 2011,                     deep network accelerators towards healthcare and biomedical applica-
     pp. 4820–4823.                                                                    tions,” IEEE Transactions on Biomedical Circuits and Systems, vol. 14,
[24] A. Temko, E. Thomas, W. Marnane, G. Lightbody, and G. Boylan,                     no. 6, pp. 1138–1159, 2020.
     “Eeg-based neonatal seizure detection with support vector machines,”         [46] H. Kassiri, S. Tonekaboni, M. T. Salam, N. Soltani, K. Abdelhalim,
     Clinical Neurophysiology, vol. 122, no. 3, pp. 464–473, 2011.                     J. L. P. Velazquez, and R. Genov, “Closed-loop neurostimulators: A
[25] U. R. Acharya, S. V. Sree, and J. S. Suri, “Automatic detection of                survey and a seizure-predicting design example for intractable epilepsy
     epileptic eeg signals using higher order cumulant features,” Interna-             treatment,” IEEE transactions on biomedical circuits and systems,
     tional journal of neural systems, vol. 21, no. 05, pp. 403–414, 2011.             vol. 11, no. 5, pp. 1026–1040, 2017.
[26] A. Kharbouch, A. Shoeb, J. Guttag, and S. S. Cash, “An algorithm for         [47] D. Kudithipudi, Q. Saleh, C. Merkel, J. Thesing, and B. Wysocki,
     seizure onset detection using intracranial eeg,” Epilepsy & Behavior,             “Design and analysis of a neuromemristive reservoir computing archi-
     vol. 22, pp. S29–S35, 2011.                                                       tecture for biosignal processing,” Frontiers in Neuroscience, vol. 9, p.
[27] Y. Liu, W. Zhou, Q. Yuan, and S. Chen, “Automatic seizure detection               502, 2016.
     using wavelet transform and svm in long-term intracranial eeg,” IEEE         [48] C. Merkel, Q. Saleh, C. Donahue, and D. Kudithipudi, “Memristive
     transactions on neural systems and rehabilitation engineering, vol. 20,           reservoir computing architecture for epileptic seizure detection,” Pro-
     no. 6, pp. 749–755, 2012.                                                         cedia Computer Science, vol. 41, pp. 249 – 254, 2014, 5th Annual
[28] I. Ullah, M. Hussain, E. ul Haq Qazi, and H. Aboalsamh, “An                       International Conference on Biologically Inspired Cognitive Architec-
     automated system for epilepsy detection using eeg brain signals based             tures, 2014 BICA.
     on deep learning approach,” Expert Systems with Applications, vol.           [49] R.-E. Karamani, I.-A. Fyrigos, V. Ntinas, I. Vourkas, G. C. Sirakoulis,
     107, pp. 61 – 71, 2018.                                                           and A. Rubio, “Memristive cellular automata for modeling of epileptic
[29] W. Zhao, W. Zhao, W. Wang, X. Jiang, X. Zhang, Y. Peng, B. Zhang,                 brain activity,” in 2018 IEEE International Symposium on Circuits and
     and G. Zhang, “A Novel Deep Neural Network for Robust Detection                   Systems (ISCAS). IEEE, 2018, pp. 1–5.
     of Seizures Using EEG Signals,” Computational and Mathematical               [50] Z. Liu, J. Tang, B. Gao, P. Yao, X. Li, D. Liu, Y. Zhou, H. Qian,
     Methods in Medicine, vol. 2020, p. 9689821, Apr. 2020, publisher:                 B. Hong, and H. Wu, “Neural signal analysis with memristor arrays
     Hindawi.                                                                          towards high-efficiency brain–machine interfaces,” Nature communica-
[30] R. Abiyev, M. Arslan, J. Bush Idoko, B. Sekeroglu, and A. Ilhan,                  tions, vol. 11, no. 1, pp. 1–9, 2020.
     “Identification of epileptic eeg signals using convolutional neural          [51] S. M. Usman, M. Usman, and S. Fong, “Epileptic seizures prediction
     networks,” Applied Sciences, vol. 10, no. 12, 2020.                               using machine learning methods,” Computational and mathematical
[31] P. Boonyakitanont, A. Lek-uthai, K. Chomtho, and J. Songsiri, “A                  methods in medicine, vol. 2017, 2017.
     comparison of deep neural networks for seizure detection in eeg              [52] K. Fujiwara, M. Miyajima, T. Yamakawa, E. Abe, Y. Suzuki,
     signals,” bioRxiv, 2019.                                                          Y. Sawada, M. Kano, T. Maehara, K. Ohta, T. Sasai-Sakuma et al.,

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                       16


     “Epileptic seizure prediction based on multivariate statistical pro-               tional Workshop on Frontiers in Handwriting Recognition, G. Lorette,
     cess control of heart rate variability features,” IEEE Transactions on             Ed., Université de Rennes 1. La Baule (France): Suvisoft, Oct. 2006.
     Biomedical Engineering, vol. 63, no. 6, pp. 1321–1332, 2015.                  [70] O. Krestinskaya, A. Irmanova, and A. P. James, “Memristive non-
[53] M. Zanghieri, A. Burrello, S. Benatti, K. Schindler, and L. Benini,                idealities: Is there any practical implications for designing neural
     “Low-latency detection of epileptic seizures from ieeg with temporal               network chips?” in 2019 IEEE International Symposium on Circuits
     convolutional networks on a low-power parallel mcu,” in 2021 IEEE                  and Systems (ISCAS), 2019, pp. 1–5.
     Sensors Applications Symposium (SAS). IEEE, 2021, pp. 1–6.                    [71] C. Lammie, W. Xiang, B. Linares-Barranco, and M. Rahimi
[54] C. N. Heck, D. King-Stephens, A. D. Massey, D. R. Nair, B. C. Jobst,               Azghadi, “MemTorch: An Open-source Simulation Framework for
     G. L. Barkley, V. Salanova, A. J. Cole, M. C. Smith, R. P. Gwinn                   Memristive Deep Learning Systems,” Neurocomputing, vol. 485, pp.
     et al., “Two-year seizure reduction in adults with medically intractable           124–133, 2022. [Online]. Available: https://www.sciencedirect.com/
     partial onset epilepsy treated with responsive neurostimulation: final             science/article/pii/S0925231222002053
     results of the rns system pivotal trial,” Epilepsia, vol. 55, no. 3, pp.      [72] A. Chen, “A comprehensive crossbar array model with solutions for line
     432–441, 2014.                                                                     resistance and nonlinear device characteristics,” IEEE Transactions on
[55] M. Nasseri, T. Pal Attia, B. Joseph, N. M. Gregg, E. S. Nurse, P. F.               Electron Devices, vol. 60, no. 4, pp. 1318–1326, 2013.
     Viana, G. Worrell, M. Dümpelmann, M. P. Richardson, D. R. Freestone          [73] J. Cheng, L. Liang, J. H. Park, H. Yan, and K. Li, “A Dynamic
     et al., “Ambulatory seizure forecasting with a wrist-worn device using             Event-Triggered Approach to State Estimation for Switched Memristive
     long-short term memory deep learning,” Scientific reports, vol. 11,                Neural Networks With Nonhomogeneous Sojourn Probabilities,” IEEE
     no. 1, pp. 1–9, 2021.                                                              Transactions on Circuits and Systems I: Regular Papers, vol. 68, no. 12,
[56] Y. Yang, M. Zhou, Y. Niu, C. Li, R. Cao, B. Wang, P. Yan, Y. Ma, and               pp. 4924–4934, 2021.
     J. Xiang, “Epileptic seizure prediction based on permutation entropy,”        [74] W. Shim, Y. Luo, J.-s. Seo, and S. Yu, “Impact of Read Disturb on
     Frontiers in computational neuroscience, vol. 12, p. 55, 2018.                     Multilevel RRAM based Inference Engine: Experiments and Model
[57] M. Pinto, A. Leal, F. Lopes, A. Dourado, P. Martins, C. A. Teixeira                Prediction,” in 2020 IEEE International Reliability Physics Symposium
     et al., “A personalized and evolutionary algorithm for interpretable eeg           (IRPS), 2020, pp. 1–5.
     epilepsy seizure prediction,” Scientific reports, vol. 11, no. 1, pp. 1–12,   [75] S. Kannan, N. Karimi, R. Karri, and O. Sinanoglu, “Detection, diagno-
     2021.                                                                              sis, and repair of faults in memristor-based memories,” in 2014 IEEE
[58] R. E. Stirling, D. B. Grayden, W. D’Souza, M. J. Cook, E. Nurse, D. R.             32nd VLSI Test Symposium (VTS). IEEE, 2014, pp. 1–6.
     Freestone, D. E. Payne, B. H. Brinkmann, T. Pal Attia, P. F. Viana et al.,    [76] C. Liu, M. Hu, J. P. Strachan, and H. Li, “Rescuing memristor-
     “Forecasting seizure likelihood with wearable technology,” Frontiers in            based neuromorphic design with high defects,” in 2017 54th
     neurology, p. 1170, 2021.                                                          ACM/EDAC/IEEE Design Automation Conference (DAC). IEEE, 2017,
[59] P. Peng, Y. Song, and L. Yang, “Seizure prediction in eeg signals using            pp. 1–6.
     stft and domain adaptation,” Frontiers in Neuroscience, p. 1880, 2021.        [77] L. Xia, W. Huangfu, T. Tang, X. Yin, K. Chakrabarty, Y. Xie, Y. Wang,
                                                                                        and H. Yang, “Stuck-at fault tolerance in rram computing systems,”
[60] J. Cong and B. Xiao, “Minimizing computation in convolutional
                                                                                        IEEE Journal on Emerging and Selected Topics in Circuits and
     neural networks,” in Artificial Neural Networks and Machine Learn-
                                                                                        Systems, vol. 8, no. 1, pp. 102–115, 2017.
     ing – ICANN 2014, S. Wermter, C. Weber, W. Duch, T. Honkela,
                                                                                   [78] B. Zhang, N. Uysal, D. Fan, and R. Ewetz, “Handling stuck-at-
     P. Koprinkova-Hristova, S. Magg, G. Palm, and A. E. P. Villa, Eds.
                                                                                        faults in memristor crossbar arrays using matrix transformations,” in
     Cham: Springer International Publishing, 2014, pp. 281–290.
                                                                                        Proceedings of the 24th Asia and South Pacific Design Automation
[61] A. Amirsoleimani, F. Alibart, V. Yon, J. Xu, M. R. Pazhouhan-
                                                                                        Conference, 2019, pp. 438–443.
     deh, S. Ecoffey, Y. Beilliard, R. Genov, and D. Drouin, “In-
                                                                                   [79] I. Yeo, M. Chu, S.-G. Gi, H. Hwang, and B.-G. Lee, “Stuck-at-fault
     memory vector-matrix multiplication in monolithic complemen-
                                                                                        tolerant schemes for memristor crossbar array-based neural networks,”
     tary metal–oxide–semiconductor-memristor integrated circuits: Design
                                                                                        IEEE Transactions on Electron Devices, vol. 66, no. 7, pp. 2937–2945,
     choices, challenges, and perspectives,” Advanced Intelligent Systems,
                                                                                        2019.
     vol. 2, no. 11, p. 2000115, 2020.
                                                                                   [80] T. Wen and Z. Zhang, “Deep convolution neural network and
[62] H. Kim, M. R. Mahmoodi, H. Nili, and D. B. Strukov, “4k-memristor                  autoencoders-based unsupervised feature learning of eeg signals,” IEEE
     analog-grade passive crossbar circuit,” Nature Communications,                     Access, vol. 6, pp. 25 399–25 410, 2018.
     vol. 12, no. 1, p. 5198, Aug. 2021. [Online]. Available: https:               [81] M. S. Hossain, S. U. Amin, M. Alsulaiman, and G. Muhammad,
     //doi.org/10.1038/s41467-021-25455-0                                               “Applying deep learning for epilepsy seizure detection and brain
[63] R. G. Andrzejak, K. Lehnertz, F. Mormann, C. Rieke, P. David,                      mapping visualization,” ACM Transactions on Multimedia Computing,
     and C. E. Elger, “Indications of nonlinear deterministic and finite-               Communications, and Applications (TOMM), vol. 15, no. 1s, pp. 1–17,
     dimensional structures in time series of brain electrical activity: de-            2019.
     pendence on recording region and brain state.” Physical review. E,            [82] J. Cao, J. Zhu, W. Hu, and A. Kummert, “Epileptic signal classification
     Statistical, nonlinear, and soft matter physics, vol. 64, p. 061907, Dec           with deep eeg features by stacked cnns,” IEEE Transactions on
     2001.                                                                              Cognitive and Developmental Systems, vol. 12, no. 4, pp. 709–722,
[64] A. L. Goldberger, L. A. N. Amaral, L. Glass, J. M. Hausdorff, P. C.                2019.
     Ivanov, R. G. Mark, J. E. Mietus, G. B. Moody, C.-K. Peng, and H. E.          [83] X. Tian, Z. Deng, W. Ying, K.-S. Choi, D. Wu, B. Qin, J. Wang,
     Stanley, “Physiobank, physiotoolkit, and physionet,” Circulation, vol.             H. Shen, and S. Wang, “Deep multi-view feature learning for eeg-based
     101, no. 23, pp. e215–e220, Aug. 2021.                                             epileptic seizure detection,” IEEE Transactions on Neural Systems and
[65] A. Burrello, L. Cavigelli, K. Schindler, L. Benini, and A. Rahimi,                 Rehabilitation Engineering, vol. 27, no. 10, pp. 1962–1972, 2019.
     “Laelaps: An energy-efficient seizure detection algorithm from long-          [84] W. Liang, H. Pei, Q. Cai, and Y. Wang, “Scalp eeg epileptogenic zone
     term human ieeg recordings without false alarms,” in 2019 Design,                  recognition and localization based on long-term recurrent convolutional
     Automation Test in Europe Conference Exhibition (DATE), 2019, pp.                  network,” Neurocomputing, vol. 396, pp. 569–576, 2020.
     752–757.                                                                      [85] A. Burrello, S. Benatti, K. Schindler, L. Benini, and A. Rahimi, “An
[66] N. D. Truong, A. D. Nguyen, L. Kuhlmann, M. R. Bonyadi, J. Yang,                   ensemble of hyperdimensional classifiers: Hardware-friendly short-
     S. Ippolito, and O. Kavehei, “Convolutional neural networks for                    latency seizure detection with automatic ieeg electrode selection,” IEEE
     seizure prediction using intracranial and scalp electroencephalogram,”             journal of biomedical and health informatics, vol. 25, no. 4, pp. 935–
     Neural Networks, vol. 105, pp. 104–111, Sep. 2018.                                 946, 2020.
[67] A. Sebastian, M. Le Gallo, R. Khaddam-Aljameh, and E. Eleftheriou,            [86] A. Pappalardo, “Xilinx/brevitas,” 2021.
     “Memory devices and applications for in-memory computing,” Nature             [87] A. Abdelhameed and M. Bayoumi, “A deep learning approach for
     Nanotechnology, vol. 15, no. 7, pp. 529–544, Jul. 2020. [Online].                  automatic seizure detection in children with epilepsy,” Frontiers in
     Available: https://doi.org/10.1038/s41565-020-0655-z                               Computational Neuroscience, vol. 15, p. 29, 2021.
[68] M. Rahimi Azghadi, Y.-C. Chen, J. K. Eshraghian, J. Chen, C.-Y.               [88] J. Yoo, L. Yan, D. El-Damak, M. A. B. Altaf, A. H. Shoeb, and A. P.
     Lin, A. Amirsoleimani, A. Mehonic, A. J. Kenyon, B. Fowler, J. C.                  Chandrakasan, “An 8-channel scalable eeg acquisition soc with patient-
     Lee, and Y.-F. Chang, “Complementary metal-oxide semiconductor                     specific seizure classification and recording processor,” IEEE Journal
     and memristive hardware for neuromorphic computing,” Advanced                      of Solid-State Circuits, vol. 48, no. 1, pp. 214–228, 2013.
     Intelligent Systems, vol. 2, no. 5, p. 1900189, 2020.                         [89] M. A. B. Altaf, J. Tillak, Y. Kifle, and J. Yoo, “A
[69] K. Chellapilla, S. Puri, and P. Simard, “High Performance Convolu-                 1.83/microj/classification nonlinear support-vector-machine-based
     tional Neural Networks for Document Processing,” in Tenth Interna-                 patient-specific seizure classification soc,” in 2013 IEEE International

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                        17


      Solid-State Circuits Conference Digest of Technical Papers, 2013, pp.        [108] M. Giordano, G. Cristiano, K. Ishibashi, S. Ambrogio, H. Tsai, G. W.
      100–101.                                                                           Burr, and P. Narayanan, “Analog-to-digital conversion with recon-
 [90] K. H. Lee and N. Verma, “A low-power processor with configurable                   figurable function mapping for neural networks activation function
      embedded machine-learning accelerators for high-order and adaptive                 acceleration,” IEEE Journal on Emerging and Selected Topics in
      analysis of medical-sensor signals,” IEEE Journal of Solid-State Cir-              Circuits and Systems, vol. 9, no. 2, pp. 367–376, 2019.
      cuits, vol. 48, no. 7, pp. 1625–1637, 2013.                                  [109] Z. Li, A. Ren, J. Li, Q. Qiu, Y. Wang, and B. Yuan, “Dscnn: Hardware-
 [91] W.-M. Chen, H. Chiueh, T.-J. Chen, C.-L. Ho, C. Jeng, M.-D. Ker, C.-               oriented optimization for stochastic computing based deep convolu-
      Y. Lin, Y.-C. Huang, C.-W. Chou, T.-Y. Fan, M.-S. Cheng, Y.-L. Hsin,               tional neural networks,” in 2016 IEEE 34th International Conference
      S.-F. Liang, Y.-L. Wang, F.-Z. Shaw, Y.-H. Huang, C.-H. Yang, and                  on Computer Design (ICCD), 2016, pp. 678–681.
      C.-Y. Wu, “A fully integrated 8-channel closed-loop neural-prosthetic        [110] P.-E. Gaillardon, M. H. Ben-Jamaa, F. Clermidy, and I. O’Connor,
      cmos soc for real-time epileptic seizure control,” IEEE Journal of Solid-          “Evaluation of a crossbar multiplexer in a lithography-based nanowire
      State Circuits, vol. 49, no. 1, pp. 232–247, 2014.                                 technology,” in 2011 IEEE International Symposium of Circuits and
 [92] M. A. Bin Altaf, C. Zhang, and J. Yoo, “A 16-channel patient-specific              Systems (ISCAS), 2011, pp. 2930–2933.
      seizure onset and termination detection soc with impedance-adaptive          [111] A. Shafiee, A. Nag, N. Muralimanohar, R. Balasubramonian, J. P.
      transcranial electrical stimulator,” IEEE Journal of Solid-State Circuits,         Strachan, M. Hu, R. S. Williams, and V. Srikumar, “Isaac: A con-
      vol. 50, no. 11, pp. 2728–2740, 2015.                                              volutional neural network accelerator with in-situ analog arithmetic in
 [93] M. A. Bin Altaf and J. Yoo, “A 1.83µj/classification, 8-channel,                   crossbars,” in 2016 ACM/IEEE 43rd Annual International Symposium
      patient-specific epileptic seizure classification soc using a non-linear           on Computer Architecture (ISCA), 2016, pp. 14–26.
      support vector machine,” IEEE Transactions on Biomedical Circuits            [112] K. Govindarajan and V. S. K. Bhaaskaran, “Borrow Select Subtractor
      and Systems, vol. 10, no. 1, pp. 49–60, 2016.                                      for Low Power and Area Efficiency,” in 2020 IEEE Computer Society
 [94] G. O’Leary, M. R. Pazhouhandeh, M. Chang, D. Groppe, T. A.                         Annual Symposium on VLSI (ISVLSI), 2020, pp. 518–523.
      Valiante, N. Verma, and R. Genov, “A recursive-memory          brain-state   [113] S. Ganesan et al., “Area, delay and power comparison of adder
      classifier with 32-channel track-and-zoom ∆2
                                                         P
                                                           ADCs and Charge-              topologies,” Ph.D. dissertation, 2015.
      Balanced Programmable Waveform Neurostimulators,” in 2018 IEEE               [114] S. Sarangi and B. Baas, “Deepscaletool: A tool for the accurate
      International Solid State Circuits Conference (ISSCC), 2018, pp. 296–              estimation of technology scaling in the deep-submicron era,” in 2021
      298.                                                                               IEEE International Symposium on Circuits and Systems (ISCAS), 2021.
 [95] Y. Wang, Q. Sun, H. Luo, X. Chen, X. Wang, and H. Zhang,                     [115] R. Balasubramonian, A. B. Kahng, N. Muralimanohar, A. Shafiee,
      “26.3 a closed-loop neuromodulation chipset with 2-level classification            and V. Srinivas, “Cacti 7: New tools for interconnect exploration
      achieving 1.5vpp cm interference tolerance, 35db stimulation artifact              in innovative off-chip memories,” ACM Trans. Archit. Code Optim.,
      rejection in 0.5ms and 97.8% sensitivity seizure detection,” in 2020               vol. 14, no. 2, jun 2017.
      IEEE International Solid-State Circuits Conference (ISSCC), 2020, pp.        [116] A. Dozortsev, I. Goldshtein, and S. Kvatinsky, “Analysis of the
      406–408.                                                                           row grounding technique in a memristor-based crossbar array,”
 [96] S.-A. Huang, K.-C. Chang, H.-H. Liou, and C.-H. Yang, “A 1.9mw svm                 International Journal of Circuit Theory and Applications, vol. 46,
      processor with on-chip active learning for epileptic seizure control,”             no. 1, pp. 122–137, 2018. [Online]. Available: https://onlinelibrary.
      IEEE Journal of Solid-State Circuits, vol. 55, no. 2, pp. 452–464, 2020.           wiley.com/doi/abs/10.1002/cta.2399
                                                                                   [117] C. Xu, X. Dong, N. P. Jouppi, and Y. Xie, “Design implications of
 [97] A. Uran, K. Ture, C. Aprile, A. Trouillet, F. Fallegger, A. Emami,
                                                                                         memristor-based rram cross-point structures,” in 2011 Design, Automa-
      S. P. Lacour, C. Dehollain, Y. Leblebici, and V. Cevher, “A 16-channel
      wireless neural recording system-on-chip with cht feature extraction               tion Test in Europe, 2011.
                                                                                   [118] M. ElAnsary, J. Xu, J. Sales Filho, G. Dutta, L. Long, C. Tejeiro,
      processor in 65nm cmos,” in 2021 IEEE Custom Integrated Circuits
      Conference (CICC), 2021, pp. 1–2.                                                  A. Shoukry, C. Tang, E. Kilinc, J. Joshi et al., “Bidirectional periph-
                                                                                         eral nerve interface with 64 second-order opamp-less adcs and fully
 [98] S.-K. Lin, Istiqomah, L.-C. Wang, C.-Y. Lin, and H. Chiueh, “An ultra-
                                                                                         integrated wireless power/data transmission,” IEEE Journal of Solid-
      low power smart headband for real-time epileptic seizure detection,”
                                                                                         State Circuits, vol. 56, no. 11, pp. 3247–3262, 2021.
      IEEE Journal of Translational Engineering in Health and Medicine,
      vol. 6, pp. 1–10, 2018.
 [99] C.-H. Yang, Y.-H. Shih, and H. Chiueh, “An 81.6 µW FastICA
      Processor for Epileptic Seizure Detection,” IEEE Transactions on                                      Chenqi Li is currently pursuing a B.A.Sc in Engi-
      Biomedical Circuits and Systems, vol. 9, no. 1, pp. 60–71, 2015.                                      neering Science, Robotics at University of Toronto,
[100] C. Chen, H. Ding, H. Peng, H. Zhu, Y. Wang, and C.-J. R. Shi, “Ocean:                                 Canada. His current research interests include ma-
      An on-chip incremental-learning enhanced artificial neural network                                    chine learning, computer vision, and brain-inspired
      processor with multiple gated-recurrent-unit accelerators,” IEEE Jour-                                computing.
      nal on Emerging and Selected Topics in Circuits and Systems, vol. 8,
      no. 3, pp. 519–530, 2018.
[101] H. G. Daoud, A. M. Abdelhameed, and M. Bayoumi, “Fpga implemen-
      tation of high accuracy automatic epileptic seizure detection system,”
      in 2018 IEEE 61st International Midwest Symposium on Circuits and
      Systems (MWSCAS), 2018, pp. 407–410.
[102] M. Ronchini, M. Zamani, H. A. Huynh, Y. Rezaeiyan, G. Panuccio,
      H. Farkhani, and F. Moradi, “A CMOS-based neuromorphic device for
      seizure detection from LFP signals,” Journal of Physics D: Applied                                     Corey Lammie (S’17) is currently pursuing a PhD
      Physics, vol. 55, no. 1, p. 014001, oct 2021.                                                          in Computer Engineering at James Cook Univer-
                                                                                                             sity (JCU), where he completed his undergraduate
[103] S. Lv, J. Liu, and Z. Geng, “Application of memristors in hardware
                                                                                                             degrees in Electrical Engineering (Honours) and
      security: A current state-of-the-art technology,” Advanced Intelligent
                                                                                                             Information Technology in 2018. His main research
      Systems, vol. 3, no. 1, p. 2000127, 2021.
                                                                                                             interests include brain-inspired computing, and the
[104] S. Yu, H. Jiang, S. Huang, X. Peng, and A. Lu, “Compute-in-memory
                                                                                                             simulation and hardware implementation of Spiking
      chips for deep learning: Recent trends and prospects,” IEEE Circuits
                                                                                                             Neural Networks (SNNs) and Artificial Neural Net-
      and Systems Magazine, vol. 21, no. 3, pp. 31–56, 2021.
                                                                                                             works (ANNs) using RRAM devices and FPGAs.
[105] M. A. Zidan, Y. Jeong, J. Lee, B. Chen, S. Huang, M. J. Kushner,                                       He has received several awards and fellowships
      and W. D. Lu, “A general memristor-based partial differential equation                                 including the intensely competitive 2020-2021 IBM
      solver,” Nature Electronics, vol. 1, no. 7, pp. 411–420, Jul. 2018.          international PhD Fellowship, a Domestic Prestige Research Training Program
[106] M. Yoshioka, M. Kudo, K. Gotoh, and Y. Watanabe, “A 10 b 125                 Scholarship (the highest paid PhD scholarship in Australia), the 2020 Circuits
      MS/s 40 mW pipelined ADC in 0.18 /spl mu/m CMOS,” in 2005                    and Systems (CAS) Society Pre-Doctoral Grant, and the 2017 Engineers
      IEEE International Digest of Technical Papers. Solid-State Circuits          Australia CN Barton Medal awarded to the best undergraduate engineering
      Conference, 2005, pp. 282–598 Vol. 1.                                        thesis at JCU. Corey has served as a reviewer for several IEEE journals and
[107] J. Jung, K.-H. Baek, S.-I. Lim, S. Kim, and S.-M. Kang, “Design of a         conferences including IEEE Transactions on Circuits and Systems I and II,
      6 bit 1.25 gs/s dac for wpan,” in 2008 IEEE International Symposium          and the IEEE International Symposium on Circuits and Systems (ISCAS).
      on Circuits and Systems, 2008, pp. 2262–2265.

ACCEPTED BY IEEE TRANSACTIONS ON BIOMEDICAL CIRCUITS AND SYSTEMS, 2022                                                                                         18


                          Xuening Dong is currently pursuing a B.A.Sc in                                      Roman Genov (S’96–M’02–SM’11) received the
                          Computer Engineering at University of Toronto,                                      B.S. degree in Electrical Engineering from Rochester
                          Canada. Her current research interests include ma-                                  Institute of Technology, NY in 1996 and the M.S.E.
                          chine learning, stochastic processes, and the design                                and Ph.D. degrees in Electrical and Computer Engi-
                          and simulation of memristor-based applications.                                     neering from Johns Hopkins University, Baltimore,
                                                                                                              MD in 1998 and 2003 respectively.
                                                                                                                He is currently a Professor in the Department of
                                                                                                              Electrical and Computer Engineering at the Uni-
                                                                                                              versity of Toronto, Canada, where he is a member
                                                                                                              of Electronics Group and Biomedical Engineering
                                                                                                              Group and the Director of Intelligent Sensory Mi-
                                                                                   crosystems Laboratory. Dr. Genov’s research interests are primarily in analog
                                                                                   integrated circuits and systems for energy-constrained biological, medical, and
                          Amirali Amirsoleimani (S’09–M’2017) is an as-            consumer sensory applications.
                          sistant professor in the Department of Electrical           Dr. Genov is a co-recipient of Jack Kilby Award for Outstanding Student
                          Engineering and Computer Science at the Lassonde         Paper at IEEE International Solid-State Circuits Conference, Best Paper Award
                          School of Engineering. He received his PhD in elec-      of IEEE Transactions on Biomedical Circuits and Systems, Best Paper Award
                          trical and computer engineering (ECE) from Univer-       of IEEE Biomedical Circuits and Systems Conference, Best Student Paper
                          sity of Windsor in December 2017 and completed           Award of IEEE International Symposium on Circuits and Systems, Best Paper
                          his postdoctoral research fellowship at the Edward S.    Award of IEEE Circuits and Systems Society Sensory Systems Technical
                          Rogers Sr. Electrical and Computer Engineering De-       Committee, Brian L. Barge Award for Excellence in Microsystems Integration,
                          partment at the University of Toronto in July 2021.      MEMSCAP Microsystems Design Award, DALSA Corporation Award for
                          His current research interests include application-      Excellence in Microsystems Innovation, and Canadian Institutes of Health
                          specific processing units, in-memory computing,          Research Next Generation Award. He was a Technical Program Co-chair
neuromorphic hardware design and RRAM-based accelerators for artificial            at IEEE Biomedical Circuits and Systems Conference, a member of IEEE
intelligence. He received IEEE Larry K. Wilson award for IEEE region 7             European Solid-State Circuits Conference Technical Program Committee, and
in 2016. He was also the recipient of a best poster honourable mention             a member of IEEE International Solid-State Circuits Conference International
award at International Joint Conference on Neural Network (IJCNN) 2017 in          Program Committee. He was also an Associate Editor of IEEE TCAS II and
Alaska, USA. He is a guest editor in Frontiers in Electronics and Frontiers in     IEEE Signal Processing Letters, as well as a Guest Editor for IEEE JSSC.
Nanotechnology journals and is also serving as a reviewer for several electrical   Currently he is an Associate Editor of IEEE Transactions on Biomedical
and computer engineering journals including IEEE Transactions on Circuits          Circuits and Systems.
and Systems I (TCASI), TCAS II, TNANO, TVLSI, TED, Frontiers in Neuro-
Science, Microelectronics journal, Neural Computing and Applications.


                         Mostafa Rahimi Azghadi (S’07–M’14–SM’19)
                         completed his PhD in Electrical & Electronic En-
                         gineering at The University of Adelaide, Australia,
                         earning the Doctoral Research Medal, as well as the
                         Adelaide University Alumni Medal. He is currently
                         a senior lecturer in the College of Science and
                         Engineering, James Cook University, Townsville,
                         Australia, where he researches low-power and high-
                         performance neuromorphic accelerators for neural
                         inspired and deep learning networks for a variety of
                         applications from agriculture to medicine. He has co-
raised over $6M in research funding from national and international resources.
   Dr. Rahimi was a recipient of several national and international accolades
including a 2015 South Australia Science Excellence award, a 2016 Endeavour
Research Fellowship, a 2017 Queensland Young Tall Poppy Science Award,
a 2018 JCU Rising Star ECR Leader Fellowship, a 2019 Fresh Science
Queensland Finalist, and a 2020 JCU Award for Excellence in Innovation
and Change. Dr Rahimi is a senior member of the IEEE and a TC member of
Neural Systems and Applications of the circuit and system society. He serves
as an associate editor of Frontiers in Neuromorphic Engineering and IEEE
Access.
```
