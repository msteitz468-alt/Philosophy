---
title: "Decision-Making Costs Model (Buchanan-Tullock)"
type: concept
domains: [political-philosophy, economics, constitutional-economics]
created: "2026-06-29"
updated: "2026-06-29"
sources: ["The Calculus of Consent (Buchanan, Tullock).txt"]
tags: [philosophy, public-choice, voting-rules, interdependence-costs, external-costs]
---

# Decision-Making Costs Model (Buchanan-Tullock)
> The optimal collective decision rule minimizes the sum of expected external costs and decision-making costs.

## Summary

In Chapter 6 of *The Calculus of Consent* (1962), James M. Buchanan and Gordon Tullock introduce their famous **expected costs model of constitutional choice**. They demonstrate that the selection of an optimal voting rule (e.g., simple majority, qualified majority, or unanimity) is a rational trade-off between two types of costs.

### The Interdependence Costs Function

When individuals choose to collectivize an activity, they face two distinct expected costs:

1. **External Costs ($C$)**: The expected utility loss or damage imposed on an individual by collective choices that go against their interest. These costs are highest under a dictatorship (where 1 person can make choices for all) and decrease to zero under the rule of **unanimity** (where no choice can be made without the individual's consent).
2. **Decision-Making Costs ($D$)**: The expected time, effort, and bargaining resources required to reach agreement among the required number of voters. These costs are lowest under a dictatorship (where the dictator decides instantly) and increase exponentially as the voting threshold approaches **unanimity** (due to holdout problems, strategic bargaining, and transaction costs).

Together, these make up the **Interdependence Costs** ($I$) of collective organization:
\[I = C + D\]

### The Cost Minimization Graph

```
Cost
  ^
  │          Interdependence Costs (C + D)
  │                  \     /
  │                   \   /  <-- OPTIMAL RULE (K*)
  │  External Costs    \ /
  │    (C)             / \   Decision Costs
  │      \            /   \      (D)
  │       \          /     \      /
  │        \________/_______\____/
  └───────────────────────────────> N (Number of consenting individuals required)
  1                                N (Unanimity)
```

At the constitutional stage, a rational individual seeks to select the decision rule (represented by the number of consenting individuals required, $K^*$) that minimizes the sum of these two cost functions. 

### Core Implications of the Model

* **No Privileged Rule**: The model refutes the traditional political assumption that **simple majority rule** ($N/2 + 1$) is mathematically or ethically privileged. Simple majority is merely one point on the spectrum. Its optimality is contingent on the specific shapes of the cost curves for a given activity.
* **The Cost-Based Rule Shift**: 
  * If an activity has extremely high expected external costs (e.g., decisions regarding property rights or individual liberties), the $C$ curve is very steep. The optimal rule will require a high consensus threshold (qualified majority or unanimity).
  * If the decision-making costs are high (e.g., emergency defense decisions), the $D$ curve is steep, shifting the optimal rule toward a smaller executive group.
* **Optimal Decentralization**: Because decision costs rise with population size, the model provides a microeconomic rationale for **decentralization** and **fiscal federalism**: keeping jurisdictions small reduces decision costs, allowing for more inclusive, consensual voting rules.

## Key Claims / Positions

### How Different Thinkers Approach This

- **Welfare Economics (Arthur Pigou)**: Pigovian welfare economics assumes that the presence of private externalities (like factory smoke) automatically justifies government intervention. Buchanan and Tullock critique this, showing that government intervention also imposes "external costs" on minorities via voting rules, and that the transaction costs of the state may exceed the costs of private externalities.
- **Ronald Coase**: In "The Problem of Social Cost" (1960), Coase showed that in the absence of transaction costs, voluntary contracting will resolve all externalities. Buchanan and Tullock build on Coase's insight: if political decision-making costs were zero, the unanimity rule would always be used, and the political process would achieve perfect Pareto efficiency. Real-world voting rules exist solely to economize on transaction costs.

## Contradictions / Open Questions

- > [!warning] Estimating the exact shapes of the expected external and decision cost curves in advance is difficult. The model provides a clear conceptual framework, but operationalizing it to write specific constitutional clauses requires making subjective judgments about future probability distributions.
- If a society is highly divided or lacks value consensus, the decision costs curve ($D$) becomes extremely high, which can lead to political gridlock or force the selection of less inclusive, majoritarian rules that increase external exploitation.

## Sources

- [[Sources/The Calculus of Consent - Buchanan and Tullock (1962)]]

## Related

- [[Thinkers/James M. Buchanan]]
- [[Thinkers/Gordon Tullock]]
- [[Concepts/Constitutional Political Economy (Buchanan-Tullock)]]
- [[Concepts/Unanimity Rule (Buchanan-Tullock)]]
- [[Concepts/Logrolling and Vote-Trading (Buchanan-Tullock)]]
- [[Concepts/Pressure Groups and Special Interests (Buchanan-Tullock)]]
