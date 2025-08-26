Goal: use existing data to predict unknown or future values
Requires labeled data (supervised)

1. Classification
	- input: features + categorical labels
	- output: assign new data to classes
	- algos: Decision trees, SVM, NN
	- ex: 
		- email is spam vs not spam
		- patient has disease vs. healthy
			- CONCERN
				- less margin of error for health compared to email, but harder to get training data (HIPAA) and get data labeled (need specialist to determine if MRI shows disease or not)
	- accuracy: # of correct predictions, F1 score (see next lecture), ROC curve, Confusion Matrix
	- loss function: mask decision boundaries, probability of classification

 2. Regression
	 - input: features
	 - output: predict a continuous variable for a set of inputs
	 - accuracy: N/A, use loss functions
	 - loss function: Mean Square Error, Mean Absolute Error, etc.
	 - algorithms:
		 - linear reg., random forest regression
	 - examples:
		 - predicting house prices
		 - predicting temp tomorrow