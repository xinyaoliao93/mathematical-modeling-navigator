# Mathematical Modeling Map

Use this catalog as a router, not as a list to apply mechanically. Search terms in parentheses help locate authoritative material.

## 1. Statistical relationships and inference

| Data/question signal | Candidate families | Decisive checks |
|---|---|---|
| Two continuous/ordinal variables | Pearson, Spearman, Kendall, robust or distance correlation | linear vs monotone, scale, ties, outliers, dependence |
| Continuous response | linear/polynomial/nonlinear regression, GAM, quantile or robust regression | functional form, heteroscedasticity, influential points, dependence |
| Binary/ordinal/nominal response | logistic, probit, ordinal or multinomial regression | link, separation, proportional odds, class imbalance |
| Counts/rates | Poisson, negative binomial, quasi-Poisson, zero-inflated or hurdle models | exposure offset, overdispersion, structural zeros |
| Proportions in [0,1] | binomial, beta, zero/one-inflated beta, fractional regression | numerator/denominator known, boundary values, precision |
| Duration or censored outcome | Kaplan–Meier, Cox, parametric survival, competing risks, frailty | censoring, proportional hazards, competing events, clustering |
| Repeated/nested/clustered data | paired methods, LMM/GLMM, GEE, multilevel Bayesian models | cluster count, random effects, covariance, population vs subject-specific target |
| Causal effect | randomized analysis, matching/weighting, IV, difference-in-differences, regression discontinuity, synthetic control | treatment assignment, confounding, overlap, parallel trends, estimand |
| Weak assumptions needed | permutation/randomization tests, bootstrap, rank/nonparametric, robust covariance | exchangeability, resampling unit, dependence-aware bootstrap |

## 2. Multivariate structure and dimension reduction

| Goal | Candidate families | Decisive checks |
|---|---|---|
| Compress correlated variables | PCA, sparse PCA, kernel PCA, autoencoder | scaling, linearity, outliers, interpretability |
| Discover latent constructs | exploratory/confirmatory factor analysis, SEM, latent class/profile | sample size, identifiability, measurement invariance |
| Relate two variable sets | canonical correlation, PLS, multivariate regression | covariance invertibility, multicollinearity, prediction vs association |
| Compare multivariate groups | MANOVA, repeated-measures MANOVA, permutation MANOVA | multivariate normality, covariance equality, dependence |
| Unsupervised grouping | k-means, hierarchical, Gaussian mixture, DBSCAN, spectral clustering | distance, scaling, cluster shape, stability |
| Supervised separation | LDA/QDA, logistic, tree/SVM/ensemble classifiers | distribution/covariance, calibration, validation |

## 3. Time series and longitudinal dynamics

| Signal | Candidate families | Decisive checks |
|---|---|---|
| Trend/seasonal forecasting | decomposition, ETS, ARIMA/SARIMA, dynamic regression | regular spacing, stationarity/differencing, seasonality, residual whiteness |
| Several interacting series | VAR/VECM, dynamic factor, state-space | stationarity, cointegration, lag order, dimensionality |
| Changing volatility | ARCH/GARCH and variants, stochastic volatility | volatility clustering, tail behavior, residual diagnostics |
| Noisy latent state | state-space, Kalman/particle filters, hidden Markov models | linear/Gaussian assumptions, observability, regime structure |
| Intervention or change | interrupted time series, intervention ARIMA, change-point models | intervention timing, counterfactual trend, autocorrelation |
| Many subjects over time | LMM/GLMM, GEE, growth curves, joint models | within-subject covariance, dropout, irregular times, outcome family |
| Event arrival/intensity | point process, Hawkes, survival/recurrent-event models | self-excitation, exposure, censoring, independence |

## 4. Spatial and spatiotemporal models

| Signal | Candidate families | Decisive checks |
|---|---|---|
| Continuous field interpolation | variogram/kriging, Gaussian process | stationarity/isotropy, distance, nugget, computational scale |
| Areal adjacency | CAR/SAR/BYM, spatial lag/error/Durbin models | weights matrix, residual spatial autocorrelation, spillover interpretation |
| Spatial counts/binary data | spatial GLMM, Bayesian CAR/BYM2, spatial point process | outcome family, offset, zero inflation, spatial confounding |
| Space and time jointly | spatiotemporal GP, dynamic spatial panel, hierarchical state-space | separability, temporal dependence, validation blocking |
| Locations of events | Poisson/log-Gaussian Cox point processes | observation window, intensity, edge effects |

## 5. Prediction, classification, and machine learning

| Structure | Candidate families | Decisive checks |
|---|---|---|
| Tabular nonlinear prediction | trees, random forest, gradient boosting, SVM, neural networks | leakage, tuning, imbalance, sample size, calibration |
| High-dimensional sparse predictors | ridge, lasso, elastic net, sparse PLS, boosting | p/n ratio, correlated predictors, stability |
| Images/text/sequences | CNN, transformers, representation learning | data volume, transfer learning, compute, shift |
| Rare/novel cases | one-class SVM, isolation forest, robust covariance, autoencoder | contamination rate, labels, threshold costs |
| Treatment/policy heterogeneity | causal forest, meta-learners, uplift models | identification, overlap, honest validation |

Always define a naive or interpretable benchmark. Use nested or properly separated validation when tuning; use grouped, temporal, or spatial splits when observations are dependent.

## 6. Optimization, control, and games

| Decision structure | Candidate families | Decisive checks |
|---|---|---|
| Linear continuous decisions | LP | linearity, units, feasibility, dual/sensitivity |
| On/off, assignment, routing, scheduling | MILP, network flow, CP/CP-SAT, combinatorial optimization | integrality, symmetry, scale, optimality gap |
| Smooth nonlinear decisions | NLP, convex optimization, quadratic/SOCP/SDP | convexity, local vs global optimum, constraint qualification |
| Conflicting objectives | weighted sum, epsilon-constraint, goal programming, Pareto methods | scales, preference elicitation, Pareto coverage |
| Uncertain inputs | stochastic, robust, distributionally robust, chance-constrained optimization | distribution/scenarios vs uncertainty set, conservatism, recourse |
| Sequential decisions | dynamic programming, MDP/POMDP, model predictive control, reinforcement learning | state/action definition, Markov property, horizon, exploration |
| Strategic agents | cooperative/noncooperative, Stackelberg, evolutionary games | information, timing, equilibrium concept, incentives |
| Intractable exact model | decomposition, approximation, local search, metaheuristics | lower/upper bounds, reproducibility, benchmark comparison |

## 7. Mechanisms, evolution, and networks

| Mechanism | Candidate families | Decisive checks |
|---|---|---|
| Continuous-time state change | ODE systems, compartment/population/epidemic models | conservation, initial conditions, parameter identifiability |
| Space-dependent processes | PDE, reaction–diffusion, transport models | boundary/initial conditions, discretization error, stability |
| Discrete-time evolution | difference equations, maps, matrix population models | step size, equilibrium, stability/bifurcation |
| Random state transitions | Markov chains, CTMC, hidden/semi-Markov models | state definition, memorylessness, transition stationarity |
| Network propagation | graph diffusion, epidemic/network cascade, centrality/community models | graph construction, dependence, temporal edges |
| Local rules/emergence | cellular automata, agent-based and system-dynamics models | rule calibration, stochastic replication, validation |

## 8. Evaluation, decision support, simulation, and uncertainty

| Goal | Candidate families | Decisive checks |
|---|---|---|
| Multi-criteria ranking | AHP/ANP, TOPSIS, VIKOR, PROMETHEE, ELECTRE | benefit/cost direction, normalization, subjective weights, rank reversal |
| Objective weighting/association | entropy/CRITIC weights, grey relational analysis | scaling, information interpretation, robustness |
| Relative efficiency | DEA, stochastic frontier analysis | input/output orientation, returns to scale, noise vs inefficiency |
| Vague linguistic judgments | fuzzy comprehensive evaluation, fuzzy AHP, evidence theory | membership/evidence elicitation, sensitivity |
| Queue/congestion | queueing theory, discrete-event simulation | arrival/service processes, stationarity, warm-up |
| Reliability/risk | reliability block/fault tree, survival, extreme value, Bayesian networks | dependence of failures, tail data, censoring |
| Complex stochastic system | Monte Carlo, discrete-event, agent-based simulation | verification, validation, random seeds, replication error |
| Uncertain model inputs | local/global sensitivity, scenario, bootstrap, Bayesian uncertainty | parameter vs structural uncertainty, dependent inputs |

## Hybrid problems

Many strong models combine branches: forecast-then-optimize, spatial zero-inflated counts, mixed-effects survival, dynamic network diffusion, simulation optimization, physics-informed ML, or Bayesian decision analysis. Keep the interfaces explicit: what one submodel outputs, how uncertainty propagates, and what is validated jointly.
