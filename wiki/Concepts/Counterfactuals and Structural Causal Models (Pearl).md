---
title: "Counterfactuals and Structural Causal Models (Pearl)"
type: concept
domains: [causality, philosophy-of-science, statistics, philosophy-of-mind, ai]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, counterfactuals, structural-causal-models, scm, potential-outcomes, neyman-rubin, abduction-action-prediction, probability-of-necessity, probability-of-sufficiency, but-for-causation, climate-attribution, hume, lewis, rung-3]
---

# Counterfactuals and Structural Causal Models (Pearl)

> Rung 3 of the Ladder of Causation: reasoning about what *would have happened* had things been different. Pearl's structural causal models (SCMs) formalize counterfactual computation via functional equations and a three-step algorithm (abduction → action → prediction). SCMs ground the legal "but-for" standard of causation, probability of necessity (PN) and probability of sufficiency (PS), and applications such as climate attribution. The Neyman-Rubin potential-outcomes framework covers the same ground but without diagrams, making identifiability conditions opaque.

## What Counterfactuals Are

A **counterfactual** is a conditional claim about what would happen in a world that is (or was) different from the actual world:
- "If I had taken the aspirin, would my headache have gone away?"
- "If the firm had not raised prices, would it have retained those customers?"
- "Was it the defendant's action that caused the plaintiff's harm?"
- "Would this hurricane have occurred without climate change?"

These are **rung-3** questions (see [[Concepts/Ladder of Causation (Pearl)]]). They cannot be answered by observational data (rung 1) or by interventional data alone (rung 2), because they ask about a *specific individual in a specific situation* — not a population under a hypothetical intervention.

Historical grounding:
- **Hume** ("but-for" causation): "We may define a cause to be an object followed by another, and where all the objects similar to the first are followed by objects similar to the second. Or in other words, where, if the first object had not been, the second never had existed." This is the counterfactual (but-for) definition. See [[Concepts/Necessary Connexion and the Two Definitions of Cause (Hume)]].
- **David Lewis** (possible-worlds analysis): a counterfactual "If A had happened, B would have happened" is true if in the closest possible world where A is true, B is also true. This captures the intuition but does not give a computational procedure.

Pearl's SCMs provide the computational procedure that Lewis's possible-worlds semantics lacked.

## Structural Causal Models (SCMs)

A **structural causal model** (SCM) consists of:
1. **Endogenous variables** V = {X₁, ..., Xₙ}: the variables of interest.
2. **Exogenous variables** U = {U₁, ..., Uₙ}: background variables representing all unmeasured influences, one per endogenous variable.
3. **Structural equations**: for each Xᵢ, a function Xᵢ = fᵢ(parents(Xᵢ), Uᵢ). This specifies the mechanism by which the parents and the exogenous noise determine Xᵢ.
4. **Distribution over exogenous variables**: P(U) — the joint distribution of background factors.

The structural equations are not regression equations — they are **functional** (mechanism-encoding) equations. The direction of each equation is asymmetric (causes produce effects, not vice versa); reversing the equation would be scientifically wrong even if mathematically valid.

**Minimal example**: A model with X (treatment), Y (outcome), and U (unmeasured confounder):
- X = fₓ(U, Uₓ) — X is caused by the confounder U and its own noise Uₓ
- Y = fᵧ(X, U, Uᵧ) — Y is caused by X, the confounder, and its own noise

## The Three-Step Counterfactual Procedure

To compute "What would Y have been, for *this individual*, had X been set to x' instead of x?" where we observed X=x:

**Step 1 — Abduction**: Use the observed evidence (X=x and all other observations for this individual) to update the distribution over exogenous variables U. This "pins down" the background context for this individual. In the deterministic case, it uniquely identifies the values of all U's.

**Step 2 — Action**: Apply the do() operation (graph surgery) to the structural equations. Replace the equation for X with X = x' (the counterfactual value).

**Step 3 — Prediction**: Compute the distribution of Y using the modified equations and the updated exogenous variables from Step 1. The result is the counterfactual outcome Y_{x'} for this individual.

**Crucial feature**: Step 1 uses actual observed data to characterize *this specific individual*. This is what makes rung-3 different from rung-2: rung-2 (do-calculus) asks about a hypothetical population; rung-3 asks about the individual in this specific context.

## Probability of Necessity and Probability of Sufficiency

Two formal measures of causal attribution for individual cases:

**Probability of Necessity (PN)**: Given that X occurred and Y occurred, what is the probability that Y would *not* have occurred had X not occurred?
$$PN = P(Y_{x'=0} = 0 \mid X = 1, Y = 1)$$

This formalizes the **"but-for" standard** used in tort law: the defendant's action is a cause of harm if, but for that action, the harm would not have occurred.

**Probability of Sufficiency (PS)**: Given that X did not occur and Y did not occur, what is the probability that Y *would* have occurred had X occurred?
$$PS = P(Y_{x=1} = 1 \mid X = 0, Y = 0)$$

Neither PN nor PS alone fully characterizes causation. A brick thrown through a window has high PN (but for the throw, no breakage) but also high PS (the throw was sufficient). A preempted cause has PN = 0 (the second cause would have produced the effect anyway) but PS = 1.

**Legal and moral implications**: PN captures the "necessary cause" standard; PS captures "sufficient cause." Disputes about causation in law, epidemiology, and ethics often reduce to which measure is appropriate given the context.

## Neyman-Rubin Potential Outcomes Framework

An alternative notation widely used in statistics and econometrics:
- Y(x): "the value Y would take if X were set to x" (potential outcome).
- The causal effect of X on Y for an individual is Y(1) − Y(0) (binary treatment).
- **Fundamental problem of causal inference**: for any individual, we can observe only one of Y(0) or Y(1) — the counterfactual is by definition unobserved.

The potential outcomes framework operates at rung 3 but (in its standard form) **does not use diagrams**. Pearl's critique:
- Without a diagram, it is unclear which quantities are identifiable from observational data and which are not.
- The assumptions needed for identification (ignorability, exchangeability, consistency) are stated in terms of potential outcomes, not in terms of the data-generating mechanism — making them hard to verify or falsify from domain knowledge.
- Pearl's SCM framework is a **superset**: every potential outcomes analysis can be translated into SCM language, but not vice versa.

The debate between the "Pearl school" (diagrams + do-calculus) and the "Rubin school" (potential outcomes without diagrams) is an active methodological dispute in statistics and epidemiology.

## Climate Attribution

A major application of rung-3 counterfactual reasoning: attributing specific weather events to anthropogenic climate change.

Procedure (using SCMs):
1. Build a climate model (the structural equations).
2. Abduction step: use observations of the actual event (e.g., the 2003 European heatwave) to calibrate the model.
3. Action step: apply do(anthropogenic forcings = 0) — remove the human contribution to climate change.
4. Prediction step: estimate the probability of the event in the counterfactual world.

**Probability of necessity**: what is the probability that this specific heatwave would *not* have occurred without climate change? Studies of the 2003 European heatwave found PN ≈ 0.75 — the heatwave was at least 90% likely to have been caused (in the but-for sense) by anthropogenic climate change.

This is rung 3 because it asks about *this specific event*, not the abstract probability of a heatwave under a different global policy.

## Contradictions / Open Questions

- > [!warning] Pearl vs. Neyman-Rubin potential outcomes: same rung-3 territory, different formal tools. Pearl argues diagrams make identifiability conditions explicit and verifiable; Rubin school argues potential outcomes are more flexible and less reliant on correctly specified structural equations. No consensus. See [[Thinkers/Judea Pearl]].
- > [!warning] SCMs require specifying structural equations — including the functional form fᵢ and the distribution of Uᵢ. In practice, both are unknown. Counterfactual results can be sensitive to these choices. Non-parametric identification (identifying causal effects without parametric assumptions about the functions) is a major technical challenge.
- SCMs are deterministic at the structural-equation level; all randomness is in U. This supports Pearl's compatibilist discussion of free will (with [[Thinkers/Daniel Dennett]]'s *Freedom Evolves*): the world is structurally deterministic, but counterfactual agency — the agent's ability to reason about "what would have happened if I had acted differently" — is still coherent and practically important.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Ladder of Causation (Pearl)]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Mediation and Direct-Indirect Effects (Pearl)]]
- [[Concepts/Necessary Connexion and the Two Definitions of Cause (Hume)]]
- [[Thinkers/Hume]], [[Thinkers/Daniel Dennett]]
- [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). Pearl's rung-3 formal apparatus: SCMs, three-step counterfactual computation, PN/PS, and comparison with the Neyman-Rubin potential-outcomes framework.*
