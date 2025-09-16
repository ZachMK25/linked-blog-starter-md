9/10
- change "without" to "with" in hw1

5.5s for without video
3m for with video


Project Presentation
- groups of 3-4???

## Dynamic Programming

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

