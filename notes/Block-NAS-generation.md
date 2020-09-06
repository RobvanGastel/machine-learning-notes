## [title](https://arxiv.org/abs/12345689)

TLDR; CNN have had a large impact on the field of computer vision with complex hand-crafted models. this paper purposes BlockQNN, a way to automate the creation of high performance networks using Q-Learning with epsilon-greedy exploration. Using block-wise generation of the models has some unique advantages, like reducing the search space immensely. The experiments where executed in a distributed asynchronous fashion. 

### Key Points
- An example of well performing Block structured models are the well known Resnet and Inception models. 
- Comparison with MetaQNN (Baker et al. 2017) which employs the same RL algorithm Q-Learning.
- Proposing the Block-wise generation strategy increases the efficiency as it converges faster than previously mentioned methods.
- The idea of NAS started in the 1980's by evolutionary/genetic algorithms for NAS.
- The layers of the network are represented as Network Structure Code (NSC). In which a lot of choices have been made explicit to stick to well known components of models as Resnet, Inception etcetera. To make for a smaller search space.
- For the Q-Learning algorithm shaped rewards are used and it's indicated this is important for better convergence. This is known as the temporal
credit assignment problem.
- Early stopping is applied when evaluating the model in the estimation strategy for this the following is used: reward = ACC_EarlyStop − µ log(FLOPs) −ρ log(Density).
- A Distributed Asynchronous Framework is used to run the experiments, where the training is customized for this.
- Observed was that the generated blocks share similar properties with those state-of-the-art hand-crafted networks.


### Notes
How can this exploration technique in a distributed asynchronous way be adjusted to work for more advanced techniques? It would be nice to see more on the generalization ability of this approach. At the end is mentioned that this could also be done for other tasks like detection and segmentation.