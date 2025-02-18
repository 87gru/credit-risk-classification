# Credit Risk Classification - Module 20 Challenge

## Overview of the Analysis

The purpose of this assignment is to build a model that determines the credit worthiness of borrowers based on several features of loan data provided by a financial institution.

In the `credit_risk_classification` notebook, the financial data is loaded into a pandas DataFrame from the `lending_data.csv` file. The final column -- `loan_status` -- shows the status of the loan. `0` indicates a healthy, current loan while `1` means the loan is at high risk of default. Since we're trying to determine 1 of 2 statuses for loans based on a number of features, logistic regression is an appropriate algorithm to utilize for the predicitive model.

Using different `sklearn` libraries such as `train_test_split` and `LogisticRegression`, I did the following:

* Separate the data into labels and features. Set the `loan_status` series as the `y` variable. The rest of the DataFrame (7 features) was defined as the X variable.
* Using `train_test_split`, Split the data into training and testing datasets (75% training, 25% testing).
* Initiate the `LogisticRegression` model, then use `.fit` to fit the model using the training data.
* Use `.predict` to make predictions based on the testing data.
* Using `confusion_matrix` from `sklearn.metrics`, generate a confusion matrix of the testing data predictions.
* Using `classification_report`, generate a classification report.


## Results


* Out of 19,384 testing samples: the model correctly identified 18,658 loans as `0` status loans.
* It also correctly identified 582 loans as `1` status.
* There were 37 false positives and 107 false negatives.
* Based on the classification report:
   * The model is excellent at predicting `0` status loans, with nearly 100% precision and 99% recall scores.
   * The F1-score of 1 also supports the model's excellent performance.
   * The model is less good at predicting `1` status loans. Precision/Specificity rate for this status is 84%, while recall is 94%. The f1-score of 0.89 is still considered very good, especially since this dataset is imbalanced.
   * Overall total accuracy is 99%.


## Summary

The Logistic Regression model did quite well in this loan analysis exercise. It's overall accuracy is very high; it has excellent metrics with the identification of `0` loans. 

Though it was less accurate with the identification of `1` status loans, the f1-score of 0.89 suggests that it is still a good model that captures the large majority of problematic loans. In order to reduce financial liability with False Positives (predicted `0`, actual `1`) while we continue to refine the model and epxlore other options, the financial instiution can still make use of this model to some degree if a more thorough review process for predicted `1` loans is established.

