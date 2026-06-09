---
title: "Entropy (Shannon)"
type: concept
domains: [information-theory, computation, ai, epistemology, communication]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, entropy, uncertainty, information, bits, probability, 1948]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# Entropy (Shannon)

> In Claude Shannon's 1948 theory, entropy H of a discrete set of probabilities p_i is H = −∑ p_i log_2 p_i (in bits). It quantifies the average information, choice, or uncertainty associated with a random variable or information source. For a stochastic source, the entropy *rate* measures information produced per symbol (or per second). Key properties: H = 0 only when the outcome is certain; H is maximized (log n) when all outcomes are equiprobable; H is additive under decomposition of choices. English text has high redundancy (low relative entropy) due to statistical structure.

## Summary

Shannon asks: given a discrete information source modeled as a Markov process (states with transition probabilities pi(j)), can we define a quantity measuring the rate at which information is produced?

For a set of possible events with known probabilities p1 … pn (but unknown which will occur), a measure H(p1, …, pn) of "choice" or "uncertainty" should satisfy:
1. Continuity in the pi.
2. For equiprobable events, monotonic increasing in n (more possibilities = more uncertainty).
3. Decomposability: H of a choice equals the weighted sum of H of sub-choices (with the coefficient for the second choice being its probability of occurring).

Theorem (proved in appendix): The only function satisfying these is H = −K ∑ pi log pi (K > 0 constant). Choosing K = 1/log 2 and log base 2 gives units of *bits*.

H is identical in form to entropy in statistical mechanics (Boltzmann H-theorem), but here it measures information/uncertainty. For a chance variable x, write H(x).

Properties (further justification):
- H = 0 iff one pi = 1 and others 0 (certainty).
- For fixed n, H maximized (= log2 n) when pi = 1/n (maximum uncertainty).
- Any averaging operation on the pi increases (or does not decrease) H.
- For joint events, H(x,y) = H(x) + Hx(y) = H(y) + Hy(x), where Hx(y) is conditional entropy.
- H(x) − Hx(y) measures the information y gives about x (mutual information / rate of transmission when y is received signal and x transmitted).

For a source, one defines the entropy rate (e.g., lim (1/n) H(X1…Xn) for stationary processes). For ergodic sources this equals the average information per symbol.

Applied to English (27-symbol alphabet including space): successive approximations (independent equiprobable letters; letter frequencies; digram structure; trigram; word frequencies; word transitions) produce text of increasing realism. This demonstrates substantial statistical structure. Shannon calculates that the redundancy of ordinary English (constraints out to ~8 letters) is roughly 50%: about half of what is written is fixed by the language, half is free choice. This redundancy enables both compression (noiseless coding) and error resistance (noisy channels).

## Key Claims / Positions

- Entropy provides a precise, additive, operational measure of information produced by a source or choice, grounded in probability and satisfying intuitive axioms.
- For sources with memory (Markov), the rate accounts for dependencies; long-range structure in natural language (English) creates high redundancy.
- Entropy rate of a source determines the minimum channel capacity needed for faithful transmission (see noiseless coding theorem).
- In noisy settings, conditional entropy (equivocation) H(x|y) quantifies information lost to noise; mutual information H(x) − H(x|y) quantifies what gets through.

## Contradictions / Open Questions

- > [!warning] Shannon's entropy is an engineering measure of uncertainty among possibilities, deliberately independent of semantics or "meaning" (see source-summary). This creates productive tension with philosophical accounts of information, knowledge, and belief (e.g., Hume on custom as the "great guide" under uncertainty; Popper on content vs. probability; confirmation holism). Does quantitative entropy capture epistemic value or "surprise" in the philosophical sense?
- Differential entropy for continuous variables is not invariant under coordinate change (unlike discrete H); it is relative. Requires care (entropy power, etc.) when generalizing.
- Modern estimates of English entropy (using better models, including LLMs) are lower than Shannon's 1948 approximations, reflecting longer-range dependencies. This improves compression and prediction but raises questions about "true" redundancy vs. model power.
- Ties to vault AI practice: next-token prediction in LLMs is explicitly entropy/cross-entropy minimization. Scaffolds and context engineering are techniques to reduce the effective entropy the model must resolve.

## Sources

- Primary: [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]] (sections on choice/uncertainty/entropy, entropy of a source, properties, English approximations, redundancy calculation ~50%).

## Related

- [[Thinkers/Claude Shannon]]
- [[Concepts/Channel Capacity (Shannon)]], [[Concepts/Redundancy (Shannon)]], [[Concepts/Equivocation (Shannon)]], [[Concepts/Noiseless Channel Coding Theorem]], [[Concepts/Noisy Channel Coding Theorem]]
- [[Thinkers/Alan Turing]] (entropy/rate as the communication counterpart to computability and learning machines; both foundational for AI)
- AI concepts: [[Concepts/Context Engineering]] (curating context reduces uncertainty/entropy for the model), [[Concepts/Reasoning Scaffolds]] (externalizing steps lowers the entropy of the solution space), [[Concepts/Cross-Model Routing]] (choosing model whose "channel" best matches the information characteristics)
- Epistemology: [[Concepts/Problem of Induction (Hume)]], [[Concepts/Custom and Belief (Hume)]], [[Concepts/Falsifiability as Criterion of Demarcation (Popper)]], [[Concepts/Confirmation Holism (Duhem-Quine Thesis)]] (quantitative measures of uncertainty and information gain)
- Language and prediction in modern sources (Daily AI Tips, Grok/Claude tutorials) — statistical structure of text is what makes LLMs work; redundancy is both compressible and protective.

*Concept page created 2026-06-04 as part of Shannon 1948 ingest. Central to information theory and the quantitative treatment of uncertainty, choice, and information rate in communication and AI.*