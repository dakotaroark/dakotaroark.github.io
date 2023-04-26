
# Classification Machine Learning Model

## Churn Analysis and Prediction

*On this page, information has been restricted and changed from the original analysis. This is to protect company and customer information. The machine learning models and evaluation metrics are unchanged.*

### What is the current problem and our current solution to this problem?
Businesses are beginning to utilize machine learning to develop a better understanding of their customer base, and this improved understanding will lead to more informed business decisions. One key indicator in business operations is our customer churn rate. Our current problem is that we must leverage our customer data to its full potential. We currently lack a viable method of predicting customer churn.
### The Scope of the Machine Learning Project
* Business Problem: An absence of proactive methods to identify potential churn in postpaid customers. 
   - This problem is causing a loss in potential Monthly Recurring Revenue (MRR)
* The Goal: Identify potential churn so that we can implement proactive outreach, ultimately increasing MRR.
   - Preliminary Key metrics: 
      * Monthly Recurring Revenue
      * Monthly Recurring Cost of the Project implementation

### The Data
* The data was retrieved from a Microsoft SQL Server.
* The data cleaning process included:
   - Analyzing Null values
   - Examining outliers and filtering out those due to data entry error
   - Evaluating explanatory variable distributions
   - Creating dummy variables
   - Standardizing quantitative variables
* After cleaning the data, and filtering for postpaid customers, we were left with 65,244 rows.

### Tools Used
* For storage and retrieval
   - SQL Script: Microsoft SQL server

* Data Cleaning, Analysis, and Model Creation
   - Python:
      * Pandas, Numpy, Matplotlib, Seaborn, Plotly, Scikit-learn, and SciPy

### Exploratory Data Analysis Findings
*Many of the Data Analysis Findings are not included in this section to protect customer data privacy. The below plot and table are a snippet of the analysis, and variables have been masked*

* Some key analyses included:
   - Churn rate by credit class and revenue area
   - Monthly Recurring Revenue by account class and Revenue area
   - Cholorpleth map of churn rate

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


### The Model(s)
* The response variable (Churn) was created using disconnect information and encoded as a binary variable
   - Churn = 1, non Churn = 0
  
* Key predictor variables included:
   * Tenure (Months)
   * Finance Balance
   * Credit Score
   * Recurring Price
   * Number of Flex devices
   * Total Monthly Recurring Cost

* Test Four different Algorithms
   * K Nearest Neighbor
   * Random Forest
   * Decision Tree
   * Logistic Regression

### Selecting the Best Model
* Model Evaluation Metrics:
   * Error Classification Rate
   * Type one error rate (FPR)
   * Type two error rate (FNR)
   * Recall scores for both binary outcomes
   * Confusion matrices
   * Weighted average f1 score for models trained on imbalanced class data
   * Macro average f1 score on training sets that were over and under-sampled so that the response class was balanced. 
* Used K-Fold cross-validation to tune models and hyperparameters

### Results of Final Model
Given the nature of churn, the response variable "Churn" was imbalanced. Evaluating models solely on classification rate would be misleading.
* **Sensitivity or True Positive Rate(TPR)**: 0.94
* **Specificity or True Negative Rate(TNR)**: 0.84
* **Geometric mean**: 0.88
* **False Positive Rate(FPR)**: 0.16
* **False Negative Rate(FNR)**: 0.06
* **Weighted Average F1 Score**: 0.92
* **AUC**: 0.9171


<iframe src="plotly_roc.html" width="120%" height="500" style="border:1px white;">  </iframe>


*Implementation is currently ongoing and model performance is continually monitored to ensure a healthy project life-cycle.*


















