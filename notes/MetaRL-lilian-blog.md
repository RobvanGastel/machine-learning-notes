## [Meta Reinforcement Learning](https://lilianweng.github.io/lil-log/2019/06/23/meta-reinforcement-learning.html)

TLDR; Meta Learning for Reinforcement learning, introducing adjustments to classical meta-learning algorithms to work within the Reinforcement learning framework. Where the same types of meta-learning algorithms Model-based, Metric-based, optimization-based are discussed. 

### Key Points
- A standard MDP< S, A, P, R> with a set of states S, a set of Actions A, the transition probability function and reward function. Where the standard S and A have a stochastic policy which, would get inputs compatible across different tasks. 
- Both Meta-RL and RL^2 implement an LSTM policy and the LSTM's hidden states serve as memory for tracking characteristics of the trajectories.
- Meta-RL has three key components; A model with memory (without this Meta-RL wouldn't work)
- a Meta-Learning algorithm refers to how we can update the model weights to optimize for solving unseen tasks. In both Meta-RL and RL^2 this is done by gradient descent.
- A distribution of MDPs, the agent is exposed to a variety of environments during training and has to learn how to adept to different MDPs.
- In Meta-RL we impose certain type of inductive biases from the task distribution and store them in memory.
- The classical algorithms consist of Model-based, Metric-based, Optimization-based.
- Meta-Learning Algorithms for Meta-RL:
    - Optimizing model weights for Meta-Learning, see MAML, Reptile.
    - Meta-learning Hyperparameters, with γ discount factor and λ bootstrapping factor. Meta-gradient RL (Xu et al., 2018) considers them as meta-parameters, that can be trained online. Experiments in the paper adopted the meta-objective function same as TD(λ) algorithm.
- Meta-learning the Exploration Strategies
    - Proposed MAESN (Gupta et al, 2018) as simply adding random noise cant capture task-dependent or time-correlated exploration strategies.
- Episodic Control, is introduced to improve sample efficiency. To as a solution to avoid forgetting and improve generalization. 
    - An episodic memory keeps explicit recordings of past events and uses these recordings directly as a point of reference for making new decisions.
- Training Task Acquisition, we can build a distribution of MDPs by modifying the reward configuration or environment.    
- Learning with Random Rewards, An MDP without a reward function R is known as a Controlled Markov Process (CMP), defined as < S, A, P>. We acquire a variety of tasks by generating a collection of reward functions R that encourage the training of an efficient meta-learning policy. Gupta et al. (2018) proposed two unsupervised approaches.

### Notes
Interesting read as follow up on this introduction is [Botvinick et al. (2019)](https://www.cell.com/action/showPdf?pii=S1364-6613%2819%2930061-0). Expansion on classical RL algorithms are covered in previous post [Meta-Learning: Learning to Learn Fast](https://lilianweng.github.io/lil-log/2018/11/30/meta-learning.html). Interesting, to expand up on.