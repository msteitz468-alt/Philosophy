---
title: "Imitation Game (Turing)"
type: concept
schools: [Computationalism, Functionalism]
domains: [epistemology, philosophy-of-mind, computation, ai]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [turing, imitation-game, turing-test, can-machines-think, interrogator, behavioral-test, 1950]
sources: ["Computing Machinery and Intelligence - Alan Turing.txt"]
---

# Imitation Game (Turing)

> Turing's proposed replacement for the question "Can machines think?": an operational "imitation game" in which a machine takes the role of a man in a three-player text-only guessing game (man/woman/interrogator). Success is measured by whether an average interrogator is fooled at rates comparable to the original man/woman version. The game focuses attention on intellectual capacities while neutralizing physical appearance, voice, and other irrelevant cues. The 1950 formulation is the direct ancestor of what later became known as the "Turing Test."

## The Game (original formulation)

Three people: a man (A), a woman (B), and an interrogator (C) who may be of either sex. The interrogator is in a room apart. The object for C is to determine which of the other two is the man and which the woman, identified only as X and Y. C may ask questions of A and B (ideally via teleprinter or intermediary to remove tone of voice). A tries to cause C to make the wrong identification; B tries to help C.

Turing then asks: "What will happen when a machine takes the part of A in this game?" Will the interrogator decide wrongly as often when the game is played with the machine as when played between man and woman? These questions replace the original "Can machines think?"

## Advantages of the Criterion (per Turing)

- Draws a fairly sharp line between physical and intellectual capacities. No need for the machine to simulate skin, dress, or beauty-competition performance.
- The question-and-answer method can introduce almost any field of human endeavour without penalizing the machine for disabilities irrelevant to intellect (e.g., losing a footrace to an aeroplane).
- "Witnesses" can brag as much as they like about charms or heroism; the interrogator cannot demand practical demonstrations.
- Avoids the infinite regress of first defining "machine" and "think" by ordinary-language survey (Gallup poll), which Turing calls absurd.

Specimen questions and answers illustrate the range:
- "Please write me a sonnet on the subject of the Forth Bridge." → "Count me out on this one. I never could write poetry."
- Arithmetic with ~30-second pause.
- Chess position: "I have K at my K1... What do you play?" → (15s pause) "R-R8 mate."

## Relation to Later "Turing Test" Usage

The 1950 paper uses "imitation game" throughout; the shorthand "Turing Test" became standard later. Turing's version is explicitly comparative (machine vs. man in the man/woman game) and time-limited (five minutes in the famous prediction). It is behavioral/functional: the interrogator has no access to internal states, only to text outputs. Turing explicitly addresses (and largely sets aside) the consciousness objection that the machine must "feel" or "know that it had written it."

## Relation to Other Vault Content

- Directly grounds the entire modern discussion of machine intelligence and the boundary with human creativity. See [[Thinkers/Garry Kasparov]] (Deep Blue matches as real-world experiments in the imitation-game space; *Deep Thinking* on where machine intelligence ends and human creativity begins) and the recurring "human creativity vs machines" theme in [[Sources/MasterClass Collection - 2026]].
- Stands in productive tension with [[Thinkers/Descartes]] (requirement of a non-mechanical *res cogitans* that thinks and knows it thinks) and with [[Concepts/Identity and Diversity - Personal Identity (Locke)]] (Locke's consciousness criterion for personal identity tested here only via observable outputs).
- The vault's own AI sources (Grok/Claude/Gemini tutorials and tips) are practical descendants: modern systems are evaluated by sustained, open-ended "interrogation" (prompting, agentic workflows, tool use) in which the user/interrogator attempts to distinguish or assess capability.

## Vault Meta / AI

The imitation game supplies the vault's implicit evaluation standard for agentic systems and the wiki itself: can the system (Grok + tools + indexed knowledge) sustain interactions in which a skilled interrogator cannot reliably distinguish its performance from that of a knowledgeable, careful human researcher across the domains the vault covers? Context engineering, reasoning scaffolds, and the persistent SCHEMA + index function as the "instruction table" and "store" that make such performance possible. The game also justifies treating outputs as evidence even when inner "understanding" remains philosophically contested.

## Related

- [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]], [[Thinkers/Alan Turing]]
- [[Concepts/Universal Machine (Turing)]], [[Concepts/Learning Machines (Turing)]], [[Concepts/Argument from Consciousness (Jefferson)]], [[Concepts/Lady Lovelace's Objection]]
- [[Thinkers/Garry Kasparov]], [[Sources/MasterClass Collection - 2026]]
- [[Thinkers/Descartes]], [[Thinkers/Locke]]
- [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]] and daily AI tips (contemporary systems evaluated under sustained interrogation)

*Concept page created 2026-06-04 during ingest of Turing's 1950 paper (cluster indexing + cross-links completed 2026-06-04). The operational criterion that launched the study of machine intelligence.*

---

*Will the interrogator decide wrongly as often when the game is played like this as he does when the game is played between a man and a woman?* (Turing, §1)
