---
title: "Logrolling and Vote-Trading (Buchanan-Tullock)"
type: concept
domains: [political-philosophy, economics, constitutional-economics]
created: "2026-06-29"
updated: "2026-06-29"
sources: ["The Calculus of Consent (Buchanan, Tullock).txt"]
tags: [philosophy, public-choice, voting-rules, logrolling, vote-trading]
---

# Logrolling and Vote-Trading (Buchanan-Tullock)
> The exchange of political votes over a sequence of decisions, allowing individuals to register their intensity of preference and trade support for mutual gain.

## Summary

In *The Calculus of Consent* (1962), James M. Buchanan and Gordon Tullock provide the first formal economic analysis of **logrolling** (vote-trading). They demonstrate that vote-trading is the political equivalent of market exchange, acting as a crucial mechanism through which individuals express preference intensity in a democracy.

### The Problem of One-Man, One-Vote

Standard democratic voting rules (simple majority, one-man, one-vote) treat all preferences as homogeneous: they record *whether* a voter supports or opposes an issue, but completely fail to measure *how intensely* they feel. 

Under a strict majority rule without trading, a bare majority that feels mildly positive about an issue can easily outvote a minority that feels intensely negative, leading to outcomes that reduce aggregate social utility.

### Logrolling as a Political Market

Logrolling resolves this by allowing voters to trade votes across a sequence of issues:

```
                            VOTER A                           VOTER B
                  ┌────────────────────────┐        ┌────────────────────────┐
                  │ Intensely supports #1  │        │ Intensely supports #2  │
                  │ Mildly opposes #2      │        │ Mildly opposes #1      │
                  └───────────┬────────────┘        └───────────┬────────────┘
                              │                                 │
                              └───────────────┬─────────────────┘
                                              │
                                              ▼
                                       THE EXCHANGE:
                               Voter A votes for Issue #2
                               Voter B votes for Issue #1
                                ➔ Both Issues Pass!
```

* **Explicit Logrolling**: Direct agreements among legislators to trade votes (e.g., "I will vote for your local harbor project if you vote for my local highway project").
* **Implicit Logrolling**: The bundling of diverse, localized benefits by political entrepreneurs into a single party platform or omnibus budget bill designed to attract a winning coalition of voters.

### The Pareto Efficiency of Vote-Trading

Buchanan and Tullock demonstrate that **with perfect side-payments or vote-trading, any collective decision-making rule can lead to Pareto-optimal allocations**. The political market allows individuals to trade away their votes on issues they care little about to secure support on issues they care about intensely. This process increases the welfare of all participants, serving as the political equivalent of voluntary market trade.

### The Pork-Barrel and Overinvestment Risks

While logrolling is allocatively efficient in theory, the authors show that under a **simple majority rule**, it creates a systemic macroeconomic bias:

* **Overextension of the Public Sector**: When public works (e.g., local roads) are financed by general national taxation but benefit only a specific locality, logrolling allows a bare majority coalition ($M/N$) to logroll a package of local projects. The coalition members receive 100% of the benefits of their local projects but pay only a fraction of the tax costs, shifting the rest onto the unorganized minority.
* **The Dominant Coalition Limit**: In representative democracies with single-member districts, the minimum coalition required to dominate can approach approximately 1/4 of all voters as the population increases, leading to highly exploitative spending.

This majoritarian logrolling results in Pigovian overinvestment and a bloated public sector.

## Key Claims / Positions

### How Different Thinkers Approach This

- **Arthur Bentley & David Truman (Pluralists)**: Documented logrolling as the key legislative process for adjusting interest group conflicts. Buchanan and Tullock build on the pluralist insight but formalize it using choice-theoretic and game-theoretic tools, analyzing its impact on Pareto efficiency and fiscal outcomes.
- **Kenneth May & Robert Dahl (Democratic Theorists)**: Dahl and May argued that political equality requires each voter's choice to have equal weight (anonymity and neutrality conditions). Buchanan and Tullock critique this, showing that ignoring preference intensity leads to inefficient, negative-sum collective choices, and that logrolling is the only practical way to restore preference intensity weights.

## Contradictions / Open Questions

- > [!warning] Democratic cultures and legal systems frequently prohibit open vote-buying or explicit side-payments as corrupt. This moral constraint prevents the political market from reaching optimal efficiency, forcing logrolling into less transparent, more complex "implicit" forms like omnibus bills.
- Logrolling can result in permanent interest cartels (pressure groups) that collude to exploit the unorganized public (taxpayers/consumers), converging with Mancur Olson's institutional sclerosis thesis. See [[Concepts/Pressure Groups and Special Interests (Buchanan-Tullock)]].

## Sources

- [[Sources/The Calculus of Consent - Buchanan and Tullock (1962)]]

## Related

- [[Thinkers/James M. Buchanan]]
- [[Thinkers/Gordon Tullock]]
- [[Concepts/Constitutional Political Economy (Buchanan-Tullock)]]
- [[Concepts/Decision-Making Costs Model (Buchanan-Tullock)]]
- [[Concepts/Unanimity Rule (Buchanan-Tullock)]]
- [[Concepts/Pressure Groups and Special Interests (Buchanan-Tullock)]]
- [[Concepts/Distributional Coalitions (Olson)]]
- [[Thinkers/John Stuart Mill]]
