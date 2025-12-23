
## Loan Default Risk Prediction Using ML

We decided to divide our project into 5 steps:
- Preproject
- Preprocessing
- Baseline models
- Advanced models
- Model comparison and final choice

# Step 1: preproject
In this stage, we began by analyzing our dataset. We examined the number of customers and performed descriptive statistics to analyze the target class. 
We then performed an initial baseline linear regression to get an idea of the progress of the models for future stages.

# Step 2: Preprocessing
We went back to the beginning because our steps in Step 1 were incorrect. We then performed the classic steps to obtain a usable dataset: removal of missing data, management of outliers, and data normalization.
At this stage, we now have a good, usable dataset. We can then develop our first models.


# Step 3. Standard models 
We implemented our first basic models: SVM, logistic, decision tree, and naive Bayes. However, these models produced poor results (recall class 1 0%, despite 88% accuracy).
Problem: our dataset contains 88% good payers, so a poor model has 88% accuracy. In fact, our target metric is not accuracy, but recall class 1: from a bank's point of view, we must eliminate all risk, even if it means refusing loans to customers who would have been good customers. 
So we developed SMOTE: a data interpolation technique to obtain as many class 1 as class 0. Our dataset is then balanced, without data leakage. We then obtain better results: 0% => 41% of recall class 1.
On the other hand: 
==> Still need some improvements.

# Step 4. Advanced models 
We then developed more advanced models: 
Within ensemble learning: bagging classifier, random forest, gradient boosting, XGBoost, as well as verification of results via a voting classifier (soft).
This gave us:
==> Much better results (40%  65% recall class 1).
We then wanted to test deep learning.
As predicted, this yielded the best results of the project. Neural networks are very powerful in this type of classification.

# Conclusion and final choice : 
The best model is our Deep Learning. It shows a 67 (six seveeen) % recall class 1, and 70 % of accuracy. However, the precision 1 is only at 25%. 
Therefore :a bank can predict 70% of bad debtors with 25% accuracy, which shows a very aggressive model.
This is necessary for the bank to avoid any risk: it is better to refuse loans than to accept future bad debtors!
