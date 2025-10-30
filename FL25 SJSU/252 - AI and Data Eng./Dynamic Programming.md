 
Suppose that the optimal path from a to e goes through b
Jab = cost of going a to b
Jbe = cost going b to e
Jae\* = Jab + Jbe = optimal cost of a to e
\* mean optimal

Claim: if a-b-e is the optimal path from a to e, then b-e is the optimal path from b to e
- assume there is a path b-e that is better
- then Jae\* (original) >= Jae' (new path)
- violates assumption that Jae\* was optimal to start
- claim holds true by contradiction

ex:

| 1   | 1   | 3   |
| --- | --- | --- |
| 2   | 2   | 1   |
| \*  | 3   | 2   |
- can only go up or right

GREEDY approach

def: v(2,2) --> max of (i, j)

objective: maximize v(2,2)


## Bellman Equation
can separate into constant amount of work, and recursive call on a subproblem

- relationship between last iteration and current iteration

$$
V_k(x_i) = min\ \{{C(x_i, x_j) + V_{k-1}(x_j)}\}
$$
$$
x_j\ N(x_i)
$$
Cost of coming from XA to Xi

`k` = number of edges allowed to use to get from XA to Xi

for `n` nodes, max of `|E| = n-1` --> table size of `n x (n-1)`
- theoretical max of `n-1`, but in many cases its fewer (ie shortest path does not include all nodes)

Example

**Row = number of steps allowed**
- ex: A-->D is checked in 1st iteration
- A --> B --> D is checked in 2nd iteration
- etc

|     | 0th | 1st         | 2nd              | 3rd | 4th | 5th | 6th... | n-1th |
| --- | --- | ----------- | ---------------- | --- | --- | --- | ------ | ----- |
| A   | 0   | V1(XA) = 0  | 0                | 0   |     |     |        |       |
| B   | inf | V1(XB) = 10 | 10               |     |     |     |        |       |
| C   | inf | V1(XC) = 20 | 20               |     |     |     |        |       |
| D   | inf | ... = 27    | min(23, 27) = 23 |     |     |     |        |       |
| E   | inf | inf         | 22               |     |     |     |        |       |
| F   | inf | inf         | inf              |     |     |     |        |       |
| G   | inf | inf         | inf              |     |     |     |        |       |

For all incoming edges, need to check to find the shortest path from the starting node


Computational Cost

$$
O(|V| * (n-1) * Δ)
$$
where Δ = maximum degree of vertex
- max num of neighbors per node


## Stochastic Cases

### Markov Decision Process
