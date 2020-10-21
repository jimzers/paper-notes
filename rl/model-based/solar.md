# SOLAR: Deep Structured Representations for Model-Based Reinforcement Learning

### First Pass

Learning representations for MB Policy improvement

- works with images
- works with LQR
- works with complex domains



Biggest challenges in field:

- modeling bias
  - if control / policy learning performed against imperfect model, performance degrades with model inaccuracy
  - past solutions: rely on accurate forward prediction for planning
    - if using complex models, need large dataset

Solution: remove need for accurate forward prediction

- local models methods
- use simple models to provide gradient directions for policy
  - PGM structure to infer dynamics

Also transfer learning for multi-task RL!

Sparse rewards with goal images!



