# Credit Risk Classification 
Module 20 Challenge

![titlepic](https://github.com/f2-b2/credit-risk-classification/assets/118685191/80458db5-8a5f-487a-b254-1bd5314cc01e)

## Background

In this Challenge, I’ll use various techniques to train and evaluate a model based on loan risk. I’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

## Before You Begin

1. Create a new repository for this project called `credit-risk-classification`. **Do not add this homework to an existing repository.**

2. Clone the new repository to your computer.

3. Inside your `credit-risk-classification` repository, create a folder titled "Credit_Risk."

4. Inside the "Credit_Risk" folder, add the `credit_risk_classification.ipynb` and `lending_data.csv` files found in the "Starter_Code.zip" file.

5. Push your changes to GitHub.

## Instructions

The instructions for this Challenge are divided into the following subsections:

  * Split the Data into Training and Testing Sets

  * Create a Logistic Regression Model with the Original Data

  * Predict a Logistic Regression Model with Resampled Training Data

  * Write a Credit Risk Analysis Report

### Split the Data into Training and Testing Sets

Open the starter code notebook and use it to complete the following steps:

1. Read the `lending_data.csv` data from the Resources folder into a Pandas DataFrame.

2. Create the labels set (`y`) from the “loan_status” column, and then create the features (`X`) DataFrame from the remaining columns.

> **_NOTE:_** A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

3. Split the data into training and testing datasets by using `train_test_split`.

### Create a Logistic Regression Model with the Original Data

Use your knowledge of logistic regression to complete the following steps:

1. Fit a logistic regression model by using the training data (`X_train` and `y_train`).

2. Save the predictions for the testing data labels by using the testing feature data (`X_test`) and the fitted model.

3. Evaluate the model’s performance by doing the following:
    * Calculate the accuracy score of the model.
    
    * Generate a confusion matrix.

    * Print the classification report.

4. Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

## Write a Credit Risk Analysis Report
### Overview of the Analysis

This analysis uses past lending activity from a peer-to-peer lending company to create a model that predicts the creditworthiness of future borrowers. The dependant variable (y) is loan status which flags a loan as healthy (0) or high-risk (1). The independent variables (X) are loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks, and total debt. We want to accuratly predict which loans will be high risk and which will be healthy because the bank does not want to reject a loan that would be repayed (false 1) or worse yet make a loan that will not be repayed (false 0).

Stages in the machine learning model process: 
1. Load data from csv into 'df_lending_data'. 
2. Create the labels set (`y`)  from the “loan_status” column, and then create the features (`X`) DataFrame from the remaining columns.
3. Check the balance of our labels by using the value_counts function. 
4. Split the data into training and testing datasets. 
5. Create a Logistic Regression Model with the Original Data by fitting the model, saving the predictions, and evaluating the performance by printing a balanced accuracy score, confusion matrix, and a classification report. 
6. Repeat using RandomOverSampler module.


### Results

* Model 1 (Original Data) Classification Report:  
![Orig_report](https://github.com/f2-b2/credit-risk-classification/assets/118685191/458a590b-4d83-4a58-b2f1-394d6e11280d)  
The balanced_accuracy score of the model: 0.9442676901753825

#### 

* Model 2 (Resampled Data) Classification Report:  
![resampled_report](https://github.com/f2-b2/credit-risk-classification/assets/118685191/84745a62-ece2-4f9c-941e-776d65265d4c)  
The balanced_accuracy score of the model: 0.9959744975744975

### Summary

Model 2 with the Resampled Data is the best option for this data because it improves the recall score for high risk loans and has higher balanced accuracy while maintianing great precision and recall for healthy loans. Improved recall means high-risk loans will be predicted more accurately allowing the bank to avoid making bad loans.
