# Marketing-Campaign

Link to Jupyter notebook below:


## Business Understanding

The business objective of this task is to find a model that can explain success of a contact. Marketing campaigns have very low response rates; therefore, this Data Mining project will aim to identify the best model in terms of positive predictive power of which customers will subscribe a deposit.

## Data Understanding

- The dataset will be assessed for any missing, duplicative, or outlier values. Depending on the feature, the sample will be removed, replaced with the mean or median value, replaced with a fixed value, or no intervention will be performed if it is deemed that it will not affect the subsequent analysis.
- The quantitiative feature distributions will be assessed for any skewness and will be scaled.
- The categorical features will be assessed and may be further condensed if too many unneccesary values are found.

## Baseline Models

- The baseline logistic regression model has perfect recall. However, it has no predictive power concerning which customers actually subscribed the deposit and there is signifcant type II error.
- The baseline knn model does have better positive predictive power. However, it comes at the cost of some type I error and significant type II error.
- The decision tree model yields similar results as the knn model. However, there is 50% more type I error at a neglible increase to positively predicting clients who subscribed a deposit.
- The SVM model yields much more positive predictive value with less type I and type II error compared to previous models.

## Model Optimization via GridSearch and Cross-Validation

Logistic Regression
Best Penalty: l1
Best C: 1
Best Class Weighting: balanced
Best Solver: liblinear

              precision    recall  f1-score   support

           0       0.99      0.85      0.92      9137
           1       0.44      0.90      0.59      1160

    accuracy                           0.86     10297
   macro avg       0.71      0.88      0.75     10297
weighted avg       0.92      0.86      0.88     10297

Decision Tree
Best Tree Criterion: entropy
Best Max Depth: 6
Best Min Samples Split: 2
Best Min Samples Leaf: 4

               precision    recall  f1-score   support

           0       0.94      0.97      0.95      9137
           1       0.66      0.51      0.57      1160

    accuracy                           0.91     10297
   macro avg       0.80      0.74      0.76     10297
weighted avg       0.91      0.91      0.91     10297

K Nearest Neighbor
Best N Neighbors: 10
Best Leaf size: 1
Best P: 2
Best Weights: uniform
Metric: minkowski

               precision    recall  f1-score   support

           0       0.93      0.97      0.95      9137
           1       0.63      0.45      0.52      1160

    accuracy                           0.91     10297
   macro avg       0.78      0.71      0.74     10297
weighted avg       0.90      0.91      0.90     10297

Support Vector Machine
Best C: 1000
Best Kernel: rbf
Best Degree: 2
Best Gamma: 0.0001

               precision    recall  f1-score   support

           0       0.92      0.98      0.95      9137
           1       0.67      0.32      0.43      1160

    accuracy                           0.91     10297
   macro avg       0.80      0.65      0.69     10297
weighted avg       0.89      0.91      0.89     10297


## Evaluation & Model Selection

- The logistic regression model has both the highest AUC score of 0.94 and the highest positive predictive power.
- The decision tree and svm models also share the highest AUC score of 0.94 have less type I error, more type II error, and much less positive predictive power.
- The knn model has a smaller AUC score of 0.92 and appears to be slightly outperformed by the decision tree model.
- Depending on the amount of resources availabe the logistic regression model would be the most successful, yet costly model due to the highest type I error of the group
- The decision tree model is much more conservative and less costly.

### Feature Importance

 - After reviewing the documentation regarding the features and the model's feature importance, I can recommend that previous outcome success, duration of call, retirement, and illiteracy are all positively associated with a successful contact.
