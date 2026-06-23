
# BayesBall: Bayesian Forecasting of Baseball Player Rates

A Bayesian model that estimates each MLB hitter's **true** home run rate and strikeout
rate — correcting for small-sample noise — and forecasts their expected output over a
future window, with honest uncertainty around every number.

**By Joel Hastings**

**Live dashboard:** https://public.tableau.com/app/profile/joel.hastings/viz/2026MLBPlayerForecastingBayesian/Dashboard1

---

## What problem this solves

Raw baseball stats lie in small samples. A hitter who homers 6 times in his first 60
plate appearances looks elite, but it may be luck. A naive ranking would put him above
proven sluggers. This project fixes that: it estimates each player's *underlying* skill
rather than trusting their noisy raw rate, and reports how confident it is in each
estimate.

For every player, the model produces three things:

- **A best estimate** of their true rate (e.g. true HR per plate appearance)
- **A 90% credible interval** — the honest range the true rate likely falls in
- **A forecast** of expected events over the next 200 plate appearances, with a
  realistic low-to-high range

The result is a decision ready table and a set of charts that rank players *while
showing how much to trust each ranking* — the difference between a list and a tool.

---

## The core idea: partial pooling (shrinkage)

The model assumes every player's rate is drawn from a shared, league-wide distribution
whose shape is learned from the data. This creates **shrinkage**: players with few
plate appearances get pulled toward the league average (the model distrusts their small
sample), while players with a full season of data stand on their own. Genuine outliers
still stand out as evidence accumulates, but hot streaks in tiny samples get discounted
automatically. This is what stops the model from overreacting to noise.

---

## Tech stack

**Python** (PyMC, ArviZ, pandas, NumPy, matplotlib) for the Bayesian model and
forecasting · **Tableau Public** for the interactive dashboard.
