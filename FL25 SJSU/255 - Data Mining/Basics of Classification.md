Training/Testing/Validation sets

Over/Underfitting

### Metrics for Classification
1. Accuracy 
$$
	\frac{TP + TN}{TP + TN + FP + FN}
$$
2. Precision
$$
	\frac{TP}{TP + FP}
$$
3. Recall
$$
	\frac{TP}{TP + FN}
$$
4. F1 Score
$$
	2* \frac{precision * recall}{precision + recall} = 2*\frac{TP}{TP + FP}
$$

5. ROC - Receiver Operating Characteristic curve
	![[Screenshot 2025-09-19 at 6.16.51 PM.png]]
6. Confusion Matrix


Why can't we just use accuracy?
- class imbalance!
	- ex: 95% of data is 'yes', 5% is 'no'
		- model could guess 'yes' and get 95% accuracy, but it's not a good model


#### Discriminative Model 
- learning conditional probability
- X input, y output
- P(y given X)
- - P(y | X)

#### Generative Model
- Learning p(y,x)
- GAN

#### Linear Regression
- fit a straight line to the data
- y  = theta1x1 + theta2x2 + ... + 

#### Gradient Descent

theta = theta - alpha * partial deriv of cost function with respect to variable trying to find

repeat until convergence
#### Neural Network
- simplified mathematical model of biological neuron
- perceptron
- NAND gate
- Multi Layer Perceptron
	- DNN is MLP with many hidden layers
- 