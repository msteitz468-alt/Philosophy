---
title: "Equivocation (Shannon)"
type: concept
domains: [information-theory, communication, ai, epistemology]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, equivocation, noise, uncertainty, mutual-information, 1948]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# Equivocation (Shannon)

> Equivocation H(x|y) is the conditional entropy of the input (or message) given the output (or received signal) in a noisy communication system. It quantifies the average remaining uncertainty about what was sent after observing what was received — the information "lost" to noise. In Shannon's noisy channel model, the rate of reliable transmission is H(x) − H(x|y). The noisy channel coding theorem shows that equivocation can be made arbitrarily small for rates below capacity C by proper coding.

## Summary

In a noisy channel, the received signal y is a noisy version of the transmitted x. Even with knowledge of the channel statistics, observing y leaves some uncertainty about x. Shannon defines this as the equivocation: the conditional entropy H(x|y) = H(x,y) − H(y) (or equivalently the expected entropy of the posterior over x given y).

It has intuitive interpretations:
- Average information sent minus the information that actually gets through.
- The "noise" component that must be resolved (or tolerated) at the receiver.
- In the limit, for rates above capacity, nature "charges" at least H − C in unavoidable equivocation.

Equivocation is central to the definition of channel capacity for noisy channels: C = max [H(x) − H(x|y)].

In the fundamental theorem, if source rate H ≤ C, coding exists that drives the equivocation (or error probability) to zero (in the limit of long blocks). If H > C, equivocation cannot be reduced below H − C.

Examples in the paper include simple noisy channels (e.g., binary symmetric channel) where explicit calculation of H(x|y) and C is possible. Natural language provides a real-world case: even if some letters are garbled (noise), the redundancy allows the receiver (reader) to resolve much of the equivocation from context.

## Key Claims / Positions

- Noise does not make reliable communication impossible below capacity; it creates a quantifiable residual uncertainty (equivocation) that coding can reduce.
- Equivocation is the precise price paid for exceeding capacity or for insufficient coding.
- In practice, some equivocation is tolerable (or even useful); the theory gives the limits.

## Contradictions / Open Questions

- > [!warning] Equivocation is an average, probabilistic quantity. For any finite message there is a chance of large error. The theorems are asymptotic (long blocks, rates in the limit). This resonates with epistemology: single observations or testimonies carry risk (Hume on miracles: proportion belief to evidence); only in the long run or with redundancy/corroboration does reliability approach the ideal. See [[Concepts/Of Miracles (Hume)]], [[Concepts/Custom and Belief (Hume)]].
- In AI: LLM outputs always carry some equivocation (hallucinations, uncertainty). Techniques (scaffolds, verification, retrieval, multi-agent critique) are attempts to reduce it, i.e., to operate the "channel" closer to its effective capacity with lower residual uncertainty. Cross-model routing can be seen as choosing the channel with lower noise/equivocation for the task.

## Sources

- Primary: [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]] (sections on equivocation and channel capacity, the fundamental theorem for noisy channels, and discussion of error vs. equivocation).

## Related

- [[Thinkers/Claude Shannon]]
- [[Concepts/Channel Capacity (Shannon)]], [[Concepts/Entropy (Shannon)]], [[Concepts/Noisy Channel Coding Theorem]]
- AI practice: [[Concepts/Context Engineering]] (rich context shrinks the posterior, lowering equivocation), [[Concepts/Reasoning Scaffolds]] and verification loops (externalize and check to resolve uncertainty), agentic workflows (iterative refinement reduces residual error)
- [[Thinkers/Alan Turing]] (learning machines must handle uncertainty in their "education" signals; behavioral tests accept some equivocation in practice)
- Epistemology of testimony and evidence (Hume, Russell on sense-data vs. inference, Popper on corroboration)

*Concept page created 2026-06-04 during Shannon 1948 ingest. The precise measure of uncertainty that remains after a noisy transmission — central to coding theory and to understanding the limits of reliable generation in AI systems.*