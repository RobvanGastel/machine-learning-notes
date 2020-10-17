## [Reinforcement Learning, Fast and Slow](https://www.cell.com/action/showPdf?pii=S1364-6613%2819%2930061-0)

TLDR; Deep Reinforcement Learning (RL) methods have had impressive advancements in the last couple of years. However, the concern has been raised that deep RL may be too sample-inefficient – that is, it may simply be too slow – to provide a plausible model of how humans learn. In the present review, we consider two key deep RL methods that mitigate the sample efficiency problem: episodic deep RL and meta-RL.

### Key Points
- The source of the slowness in Deep RL. Two primary sources of sample inefficiency can be described:
    - The first source of slowness in deep RL is the requirement for incremental parameter adjustment. The adjustments made during this form of learning must be small, in order to maximize generalization [27] and avoid overwriting the effects of earlier learning (an effect sometimes referred to as ‘catastrophic interference’).
    - A second source is weak inductive bias. A basic lesson of learning theory is that any learning procedure necessarily faces a bias–variance trade-off: the stronger the initial assumptions the learning procedure makes about the patterns to be learned the less data will be required for learning to be accomplished.
- Episodic Deep RL: Fast Learning through Episodic Memory
    - 
    If incremental parameter adjustment is one source of slowness in deep RL, then one way to learn faster might be to avoid such incremental updating. Episodic RL algorithms estimate the value of actions and states using episodic memories. The fast learning of episodic deep RL depends critically on slow incremental learning. This is the gradual learning of the connection weights that allows the system to form useful internal representations or embeddings of each new observation.
- Meta-RL: Speeding up Deep RL by Learning to Learn
    - As discussed earlier, a second key source of slowness in standard deep RL, alongside incremental updating, is weak inductive bias. As formalized in the idea of the bias–variance trade-off, fast learning requires the learner to go in with a reasonably sized set of hypotheses concerning the structure of the patterns that it will face. The narrower the hypothesis set, the faster learning can be.
- Episodic deep RL provides a forum for exploring how this general
principle might scale to rich, high-dimensional sequential learning problems. Perhaps more fundamentally, it highlights the important role that representation learning and metric learning might play in RL based on episodic memory.

### Notes
Some interesting references are added here,

27. Hardt, M. et al. (2015) Train faster, generalize better: stability of
stochastic gradient descent. arXiv, 1509.01240