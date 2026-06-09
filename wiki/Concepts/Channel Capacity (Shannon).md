---
title: "Channel Capacity (Shannon)"
type: concept
domains: [information-theory, computation, ai, communication]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, channel-capacity, mutual-information, noisy-channel, 1948]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# Channel Capacity (Shannon)

> In Shannon's theory, the capacity C of a communication channel is the maximum rate (in bits per second) at which information can be transmitted reliably through it. For a noiseless discrete channel, C is the maximum entropy per second achievable by choice of input symbol probabilities. For a noisy channel, C = max [H(x) − H(x|y)], the maximum mutual information over all possible input distributions (x transmitted, y received). The noisy channel coding theorem states that reliable communication (arbitrarily low error) is possible at any rate below C with suitable coding, but impossible above C.

## Summary

A channel is the medium that carries signals from transmitter to receiver; it may be subject to noise. Shannon defines its capacity as the supreme limit on the rate of information transfer.

**Noiseless discrete case**: Symbols have durations and transition constraints (e.g., no two spaces in telegraphy). Capacity C is the maximum of the entropy of the output symbols per unit time, achieved by solving for the input probabilities (or state transition probabilities) that maximize entropy rate subject to the channel's constraints. Graphically represented as a state diagram; C satisfies equations involving the durations and the maximizing probabilities.

**Noisy discrete case**: Noise creates uncertainty. Let x be the input (transmitted) random variable, y the output (received). Equivocation H(x|y) is the remaining uncertainty about what was sent after observing y. The rate of transmission is H(x) − H(x|y) (information sent minus what is lost to noise; equivalently H(y) − H(y|x) or H(x) + H(y) − H(x,y)).

Channel capacity is then defined as the maximum of this quantity over all possible input sources (distributions on x):
C = max [H(x) − H_y(x)]

This reduces to the noiseless definition when H_y(x) = 0 (no noise).

The fundamental theorem for the noisy channel: if a source produces information at rate H ≤ C, there exists an encoding such that the source output can be sent over the channel with arbitrarily small error probability (or equivocation). If H > C, the equivocation is at least H − C no matter the coding. Thus C is a sharp, achievable limit. Coding introduces redundancy in a controlled way (error-correcting codes) to combat noise; rates above C necessarily leave residual uncertainty.

The paper also derives capacities for special channels (e.g., binary symmetric) and treats the continuous case (additive white Gaussian noise in band-limited channels yields the familiar C = W log₂(1 + P/N) formula in the limit).

## Key Claims / Positions

- Every channel has a definite capacity C that is the absolute upper bound on reliable information rate.
- C is an operational quantity: it is the highest rate at which one can design codes guaranteeing (in the limit) arbitrarily reliable transmission.
- Noise does not destroy the possibility of reliable communication below C; proper coding (introducing the right redundancy) suffices.
- Natural sources with redundancy (e.g., English) already contain some protection against noise via context, though explicit coding can do better or approach the limit.

## Contradictions / Open Questions

- > [!warning] The existence of a sharp capacity even for noisy channels seems counter-intuitive ("we can never send certain information"). Shannon shows that by allowing redundancy to grow (but in the right way), error can be driven to zero at rates up to C. This has deep implications for AI: LLMs can be viewed as "channels" with their own capacity and noise characteristics (hallucinations = equivocation); prompting, scaffolding, and verification are forms of coding/source matching to stay below effective capacity and reduce error.
- The definition and theorems assume the channel is known and stationary. Real channels (including LLM inference) may be unknown, time-varying, or adversarial.
- Ties to epistemology: capacity as a limit on "knowledge transmission" under uncertainty resonates with limits on induction, corroboration, and the web of belief. See Hume, Popper, Quine.

## Sources

- Primary: [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]] (sections on representation of noisy channels, equivocation and channel capacity, the fundamental theorem for discrete channel with noise, special cases, and continuous extensions).

## Related

- [[Thinkers/Claude Shannon]]
- [[Concepts/Entropy (Shannon)]], [[Concepts/Equivocation (Shannon)]], [[Concepts/Redundancy (Shannon)]], [[Concepts/Noiseless Channel Coding Theorem]], [[Concepts/Noisy Channel Coding Theorem]]
- [[Thinkers/Alan Turing]] (capacity and coding as the communication dual to computability and learning; together they underwrite modern digital systems and AI)
- Vault AI sources and concepts: [[Concepts/Context Engineering]], [[Concepts/Reasoning Scaffolds]], [[Concepts/Agentic Workflows]] (techniques to match "source" (user intent) to the "channel" (model) to approach reliable transmission), [[Sources/Daily Advanced AI Tips - 2026-06-02]] and follow-ups (model capabilities as channel characteristics; routing and scaffolding as capacity-approaching strategies)
- [[Thinkers/Garry Kasparov]] (chess search and evaluation as operating within information-theoretic bounds on branching and evaluation "noise")

*Concept page created 2026-06-04 during Shannon 1948 ingest. Central to the quantitative limit on reliable communication and the justification for error-correcting codes and statistical modeling in AI.*