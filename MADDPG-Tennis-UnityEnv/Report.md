## Report

**Algorithm used:**
MADDPG - Multi-Agent Deep Deterministic Policy Gradients
 - DDPG is considered as an equivalent of **DQN for continuous control** problems. Hence it is an offline learning algorithm.
 - In DDPG we use **2 networks**, actor which learns the policy, which predicts the optimal action and a critic which learns the action value function Q, which is used to train the policy.
 - There are two copies of each, actior and critic, a local and a target copy, the local copy is up to date and the target copy is updated using the **soft-updates**, with TAU as mentioned below.
 - DDPG uses **Ornstein-Uhlenbeck Process** to add noise to the action output, **for exploration** in continuous action spaces. The hyperparameters used for noise generation are mentioned below with OU_ prefix.\
 - Single actor and critic networks were used for both the agents.


**Model architecture:** Feed-forward network with 2 hidden layers each containing [200,200] neurons. For both actor and critic.

**Hyperparameters:**
- BUFFER_SIZE = 1e6
- BATCH_SIZE = 128
- GAMMA = 0.99
- TAU = 1e-3
- LR_ACTOR = 1e-3
- LR_CRITIC = 1e-3
- OU_MU = 0.
- OU_THETA = 0.15
- OU_SIGMA = 0.1

**Reward Plot** <br>
Averaged over 100 episode <br>
![Reward Plot](./rewards_plot.png)
![Averaged Reward Plot](./averaged_rewards_plot.png)

**Future Work**
- A3C/A2C using 20 parallel models trained.
- Training separate models for different agents.