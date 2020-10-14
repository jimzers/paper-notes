# PILCO: A Model-Based and Data-Efficient Approach to Policy Search

### First pass

####Why PILCO??
- reduces model bias (huge problem in MBRL)
- learns a probabilistic dynamics model
- explicit model uncertainty with long-term planning
- works on small amount of data, or can learn from scratch pretty quick
- closed form policy evalutation
- analytical policy gradient calculation


Do not assume:
- No expert knowledge (no demos! no dynamics!)

Model bias:
- MBRL assumes learned dynamics model accurately resembles real environment
- hurts more with less data

What to do?
- probabilistic fn approximator for long-term planning
- expresses a level of uncertainty about the model
- non-parametric gaussian processes used

How to use model uncertainty in planning and policy eval?
- determinsitic approximate inference techniques
- analytic policy gradient
- explicit value fn model not required

Dynamic systems described in paper are just describing new state from state x and control u. No differences in states used yet here.

PILCO is not an optimal control method - it just finds a solution for the task.
- no global optimality guarantee since optimization problem not convex

Nonzero gradients from approx of experted return for indirect policy search 

Another con: the dynamic models are only confident in areas of state space that are previously observed

Very condiational on exposed experiences


Past work to see:

Schneider (1997) => model uncertainty treated as temporally uncorrelated noise

and some other stuff... we'll check this out later

