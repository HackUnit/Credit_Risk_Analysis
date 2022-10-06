# Credit_Risk_Analysis


## Overview of the analysis:

For this analysis the goal was to solve a real-world challenge of credit card risk. A credit card dataset from LendingClub (a lending services company) was used and different techniques employed to train and evaluate models utilizing the unbalanced classes pulled from the dataset. Specifically, the Imbalanced-learn and Scikit-learn libraries were used to build and evaluate these models through resampling.

In the actual analysis a variety of model techniques were used. This started with oversampling the data using the RandomOverSampler and SMOTE algorithms. To further evaluate models to get the best one to predict credit risk the ClusterCentroids algorithm was used to then under sample the data. Next, over and under sampling were combined using the SMOTEENN algorithm as a credit risk prediction model. Finally, two models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, were used to predict credit risk. The performance of each of these models was evaluated and a recommendation written on whether any of the models could be used to predict credit risk.

<br>

## Results:

To begin the analysis, the balanced accuracy scores, precision and recall scores of each machine learning model will be presented with a brief summarization of each score. While both class scores of low and high risks are printed in the screenshots, the written focus will be on the ability of the models to predict high credit risk. Following will then be a written analysis that will use this collected information to make a summarized deduction on the accuracy of these models and which (if any) model would be best used by creditors to predict high credit risk.

### Oversampling

- Naive Random Oversampling:
This model gave a balanced accuracy score of ~64% and the high-risk class reported a 1% precision and 63% recall score.

![Naive Random Oversampling Accuracy Score](Resources/images/NROAS.png)
<br>
<sub>Naive Random Oversampling Accuracy Score</sub>

![Naive Random Oversampling Classification Report](Resources/images/NROCR.png)
<br>
<sub>Naive Random Oversampling Classification Report</sub>
<br>
<br>

- SMOTE Algorithm:
This model also gave a balanced accuracy score of ~64% and similarly the high-risk class reported a 1% precision and 63% recall score.

![SMOTE Accuracy Score](Resources/images/SAS.png)
<br>
<sub>SMOTE Accuracy Score</sub>

![SMOTE Classification Report](Resources/images/SCR.png)
<br>
<sub>SMOTE Classification Report</sub>
<br>
<br>

### Undersampling

- Cluster Centroids:
This under sampling technique gave a balanced accuracy score of ~64% and the high-risk class reported a 1% precision and 61% recall score.

![Cluster Centroids Accuracy Score](Resources/images/CCAS.png)
<br>
<sub>Cluster Centroids Accuracy Score</sub>

![Cluster Centroids Classification Report](Resources/images/CCCR.png)
<br>
<sub>Cluster Centroids Classification Report</sub>
<br>
<br>

### Combination (Over and Under) Sampling

- SMOTEENN Algorithm:
In combining over and under sampling this technique gives us a balanced accuracy score of ~53% and the high-risk class reported a 1% precision, and a 71% recall score.

![SMOTEENN Accuracy Score](Resources/images/SMAS.png)
<br>
<sub>SMOTEENN Accuracy Score</sub>

![SMOTEENN Classification Report](Resources/images/SMCR.png)
<br>
<sub>SMOTEENN Classification Report</sub>
<br>
<br>

### Ensemble Learners

- Balanced Random Forest Classifier:
Switching to ensemble learning models we see an increase in scores across the board. For the Balanced Random Forest Classifier, the balanced accuracy score came out to ~80% and the high-risk class reporting a 4% precision and 71% recall score.

![Balanced Random Forest Classifier Accuracy Score](Resources/images/BRFCAS.png)
<br>
<sub>Balanced Random Forest Classifier Accuracy Score</sub>

![Balanced Random Forest Classifier Classification Report](Resources/images/BRFCCR.png)
<br>
<sub>Balanced Random Forest Classifier Classification Report</sub>
<br>
<br>

- Easy Ensemble AdaBoost Classifier:
This final model gave a balanced accuracy score of ~92% and the high-risk class reported a 7% precision and 91% recall score.

![Easy Ensemble AdaBoost Classifier Accuracy Score](Resources/images/EEACAS.png)
<br>
<sub>Easy Ensemble AdaBoost Classifier Accuracy Score</sub>

![Easy Ensemble AdaBoost Classifier Classification Report](Resources/images/EEACCR.png)
<br>
<sub>Easy Ensemble AdaBoost Classifier Classification Report</sub>
<br>
<br>

## Summary:

As is shown in the graduated progress through each model a definitive verdict can be made that predicting credit risk is an incredibly challenging feat. Specifically with the high-risk side of things. Each model did very well at predicting the low-risk classes, but struggled almost consistently across each model on its precision in predicting the high-risk classes. While this is mostly due to the imbalanced state of the dataset, this essentially means that there are a lot of false positives, and applicants who are not really high risk are getting lumped in with the small number of high-risk applicants.
From a creditor and applicant perspective this could be very damaging for both sides. For the applicants who would be incorrectly identified as high risk, they now not only have a ding on their credit, but no loan despite the reality of their low-risk status. For the creditor; they are losing a decent chunk of possible debtors that would be able to repay what they borrowed. These low-risk applicants are truly the bread and butter for creditors, so models predicting high risk false positives means in turn that the creditors are losing a lot of potentially good customers.
In summary, if a model had to be selected, the Easy Ensemble AdaBoost Classifier would be the best model to choose. But this would not actually be the best recommendation in the end. The recommendation would be to continue working with models until one is able to have less false positives in regards to high risk. This optimal model would instead have a high precision but low recall, which would actually match the dataset better and assure that the majority who are actually low risk not be pooled in with minority of high-risk applicants. With this kind of model, the very few actually high-risk applicants that get labeled as low risk could be easily dealt with further along in the process by the creditor versus losing what would be a good percentage of perfectly good loan applicants from the get go.
