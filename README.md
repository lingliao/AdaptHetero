# A Machine Learning Interpretation-Guided Framework for Subpopulation-Aware Model Adaptation in Electronic Health Records (AdaptHetero)


Manuscript can be accessed from [here](https://arxiv.org/abs/2507.21197).

## Overview

Machine learning interpretation  has primarily been leveraged to foster clinician trust and extract insights from electronic health records (EHRs), rather than to guide subpopulation-specific, operationalizable modeling strategies. To bridge this gap, we propose AdaptHetero, a novel machine learning interpretation-driven framework that translates interpretability insights into actionable guidance for patient cluster-aware model evaluation and potential cluster-specific model retraining. Evaluated on three large-scale EHR datasets—GOSSIS-1-eICU, WiDS, and Mass General Brigham health system—AdaptHetero consistently uncovers heterogeneous model behaviors across patient clusters, with AUPRC ranging from 0.014 to 0.640 for ICU mortality, 0.019 to 0.559 for in-hospital death, and 0.297 to 0.448 for hospital-onset infection. Furthermore, retraining cluster-specific models improved predictive performance for several subpopulations. These results demonstrate the potential of the framework to enable more robust, equitable, and context-aware clinical deployment of predictive models.


Below conatins the overview of the framwwork:

<div style="text-align: center;">
  <img width="343" height="195" alt="image" src="https://github.com/user-attachments/assets/7aff2378-e781-4828-94d7-924635073cab" />
</div>

Step 1: Cluster identification and evaluation. The full dataset is randomly divided into training (80%) and testing (20%) sets. An initial XGBoost model is trained on the training set, and SHAP values computed from this model serve as feature representations for unsupervised clustering, resulting in patient clusters within the training data. For the testing set, SHAP values are computed using the same trained model, and the learned clustering structure is then applied to the testing set SHAP representations, enabling patient cluster-specific evaluation using the AUPRC (area under the precision–recall curve). Step 2: Cluster-specific model retraining. For all non-empty patient clusters containing more than 500 training samples and both positive and negative labels, separate models are retrained on the corresponding cluster-specific training sets. Step 3: Evaluation of retrained models. The AUPRC and cluster-level SHAP patterns from the retrained models are compared with those obtained from the initial full-dataset model on the testing set. All subpopulation identification procedures are performed exclusively on the training set to prevent post hoc analysis and data leakage.


## Methods

WiDS_19.ipynb contains a clean, end-to-end example script showing how to run the full pipeline on the WiDS-19 (hospital mortality) dataset, written in a reproducible style.

More to come soon...


## Dataset Availability
The data utilized in this study is downloaded from [here]( https://physionet.org/).

## We appreciate you attention.

**AI for IMPROVEMENT and for EVERYONE.**
