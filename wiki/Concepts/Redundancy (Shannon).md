---
title: "Redundancy (Shannon)"
type: concept
domains: [information-theory, communication, ai, language, computation]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, redundancy, entropy, language, compression, error-correction, 1948]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# Redundancy (Shannon)

> In Shannon's framework, the redundancy of a source is one minus its relative entropy: 1 − (H / H_max), where H is the actual entropy rate and H_max is the maximum possible entropy if symbols were independent and equiprobable. It measures the fraction of the message that is determined by the statistical structure (constraints, correlations) of the source rather than free choice. For ordinary English (considering structure up to ~8 letters), redundancy is roughly 50%. Redundancy enables both compression (noiseless channels) and error resistance (noisy channels).

## Summary

Given a source restricted to a certain alphabet, the maximum entropy it could have (if successive symbols were chosen independently and with equal probability) is log |alphabet|. The actual entropy rate H of the source, accounting for its statistical dependencies, is lower. Relative entropy = H / log |alphabet|. Redundancy = 1 − relative entropy.

Shannon illustrates with English (27 symbols: 26 letters + space). Successive approximations to English text (zero-order random; first-order by letter frequencies; second-order digrams; third-order trigrams; then word-level) show increasing resemblance to real text. Calculation of entropy from these approximations, plus other methods (letter deletion/restoration experiments, cryptography results), yields ~50% redundancy for English: when writing, roughly half the letters are fixed by the language's structure and half represent genuine choice.

Redundancy has two faces:
- In a noiseless channel, it represents "waste" that can be removed by efficient coding (source coding theorem), allowing transmission at rate C/H.
- In a noisy channel or storage medium, redundancy provides protection: errors can often be detected/corrected from context. Natural language already exploits this (we can read text with many letters missing or garbled). Explicit error-correcting codes introduce controlled redundancy to approach the capacity limit with low error.

The paper notes extremes: Basic English has very high redundancy (limited vocabulary); Joyce's *Finnegans Wake* pushes in the other direction. Crossword puzzles are possible only up to a certain redundancy level (too high and constraints make large puzzles impossible; zero redundancy would make any letter string valid).

## Key Claims / Positions

- Redundancy is a measurable, exploitable property of real sources (especially natural language) arising from statistical constraints.
- It is the key resource that makes both data compression and reliable communication over noisy media possible.
- English's ~50% redundancy (local constraints) explains both why it is compressible and why it tolerates substantial noise via context.

## Contradictions / Open Questions

- > [!warning] Shannon treats redundancy as a statistical fact about symbol sequences, bracketed from semantics. Yet in natural language, much of the "structure" that creates redundancy is semantic, syntactic, and pragmatic (meaning, grammar, world knowledge). This raises questions for AI: when LLMs exploit redundancy for prediction, are they capturing "mere statistics" or something closer to meaning? Ties to Turing on originality and to debates about whether current models truly understand or merely model surface redundancy.
- Long-range dependencies (beyond 8 letters) increase redundancy further; modern large models capture much more, driving estimated entropy of text lower. Is there a fundamental lower bound, or does better modeling approach the "true" semantic entropy?
- In the vault: context engineering and scaffolds are deliberate ways to *inject* redundancy/priors so the model operates in a lower-entropy regime. Prediction in LLMs is entropy minimization; the "redundancy" of training data is what makes generalization (and hallucination) possible.

## Sources

- Primary: [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]] (English approximations section, redundancy calculation of ~50%, discussion of its implications for coding and noise resistance).

## Related

- [[Thinkers/Claude Shannon]]
- [[Concepts/Entropy (Shannon)]], [[Concepts/Channel Capacity (Shannon)]], [[Concepts/Equivocation (Shannon)]], [[Concepts/Noiseless Channel Coding Theorem]], [[Concepts/Noisy Channel Coding Theorem]]
- AI concepts: [[Concepts/Context Engineering]] (providing external structure/priors is like increasing the known redundancy to reduce uncertainty the model must resolve), [[Concepts/Reasoning Scaffolds]] (imposing structure reduces the effective branching/entropy)
- Language and vault meta: the wiki itself is a highly redundant, structured source (cross-links, schema, index) designed for reliable "transmission" of knowledge across time and queries; ingest is a form of matching new sources to the existing "channel" of the vault.
- [[Thinkers/Alan Turing]] (learning machines are educated on structured, redundant data; redundancy in training "language" enables generalization)

*Concept page created 2026-06-04 during Shannon 1948 ingest. Explains both the compressibility of language and its robustness, with direct application to modern AI prediction and error tolerance.*