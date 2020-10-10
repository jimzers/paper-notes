# Universal Value Function Approximators

abstract intro conclusion

value fns - typically construct single fn approx V(s; theta) estimating long term reward from state s.

introduce V(s, g; theta) that also generalise over goals

utilize supervised learning of UVFAs
- learn embedding for s and g
- then learn mapping to embeddings

able to generalize to unseen goals


Value fns:
- cache knowledge to represent utilty of a state s
- V_g(s) represent utility of state s in achieving a goal g
- pseudo-reward function to reperesent progress towards "waypoint" goal

goal space often contains just as much structure as the state space

since this structure is so similar, we extend value fn approx to both states and goals using UVFAs
- both identify and exploit structure across both s and g

universal: value fn can generalise to any goal g in a set G of possible goals

exploit two kinds of structure b/w goals:
1. similarity encoded a priori in goal representations
2. structure in induced value fns discovered bottom up

complexity of UVFA learning does not depend on no. of "demons" but on the inherent domain complexity

note: demons are a discrete set of value functions (see Horde architecture from Sutton 2011)

complexity is larger than standard value fn approx, so you need a rich fn approximator like a DNN for UVFA


Challenges of learnin a UVFA:

- agent only sees small subset of (s, g) but we want to generalize in several diff ways

- introduce a factorization approach to decompose the regression problem into two states:
1. find low-rank factorization of a table (sparse table that contains one row for each state, and one column of each observed goal g) into state embeddings and goal embeddings
2. learn non-linear mappins from states s to state embeddings, and goals to goal embeddings (with standard regression techniques like gradient descent)

this learns much faster

2 algorithms for learning UVFAs directly from rewards
1. Finite Horde of general value functions and use thse values to seed the table and learn a UVFA that generalizes to prev unseen goals
2. bootstrap directly from value of UVFA at successor states

Conclusion:

UVFA learnable from either supervised targets or directly from real experience.

UVFAs can be used for transfer learning to new tasks with same dynamics but different goals
- the values in a UVFA can be used to initialise a new single value function for a new task with unseen goal

generalized value functions can be used as features to represent state. This is a form of predictive representation. A UVFA compresses a large number of predictions into a short feature vector (with state embedding and goal embeddings)

can also generate temporally abstract options with UVFA. For any goal g you can construct a greedy option to V and terminate upon reaching g - universal option that represents optimal behaviour towards any goal. *can use with hierachial policies*

Universal option model - if psuedo-rewards are defined by goal achievement. Then V approximates the probability of reacing g from s (discounted prob), under a policy that attempts to reach it.
