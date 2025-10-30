
**computer agent learns to perform a task through repeated trial and error interactions with a dynamic environment**

### RL Elements
- Agent
- Environment
- Reward
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