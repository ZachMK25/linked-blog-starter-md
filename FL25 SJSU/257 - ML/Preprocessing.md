
## Regularization

if we don't know what features to remove

#### Lasso Regression
adds an absolute value of magnitude of the coefficient as a penalty term to the loss function
squared term makes small features go to 0
***feature selection***

#### Ridge Regression
adds the squared value of magnitude
never "kills" a feature, but they are less important than others
***feature prioritization***

When to use what?
- no right or wrong answer
- just try to end up with a reasonable number of features in the end based on the input data

## Standardization
remove outliers
same order of magnitude across data
##  Model Evaluation
### Class Imbalance
dataset has many observations of one case (ex: no disease) but not the other
model may perform better classifying one class vs the other
recall sensitivity and specificity can be used to evaluate a model's performance on these

F1 score can be used as a general score