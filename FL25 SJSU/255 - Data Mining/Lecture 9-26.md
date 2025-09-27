## KNN
- supervised learning algo
- based on finding closest prediction class using distance
- ex: classifying cats vs dogs

| Animal ID | Len of Tail | Weight | Label |
| --------- | ----------- | ------ | ----- |
| A         | 20cm        | 2kg    | cat   |
| B         | 22cm        | 5kg    | cat   |
| C         | 100cm       | 40kg   | dog   |
| D         | 140cm       | 80kg   | dog   |

trying to predict for E(50cm, 30kg)
assume k=2
- remember how to find optimal k

1. calculate distance (euclidean is preferred)
$$
	dist = \sqrt{(x_1-x_2)^2 + (y_1-y_2)^2}
$$
2. pairwise get all distances compared to existing points
3. find k=2 vectors with the lowest distance (A and B in this case)
4. (Cat, Cat) --> predict Cat
5. if (Cat, Dog), then inconclusive bc no majority in voting

## Decision Tree
- Supervised
- start with features
- make some decisions to split features
	- fans out
- concludes to one final decision

data

| Weather  | Humidity | Play Cricket? |
| -------- | -------- | ------------- |
| sunny    | low      | yes           |
| rainy    | low      | no            |
| overcast | high     | yes           |
| rainy    | normal   | yes           |

test: (sunny, normal)

![[Drawing 2025-09-26 18.29.08.excalidraw]]

Closest Node is (Sunny, Low) --> predict Yes
## Classification based on Bayes' Theorem

Basic Probability



## SVM
Support Vector Machine
Focus on Linear SVM

support vectors:
- points that are closest to the hyperplane
- distance between point and line

find separating line that *maximizes* distance between support vectors

maximize ρ, or the margin between the line and the support vectors

Optimization Problem:

$$
w = sigma(a_iy_ix_i)\ \ b=y_k - sigma(a_iy_ix_i^Tx_k) ,\  k > 0
$$

non-linear svm: 

can use *kernel trick?* to create higher dimensionality required to successfully separate points that would not be separable linearly

slack variable
## Basics of Neural Networks

simplified mathematical model of biological neuron
- processing unit of brain
- brain composed of billions of neurons
- each neuron communicates with another neuron by sending electrical signals
- mesh network
- dendrite
	- takes input
- nucleus
	- processes input
- synapse
	- sends output

### Perceptron

![[Drawing 2025-09-26 18.55.24_0.excalidraw]]


### Multilayer Perceptron
![[Pasted image 20250926190217.png]]
- 3 input layer
- multiple hidden layers w/ 4 perceptrons
- 1 output layer
- **fully connected**: each node is connected to every other node in the next layer
- can also be **sparse** if not fully connected

### Training multi-layer networks
- gradient descent to update weights
	- partial derivative of Cost function
	- E(w)
	- repeat until reach local minima
$$
	w_{n+1} = w_n - α \frac{ẟE}{ẟw}
$$
	- α determines size of step
		- too small --> takes too long to find local min
		- too large --> risk overshooting local min

#### **Back-propagation Algorithm**


**Forward-Backward Propagation**
1. Assign RANDOM values to all weights
2. forward propagation: take inputs and compute output of each node
3. backward propagation: applying chain rule to gradient descent (SEE LECT 6_1 SLIDES FOR DIAGRAM)
4. repeat depending on number of **EPOCHs**
	1. want loss value to converge


sigmoid function:
$$
g(t) = \frac{1}{1+e^{-x}}
$$


#### NNs are Universal Approximators (in theory)
- if you have the *right data*, and apply it properly, then a NN can predict anything
- for any nonlinear function
- NAND gate
	- universal bc it can represent any other gate

#### Weight Initialization
- all Zeroes?
	- VERY WRONG
- small random initializations

#### Activation Functions
- Sigmoid
- Tanh
- Softplus
- ELU
- ReLU
- Leaky ReLU/PReLU
- Randomized Leaky ReLU
- etc...

#### Overfitting for NNs
- want training accuracy to increase and validation accuracy to increase
- training accuracy up + val accuracy down --> overfitting
	- testing on unseen data --> bad performance


### Underfitting for NNs
- training accuracy too low

Next-Class: N-sample methods