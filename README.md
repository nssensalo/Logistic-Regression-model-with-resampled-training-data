# Credit Risk Classification

## Overview of the Analysis


This purpose of the following analysis is to investigate and compare certain machine learning tools and techniques to evaluate ways to help remedy the issue of imbalanced data when training a machine model. The goal was to be able to predict whether a borrower had potential for an ultimately healthy loan, or a risky loan. The data set consist of historical peear-to-pear lending activity including loan size, interest rate, borrowesr income, debt-to-income ration, number of accounts the borrower has, derogatory, marks, total debt, and the most importantly the loan status ( healthy loan or risky loan ). In order to make predictions the loan status data was divided and tallied using a function called value_counts which shows the total number of healthy loans and the total of risky loans. Given this ratio was imbalanced, favoring a higher number of healthy loans, the model was executed using the imbalanced data and again with the data rebalanced. A classification report of both executions was compared to see which yieled better prediction outcomes. Below are the following stages:

* The data frame was divided into two parts, the loan status data set to y and the rest of the data set to X.
* The value_counts function was used to calcuate the break down of the imbalanced data.
* All of the data was divided and used for training data or testing data using the train_test module.
* The training data was fit to a linear Logistic Regression model.
* Predictions were make using the test data.
* The balanced accuracy score, confusion matrix, and classification report were calculated.
* This process was repeated with the data rebalanced by using the random over sampler model which evened the balance of healthy and risky loans before in the begining of the process. 


## Results

* Machine Learning Model 1:
  * balanced accuracy score: .95
  * precision score: healthy = 1.00 risky = .85
  * recalls score: healthy = .99 risky = .91


* Machine Learning Model 2:
  * balanced accuracy score: .99
  * precision score: healthy = 1.00 risky = .84
  * recall score: healthy = .99 risky = .99


## Summary

In Machine Learning Model 1 there is a perfect precision score for healthly loans but may have false positives when identifying risky loans (15 for every 100 applicants). It's recall is similar in that it detects almost all the healthy loans 99% of the time, but has a 9% chance that it won't catch the risky loans accidently percieved as false positives which can be a big problem given the point of the loan process is to identify risky loans. The Machine Learning Model 2, fit with oversampled data, produces a higer recall of risky loans showing a 99% chance it will detect all the risky loans and not accidently classficy them as false positives which is really important. The accurancy is also higher at 99% compared to 95% in the first model, which with an even number of healthy and risky loans to start,exhibits stronger evidence that the training was done on data not sqewed. I therfore would recommend Machine Learning Model 2. 
