# BayesBall: MLB Player Forecasting System — 2026 Season

![Python](https://img.shields.io/badge/Python-3.11-blue)
![PyMC](https://img.shields.io/badge/PyMC-Bayesian-orange)
![Status](https://img.shields.io/badge/Status-Live-green)

## What This Does for a Front Office

Small samples mislead. A hitter with 6 home runs in his first 
60 plate appearances looks elite on a leaderboard. He probably 
isn't. This system separates real skill from noise and tells 
you how confident to be in every number it produces.

Built for roster construction, waiver wire decisions, and 
contract evaluation where acting on a hot streak costs 
real money.

📊 **[View Live Dashboard](https://public.tableau.com/app/profile/joel.hastings/viz/2026MLBPlayerForecastingBayesian/Dashboard1)**

---

## The Problem It Solves

Every front office deals with the same question: is this 
player's performance real or is it a small sample illusion?

Raw stats don't answer that. This system does. It estimates 
each player's underlying skill level, not just what they've 
done, and reports an honest confidence range around every 
projection. You get a ranking you can act on, not just a 
leaderboard that rewards luck.

---

## What the Model Produces for Every Player

**True rate estimate** — the player's most likely actual 
skill level for HR rate and strikeout rate, corrected for 
sample size

**90% credible interval** — the honest range the true rate 
falls in. Wide interval means low confidence. Narrow means 
the signal is real.

**200 plate appearance forecast** — expected output over 
the next window with a realistic low-to-high range for 
planning purposes

---

## The Key Insight

Players with small samples get pulled toward league average 
automatically. Players with a full season of evidence stand 
on their own numbers. Genuine breakouts still surface. 
Hot streaks in 40 plate appearances get discounted.

This is the same logic a seasoned scout applies 
instinctively. The model applies it consistently across 
all 347 players with no exceptions and no gut-feel bias.

---

## Front Office Applications

**Waiver wire targeting:** Identify players whose raw stats 
understate their true skill because of sample size. Pick 
them up before the market catches on.

**Contract evaluation:** Know whether a career year is 
a real shift in skill or a reversion waiting to happen 
before you commit money to it.

**Platoon and lineup decisions:** Build decisions around 
true rate estimates rather than recent performance windows 
that may not hold.

---

## Tech Stack

Python (PyMC, ArviZ, pandas, NumPy, matplotlib) for 
Bayesian modeling and forecasting. Tableau Public for 
the interactive dashboard. 347 MLB hitters analyzed 
for the 2026 season.

---

## Author

Joel Hastings — M.S. Data Science, University of Colorado Boulder  
[LinkedIn](https://www.linkedin.com/in/joel-hastings-976bb855) | [Portfolio](https://github.com/JHastings46)
