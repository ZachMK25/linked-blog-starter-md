Pros:
- low post-development cost
- labelled datasets
- specific to problem-set/domain

Cons:
- time consuming: training for supervised learning needs a lot of computation time and it requires a training process
- application limitations: supervised learning cannot handle all complex tasks in machine learning
	- inflexible
- higher initial cost

## Classification
### Algs
- **KNN**
	- identify the nearest neighbors of a given query point, so that we can assign a class label to that point
	- only votes that count are the `k` nearest neighbors
		- closest can be determined by euclidean, manhattan, etc.
	- no centroids
	- ![[Screenshot 2025-09-25 at 1.59.24 PM.png]]
	- optimal k?
		- try a range and look for elbow
- **Support Vector Machines (SVM)**
	- simply assigns binary classification
		- can be linear or non-linear
	- constraint is also its advantage
		- can create a multi-class classifier by creating pairs of classifiers
		- ex to get A,B,C, run AB, BC, AC
			- layer results to get final classes
			- ex:![[Drawing 2025-09-25 14.16.44.excalidraw]]
		- **C - Parameter**
			- margin of error for the borderline points
			- ![[Screenshot 2025-09-25 at 2.19.35 PM.png]]
			- low c --> low regularization --> underfitting
			- high c --> high regularization --> overfitting
	- 
- Decision Trees
	- **Random Forest**
		- 
	- **XGBoost**
		- 

## KNN vs K-Means
DIFF = HOW GROUPING HAPPENS
- centroid vs voting