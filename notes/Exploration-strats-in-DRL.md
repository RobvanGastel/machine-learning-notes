## [Exploration Strategies in Deep Reinforcement Learning](https://lilianweng.github.io/lil-log/2020/06/07/exploration-strategies-in-deep-reinforcement-learning.html)

TLDR; The topic of exploration vs exploitation in RL. Common Classic exploration techniques for (Deep) RL. Two key problems in RL exploration called the Hard-Exploration and Noisy-TV problem. Ways of solving these problems by Count-Based Exploration, Prediction-Based Exploration and Memory-Based Exploration. A large variation of solutions have been brought forward, under which the exploration techniques in Go and Agent57. The topic of exploration contains a lot more ideas than this article entails. 

### Key Points
- Classic Exploration Strategies:
    - Epsilon-greedy, Upper confidence bounds, Boltzmann exploration, Thompson sampling
    - With the following strategies being for Deep RL:
    - Entropy loss term, add an entropy term H(policy) into the loss function, encouraging the policy to take diverse actions.
    - Noise-based Exploration, add noise to the possible parameters.
- Key Exploration Problems:
    - The Hard-Exploration problem, refers to exploration in an environment with very sparse or deceptive rewards. Random exploration in these scenarios can rarely discover successful states. Montezuma's Revenge is a concrete example.
    - The Noisy-TV problem, Imagine an agent that is rewarded with seeking novel experience, a TV with random and unpredictable noise will attract his attention forever. The agent will stop progressing.
- Intrinsic rewards as exploration bonuses, helps for solving the Hard-Exploration problem, reward is composed out of two terms r = r^{extrinsic} + \beta r^{intrinsic}. Where \beta regulates the balance between exploration and exploitation.
    - Inspired by intrinsic motivation in psychology.
    - methods of bonus exploration rewards can be categorized as; Discovery of novel states and Improvement of agent's knowledge about the environment.
- Count-Based Exploration, We need to keep a count to measure if a state occurs often and is novel. 
    - This becomes harder when the state space is continuous or high-dimensional. 
    - Counting by density estimation, this approach requires the model to be learning-positive and trained in online fashion. Also generative models have been applied for this.
- Prediction-Based Exploration, rewarded for improving the agent's knowledge about the environment. 
    - Forward dynamics prediction model, approximates knowledge of environment obtained.
    - An Intrinsic Curiosity Module (ICM) learns the state space encoding with a self-supervised model.
    - Random Networks, tends to work well for the Hard-Exploration problem. RND introduces a prediction task independent of the main task. Works best in non-episodic setting.
- Memory-Based Exploration, reward-based exploration has several drawbacks. A solution to rely on external memory to resolve these disadvantages.
    - Episodic Memory, the exploration strategy Never Give Up (NGU) has two bonuses as intrinsic reward by two modules, within one episode and across multiple episodes.
    - The nice properties NGU brings is; It **rapidly** discourages visiting the same state within one episode and **slowly** discourages revisiting states that have been visited many times across episodes.
    - Agent57 Has further improvements on NGU; A population of policies are trained and a meta-controller (sliding-window MAB algorithm) is used to prioritize which policy to train first.
    Secondly a new parameterization for the Q-value function.
    - Episodic Curiosity (EC) Module, estimates the reachability between states by a siamese neural network. Claims are made this solved the noisy-TV problem.
- Q-value Exploration Bootstrapped DQN introduces a new notion of uncertainty in Q-value approximation by bootstrapping.
- Variational Options, Options are policies with termination conditions. The search space has a large amount of options independent of the agent's intentions. Intrinsic options are included explicitly into modelling. 


### Notes
A lot of references are made in this blog post it would be interesting to further explore the meta-controller adjustments for agent57.
