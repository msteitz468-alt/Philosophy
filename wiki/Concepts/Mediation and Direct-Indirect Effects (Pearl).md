---
title: "Mediation and Direct-Indirect Effects (Pearl)"
type: concept
domains: [causality, statistics, epidemiology, philosophy-of-science]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, mediation, direct-effect, indirect-effect, controlled-direct-effect, natural-direct-effect, natural-indirect-effect, mediation-formula, simpsons-paradox, barbara-burks, scurvy, vitamin-c, berkeley-admissions]
---

# Mediation and Direct-Indirect Effects (Pearl)

> How does X affect Y — through which mechanisms? Mediation analysis partitions the total causal effect of X on Y into a direct effect (X→Y, bypassing the mediator) and an indirect effect (X→M→Y, through the mediator). Pearl's framework distinguishes controlled direct effects (CDE), natural direct effects (NDE), and natural indirect effects (NIE), and provides the Mediation Formula for estimating them. Crucially, NDE and NIE require counterfactual (rung-3) reasoning — not merely regression. Historical illustrations: scurvy and vitamin C (wrong mediator), Barbara Burks (1926, collider bias pioneer), Berkeley admissions.

## The Mediation Question

Total causal effect of X on Y = direct effect + indirect effect(s). But "direct" and "indirect" require a reference mediator M and careful definition:

- **Direct path**: X → Y (X affects Y without going through M)
- **Indirect path**: X → M → Y (X affects Y by first changing M, which then changes Y)

Applications: Does aspirin (X) cure headaches (Y) by reducing prostaglandin levels (M), or by some other mechanism? Does education (X) increase wages (Y) directly, or mainly through occupation (M)? Did the UC Berkeley admissions process (X) discriminate against women (Y) directly, or through the indirect path of department applied to (M)?

The answer shapes both scientific understanding (which mechanism to target?) and policy or legal attribution (is the direct or indirect effect what we care about?).

## Historical Case Study: Scurvy and the Wrong Mediator

18th-century British Navy discovered that citrus juice (lemon, lime) prevented scurvy. The working hypothesis was that the active ingredient was the *acidity* of citrus juice (the proposed mediator between "citrus" and "anti-scurvy"). When the Navy switched to lime juice concentrate (cheaper, more shelf-stable but less acidic — and crucially, lower in vitamin C), scurvy returned.

The error: they identified the *wrong mediator*. The true mechanism was:
- Citrus → vitamin C (M, the true mediator) → collagen synthesis → scurvy prevention

But the Navy modeled:
- Citrus → acidity (M', the wrong mediator) → anti-scurvy effect

By optimizing for acidity without vitamin C, they inadvertently eliminated the true causal mechanism. Pearl uses this as a paradigmatic example of why identifying the correct mediator matters — and why intuition about mechanism is not sufficient; formal mediation analysis is required.

## Barbara Burks (1926): A Pioneer Recovered

Barbara Burks (1902–1943) was an American psychologist who in 1926 used path diagrams (independently of Sewall Wright) to study the relative contributions of heredity and environment to IQ. She analyzed foster-child data to partition the variance in IQ between genetic and environmental influences.

More importantly, Burks was among the first to recognize **collider bias**: conditioning on a variable that is a common effect (collider) of two independent causes creates a spurious association between those causes. In her data, she noticed that "foster home quality" (a collider of parental IQ and home environment quality) needed to be handled carefully to avoid confounding the heredity–environment comparison.

Burks's work was largely forgotten, partly because she died young (suicide, 1943) and partly because the statistics establishment did not have the conceptual vocabulary to evaluate path-diagram methods. Pearl rehabilitates her in *The Book of Why* as a founder of both mediation analysis and collider-bias recognition in the social sciences.

## Formal Definitions

### Total Effect
$$TE = P(Y = y \mid do(X = x)) - P(Y = y \mid do(X = x'))$$

The total change in Y when X is changed from x' to x.

### Controlled Direct Effect (CDE)
Fix M by intervention to a specific value m:
$$CDE(m) = P(Y = y \mid do(X = x), do(M = m)) - P(Y = y \mid do(X = x'), do(M = m))$$

The CDE is a rung-2 (interventional) quantity: it asks what would happen if we both changed X and held M fixed by external manipulation. This captures the direct effect of X with M blocked.

**Limitation of CDE**: it holds M fixed at a specific value m. But the "natural" level of M varies across individuals. The CDE at m may not be the relevant quantity for policy (if we cannot actually intervene to set M = m for everyone).

### Natural Direct Effect (NDE)
The direct effect of X on Y, letting M adjust to the value it would "naturally" take under X = x' (the reference level of X):
$$NDE = P(Y_{x, M_{x'}} = y) - P(Y_{x'} = y)$$

Here Y_{x, M_{x'}} is the counterfactual outcome under X=x but with M taking the value it would have taken under X=x'. This requires a counterfactual (rung 3): we need to know "what M would be if X=x'" for each individual, while simultaneously setting X=x.

### Natural Indirect Effect (NIE)
The effect operating exclusively through the mediator, holding X's direct influence constant at x:
$$NIE = P(Y_{x', M_x} = y) - P(Y_{x'} = y)$$

Y_{x', M_x} is the counterfactual outcome under the reference X=x' but with M taking the value it would take under X=x (i.e., we change M as if X had changed, without changing X's direct path to Y).

**Decomposition**: TE = NDE + NIE (under certain assumptions, specifically no interaction between X and M on Y, and no confounding of M→Y by X). This decomposition partitions the total effect into what would happen if only the direct path were operative (NDE) and what would happen if only the indirect path were operative (NIE).

## The Mediation Formula

Under the assumption that (a) X is not confounded with Y, (b) M is not confounded with Y conditional on X, and (c) no X-M interaction on Y:

$$NDE = \sum_m \left[E(Y \mid do(X=x), M=m) - E(Y \mid do(X=x'), M=m)\right] P(M=m \mid do(X=x'))$$

$$NIE = \sum_m E(Y \mid do(X=x'), M=m) \left[P(M=m \mid do(X=x)) - P(M=m \mid do(X=x'))\right]$$

When X is randomized and there is no M–Y confounding, the do() operators reduce to ordinary conditionals, giving the traditional mediation formula in terms of observational expectations.

Key point: **the traditional regression-based mediation analysis (Baron-Kenny, 1986 in psychology) is a special case** valid only when there is no interaction between the direct and indirect paths, no unmeasured confounders of M→Y, and binary or linear relationships. Pearl's framework generalizes this and makes the assumptions explicit.

## Berkeley Admissions Paradox (Mediation Reframe)

The classic Simpson's paradox case (Chapter 6 of *The Book of Why*): overall, women applicants to UC Berkeley had lower acceptance rates than men, but within nearly every individual department, women's rates were equal or higher.

**Mediation reframe**: the question is not "did sex (X) affect admission (Y)?" but rather:
- **NDE**: what is the direct effect of sex on admission, holding constant the mediator (department applied to, M)?
- **NIE**: what is the indirect effect of sex on admission operating through department choice?

The data show: women applied to competitive departments (M was confounded with X), accounting for the aggregate disparity. The direct effect (sex → admission conditional on department) was negligible or reversed. The "discrimination" was in the indirect path (women were channeled toward, or self-selected into, more competitive departments with lower overall admit rates).

This reframe shows that mediation analysis — not just stratification — is required to understand Simpson's paradox in this case. The causal question "Is this discrimination?" requires NDE/NIE decomposition, not just aggregate vs. stratified comparisons.

## Contradictions / Open Questions

- > [!warning] NDE and NIE require counterfactual cross-world quantities (e.g., Y_{x, M_{x'}}), which are not directly observable and require structural equations (SCMs) to compute. In non-parametric models, identification of NDE/NIE requires strong assumptions (sequential ignorability, no M→Y unmeasured confounders). Violation of these assumptions is common in observational studies.
- The scurvy example illustrates that mediator misidentification leads to failed interventions. In practice, identifying the correct mediator is a scientific judgment that causal diagrams structure but do not resolve.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Counterfactuals and Structural Causal Models (Pearl)]]
- [[Concepts/Confounding and Back-Door Criterion (Pearl)]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). Pearl's formal mediation framework: CDE, NDE, NIE, the Mediation Formula, and the historical cases (scurvy, Barbara Burks, Berkeley admissions) that motivate and illustrate it.*
