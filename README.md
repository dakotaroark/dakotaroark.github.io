# Churn Prediction

## This page is still a work in progress 

## What is the current problem and our current solution to this problem?
Businesses are beginning to utilize machine learning to develop a better understanding of their customer base and 
this improved understanding will lead to more informed business decisions. One key indicator in business operations 
is our customer churn rate, with the ultimate goal to net more adds than those who churn. The current problem we 
have is that we are not leveraging our customer data to its full potential. We currently lack a viable method of 
predicting customer churn, which brings us to a possible solution, developing a churn prediction model. 

## The Scope of the Machine Learning Model
* The goal of this model is to viably predict *postpaid* customer churn. 
   - Advance pay customer's lack key variables such as credit scores and credit class to accurately predict churn.
* The big picture goal of this project is an increased in business understanding
   - This understanding can better guide our retention efforts, pricing and credit classification.

## The Data
* The data consisted of 122,616 rows from the January 2021 to August 2022.
* After cleaning the data, and filtering for postpaid customer, we were left with 65,244 rows.
   - Our overall churn rate was 16.27% over the 20 month period.
   - The average monthly recurring price was $44.90


## Exploratory Data Analysis Findings

<iframe src="dummy_county_churn.html" width="120%" height="500" style="border:1px white;">  </iframe>


| **County** | **Population Proportion** | **Churn Proportion** |
| County 1 | 3% | 5% |
| County 2 | 4% | 3% |
| County 3 | 17% | 11% |
| County 4 | 7% | 5% |
| County 5 | 1% | 2% |
| County 6 |5% | 10% |
| County 7 |2% | 4% |
| County 8 | 3% |5% |
| County 9 | 14% | 14% |
| County 10 | 9% | 8% |
| County 11 | 35% | 33% |


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


















