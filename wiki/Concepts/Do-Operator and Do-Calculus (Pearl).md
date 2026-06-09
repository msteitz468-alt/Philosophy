---
title: "Do-Operator and Do-Calculus (Pearl)"
type: concept
domains: [causality, statistics, ai, philosophy-of-science]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, do-operator, do-calculus, intervention, graph-surgery, identification, causal-inference, back-door, front-door, shpitser, completeness]
---

# Do-Operator and Do-Calculus (Pearl)

> The do-operator formalizes the distinction between *observing* and *doing*: P(Y | X=x) captures what we learn by seeing X=x in the world; P(Y | do(X=x)) captures what would happen if we *set* X to x by external intervention, severing X from its natural causes. Do-calculus is the system of three rules that allows systematic derivation of P(Y | do(X)) — and more complex interventional and counterfactual expressions — from observational data and a causal diagram. Proven complete by Shpitser (2006): every identifiable causal effect can be found using these rules.

## The Core Distinction: Seeing vs. Doing

The fundamental insight: **observing that X=x and setting X=x are mathematically distinct operations**. In standard probability, P(Y | X=x) is a conditional probability — it restricts attention to the subset of the world where X happens to equal x. In a causal diagram, those cases may be selected partly by confounders (common causes of X and Y), which distorts the apparent X→Y relationship.

The do-operator models a different operation: **graph surgery**. To compute P(Y | do(X=x)):
1. Remove all arrows *into* X from the causal diagram. This represents cutting X free from its natural determinants (confounders, prior variables).
2. Set X = x in the mutilated graph.
3. Propagate the effects of X=x through the remaining causal structure.

The mutilated graph models what happens in a randomized controlled trial (RCT): the experimenter assigns X by fiat, breaking any dependence between X and confounders. Crucially, this operation can be computed from observational data — if the causal diagram is known — without actually running an experiment.

## Formal Notation

- P(Y | X=x): observational — "what fraction of cases where X=x also have Y=y?"
- P(Y | do(X=x)): interventional — "if we set X=x by force, what distribution of Y results?"
- These are equal when X has no confounders (no common causes of X and Y).
- They differ when confounders exist: the observational estimate is biased; the do() estimate gives the true causal effect.

## The Back-Door Adjustment

The most commonly used tool for computing P(Y | do(X)) from observational data. A set Z of variables satisfies the **back-door criterion** relative to (X, Y) if:
1. Z blocks every "back-door path" from X to Y — noncausal paths that enter X through its parents (back-door paths = paths with an arrow pointing *into* X).
2. No element of Z is a descendant of X (conditioning on a descendant of X can open collider paths or block the causal path).

If Z satisfies the back-door criterion:
$$P(Y = y | do(X = x)) = \sum_z P(Y = y | X = x, Z = z) \cdot P(Z = z)$$

This is the standard adjustment formula used in observational epidemiology when confounders are measured.

## The Front-Door Adjustment

When no measured set Z satisfies the back-door criterion (e.g., the confounder U is unmeasured), a mediator M may still allow identification. M satisfies the **front-door criterion** if:
1. M blocks all directed paths from X to Y (M is the complete mediator).
2. There are no unblocked back-door paths from X to M.
3. All back-door paths from M to Y are blocked by X.

Under these conditions:
$$P(Y = y | do(X = x)) = \sum_m \left[\sum_{x'} P(Y = y | X = x', M = m) P(X = x')\right] P(M = m | X = x)$$

This is the front-door formula. Historically illustrated by the smoking → tar deposits → cancer example: even if the confounder (genetic susceptibility to both smoking and cancer) is unmeasured, we can identify the causal effect by tracking the mechanism through the mediator (tar deposits).

## Do-Calculus: Three Rules

Pearl's do-calculus provides a complete set of rules for transforming expressions involving do() operators into observationally computable quantities. Let G be the causal DAG, G_{X̄} the graph with arrows into X removed, and G_{X} the graph with arrows out of X removed. Let W, X, Y, Z be arbitrary disjoint sets of variables.

**Rule 1 (Insertion/deletion of observations)**: If Y is d-separated from Z in G_{X̄}, conditioned on W:
$$P(Y | do(X), Z, W) = P(Y | do(X), W)$$

**Rule 2 (Action/observation exchange)**: If Y is d-separated from Z in G_{X̄Z} (graph with arrows into X removed and arrows into Z removed), conditioned on W:
$$P(Y | do(X), do(Z), W) = P(Y | do(X), Z, W)$$
(The intervention on Z can be replaced by observation of Z.)

**Rule 3 (Insertion/deletion of actions)**: If Y is d-separated from Z in G_{X̄, Z(W)} (graph with arrows into X and arrows out of Z(W) removed, where Z(W) is the subset of Z not an ancestor of W), conditioned on W:
$$P(Y | do(X), do(Z), W) = P(Y | do(X), W)$$
(The intervention on Z can be deleted.)

**Completeness theorem (Shpitser, 2006)**: A causal effect P(Y | do(X)) is non-parametrically identifiable from observational data + the causal diagram *if and only if* it can be derived using the three rules of do-calculus. This closed the major open question: the calculus is not just sufficient but necessary.

## Identification: The Core Problem

The central question of causal inference is **identification**: given a causal diagram and observational data, can P(Y | do(X)) be computed? Not every causal effect is identifiable. If the diagram contains an unidentifiable structure (a "hedge" in Shpitser's notation), no amount of data or algebraic manipulation can recover the causal effect without additional assumptions.

Do-calculus is the complete solution to the identification problem: apply the three rules to rewrite P(Y | do(X)) into an expression involving only observational probabilities P(·) without any do() operators. If this succeeds, the effect is identifiable; if the rules cannot eliminate all do() operators, the effect is not identifiable from observational data alone.

## Relation to Experiments (RCTs)

A randomized controlled trial implements the do() operator physically: random assignment severs the correlation between the treatment variable and confounders. Pearl's contribution is to show that RCTs are not *always* necessary: when a valid adjustment set exists (back-door or front-door), observational data suffices. This has major implications for epidemiology, economics, and social science — where RCTs are often impossible, unethical, or cost-prohibitive.

## Contradictions / Open Questions

- > [!warning] Pearl's do-calculus vs. Neyman-Rubin potential outcomes: both express rung-2 quantities, but Pearl's framework uses explicit diagrams to determine identifiability, which the potential-outcomes framework does not. Pearl argues diagrams make hidden assumptions explicit; critics argue diagrams require causal knowledge that is often unavailable. See [[Thinkers/Judea Pearl]].
- Do-calculus assumes the causal diagram is known. In practice, learning the diagram from data (causal discovery) is a separate, hard problem. The causal revolution provides tools for *using* a diagram; constructing the right diagram requires domain knowledge and/or causal discovery algorithms.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Ladder of Causation (Pearl)]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Confounding and Back-Door Criterion (Pearl)]]
- [[Concepts/Counterfactuals and Structural Causal Models (Pearl)]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). The formal apparatus of Pearl's rung-2 causal inference: do-notation, graph surgery, back-door/front-door adjustments, and the complete three-rule calculus.*
