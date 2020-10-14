# Hindsight Experience Replay

### First pass

Sample-efficient learning from sparse binary rewards

Avoid reward engineering

Can be commbined with off-policy RL ~ kind of implicit curriculum

Actual experiment: Robotic arm pushes, slides, pick and place


Inspiration fromm humans: unlike current model-free algorithms (written in 2017), helpful conclusions are still drawn from failures beyond just "fail"

Training universal policies - takes goal and regular state as input. Replay each episode wit a different goal than the one the agent was trying to achieve

Experiments used DQN and DDPG, two arbitrary off policy (model-free) algos.


### Second pass

Note the build up from UVFA - quick recap:
- every goal g has it's own reward fn r_g
- every episode starts by sampling a state-goal pair from a distribution p(s_0, g)
- goal is fixed entire episode
- the agent takes in both state and goal as input per timestep
- Q fn depends on goal too
- greedy policy from this Q fn can generalize to unseen state-action pairs

A motivating example - very very sparse environment (bit flipping). Exploration techniques don't help here b/c the problem isn't the lack of diversity in state exploration - it's just a really big state space.
- Normally solved with shaped reward fn which is hell to make... you need domain knowledge
- look at failed trajectories as successes... to a different goal than originally intended
- make a new transition in the buffer with replaced goal. can also add in the transition with the original goal.

Actual algo:
- after each episode, store all the regular transitions with original goal, AND also store alternative transitions with a subset of other goals (in the paper they just use a single replacement goal - the final state of the episode)
- as long as an off-policy RL algo is being used, trajectories can be replayed with arbitrary goals

![Hindsight Algo Pic](imgs/hindsight-algo-pic.PNG)

Implicit curriculum
- because goals shift from ones that are achieved randomly (low iq) to more and more difficult ones
- but not explicit because HER doesn't control the initial environment states
