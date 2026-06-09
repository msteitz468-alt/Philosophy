---
title: "Ladder of Causation (Pearl)"
type: concept
domains: [causality, ai, cognitive-science, philosophy-of-science, statistics]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, ladder-of-causation, association, intervention, counterfactuals, do-operator, rung-1, rung-2, rung-3, strong-ai, deep-learning, mini-turing-test]
---

# Ladder of Causation (Pearl)

> Pearl's three-rung hierarchy of causal and counterfactual reasoning: Association (seeing, rung 1), Intervention (doing, rung 2), and Counterfactuals (imagining, rung 3). Each rung requires strictly richer information than the one below. All of statistics and deep learning live at rung 1; human intelligence routinely reaches rung 3. The ladder explains why data alone — no matter how abundant — cannot answer causal or counterfactual questions, and why current AI falls short of human-level reasoning.

## The Three Rungs

| Rung | Name | Question | Formal notation | Who operates here |
|---|---|---|---|---|
| 1 | Association / Seeing | What does observing X tell me about Y? | P(Y \| X) | Animals, deep learning, all of classical statistics |
| 2 | Intervention / Doing | What will happen if I *do* X? | P(Y \| do(X)) | Humans planning actions; causal AI with a diagram |
| 3 | Counterfactuals / Imagining | What would have happened if X had been different? | P(Y_x \| X' = x') | Humans reasoning morally, legally, regretfully |

The rungs are **not interchangeable**. Rung 2 cannot be derived from rung-1 data alone; rung 3 cannot be derived from rung-2 data alone. Moving up requires additional structural assumptions — encoded in a causal diagram (rung 2) or a full structural causal model (rung 3).

## Rung 1: Association

The domain of classical statistics, machine learning, and deep learning. The question is always: given that X has been *observed*, what can we infer about Y? This captures:
- Correlation: "Smokers have higher rates of lung cancer"
- Regression: "Each extra year of education predicts $X more income"
- Bayesian updating: "Given this symptom, what is the probability of this disease?"
- Deep learning: "Given this image, what is the probability it contains a cat?"

All of these can be computed from the joint probability distribution P(X, Y). They do not tell you what would happen if you *forced* X to a certain value. Pearl's example: the association between carrying a lighter and lung cancer (via the confounder of smoking) does not imply that confiscating lighters would reduce lung cancer.

**The ceiling of rung 1**: no amount of data, no algorithm, no neural network operating only on P(X, Y) can answer the question "What would happen if we set X to x?" — because the data do not distinguish correlation from causation, confounded association from direct effect.

## Rung 2: Intervention

The domain of experimental science and policy. The question is: what happens if we actively *set* X, cutting it off from its natural causes? Notation: do(X = x).

The do-operator is realized in the causal diagram by **graph surgery**: remove all arrows pointing into X and set X = x. This models what happens in a randomized controlled trial (RCT): X is assigned by the experimenter, severing its dependence on confounders.

Key examples:
- Medical: "What is the causal effect of this drug on recovery?" — requires an RCT or a back-door/front-door adjustment, not just a regression.
- Policy: "What would happen to employment if we raised the minimum wage?" — requires intervention logic, not observational correlation between wage levels and employment.
- Vaccination: "Does the vaccine prevent disease?" — P(disease | vaccinated) ≠ P(disease | do(vaccinated)), because people who vaccinate are different from those who don't.

Rung 2 requires a causal diagram (a structural model) to compute. Without knowing the causal graph, you cannot perform graph surgery. This is why Pearl insists: **a causal diagram encodes assumptions; those assumptions are what make causal inference possible**.

## Rung 3: Counterfactuals

The domain of human moral reasoning, legal causation, regret, credit, blame, and historical explanation. The question is: given that X *did* occur, what would have happened in a world where X had not occurred (or had been different)?

This goes beyond rung 2 in a crucial way: rung 2 asks about a hypothetical population (everyone treated vs. everyone untreated); rung 3 asks about *this specific individual*, given what actually happened to them.

Key examples:
- Legal: "But for the defendant's action, would the plaintiff have been harmed?" — the but-for standard of legal causation.
- Medical: "Did the drug cause this patient's side effect, given that they took it and the side effect occurred?"
- Historical: "Would the French Revolution have occurred without the financial crisis?"
- Climate: "Was this heatwave caused by climate change?" — climate attribution studies use SCMs to answer this.

Rung 3 requires full **structural causal models (SCMs)** — functional equations X_i = f_i(parents, U_i) that specify not just the causal graph but the exact mechanisms and the distributions of exogenous noise variables. See [[Concepts/Counterfactuals and Structural Causal Models (Pearl)]].

## Why the Ladder Matters for AI

Pearl's "mini-Turing test" reframes the AI challenge: instead of asking "Can the machine imitate human conversation?" (Turing's rung-1 behavioral criterion), ask "Can the machine answer causal and counterfactual questions?" This is the criterion that distinguishes human intelligence from sophisticated pattern matching.

Current deep learning (as of 2018) is rung 1. It can achieve astonishing rung-1 performance (image recognition, language generation, game playing) but:
- Cannot answer "What would happen if I intervened on X?" without being given an explicit causal model.
- Cannot answer "Why did Y happen — was X the cause?" without rung-3 machinery.
- Cannot distinguish "X predicts Y" from "X causes Y."

Pearl's argument: adding a causal-inference module (rung 2 + 3 machinery) to current AI is the key step toward human-level reasoning. No amount of additional data, parameters, or compute closes this gap because the gap is structural — it is a difference in the *type* of question being asked, not the *amount* of information available.

## Relation to Other Vault Concepts

- **[[Concepts/Do-Operator and Do-Calculus (Pearl)]]**: the formal machinery for rung 2.
- **[[Concepts/Counterfactuals and Structural Causal Models (Pearl)]]**: the formal machinery for rung 3.
- **[[Concepts/Causal Diagrams and DAGs (Pearl)]]**: the structural representation that enables the move from rung 1 to rung 2.
- **[[Concepts/Imitation Game (Turing)]]**: Turing's behavioral criterion — Pearl's mini-Turing test proposes a causal alternative.
- **[[Concepts/Learning Machines (Turing)]]**: Turing's learning machines learn from data; Pearl argues they need a causal layer.
- **[[Concepts/Cybernetics (Wiener)]]**: Wiener's feedback/control framework addresses rung-2 intervention informally.
- **[[Concepts/Multiple Drafts Model (Dennett)]]**: Dennett's account of consciousness as a rung-1/2 system (reactive, without explicit counterfactual self-modeling).

## Contradictions / Open Questions

- > [!warning] Pearl vs. deep learning advocates: can rung-2 reasoning be approximated by sufficiently large rung-1 systems? Pearl says no in principle; some empirical evidence from LLMs is ambiguous. See [[Thinkers/Judea Pearl]].
- > [!warning] Pearl's mini-Turing test vs. Turing's Imitation Game: different operational criteria for AI. See [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]] and [[Thinkers/Alan Turing]].
- Does rung 3 (counterfactual reasoning) require consciousness, or only the structural-causal machinery? Pearl's framework is silent on phenomenal consciousness; Dennett's account is relevant here.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Counterfactuals and Structural Causal Models (Pearl)]]
- [[Concepts/Imitation Game (Turing)]], [[Concepts/Learning Machines (Turing)]]
- [[Concepts/Cybernetics (Wiener)]]
- [[Thinkers/Alan Turing]], [[Thinkers/Norbert Wiener]]

*Concept page created 2026-06-04 during ingest of The Book of Why (2018). Pearl's primary organizing framework: three rungs of causal and counterfactual reasoning, with AI currently stuck at rung 1.*
