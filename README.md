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
      * F1 score is calculated by taking the harmonic mean of the models precision and recall.
         * Recall: Proportion of samples that a the model correctly identifies as belonging to the positive class. 
         * ![Recall equation](https://latex.codecogs.com/gif.latex?%5Cfrac%7BTP%7D%7BTP&plus;FN%7D)
         * Precision: Proportion of correct positive predictions. The models predicted positive instances that are actually positive.
         * ![Precision Equation](https://latex.codecogs.com/gif.latex?%5Cfrac%7BTP%7D%7BTP&plus;FP%7D)
   * Macro average f1 score on training sets that were over and under sampled so that the response class was balanced. 

## The Result
* **True Positive Rate(TPR)**: .94
* **False Positive Rate(FPR)**: .16
* **False Negative Rate(FNR)**: .06
* **True Negative Rate(TNR)**: .84
* **Weighted Average F! Score**: .92
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


















