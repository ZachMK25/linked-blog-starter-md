Perceptron: basic binary classifier (outputs 0 or 1) based on stimuli (inputs * weights)

| Advantages                                                                                                                                                                                                     | Disadvantages                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Effective visual analysis<br>Processing of unorganized data<br>Adaptive structure<br>	- can adjust to new environments<br>	- ex: same NN model used for detecting rot in potatoes --> used for cancer research | Hardware requirement:<br>	- more compute<br>Incomplete results<br>Data suitability |
### NN Architecture
#### Input Layer
information from the outside world. 1 node per feature

#### Hidden Layer
inner workings and decisions that take place
different combinations of different features take place at different levels

#### Output Layer
Result. Can have one or multiple nodes (ex: multiclass situation)

#### Nodes
Each node is its own linear regression

#### Propagation
If an output exceeds a given threshold, it activates the node, passing the data to the next layer

##### Feedforward Propagation
processes data in one direction. Data is sent from one node to ALL nodes in next layer (not all nodes look at all features in data, however)

##### BackPropagation
mechanism that allows NN to *self-correct* by adjusting the weights being inserted in the nodes
~gradient descent in NN form

