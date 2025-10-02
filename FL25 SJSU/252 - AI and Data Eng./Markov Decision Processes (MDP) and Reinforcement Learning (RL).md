
## Pac-Man
- different states for different locations on game board
- can model decisions with a graph
- maximize "rewards"

Can think of it as [[Dynamic Programming#Bellman Equation]]

use value iteration to update the table while stepping through the problem
- table will converge to final state

Cost-to-Go

### Uncertain Navigation
- actions are **not deterministic**
- 70% to go north, 30% to end in one of other neighboring cells
	- P((0,2) | (0,1)) = 70%
- instead of open-loop plan, we want decision making feedback policies --> **MDP**

#### Formulation
- S: set of states that robot can reach
- A: set of actions that robot can take
- T: transition function, T: S x A x S --> R+
- T(*s*,*a*,*s'*) = probability that the robot ends in state *s'* by applying action *a* from state *s*
- R: Reward function, R: S x A x S --> R+
- R(*s*,*a*,*s'*) = reward obtained by executing action *a* to transition from *s* to *s'*

MDP is the tuple <S, A, T, R>

In MDP, both transition probabilities and rewards only depend on the present state, not the history of the state. This is called the **Markov Property**
- R depends on S_t, a_t
Goal: Find a policy (i.e., mapping from states to actions that give a plan for the robot to follow)

Objective Functions
- in general, maximize sum of rewards collected

Discounted Reward
maximize
$$
Σ^∞_{t=0}ℽ^tR(s_t,a_t,s_{t+1})
$$
for ℽ in (0,1]

gamma is discount factor
- models the fact that immediate reward is better than far out reward
- ensures that the sum of rewards is always finite

Expected value
- cannot get full value of reward bc of probability
- ex: 70% to move North to position (0,2) with reward X
	- --> 0.7\*X

Value Function
- V\*(*s*) is the optimal (discounted) reward-to-go
- that is, if you follow the optimal policy starting from a state *s*, til you reach the goal state *s_g*, you will collect (in expectation) a reward to V\*(*s*) 
- Computing V\*(*s*) is not as simple

Value Iteration
-  V_i(*s*): estimate of V\*(*s*) in the *i*th iteration
- we will start with  V_0(*s*) = 0 for all *s*
- in each iteration, improve our estimate
- repeat until no further improvement is possible
	- does this converge? does this converge to V\*(*s*)?
	- ## HOMEWORK: HOW MANY VALUES TO CHECK FOR IT TO CONVERGE
	- compute V_{i+1}(*s*) greedily
		- n^2
		- for n nodes, need to check all neighbors for best cost
			- INCOMING COST TO COME
			- OUTGOING COST TO GO
		- Propagating probabilities and expected values????
		- see slides for exact formula
		- set some threshold for being close enough to V\*(*s*)

PSEUDOCODE:

DP
\# of options = \# of neighbors
```
for each row:
	for each col:
		for each option:
			// BELLMAN EQ
			V_{i+1}(S) = ?
```


MDP
\# of options = set of actions
```
for each row:
	for each col:
		for each option:
			// BELLMAN EQ
			V_{i+1}(S,a) = ?
			= sum of probs to get to each s' \* rewards of getting to each s'
			= 70%*X + + ℽVi(s'x) + 15%*Y + + ℽVi(s'y) + 15%*Z + ℽVi(s'z)
```

Choosing value for epsilon
- balance of optimality and efficiency
- can be closer to V\*(*s*) but takes more time to fill out table, v.v.