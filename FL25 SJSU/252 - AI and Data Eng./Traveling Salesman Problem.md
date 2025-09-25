approximations
- backtracking
- O(2^n)

brute force?
= O(n!)

Walkthrough

Given graph G with edges e1, ... en

assign variables x1, ... xn to each edge

x1=0, then e1 is not a part of final solution, vv


objective function: minimize traveling cost (w--> * x-->)
- where w--> is the vector representing all weights
- and x--> is the vector representing the true/false of edges included
- HOWEVER, this includes many edges that are not part of the final circle
	- Split into e_circle and e_non-circle, such that edges are split into which are counted and which aren't
constraints: create circle

for every node, 
- all incoming edges X's must sum to 1 (ie exactly one incoming edge per node)


HW:

Why do we need the last constraint in the IP TSM problem?
- must be circle


What about if we allow no more than 2 visits?
- Find a MST (min spanning tree)
- "Trace" a DFS on the MST to explore path
- skip vertices already visited. Use edges not included in MST when skipping
- since we're traversing each edge {twice}() then the cost is at worst 2\*optimal


## KNAPSACK PROBLEM ON EXAM!!!