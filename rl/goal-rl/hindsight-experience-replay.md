# Hindsight Experience Replay

### First pass

Sample-efficient learning from sparse binary rewards

Avoid reward engineering

Can be commbined with off-policy RL ~ kind of implicit curriculum

Actual experiment: Robotic arm pushes, slides, pick and place


Inspiration fromm humans: unlike current model-free algorithms (written in 2017), helpful conclusions are still drawn from failures beyond just "fail"

Training universal policies - takes goal and regular state as input. Replay each episode wit a different goal than the one the agent was trying to achieve

Experiments used DQN and DDPG, two arbitrary off policy (model-free) algos.
