
Text --> NLP
Sentiment analysis on text
- text --> + or -

Whenever one-shot models are not doing well, can use annotated portion of data to fine-tune

Frequency count: simple histogram distribution of word occurrences

Scene Understanding
- image to text
- tries to describe the scene of the image with text

Speech recognition (ASR) audio --> text
- whisperX
- kaldi
- espnet

Frequency: How often a link is opened, etc.
- very important for data mining & determining habits

GNN
- Graph Neural Nets
- Nodes and Edges

G CNN
- Graph Convolutional NN
- input data --> graph --> graph feature metrics & adjacency matrix
	- GFM
		- how many nodes I have, and how many features per node
	- AM
		- (N,N)
			- includes some weight on each edge

Graph Attention Network (GAN)

## Privacy and Ethics

PII = Personally Identifiable Information
- names
- photos
- etc.

Need informed consent

Need to secure data in database
- only available to access for authorized users
- encryption standards


SPII = Sensitive Personally Identifiable Information
- bank information
- SSN
- etc.

Fairness
- model is not biased
	- ex: speech recognition good for American English but not other accents/dialects
- model should not be a black box

