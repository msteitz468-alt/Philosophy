---
title: "A Mathematical Theory of Communication - Claude Shannon (1948)"
type: source-summary
domains: [computation, information-theory, ai, communication, epistemology]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, entropy, channel-capacity, information-theory, noisy-channel, redundancy, source-coding, 1948, bell-system-technical-journal, communication, ai-foundations]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# A Mathematical Theory of Communication - Claude Shannon (1948)

> C. E. Shannon's foundational 1948 paper that defines information in terms of uncertainty (entropy H = −∑ p log p in bits), models a general communication system (source → transmitter → noisy channel → receiver → destination), brackets semantic meaning as irrelevant to the engineering problem, introduces channel capacity C as the maximum reliable transmission rate, proves the noiseless and noisy channel coding theorems (reliable communication possible at rates up to C with proper coding), and analyzes language as a stochastic process with substantial redundancy (~50% for English).

**Full citation**: C. E. Shannon, “A Mathematical Theory of Communication,” *Bell System Technical Journal*, vol. 27, pp. 379–423, 623–656, July, October, 1948.

## Summary

Shannon opens by noting recent modulation techniques (PCM, PPM) that trade bandwidth for signal-to-noise ratio and the need for a general theory. He builds on Nyquist and Hartley but adds noise in the channel and the statistical structure (redundancy) of messages.

The fundamental problem of communication is reproducing at one point a message selected at another. Semantic aspects (meaning, correlation with physical entities) are irrelevant to the engineering problem. What matters is that the message is chosen from a set of possible messages; the system must work for every possible selection.

A communication system has five parts:
1. Information source (produces message or sequence; discrete, continuous, or mixed).
2. Transmitter (operates on message to produce suitable signal; e.g., encoding, sampling, modulation).
3. Channel (the medium; may add noise).
4. Receiver (inverse of transmitter; reconstructs message from signal).
5. Destination (intended recipient).

Information is measured logarithmically. Using base 2 gives units of *bits* (suggested by J. W. Tukey). A device with two stable states stores one bit. Reasons for log measure: practical (parameters like time/bandwidth/relays vary linearly with log of possibilities), intuitive (linear comparison), and mathematical convenience for limits.

**Discrete noiseless case**: Source modeled as discrete Markov process (states with transition probabilities; can be ergodic/stationary). Entropy H of a set of probabilities p_i is H = −∑ p_i log_2 p_i (K=1 for bits). Properties: H=0 only when certain; maximum log n when equiprobable; additive for successive choices (with weighting).

For a source, the entropy rate H' (bits per symbol or per second) measures average information produced. For English, successive approximations (zero-order random letters, first-order letter frequencies, digram/trigram structure, word frequencies, word transitions) illustrate increasing realism. Shannon estimates the redundancy of ordinary English (constraints up to ~8 letters) at roughly 50%: when writing, about half the letters are determined by language structure, half chosen freely. This enables compression and helps combat noise.

**Channel capacity**: For a discrete noiseless channel, capacity C is the maximum entropy per second achievable by choice of symbol probabilities (or transition probs in state diagram). Fundamental theorem for noiseless channel: a source with entropy H can be encoded to transmit at average rate C/H symbols per second (arbitrarily close) over a channel of capacity C; cannot exceed it.

**Noisy discrete channel**: Introduces equivocation H(x|y) — the uncertainty about the input given the output (due to noise). Mutual information / rate of transmission = H(x) − H(x|y). Channel capacity C = max [H(x) − H_y(x)] over input sources. The noisy channel coding theorem (fundamental theorem): if source entropy rate H ≤ C, there exists coding such that the source output can be transmitted with arbitrarily small frequency of errors (or equivocation). If H > C, any encoding will have equivocation at least H − C (approximately). Reliable communication is possible up to capacity with sufficient redundancy introduced in the proper (error-correcting) way; natural language redundancy already provides some noise resistance.

The paper also treats continuous cases (differential entropy for continuous distributions, with caveats that it is relative to coordinate system; entropy power; band-limited channels with white noise, yielding the famous C = W log(1 + P/N) form in limiting cases).

Applications noted: not only communication engineering but theory of computing machines, telephone exchanges, cryptography, and any field involving selection from possibilities or statistical structure.

## Key Claims / Positions

- Information is fundamentally about *choice* and *uncertainty* among possible messages, independent of semantics or "meaning."
- The logarithmic measure (bits) is the natural, convenient, and mathematically tractable unit.
- Sources have statistical structure (Markov/ergodic processes) that can be measured by entropy rate; English has ~50% redundancy from local constraints.
- A channel has a definite capacity C (maximum rate of information transfer in bits/sec) even when noisy.
- Noiseless coding theorem: messages can be encoded to transmit at rates approaching C/H without loss.
- Noisy coding theorem: with proper encoding, information can be sent at rates up to C with error probability (or equivocation) made arbitrarily small. Rates above C necessarily incur equivocation at least the excess.
- Redundancy is a resource: in sources it allows compression; in channels or coding it combats noise (as seen in natural language error correction via context).
- The discrete case foundations the continuous/mixed cases (e.g., PCM).

## Contradictions / Open Questions

- > [!warning] Shannon explicitly sets semantics/meaning aside as "irrelevant to the engineering problem." This brackets precisely the questions of reference, intentionality, and understanding central to philosophy of mind and the vault's Turing/Descartes/Locke/Augustine threads. Ties directly to Turing's behavioral criterion and later debates (e.g., Chinese Room, "stochastic parrots"): does successful transmission of information (low equivocation) entail or require semantic grasp at source or destination? See [[Thinkers/Alan Turing]], [[Concepts/Argument from Consciousness (Jefferson)]], and modern AI sources on whether LLMs "understand" or merely manipulate symbols.
- The 50% redundancy figure for English is an approximation ignoring long-range structure; actual entropy rate estimates have varied with better models (modern LLMs achieve far better prediction, effectively lower estimated H).
- Differential entropy in continuous case is not absolute (changes with coordinate transformation); requires care in interpretation (entropy power, etc.). Contrasts with absolute discrete entropy.
- The theory is engineering-focused; philosophical questions of whether "information" captures all aspects of communication or knowledge remain open (links to epistemology: Hume on induction/custom as "great guide," Popper on information content vs. probability, Quine web of belief).

## Sources

- Primary: `raw/A Mathematical Theory of Communication - Claude Shannon.txt` (full 1948 BSTJ paper, including discrete noiseless/noisy cases, entropy definitions and properties, fundamental theorems, English language examples, and continuous extensions).

## Related

- [[Thinkers/Claude Shannon]] (new entity page)
- [[Concepts/Entropy (Shannon)]], [[Concepts/Channel Capacity (Shannon)]], [[Concepts/Redundancy (Shannon)]], [[Concepts/Equivocation (Shannon)]], [[Concepts/Noiseless Channel Coding Theorem]], [[Concepts/Noisy Channel Coding Theorem]]
- [[Thinkers/Alan Turing]] (complements computation/universal machines with communication theory, capacity, and coding; both 1948–1950 papers foundational to digital computing, AI, and cognitive science; learning machines + information transmission)
- Modern vault AI sources ([[Sources/Daily Advanced AI Tips - 2026-06-02]], [[Sources/Daily Advanced AI Tips - 2026-06-03]], [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]], [[Sources/Claude AI Advanced User Guide - 2026]]) (next-token prediction as entropy minimization; context engineering as supplying statistical priors to reduce uncertainty; agentic workflows as reliable transmission of intent through noisy LLM "channels"; cross-model routing as adapting to channel characteristics)
- [[Concepts/Reasoning Scaffolds]] and [[Concepts/Context Engineering]] (scaffolds and curated context as ways to lower effective entropy/uncertainty for the "receiver" model)
- [[Thinkers/Garry Kasparov]] (chess as a discrete information game with perfect information, branching factor, and search under uncertainty; Deep Blue as engineering realization using Shannon-style information measures and search)
- Epistemology cluster (Hume on custom/habit as guide under uncertainty; Popper on content and corroboration; probability and induction threads) — Shannon provides a precise quantitative measure of uncertainty and information gain.

*Source-summary created 2026-06-04 during ingest of the Shannon 1948 primary text (source-summary + thinker + ~6 concepts; targeted index and log updates). This paper is the canonical origin point for information theory and, paired with the vault's Turing source, supplies the communication + computation foundations for the AI & Cognitive Science leg. Cross-references established to Turing (info + computability), contemporary AI usage (prediction, context, reliable generation), and language redundancy as natural error correction.*

---

*"The fundamental problem of communication is that of reproducing at one point either exactly or approximately a message selected at another point."* (C. E. Shannon, opening of the paper)