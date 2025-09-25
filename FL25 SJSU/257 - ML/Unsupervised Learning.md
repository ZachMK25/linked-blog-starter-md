Give the algorithm the ability to identify the patterns within the data
- NO TARGET INCLUDED IN DATA

### Pros
- Flexibility: Unsupervised learning is flexible in that it can be applied to a wide variety of problems, including clustering, anomaly detection, among others.
- Exploration: Unsupervised learning allows for the exploration of data and the discovery of novel and potentially useful patterns that may not be apparent from the outset,
- Low cost: Unsupervised learning is often less expensive than supervised learning because it doesn’t require labeled data, which can be time-consuming and costly to obtain.

### Cons
- Lack of guidance: Unsupervised learning lacks the guidance and feedback provided by labeled data, which can make it difficult to know whether the discovered patterns are relevant or useful,  
- Sensitivity to data quality: Unsupervised learning can be sensitive to data quality, including missing values, outliers, and noisy data,  
- Scalability: Unsupervised learning can be computationally expensive, particularly for large datasets or complex algorithms, which can limit its scalability.  

## Types of UL
- Clustering
	- K-Means
	- DBScan
- Dimensionality Reduction
	- PCA
- Association Rules
	- Apriori
## Clustering
- Overlapping
- Agglomerative
- Divisive
- Probabilistic
- Density-based
	- similarly concentrated data points and separates from sparsely populated areas

### DBSCAN

Chaining Rule:
continue to chain as long as all data points are all in the radius
- based on epsilon (radius) and MinPts (number of neighbors required to chain)

#### Advantages:  
- Finds arbitrarily shaped clusters  
- No need to pre-specify k  
- Robust to noise/outliers  
#### Disadvantages:  
- Sensitive to ε and minPts 
- Struggles with varying densities  
- Not effective in high-dimensional data

## PCA
- 'Helper' model
	- PCA never used by itself
- NOT Linear Regression
	- PCA is unsupervised while Lin Reg is
- Cannot use unless we can see that there is *some* correlation between some of the features
	- ex: use a heatmap ![[Screenshot 2025-09-18 at 2.13.42 PM.png]]


## Apriori Algorithm
- **Support** - the ratio of the number of transactions in which item x appears to the total number of transactions
	- popularity of x
- **Confidence** - the likelihood of the item y being purchased when item x is purchased. This method takes into account the popularity of item x

- **Lift** - the likelihood of the item y being purchased when item x is sold. This method takes into account the popularity of item y
