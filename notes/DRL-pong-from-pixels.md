## [Deep Reinforcement Learning: Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/)

TLDR; Applying Policy Gradients to the game of Pong, to learn ways of modeling other complex problems in similar ways. With they key points being on the details of the given implementation. PG works best for problems with frequent reward signals and little ahead planning. In practice Trust Region Policy Optimization (TRPO) almost always works better and more consistently than vanilla PG.

### Key Points
- In fact most people prefer to use Policy Gradients, including the authors of the original DQN paper who have shown Policy Gradients to work better than Q Learning when tuned well.
- Policy network. First, we’re going to define a policy network that implements our player (or “agent”).
- The feed difference in frames is passed to the network to see the movement. And decide our policy gradient to move up or down.
- And how do we figure out which of the million knobs to change and how, in order to do better in the future? We call this the credit assignment problem.
-  So if we fill in -1 for log probability of DOWN and do backprop we will find a gradient that discourages the network to take the DOWN action for that input in the future.
- Training settings 100 games of pong with 200 frames. The network is only updated for the games of pong where it won. 
- Important to pick a good discount value for the eventual reward.
- For more in depth analysis on the Policy gradient, visit John Schulman's second lecture.
- Policy Gradients are a brute force solution, where the correct actions are eventually discovered and internalized into a policy.
- there are many games where Policy Gradients would quite easily defeat a human. In particular, anything with frequent reward signals that requires precise play, fast reflexes, and not too much long-term planning would be ideal


### Notes
- Four separate factor that limit progress in AI; Compute (Moore's Law, GPUs), Data (In nice form), Algorithms (research and ideas, like backprop, CNN) and Infrastructure (software under you - Linux, AWS, tensorflow)
