## AI vs ML

> **Well-posed Learning Problem**: "A computer is said to learn from experience (E) with respect to the same task (T) and some performance measure (P), if its performance on T as measured by P, improves with experience E"
- EXCLUSIVE to ML
- ML must LEARN

AI: 
- can be generalized for different tasks
- ex: GenAI can be applied to many different problems

ML:
- Model is designed for one task and one task only

## 'Tree' example
- image classification on features
	- organic - 0.3
	- shape - 0.1
		- not uniform across all (ex: fir, willow, oak, etc.)
	- soil - 0.05
	- trunk - 0.3
	- branches - 0.15
	- texture - 0.1

### ML Challenges
- Lack of training data
	- in many cases, don't have access to millions of real examples
- Poor quality of data
- Data overfitting
	- model too specific training data provided
- Data underfitting
	- model too simple or misses parameters that should've been included
- Irrelevant features
- Data security

### Data
- splitting
	- usually 70-20-10 division, but other options can work
	- train
	- test
	- validation
		- used later to make sure the model is still working

## Bias
- the difference between predicted values from your ML model and the correct/expected values
	- high bias - large error with both training/testing datasets
		- the model is oversimplified - **underfitting**

## Variance
- the variability of the ML model given the provided data points
	- High variance - almost no error with both training/testing datasets
		- the model is too complex - **overfitting**

$$
Total\ Error = Bias^2 + Variance + Irreducible\ Error
$$


| Fitting | Training error | error type | test     |
| ------- | -------------- | ---------- | -------- |
| under   | high\*         | high bias  | either\* |
|         | low            | low bias   | down     |
| over    | low            | high var   | high     |
|         | low            | low var    | low      |
\* if you have low testing, compare to how it fits the training data

### Cost (or Loss) Function
- measures the performance of a ML model for given data
- quantifies **the error between predicted and expected values**
- can be formed in many different ways
- ex:
$$
J(θ_0, θ_1) = 1/2m\ Σ_i^m (h0(x_i) - y_i)^2
$$

