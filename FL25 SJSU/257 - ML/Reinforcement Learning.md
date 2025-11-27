
**computer agent learns to perform a task through repeated trial and error interactions with a dynamic environment**

### RL Elements
- Agent
- Environment
- Reward/Value
- Policy

focusing on behavioral, non-deterministic data
- ex playing a video game

Disadvantages:
- very costly
- very slow to train
- may not get the result wanted --> must try again

#### Positive Reinforcement
when an event occurs do to a particular behavior, it increases the strength and frequency of the behavior

Advantages: 
- maximized performance
- can sustain agent (behavior) change for a long period of time

Disadvantages: 
- too much PR can lead to an overload of states and can diminish results

#### Negative Reinforcement
defined as strengthening of behaviors, because a negative condition is stopped or avoided

Advantages:
- increases behavior
- provide defiance to a minimum standard of performance

Disadvantages:
- it only provides enough feedback to meet up with the minimum behavior required

#### Model-based
- build a model of the environment by sampling the states, taking actions and observing the rewards
- for every state and a possible action the model predicts the expected reward and the expected future state.
#### Model-free
- do not build an explicit model of the environment
- closer to trial-and-error algorithms that run experiments with the environment
##### Value based
Could give +/- value for action
##### Policy based
set of do's and don't's that the agents can do 

##### Q-Learning
- what can be done in said environment for this agent?
- Terminology
	- States(S)
	- Actions(a)
	- Rewards
	- Q(St+1, a): expected optimal Q-value of doing the action in a particular state
	- Q(St, At): it is the current estimation of Q(St+1, a)
	- Q-table: a data structure of sets of actions and states, and we use the Q'learning algo to update the values in the table
	- Temporal Differences: used to estimate the E(Q(St+1, a)) by using the current state and action and previous state and action

![[Screenshot 2025-10-30 at 1.52.24 PM.png]]

each iteration is called an **episode**

[[Dynamic Programming#Bellman Equation]]

Example for path traversal

| Value Based                                                                                                                | Policy Based                                          |
| -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| reward for moving towards goal is 1<br>reward for taking the wrong path (falling in the hole) is 0<br>reward for idle is 0 | move towards the goal<br>dont fall in the pit<br>move |


| E2* |     | X   | E7  | E8  |
| --- | --- | --- | --- | --- |
| X   |     | X   | E6  | X   |
| E2  | E3  | E4  | E5  | X   |

Q1=(1)
Q2=1(1 + 0 + 0) = 1
Q3_1=1(1+1+0) = 2
(2 available paths at step 3, chose the opt for brevity)
Q4=2(1+0)
Q5=2
Q6=2
Q7=2
Q8=2

(overall quality)
SUM(Q) = 7

Starting at E2* would get SUM(Q) = 9

looking for optimal quality = MINIMUM TOTAL
- think path length

