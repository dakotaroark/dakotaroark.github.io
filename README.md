# Churn Prediction

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

![alt text](https://raw.githubusercontent.com/dakotaroark/dakotaroark.github.io/main/flex_by_cred_class.png)

<iframe src="test.html" width="115%" height="500" style="border:1px white;">  </iframe>

<iframe src="test2.html" width="115%" height="500" style="border:1px white;">  </iframe>

| **County** | **Population Proportion** | **Churn Proportion** |
| Alexander | 3% | 5% |
| Alleghany | 4% | 3% |
| Ashe | 17% | 11% |
| Avery | 7% | 5% |
| Burke | 1% | 2% |
| Caldwell |5% | 10% |
| Catawba |2% | 4% |
| Rutherford | 3% |5% |
| Surry | 14% | 14% |
| Watauga | 9% | 8% |
| Wilkes | 35% | 33% |

**THIS IS STILL A WORK IN PROGRESS**
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

## Selecting the Best Model


## The Result
* **True Positive Rate(TPR)**: .94
* **False Positive Rate(FPR)**: .16
* **False Negative Rate(FNR)**: .06
* **True Negative Rate(TNR)**: .84
* **AUC**: .9030
   * Measure of how well the model is able to distinguish between churn and non churn


![alt text](https://raw.githubusercontent.com/dakotaroark/dakotaroark.github.io/main/roc_curve.png)

#### Confusion Matrix


|                        | **Actual Positive** | **Actual Negative** |
| **Predicted Positive** | True Positives | False Positives |
| **Predicted Negative** | False Negative | True Negatives | 

|                        | **Actual Positive** | **Actual Negative** |
| **Predicted Positive** | 10651 | 277 |
| **Predicted Negative** | 700 | 1421 | 


## Implications
* Recall our total Churn Rate over a period of 20 months was 16.27%
* The total sum of Monthly Recurring cost in that time period was $2,929,673.05
* The Model caught 84% of churn
* 84% * 16.27% = 13.68%
* 13.68% * $2,929,673.05 = $400638.65 in caught loss over a period from January 2021 through August 2022 (20 months)


















