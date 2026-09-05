---
name: mathematical-modeling-navigator
description: Use when a user needs to select, compare, learn, or validate a mathematical model from a research objective and data structure, especially when they are unsure which regression, correlation, multivariate, time-series, spatial, machine-learning, optimization, dynamical-system, evaluation, or simulation method applies.
---

# Mathematical Modeling Navigator

## Purpose

Turn a modeling problem into a defensible shortlist before deriving or coding anything. Route by the data-generating structure and decision objective, not by familiar model names. Never imply that a catalog covers every possible published model.

## Operating modes

1. **Selection mode:** The user has a problem or dataset but has not chosen a model.
2. **Deep-dive mode:** The user has selected or explicitly named a model and needs formulas, estimation, errors, tests, diagnostics, validation, or interpretation.
3. **Audit mode:** The user has a proposed model or paper and wants to know whether the assumptions and analysis are defensible.

## Selection workflow

1. Extract what is already known:
   - scientific question: description, association, explanation, causal effect, prediction, evaluation, optimization, control, or simulation;
   - response type: continuous, binary, categorical, ordinal, count, proportion, duration, censored, multivariate, curve/image/text, or no statistical response;
   - observational unit and dependence: independent, paired, repeated, nested, clustered, temporal, spatial, networked, or panel;
   - sample size, missingness, censoring, imbalance, zero inflation, outliers, nonlinearities, constraints, and uncertainty;
   - required output: inference, forecast, ranking, policy, feasible plan, mechanism, or scenario comparison.
2. If one missing fact would change the model family, ask the smallest possible discriminating question. If the user refuses or time is limited, state explicit conditional branches; do not announce one unconditional “best model.”
3. Read only the relevant sections of [references/model-map.md](references/model-map.md). Use adjacent branches when the problem is hybrid.
4. Produce 2–5 credible candidates. For each, state:
   - what question it answers;
   - required response/data structure;
   - decisive assumptions and minimum data needs;
   - strengths, failure modes, and why it may be rejected;
   - the key distinction from the other candidates.
5. Recommend one only when the available information supports it. Separate a primary model from sensitivity or benchmark models.
6. Do not write Python or MATLAB code in selection mode unless the user explicitly asks.

## Authority and research

Use [references/authoritative-sources.md](references/authoritative-sources.md) whenever a model is unfamiliar, niche, recently named, disputed, or materially affects the recommendation. For a decisive recommendation, prefer corroboration from two relevant entries among the five approved official domains. Cite the exact supporting pages. If the five sources do not cover the model, say so and ask whether the user permits expanding to an original paper or another authoritative source; never fill the gap from memory while presenting it as verified.

## Deep-dive workflow

Once the user selects a model, read [references/model-analysis-checklist.md](references/model-analysis-checklist.md) and provide the applicable items:

- mathematical formulation, indices, parameters, latent/random components, constraints, and estimand;
- error distribution or uncertainty structure, including covariance/dependence assumptions;
- parameter estimation or optimization method and identifiability conditions;
- assumption checks and data preprocessing that change interpretation;
- significance tests and confidence/credible intervals when inferentially meaningful;
- residual, convergence, goodness-of-fit, calibration, predictive, optimality, or stability diagnostics as appropriate;
- validation design, sensitivity/robustness analysis, failure signs, and alternatives;
- interpretation limits: association versus causation, interpolation versus extrapolation, and population scope.

Do not force p-values onto every model. For predictive models emphasize out-of-sample validation and calibration; for optimization emphasize feasibility, optimality gap, scenario sensitivity, and robustness; for simulations emphasize stochastic error, verification, validation, and replication.

Only after the user requests implementation should you ask for Python, MATLAB, or both if not already specified. Match the equations, parameterization, and diagnostics across languages.

## Audit workflow

Compare the proposed model against the intake structure and the checklist. Lead with violations that could change conclusions: wrong outcome family, ignored dependence, leakage, pseudo-replication, unidentifiable parameters, invalid validation split, unsupported causal language, or omitted uncertainty. Distinguish fatal mismatches from repairable limitations.

## Response discipline

- Label verified facts, modeling judgments, and assumptions made for progress.
- Explain why a model is suitable, not merely what command fits it.
- Never choose from statistical significance alone.
- Never treat high correlation as proof of causation or model adequacy.
- Never silently assume observations are independent.
- Prefer the simplest model that answers the question and survives diagnostics; complexity requires a concrete benefit.
