# Credit_Risk_Analysis

# Project Overview:
To apply machine learning to solve a real-world challenge: credit card risk.

## Resources
- Data:  LoansStat-2019
- Software: Python, Anaconda, Jupyter Notebook

## Background
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, a variety of techniques should be employed to train and evaluate models with unbalanced classes. This should be accomplished using imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, data has been oversample using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, combinatorial approach was used, consisting of over- and undersampling using the SMOTEENN algorithm. Next, the two new machine learning models were compared for bias reduction using BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Finally, these model's performance were evlauated and a written recommendation was composed relatig to use for credit risk predication.

## Analysis

**This project consists of three technical analysis deliverables**

**Deliverable 1:** ***Use Resampling Models to Predict Credit Risk***
Using the imbalanced-learn and scikit-learn libraries, three machine learning models were evaluated using resampling to determine which is better at predicting credit risk. Algorithms used:
- *RandomOverSampler*
- *SMOTE algorithm*
- *ClusterCentroids*

### Oversampling
This section compares two oversampling algorithms to determine which algorithm results in the best performance. Data oversampling was achieved using the naive random oversampling algorithm and the SMOTE algorithm. Each algorithm contains the following steps: 
1. View the count of the target classes using Counter from the collections library.
2. Use the resampled data to train a logistic regression model.
3. Calculate the balanced accuracy score from sklearn.metrics.
4. Print the confusion matrix from sklearn.metrics.
5. Generate a classication report using the imbalanced_classification_report from imbalanced-learn.

***Naive Random OverSampling***<br>
![Naive_Oversampling_code](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/Naive_oversampling_code.png)

***SMOTE Oversampling***<br>
![SMOTE_Oversampling_code](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/SMOTE_oversampling_code.png)

### UnderSampling
This section tested an undersampling algorithm to determine which algorithm results in the best performance compared to the oversampling algorithms above. Undersampling was conducted using the Cluster Centroids algorithm by follwoing the steps below:
1. View the count of the target classes using Counter from the collections library.
2. Use the resampled data to train a logistic regression model.
3. Calculate the balanced accuracy score from sklearn.metrics.
4. Print the confusion matrix from sklearn.metrics.
5. Generate a classication report using the imbalanced_classification_report from imbalanced-learn.

![UnderSampling_code](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/UnderSampling_code.png)<br>

## Deliverable 1 Results:
*SMOTE* outperformed both the Naive Random Oversampling and UnderSampling tequniques for accuracy, precision, and recall by approximately 3%.

**Deliverable 2:** ***Use the SMOTEENN Algorithm to Predict Credit Risk***
A combinatorial approach of over- and undersampling techinque using the SMOTEENN algorithm was used to determine if the results from the combinatorial approach are better at predicting credit risk than the resampling algorithms from Deliverable 1.<br>
The following libraries weren used:
- imbalanced-learn 
- cikit-learn libraries <br>

### Combination (Over and Under) Sampling
This section combines an over- and under-sampling algorithm to determine if the algorithm results in the best performance compared to the other sampling algorithms above. Data was resample using the SMOTEENN algorithm and following the steps below:
1. View the count of the target classes using Counter from the collections library.
2. Use the resampled data to train a logistic regression model.
3. Calculate the balanced accuracy score from sklearn.metrics.
4. Print the confusion matrix from sklearn.metrics.
5. Generate a classication report using the imbalanced_classification_report from imbalanced-learn.

![SMOTEENN_sampling_code](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/SMOTEENN_Over_Under_Sampling.png)

### Results
SMOTE and SMOTEENN were comparable across the board. SMOTEENN would likely be preferred to SMOTE though due to the additional undersampling step which removes some of the outliers resulting in more cleanly separated data classes.

**Deliverable 3:** ***Use Ensemble Classifiers to Predict Credit Risk***
Using the imblearn.ensemble library, two different ensemble classifiers were trained and compared, , to predict credit risk and evaluate each model
The following ensemble Classifiers were evaluated:
- BalancedRandomForestClassifier
- EasyEnsembleClassifier

For each algorithm, the folliowing steps were completed:
1. Train the model using the training data.
2. Calculate the balanced accuracy score from sklearn.metrics.
3. Print the confusion matrix from sklearn.metrics.
4. Generate a classication report using the imbalanced_classification_report from imbalanced-learn.
5. For the Balanced Random Forest Classifier onely, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.
![Sorted Features](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/Sorted%20Features.png)
![Balanced_Random_Forest](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/Balaced_Random_Forest_Classifier.png)
![Easy_Ensemble](https://github.com/Quinneth/Credit_Risk_Analysis/blob/main/Easy_Ensemble_adaboost_classifier.png)

### Results
The Easy Ensemble AdaBoost Classifier performed superior to the Balanced Random Forest algorithm, especially for the minority class. 


## Summary

- ***Naive Random OverSampling***
-- Balanced Accuracy Score:  0.836
-- Precision majority Score:  0.83
-- Precision minority Score:  0.84
-- recall majority Score:  0.84
-- recall minority Score:  0.83

- ***SMOTE Oversampling***
-- Balanced Accuracy Score:  0.871
-- Precision majority Score:  0.87
-- Precision minority Score:  0.87
-- recall majority Score:  0.87
-- recall minority Score:  0.88

- ***UnderSampling***
-- Balanced Accuracy Score:  0.833
-- Precision majority Score:  0.82
-- Precision minority Score:  0.85
-- recall majority Score:  0.88
-- recall minority Score: 0.81

- ***SMOTEENN (Over and Under) Sampling***
-- Balanced Accuracy Score:  0.873
-- Precision majority Score:  0.87
-- Precision minority Score:  0.87
-- recall majority Score:  0.86
-- recall minority Score:  0.87

- ***BalancedRandomForestClassifier***
-- Balanced Accuracy Score:  0.789
-- Precision majority Score:  1.0
-- Precision minority Score:  0.03
-- recall majority Score:  0.89
-- recall minority Score:  0.63

- ***EasyEnsembleClassifier***
-- Balanced Accuracy Score:  0.932
-- Precision majority Score:  1.0
-- Precision minority Score:  0.09
-- recall majority Score:  0.94
-- recall minority Score:  0.92


## Recommendation
SMOTEENN provided the most favorable way of determining credit risk for the six algorithms provided. A dataset that includes more high-risk applicants would increase the accuracy and precision of the classifier models. 

