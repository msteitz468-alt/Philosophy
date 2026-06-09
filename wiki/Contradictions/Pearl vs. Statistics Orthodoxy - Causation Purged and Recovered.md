---
title: "Pearl vs. Statistics Orthodoxy — Causation Purged and Recovered"
type: contradiction
domains: [causality, statistics, philosophy-of-science, ai, history-of-science]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Book of Why - Judea Pearl.txt"]
tags: [pearl, causality, statistics, galton, pearson, fisher, sewall-wright, causal-revolution, simpsons-paradox, correlation, data-centrism, deep-learning, rung-1]
---

# Pearl vs. Statistics Orthodoxy — Causation Purged and Recovered

> The deepest methodological rift in the vault's AI & Cognitive Science leg: 19th-century statistics (Galton, Pearson, Fisher) founded the discipline on a deliberate exclusion of causal language — treating "cause" as metaphysical and restricting science to correlations. Judea Pearl argues this was a century-long mistake that blocked the natural sciences and social sciences from formalizing the questions they most wanted to answer, crippled AI at rung 1, and left statistical paradoxes (Simpson's, Berkson's) unresolvable without a causal model. The Causal Revolution (1990s–2010s) is the recovery.

## The Orthodoxy: Causation Is Not Science

### Galton and Pearson: Correlation Without Cause

Francis Galton (1822–1911) invented regression to the mean and correlation. Karl Pearson (1857–1936) formalized the correlation coefficient and founded the discipline of mathematical statistics. Both held a strict positivist view: *science deals only in measurable associations between phenomena*, not in unobservable "causes." Pearson wrote: "beyond such discarded fictions as 'matter' and 'force,' there lies the common property of sequences... termed cause-and-effect." Cause was metaphysical; only correlation was scientific.

This was not mere philosophical squeamishness — it shaped the entire apparatus of 20th-century statistics:
- Statistical models describe distributions, not mechanisms.
- All methods (correlation, regression, factor analysis, later ANOVA, significance testing) are fundamentally symmetric: they describe associations but do not specify the direction or mechanism of causation.
- The phrase "correlation does not imply causation" became the disciplinary mantra — but Pearson's statistics offered nothing in its place. It named the problem but provided no solution.

### Ronald Fisher: The RCT as the Only Legitimate Causal Tool

Ronald Fisher (1890–1962) took a different but complementary position. Fisher recognized that causal inference required something beyond correlation — specifically, **randomization**. The randomized controlled trial (RCT), which Fisher developed and championed, physically severs the treatment variable from confounders by randomly assigning subjects. This is the do() operation implemented in physical design.

Fisher's position had two consequences:
1. **RCTs are the gold standard** — the only legitimate method for causal inference.
2. **Observational data cannot support causal conclusions** — a position Fisher weaponized in the smoking/cancer debate of the 1950s–60s, arguing that the correlation between smoking and cancer (even with Bradford Hill's criteria) did not prove causation because there was no randomized experiment.

Pearl's critique of Fisher: Fisher was right that RCTs implement do(), but wrong that RCTs are the *only* method. Pearl's do-calculus shows that observational data, combined with a correct causal diagram, can yield valid causal inferences without an experiment. Fisher's position was excessively conservative — and in the smoking case, provided cover for industry obfuscation.

### Sewall Wright Suppressed

Sewall Wright (1889–1988), geneticist, developed **path diagrams** in the 1920s independently of the correlation-only tradition. His dot-and-arrow pictures with path coefficients represented direct causal relationships among variables. Wright's method allowed decomposition of correlations into direct and indirect causal contributions.

Fisher and Pearson both rejected Wright's approach as scientifically illegitimate. Path analysis was marginalized in statistics for decades; it survived mainly within genetics and later entered sociology and economics under the "structural equation models" label — but stripped of Pearl's formal causal interpretation and identification theory.

Pearl rehabilitates Wright as the unrecognized founder of causal diagrammatic methods. The key point: the statistics establishment's rejection of Wright was not a correction of error but an ideological exclusion, driven by the positivist commitment to correlation-only science.

## Pearl's Position: Data Are Profoundly Dumb

Pearl's central counter-argument: **the positivist commitment to correlation-only statistics created a methodological void that made science and AI unable to answer the questions they actually cared about**.

Evidence:
1. **Simpson's paradox** remained "paradoxical" for decades because it could not be resolved by statistics alone. Pearl shows it is immediately resolved once you draw the causal diagram and ask which variables to stratify on. The paradox is a symptom of the causation-free framework's inability to tell you what action to take.

2. **The smoking/cancer dispute** dragged on for decades partly because the statistics establishment had no formal causal language to evaluate the evidence. Bradford Hill's 1965 criteria were informal workarounds, not a formal causal calculus.

3. **Deep learning** is the modern culmination of the positivist tradition: a system of extraordinary power for rung-1 pattern recognition, but unable to answer rung-2 or rung-3 questions. Pearl argues current AI is repeating the mistake of the statistics orthodoxy at scale — treating data compression as the summit of intelligence.

4. **Policy failures** (e.g., birth-weight paradox in neonatology; gender equity measures that accidentally worsen outcomes by ignoring collider structures) follow directly from ignoring causal structure.

## The Causal Revolution

Pearl dates the Causal Revolution to the 1990s–2010s:
- 1986–1988: Bayesian networks (Pearl's probabilistic reasoning framework — but still rung 1)
- Early 1990s: Pearl's apostasy — recognition that Bayesian networks cannot answer causal questions; development of the do-operator
- 1993–2000: do-calculus; back-door and front-door criteria; *Causality* (2000)
- 2006: Shpitser's completeness theorem for do-calculus
- 2018: *The Book of Why* — popular account of the full framework

Key allies: Sander Greenland, James Robins, and Miguel Hernán in epidemiology (who adopted DAG methods); economists in the tradition of Angrist and Pischke (instrumental variables and natural experiments); Donald Rubin and Jerzy Neyman (potential outcomes — an earlier parallel track, without diagrams).

## Where Orthodoxy and Pearl Agree

Both the statistics orthodoxy and Pearl agree that:
- Correlation does not imply causation.
- Observational data are insufficient alone for causal inference.
- Randomized experiments are the most direct route to causal claims.

The disagreement is over what follows from the insufficiency of observational data:
- **Orthodoxy**: therefore restrict science to correlations (with RCTs as a special case).
- **Pearl**: therefore add explicit causal assumptions (encoded in a diagram) to observational data, enabling causal inference without requiring an experiment.

## The AI Connection

The modern AI version of the dispute: deep learning is the statistical orthodoxy at massive scale. It is rung-1 — extraordinarily powerful at compression and prediction, but unable by design to answer do() or counterfactual questions. Pearl's critique of deep learning is structurally identical to his critique of Galton/Pearson: treating rung-1 pattern recognition as the summit of intelligence, and refusing to add the structural (causal) assumptions that would enable rung-2 and rung-3 reasoning.

Pearl's mini-Turing test is his operationalization of the gap: a system that can answer causal questions has crossed the rung boundary; a system that can only answer associational questions has not, regardless of its performance on behavioral imitation tests. See [[Concepts/Imitation Game (Turing)]] and [[Thinkers/Alan Turing]].

## Relation to Other Vault Contradictions

- **[[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]]**: Both Pearl and Hofstadter argue that current AI (rung-1, syntax-only) is insufficient for genuine intelligence; both argue for a richer computational substrate. But their accounts of what is missing differ: Hofstadter says strange loops / sufficient self-referential complexity; Pearl says a causal inference module (rungs 2–3). They are not in direct contradiction but offer different diagnoses of the AI gap.

- **[[Concepts/Problem of Induction (Hume)]]**: Hume's problem — data never logically entail causal necessity — is in a sense the philosophical ancestor of Pearl's "data are profoundly dumb." Pearl's causal models are the pragmatic response: not a solution to Hume's philosophical problem, but a framework for making causal assumptions explicit and using them productively. See [[Thinkers/Hume]].

- **[[Concepts/Falsifiability as Criterion of Demarcation (Popper)]]**: Popper's rejection of induction as the basis of science resonates with Pearl's critique of the correlation-only tradition. Both argue that science requires going beyond the data — Popper through bold conjectures, Pearl through bold causal assumptions. A causal diagram is a bold conjecture about mechanism, subject to refutation by interventional evidence.

## Sources

- [[Sources/The Book of Why - Judea Pearl (2018)]]

## Related

- [[Thinkers/Judea Pearl]]
- [[Concepts/Ladder of Causation (Pearl)]]
- [[Concepts/Causal Diagrams and DAGs (Pearl)]]
- [[Concepts/Do-Operator and Do-Calculus (Pearl)]]
- [[Concepts/Confounding and Back-Door Criterion (Pearl)]]
- [[Thinkers/Hume]] — but-for causation; problem of induction
- [[Thinkers/Alan Turing]] — imitation game vs. mini-Turing test
- [[Thinkers/Douglas Hofstadter]], [[Thinkers/John Searle]] — related AI debates
- [[Concepts/Imitation Game (Turing)]], [[Concepts/Learning Machines (Turing)]]
- [[Concepts/Problem of Induction (Hume)]], [[Concepts/Falsifiability as Criterion of Demarcation (Popper)]]
- [[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]]

*Contradiction page created 2026-06-04 during ingest of The Book of Why (2018). The methodological dispute at the foundation of 20th-century statistics: the deliberate purge of causal language (Galton, Pearson, Fisher) vs. Pearl's Causal Revolution — with consequences for science, epidemiology, and AI.*
