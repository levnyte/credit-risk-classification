# Module 20 Analysis

The purpose of this analysis is to determine which machine learning model is better at determining the creditworthiness of borrowers.  The models take the loan status of each borrower, looks at the financial characteristics that accompany the loan status, and make predictions based on that information.  Those financial characteristics are loan size, interest rate, borrower income, debt-to-income, number of accounts, derogatory marks, and total debt.  

The two models were a logistical regression with the original data, and a logistical regression with resampled training data.

With regular logistical regression, the data read from the CSV file was separated into two variables. Lowercase "y" represented the loan status, and uppercase "X" represented the eight other columns which were the aforementioned characteristics.  the value_counts function broke down the loan status numbers.  The loan status can be classified as healthy or high-risk.  Of the 77,536 loans, 2,500 were high-risk (3.22%), and 75,036 were healthy (93.78%).  The train_test_split function separated the "X" and "y" variables into training and testing variables.  By default, 25 percent of the data is used for testing.

A model is made using logistic regression which was then fitted using the training data of X_train and y_train.  Predictions were then made using the testing data of X_test.  The balanced accuracy score is used to evaluate the model when there is  a class imbalance in the data.  A confusion matrix was then used to help visualize how well the model was identify healthy and high-risk loans.  Finally, a classification report was made to give an overview of the model's performance.

A logistical regression with resampled training data involved similar steps.  However, a random oversampler was used.  The original training data was then fitted to the random oversampler model.  A classifier was then fitted using the resampled training data.  A second set of predictions were made using the classifier and X_test.  From there, a balanced accuracy score, a confusion matrix, and a classification report were produced.

## Results

* Machine Learning Model 1 (Original Data):
  * Balanced Accuracy Score:  0.9520479254722232
  * Precision:  
    * Healthy Loan:           1.00
    * High-Risk Loan:         0.85
  * Recall Score:
    * Healthy Loan:           0.99
    * High-Risk Loan:         0.91


* Machine Learning Model 2 (Oversampling):
  * Balanced Accuracy Score:  0.9936781215845847
  * Precision:  
    * Healthy Loan:           1.00
    * High-Risk Loan:         0.84
  * Recall Score:
    * Healthy Loan:           0.99
    * High-Risk Loan:         0.99

## Summary

The model that used oversampling had increased the recall score of the high-risk loans.  This means that a high-risk case is rarely missed.  The balanced accuracy score also moved closer to 1.  Oversampling increases the number of samples in minority classes in order to balance class distribution.  This helps the model make accurate predictions for minority classes.  The minority class in this dataset is high-risk loans.  A lending service is more concerned about risk.  Therefore, I recommend the oversampling model.

# Reference
edX. "Module 20 Challenge." 8 February 2024, bootcampspot.instructure.com/courses/4916/assignments/61919?module_item_id=1077659.