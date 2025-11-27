
|                        | What is it (best) for?                                     | Advantages                                        | Disadvantages                                    | Models/Approaches/Concepts                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------- | ---------------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reinforcement Learning | non-deterministic environments<br><br>how "it" behaves<br> | real-world environments<br><br>behavioral setting | slow performance<br><br>training quality<br><br> | agent/environment, policy, value<br><br>positive vs negative reinforcement<br><br>negative --> can make agent too cautious, bare-minimum behavior<br><br>positive --> can learn 1 behavior<br><br>model-free vs. model-based<br><br>model-free: trial and error<br><br>model-based: emulate environment by sampling states<br><br>Model-free: policy vs value<br><br>MF-pol: set of rules<br><br>MF-value: get reward of X for doing task Y<br><br>q-learning: MF-val based |
| Neural Networks        |                                                            |                                                   |                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Deep Learning          |                                                            |                                                   |                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
# Reinforcement Learning

## What is it (best) for?
- non-deterministic environments
- how "it" behaves

## Advantages

- real-world environments
- behavioral setting
## Disadvantages

- slow performance
- training quality

## Models/Approaches/Concepts

- agent/environment, policy, value
- positive vs negative reinforcement
	- negative --> can make agent too cautious, bare-minimum behavior
	- positive --> can learn 1 behavior
- model-free vs. model-based
	- model-free: trial and error
		- policy vs value
			- MF-pol: set of rules
			- MF-value: get reward of X for doing task Y
	- model-based: emulate environment by sampling states

#### Q-learning
- MF-val base
- Q-table (initialize) --> make action --> measure reward --> Q-table (update) --> repeat

![[Screenshot 2025-11-25 at 2.09.05 PM.png]]

# Neural Networks
## What is it (best) for?
- learning complex patterns
	- non-linear relationships
- mimics how human brain thinks

## Advantages
- unstructured data
- flexibility (potato rot and skin cancer cells)

## Disadvantages
- hardware requirements
- incomplete results
	- not all nodes may be trained --> may lose specific insights
	- may only be trained for "optimal"
- data quality
## Models/Approaches/Concepts
- perceptron
- input layer
- output layer
- feedforward
- backpropagation
- feature learning
	- FC layer
- CNN
	- convolution neural network youtube.com/watch?v=QzY57FaENXg
	- used for image processing
		- dissecting image to get shapes, patterns to get features of image
	- 3 types of layers
		- convolutional layer
		- pooling layer
		- fully-connected (FC) layer
- RNN
	- recurrent neural network
	- used for temporal series
	- problems
		- vanishing and exploding gradients
	- ![[Excalidraw/Drawing 2025-11-25 14.32.34.excalidraw.md]]

# Deep Learning
## What is it (best) for?

adding to NN

& auto feature extraction

## Advantages

- handling missing data
- automatic feature learning
- handling structured and unstructured data
- modular
	- can change aspects of the model without changing the entire model itself

## Disadvantages
- black box
- overfitting
- intensive requirements for training
- data quality

## Models/Approaches/Concepts

- LSTM
	- long-short term memory
	- memory cell
		- LSTM is just RNN with a memory cell at each step
		- input gate, forget gate, output gate
		- forget gate
			- if inputs are enough to activate threshold, then we "forget" the value
			- determines if information seen at time t is something worth remembering
		- input gate
			- acts differently depend on the output of the forget gate
		- output gate
			- outputs everything (normal neuron activation function)

## MORE ON CANVAS

EXAM ON 12/16