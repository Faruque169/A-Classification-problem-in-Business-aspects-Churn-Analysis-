                                 A-Classification-problem-in-Business-aspects-(Churn-Analysis)
Here I have tried to illustrate the insight of the data using data curing, data wrangling, Data Evaluation and finally build a model using xgboost.


## Prediction algorithm overview -
XGboost:
XGboost is an ensemble method for fast outcome and it is a sequetial learning algorithom that supports auto tunning for hyperparameter.
This algorithom also attempt to solve some of the key business challenges pertaining to customer attrition like, 
(1) what is the likelihood of an active customer leaving an organization? 
(2) what are key indicators of a customer churn? 
(3) what retention strategies can be implemented based on the results to diminish prospective customer churn?

**Features of XGBoost:
 XGBoost is scalable in distributed as well as memory-limited settings. This scalability is due to several algorithmic optimizations.

1. Split finding algorithms: approximate algorithm
2. Column block for parallel learning
3. Weighted quantile sketch for approximate tree learning
4. Sparsity-aware algorithm
5. Cache-aware access
6. Out-of-core computation
7. Regularized Learning Objective.

Obj(Θ)=L(θ)+ Ω(Θ)
where Ω is the regularization term which most algorithms forget to include in the objective function. However, XGBoost includes regularization, thus controlling the complexity of the model and preventing overfitting.

The above 7 features maybe individually present in some algorithms, but XGBoost combines these techniques to make an end-to-end system that provides scalability and effective resource utilization.

## Reason for choosing
1. Speed
2. Awareness of sparse data
3. Implementation on single, distributed systems and out-of-core computation
4. Parallelization

## Findings
I have summarise some of the key findings from EDA -
1. The dataset does not have any missing or erroneous data values.
2. negatively correlated with the days_active and churn(closed_deals) rate 
   and weekly correlated with the activity_type, activity_count with churn(closed_deals) rate. 
   Also shows some correlation with activity_type_f and days_active.
3. The dataset is imbalanced with the majority of customers being active.
4. There is almost no multicollinearity between activity_type's, activity_count and days_active.

*Note: All findings were describes in the source code after each checkpoints. 

# Plan on improving performance
In our case we use logistics regression to solve the classification we may also try more ML algorithoms to compare the best one-
k-Nearest Neighbors.
Decision Trees.
Support Vector Machine.
Naive Bayes.
SVC.

We used boosting technique whereas begging can be used as well. Later we can follow-  
1. Model Evaluation - Through train & evaluate Chosen Model, AUC/ROC curve ETC
2. Model Improvement - Hyperparameter tunning, changing gradient decent, usinng different parameters, changing activation functions if required.
3. Future Predictions - Compare predictions against the test set
4. Model Deployment - Save/dump the model for future use case.


# Missing information, what do we need to get more from the company?
More featue like Socio economic and demorgraphic data like gender,seniority of the clients, partner/friend is in the company, tenure etc
