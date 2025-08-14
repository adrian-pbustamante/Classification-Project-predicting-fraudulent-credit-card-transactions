# predicting-fraudulent-credit-card-transactions

#### Adrian P. Bustamante, Ph.D.
#### adrianpebus@gmail.com

## Objective

We study a dataset containing transactions made by credit cards that occurred during two days in 2013. The dataset is highly unbalanced, we have 492 frauds out of  284 807 transactions, roughly the 0.172% of all transactions. 

The objective of this study is to train different classification models to predict whether a transaction is fraudulent or not. We want to find a model that performs well on precision, recall, and fscore.

Our focus is on predictability but we also include a couple of results on interpretability. To measure the performance of the models considered we will be focusing on precision, recall and f1score.

## About the data

The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset present transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. More details on current and past projects on related topics are available on http://mlg.ulb.ac.be/BruFence and http://mlg.ulb.ac.be/ARTML.

The dataset used for this project can be found at https://www.kaggle.com/datasets/qnqfbqfqo/credit-card-fraud-detection-date-25th-of-june-2015

## Conclusion

We worked with a dataset containing information about credict card transactions and our objective was to determine whether a credit card transaction was fraudulent or not. That is, our aim was to find a classification model that performs well on precision, recall, and fscore. We focused on these metrics due to the fact that the dataset is highly unbalanced.

The model found to perform best (among the models considered) is a Voting Classifier constructed from an ensemble of models containing the following ones: Log-Regression, KNN, SVC, Bagging Trees, Random Forest, and XGBoost. This Voting Classifier yiels a Precision $\approx 0.95$, a Recall $\approx 0.81$, and a Fscore $\approx 0.87$. Moreover, we performed Permutation Feature Importance (PFI) analysis and use a Logistic Regression as a Global Surrogated Model, from their results it seems that the feature 'V14' is the most important one for the classification.

The main challenge for this study was the lack of computational resources (everything was run in a laptop with 16gp of ram memory and 4 cores). In order to reduce the computational time, to perform the cross validations and PFI, we have decided to use large test sets, about 50% of the data. With better computational resources a more exhaustive search for the best hyperparameters can be achieve and, presumably, better results as well.
