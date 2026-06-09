---
title: "Confounding and Back-Door Criterion (Pearl)"
type: concept
domains: [causality, statistics, epidemiology, philosophy-of-science]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, confounding, back-door-criterion, front-door-adjustment, deconfounding, instrumental-variables, simpsons-paradox, collider-bias, sewall-wright, observational-study, rct]
---

# Confounding and Back-Door Criterion (Pearl)

> Confounding occurs when a common cause of X and Y distorts the apparent causal relationship between them. Pearl's back-door criterion provides a graph-theoretic rule for identifying which variables to adjust for — and which not to — in order to recover the true causal effect P(Y | do(X)) from observational data. The front-door criterion handles cases where confounders are unmeasured. Resolving confounding requires a causal diagram, not just data.

## What Is Confounding?

A **confounder** is a variable that is a common cause of both the treatment (X) and the outcome (Y). In a causal diagram, it appears as the center of a fork: C←U→Y (where U is the confounder). This creates a spurious association between X and Y that does not reflect the direct causal effect of X on Y.

Classic example: carrying a lighter is associated with lung cancer, but lighters do not cause cancer. The confounder is smoking: smokers are more likely to carry lighters (X←U) and more likely to get cancer (U→Y). Adjusting for smoking removes the spurious lighter–cancer association.

Confounding is not visible in the data alone. Two datasets with identical P(X,Y,Z) distributions can be confounded or unconfounded depending on the causal structure — which is not encoded in the distribution. This is the fundamental reason Pearl insists a causal model is required.

## The Back-Door Criterion

A set Z of observed variables satisfies the **back-door criterion** relative to (X → Y) in causal diagram G if:
1. **Z blocks every back-door path** from X to Y. A back-door path is any path that has an arrow pointing *into* X — i.e., a path that enters X "from behind" via its causes.
2. **Z contains no descendants of X**. Conditioning on a descendant of X can block causal paths or open new collider-induced paths.

When Z satisfies the back-door criterion, the causal effect is identified by the **adjustment formula**:
$$P(Y = y \mid do(X = x)) = \sum_z P(Y = y \mid X = x, Z = z) \cdot P(Z = z)$$

This stratified regression is the formal justification for what epidemiologists call "adjusting for confounders" — but with the crucial addition that the graph, not the data, determines which variables to adjust for.

## What Not to Adjust For: The Mediator and Collider Traps

Knowing what *not* to condition on is as important as knowing what to adjust for:

**Do not adjust for mediators**: if M lies on the causal path X→M→Y, conditioning on M blocks the very effect we want to estimate. Example: if we want to know the total effect of education (X) on income (Y) and occupation (M) is a mediator, adjusting for occupation removes the indirect pathway through which education affects income.

**Do not adjust for colliders**: conditioning on a collider C of X and Y (i.e., X→C←Y or X→C←U where U confounds) opens a spurious path, introducing bias rather than removing it. The birth-weight paradox is the paradigmatic case: conditioning on low birth weight (a collider of smoking and genetic defects) creates a spurious protective effect of smoking.

**Do not adjust for descendants of confounders that are also colliders**: this is a more subtle form of collider bias where an intermediate variable serves both as a proxy for a confounder and as a collider.

## Five Deconfounding Games

Pearl presents a hierarchy of cases:

1. **Direct adjustment (back-door satisfied by observed covariates)**: Straightforward — adjust for the confounders using the back-door formula.

2. **No measured back-door set exists, but the front-door criterion applies** (see below): Use the front-door adjustment.

3. **Instrumental variables**: When neither back-door nor front-door apply, a valid instrument Z (independent of confounders, no direct effect on Y, associated with X) identifies the causal effect via the instrumental variable formula.

4. **Regression discontinuity**: Near a threshold, assignment to X is effectively random — a natural experiment.

5. **Difference-in-differences**: Compare treatment and control groups before and after an intervention, assuming parallel trends.

Games 1–2 are Pearl's core tools; games 3–5 are allied methods. In all cases, the diagram determines which game is applicable.

## Front-Door Adjustment

When confounders are unmeasured and no back-door adjustment is possible, a **mediator M** on the path X→M→Y may permit identification via the front-door criterion:

**Conditions** (M satisfies the front-door criterion for X→Y if):
1. M intercepts all directed paths from X to Y (M is the only route).
2. There are no unblocked back-door paths from X to M.
3. All back-door paths from M to Y are blocked by X.

**Formula**:
$$P(Y = y \mid do(X = x)) = \sum_m P(M = m \mid X = x) \sum_{x'} P(Y = y \mid X = x', M = m) P(X = x')$$

**Illustration**: smoking (X) → tar deposits in lungs (M) → cancer (Y), with unmeasured genetic susceptibility confounding smoking and cancer. Even though the confounder is unmeasured, the front-door formula uses (a) the unconfounded X→M effect and (b) the M→Y effect (blocked by conditioning on X) to reconstruct the total X→Y causal effect.

## Instrumental Variables

When neither back-door nor front-door applies, a valid **instrument Z** allows identification of the causal effect. Z must satisfy:
1. Z is independent of all confounders (no arrow from any confounder to Z).
2. Z has no direct effect on Y (only through X).
3. Z is associated with X.

**Historical case — John Snow (1854)**: Snow identified the cholera–water source link using the different water companies serving London neighborhoods as an instrument. The company assignment was essentially random (historical accident of pipe layout), satisfying conditions 1–2; companies differed in water source quality, satisfying condition 3.

**Mendelian randomization**: In epidemiology, genetic variants that predict exposure levels (e.g., variants that affect LDL cholesterol) are used as instruments to estimate the causal effect of the exposure on outcomes (e.g., heart disease), since genetic variants are randomly assigned at conception (satisfying condition 1) and typically affect outcomes only through the exposure (condition 2).

**Historical priority dispute**: Pearl credits Philip Wright (1928) as the originator of the instrumental variable method (his *The Tariff on Animal and Vegetable Oils* used supply-side weather instruments to identify demand curves). Sewall Wright may have contributed; the attribution is contested.

## Simpson's Paradox and Causal Resolution

**The paradox**: An aggregate trend X→Y reverses when the data are stratified by Z. Example: a treatment appears effective overall but harmful in every subgroup.

**Pearl's resolution**: Simpson's paradox is not a statistical puzzle — it is a *causal* problem. The correct table to use (aggregate or stratified) depends on the causal structure:
- If Z is a **confounder** (common cause of X and Y): stratify — use the subgroup-specific estimates.
- If Z is a **mediator** (on the causal path X→Z→Y): do not stratify — use the aggregate estimate.
- If Z is a **collider** (common effect of X and Y): do not condition on Z at all.

Data alone cannot resolve the paradox because the data do not encode the causal structure. The diagram is required. This is Pearl's sharpest demonstration that "data are profoundly dumb" — the same numbers demand different actions depending on the causal story.

## Contradictions / Open Questions

- > [!warning] Pearl vs. Epidemiology tradition: many epidemiologists chose confounder sets based on domain knowledge and "common sense" rules (e.g., "include everything correlated with X and Y"), not graphical criteria. Pearl argues this leads to systematic errors (adjusting for colliders or mediators). The adoption of DAG-based confounding analysis has been slow in some fields. See [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]].
- The back-door criterion assumes the causal diagram is correctly specified. If the diagram is wrong (e.g., a confounder is missing), the adjustment is invalid — and no statistical test can detect this from data alone.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Concepts/Mediation and Direct-Indirect Effects (Pearl)]]
- [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]]
- [[Concepts/Necessary Connexion and the Two Definitions of Cause (Hume)]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). The core tools for moving from observational data to causal estimates: back-door criterion, front-door adjustment, instrumental variables, and the causal resolution of Simpson's paradox.*
