What is text mining?
- extracting useful patterns, knowledge, or insights from large collections of text
- converts **unstructured** text --> **structured data** for analysis
- used in:
	- information retrieval (Google search)
	- sentiment analysis
	- topic modeling
	- spam detection
	- document clustering
	- chatbots and recommendation systems

Sources of text data
- emails, reviews, tweets, research papers, medical notes, etc.
- data is often noisy, high-dimensional, and context-dependent

Text processing

- typical pipeline
	1. tokenization - splitting text into words or subwords
		1. "I love data mining!" --> \["I", "love", "data", "mining"\]
	2. lowercasing
	3. removing punctuation and stop words ("is", "the")
	4. Stemming
		1. "running", "runs" --> run
	5. lemmatization - converting base words using vocabulary and morphology
		1. "better" --> "good"
	6. Handling negations and emojis (for social media)

Bag-of-Words Representation
- represent the document as a vector of word counts


Text Representation and Feature Extraction

Word Embeddings
- learn **dense vector representations** of words that capture semantics

Word2Vec
- Skip-Gram: predict context given word
- CBOW: predict word given context
- Embedding vectors trained via neural network

GloVe (Global Vectors)
- Uses word co-occurrence matrix
- captures global statistical information


Classical Text Mining Models

- LR
- SVM
- KNN

Modern NLP -- Deep Learning Approaches
Sequence Models
- RNNs / LSTMs / GRUs: Handle sequential text input
	- use sentiment classification, named entity recognition
	- Limitation: vanishing gradients, long dependencies

Transformer Architecture
- replaces recurrence with **self-attention**
- models