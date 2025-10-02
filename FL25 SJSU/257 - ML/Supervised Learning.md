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
- **Decision Trees**

- continuously split by feature

	- **Random Forest**
		- combining multiple trees
		- **what makes it random?**
			- organize and correlate features randomly
			- **Out of Bag (OOB)**:
				- no actual result came from it
				- stops prior to leaf node
				- refers to points not in training
			- **Gini Index**:
				- metric used within each tree to measure the quality of a potential split
			![[Screenshot 2025-09-30 at 2.03.16 PM.png]]
	- majority vote between the trees for final answer
		- or average outputs in case of regression
	- ```
	  # Create RF classifier of 100 trees
	  clf = RandomForestClassifier(n_estimators = 100)
	  
	  # Training the model on the data
	  clf.fit(X_train, y_train.values.flatten())
	  
	  y_pred = clf.predict(X_test)
	  
	  ```
	- ![[Screenshot 2025-09-30 at 2.09.07 PM.png]]
	- **XGBoost**
		- each tree is built on the previous tree
		- use the error from the previous tree that is moved on to the next tree
		- ![[Screenshot 2025-09-30 at 2.21.58 PM.png]]
		- 
$$
T_1 = ax_1 + bx_2 + cx_3 + dx_4 + ex_5
$$
$$
T_2 = ε_1(T_1)
$$
$$
T_3 = ε_2(T_2)
$$
		...
$$
Output = Σ^n_{i=1} C
$$
		Pros:
		- High accuracy on structured/tabular data  
		- Regularization reduces fitting issues  
		- Handles missing values natively  
		- Fast and scalable
		
		Cons:
		- Complex hyperparameter tuning  
		- Slower training (compared to Random Forest)  
		- Risk of overfitting if poorly tuned

## KNN vs K-Means
DIFF = HOW GROUPING HAPPENS
- centroid vs voting