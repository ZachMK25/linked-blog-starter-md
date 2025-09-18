
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
Cost of going from Xi to End Node

for `n` nodes, max of `|E| = n-1` --> table size of `n x (n-1)`
- theoretical max of `n-1`, but in many cases its fewer (ie shortest path does not include all nodes)

Example


|     | 1st          | 2nd | 3rd | 4th | 5th | 6th... | n-1th |
| --- | ------------ | --- | --- | --- | --- | ------ | ----- |
| A   | V1(XA) = inf |     |     |     |     |        |       |
| B   | V1(XB) =     |     |     |     |     |        |       |
| C   | V1(XC)       |     |     |     |     |        |       |
| D   | ...          |     |     |     |     |        |       |
| E   |              |     |     |     |     |        |       |
| F   |              |     |     |     |     |        |       |
| G   |              |     |     |     |     |        |       |
