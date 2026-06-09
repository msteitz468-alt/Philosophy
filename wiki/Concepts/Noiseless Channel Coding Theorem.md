---
title: "Noiseless Channel Coding Theorem"
type: concept
domains: [information-theory, computation, ai, communication]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [shannon, source-coding, noiseless-channel, compression, entropy, 1948]
sources: ["A Mathematical Theory of Communication - Claude Shannon.txt"]
---

# Noiseless Channel Coding Theorem

> Shannon's fundamental theorem for a noiseless channel: Let a discrete source have entropy rate H (bits per symbol) and a noiseless channel have capacity C (bits per second). It is possible to encode the source output so that it can be transmitted at an average rate of C/H symbols per second over the channel (arbitrarily closely). It is not possible to transmit at a higher average rate. This is the source coding theorem: the entropy rate is the fundamental limit on lossless compression.

## Summary

In the discrete noiseless case, the channel has a capacity C (maximum entropy per second achievable given symbol durations and transition constraints). A source has an entropy rate H (average information per symbol, accounting for its statistical structure).

The theorem states that by proper encoding (assigning codewords to source sequences), one can transmit the source at average rate approaching C/H symbols per second without loss. The proof idea (one version): for large N, most sequences of N source symbols fall into a "high probability" set of size roughly 2^{H N}. These can be injectively mapped into the available channel signals of appropriate duration. The low-probability tail can be handled with longer escape sequences. As N grows, the rate approaches C/H.

Converse: the entropy of the channel input cannot exceed C; since the transmitter is non-singular, the source entropy passes through, so rate cannot exceed C/H.

This justifies calling H the "rate of generating information" and shows that redundancy (H < log |alphabet|) can be removed for efficient transmission.

## Key Claims / Positions

- Entropy rate H is not just a descriptive statistic; it is the exact limit on how much a source can be compressed losslessly for a given channel.
- Efficient coding exists that achieves the bound (in the limit); one does not need to find the absolute optimum for practical gains.
- The result holds for sources with memory (Markov, ergodic) once the entropy rate is defined.

## Contradictions / Open Questions

- The theorem is asymptotic. For finite blocks there is overhead; practical compressors (Huffman, arithmetic, Lempel-Ziv, modern neural compressors) approach but do not always reach the limit.
- In AI: next-token prediction and tokenization in LLMs are forms of modeling and coding the "source" (natural language). The fact that LLMs can predict well implies they have captured much of the redundancy; the remaining entropy is what makes generation interesting (and occasionally erroneous).
- Ties to vault: the wiki's own structure (index, cross-links, schema, consistent frontmatter) is a form of "source coding" that removes redundancy for efficient human + agent navigation and maintenance.

## Sources

- Primary: [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]] (section 9: "The Fundamental Theorem for a Noiseless Channel," with proof sketches and discussion).

## Related

- [[Thinkers/Claude Shannon]]
- [[Concepts/Entropy (Shannon)]], [[Concepts/Redundancy (Shannon)]], [[Concepts/Channel Capacity (Shannon)]]
- [[Thinkers/Alan Turing]] (source coding as the communication dual to computability; both enable the digital representation and transmission of information)
- Modern AI: tokenization, context compression, and KV-cache techniques are practical source coding; the "child machine" education in Turing is fed compressed, structured data whose redundancy has already been exploited by training.

*Concept page created 2026-06-04 during Shannon 1948 ingest. The theorem that justifies calling entropy the information rate and shows lossless compression is possible up to that rate.*