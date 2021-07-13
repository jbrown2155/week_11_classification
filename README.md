# Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that I help them predict credit risk with machine learning techniques.

In this assignment I built and evaluated several machine learning models to predict credit risk using data typically seen from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so I employed different techniques for training and evaluating models with imbalanced classes. I used the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

### Files

[Resampling Starter Notebook](Starter_Code/credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](Starter_Code/credit_risk_ensemble.ipynb)

[Lending Club Loans Data](Resources/LoanStats_2019Q1.csv.zip)

- - -

### Instructions

#### Resampling

Use the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

To begin:

1. I read the CSV into a DataFrame.

2. I split the data into Training and Testing sets.

3. I scaled the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. I used the provided code to run a Simple Logistic Regression:
    * Fit the `logistic regression classifier`.
    * Calculate the `balanced accuracy score`.
    * Display the `confusion matrix`.
    * Print the `imbalanced classification report`.

Next I:

1. Oversampled the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersampled the data using the `Cluster Centroids` algorithm.

3. Over- and undersampled using a combination `SMOTEENN` algorithm.


For each of the above, I:

1. Trained a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

2. Calculated the `balanced accuracy score` from `sklearn.metrics`.

3. Displayed the `confusion matrix` from `sklearn.metrics`.

4. Printed the `imbalanced classification report` from `imblearn.metrics`.


Using the above I answered the following questions:

* Which model had the best balanced accuracy score?
    SMOTE Oversampling 0.994827
>
* Which model had the best recall score?
    All models returned a 0.99 recall score
>
* Which model had the best geometric mean score?
    SMOTE Oversampling, Naive Random Oversampling, and Combination Sampling all returned a 0.99 geometric mean score

#### Ensemble Learning

In this section, I trained and compared two different ensemble classifiers to predict loan risk and evaluate each model. I used the [Balanced Random Forest Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html#imblearn-ensemble-balancedrandomforestclassifier) and the [Easy Ensemble Classifier](https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.ensemble.EasyEnsembleClassifier.html#imblearn-ensemble-easyensembleclassifier). Refer to the documentation for each of these to read about the models and see examples of the code.

To begin, I:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then, I completed the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Display the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.


Using the above I answered the following questions:

* Which model had the best balanced accuracy score?

* Which model had the best recall score?

* Which model had the best geometric mean score?

* What are the top three features?

- - -

### Hints and Considerations

Use the quarterly data from the LendingClub data provided in the `Resources` folder. Keep the file in the zipped format and use the starter code to read the file.

Refer to the [imbalanced-learn](https://imbalanced-learn.readthedocs.io/en/stable/) and [scikit-learn](https://scikit-learn.org/stable/) official documentation for help with training the models. Remember that these models all use the model->fit->predict API.

For the ensemble learners, use 100 estimators for both models.

- - -

### Submission

* Create Jupyter notebooks for the homework and host the notebooks on GitHub.

* Include a markdown that summarizes your homework and include this report in your GitHub repository.

* Submit the link to your GitHub project to Bootcamp Spot.

- - -

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
