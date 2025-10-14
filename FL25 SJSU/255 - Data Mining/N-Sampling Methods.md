
## Why use N-Sampling
- combine multiple models together and use majority to determine classification/prediction
- gain a consensus
	- ex: multiple doctor opinions

# 3 Techniques
Bagging --> train many models independently in parallel
- Random Forest
Boosting --> models trained sequentially, correcting each other's mistakes
- XGBoost
Stacking --> meta-learning learns how to combine models

Why ensembles work
- Reduce Variance
	- bagging
- Reduce Bias
	- boosting
- Improve Generalization
	- stacking


# Bagging (Bootstrap Aggregating)

**Concept**: train models on **different bootstrapped samples** of data, then aggregate

**Process**:
1. Take bootstrap samples (random samples **with replacement**)
2. Train a base model
3. Aggregate predictions by voting (classification) or averaging (regression)

#### Random Forest
- extension of bagging
- **extra randomness**: at each tree split, consider only a **random subset of features**, not all
- **Algo:**
	1.  \[idk]
	2. For each node, randomly choose mmm features out of ppp
	3. split on best feature among those mmm
	4. grow many trees
	5. aggregate by voting/averaging


# Boosting

## **AdaBoost (Adaptive Boosting)**
- **Concept**: sequentially train weak learners (e.g. shallow trees). Each new learner focuses on more mistakes of the previous ones

### **Example**
Email Spam classification
- First weak classifier misclassifies 20%
- Increase weights of those emails
- the second classifier focuses on them
- combine --> strong classifier

### **Steps**
Initialize weights (all samples are equally important at the start), train Model 1, *assign weight to this learner based on accuracy*, increase weights of misclassified points so that the next learner focuses on them, **combine all weak learners into one strong model**

## Gradient Boosting
instead of re-weighting samples (like AdaBoost), Gradient Boosting treat boosting as an optimization problem and uses gradient descent to minimize loss function (e.g. LSE, LogLoss)

Start with simple model

Compute Residuals (error) between prediction and labels

Update the model


XGBoost, LightGBM (uses histogram-based splits) and CatBoost( Suppose you have a feature "City) with values {NY, LA, SF}
- traditional one-hot encoding --> large sparse vectors
- CatBoost converts "City" into a smarter numeric version


## Stacking

instead of just averaging, train a **meta-model** to learn how to combine predictions from base models

