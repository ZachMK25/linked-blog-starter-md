grouping/partitioning/segmentation
## Different Approaches for image segmentation
### Histogram approach (look at pixel intensity distributions)
1. binning
2. looks at distribution of data
3. naive
### k-means clustering
1. extract features
	1. motion vectors, rgb values, etc.
2. consider n feature vectors f1, f2, ..., fn
3. consider k segments
4. need to have centroids converge to get final groups
	1. can sample from dataset to get better starting points for centroids rather than random points
5. how to choose k?
	1. elbow method?
### mean-shift clustering
1. computationally expensive
2. all the points the climb to the same peak belong to the same cluster
3. REVIEW LECTURE RECORDING
### graph-based clustering
1. can cut graph based on existing algorithms (think 347)
2. distance formula
3. partition the graph
4. keep going until cost value converges(?)
5. REVIEW LECTURE RECORDiNG

### Auto Encoder (AE)
Encoder f_θ and Decoder d_ϕ

![[Drawing 2025-10-17 18.26.17.excalidraw]]

Neural Network that learns an _Identity Function_

Uses: Dimensionality reduction

ex: input = (100, T, 10)

use RNN or LSTM with 128 neurons --> (100, T, 128)

FCN output at given timestep only depends on input

RNN or LSTM at given timestep depends on input and previous output
- concept of *memory/latch*
- Can take **last timestep** output and say that its a summary of *all previous timestep outputs*

TD = Time Distributed Dense Layer

![[IMG_7986.heic]]


#### Background: Analog to Digital
- sampling - look at the values at discrete time slots
	- sampling frequency determines the rate at which the time value is being updated
- also need to discretize the y axis (amplitude)
	- quantization

Ex: 2 seconds, 16KHz
32K points

Ex: Brainscan with 1 subject, 5 seconds, 1000Hz sampling rate, 31 sensors
(1, 5000, 31)

### Variational Auto Encoder


### Self-Supervised Clustering

