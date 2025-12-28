# An MLI-Guided Framework for Subgroup-Aware Modeling in Electronic Health Records (AdaptHetero)

Manuscript can be accessed from [here](https://arxiv.org/abs/2507.21197).

## Overview

Machine learning interpretation (MLI) has primarily been leveraged to foster clinician trust and extract insights from electronic health records (EHRs), rather than to guide subgroup-specific, operationalizable modeling strategies. To bridge this gap, we propose AdaptHetero, a novel MLI-driven framework that transforms interpretability insights into actionable guidance for tailoring model training and evaluation across subpopulations. Evaluated on three large-scale EHR datasets—GOSSIS-1-eICU, WiDS, and MIMIC-IV—AdaptHetero consistently uncovers heterogeneous model behaviors in predicting ICU mortality, in-hospital death, and hidden hypoxemia. Integrating SHAP-based interpretation with unsupervised clustering, AdaptHetero identifies clinically meaningful, subgroup-specific characteristics, improving predictive performance across many subpopulations (with gains up to 185.71% in AUPRC) while proactively flagging potential risks in others. These results highlight the framework’s promise for more robust, equitable, and context-aware clinical deployment.


Below conatins the overview of the framwwork:

<div style="text-align: center;">
  <img width="343" height="195" alt="image" src="https://github.com/user-attachments/assets/7aff2378-e781-4828-94d7-924635073cab" />
</div>

Input data are split into training and testing sets. After initial model training, patient subgroups are derived from the training data by integrating SHAP-based interpretation with unsupervised clustering. These cluster assignments are then propagated to the testing data, enabling subgroup-specific performance evaluation.  For all non-empty combinations of cluster-defined subgroups containing both positive and negative cases, separate models are retrained using the corresponding training data and evaluated on the matching test data. Following retraining, subgroup-specific SHAP values are computed on the testing data and compared with initial SHAP interpretations to assess clustering quality and evaluate cluster-wise predictive performance between the original and retrained models. This procedure thereby forms a closed-loop evaluation framework that links subgroup discovery, model refinement, and interpretability analysis. Final predictive performance is assessed on the testing data using AUPRC (Area Under the Precision–Recall Curve), while SHAP representations are analyzed to validate model behavior and heterogeneity across subpopulations.


## Dataset Availability
The data utilized in this study is downloaded from [here]( https://physionet.org/).

## We appreciate you attention.

**AI for IMPROVEMENT and for EVERYONE.**
