# Model Analysis Checklist

Apply only relevant items, but never omit an item that could invalidate the conclusion.

## A. Mathematical specification

- Define observational units, indices, variables, parameters, latent states, random effects, decisions, objectives, and constraints.
- State the response distribution or deterministic evolution law.
- Write the mean/link/system equation and the error, covariance, or uncertainty structure separately.
- Name the estimand or decision quantity. Distinguish parameters from predictions and latent variables.
- Check units, domains, boundary/initial conditions, conservation laws, and feasibility.

## B. Estimation and computation

- Specify least squares, maximum likelihood, REML, moments, Bayesian posterior, numerical integration, or optimization algorithm.
- State identifiability, full-rank, convexity, stationarity, observability, or constraint-qualification requirements when relevant.
- Report initialization, convergence criteria, multiple starts, solver tolerance, and optimality gap when they affect reliability.
- Explain missing-data, censoring, weighting, offsets, scaling, encoding, and resampling units.

## C. Errors and uncertainty

- Identify sampling error, measurement error, process noise, parameter uncertainty, model-form uncertainty, and numerical error as applicable.
- Check independence; if false, specify repeated, cluster, temporal, spatial, or network covariance.
- Check distributional shape, variance structure, overdispersion, zero inflation, heavy tails, and influential observations.
- Propagate uncertainty across multi-stage models instead of treating estimated inputs as exact.

## D. Inference and fit

- For inference: effect estimates, standard errors, confidence/credible intervals, global and targeted tests, multiplicity where applicable.
- For likelihood models: likelihood/deviance, information criteria used for a declared purpose, and residual or posterior predictive checks.
- For mixed/hierarchical models: fixed effects, variance components, random-effect structure, ICC when meaningful, singular fit, small-cluster limitations.
- For survival: censoring assumptions, proportional hazards or time-varying effects, competing risks.
- Never use p-values as the sole selection criterion or describe non-significance as proof of no effect.

## E. Prediction and classification

- Separate training, tuning, and final evaluation; prevent leakage.
- Respect grouped, temporal, and spatial dependence in splits.
- Use task-appropriate metrics and uncertainty: RMSE/MAE, log score, AUC/PR, sensitivity/specificity, calibration, coverage, or decision cost.
- Compare against a simple benchmark and examine subgroup/shift performance.

## F. Optimization and decision models

- Verify feasibility and units; report objective value, bounds, gap, runtime, and binding constraints.
- Perform sensitivity to coefficients, weights, capacities, budgets, scenarios, and uncertainty-set size.
- For multiple objectives, show trade-offs or Pareto solutions rather than hiding preferences in arbitrary weights.
- Validate out of sample or by stress scenarios; distinguish model optimum from real-world implementability.

## G. Dynamical systems and simulation

- Analyze equilibria, stability, bifurcation or reproduction thresholds when relevant.
- Check discretization, step-size, truncation, and numerical stability.
- Verify implementation against conservation identities or solvable cases; validate against independent observations.
- Use warm-up, multiple seeds/replications, Monte Carlo standard errors, and convergence checks.

## H. Robustness and communication

- Test plausible alternative specifications, preprocessing choices, priors, covariance structures, and validation splits.
- State failure signs and a simpler fallback.
- Distinguish association, prediction, mechanism, and causation.
- State the population, time, and space over which conclusions may generalize.

## Recommended deep-dive response order

1. Why this model answers the user's question.
2. Mathematical formulation and parameter meanings.
3. Assumptions and data requirements.
4. Estimation/computation.
5. Error and dependence structure.
6. Inference or model-specific validation.
7. Diagnostics and failure signs.
8. Sensitivity, robustness, alternatives, and interpretation limits.
9. Implementation plan; code only when requested.
