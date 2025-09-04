Undirected vs Directed

**neighborhood** of a vertex:
	Ni = {vj ∈ V | (vi, vj) ∈ V}

Complete graph: 
- each node is connected to every other node

Bipartite graph:
- graph divided into two groups, where one group is only connected to every other node in the other group
- ![[Excalidraw/Drawing 2025-08-27 18.18.55.excalidraw.md]]

Weakly connected:
	not every pair has path between them (ex: directed)
Strongly connected:
	every pair of vertices has a path between them


## Dynamic Graph
- changes over the duration of a system's execution
- mobile systems


### Degree Matrix
- for an undirected matrix, is the diagonal matrix of vertex degrees
- cardinality of neighborhood (how many neighbors)
- symmetric
- ex: triangle is:

| 2   | 0   | 0   |
| --- | --- | --- |
| 0   | 2   | 0   |
| 0   | 0   | 2   |
### Adjacency Matrix
- if edge (vi,vj) exists, the 1
- else 0
- symmetric if undirected
- ex: triangle

| 0   | 1   | 1   |
| --- | --- | --- |
| 1   | 0   | 1   |
| 1   | 1   | 0   |

### Laplacian Matrix
- Adjacency matrix for directed graphs
rules:
- -1 if vi is the tail of ej
- 1 if vi is the head of ej
- 0 otherwise

difference between degree and adjacency matrices
- Δ(G) - A(G) = L(G)

properties:
- row must sum to 0 for a directed graph
- one eigenvalue must be 0, with an eigenvector of all 1s
- **positive semidefinite** (doesn't hold for disconnected graphs)
$$
	x^T ⋅ L(G) ⋅ x >= 0
$$
	--> all eigenvalues will be non-negative
	
	REVIEW EIGENVALUES/VECTORS

ex: triangle

| 2   | -1  | -1  |
| --- | --- | --- |
| -1  | 2   | -1  |
| -1  | -1  | 2   |
represents graph, but doesn't tell geometry information


HOMEWORK: PROVE THAT LAPLACIAN MATRIX IS POSITIVE SEMIDEFINITE

| x1  |     |
| --- | --- |
| x2  |     |
| x3  |     |
Show that:
$$
x^T A x >= 0
$$
for all x, where A is the laplacian matrix

example using laplacian matrix from above:

$$
x^T A x = (2x_1^2 - x_1x_2 - x_1x_3) + (-x_1x_2 + 2x_2^2 -x_2x_3) + (-x_1x_3 -x_2x_3 + 2x_3^2)
$$

$$
= 2x_1^2 + 2x_2^2 + 2x_3^2 - 2x_1x_2 - 2x_1x_3 - 2x_2x_3
$$

the value would be dominated by the x^2 terms and thus can never be negative?

heuristic: estimation
- estimate traveling distance from node to destination
- get to choose
	- ex: euclidean distance, manhattan distance

![[Excalidraw/Drawing 2025-08-27 19.59.04.excalidraw.md]]

| node | *d* | *h* (curr to P) | *g* = *d*+*h* |
| ---- | --- | --------------- | ------------- |
| A    | 0   | 16              | 16            |
| B    | 5   | 17              | 22            |
| C    | 5   | 18              | 18            |
| D    | 12  | 19              | 28            |
| E    | 12  | 20              | 28            |
| F    |     | 17              |               |
| G    |     | 11              |               |
| H    | 13  | ...             |               |
| ...  |     |                 |               |


### Open and Closed Lists
- open lists --> frontiers of expansion
- new nodes that haven't been visited but can be visited based on current visited locations
	- ex: in example above, if visited = {A, B, C}, then frontier would be {D, H, E}
- 