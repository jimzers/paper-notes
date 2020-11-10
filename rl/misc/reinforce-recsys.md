# Top-K Off-Policy Correction for a REINFORCE Recommender System

### First pass

They used off-policy policy gradient



Challenges:

1. Scale PG to huge action space
2. Applying off-policy correction from logged feedback
3. top-K off-policy correction (b/c recommending multiple item at a time)
4. exploration

What RecSys deals with:

- small amt of data for large state + action space
- very sparse data
- non-stationary data flows in
- user preferences shifting (user states changing)

RL for recommendation distinctions from typical RL

- Simulation not possible - complex dynamics IRL

Model relies mostly on data from previous policies







