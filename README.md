# Telco Customer Churn
My experiences with a fictional churn dataset found on Kaggle:
https://www.kaggle.com/blastchar/telco-customer-churn

## Summary
This churn dataset consists of 7043 unique rows, representative of 7043 customers and their corresponding 21 features. The goal is the utilize 20 of these features to construct a model that can accurately predict the 21st feature, Churn.

## Data Dictionary
**NOTE:** There was no provided data dictionary with the Kaggle dataset. I have done external research, as well as asked fellow data scientists, and have made several assumptions in order to proceed with my exploration of this data set.


| Variable Name | Data Type | Description |
|---------------|-----------|-------------|
| customerID    |  string   | Unique ID for row. Set as index.|
| gender        | int64     | Female = 1, Male = 0 |

## Models
The following modeling technique were utilized throughout this project. Inferences can be found below, with further details outlined in the notebook. As we are attempting to perdict churn, which is a binary classification, we will be looking at models that deal with binary classification. 

### Logistic Regression
