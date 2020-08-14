## [Neural Architecture Search](https://lilianweng.github.io/lil-log/2020/08/06/neural-architecture-search.html)

TLDR; The survey paper of Elsken, et al 2019 explained in greater detail. Where NAS can be decomposed in 3 components, Search Space, Search Algorithms and Evaluation Strategy. Describing a set of approaches for all 3 components. Interest of applying RL as evaluation Strategy, Speed increase of 1000x with ENAS. Interesting to explore the idea of weight sharing? In general its hard to do inference why a specific architecture works well. Call for unsupervised NAS?

### Key Points
-  Elsken, et al 2019. characterizes NAS as a system with three major components;
    - Search space: The NAS search space defines a set of operations (e.g. convolution, fully-connected, pooling).
    - Search algorithm: A NAS search algorithm samples a population of network architecture candidates.
    - Evaluation strategy: We need to measure, estimate, or predict the performance of a large number of proposed child models in order to obtain feedback.
- Search Space;
    - Modeling the search space with Sequential Layer-wise Operations is too expensive!
    - Cell-based Representation, reduces this search space a lot, transfers to different datasets and creates useful design patterns.
    - Hierarchical Structure (DAG) modeling, simple search can be enhanced by well-designed search spaces.
    - Memory-bank Representation view a neural network as a system with multiple memory blocks which can read and write.
- Search Algorithms;
    - Random Search, a naive baseline algorithm it samples from the search space at random.
    - Reinforcement Learning, involves a RL-based controller for proposing child model architectures for evaluation. MetaQNN (Baker et al. 2017) trains an agent to sequentially choose CNN layers using Q-learning.
- Evaluation Strategy, we need to evaluate the performance of every child model;
    - Proxy Task Performance, train on a smaller dataset with fewer epochs. 
    - Parameter Sharing, Efficient Architecture Search (EAS). EAS sets up an RL agent, known as a meta-controller, to predict function-preserving network transformation so as to grow the network depth or layer width.
    - Prediction Based, Employ HyperNet to directly generate the weights of a model conditioned on an encoding of it's architecture configuration.
- One-Shot Approach: Search + Evaluation
- Combines the Search for architecture with the weight parameters. Trains a single huge network containing every possible model combination. 

