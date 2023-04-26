# Churn Model

*On this page, information has been restricted and changed from the original analysis. This is to protect company and customer information.*

## What is the current problem and our current solution to this problem?
Businesses are beginning to utilize machine learning to develop a better understanding of their customer base, and this improved understanding will lead to more informed business decisions. One key indicator in business operations is our customer churn rate, aiming to add more customers than those who churn. Our current problem is that we must leverage our customer data to its full potential. We currently lack a viable method of predicting customer churn.
## The Scope of the Machine Learning Project
* Business Problem: An absence of proactive methods to identify potential churn in postpaid customers. 
   - This problem is causing a loss in potential Monthly Recurring Revenue (MRR)
* The Goal: Identify potential churn so that we can implement proactive outreach, ultimately increasing MRR
   - Preliminary Key metrics: 
      * Monthly Recurring Revenue
      * Monthly Recurring Cost of the Project Implentation

## The Data
* The data was retrieved from a Microsoft SQL Server.
* The data cleaning process included:
   - Analyzing Null values
   - Examining outliers and filtering out those due to data entry error
   - Evaluating explanatory variable distributions
   - Creating dummy variables
   - Standardizing quantitative variables
* After cleaning the data, and filtering for postpaid customer, we were left with 65,244 rows.
   - Our overall churn rate was 16.27% over the 20 month period.
   - The average monthly recurring price was $44.90


## Exploratory Data Analysis Findings

<iframe src="dummy_county_churn.html" width="120%" height="500" style="border:1px white;">  </iframe>


| **County** | **Population Proportion** | **Churn Proportion** | **MRR Proportion** |
| County 1 | 3% | 5% | 3% |
| County 2 | 4% | 3% | 4% |
| County 3 | 17% | 11% | 17% |
| County 4 | 7% | 5% | 8% |
| County 5 | 1% | 2% | 1% | 
| County 6 |5% | 10% | 4% |
| County 7 |2% | 4% | 2% |
| County 8 | 3% |5% | 4% |
| County 9 | 14% | 14% | 14% |
| County 10 | 9% | 8% | 9% |
| County 11 | 35% | 33% | 34% |


## The Model(s)
* The response variable in this dataset was Churn
   * Encoded as a binary class with non-Churn = 0, churn = 1
* Key predictor variables included:
   * Tenure (Months)
   * Credit Class (1:6)
   * Flex Balance
   * Initial Credit Score
   * Recurring Price
   * Current Credit Score
   * Number of Flex devices
   * Total Monthly Recurring Cost

* Test Four different Algorithms
   * K Nearest Neighbor
   * Random Forest
   * Decision Tree
   * Logistic Regression

## Selecting the Best Model
* Model Evaluation Metrics:
   * Each model was evaluated base upon multiple measures 
   * Confusion matrix for each individual model
   * Weighted average f1 score for models trained on imbalanced class data
      * F1 score is calculated by taking the harmonic mean of the models precision and recall
   * Macro average f1 score on training sets that were over and under sampled so that the response class was balanced. 

## The Result
* **True Positive Rate(TPR)**: .94
* **False Positive Rate(FPR)**: .16
* **False Negative Rate(FNR)**: .06
* **True Negative Rate(TNR)**: .84
* **Weighted Average F1 Score**: .92
* **AUC**: .9030
   * Measure of how well the model is able to distinguish between churn and non churn


<iframe src="plotly_roc.html" width="120%" height="500" style="border:1px white;">  </iframe>



## Implications


















