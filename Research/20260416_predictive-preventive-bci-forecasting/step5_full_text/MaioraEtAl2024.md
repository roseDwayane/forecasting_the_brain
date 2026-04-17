---
citation_key: "MaioraEtAl2024"
paper_id: "paper_263"
title: "Older Adult Fall Risk Prediction with Deep Learning and Timed Up and Go (TUG) Test Data."
authors: "Josu Maiora; Chloe Rezola-Pardo; Guillermo García; Begoña Sanz; Manuel Graña"
year: 2024
doi: "10.3390/bioengineering11101000"
source: "publisher-pdf (doi: 10.3390/bioengineering11101000)"
access_level: "full-text-pdf"
retrieved_date: "2026-04-16"
tier: 1
composite: 4.5
---

# Older Adult Fall Risk Prediction with Deep Learning and Timed Up and Go (TUG) Test Data.

**Citation:** `MaioraEtAl2024` · **Tier:** 1 · **Composite:** 4.5
**DOI:** [10.3390/bioengineering11101000](https://doi.org/10.3390/bioengineering11101000)
**Source PDF:** `full_pdf/Maiora2024.pdf`

## Abstract

Falls are a major health hazard for older adults; therefore, in the context of an aging population, predicting the risk of a patient suffering falls in the near future is of great impact for health care systems. Currently, the standard prospective fall risk assessment instrument relies on a set of clinical and functional mobility assessment tools, one of them being the Timed Up and Go (TUG) test. Recently, wearable inertial measurement units (IMUs) have been proposed to capture motion data that would allow for the building of estimates of fall risk. The hypothesis of this study is that the data gathered from IMU readings while the patient is performing the TUG test can be used to build a predictive model that would provide an estimate of the probability of suffering a fall in the near future, i.e., assessing prospective fall risk. This study applies deep learning convolutional neural networks (CNN) and recurrent neural networks (RNN) to build such predictive models based on features extracted from IMU data acquired during TUG test realizations. Data were obtained Citation: Maiora, J.; Rezola-Pardo, C.; from a cohort of 106 older adults wearing wireless IMU sensors with sampling frequencies of 100 Hz García, G.; Sanz, B.; Graña, M. Older while performing the TUG test. The dependent variable is a binary variable that is true if the patient Adult Fall Risk Prediction with Deep suffered a fall in the six-month follow-up period. This variable was used as the output variable for Learning and Timed Up and Go the supervised training and validations of the deep learning architectures and competing machine (TUG) Test Data. Bioengineering 2024, learning approaches. A hold-out validation process using 75 subjects for training and 31 subjects 11, 1000. https://doi.org/10.3390/ for testing was repeated one hundred times to obtain robust estimations of model performances At bioengineering11101000 each repetition, 5-fold cross-validation was carried out to select the best model ove

---

## Full Text (from PDF)

> Source: extracted verbatim via `pdftotext -layout`. Two-column layouts may produce interleaved text; content is preserved for downstream synthesis.
> 資料來源：`pdftotext -layout` 直接擷取。雙欄排版可能交錯呈現，內容保留供後續合成使用。

```text
bioengineering

Article
Older Adult Fall Risk Prediction with Deep Learning and Timed
Up and Go (TUG) Test Data
Josu Maiora 1,2, * , Chloe Rezola-Pardo 3 , Guillermo García 4 , Begoña Sanz 3,5                             and Manuel Graña 2

                                          1   Electronic Technology Department, Faculty of Engineering of Gipuzkoa, University of the Basque Country,
                                              20018 San Sebastian, Spain
                                          2   Computational Intelligence Group, Department of CCIA, University of the Basque Country,
                                              20018 San Sebastian, Spain; manuel.grana@ehu.eus
                                          3   Department of Physiology, University of the Basque Country, 48940 Leioa, Spain;
                                              chloe.rezola@ehu.eus (C.R.-P.); mariabegona.sanz@ehu.eus (B.S.)
                                          4   Systems and Automation Department, Faculty of Engineering of Gipuzkoa, University of the Basque Country,
                                              20018 San Sebastian, Spain; g.garcia@ehu.eus
                                          5   Biobizkaia Health Research Institute, 48903 Barakaldo, Spain
                                          *   Correspondence: j.maiora@ehu.eus; Tel.: +34-94-301-8617


                                          Abstract: Falls are a major health hazard for older adults; therefore, in the context of an aging
                                          population, predicting the risk of a patient suffering falls in the near future is of great impact for
                                          health care systems. Currently, the standard prospective fall risk assessment instrument relies on
                                          a set of clinical and functional mobility assessment tools, one of them being the Timed Up and Go
                                          (TUG) test. Recently, wearable inertial measurement units (IMUs) have been proposed to capture
                                          motion data that would allow for the building of estimates of fall risk. The hypothesis of this study is
                                          that the data gathered from IMU readings while the patient is performing the TUG test can be used
                                          to build a predictive model that would provide an estimate of the probability of suffering a fall in
                                          the near future, i.e., assessing prospective fall risk. This study applies deep learning convolutional
                                          neural networks (CNN) and recurrent neural networks (RNN) to build such predictive models based
                                          on features extracted from IMU data acquired during TUG test realizations. Data were obtained
Citation: Maiora, J.; Rezola-Pardo, C.;   from a cohort of 106 older adults wearing wireless IMU sensors with sampling frequencies of 100 Hz
García, G.; Sanz, B.; Graña, M. Older     while performing the TUG test. The dependent variable is a binary variable that is true if the patient
Adult Fall Risk Prediction with Deep      suffered a fall in the six-month follow-up period. This variable was used as the output variable for
Learning and Timed Up and Go              the supervised training and validations of the deep learning architectures and competing machine
(TUG) Test Data. Bioengineering 2024,
                                          learning approaches. A hold-out validation process using 75 subjects for training and 31 subjects
11, 1000. https://doi.org/10.3390/
                                          for testing was repeated one hundred times to obtain robust estimations of model performances At
bioengineering11101000
                                          each repetition, 5-fold cross-validation was carried out to select the best model over the training
Academic Editors: Massimiliano Pau,       subset. Best results were achieved by a bidirectional long short-term memory (BLSTM), obtaining an
Maria Giovanna Bianco, Salvatore          accuracy of 0.83 and AUC of 0.73 with good sensitivity and specificity values.
Pullano and Syed Kamrul Islam

Received: 24 July 2024
                                          Keywords: inertial sensors; fall prediction; fall risk assessment; deep learning; machine learning
Revised: 23 September 2024
Accepted: 30 September 2024
Published: 5 October 2024
                                          1. Introduction
                                                Older people suffering falls often require medical attention [1,2], hence falls are becom-
                                          ing a major public health problem due to the increasing aging of the population. The rising
Copyright: © 2024 by the authors.
                                          incidence of accidental falls has a great economic impact on health care systems and society:
Licensee MDPI, Basel, Switzerland.
                                          20–30% of falls lead to mild to severe injuries, and falls were the underlying cause of 10–15%
This article is an open access article
distributed under the terms and
                                          of all emergency department visits of older people in the United Kingdom in 1999 [3]; these
conditions of the Creative Commons
                                          figures are growing, with the population aging since then. Moreover, falls often cause
Attribution (CC BY) license (https://     mobility impairments that lead to dependency for activities of daily living, along with
creativecommons.org/licenses/by/          psychological consequences such as anxiety and fear for future falls [4,5]. According to
4.0/).                                    the World Health Organization, the approximate worldwide yearly incidence of falls for


Bioengineering 2024, 11, 1000. https://doi.org/10.3390/bioengineering11101000                        https://www.mdpi.com/journal/bioengineering

Bioengineering 2024, 11, 1000                                                                                            2 of 14


                                people over 65 years old is 28–35%, increasing to 32–42% for people aged over 70 years [6].
                                In particular, older adults living in nursing homes are especially prone to falling. In fact,
                                the fall incidence in this population is three times that of older people living in the com-
                                munity [7]. The financial toll from older adult falls in the United States the medical costs
                                attributed to nonfatal and fatal falls amounts to approximately $50 billion every year [8].
                                Therefore, fall prevention in older adults is of utmost socioeconomic importance.
                                     To this end, clinical questionnaires and clinical assessment-based fall risk prediction
                                tools have been proposed reporting a wide range in performance scores (sensitivity in
                                the range 14–94%, specificity in the range 38–100%) [9]. Additionally, fall risk assessment
                                protocols like the STEADI (stopping elderly accidents, deaths, and injuries) proposed by the
                                Centers for Disease Control (CDC) rely on functional mobility assessment tools in the form
                                of questionnaires, physical tests, gait analysis, and physical activity measurements [10].
                                Some of the most widely used assessment tools are the Timed Up and Go (TUG) test [11],
                                the Tinetti Assessment Tool [12], the STRATIFY score [13], and the Five-Times-Sit-to-Stand
                                (FTSS) test [14]. Specifically, the TUG test has proven valuable in early assessment of
                                balance and mobility [15–17]. However, all of these tools are in fact used qualitatively by
                                the clinician trying to assess prospective fall risk.
                                     The main hypothesis of this study is that the information extracted from IMU readings
                                during the realization of the TUG test can be used to build predictive models that provide
                                an estimate of the probability of the patient suffering a fall in the near future. In other
                                words, this information may be used for quantitative and predictive fall risk assessment.
                                This information would be of great importance to guide fall prevention for older adults,
                                and especially for those living in nursing homes due to their greater fall incidence.
                                     The paper reports two computational experiments. The first corresponds to application
                                of supervised machine learning algorithms to some descriptive variables of the TUG test
                                phases. The second corresponds to the application of deep learning architectures over the
                                raw data of the IMU wearable.
                                     The contributions of this paper are the following: (a) the collection of a dataset of IMU
                                readings while a large number of subjects are realizing a TUG test whose {F,NF} labels are
                                generated in a follow-up period of 6 months; (b) the proposal of deep learning architectures
                                to deal with this prediction problem; (c) the proposal of feature extraction processes and
                                conventional machine learning for comparison with the deep learning approaches.

                                2. Materials and Methods
                                      Recent surveys on the application of machine learning methods for prospective and
                                retrospective discrimination between patients who experience falls, i.e., fallers, (F) from non-
                                fallers (NF) using IMU information report widely different predictive performance results
                                (accuracy: 62–100%, sensitivity: 55–99%, specificity: 35–100%) in populations over 65 years
                                old [18–21]. These surveys also report a large heterogeneity of sensor placement, tasks
                                assessed, and sensor features. Specifically, some authors found that data from wearable
                                IMU sensors add meaningful information to the TUG test [22].
                                      Deep learning architectures have been applied successfully in many areas of computer
                                vision [23], medical image analysis [24], assisted/autonomous driving [25], and machine
                                anomaly monitoring [26], to name a few applications. Deep learning has already been
                                applied to the classification of IMU sensor data [27–30] for human activity recognition.
                                However, multiple data sources and adequate assessment tests are necessary to generalize
                                fall risk predictions. Nait Aicha et al. [31] compared deep learning approaches to traditional
                                machine learning methods to model fall risk on the basis of daily life body trunk accelerom-
                                eter data. They acquired data of participants wearing a triaxial accelerometer for 1 week.
                                They evaluated convolutional neural network (CNN), the long short-term memory (LSTM)
                                model, and a combination of both which they refer to as the “ConvLSTM”, reporting good
                                results in modeling the training data, but it generalized poorly over new subjects and the
                                relatively long period during which subjects must wear the inertial sensor is a barrier to
                                its implementation.

Bioengineering 2024, 11, 1000                                                                                                   3 of 14


                                      Due to the multidimensional nature of the risk of falls in older adults, there is no
                                 single ideal tool that performs a perfect risk assessment in any context. For this reason, the
                                 simultaneous application of multiple tools is recommended [32].
                                      The present article presents a secondary analysis of two single-blinded and multicenter
                                 randomized controlled trials that were registered with codes [ACTRN12618000536268;
                                 NCT03996083] whose primary outcomes have previously been published [33,34]. This
                                 study includes 106 subjects (68 women and 38 men) from 9 long-term nursing homes
                                 (LTNHs) (Gipuzkoa, Basque Country, Spain). Subject’s ages ranged from 70 to 104 years
                                 old and their physical and cognitive characteristics were described previously [35]. After
                                 providing written consent, participants performed the TUG test twice wearing a wireless
                                 inertial sensor (G-Walk, BTS Bioengineering Corp., Milan, Italy) and the best (fastest) trial
                                 was selected. This sensor was placed on the lower back area in order to quantify the center
                                 of mass movement. This study was approved by the Committee on Ethics in Research
                                 at the University of the Basque Country (Humans Committee Code M10/2016/105). All
                                 feature extraction and classification cross-validation was carried out in Matlab 2022b using
                                 wavelet, statistics and machine learning, and deep learning toolboxes. For performance
                                 evaluation we split the data in 5 groups and in each iteration, we hold out one group/fold
                                 and train the algorithms in the remaining 4 groups. We perform this method to obtain
                                 a less biased model than other methods, such as a simple train/test split. This process
                                 is carried out for all evaluated classifiers and feature extraction techniques. A fall was
                                 defined as an unintentional event in which the person comes to rest on the ground, not
                                 as a result of an epilectic seizure or an acute stroke [36]. Falls suffered by the residents
                                 are systematically detected and immediately recorded in the database by the staff of each
                                 nursing home. Information regarding residents who experienced any fall during 6-month
                                 follow-up period was extracted from the participant’s medical record as provided by the
                                 medical staff. Participants were labeled as faller (F) or non-faller (NF). The number of falls
                                 was not taken into consideration in the present study.

                                 2.1. Data and Feature Extraction
                                 2.1.1. TUG Test Realization for Data Capture
                                     The TUG test process is decomposed into six phases, as shown in Figure 1, which are
                                 described as follows:
                                 1.       The time elapsed from the beginning of standing-up motion up to the instant when
                                          the subject stands up;
                                    2.    The time elapsed walking from the initial standing up position to the position where
Bioengineering 2024, 11, x FOR PEER REVIEWs/he starts turning down;                                                            4 of 14
                                    3.    The time elapsed while turning down;
                                    4.    The time elapsed walking back to the chair from the end of the first turn to the
                                    g. Thebeginning
                                           gyroscopeofalso
                                                        the has
                                                            second   turn;
                                                                 a resolution  of 16 bits per axe and its sensitivity was adjusted to
                                    2000°/s. The magnetometer hasto
                                    5.    The  time elapsed  turning     prepare to of
                                                                       a resolution   sit13
                                                                                          down,  and a sensitivity of 1200 µT. Figure
                                                                                            bits with
                                    6.    The  time elapsed  sitting down   in
                                    2 shows example readings from the sensor.  the chair,  completing  the TUG test.


                                 Figure
                                 Figure 1. The
                                           The process
                                               process of
                                                       of the
                                                          the realization
                                                              realization of the TUG test decomposed into six phases.

                                2 shows example readings from the sensor.


Bioengineering 2024, 11, 1000                                                                                                             4 of 14


                                   2.1.2. Raw IMU Data and Labels
                                        The G-Walk IMU sensor acquires acceleration, angular velocity and magnetic field
                                   data. Its components are a triaxial accelerometer (x, y, z), a triaxial gyroscope (x, y, z), and a
                                   triaxial magnetometer (roll, pitch, yaw). Sampling frequency was adjusted to 100 Hz. The
                                   accelerometer has a resolution of 16 bits per axe and its sensitivity was adjusted to 2 g. The
                                   gyroscope also has a resolution of 16 bits per axe and its sensitivity was adjusted to 2000◦ /s.
                                   The magnetometer has a resolution of 13 bits with a sensitivity of 1200 µT. Figure 2 shows
                                   example
                                Figure 1. Thereadings
                                               process from
                                                       of thethe sensor. of the TUG test decomposed into six phases.
                                                              realization


                                 (a)                                                                      (b)
                                Figure  2. An
                                   Figure       instance
                                            2. An instanceofofthe
                                                               thereadings  of the
                                                                   readings of theG-walk
                                                                                    G-walkduring
                                                                                            during  a TUG
                                                                                                  a TUG testtest realization
                                                                                                             realization     shown
                                                                                                                         shown      asdata
                                                                                                                               as raw  raw data
                                plots: (a) triaxial accelerometer,    and  (b)  triaxial gyroscope.
                                   plots: (a) triaxial accelerometer, and (b) triaxial gyroscope.

                                       WeWecollected
                                                collected rawraw IMU IMUdata    for for
                                                                             data   eacheach
                                                                                          TUG test    realization by
                                                                                                 TUG test                 subject.
                                                                                                                realization        Due to
                                                                                                                                by a       variabil-
                                                                                                                                       subject.  Due to
                                    ity in  the   time   taken    to  perform    the TUG    test, the   number    of samples
                                variability in the time taken to perform the TUG test, the number of samples per subject        per  subject varies
                                    fromfrom
                                varies     13641364to 9975to as  shown
                                                              9975         in Figure
                                                                      as shown         3. Additionally,
                                                                                   in Figure               data of patients
                                                                                                3. Additionally,       data ofsuffering
                                                                                                                                patientsfall occur- fall
                                                                                                                                          suﬀering
                                    rences during a 6-month follow-up period were collected and provided to the researchers
                                occurrences during a 6-month follow-up period were collected and provided to the
                                    by the staff of the LTNHs. In this period, 21 subjects (19%) were labeled as fallers (F).
                                researchers
                                   This label by   datathearestaﬀ
                                                                usedofasthetheLTNHs.
                                                                               dependent  In variable
                                                                                              this period,
                                                                                                         in the21training
                                                                                                                   subjects and(19%)   were of
                                                                                                                                 validation   labeled
                                                                                                                                                the as
                                fallers  (F). This algorithms,
                                    classification     label data are   for used   as the
                                                                            both the   deepdependent       variableand
                                                                                              learning networks        in the training and
                                                                                                                           conventional       validation
                                                                                                                                          machine
                                of the   classification
                                    learning approaches.        algorithms,      for  both   the   deep    learning     networks     and  conventional
                                machine      learning
                                          In the           approaches.
                                                   pre-processing       steps, we remove the subjects with missing values of IMU sensors
                                    orIn
                                       without
                                           the label       informationsteps, we
                                                  pre-processing            (faller/non-faller).
                                                                                        remove the  Then, we    sort the
                                                                                                          subjects    withsubjects regarding
                                                                                                                              missing   valuestheir
                                                                                                                                                 of IMU
                                    number      of  samples,     observing     that  the  great  majority    of them
                                sensors or without label information (faller/non-faller). Then, we sort the subjects    have  less than  5000  IMU
                                    data samples,
                                regarding               and that those
                                                their number                 above this
                                                                      of samples,         number that
                                                                                      observing      couldthebe considered
                                                                                                                 great majorityoutliers. However,
                                                                                                                                     of them   have less
                                    these subjects are precisely the ones that have a higher fall risk. Consequently, we train our
                                than 5000 IMU data samples, and that those above this number could be considered
                                    model with data from all the subjects.
                                outliers.The However,          these subjects
                                                 class imbalance                    are precisely
                                                                         in the dataset    is moderate  the(ratio
                                                                                                              ones1:5);
                                                                                                                      thathowever,
                                                                                                                             have a conventional
                                                                                                                                      higher fall risk.
                                Consequently,          we   train   our   model     with  data   from    all the  subjects.
                                    machine learning approaches are usually biased towards the majority class, which in this
                                       Theis the
                                    study     classnon-fallers
                                                       imbalance    (NF)in the
                                                                           class, dataset
                                                                                  sufferingisfrom
                                                                                                moderate      (ratio even
                                                                                                    low sensitivity     1:5); when
                                                                                                                              however,    conventional
                                                                                                                                    reporting high
                                machine
                                    accuracy learning
                                                 [37]. approaches are usually biased towards the majority class, which in this
                                study isThe  thenorm     of the 3D(NF)
                                                    non-fallers        acceleration   vectors is computed
                                                                             class, suﬀering       from lowatsensitivity
                                                                                                                  each instanteven
                                                                                                                                 in order to obtain
                                                                                                                                       when    reporting
                                    a scalar   time
                                high accuracy [37].   series.   In this  way,  significant  changes    in acceleration    magnitude,   which  occur
                                    in events such as walking, turning, or getting up/sitting in the chair, are easily detected
                                    regardless of the orientation of the device.

Bioengineering 2024, 11, x FOR PEER REVIEW                                                                                            5 of 14
  Bioengineering 2024, 11, 1000                                                                                                          5 of 14


                                  Figure
                                    Figure3.3.
                                            Number
                                               Numberofofsamples per
                                                           samples   recorded
                                                                   per        IMU
                                                                       recorded   sequence
                                                                                IMU        during
                                                                                    sequence      the
                                                                                             during   realization
                                                                                                    the           ofof
                                                                                                        realization  TUG tests
                                                                                                                       TUG     sorted
                                                                                                                           tests sorted
                                  inin
                                     ascending
                                       ascendingorder.
                                                  order.

                                    2.1.3.
                                        The TUG
                                              norm Test
                                                      of Variables   per Phasevectors is computed at each instant in order to obtain
                                                         the 3D acceleration
                                  a scalarWetimerecorded    spatiotemporal
                                                    series. In this            measurements
                                                                       way, significant         of the
                                                                                           changes    inIMU   wearable sensor
                                                                                                          acceleration            during
                                                                                                                          magnitude,      TUG
                                                                                                                                       which
                                    test in
                                  occur  realizations    decomposed
                                              events such as             into turning,
                                                                  walking,     standing or
                                                                                         phase,  sitting
                                                                                            getting        phase, in
                                                                                                       up/sitting walking    phases,
                                                                                                                       the chair,  areand body
                                                                                                                                        easily
                                    trunk rotations
                                  detected               (flexion
                                              regardless of    theand/or     extension
                                                                    orientation   of the angle).
                                                                                         device. These measurements are used as input
                                    variables by the conventional machine learning classification algorithms. Table 1 shows
                                    the TUG
                                  2.1.3. maximum,       minimum
                                                 Test Variables      and
                                                                   per     average values of each of these parameters across subjects.
                                                                       Phase
                                    TheWe first  group   of  variables  are  the duration ofofthe
                                             recorded spatiotemporal measurements                thedifferent   phases.
                                                                                                      IMU wearable          During
                                                                                                                         sensor     the “Sit
                                                                                                                                during   TUGto
                                    Stand”
                                  test        and “Stand
                                       realizations           to Sit” phases,
                                                       decomposed                we recorded
                                                                       into standing           the vertical,
                                                                                       phase, sitting   phase,media-lateral,
                                                                                                                walking phases, andandanterior–
                                                                                                                                         body
                                  trunk rotations (flexion and/or extension angle). These measurements are used as phases,
                                    posterior    accelerations,   as  well  as extension  and  bending      angles. In  the “Turning”   input
                                    we recorded
                                  variables    by thetheconventional
                                                          angular accelerations.     We recorded
                                                                         machine learning           the duration
                                                                                              classification        of each activity
                                                                                                               algorithms.    Table 1phase
                                                                                                                                       shows for
                                    all subjects,   computing     the  mean    and variance  of  each   of them.
                                  the maximum, minimum and average values of each of these parameters across subjects.
                                  The first group of variables are the duration of the diﬀerent phases. During the “Sit to
                                    Table 1. Descriptive statistics of the spatiotemporal measurements of the TUG test realizations corre-
                                  Stand” and “Stand to Sit” phases, we recorded the vertical, media-lateral, and anterior–
                                    sponding to standing phase, sitting phase, and rotations body trunk kinematics (flexion and/or extension
                                  posterior accelerations, as well as extension        and bending angles. In the “Turning” phases,
                                    angle). Accelerations (acc) are measured in m/s2 . Body trunk rotations are measured in degrees. Anterior–
                                  we recorded the angular accelerations. We recorded the duration of each activity phase
                                    posterior (AP), Medio-Lateral (ML), and Vertical (Vert) axis accelerometer data are shown.
                                  for all subjects, computing the mean and variance of each of them.
                                                        Variable                          Max               Min              Average
                                  Table 1. Descriptive statistics of the spatiotemporal measurements of the TUG test realizations
                                                                               Phase
                                  corresponding to standing phase, sitting phase,    Duration
                                                                                   and rotations body trunk kinematics (flexion and/or
                                  extension angle). Sit_to_Stand
                                                    Accelerations(s)(acc) are measured in m/s
                                                                                           4.72. Body trunk 0.33
                                                                                                             rotations are measured
                                                                                                                              1.73 in
                                                   Walking_out
                                  degrees. Anterior–posterior     (s) Medio-Lateral (ML),24.99
                                                                (AP),                                        0.78
                                                                                            and Vertical (Vert)               4.66 data
                                                                                                                axis accelerometer
                                  are shown.           Turning (s)                        17.19               1.5             4.81
                                                    Walking_in (s)                         10.1              0.57             3.15
                                                       Variable (s)
                                                 Turning_around                           Max
                                                                                          11.43            Min1.5          Average
                                                                                                                              3.73
                                                    Stand_to_Sit (s)         Phase Duration  4                0.5             1.95
                                                     Sit_to_Stand (s)                         4.7
                                                                                   Sit To Stand                0.33              1.73
                                                     Walking_out   (s) (m/s2 )
                                             Sit_to_Stand_Vert_Min_acc                   24.99
                                                                                         4.53                  0.78
                                                                                                                 0.26            4.66
                                                                                                                                   1.83
                                                        Turning (s)
                                             Sit_to_Stand_Vert_Min_acc (m/s2 )           17.19
                                                                                         − 0.72                −1.5
                                                                                                                  4.12           4.81.93
                                                                                                                                  −
                                             Sit_to_Stand_ML_Max_acc   (m/s 2)           2.26                     0.1              0.86
                                                      Walking_in (s)                      10.1                 0.57              3.15
                                             Sit_to_Stand_ML_Min_acc   (m/s2)            − 0.34                −  2.34            − 0.94
                                                   Turning_around (s)                    11.43                  1.5              3.73
                                             Sit_to_Stand_AP_Max_acc (m/s2 )             4.27                    0.29              1.60
                                                     Stand_to_Sit (s)      2                4
                                                                                         −0.42
                                                                                                               0.5
                                                                                                               −2.69
                                                                                                                                 1.95
                                                                                                                                  −1.12
                                          Sit_to_Stand_AP_Min_acc (m/s )
                                                                         ◦
                                           Sit_to_Stand_Extension_Peak ( )    Sit To Stand
                                                                                         60.2                    4.9               33.36
                                          Sit_to_Stand_Extension_Range
                                        Sit_to_Stand_Vert_Min_acc        (◦ )
                                                                     (m/s²)                39
                                                                                          4.53                   0.1
                                                                                                              0.26                14.21
                                                                                                                                1.83
                                            Sit_to_Stand_Bending_Peak ( ◦)                 70                   19.9              47.42
                                        Sit_to_Stand_Vert_Min_acc (m/s²)                 −0.72                −4.12             −1.93
                                           Sit_to_Stand_Bending_Range (◦ )                69.9                  10.4              44.85
                                        Sit_to_Stand_ML_Max_acc (m/s²)                    2.26                 0.1              0.86

                                     Sit_to_Stand_AP_Min_acc (m/s²)                        −0.42        −2.69             −1.12
                                      Sit_to_Stand_Extension_Peak (°)                       60.2         4.9              33.36
                                     Sit_to_Stand_Extension_Range (°)                        39          0.1              14.21
Bioengineering 2024, 11, 1000          Sit_to_Stand_Bending_Peak (°)                         70         19.9              47.42
                                                                                                                           6 of 14
                                      Sit_to_Stand_Bending_Range (°)                       69.9         10.4              44.85
                                                                                 Turning
                                   Table 1. Cont.
                                   First_Turn_Avg__Angular_Acc (m/s²)                         88.4      11.4             43.76
                                   First_turn_Peak_Angular_Acc
                                                      Variable          (m/s²)            Max181.4      28.5
                                                                                                      Min                88.63
                                                                                                                    Average
                                                                           Turning     Around
                                                                                   Turning
                                  Second_Turn_Avg_Angular_Acc
                                       First_Turn_Avg__Angular_Acc (m/s2   (m/s²)
                                                                              )              109.2
                                                                                           88.4       11.414.1            50.71
                                                                                                                      43.76
                                  Second_turn_Peak_Angular_Acc
                                       First_turn_Peak_Angular_Acc (m/s )  (m/s²)
                                                                            2                194.3
                                                                                          181.4       28.540.3           100.20
                                                                                                                      88.63
                                                                               Stand   To
                                                                              Turning AroundSit
                                    Stand_to_Sit_Vert_Max_acc
                                      Second_Turn_Avg_Angular_Acc (m/s²)
                                                                      (m/s2                   9.84
                                                                                          109.2       14.10.39        50.714.88
                                      Second_turn_Peak_Angular_Acc    (m/s    2)          194.3       40.3           100.20
                                    Stand_to_Sit_Vert_Min_acc (m/s²)                         −0.59      −4.84             −2.39
                                     Stand_to_Sit_ML_Max_acc (m/s²)              Stand To Sit 3.69       0.67             1.78
                                     Stand_to_Sit_ML_Min_acc         (m/s²)
                                         Stand_to_Sit_Vert_Max_acc (m/s   2)                 −0.53
                                                                                           9.84         −6.59
                                                                                                     0.39              4.88−1.87
                                         Stand_to_Sit_Vert_Min_acc (m/s  2)               −0.59      −4.84            −2.393.02
                                     Stand_to_Sit_AP_Max_acc         (m/s²)
                                                                                              6.19       0.43
                                         Stand_to_Sit_ML_Max_acc (m/s )                    3.69      0.67              1.78
                                     Stand_to_Sit_AP_Min_acc        (m/s²)
                                         Stand_to_Sit_ML_Min_acc (m/s2 )
                                                                                              0.11
                                                                                          −0.53
                                                                                                         −2.5
                                                                                                     −6.59            −1.87
                                                                                                                           −0.98
                                     Stand_to_Sit_Extension_Peak
                                         Stand_to_Sit_AP_Max_acc (m/s )  2 (°)                55.8
                                                                                           6.19      0.43 1            3.0211.82
                                          Stand_to_Sit_AP_Min_acc
                                    Stand_to_Sit_Extension_Range  (m/s2 ) (°)              0.11
                                                                                              66.5   −2.50.6          −0.9842.28
                                          Stand_to_Sit_Extension_Peak (◦ )                55.8         1              11.82
                                      Stand_to_Sit_Bending_Peak          (°)
                                         Stand_to_Sit_Extension_Range (◦ )                66.5
                                                                                              75.5    0.6
                                                                                                         19.5         42.28
                                                                                                                           53.27
                                     Stand_to_Sit_Bending_Range
                                           Stand_to_Sit_Bending_Peak ( ) (°)
                                                                       ◦                      62.6
                                                                                           75.5      19.5 0           53.2724.94
                                          Stand_to_Sit_Bending_Range (◦ )                62.6          0              24.94
                                     Figure 4 shows a box plot of the duration of each phase. The turning phase has the
                                longest Figure
                                         average4 shows
                                                   duration  followed
                                                          a box plot of by
                                                                        the the  walking
                                                                             duration       out,phase.
                                                                                       of each    turningThearound
                                                                                                              turningand  walking-in
                                                                                                                        phase has
                                    the longest average  duration followed  by the  walking   out, turning  around
                                phases. The sitting and standing activities have the shortest average durations. We and  walking-
                                    in phases.
                                compute         The sitting Chi-Square
                                           the univariate   and standingTest
                                                                          activities
                                                                              [38] ofhave
                                                                                       eachthefeature
                                                                                                shortest averagetodurations.
                                                                                                       relative     the {F, NF}Weclass
                                    compute
                                label,        the univariate
                                       obtaining  the featureChi-Square
                                                              importance Test [38] of shown
                                                                            ranking   each feature   relative
                                                                                                in Figure  5. to the {F, NF} class
                                    label, obtaining the feature importance ranking shown in Figure 5.


                                    Figure 4. Box-plot of each phase duration in TUG test. The median, upper-lower quartiles and
                                Figure 4. Box-plot of each phase duration in TUG test. The median, upper-lower quartiles and max-
                                    maximum-minimum values are shown.
                                imum-minimum values are shown.

                    Bioengineering 2024, 11, x FOR PEER REVIEW
Bioengineering 2024, 11, 1000                                                                                                                   7 of 14


                                                    Figure 5.
                                   Figure 5. Univariate       Univariate
                                                        Chi-Square       Chi-Square Test
                                                                   Test importance        importance
                                                                                    ranking of        ranking
                                                                                                 TUG test phaseofinput
                                                                                                                   TUG test phase
                                                                                                                       variables  input
                                                                                                                                 used byvariables
                                                    conventional machine   learning
                                   conventional machine learning classifiers.       classifiers.

                                   2.1.4. Wavelet 2.1.4.
                                                  Features
                                                         Wavelet Features
                                         Wavelet Transforms   (WT) are
                                                        Wavelet          used to
                                                                 Transforms    (WT)represent
                                                                                        are used a to
                                                                                                   signal in terms
                                                                                                       represent a of  localized
                                                                                                                    signal        basis
                                                                                                                            in terms  of localize
                                   functions calledfunctions
                                                    wavelets.called
                                                               WT use a   wavelet
                                                                    wavelets.        function
                                                                                 WT use           and a function
                                                                                             a wavelet   lowpass and
                                                                                                                  scaling  function to
                                                                                                                        a lowpass   scaling func
                                   generate low-variance
                                                   generaterepresentations
                                                             low-variance of     real-valued of
                                                                            representations       time series  datatime
                                                                                                      real-valued    at series
                                                                                                                        differentdata
                                                                                                                                  timeat diﬀere
                                   scales. The general formulation  of the wavelet    is  like  the following  equation:
                                                   scales. The general formulation of the wavelet is like the following equation:
                                                                                                t − τ1 𝑥 𝑡 · 𝜓 𝑡 − 𝜏
                                                                                                     
                                                                                 Z
                                                                 γ(s, τ ) = √       x (t𝛾)·𝑠,
                                                                                           ψ𝜏 =                      𝑠
                                                                               s                  s √𝑠
                                                           Traditional frequency analysis methods such as the Fourier Transform yie
                                         Traditional frequency analysis methods such as the Fourier Transform yield only
                                                     frequency-domain
                                   frequency-domain information without       information       without
                                                                                    any indication       ofany     indicationlocation/extent
                                                                                                             the temporal        of the temporaloflocation/ex
                                                                                                                                                        a
                                   given frequency component. Wavelet transforms, on the other hand, provide both temporal provid
                                                     a  given    frequency     component.         Wavelet      transforms,      on  the   other    hand,
                                                     temporal andasfrequency
                                   and frequency information,                         information,
                                                                          the basis functions            as the
                                                                                                    it relies     basis
                                                                                                               upon       functions
                                                                                                                        are localizeditinrelies
                                                                                                                                            bothupon
                                                                                                                                                   time are local
                                   and frequency.    both   time   and   frequency.
                                         The IMU readings  The areIMU     readings are
                                                                      transformed       bytransformed
                                                                                            the wavelet by     time thescattering
                                                                                                                         wavelet time       scattering decomp
                                                                                                                                    decomposition
                                                     using    the  Gabor    wavelet    [39]  that   yields  representations
                                   using the Gabor wavelet [39] that yields representations insensitive to translations in        insensitive     tothe
                                                                                                                                                      translation
                                   input signal without sacrificing class discriminability and separate the data from different from d
                                                     input   signal  without    sacrificing     class   discriminability      and  separate     the  data
                                                     classes
                                   classes as far clear  as as    far clear
                                                            possible.        as wavelet
                                                                         These  possible. These        wavelet
                                                                                            features are           features
                                                                                                              obtained        areapplying
                                                                                                                           after  obtainedthe  after   applying th
                                                                                                                                                   filter
                                                     banks of the
                                   banks of the wavelet       transformwavelet
                                                                            to ourtransform
                                                                                     signals to Theour     signals The
                                                                                                       scattering            scattering
                                                                                                                      sequences     are sequences
                                                                                                                                         38-by-1250,are 38-b
                                   where 1250 is the where
                                                         number1250ofis time
                                                                         the number
                                                                               steps and of 38time    steps
                                                                                                  is the      and 38ofisscattering
                                                                                                           number           the number       of scattering
                                                                                                                                        scales.    This        scale
                                                     matrix    constitutes    the  input    features     for  our    1-D
                                   matrix constitutes the input features for our 1-D CNN approach to fall risk prediction. CNN    approach      to  fall  risk  pred
                                                     Additionally,      for we   consider     each   element      of the
                                   Additionally, for we consider each lement of the matrix as an independent feature. As amatrix   as  an  independent       featu
                                   result, we receiveresult,
                                                        47,500we receive
                                                                 independent 47,500    independent
                                                                                  wavelet    features withwaveletthis features    with this
                                                                                                                      decomposition.           decomposition.
                                                                                                                                           Due to the
                                   large number ofthe     large we
                                                       features,  number
                                                                       needofto carry
                                                                                features, outwea need
                                                                                                   featureto carry
                                                                                                             selectionout a   feature
                                                                                                                           process   toselection
                                                                                                                                        enhance the  process to e
                                   efficiency of thethe   eﬃciency
                                                      model.     The of the
                                                                      importancemodel. of The    importance
                                                                                          each wavelet            of each
                                                                                                              feature    to wavelet    feature
                                                                                                                            discriminate          to vs.
                                                                                                                                              faller  discriminat
                                   non faller is     vs.
                                                 evaluatednonby faller is  evaluated
                                                                   individual            by
                                                                                 Chi-square   individual
                                                                                                  tests       Chi-square
                                                                                                         [38]. Finally,    wetests  [38].the 20
                                                                                                                                choose     Finally,
                                                                                                                                                  most we choose
                                                     most    significant     wavelet    features      as  the   optimal
                                   significant wavelet features as the optimal ones. Increased number of wavelet features didones.  Increased       number      of w
                                   not improve thefeatures       did ot improve
                                                      classification    performance.   the classification performance.

                                                       2.2. Machine Learning
                                                            The fall risk assessment is stated as a binary classification problem, where
                                                       classes are {F, NF} labels assigned in the follow-up period after the IMU measur
                                                       (hence, we deal with a prospective problem).

Bioengineering 2024, 11, 1000                                                                                              8 of 14


                                2.2. Machine Learning
                                     The fall risk assessment is stated as a binary classification problem, where the classes
                                are {F, NF} labels assigned in the follow-up period after the IMU measurements (hence, we
                                deal with a prospective problem).

                                2.2.1. Conventional Machine Learning Algorithms
                                     We have applied the following 5 conventional Machine Learning (ML) algorithms
                                to classify the subjects according to their fall risk assessment: Random Forest (RF), Sup-
                                port Vector Machines (SVM), K nearest neighbors (KNN), Naive Bayes (NB). The hyper-
                                parameters of the machine learning algorithms are set as follows: RF: #splits = 105,
                                #learners = 30 SVM: quadratic kernel; KNN: K = 10; NB: Gaussian kernel. The imple-
                                mentations used are the standard ones provided in MATLAB. Conventional ML algorithms
                                are applied over TUG test phase variables described in Table 1, because the raw IMU signals
                                have an extremely large dimensionality to be used as inputs for the selected ML models.

                                2.2.2. Deep Learning Neural Network Models
                                      One of the most distinctive characteristics of deep learning approaches is that they
                                learn a hierarchy of abstract representations from the raw data [40] overcoming the need
                                to define and tune specific features for the problem at hand. In fact, most deep learning
                                approaches are artificial neural networks, so that the term “deep” refers to the number of
                                layers in the network—the more layers, the deeper the network. Two of the most popular
                                deep learning networks are the convolutional neural network (CNN) [41] and the long
                                short-term memory (LSTM) [42]. CNNs built up a hierarchy of convolution filters trained
                                from the data. We use a specific brand of CNNs whose input data are extracted by means
                                of Scattering Wavelet Transforms [42,43] in its 1D version.
                                      An LSTM is good for classifying sequential and time-series data, when the prediction
                                or output of the network must be based on a remembered sequence of data points. An LSTM
                                is a type of recurrent neural network (RNN) [44] that can learn long-term dependencies
                                between time steps of sequence data. Unlike a CNN, a LSTM can remember the state of the
                                network between predictions [23]. The core components of a LSTM network are a sequence
                                input layer and a LSTM layer. A sequence input layer incorporates time-series data into
                                the network. A LSTM layer learns long-term dependencies between time steps of sequence
                                data over time. The LSTM is trained on the raw IMU readings after computing the norms
                                of the 3D vectors of each measure.

                                3. Results
                                      We have performed four different computational experiments evaluating the different
                                fall risk predictors’ performance in terms of accuracy, sensitivity, and specificity. In the case
                                of raw data, we have also computed the area under the receiving operator curve (AUC). In
                                all cases, we have carried out 100 repetitions of the holdout cross validation with 75 subjects
                                for training and 31 for testing using stratified sampling in the sample extraction, and 5-fold
                                cross-validation over the training set to select the best model for testing at each holdout
                                repetition.

                                3.1. Conventional Machine Learning Classifiers
                                      We have carried out two different computational experiments with conventional
                                ML classifiers that will serve as benchmarks for the deep learning approaches. In the
                                first experiment, we use as features the aggregated spatiotemporal measurements of the
                                realizations of TUG test corresponding to standing phase, sitting phase, and rotations
                                body trunk kinematics from Table 1. The results are shown in Table 2. We have carried
                                out the classifier validation experiments over three distinct subsets of features: (a) the
                                most important TUG phase descriptive variables selected by independent Chi-square
                                tests, (b) the duration of each phase of the TUG test, and (c) the entire set of TUG phase

Bioengineering 2024, 11, 1000                                                                                                        9 of 14


                                descriptive variables. Results are rather poor for all models and features, with accuracy
                                below 0.7, and sensitivity below 0.33.

                                Table 2. Average test performance results after 100 repetitions of hold-out cross-validation of different
                                classifiers for sets of features extracted from the TUG test phases enumerated in Table 1.

                                              Feature Set              Classifier          Accuracy        Sensitivity    Specificity
                                                                           RF                 0.62              0.08          0.84
                                                                          SVM                 0.65              0.25          0.80
                                  6 Most Important Feature Set            KNN                 0.69              0.04          0.95
                                                                           NB                 0.65              0.25          0.80
                                                                           LR                 0.66              0.04          0.90
                                                                           LD                 0.67              0.04          0.92
                                                                           RF                 0.60              0.17          0.77
                                                                          SVM                 0.65              0.21          0.82
                                     Phase Duration Features              KNN                 0.65              0.46          0.72
                                                                           NB                 0.66              0.21          0.84
                                                                           LR                 0.66              0.13          0.87
                                                                           LD                 0.66              0.13          0.87
                                                                           RF                 0.68              0.17          0.89
                                                                          SVM                 0.54              0.21          0.67
                                          All Feature Set                 KNN                 0.58              0.33          0.67
                                                                           NB                 0.59              0.25          0.72
                                                                           LR                 0.48              0.21          0.59
                                                                           LD                 0.57              0.36          0.62


                                     In the second experiment, we apply the ML classifiers to the selection of the 20 most
                                significant wavelet scattering features extracted from the magnitude of the acceleration
                                signal. Results presented in Table 3 show significant improvement over results reported
                                in Table 2. The increase in specificity may be due to the class-imbalance induced bias,
                                while the naive Bayes approach achieves an average sensitivity of 0.52, which is the best
                                result found.

                                Table 3. Average test performance results after 100 repetitions of hold-out cross-validation of different
                                classifiers using the 20 most significant wavelet scattering features extracted from the acceleration
                                magnitude signal recorded along the TUG test.

                                     Classifier.            Accuracy            Sensitivity           Specificity          AUC
                                         RF                   0.81                  0.10                 0.99               0.75
                                       SVM                    0.69                  0.29                 0.79               0.64
                                       KNN                    0.77                  0.10                 0.94               0.61
                                        NB                    0.79                  0.52                 0.86               0.77
                                         LR                   0.71                  0.19                 0.84               0.61
                                        LD                    0.73                  0.19                 0.86               0.70


                                3.2. Deep Learning Results
                                3.2.1. CNN
                                     We evaluate 1-D CNN using as inputs the wavelet scattering matrices computed over
                                the acceleration magnitude. The scattering sequences are 38-by-1250 where 1250 is the

Bioengineering 2024, 11, 1000                                                                                                    10 of 14


                                number of time steps and 38 is the number of scattering paths. Results are shown in Table 4
                                for various selections of gradient descent optimization methods (RMSProp, SGDM, and
                                Adam). Results improve over the ML conventional classifiers in terms of accuracy; however,
                                they are not above of RF in terms of AUC, which for many authors is a more appropriate
                                performance measure for class imbalanced datasets.

                                Table 4. Average test performance results after 100 repetitions of hold-out cross-validation for the 1D
                                CNN architectures.

                                                                                           1D CNN
                                                                 RMSProp                    SGDM                      Adam
                                        Accuracy                    0.84                      0.81                      0.81
                                       Sensitivity                  0.33                      0.33                       0
                                       Specificity                  0.96                      0.92                       1
                                        Precision                   0.66                      0.50                       0
                                          AUC                       0.63                      0.65                      0.5


                                3.2.2. LSTM
                                      We evaluate LSTM deep learning algorithms over raw inertial sensor data (triaxial
                                accelerometer, gyroscope and magnetometer). Both standard LSTM and bidirectional LSTM
                                (BLSTM) were used as we have access to the entire sequence of data. We evaluated mini-
                                batch sizes from 5 to 25 with number of hidden units set to 40 and a learning rate of 0.005.
                                The best accuracy results were obtained for mini-batch sizes of 10, 11, and 15. To find the
                                optimal number of hidden units, we set the mini-batch size to 11 and evaluated the accuracy
                                beginning from 10 until 100 units using increments of 10. The best values are obtained for
                                40 hidden units. We chose a mini-batch size of 11. Subjects were ordered according to their
                                number of samples and shuffle was disabled to reduce the “padding effect”.
                                      Table 5 shows the average test performance results after 100 repetitions of hold-
                                out cross-validation of various LSTM architectures. We found that BLSTM performance
                                measures are significantly better than standard LSTM results for every mini-batch size and
                                the best size for BLSTM is ten. The BLSTM trained with SGDM significantly outperforms
                                all other approaches in terms of sensitivity and AUC. Figure 6 shows the corresponding
                                ROC curve with point-wise confidence bounds.

                                Table 5. Average test performance results after 100 repetitions of hold-out cross validation for the
                                LSTM architectures.

                                                     LSTM        LSTM           LSTM          BLSTM         BLSTM            BLSTM
                                                RMSProp         SGDM            Adam        RMSProp          SGDM              Adam
                                  Accuracy           0.87         0.80           0.80           0.83          0.83             0.87
                                 Sensitivity         0.33         0.16           0.16           0.33          0.50             0.33
                                  Specificity         1           0.96           0.96           0.96          0.92              1
                                  Precision           1           0.50           0.50           0.66          0.85              1
                                    AUC              0.60         0.64           0.62           0.66          0.73             0.78

Bioengineering 2024, 11, x FOR PEER REVIEW                                                                                                          11 of 14
       Bioengineering 2024, 11, 1000                                                                                                                          11 of 14


                                         Figure 6. ROC curve with Point-wise Confidence Bounds of an instance of the 5-fold cross-validation
                                  Figure 6. ROC curve with Point-wise Confidence Bounds of an instance of the 5-fold cross-validation
                                         of the BILSTM
                                  of the BILSTM          architecture.
                                                  architecture.        The dashed
                                                                The dashed         lines represent
                                                                            lines represent        the chance
                                                                                            the chance  ROC. ROC.
                                         4. Discussion
                                  4. Discussion
                                                In the present study, conventional machine learning classifiers and deep learning
                                       Innetworks
                                            the present havestudy,been conventional          machine learning
                                                                          applied to prospective            fall riskclassifiers
                                                                                                                        predictionand   overdeepIMU  learning
                                                                                                                                                         sensor data
                                  networks
                                         captured during the realization of the TUG test for a cohort of older adults (Ncap-
                                               have    been    applied     to  prospective       fall risk  prediction     over   IMU    sensor    data      = 106, of
                                  tured which
                                         during21the  arerealization
                                                           fallers). The   of hypothesis
                                                                              the TUG test    of for
                                                                                                  thisawork
                                                                                                         cohortis of
                                                                                                                  thatolder   adults (N
                                                                                                                        processing         = 106,
                                                                                                                                       these  dataofwithwhich machine
                                  21 arelearning
                                           fallers). and
                                                       The deep
                                                             hypothesis
                                                                      learning of this   work iswould
                                                                                  approaches           that allow
                                                                                                             processing      these data
                                                                                                                       prospective      fall with
                                                                                                                                             risk machine
                                                                                                                                                   prediction. We
                                  learning
                                         haveand deep
                                                 explored   learning      approaches
                                                                 several signal            would allow
                                                                                     features,                prospective
                                                                                                     including the       raw fall    riskand
                                                                                                                               signal,     prediction.
                                                                                                                                                 several We  machine
                                  have explored
                                         learning andseveral
                                                           deep   signal   features,
                                                                    learning           including
                                                                                approaches.         Thethe raw
                                                                                                         best    signal,
                                                                                                              results   inand    several
                                                                                                                            terms of       machine(i.e.,
                                                                                                                                       sensitivity       learn-
                                                                                                                                                              accurate
                                  ing and    deep    learning      approaches.       The    best    results  in  terms     of sensitivity
                                         prediction of fallers) have been obtained by the naive Bayes approach on wavelet scattering         (i.e.,  accurate
                                  prediction    of fallers)
                                         features               have been
                                                      (sensitivity             obtained
                                                                         = 0.52),   and by   bythethe BLSTM
                                                                                                        naive Bayes     approach
                                                                                                                  trained             on wavelet
                                                                                                                              with SGDM         on the scatter-
                                                                                                                                                            raw IMU
                                  ing features     (sensitivity
                                         signal data      (0.50). =We   0.52),  and byhigh
                                                                           obtained        the BLSTM        trained
                                                                                                 specificity in        with SGDM
                                                                                                                    many     instances;on the
                                                                                                                                           however,raw the IMUcost of
                                  signal data     (0.50). We of a
                                         misclassification         obtained     high
                                                                         faller is     specificity
                                                                                   higher     than in many           instances;
                                                                                                      misclassification            however, the
                                                                                                                             of a non-faller,    hence  cost of
                                                                                                                                                           sensitivity
                                  misclassification
                                         is a more of        a faller is
                                                       relevant            higher than
                                                                     performance            misclassification
                                                                                       measure. It        was arguedof a that
                                                                                                                          non-faller,    hence
                                                                                                                                the ability       sensitivity
                                                                                                                                               of the    TUG test to
                                  is a more   relevant
                                         assess            performance
                                                   prospective                 measure.
                                                                     fall risk was    limited It was
                                                                                                   [14];argued
                                                                                                         however, thatour
                                                                                                                        theresults
                                                                                                                              ability of
                                                                                                                                     show thethat
                                                                                                                                                TUG test
                                                                                                                                                     processingto the
                                  assessIMU
                                          prospective
                                                 sensor fall
                                                           data,riskthatwas   limited [14];
                                                                           implicitly            however,
                                                                                         takes into           our results
                                                                                                          account     posturalshow    that gait,
                                                                                                                                  stability,processingstride thelength,
                                  IMU and
                                        sensor sway,
                                                   data,a that
                                                           fair implicitly
                                                                   prediction of     fallinto
                                                                                 takes      risk can
                                                                                                 account be postural
                                                                                                            achieved. In       the future,
                                                                                                                          stability,  gait, we
                                                                                                                                             stridewill     be testing
                                                                                                                                                       length,
                                         our a fair
                                  and sway,    approach        in larger
                                                        prediction           cohorts.
                                                                         of fall          Additionally,
                                                                                 risk can be      achieved. In wethe will   be we
                                                                                                                        future, exploring
                                                                                                                                       will bethe    application
                                                                                                                                                 testing    our     of
                                         Generative
                                  approach in             Adversarial
                                                   larger cohorts.           Networks we
                                                                          Additionally,      (GAN)  willfor
                                                                                                          be the   enrichment
                                                                                                             exploring      the of     the faller
                                                                                                                                 application     of class
                                                                                                                                                     Genera-  in order
                                  tive to    obtain more
                                       Adversarial      Networks balanced(GAN) datasets
                                                                                   for thefor    training and
                                                                                              enrichment            synthetic
                                                                                                               of the            datain order
                                                                                                                        faller class     generation       techniques
                                                                                                                                                    to obtain
                                  more like    SMOTE
                                         balanced           (Synthetic
                                                       datasets              Minority
                                                                    for training          Over-sampling
                                                                                    and synthetic                Technique). We
                                                                                                          data generation      techniquesbelieve
                                                                                                                                               likeourSMOTEresults are
                                  (Synthetic Minority Over-sampling Technique). We believe our results are promising and and
                                         promising       and     could    contribute     to   fall  prevention      enhancement.         This   is  important
                                  couldwould       directly
                                          contribute           benefit
                                                          to fall         older adults
                                                                     prevention            themselves,This
                                                                                     enhancement.           as those    at risk of falling
                                                                                                                  is important      and wouldwoulddirectly
                                                                                                                                                        be identified
                                         beforehand
                                  benefit older     adultsand it     would as
                                                              themselves,      enable
                                                                                   thosetheat risk
                                                                                               relevant    entities to
                                                                                                       of falling         consider
                                                                                                                    would be           proper measures
                                                                                                                                  identified    beforehandand to
                                         implement
                                  and it would      enablestrategies      to prevent
                                                                the relevant              falling,
                                                                                 entities to          ultimately
                                                                                                  consider    proper  preserving
                                                                                                                         measurestheir and toindependence
                                                                                                                                                 implement and
                                         reducing
                                  strategies           medical
                                               to prevent           care costs.
                                                               falling,    ultimately preserving their independence and reducing med-
                                  ical care costs.
                                         5. Conclusions
                                             Falls are among the most significant challenges faced by older adults, making their
                                  5. Conclusions
                                        assessment and prevention critically important, particularly in the current demographic
                                       Falls are among the most significant challenges faced by older adults, making their
                                        context. Although several tools exist for assessing fall risk, these are typically based on
                                  assessment and prevention critically important, particularly in the current demographic
                                        time, distance, or visual observation metrics. In fact, these tools are of qualitative nature

Bioengineering 2024, 11, 1000                                                                                                       12 of 14


                                  helping to guide the medical staff assessment. Our approach, by contrast, leverages the
                                  large amount of information that can be collected by wearable IMU sensors on individ-
                                  uals being studied while performing the Timed Up and Go (TUG) test; specifically, we
                                  can use the raw data from the accelerometer, gyroscope, and magnetometer. Given the
                                  relatively high sampling frequency (100 samples per second), the duration of the test, and
                                  the three-dimensional data produced by each of the three sensors, a substantial volume of
                                  data are generated. The most effective way to analyze such data, with current technological
                                  capabilities, is through the application of artificial intelligence. The study includes 106 sub-
                                  jects (68 women and 38 men) from 9 long-term nursing homes (LTNHs). Upon comparing
                                  traditional machine learning methods with deep learning approaches, it was found that
                                  the latter yielded the most accurate results, specifically the BLSTM algorithm. We believe
                                  that our method complements traditional fall risk screening methods and adds valuable
                                  information to improve the assessment of subjects with frailty.

                                  Author Contributions: Conceptualization, J.M., G.G., C.R.-P. and M.G.; methodology, J.M.; software,
                                  J.M.; validation, G.G., C.R.-P. and B.S.; investigation, G.G. and B.S.; resources, C.R.-P. and B.S.; data
                                  curation, J.M.; writing—original draft preparation, J.M.; writing—review and editing, M.G., C.R.-P.
                                  and B.S.; visualization, J.M.; supervision, M.G.; funding acquisition, M.G. All authors have read and
                                  agreed to the published version of the manuscript.
                                  Funding: The Grupo de Inteligencia Computacional, Universidad del Pais Vasco, UPV/EHU, received
                                  research funds from the Basque Government from 2007 until 2025. The current code for the grant is
                                  IT1689-22. The Spanish MCIN (Ministerio de Ciencia, Innovación y Universidades) has also granted
                                  the authors a research project under code PID2020-116346GB-I00.
                                  Institutional Review Board Statement: The study was conducted in accordance with the Declaration
                                  of Helsinki and approved by the Committee on Ethics in Research at the University of the Basque
                                  Country (Humans Committee Code M10/2016/105). for studies involving humans.
                                  Informed Consent Statement: Informed consent was obtained from all subjects involved in the study.
                                  Data Availability Statement: Restrictions apply to the availability of these data. Data were obtained
                                  from Matia Fundazioa and are available from the authors with the permission of Matia Fundazioa.
                                  Acknowledgments: We would like to thank the staff of the centers that participated in our study
                                  for their support: Bermingham, Lamourous, Julián Rezola (Matia Fundazioa), Anaka, Betharram
                                  (Fundación Caser), Villa Sacramento, Berra (DomusVi), Zorroaga, and San Markosene. We especially
                                  thank the study participants and their families for their participation and cooperation.
                                  Conflicts of Interest: The authors declare no conflicts of interest. The funders had no role in the design
                                  of the study; in the collection, analyses, or interpretation of data; in the writing of the manuscript; or
                                  in the decision to publish the results.

References
1.    Kannus, P.; Parkkari, J.; Koskinen, S.; Niemi, S.; Palvanen, M.; Järvinen, M.; Vuori, I. Fall-Induced Injuries and Deaths Among
      Older Adults. JAMA 1999, 281, 1895–1899. [CrossRef] [PubMed]
2.    Sterling, D.A.; O’Connor, J.A.; Bonadies, J. Geriatric Falls: Injury Severity Is High and Disproportionate to Mechanism. J. Trauma
      Inj. Infect. Crit. Care 2001, 50, 116–119. [CrossRef] [PubMed]
3.    Ashraf, S.; Ahmed, T. Sagacious Intrusion Detection Strategy in Sensor Network. In Proceedings of the 2020 International
      Conference on UK-China Emerging Technologies (UCET), Glasgow, UK, 20–21 August 2020; IEEE: Piscataway, NJ, USA; pp. 1–4.
4.    Eggenberger, P.; Theill, N.; Holenstein, S.; Schumacher, V.; de Bruin, E.D. Multicomponent physical exercise with simultaneous
      cognitive training to enhance dual-task walking of older adults: A secondary analysis of a 6-month randomized controlled trial
      with 1-year follow-up. Clin. Interv. Aging 2015, 10, 1711–1732. [CrossRef] [PubMed]
5.    Hallford, D.J.; Nicholson, G.; Sanders, K.; McCabe, M.P. The Association Between Anxiety and Falls: A Meta-Analysis. J. Gerontol.
      Ser. B Psychol. Sci. Soc. Sci. 2016, 72, gbv160. [CrossRef] [PubMed]
6.    United Nations Department of Economic and Social Affairs. WHO Global Report on Falls Prevention in Older Age; Community
      Health: Geneva, Switzerland, 2007; p. 53. Available online: https://www.who.int/publications/i/item/9789241563536 (accessed
      on 29 September 2024).
7.    Rubenstein, L.Z. Falls in older people: Epidemiology, risk factors and strategies for prevention. Age Ageing 2006, 35 (Suppl. S2),
      ii37–ii41. [CrossRef]

Bioengineering 2024, 11, 1000                                                                                                         13 of 14


8.    Florence, C.S.; Bergen, G.; Atherly, A.; Burns, E.; Stevens, J.; Drake, C. Medical costs of fatal and nonfatal falls in older adults. J.
      Am. Geriatr. Soc. 2018, 66, 693–698. [CrossRef] [PubMed]
9.    Scott, V.; Votova, K.; Scanlan, A.; Close, J. Multifactorial and functional mobility assessment tools for fall risk among older adults
      in community, home-support, long-term and acute care settings. Age Ageing 2007, 36, 130–139. [CrossRef]
10.   Perell, K.L.; Nelson, A.; Goldman, R.L.; Luther, S.L.; Prieto-Lewis, N.; Rubenstein, L.Z. Fall Risk Assessment Measures: An
      Analytic Review. J. Gerontol. Ser. A Biol. Sci. Med. Sci. 2001, 56, M761–M766. [CrossRef]
11.   Mathias, S.; Nayak, U.S.; Isaacs, B. Balance in elderly patients: The ‘get-up and go’ test. Arch. Phys. Med. Rehabil. 1986, 67,
      387–389.
12.   Tinetti, M.E.; Williams, T.F.; Mayewski, R. Fall risk index for elderly patients based on number of chronic disabilities. Am. J. Med.
      1986, 80, 429–434. [CrossRef]
13.   Oliver, D.; Britton, M.; Seed, P.; Martin, F.C.; Hopper, A.H. Development and evaluation of evidence based risk assessment tool
      (STRATIFY) to predict which elderly inpatients will fall: Case-control and cohort studies. BMJ 1997, 315, 1049–1053. [CrossRef]
      [PubMed]
14.   Csuka, M.; McCarty, D.J. Simple method for measurement of lower extremity muscle strength. Am. J. Med. 1985, 78, 77–81.
      [CrossRef] [PubMed]
15.   Bruyere, O.; Wuidart, M.-A.; Di Palma, E.; Gourlay, M.; Ethgen, O.; Richy, F.; Reginster, J.-Y. Controlled whole body vibration to
      decrease fall risk and improve health-related quality of life of nursing home residents. Arch. Phys. Med. Rehabil. 2005, 86, 303–307.
      [CrossRef] [PubMed]
16.   Herman, T.; Giladi, N.; Hausdorff, J.M. Properties of the ‘Timed Up and Go’ Test: More than Meets the Eye. Gerontology 2011, 57,
      203–210. [CrossRef] [PubMed]
17.   Schoene, D.; Wu, S.M.-S.; Mikolaizak, A.S.; Menant, J.C.; Smith, S.T.; Delbaere, K.; Lord, S.R. Discriminative Ability and Predictive
      Validity of the Timed Up and Go Test in Identifying Older People Who Fall: Systematic Review and Meta-Analysis. J. Am. Geriatr.
      Soc. 2013, 61, 202–208. [CrossRef]
18.   Shany, T.; Wang, K.; Liu, Y.; Lovell, N.H.; Redmond, S.J. Review: Are we stumbling in our quest to find the best predictor?
      Over-optimism in sensor-based models for predicting falls in older adults. Healthc. Technol. Lett. 2015, 2, 79–88. [CrossRef]
19.   Hamacher, D.; Singh, N.; Van Dieën, J.; Heller, M.; Taylor, W. Kinematic measures for assessing gait stability in elderly individuals:
      A systematic review. J. R. Soc. Interface 2011, 8, 1682–1698. [CrossRef]
20.   Howcroft, J.; Kofman, J.; Lemaire, E.D. Review of fall risk assessment in geriatric populations using inertial sensors. J. Neuroeng.
      Rehabil. 2013, 10, 91. [CrossRef]
21.   Howcroft, J.; Kofman, J.; Lemaire, E.D. Prospective Fall-Risk Prediction Models for Older Adults Based on Wearable Sensors.
      IEEE Trans. Neural Syst. Rehabil. Eng. 2017, 25, 1812–1820. [CrossRef]
22.   Cimolin, V.; Cau, N.; Albedi, G.M.; Aspesi, V.; Merenda, V.; Galli, M.; Capodaglio, P. Do wearable sensors add meaningful
      information to the Timed Up and Go test? A study on obese women. J. Electromyogr. Kinesiol. 2019, 44, 78–85. [CrossRef]
23.   Tang, P.; Wang, H.; Kwong, S. G-MS2F: GoogLeNet based multi-stage feature fusion of deep CNN for scene recognition.
      Neurocomputing 2017, 225, 188–197. [CrossRef]
24.   Shin, H.-C.; Roth, H.R.; Gao, M.; Lu, L.; Xu, Z.; Nogues, I.; Yao, J.; Mollura, D.; Summers, R.M. Deep Convolutional Neural
      Networks for Computer-Aided Detection: CNN Architectures, Dataset Characteristics and Transfer Learning. IEEE Trans. Med.
      Imaging 2016, 35, 1285–1298. [CrossRef] [PubMed]
25.   Rao, Q.; Frtunikj, J. Deep learning for self-driving cars. In Proceedings of the 1st International Workshop on Software Engineering
      for AI in Autonomous Systems—SEFAIS ’18, New York, NY, USA, 27 May–3 June 2018; ACM Press: Cambridge, MA, USA, 2018;
      pp. 35–38. [CrossRef]
26.   Tamilselvan, P.; Wang, P. Failure diagnosis using deep belief learning based health state classification. Reliab. Eng. Syst. Saf.
      2013, 115, 124–135. Available online: https://www.sciencedirect.com/science/article/pii/S0951832013000574 (accessed on 19
      July 2019). [CrossRef]
27.   Dehzangi, O.; Taherisadr, M.; ChangalVala, R. IMU-Based Gait Recognition Using Convolutional Neural Networks and Multi-
      Sensor Fusion. Sensors 2017, 17, 2735. [CrossRef]
28.   Nweke, H.F.; Teh, Y.W.; Mujtaba, G.; Al-Garadi, M.A. Data fusion and multiple classifier systems for human activity detection
      and health monitoring: Review and open research directions. Inf. Fusion 2019, 46, 147–170. [CrossRef]
29.   Hannink, J.; Kautz, T.; Pasluosta, C.F.; Gasmann, K.-G.; Klucken, J.; Eskofier, B.M. Sensor-Based Gait Parameter Extraction with
      Deep Convolutional Neural Networks. IEEE J. Biomed. Health Inform. 2017, 21, 85–93. [CrossRef]
30.   Ravi, D.; Wong, C.; Lo, B.; Yang, G.-Z. A Deep Learning Approach to on-Node Sensor Data Analytics for Mobile or Wearable
      Devices. IEEE J. Biomed. Health Inform. 2017, 21, 56–64. [CrossRef] [PubMed]
31.   Aicha, A.N.; Englebienne, G.; Van Schooten, K.S.; Pijnappels, M.; Kröse, B. Deep Learning to Predict Falls in Older Adults Based
      on Daily-Life Trunk Accelerometry. Sensors 2018, 18, 1654. [CrossRef]
32.   Strini, V.; Schiavolin, R.; Prendin, A. Fall Risk Assessment Scales: A Systematic Literature Review. Nurs. Rep. 2021, 11, 430–443.
      [CrossRef]
33.   Rezola-Pardo, C.; Arrieta, H.; Gil, S.M.; Zarrazquin, I.; Yanguas, J.J.; López, M.A.; Irazusta, J.; Rodriguez-Larrad, A. Comparison
      between multicomponent and simultaneous dual-task exercise interventions in long-term nursing home residents: The Ageing-
      ONDUAL-TASK randomized controlled study. Age Ageing 2019, 48, 817–823. [CrossRef]

Bioengineering 2024, 11, 1000                                                                                                     14 of 14


34.   Rezola-Pardo, C.; Rodriguez-Larrad, A.; Gomez-Diaz, J.; Lozano-Real, G.; Mugica-Errazquin, I.; Patiño, M.J.; Bidaurrazaga-Letona,
      I.; Irazusta, J.; Gil, S.M. Comparison Between Multicomponent Exercise and Walking Interventions in Long-Term Nursing Homes:
      A Randomized Controlled Trial. Gerontologist 2020, 60, 1364–1373. [CrossRef] [PubMed]
35.   Rezola-Pardo, C.; Arrieta, H.; Gil, S.M.; Yanguas, J.J.; Iturburu, M.; Irazusta, J.; Sanz, B.; Rodriguez-Larrad, A. A randomized
      controlled trial protocol to test the efficacy of a dual-task multicomponent exercise program in the attenuation of frailty in
      long-term nursing home residents: Aging-ONDUAL-TASK study. BMC Geriatr. 2019, 19, 6. [CrossRef]
36.   American Geriatrics Society; Geriatrics Society; American Academy of Orthopaedic Surgeons Panel on Falls Prevention. Guideline
      for the Prevention of Falls in Older Persons. J. Am. Geriatr. Soc. 2001, 49, 664–672. [CrossRef]
37.   Luque, A.; Carrasco, A.; Martín, A.; de las Heras, A. The impact of class imbalance in classification performance metrics based on
      the binary confusion matrix. Pattern Recognit. 2019, 91, 216–231. [CrossRef]
38.   McHugh, M.L. The Chi-square test of independence. Biochem. Med. 2013, 23, 143–149. [CrossRef]
39.   Mallat, S. Group Invariant Scattering. Commun. Pure Appl. Math. 2012, 65, 1331–1398. [CrossRef]
40.   Alom, M.Z.; Taha, T.M.; Yakopcic, C.; Westberg, S.; Sidike, P.; Nasrin, M.S.; Hasan, M.; Van Essen, B.C.; Awwal, A.A.S.; Asari, V.K.
      A State-of-the-Art Survey on Deep Learning Theory and Architectures. Electronics 2019, 8, 292. [CrossRef]
41.   Avilés-Cruz, C.; Ferreyra-Ramírez, A.; Zúñiga-López, A.; Villegas-Cortéz, J. Coarse-Fine Convolutional Deep-Learning Strategy
      for Human Activity Recognition. Sensors 2019, 19, 1556. [CrossRef]
42.   Ordóñez, F.J.; Roggen, D. Deep Convolutional and LSTM Recurrent Neural Networks for Multimodal Wearable Activity
      Recognition. Sensors 2016, 16, 115. [CrossRef]
43.   Bruna, J.; Mallat, S. Invariant Scattering Convolution Networks. IEEE Trans. Pattern Anal. Mach. Intell. 2013, 35, 1872–1886.
      [CrossRef]
44.   Ullah, A.; Ahmad, J.; Muhammad, K.; Sajjad, M.; Baik, S.W. Action Recognition in Video Sequences using Deep Bi-Directional
      LSTM with CNN Features. IEEE Access 2017, 6, 1155–1166. [CrossRef]

Disclaimer/Publisher’s Note: The statements, opinions and data contained in all publications are solely those of the individual
author(s) and contributor(s) and not of MDPI and/or the editor(s). MDPI and/or the editor(s) disclaim responsibility for any injury to
people or property resulting from any ideas, methods, instructions or products referred to in the content.
```
