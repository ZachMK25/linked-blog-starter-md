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

1. calculate distance (euclidean is preferred)
$$
	dist = \sqrt{(x_1-x_2)^2 + (y_1-y_2)^2}
$$
2. pairwise get all distances compared to existing points
3. find k=2 vectors with the lowest distance (A and B in this case)
4. (Cat, Cat) --> predict Cat
5. if (Cat, Dog), then inconclusive bc no majority in voting


## Decision Tree

## Classification based on Bayes' Theorem

## SVM

## Basics of Neural Networks


Next-Class: N-sample methods