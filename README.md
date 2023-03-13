# Credit Risk Analysis

## Overview of the Analysis

The analysis was intended to compare the performance of two machine learning models used to classify a loan as being 'healthy' or 'high risk'.  

The underlying data used for the modeling consisted of a total of 77,536 observations each with 7 features plus the target variable. The data is heavily imbalanced, containing only 3.22% of observations with the 'high risk' label.

The data was split into training and test datasets, with 75% being used for training.

After splitting into train and test datasets, both datasets underwent standarization of the features using a StandardScaler fit to the training data.

Both models used were logistic regression models, using Scikit-learn's LogisticRegression model. One model used the original data while the second was resampled using imblearn's RandomOverSampler.

The oversampled data showed a balanced dataset with 56,244 observations for both the 'healthy' and 'high risk' loans.

## Results

Both models were evaluated using a balanced accurracy score along with precision, recall and f1 scores. The results for each of the two models were:

### Machine Learning Model 1 (original data):
* Average metrics
  * balanced accuracy: 95.3%
  * average precision: 99%
  * average recall: 99%
  * average f1: 99%
  
* 'high risk' loan metrics
  * precision: 0.85
  * recall: 0.91
  * f1: 0.88
      
* 'healthy" loan metrics
  * precision: 1.00
  * recall: 1.00
  * f1: 1.00



### Machine Learning Model 2 (rebalanced data):

* Average metrics
  * balanced accuracy: 99.5%
  * average precision: 1.00
  * average recall: .99
  * average f1: .99
  
* 'high risk' loan metrics
  * precision: 0.85
  * recall: 1.00
  * f1: 0.92 

* 'healthy' loan metrics
  * precision: 1.00
  * recall: 0.99
  * f1: 1.00 


## Summary

There is a difference in performance between the two models. 

The overrall balanced acccuracy of the resampled data was 99.5% compared to only 95.3% for the original data. 

The performance on the 'healthy' class is comparable, with the original data showing a slightly better recall score.

The performance on the 'high risk' class shows an improved recall and f1 score.

Considering that corrrectly classifying the 'high risk' class can be more critical than doing so for the 'healty' class I would recommend using the second model to take advantage of the improved scoring especially as it relatess to the 'high risk' class.