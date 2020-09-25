## [The Sorcerer’s Apprentice Guide to Training LSTMs](https://www.niklasschmidinger.com/posts/2020-09-09-lstm-tricks)

TLDR; A very short overview of the workings of LSTM units.

### Key Points
- The Vanilla LSTM is characterized by three gates and a memory state. 
- The adoption of tanh first required two mental shifts. First, tanh makes intuitive sense in a meta-learning setting. Instead of patterns, we now use memory cells to store the weights for another neural network. The second intuitive interpretation is the storage of hints. 
- Tanh has desired properties over the for example ReLu and Sigmoid. expected value of the cell input activation is zero for tanh. To prevent the drift effect (The quick growth of value c(t) for long sequences). This becomes a problem during the backwards pass.
- With its range centred around zero, the cell state is prevented from accumulating over time. This in turn stabilises the learning signal, which is key to learning long-term dependencies.
- To prevent the cell state from accumulating the forget gate was proposed (Felix Gehrs and Jürgen Schmidhuber). The problem with the forget gate is that it reintroduces the vanishing gradient problem. For short sequences this usually doesn't pose a problem.
- The Focused LSTM is a simplified LSTM without forget gate. This reduces the amount of parameters and can aid explainability. 
- Negative gate biases help improving the ability to learn by solid bias initializations.
- Linear activation functions for g or h. Is especially useful where the memory units are being used to count or accumulate information. This can speed up learning and help to extrapolate in situations characterised by additive effects.
- Time Awareness to give LSTM the capability to distinguish between a few exact time steps we can use the modulo operator. To take different modulo operators for every new column. 
- Two very useful remarks:
    - It is a good idea to rescale the targets into the range [0.2,0.8] when using sigmoid output units. This prevents the output activations from being pushed into saturated regions where learning stalls, i.e. zero gradients.
    - Always standardise the input to zero mean and unit variance. A neat trick you can use if there are outliers in the data is to standardise, apply tanh and then standardise again. Repeat this procedure to move the outliers closer towards the remaining data points. In this way, we can reduce the impact of outliers without entirely removing them.



### Notes
The [RUDDER](https://arxiv.org/abs/1806.07857) paper is a good example of the use of linear activation functions, the LSTM’s memory cells keep track of the collected rewards of a reinforcement learning agent playing Atari games. 

The [RUDDER blog](https://ml-jku.github.io/rudder/) with demonstration of the algorithm.