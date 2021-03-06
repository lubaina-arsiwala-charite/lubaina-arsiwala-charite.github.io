# lubaina-arsiwala-charite.github.io
# Artificial intelligence in dental research: A checklist for authors and reviewers
![Prof. Schwendicke](https://www.google.com/search?q=charite+dept+of+oral+diagnostics&rlz=1C1CHBF_deDE935DE935&sxsrf=ALeKk025TjZH1r3cXTykeG9iqeCyL_5nzg:1611907431318&source=lnms&tbm=isch&sa=X&ved=2ahUKEwj1seqO18DuAhUID-wKHZbrBMsQ_AUoAXoECAcQAw&biw=1707&bih=803&dpr=1.13#imgrc=5aQDdWsYMjS-_M.jpeg)
*Planning and conducting*
1. *Study Goal*: Researchers should early on define the relevance, scope and meaning of
the AI application they aim to develop or validate. The pitfalls in methodology when using
AI methods, especially towards data and technical requirements (see below), should be
kept in mind early on. Also, the end-users (patients or dentists) should be considered
when designing the study, as should be regulatory requirements, ethics and data
protection.
2. Study Focus: A clear focus on the study aims should be defined, e.g. what goal does the
research have (developing a new or validating an existing model, diagnostics or
prognostics etc.).
3. Data: A major aspect when planning AI studies is data; especially in dentistry, datasets
are oftentimes small and imbalanced (i.e. one class, like a pathology, is
underrepresented, which makes training but also evaluation of AI models more difficult
and needs to be addressed, see below). Datasets should be as heterogenous as
possible for the model to be as generalizable as possible, and this should be planned to
be demonstrated (see below). Generally, researchers should consider the target
population on which they envisage their model to be applied on, and critically compare
the dataset they plan to train and to test their model on against that population.
4. Study Aim: Researchers should have a clear idea if their study is exploratory or
hypothesis-testing: Clearly, there is also a need for exploratory studies, which generate
hypotheses and open up new avenues, while a full sample size estimation is required
when wanting to demonstrate any value of the model with statistical certainty.
5. Reference Test: A major difficulty is the construction of the reference test (i.e. the labels
of the data to be learnt and tested on) in the absence of a hard “gold standard” (e.g.
histological assessment). Instead, dental researchers are oftentimes forced to use
multiple human annotators to independently label the data, thereby generating a “fuzzy”
gold standard. Depending on the study’s aim, a clear case definition and calibration of
annotators might be desired or not. The construction of the single label from this fuzzy
data needs further considerations, e.g. researchers may use the majority votes. Ideally,
if multiple data sources are available, they may be used to triangulate. Last, noise and
uncertainty may be to a certain extend acceptable in the training dataset, but hurtful and
possible lead to bias in the test dataset.
6. Clustering: When feeding annotated data into the model, it is relevant to consider the
specifics of dental data: Often, multiple datapoints (images, clinical assessment) are
available from the same patient, either from the same time point (e.g. bitewing
radiograph pairs, periapical radiographs used for periodontal status) or over different
time points (during follow-up). The associated clustering may be used to add information
to the model and provide new insights, while it is relevant to not spread data from the
same patient between training and test dataset to avoid “data snooping bias”.
7. Test dataset: When testing the model, it is most relevant to not only report on validation
data (i.e. data the model was exposed to during the training process) but a separate
hold-out test dataset which the model has never seen, or even better a completely
external dataset (which is the only option to demonstrate generalizability). Researchers
should consider this during planning their study. Reporting only data from within-sample
validation is insufficient. Validation that follows a k-fold cross-validation approach may
be taken into consideration but claims of generalizability should be avoided.
8. Computational resource: Researchers should, before engaging into AI research,
consider the computational resources, which are a major constrain especially when
dealing with image data, large datasets or complex models. Researchers should be
aware that the available computational resources may restrict the resolution of the
images that are used for training, with features that are clearly identifiable at the original
scale possibly being lost during preprocessing. Further, iterative hyperparameter tuning
(see below) is computationally expensive and time-consuming, which should be
considered, too.
9. Comparator: The model should be compared against relevant alternatives. These could
be an independent group of dental examiners, possibly of different experience (to reflect
the usefulness of the model in different groups) or against other accepted imagery or
clinical tests. For such comparisons, relevant outcomes and outcome metrics should be
used. Here, it is important to bridge the gap between dental research and technical
disciplines. While the former often reports on accuracy metrics (which are not all useful
in imbalanced datasets, see below), the latter considers F1-score or other metrics (which
are more robust, but not interpretable from a medical perspective). This aspect becomes
even more important when applying object detection or segmentation models.
Commonly applied metrics such as (weighted) average precision or intersection over
union are very domain specific so that concepts to convey them into the medical/dental
research domain are warranted [16]. Ideally, an outcome set which reflects not only on
the model’s accuracy, but also further aspects should be considered, again keeping in
mind who will employ, commission, receive or pay for the application which may be
developed using the model.

Reporting

A range of items should be reported. Note that it may not be necessary to expand on each item
in each study report, but that all items should be considered and, if not presented, this absence
should be justified.

10. Title: The title should clearly lay out that any kind of AI (deep learning, shallow machine
learning, or more specifically the type of model like convolutional neural networks or
random forests, among others) was used. Moreover, it should mention the study’s focus
(diagnostic/prediction, development/validation), the clinical problem (e.g. caries
detection on bitewings etc.) and the main outcome metric (accuracy, cost-effectiveness
etc.)
11. Abstract: The abstract should present a structured summary of the study’s aim, methods,
results, and conclusion. The abstract should stand for itself and should be
understandable without reading the main manuscript. That also means that the used
data (main characteristics, source of origin, type of sampling, partitioning into training,
validation and testing datasets), the model and outcome metrics and the statistical
analysis that was performed should be provided. The results section should provide full
metrics, including measures of variance, for the primary outcome on the test (not only
the training) dataset, and allow for any comparisons against alternatives.
12. Introduction: The introduction should briefly sum up the dental background of the study,
if there is one, and deduce the need for an AI solution. It should be made clear if there
is a clinical, a research or a teaching problem. The introduction should then lay out the
achievements and limitations made in this direction so far to provide a rationale for the
study, its goals, and anticipated impact. It should be made clear in this section if the
problem is of diagnostic or prognostic nature and if the study aims to explore new AI
applications or validate existing ones. The former study type will be different in its setup
from the latter type, where finally the introduction will provide one or more hypotheses to
be tested and for which a sample size estimation (for the test dataset) will be needed
(see above and below).
13. Study Design: It is advisable to provide a short overview about the study design. This
should include an overview about the study goal (will the model be used for detection,
staging, monitoring, surveillance, prediction, or prognosis), data, its origin and sampling
(retro- or prospective), modeling techniques, evaluation and scope
(exploratory/hypothesis-testing, for the latter: aiming to demonstrate superiority or noninferiority).
If the methods part cannot, due to space restrictions, contain sufficient details
for full replication, an appendix may be used and introduced early on. A possible
registration of the study should be provided here, as should any definitions or terms used
throughout the study. These definitions are relevant to consider given that different terms
are used in the dental versus the technical disciplines; it is advisable to clarify them early
on (e.g. in dental and, generally, medical research the model would be seen as index
test which is tested against a reference test; in the technical disciplines, these terms are
not used; similarly, the model aims – classification, detection, segmentation – should be
briefly mentioned and defined for clarity reasons). If a reporting checklist like this one or
any other guidance document was used and adhered to, this may be reported here, too.
14. Data: As data are the main component of any AI model, this section is particularly
relevant. The source of data for training, validation and testing (primary care, secondary
care, general population) including the exact location of each data source, the timeframe
of the sampling and in- or exclusion criteria should be defined (see next point). The data
should be critically compared against the characteristics of the target population to help
the reader gauge the generalizability and applicability (this should be taken up in the
discussion). The heterogeneity of the data and potential sources of bias (especially
concerning age, sex, ethnicity) should be explored. It should be made clear if any of
these data had been used for other studies before. Ethical aspects (including ethical
approval, informed consent) and data protection aspects (e.g. employed strategies for
de-identification) should be laid out. Ideally, the data should be provided in a repository.
Notably, any code (see below) should so, too (e.g. GitHub, GitLab, etc.).
Dental datasets are oftentimes relatively small and narrow, which is why dental
researchers have used within-sample validation as one means for demonstrating the
value of the developed AI models. If any kind of hold-out, external or temporally separate
test set has been used, this should be clarified, as should be the partitioning between
training, validation and test dataset. When partitioning data, it should be clarified how
repeated data from the same patient from the same or different time points was
managed, as ideally the disjoint should be on the patient level so that data of the same
patient do not appear in each partition. Researchers should indicate if there are any
systematic differences between the data in each partition, and if so, why. A tabularization
of the different partitions’ characteristics can be helpful. If any kind of covariates were
used for modelling, it should be made clear here which ones, and when and how they
were collected and measured.

a. The identification, recruitment and inclusion of eligible data should be clarified.
Inclusion and exclusion criteria, specifically the case definition (symptoms,
characteristics) or criteria related to data type or quality, the data source location
and setting, the source (for imagery, the technical characteristics including the
machines used to generate images, acquisition parameters, reformat
parameters) should be made clear. The study dates, including start of accrual;
end of accrual; and, if applicable, end of follow-up, should be specified. The
sampling strategy (consecutive, random, or convenience) should be laid out and
justified. The number of centers, patients, datapoints and any meta-data should
be presented to gauge the representativeness of the data.

b. It is relevant to consider if data protections standards in the US (HIPAA) or the
EU (GDPR), or other relevant jurisdictions have been fulfilled, including
appropriate institutional review if required. De-identification of dental datasets
(especially imagery) is often considered difficult., e.g. clinical reports or facial
profiles can allow identification.

c. In almost all studies the raw data need to be extracted, transposed and loaded
into machine-readable formats. Often the data originally stems from patient
management systems or image databases (e.g. PACS). Hence, data extraction
and preprocessing steps (manual or automated) should be described in detail.
For imagery, elaborate on the use of normalization, change in bit depth,
rescaling, cropping, compression, standardization, anonymization and file types.
Include information (source and version number) on leveraged software, libraries,
or any other tools.

d. If any data were missing (e.g. covariates etc.), it should be made clear how they
were handled. Researchers should consider the bias that missing, replaced or
imputed data might introduce.

15. Reference test: A major difficulty in AI studies is the construction of the reference test.
The case definition and any kind of grading schemes for sub-types should be defined, if
possible using accepted disease ontologies. The test threshold (positive cutoff), if
defined, needs to be explained and justified, as it has an impact on the model and
possibly also comparative dentists’ accuracy. It should also be made clear if this was all
specified upfront or adjusted post hoc. It should be explained whether any clinical
information was available to the assessors of the reference standard, or if any preannotation
by a model was performed (so-called human-in-the-loop approach). Both can
significantly impact on the reference test conduct. If any kind of existing label was used
(e.g. from free-text imaging reports, electronic health, or existing models), researchers
need to lay out how these labels had been generated, and need to gauge the risk of
misclassification bias, unmeasured confounding, missing data. If using human
annotators, the number of human annotators and their qualifications should be specified,
as should be any instructions and training given to them, including training materials
(handbooks), which may be provided as a supplement. Researchers should describe
whether annotations were done independently and how any discrepancies among
annotators were resolved, if all annotators assessed each datapoint or not, and how
(software used etc.). If multiple annotators assessed the same datapoint (e.g. an image),
it needs clear reporting of how the fuzzy labels were translated into a single one, e.g. if
majority vote schemes were applied, if experts could override the majority etc.. These
aspects should be especially clarified for the test dataset, as this is used to demonstrate
the value of any AI application, but also to showcase dentists’ performance against the
AI. If available, triangulation with other data or any efforts to provide a hard gold standard
(like histology) should be separately explained here. Researchers should also report on
inter- and intrarater variability, and the steps taken to reduce or mitigate this variability.
16. Sample size: The sample size and how it was determined (sample size estimation)
needs to be fully explained. Specifically, for dental data, researchers should consider
clustering effects (lesion being clustered in teeth, teeth in humans, in centers, and all of
this often in repeated cross-sections). Sample size estimation mainly applies to test
dataset, as any kind of hypothesis testing will be performed on this dataset. Knowing a
priori the sufficient size of the training dataset is difficult. Notably, though, researchers
should consider sensitivity analyses on how data drop or addition to their training dataset
impacts on the model’s performance and generalizability.
17. Model: A complete and detailed description of the model is warranted, allowing to
replicate the employed methods. In particular for neural network models inputs, outputs,
intermediate layers, pooling, normalization, regularization, and activation should be
reported. Cite a reference if the model was previously published. Further, the structure
of the model may be presented in form of a graphical representation in the appendix or
in code as supplemental data. Specify the names and version numbers of all software
libraries, frameworks, and packages used. Further add information on the used
hardware, in particular GPU specifications and used platforms (e.g. cloud vs. local
cluster vs. on premise), possibly in the appendix.

a. In particular for neural networks the parameter initialization is crucial. Name the
applied initialization strategy/distribution (zero, uniform, standard normal, He
[17], Glorot [18] etc). If transfer learning is applied, specify the source of the
starting weights and if there is a combination of initialization and transfer learning,
specify which parts of the model were initialized with which strategies.

18. Training: Describe the training procedures in sufficient detail so that another researcher
could reproduce the training process. Describe which data augmentation techniques
were applied. State how the training process was monitored, and which criteria were
used for stopping the training. List the values of the hyperparameters, describe the
hyperparameter search strategy and provide the ranges of values that were considered.
For neural networks, at least the learning rate schedule, optimization method, batch size,
dropout rates, regularization parameters (if any) and number of epochs should be
provided. Discuss what objective function was applied and why it was selected. If transfer
learning was applied, state which model parameters/layers were frozen and the portion
of the training (e.g. number of epochs) that was affected.
19. Describe the method and model metric to select the final model and evaluate it against
the test set. If using an ensemble of models, describe each model in accordance with
guidelines outlined above. Describe how the component models were weighted and/or
combined.
20. Evaluation: Researchers should describe the outcome and outcome metric(s) used to
measure the model’s performance, defining the primary outcome and metric and relating
it to the outlined clinical/teaching/research problem. Ideally, they should not only report
on accuracy, but consider outcomes relevant for decision making, applicability etc., as
well. It should be made clear how any superiority over the current standards or
alternatives is demonstrated (or not) and, if available, how the developmental and
application costs may be justified thereby. The involvement of the public and patients
should be considered when discussing outcome in the absence of any core outcome set.
21. Lay out out how uncertainty of the performance metrics values was assessed, how any
comparisons between groups were done and how robust these comparisons were, for
example by subgroup analyses of tooth groups, dentitions, patient risk groups, or data
sources (from different centers or machinery). If comparing the AI model against
individual dentists, the dentists’ characteristics should be provided here, too.
22. If feasible, researchers should lay out how the explainability, trustworthiness, and
transparency of the model was assessed. There are an increasing number of
applications towards “explainable AI” available [19]. This is also increasingly seen as a
regulatory requirement for any kind of clinical application later on.
23. Results: The flow of data, including those in- and excluded, and data partitions into
training, validation and test dataset should be clarified; a flowchart may be helpful. The
sample should be characterized demographically, but also towards the prevalence of the
condition of interest and the population’s risk profile to gauge its representativeness for
the target population. If subgroups of severity have been defined, these should be
characterized, too.

a. The performance metrics on all data partitions should be provided. The final
model’s performance on the test partition should be provided in detail and
benchmarked against current technical standards or individual dentists.
Estimates of variance like 95% confidence intervals or nonparametric estimates
from bootstrap samples should be reported to gauge uncertainty. If useful,
graphical displays like the Receiver Operating Characteristics Curves (ROC) or
the Precision Recall curve [20] could be used. Results on subgroups should be
presented. If possible, any accuracy estimates should be translated into
meaningful measures of decision making (e.g. sensitivity, specificity, positive and
negative predictive value), and relative estimates may be translated into absolute
ones additionally. Researchers should further provide information to understand
incorrect predictions to help readers better understand the strengths and
limitations of the model. Results from any explainability analyses should be
presented and explored (e.g. as heatmaps, see above).

24. Discussion: As mostly recommended, we also see four aspects which should be
provided; a summary, a strengths and limitations sections, a section on findings and their
implications, and one on future directions. The results should be briefly summed up and
contrasted against the study aim and hypothesis.

a. The study’s strengths, but more so limitations, especially towards data, the
reference test, the applied metrics as well as associated biases, uncertainty,
generalizability and robustness should be discussed. Necessary comparison with
other studies should be drawn and the findings interpreted, for example as to
their relevance for practice, including the potential clinical application of the AI
model. Possible subsequent steps that one might take to build upon the provided
results should be summed up and aspects which may hamper or facilitate
successful translation into practice, research or teaching should be discussed.

25. Other Information: Here, recommendations towards authorship and registration
according to the International Committee of Medical Journal Editors (ICMJE) should be
followed. The full study protocol may be linked in here, too. Sources of funding and the
role of the funders as well as potential conflicts of interest should be explained.
