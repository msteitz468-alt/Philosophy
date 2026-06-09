---
title: "Causal Diagrams and DAGs (Pearl)"
type: concept
domains: [causality, statistics, ai, philosophy-of-science, cognitive-science]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, causal-diagrams, dags, directed-acyclic-graphs, d-separation, chains, forks, colliders, bayesian-networks, sewall-wright, path-diagrams, confounding, collider-bias]
---

# Causal Diagrams and DAGs (Pearl)

> Directed acyclic graphs (DAGs) with variables as nodes and directed edges as causal relations are Pearl's formal language for representing knowledge about data-generating mechanisms. Unlike Bayesian networks (which only represent probabilistic dependence), causal diagrams encode structural claims about *mechanism*: which variables directly cause which others. They enable identification of interventional and counterfactual quantities, resolution of Simpson's paradox, and detection of collider bias. Historical precursor: Sewall Wright's path diagrams (1920s).

## What a Causal Diagram Is

A causal diagram is a **directed acyclic graph (DAG)** where:
- Each **node** represents a variable (measured or unmeasured).
- Each **directed edge** (arrow) A→B represents the claim: A is a direct cause of B (in the context of the other variables in the diagram).
- **Acyclicity**: no variable is its own ancestor (no feedback loops in the static representation; dynamic feedback can be represented with time-indexed variables).

The arrows are **structural claims**, not merely statistical ones. The direction matters: A→B says A causes B, not that A and B are correlated (which is symmetric). This is what distinguishes a causal diagram from a Bayesian network, even though both use DAGs.

**What the arrows mean**: each arrow represents the existence of a direct causal mechanism. An arrow from A to B says: there is a process by which changes in A produce changes in B, holding all other parents of B constant. Absence of an arrow is also a claim: no direct mechanism from A to B.

## The Three Fundamental Junction Types

All causal reasoning with diagrams reduces to understanding three basic patterns:

### Chain: A → B → C
B mediates the effect of A on C. Information flows from A to C through B.
- A and C are (marginally) associated.
- **Conditioning on B blocks the flow**: if we know B, knowing A tells us nothing more about C (A ⊥ C | B). This is the mediation pattern.
- Practical implication: if we condition on a mediator, we may block the causal path we are trying to estimate. (Example: conditioning on "tar deposits" when studying smoking → cancer blocks the front-door mechanism.)

### Fork: A ← B → C
B is a common cause (confounder) of A and C. B creates a spurious association between A and C.
- A and C are associated (because both are effects of B), even though neither causes the other.
- **Conditioning on B blocks the spurious flow**: A ⊥ C | B. This is the deconfounding operation: stratify on (or adjust for) B to remove the spurious association.
- This is the formal basis for the back-door adjustment.

### Collider: A → B ← C
B is a common effect of A and C. By default, A and C are *independent* (no spurious association) — the collider *blocks* the path.
- **Conditioning on B *opens* the path**: once we know B, A and C become dependent (A ⊥ C becomes false). This is the crucial counterintuitive result.
- This is the source of collider bias, Berkson's paradox, and the birth-weight paradox.

## d-Separation

**d-separation** (directional separation) is the formal criterion for reading conditional independence from a DAG. A set of variables Z d-separates X from Y if and only if every path between X and Y is "blocked" by Z, where blocking is defined by the three junction rules:
- A chain A→B→C is blocked by conditioning on B.
- A fork A←B→C is blocked by conditioning on B.
- A collider A→B←C is blocked *unless* we condition on B (or any descendant of B) — conditioning opens it.

**Implication**: if X and Y are d-separated by Z in the causal diagram, then X ⊥ Y | Z in the observational distribution. This allows reading off all conditional independence relationships directly from the graph — without data.

Conversely, if X and Y are d-connected given Z, they are (in general) dependent in the observational distribution. This powers the Markov condition: every variable is conditionally independent of its non-descendants given its parents.

## Collider Bias: The Key Counterintuitive Result

The collider pattern is responsible for most confusing paradoxes in statistics and epidemiology:

**Berkson's paradox**: In a hospital, patients are selected by having at least one of two diseases A and B (both trigger hospitalization). Within the hospital population, A and B appear negatively correlated, even if they are independent in the general population — because conditioning on "hospitalized" (a collider of A and B) opens the path.

**Birth-weight paradox**: Smoking and genetic defects are both causes of low birth weight. Within the low-birth-weight subgroup (conditioning on the collider), smoking *appears* protective — because within this selected group, a low-birth-weight baby who doesn't have a genetic defect is more likely to have a smoking-related cause, and vice versa. This is a spurious, harmful artifact of collider conditioning.

**Berkeley admissions paradox** (Simpson's paradox): Overall acceptance rates appeared lower for women, but in every department women had equal or higher rates. The department variable is a collider between sex and the admission decision when applicants self-select into departments with different admit rates.

## Historical Precursor: Sewall Wright's Path Diagrams

Sewall Wright (1889–1988), American geneticist, independently developed **path diagrams** in the 1920s to represent causal relationships among variables in genetics. He used path coefficients (standardized regression-like coefficients) to decompose correlations into direct and indirect causal contributions. First applied to guinea pig coat color genetics, then to animal breeding more broadly.

Wright's method was rejected by the statistics establishment (Ronald Fisher and Karl Pearson both dismissed it as unrigorous) on the grounds that causal language was scientifically illegitimate. His work lay largely dormant outside genetics for decades.

Pearl's *The Book of Why* rehabilitates Wright as the unrecognized founder of causal diagrammatic methods. The distinction between Wright's path diagrams and Pearl's causal diagrams: Pearl's framework adds the do-calculus and the formal identification theory; Wright's work was largely correlational (rung 1) with causal interpretation added informally.

## Causal Diagrams vs. Bayesian Networks

Both use DAGs. The key difference:

| | Bayesian network | Causal diagram |
|---|---|---|
| Arrows mean | Probabilistic dependence (one direction of a factorization) | Direct causal mechanism |
| Arrow direction | Can be reversed while preserving the same distribution | Cannot be reversed without changing the causal claim |
| Enables | Rung-1 probabilistic reasoning | Rung-2 do() computations; rung-3 counterfactuals with SCMs |
| Interventions | Cannot represent do(X) | Graph surgery on do(X) is defined |
| Foundation | Conditional independence + Markov factorization | Structural equations + do-calculus |

Pearl built Bayesian networks first (1988) and then realized they were insufficient for causal questions — even though they use the same diagrammatic representation. The arrows in a Bayesian network can be reversed without changing the statistical model (any DAG consistent with the conditional independence structure works); the arrows in a causal diagram are directional claims that cannot be reversed.

## Unmeasured Confounders (Bidirected Edges)

When a common cause U of X and Y is unmeasured (latent), it cannot appear as a node in the observed diagram. Convention: represent it with a **bidirected dashed arc** X ↔ Y (sometimes written X ⟵ U ⟶ Y). This signals that X and Y share an unmeasured common cause without specifying it.

The presence of bidirected arcs constrains identifiability: many causal effects that would be identifiable without unmeasured confounding become non-identifiable. The do-calculus (and the completeness theorem) tells us exactly which effects are still identifiable given the pattern of bidirected arcs.

## Contradictions / Open Questions

- > [!warning] Causal diagram construction requires domain knowledge — this is where scientific judgment enters. The diagram encodes assumptions; if the assumptions are wrong, the causal conclusions are wrong. This is a genuine limitation and the subject of the causal discovery literature (algorithms for learning DAGs from data under faithfulness and Markov assumptions). See [[Thinkers/Judea Pearl]].
- d-separation assumes the Markov condition and faithfulness. Faithfulness fails in special cases (parameter cancellations) — a theoretical concern that limits the power of purely observational causal discovery.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Ladder of Causation (Pearl)]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Concepts/Confounding and Back-Door Criterion (Pearl)]]
- [[Concepts/Counterfactuals and Structural Causal Models (Pearl)]]
- [[Concepts/Mediation and Direct-Indirect Effects (Pearl)]]
- [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). The formal language of Pearl's causal framework: DAGs, three junction types, d-separation, collider bias, and their historical root in Wright's path diagrams.*
