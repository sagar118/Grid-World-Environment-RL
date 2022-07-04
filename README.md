# Grid World EnvironmentRL
The main objective of this project is to implement a reinforcement environment following OpenAI Gym standards. We focus on implementing deterministic and stochastic environments that are based on Markov Decision Process. The agent is trained using Q- learning and Double Q-learning tabular methods. The agent derives an optimal policy to navigate the environment to reach the goal and avoid obstacles. Hyper-parameters were tuned to find the optimal results and the performance of the agent on both deterministic and stochastic environments was analyzed.

## Implementation
The project was implemented following OpenAI Gym standards.

### Environment
The environment is a 5*5 Grid World that consists of 25 states. The environment is fully observable, Single-agent, Episodic, and Discrete.

<p align="center">
  <img width="647" alt="image" src="https://user-images.githubusercontent.com/24275587/177084337-5fd18223-ad3d-4972-9063-2a12694a18ba.png">
</p>

### State set
It is the set of all possible states present in the environment.
`𝑆 = {s1, 𝑠2, 𝑠3, 𝑠4, 𝑠5, 𝑠6, 𝑠7, 𝑠8, 𝑠9, 𝑠10, 𝑠11, 𝑠12, 𝑠13, 𝑠14, 𝑠15, 𝑠16, 𝑠17, 𝑠18, 𝑠19, 𝑠20, 𝑠21, 𝑠22, 𝑠23, 𝑠24, 𝑠25}`
State s1 is the starting state and state s25 is the goal state. States s4, s13 contains reward of +5 and +10 respectively. State s16 contains a reward of -3. States s9, s12 are dead states i.e. when an agent reaches that state the environment resets and the agent receives a reward of -50 in each state. State s25 contains a reward of +50. All the other states have a reward of -1. An episode ends if the agent reached the goal state or any one of the dead states.

### Action set
It is the set of actions that an agent can take in the environment. For the grid world environment the action set is given below: 
`𝐴 = {𝑈𝑝, 𝐷𝑜𝑤𝑛, 𝐿𝑒𝑓𝑡, 𝑅𝑖𝑔h𝑡}`

### Rewards
Reward set: It is the set of all possible rewards an agent can receive from the environment after taking an action. For the grid world environment the reward set is as follows: `𝑅 = {−1, −3, 5, 10, −50, 50}`

## Hyperparameters

1. Epsilon: It defines the degree of randomness, whether the agent should explore different states or exploit the knowledge already learned. Initially, we would want the agent to explore and determine the action-value values for different states and actions. As the training progresses we want to exploit the knowledge and take the actions that produce the highest reward. Hence, we decay epsilon as the training progresses.
2. Alpha: It defines the learning rate of the agent i.e. how fast the agent is trained for the given problem. For a large value of alpha, the agent will train faster but may not produce the optimal results. On the other hand, for a small value of alpha, the agent may learn the optimal policy but it will take a longer time.
3. Gamma: It defines the discount factor which penalizes future rewards. It determines how important are the future rewards since these rewards can be uncertain and not give any immediate benefits.
4. Epsilon: The number of epochs the agent is trained.

## Experiments
To solve the environment we have used Q-learning and Double Q-Lerning algorithms to train our agent. We experiements with vairous parameters and provided detailed explaination in our report. Also, we tried keeping the environment deterministic and stochastic to see how the agent behaves in such scenario. Finally we have compared the performance of both the algorithms on both deterministic and stochastic environments. More information can be read in the report.
