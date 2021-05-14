# Telco Customer Churn
Matthew David Mandel Hemsley

https://mdmhemsley.github.io/

My experiences with a fictional churn dataset found on Kaggle:

https://www.kaggle.com/blastchar/telco-customer-churn

## Summary
This churn dataset consists of 7043 unique rows, representative of 7043 customers and their corresponding 21 features. The goal is the utilize 20 of these features to construct a model that can accurately predict the 21st feature, Churn.

## Python Libraries
<ul>
 <li>Pandas</li>
 <li>NumPy</li>
 <li>MatPlotLib</li>
 <li>Seaborn</li>
 <li>StatsModels API</li>
 <li>SKLearn</li>
</ul>

## Data Dictionary
**NOTE:** There was no provided data dictionary with the Kaggle dataset. I have done external research, as well as asked fellow data scientists, and have made several assumptions in order to proceed with my exploration of this data set. Features will assumed descriptions will be labeled Ambiguous prior to their description.


| Variable Name | Data Type | Description |
|---------------|-----------|-------------|
| customerID    | string | Unique ID for row. Set as index |
| gender        | string (int64) | Female = 1, Male = 0, later dropped for statistical irrelivence and ethical concerns |
| SeniorCitizen | int64 | Ambiguous - Greater than or equal to 65 Years  = 1, Under 65 years = 0 |
| Partner | string (int64) | Ambiguous - Long term planned cohabitation with an individual of similar age = 1, later dropped for statistical irrelivence |
| Dependents | string (int64) | Ambiguous - Cohabitating with individuals with whom the customer is fiscally responsible for = 1 |
| Tenure | int64 | Ambiguous - Number of months customer has been a member |
| PhoneService | string (int64) | Subscribe to phone service = 1, else 0 |
| MultipleLines | string (Dummify) | Divided into three binary features, later dropped for statistical irrelivence |
| InternetService | string(Dummify) | Subscribe to phone service = 1, else 0 |
| Online Security | string(Dummify) |Subscribe to online security service = 1, else 0 |
| Online Backup | string(Dummify) | Subscribe to online backup service = 1, else 0 |
| DeviceProtection | string(Dummify) | Subscribe to device protection service = 1, else 0 |
| TechSupport | string(Dummify) | Subscribe to tech support service = 1, else 0 |
| StreamingTV | string(Dummify) | Subscribe to television streaming service = 1, else 0 |
| StreamingMovies | string(Dummify) | Subscribe to movie streaming service = 1, else 0 |
| Contract | string(Dummify) | Type of contract: Month-to-month, One Year, or Two Year. |
| PaperlessBilling | string (int64) | Yes = 1, No = 0 |
| PaymentMethod | string(Dummify) | Electronic Check, Mailed Check, Bank Transfer(Automatic), Credit Card(Automatic), later dropped for statistical irrelivence |
| MonthlyCharges | float64 | Ambiguous = Amount due at month end in United States Dollars |
| TotalCharges | float64 | Ambiguous - Total number of charges incurred by the account throughout it's membership |
| Churn | int64 | If the customer churned = 1, else the customer was retained = 0 |

## Models
The following modeling technique were utilized throughout this project. Inferences can be found below, with further details outlined in the notebook. As we are attempting to perdict churn, which is a binary classification, we will be looking at models that deal with binary classification. 

 Important Metrics include: 
<ul>
  <li>Recall/Sensitivity - Our goal is to minimize Type II errors, which is to say we wish to avoid miss classifying a customer as not churning and then being surprised when they churn. To accomplish this, we will be seeking to maximize recall over accuracy.</li>
  <li>Area Under the Receiver Operating Characteristics Curve Score - We will be utilizing this score to compare our models, as we are seeking to best represent the seperation of our data.</li></ul>

### Logistic Regression
 Logistic regression is utilized to determine the statistical significance of each feature based on their z-score and coefficent to determine impact on the dependent variable, churn. Not only did this model perform the best, but also provided the most interpretation in order to dervice insights from the performance of our model concerning given features.

### K-Nearest Neighbors
K-Nearest Neighbors predicts the class of an observation by identifing the closest observations that are closest to it. Gridsearching is used to tune this model across both the way it measures distances, as well as how much importance it places on the proximity of each neighbor.


### Support-Vector Machine
Support-Vector Machines are supervised learning models with associated learning algorithms that analyze data for classification. One of the most powerful non-neural network models, for more details I recommend reading Towards Data Science's article: https://towardsdatascience.com/support-vector-machine-introduction-to-machine-learning-algorithms-934a444fca47
