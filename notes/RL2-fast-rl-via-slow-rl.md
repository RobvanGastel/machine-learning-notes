## [RL^2: Fast Reinforcement Learning via Slow Reinforcement Learning](https://openreview.net/pdf?id=HkLXCE9lx)

TLDR; The Deep RL  learning process takes a large number of trials to learn tasks. To improve the learning a representation as a recurrent neural network (RNN) is purposed. The RNN receives the same inputs a typical RL algorithm would like observations, actions, rewards and termination flags. The new method RL^2 is done via a general purpose RL ("slow") algorithm. Where the activations of the RNN store the state of the "fast" RL algorithm.

### Key Points
- Bayesian reinforcement learning introduces a way to incorporate good priors into the learning process but is infeasible for all but simple cases.
- The procedure of agent-environment interaction is defined as follows. A trail contains a series of episodes of interaction with a fixed MDP. Where the hidden state is preserved between episodes but not between trials.
- The inner problem has been defined as an MDP instead of an Partially Observable MDP (POMDP). 
- The policy is represented as a general recurrent neural network. Where the tuple (s, a, r, d) is the input with an embedding function φ(s, a, r, d) as input to an RNN. The specific type of RNN used is the GRU. Which after is fed to a fully connected layer followed by a softmax function. 
- For the policy optimization any off-the-shelf RL algorithm can be used to optimize the policy. A choice is made for Trust Region Policy Optimization (TRPO) (Schulman et al., 2015) as it doesn't require excessive hyperparameter tuning. 
- RL^2 yield competitive results with other approaches to solving MABs. As well as tested on larger visual problems.
- Two earlier methods have been introduced to solving mazes A3C paper (Mnih et al.,
2016) and (Heess et al., 2015a) but there is a focus on the memory aspect instead of the fast RL aspect.
- A better architecture may be required for larger horizons as the outer loop was an immediate bottleneck. Algorithms and policy architectures that exploit the problem structure is expected to significantly boost the performance.

### Notes
New to the policy optimization algorithm TRPO attached paper is (Schulman et al., 2015).