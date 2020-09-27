## [On First-Order Meta-Learning Algorithms](https://arxiv.org/abs/1803.029999)

TLDR; In this paper the meta-learning problem is considered, in specific the First-Order Meta-Learning approach is expanded on and explored. Where the idea of first-order MAML is used, as idea for their new algorithm Reptile. 

### Key Points
- Tenenbaum and collaborators, argues that humans’ fast-learning abilities can
be explained as Bayesian inference, and that the key to developing algorithms with human-level learning speed is to make our algorithms more Bayesian.
- Meta-learning emerges from an approach to use for learning from a small amount of data. Instead of trying to do Bayesian inference which may be intractable.
- In this work meta-learning algorithms based on the first order gradient information is explored. Introduced is the algorithm MAML (Model-Agnostic Meta-Learning), where later first-order MAML, FOMAML, was introduced obtained nearly as well performance as MAML on ImageNet while ignoring the second-order gradient information. This has been seen in other meta-learning approaches as well.
- The same optimization problem is considered as in MAML. Like MAML, Reptile learns an initialization for the parameters of the neural network. This is described in more detail in the paper.

### Notes
Follow up reading the original MAML paper for more insight, Chelsea Finn, Pieter Abbeel, and Sergey Levine. Model-agnostic meta-learning for fast adaptation of
deep networks.