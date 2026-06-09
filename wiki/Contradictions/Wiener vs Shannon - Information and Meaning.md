---
title: "Wiener vs Shannon — Information and Meaning"
type: contradiction
domains: [information-theory, cybernetics, philosophy-of-mind, ethics, philosophy-of-language]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["The Human Use of Human Beings - Norbert Wiener.txt", "A Mathematical Theory of Communication - Claude Shannon.txt"]
tags: [wiener, shannon, information, semantics, entropy, commodity, meaning, cybernetics, information-theory]
---

# Wiener vs Shannon — Information and Meaning

> Two founders of modern information theory — Norbert Wiener and Claude Shannon — share the same entropy mathematics (H = −∑ p log p) but reach opposite philosophical conclusions about what information *is* and whether its meaning matters. Shannon explicitly brackets semantics: "the semantic aspects of communication are irrelevant to the engineering problem." Wiener insists information is fundamentally social and semantic: society is understandable only through its messages and their meanings. A secondary clash: Shannon models information as a commodity-like resource (channel capacity, bits per second, transmission efficiency); Wiener argues information is categorically *not* a commodity — it decays, cannot be stored, and cannot be owned.

## The Positions

### Shannon: Semantics Bracketed, Information as Engineering Resource

In *A Mathematical Theory of Communication* (1948), Shannon is explicit:

"**The semantic aspects of communication are irrelevant to the engineering problem.** The significant aspect is that the actual message is one selected from a set of possible messages. The system must be designed to operate for each possible selection, not just the one which will actually be chosen since this is unknown at the time of design."

For Shannon:
- Information = reduction of uncertainty (one selection from a set of equally likely alternatives)
- H = −∑ p_i log_2 p_i in bits: the measure of uncertainty before the message is received
- The *meaning* of the message is irrelevant to this measure: a message saying "the cat sat on the mat" and one saying "the sun is a hot plasma sphere" have the same information content if they are equally probable selections
- Communication = reliable transmission of a message from source to destination over a noisy channel; success = the destination receives exactly what the source sent
- Semantics/meaning is a separate problem for psychologists and philosophers, not engineers
- Information is treated implicitly as a resource: measured in bits, transmissible at rates up to channel capacity C, storable in memory, compressible

Shannon's framework produces six operational concepts: entropy, channel capacity, equivocation (noise-induced uncertainty), redundancy (statistical structure of natural language), and the two coding theorems (noiseless: transmit at C/H; noisy: reliable transmission at H ≤ C with coding).

### Wiener: Information is Social, Semantic, and Anti-Commodity

In *The Human Use of Human Beings* (1950), Wiener claims the opposite:

"**Society can only be understood through a study of the messages and the communication facilities which belong to it.**"

For Wiener:
- Information is not a neutral engineering quantity — it is the substance of which social reality is made
- Information has thermodynamic meaning: it is anti-entropy, the measure of local order in a universe trending toward maximum disorder
- The *semantic and behavioral* dimensions of messages — their meaning for recipients, their effects on action — are precisely what matters for understanding society
- Information is **not conserved**: it decays, is anti-additive (like entropy, unlike gold), and cannot be owned or stored without depreciation
- Treating information as a commodity — as American patent law and secrecy classification do — is a category error
- "Information is more a matter of process than of storage"

## The Philosophical Divergence

| Issue | Shannon | Wiener |
|---|---|---|
| Role of semantics | Irrelevant to engineering | Central to social understanding |
| What is information? | Statistical uncertainty reduction (pure engineering) | Anti-entropy; the substance of social reality |
| Is information a commodity? | Implicitly yes (bits as resource, measurable, transmissible) | Explicitly no — decays, anti-additive, cannot be owned |
| What is the communication system for? | Reliable reproduction of signals at destination | Creating social meaning and coordination |
| Foundation of the framework | Engineering pragmatism | Thermodynamic and social philosophy |
| Does the formula have metaphysical significance? | No — it is a useful mathematical tool | Yes — it reflects the universe's thermodynamic structure |

## The Shared Mathematics

What makes this contradiction philosophically interesting is that **both men use the same formula** and know it:

Wiener independently derived H = −∑ p log p from thermodynamic considerations (related to Boltzmann entropy) around the same time Shannon derived it from communication theory. When they compared notes, both recognized the identity. Shannon acknowledged the connection in his 1948 paper; Wiener acknowledged it in *Cybernetics* (1948).

Yet they draw opposite philosophical conclusions:
- Shannon: the mathematical identity with Boltzmann entropy is a convenient formal coincidence. It helps mathematically but doesn't mean "information" and "physical entropy" are the same thing. The semantics of "information" is for someone else to worry about.
- Wiener: the mathematical identity is *not* a coincidence. Information *is* a thermodynamic phenomenon — the measure of local anti-entropy. The mathematical connection to Boltzmann entropy reflects a real physical/metaphysical connection. Therefore information has the same "not-a-commodity" structure as thermodynamic entropy.

## The Information-as-Commodity Debate

Shannon's framework enables treating information as a commodity in specific technical senses:
- Information can be *measured* (in bits)
- It can be *transmitted* at rates up to C
- It can be *stored* (memory capacity in bits)
- It can be *compressed* (removing redundancy)
- It can be *protected* against noise (error-correcting codes add redundancy)

This instrumental treatment has been enormously successful — it is the foundation of all digital communication, data storage, and error correction.

Wiener's anti-commodity argument:
- The *meaning* of information degrades as context changes — yesterday's intelligence is today's history
- *Scientific* information becomes worthless unless it is being actively developed: "There is no Maginot Line of the brain"
- Information "owned" by one party (secret) loses value to the owner faster than it threatens competitors
- Patent law on scientific discoveries reflects the error of treating ideas as ownable commodities — once an idea is demonstrably achievable, others will re-derive it

Wiener's argument is about a *different* dimension of information — its social/temporal/semantic value — not about the Shannon bits-per-second measure. This suggests the contradiction is partly a matter of different levels of analysis.

## What Each Gets Right

**Shannon gets right**: the purely engineering dimension. For designing reliable communication systems — telephone networks, data storage, error-correcting codes, compression algorithms, neural network training (cross-entropy loss) — Shannon's framework is indispensable. The bracketing of semantics is exactly the right move to make the engineering tractable.

**Wiener gets right**: the social and political dimension. Information classified as state secrets does depreciate. Scientific knowledge that is not actively maintained and developed does lose relevance. Patent law does increasingly fail to correspond to how scientific invention works. The American obsession with "know-how" as ownable commodity does distort science policy. These are important truths about how information behaves in society over time.

## The Synthesis (Not Achieved by Either)

Neither thinker achieves a synthesis. Shannon's framework is silent about the social role of meaning; Wiener's framework is philosophically rich but technically informal. The vault holds them in tension.

One candidate synthesis: Shannon's H measures *potential* information (how much uncertainty could in principle be resolved by a message). Wiener's anti-commodity argument applies to *realized* information (the actual value of a message in a given social context over time). These are genuinely different dimensions; both are real; neither reduces to the other.

The modern AI field mostly uses Shannon's framework (cross-entropy training, information bottleneck theory, compression as intelligence), but increasingly confronts Wiener's questions: What does a language model "know"? What do its outputs *mean*? How does knowledge depreciate as the world changes (training data cutoff)?

## Relation to the Broader AI Leg

This contradiction is less sharp than [[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]] because Shannon and Wiener are not directly arguing with each other — they worked in parallel and were broadly allies. But the philosophical divergence is real and consequential for the vault's AI leg:

- The Hofstadter/Searle debate turns on whether syntax produces semantics.
- The Wiener/Shannon tension turns on whether semantics is *relevant to information at all*.
- Wiener's answer (yes, absolutely) puts him closer to Searle's concern about meaning than Shannon's engineering pragmatism does — even though Wiener would not endorse Searle's biological naturalism.

## Sources

- [[Sources/The Human Use of Human Beings - Norbert Wiener (1950)]]
- [[Sources/A Mathematical Theory of Communication - Claude Shannon (1948)]]

## Related

- [[Thinkers/Norbert Wiener]], [[Thinkers/Claude Shannon]]
- [[Concepts/Cybernetics (Wiener)]], [[Concepts/Entropy and Information (Wiener)]]
- [[Concepts/Entropy (Shannon)]], [[Concepts/Channel Capacity (Shannon)]]
- [[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]] (the vault's other major AI contradiction; syntax/semantics gap vs. information/meaning gap)
- [[Thinkers/John Searle]] (Searle's syntax/semantics distinction is related: Shannon's system has only syntax; Wiener insists information has semantics)

*Contradiction page created 2026-06-04 during Wiener 1950 ingest. The vault's information-theory tension: Shannon brackets semantics for engineering tractability; Wiener insists information is fundamentally social and meaningful — and cannot be treated as a commodity.*
