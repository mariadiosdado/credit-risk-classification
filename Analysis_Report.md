# Analysis

## Overview 

- Logistic Regression is a common method used for binary classification. It is preferred among other methods because it is simple to explain and undestand. It is widely used for credit scoring (high or low risk), economics, and even the medical field. However, since logistic regression assumes a linear relatioship, it cannot handle large number of variables. 
In this case, logistic regression is used to determine whether a borrower is 'healthy' or 'high-risk'. Data is collected, evaluated, and a machine learning model created in order to assess loan risk.

- The dataset used comes from historical lending activity from a peer-to-peer lending services company.

- The data provided the following  information:
    - loan_size
    - interest_rate
    - borrower_income
    - debt_to_income
    - num_of_accounts
    - derogatory_marks
    - total_debt

- We were tasked with predicting `loan status`
- The machine learning model used `LogisticRegression` algorithm for two-class classification. Then, `RandomOverSampler` method was used in order to attain a more balanced distribution of data by randomly duplicating instances of the minority class. The goal is to create an objective lending model.

## Results
- For the first model we used the original data. The data was split into training a testing datasets by using train_test_split. Then we fit a logistic regression model by using the training data. Finally, predictions were made and the model was evaluated based on the accuracy score and the classification report.
- Machine Learning Model 1:
  - Description of Model 1 Accuracy, Precision, and Recall scores.
  - Accuracy: Predicted 95%
  - Precision: Healthy Loan (`0`) with 100% 
               High-Risk Loan (`1`) with 85%
  - Recall: Healthy Loan (`0`) with 99% 
            High-Risk Loan (`1`) with 91%


- For the second model, logistic regression model was used to fil the data. Then, the `RandomOverSampler` method was used in order to achieve a more objective model. Finally, the data was evaluated using accuracy score and classification report. 
  - Machine Learning Model 2:
  - Description of Model 2 Accuracy, Precision, and Recall scores.
  - Accuracy: Predicted 99%
  - Precision: Healthy Loan (`0`) with 100% 
               High-Risk Loan (`1`) with 84%
  - Recall: Healthy Loan (`0`) with 99% 
            High-Risk Loan (`1`) with 99%


## Summary

- After evaluating both models, one using original data and another model using resampled data, results tell us that the second model performs better. 
- A noticiable change is in the accuracy of the models. The first model has a 95% accuracy while the resampled_data model has 99% accuracy. This can likely be attributed to the `RandomOverSampler` method used to balance the data.
- The Recall score also increased in the second model from 91% to 99% in a High-Risk Loan.
- From the available options, Model 1 or Model 2, one might be tempted to choose model 2 because of the accuracy percentage compared to the other model. Also, because the model was created to be more objective. Rather than be biased toward 'healthy loans', it gives other borrowers an opportunity to also get a loan. The problem with this, however, is that the model is not close to perfect as represented by the amount of False Positives. Since we don't want history repeating itself, the lender cannot risk having a large amount of borrowers defaulting on their loans. My recommendation is to go with Model 2 after some fine-tuning has been done in which the false postives decrease from 519 to less than 100.