## [Learning to Reinforcement learn](https://arxiv.org/pdf/1611.05763.pdf)

TLDR; The idea of meta-RL is explored where a new novel approach is suggested using the Advantage Actor-Critic algorithm and performing varying experiments have been performed such as multiple settings for multi-armed bandits, the "Harlow" task and solving of mazes. 

### Key Points
- Seen from previous work is that recurrent neural networks can support meta-RL in fully supervised context.
- The approach described in the paper, is by usage of RNN for the meta variables in similar fashion to RL^2.
- For all RL the Advantage Actor-Critic Algorithm was used Mnih et al. (2016) and Mirowski et al. (2016). Where entropy regularization and a combined policy and value estimation loss follows the paper of n Mirowski et al. (2016) closely. 
- The performance is measured on different cases for multi armed bandits and compared. 
- With as goal for all the experiments will be to examine how meta-RL adapts to invariances in task structure.
    - Bandits with independent arms, performance of the LSTM A2C model is close to the Gittins approach.
    - Bandits with dependent arms, where the LSTM A2C is able to deterministically exploit the highest-paying arm. 
    - (Non-stationary) Restless Bandits, where now the return varies per time step.
- A difference is described between the model-free approach that caches values of actions in states e.g. TD(1) Q-Learning and a model-based approach that learns the internals of the environment and evaluates the value of actions at the time of decision making through look-ahead planning (Daw et al., 2005). THis idea is widely used in neuroscience literature.
    - "Our interest was in whether meta-RL would give rise to behavior emulating a model-based strategy, despite the use of a model-free algorithm (in this case A2C) to train the system weights."
- The Harlow task (described in more detail in the paper) displays that Meta-RL can operate effectively within a visually rich environment. 
- There is a lot of research not labelled as Meta-RL even though they do involve the key ingredients of deep meta-RL – a neural network with memory, trained through RL on a series of interrelated tasks.


### Notes
Two of the earliest papers mentioned discussing the idea of meta-learning are (Schmidhuber et al., 1996; Thrun and Pratt, 1998). With (Thrun and Pratt, 1998) containing some theoretical notions of bounds. Also the idea of having an inner and outer loop for the meta-learning task.