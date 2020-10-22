# Can You Trust Your Model's Uncertainty? Evaluating Predictive Uncertainty Under Dataset Shift

### First pass

Many probabilistic DL methods (bayesian and nonbayesian) attempt to quantify predictive uncertainty

Empirical comparison of methods under dataset shift

SOTA (2019) vs classification problems - dataset shift on accuracy / calibration



Importance: high stakes applications - need to know confidence in predictions

Current solution: Taking independent label samples from target data distribution as estimation of certainty

Problem: Once deployed to real world, distribution might change

Need robustness!



Contributions:

- How trustworthy are uncertainty estimates of different methods under dataset shift?

- Does calibration in independent and identically distributed envs translate under shift?

- How do uncertainty and accuracy vary under data shift - and which methods are robust to shift

Takeaways:

- Accuracy and uncertainty get worse with shift (duh)
- Calibration and accuracy on iid test set doesn't translate to good calibration under dataset shift
- Post-hoc calibration: works for puny values of shift. But when the going gets tough, pick a method that utilizes epistemic uncertainty
- Last layer Dropout exhibits less uncertainty vs reg dropout (on shifted and OOD)
- SVI (stochastic variational bayesian inference for DL) works well on toy datasets. can't do complex things
- flaw w/ experiments: consistent relative ordering
- Deep ensembles: most robust to dataset shift. Even a size of ~5 is bueno
- there's a long way to go