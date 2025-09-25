Pros:
- low post-development cost
- 

Cons:
- time consuming: training for supervised learning needs a lot of computation time and it requires a training process
- application limitations: supervised learning cannot handle all complex tasks in machine learning
- higher initial cost


## Classification
### Algs
- KNN
	- identify the nearest neighbors of a given query point, so that we can assign a class label to that point
	- only votes that count are the `k` nearest neighbors
		- closest can be determined by euclidean, manhattan, etc.
	- no centroids
	- ![[Screenshot 2025-09-25 at 1.59.24 PM.png]]
	- optimal k?
		- try a range and look for elbow
- Support Vector Machines
- Decision Trees
	- Random Forest
	- XGBoost

## KNN vs K-Means
DIFF = HOW GROUPING HAPPENS
- centroid vs voting