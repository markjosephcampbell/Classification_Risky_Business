# Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that you help them predict credit risk with machine learning techniques.

In this assignment I built and evaluated several machine learning models to predict credit risk using data you'd typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so I needed to employ different techniques for training and evaluating models with imbalanced classes. I used the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

## Files

[Resampling Starter Notebook](Starter_Code/credit_risk_resampling.ipynb)

[Lending Club Loans Data](Resources/LoanStats_2019Q1.csv.zip)

- - -

### Resampling

I used the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and built and evaluated logistic regression classifiers using the resampled data.

First:

1. Read the CSV into a DataFrame.

2. Split the data into Training and Testing sets.

3. Scaled the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Used the provided code to run a Simple Logistic Regression:
    * Trained a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.
    * Calculated the `balanced accuracy score` from `sklearn.metrics`.
    * Displayed the `confusion matrix` from `sklearn.metrics`.
    * Printed the `imbalanced classification report` from `imblearn.metrics`.

Then:

5. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

6. Undersample the data using the `Cluster Centroids` algorithm.

7. Over- and undersample using a combination `SMOTEENN` algorithm.


Analysis:

* All three models based on oversampling data had the best balanced accuracy score.
>
* The model based on undersampling data had the best recall score. 
>
* All the three models showed good geometric mean scores based on the oversampling data.

### Ensemble Learning

In this section, I trained and compared two different ensemble classifiers to predict loan risk and evaluated each model. I used the [Balanced Random Forest Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.BalancedRandomForestClassifier.html) and the [Easy Ensemble Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.EasyEnsembleClassifier.html). 

First:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scaled the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then:

4. Trained the model using the quarterly data from LendingClub provided in the `Resource` folder.

5. Calculated the balanced accuracy score from `sklearn.metrics`.

6. Displayed the confusion matrix from `sklearn.metrics`.

7. Generated a classification report using the `imbalanced_classification_report` from imbalanced learn.

8. For the balanced random forest classifier only, I printed the feature importance sorted in descending order (most important feature to least important) along with the feature score.


Analysis:

* Easy Ensemble Classifier has the best balanced accuracy score.

* Easy Ensemble Classifier had the best recall score?

* Easy Ensemble Classifier had the best geometric mean score?

* The top three features are 'total_rec_prncp', 'last_pymnt_amnt', 'total_pymnt'

- - -

© 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
