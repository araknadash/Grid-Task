# xy_grid_task

The experiment consists of a 20 x 20 grid task where an agent must avoid collisions
with the obstacles and reach the target. Here, the target and obstacle are randomly assigned
with 0% chance of being too close to each other resulting in always having a solution to
reach the target without colliding with the obstacle. The agent can only move in four
directions which are left, right, up and down as the environment is in 2D space. The actions
are decided based on Deep Q network, which uses observation from the environment that
consists of an obstacle, target and agent’s present location and decides what action has to
be taken to improve the reward function.


In this experiment, the agent is considered to have made a successful reach if it reaches
the target successfully which results in a reward of +1. Similarly, the agent is considered
to have made a collision if they reach an obstacle which results in a reward of -1, all of
these reaches have to be made within 50 timesteps. The RL agent uses regret minimization,
which can be defined as the expected decrease in reward gained due to executing the
algorithm instead of behaving optimally from the very beginning. This way every time the
agent makes a mistake they are penalized.
The model is trained on 400K episodes using an Adam Optimizer. The
Experience replay buffer size used was 10,000 with minibatch sizes of 32 with the discount
factor for target networks as 0.9, these parameters have been selected based on their
performance after several test sessions.
