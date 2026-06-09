---
title: "Discrete-State Machine (Turing)"
type: concept
schools: [Computationalism]
domains: [computation, epistemology, philosophy-of-mind, ai]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [turing, discrete-state-machine, state-transition, predictability, digital-computers, universal-machine, 1950]
sources: ["Computing Machinery and Intelligence - Alan Turing.txt"]
---

# Discrete-State Machine (Turing)

> Machines whose internal states are sufficiently distinct that they can be treated as jumping from one definite configuration to another; next state and output are functions of current state + input. Digital computers belong to this class and are universal within it: any other discrete-state machine (with adequate storage and speed) can be mimicked by programming a digital computer with the target machine's state-transition table.

## Definition and Properties (from Turing 1950 §5)

Turing introduces the class to make the notion of "machine" in the imitation game precise while showing it is not overly restrictive.

- Discrete-state machines "move by sudden jumps or clicks from one quite definite state to another."
- States are "sufficiently different for the possibility of confusion between them to be ignored."
- They can be fully described by tables: (1) internal state determined by previous state + input signal; (2) output signals likewise.
- Given the table, initial state, and sequence of inputs, "it is always possible to predict all future states."
- This is Laplace-like predictability but "far nearer to practicability" because small errors in initial conditions do not avalanche (unlike continuous physical systems).

Example: a wheel that clicks round through 120° once a second, stoppable by a lever; lamp lights in one position. Three states (q1, q2, q3); input (lever position); tabulated transitions and outputs.

Digital computers are discrete-state machines. The Manchester machine of Turing's day had ~10^50,000 possible states (storage capacity ~165,000 digits). Enormous but finite; "infinitive capacity" (unlimited store in theory) is imaginable.

## Contrast with Continuous Machines

The nervous system is not discrete-state: "a small error in the information about the size of a nervous impulse impinging on a neuron, may make a large difference to the size of the outgoing impulse."

Turing grants the point but argues it does not defeat the imitation game: under the game's conditions (text-only interrogation, no requirement to replicate physical embodiment), the interrogator cannot exploit the difference. A continuous machine (e.g., differential analyser) can still be made to give "the right sort of answer" by a discrete imitator choosing randomly among nearby values.

## Relation to Universality and the Imitation Game

Universality is stated for discrete-state machines: a digital computer with enough storage/speed, suitably programmed, can mimic any other member of the class. The imitation game therefore reduces to: can a digital computer (universal discrete-state machine) be programmed to play the part of the man (A) so well that the interrogator is fooled at rates comparable to the man/woman version?

Babbage's Analytical Engine already embodied the essential ideas (mechanical, never completed); electricity is theoretically inessential (nervous systems involve chemistry too; some computers used acoustic storage).

## Relation to Other Vault Content

- Grounds the computability side of the vault's emerging AI & Cognitive Science leg: every modern digital computer, virtual machine, interpreter, and LLM inference engine is a concrete realization of a universal discrete-state machine.
- Links directly to [[Concepts/Universal Machine (Turing)]] (the positive consequence) and [[Concepts/Imitation Game (Turing)]] (the test that can be passed by programming one).
- The predictability of discrete-state systems contrasts with the "informality of behaviour" objection (§8) Turing addresses later: even when we cannot easily recover the programme by observation, the machine remains in principle a discrete-state system.
- Prefigures later discussions of finite-state vs. more powerful models, though Turing's 1950 treatment already encompasses the full power of digital computers (equivalent to Turing machines from his 1936 work).

## Vault Meta / AI

The wiki itself can be viewed as operating over a (very large) discrete state space: each page + frontmatter + wikilink graph is a configuration; an ingest or edit is an input that deterministically (or with controlled randomness via tools/exploration) produces a new configuration. The SCHEMA + index function as the "table of instructions" and compressed memory of prior states. Agent actions (search, read, targeted replace, log append) are the executive/control steps that traverse and update the state according to rules.

## Related

- [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]], [[Thinkers/Alan Turing]]
- [[Concepts/Universal Machine (Turing)]], [[Concepts/Imitation Game (Turing)]], [[Concepts/Learning Machines (Turing)]]
- [[Concepts/Argument from Consciousness (Jefferson)]], [[Concepts/Lady Lovelace's Objection]] (other objections addressed in the same paper)
- Modern computing concepts realized in the vault's tools (Grok Build, agent orchestration, file/graph state as store)

*Concept page created 2026-06-04 during completion of the Turing 1950 ingest. The formal class that lets Turing show both the scope and the limits of what the imitation game requires of "machines."*

---

*It will seem that given the initial state of the machine and the input signals it is always possible to predict all future states.* (Turing, §5)