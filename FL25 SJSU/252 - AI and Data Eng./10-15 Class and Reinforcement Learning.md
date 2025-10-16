1. HPC available
2. hw2
	1. get sheet
3. presentation
	1. ONLINE NEXT WEEK
	2. overview of paper + our contribution
		1. ensemble model + comparison of results?
		2. maybe give 
	3. with video of code running?
	4. ~ 10 minutes + Q&A
4. course make-up
	1. online
	2. look for announcement regarding timing

## Review
### DP: Deterministic

### MDP: Stochastic
- recall: probabilities associated with actions
	- slightly random

<S, A, T, R>
S = State
A = Actions
T = Transition Probabilities
R = Reward


## Reinforcement Learning
We don't know transition probabilities (T) and sometimes we don't know reward (R)

π: Policy that maps S --> a

![[Markov Decision Processes (MDP) and Reinforcement Learning (RL)#Discounted Reward]]



### Policy Iteration

1. Initialize π(s) with arbitrary values
2. repeat until convergence
	1. Policy evaluation: compute the value function for π, i.e., solve for V_π(s) values
	2. Policy improvement: compute a new policy, π', based on V_π(s) values
		Given all values V_π(s), compute a new policy π'(s):
$$
			π'(s) = \text{argmax}_a Σ_{s'}T(s, a, s')(R(s, a, s') + ℽV_π(s'))
$$


F (input/video/image) --> loss

Image/video --> 


Episode (also called trial)

- think of learning policies for repeated tasks
- these tasks have a terminal state after which you stop getting reward
- we call one execution from start to terminal state as an *episode*

**If we don’t know T or R, we can't use MDP --> USE RL**

## Two Approaches

suppose R(s, a, s') is known, but T(s, a, s') is unknown

1. Model-Based: Execute each (s,a) pair many, many times. Estimate T(s, a, s') empirically. Then find the optimal policy and value function by, for example, value iteration
2. Model-Free: Directly find the optimal value function (and the optimal policy)


# EXAM
Given equations and episodes, run it a few times and get expected values