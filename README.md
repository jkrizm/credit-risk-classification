# Module 12 Report

## Overview of the Analysis

The goal of this analysis was to develop and evaluate a model of determining loan risk by using a dataset of historical lending activity from a peer-to-peer lending services company. The purpose of the model was to identify  creditworthiness of borrowers to determine whether or not someone is likely to pay back the loan or if the bank would be putting themselves at high-risk of not seeing the return. 

The dataset consists of historical data from 75036 healthy loans and 2500 high-risk loans. The following data were used to predict loan status (healthy or high-risk):
loan_size,interest_rate,borrower_income,debt_to_income,num_of_accounts,derogatory_marks,and total_debt. This prediction was performed using a logistic regression, which estimates the probability of an event occurring (in our case, a loan being healthy or high-risk), given some set of dependent variables (in our case, the loan size, interest rate, borrower income, debt-to-income ratio, number of accoutns, derogatory marks, and total debt)

The following steps were used in the analysis:
1. load in csv with historical data
2. Use the loan_status column to create the labels that were going to be predicted, and then create a DataFrame from the remaining columns that would be used to predict the labels in loan_status.
3. Split the dataset into training and test sets.
4. Train the logistic regression model on 75% of the data (58,152 loans)
5. Use the remaining 25% of the data (19,384 loans) to test the model. 



## Results

Logistic Regression Results:

Accuracy: Although the balanced accuracy score was not listed in the starter code, it was listed as something to include here, so I ran it and found that the balanced accuracy is about 95%.
Precision: The average precision was 92%. The precision was better for the healthy loans (100%) than the high-risk loans (84%). 
Recall: The average recall was 95%. The recall was better for the healthy loans (99%) than the high-risk loans (91%). 

These correspond to the values of the confusion matrix, which showed:
True positive (i.e., actually healthy, predict healthy): 18648
False negative (i.e., actually healthy, predict high-risk): 109
False positive (i.e., actually high-risk, predict healthy): 54
True negative (i.e., actually high-risk, predict high-risk): 573


## Summary

Because only one model was used, it is not possible to compare and contrast models. However, from these data, it is evident that the logistic regression does a very good job of predicting healthy loans and an okay job of predicting high-risk loans. Because the lender is looking for safe bets when loaning money (i.e., they want to be positive that the loan will be repaid), this model is probably sufficient, given that the number of high-risks that were predicted as healthy were relatively low and 99% of healthy loans were accurately identified as such. 
