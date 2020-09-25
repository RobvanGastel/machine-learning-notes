## [Learning to reinforcement learn for Neural Architecture Search](https://arxiv.org/abs/1911.03769)

TLDR; Applies meta-RL for NAS with Reinforcement Learning, on a broader set of data set than before. The 3 components for NAS can be split in search space, search algorithm and performance estimation strategy. Where for the search strategy deep-meta-RL is applied.

### Key Points
- Policies learned in the typical RL problem only capture one-to-one state action relation of the environment for this meta-RL is introduced. In metaRL agents are trained to learn transferable policies. We can identify two types of meta-RL algorithms:
    - The ones that learn good initialization of parameters
    - The ones that learn policies that adapt their decision making strategy to new environments
- Two algorithms proposed that can adapt their decision-making
strategy to new environments; Learning to reinforcement
learn and RL^2. 
- A bottleneck is the high computational cost to calculate the reward, which typically is the test accuracy. Thus performance estimation strategies have been proposed for this and limitations on the search space of the NAS.
- The system can be split into two components, NAS variables and the reinforcement learning framework. Works with an adjusted version of BlockQNN.
- The NAS elements, search space is modelled as NSC vectors, performance estimation strategy, follows the BlockQNN early stopping approach. Search strategy, applied deep-meta-RL different from traditional RL.
- NSC vectors contain categorical variables, which isn't optimal in a machine learning setting.
- A policy learned by deep-meta-RL can be transferred to other environments quickly.
- Hard to evaluate multi-branch settings with limitations to computing power. Thus choice of branch setting.


- constrain the search strategy to a deep meta-reinforcement learning algorithm

### Notes
Can more computational methods be applied to reproduce this result, e.g. proxy task performance, parameter sharing?
Having custom blocks constraints for NAS have also performed well.
Study other RL algorithms for NAS is suggested in the paper.
How can a meta-controller be used to improve NAS, instead of applying RNN explicitly?
