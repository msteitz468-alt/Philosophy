---
title: "Learning Machines (Turing)"
type: concept
schools: [Computationalism]
domains: [epistemology, philosophy-of-mind, computation, ai]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [turing, learning-machines, child-machine, education, evolution-analogy, random-element, programming, 1950]
sources: ["Computing Machinery and Intelligence - Alan Turing.txt"]
---

# Learning Machines (Turing)

> Turing's proposed positive research programme for achieving machine intelligence: rather than attempting to programme an adult human mind directly, construct "child machines" with minimal built-in mechanism ("rather little mechanism, and lots of blank sheets") and subject them to an appropriate education. The process is explicitly analogized to evolution (heredity = structure of the child machine; mutation = changes; natural selection = experimenter judgment). Includes random elements for search, punishments/rewards (with "unemotional" symbolic channels being far more efficient), and the encoding of imperatives inside logical systems. The 1950 paper presents this as the practical route to the imitation game.

## Why Child Machines Rather Than Adult Simulation?

Turing notes three components that have brought the adult human mind to its state:
(a) initial state at birth,
(b) education,
(c) other experience.

"Instead of trying to produce a programme to simulate the adult mind, why not rather try to produce one which simulates the child's?" The child brain is "something like a notebook as one buys it from the stationer's." If there is so little mechanism in the child brain, something like it can be easily programmed. The amount of work in the education can be assumed, as first approximation, roughly the same as for a human child.

The two parts (child programme + education process) "remain very closely connected."

## Evolution Analogy

- Structure of the child machine = hereditary material
- Changes of the child machine = mutation
- Natural selection = judgment of the experimenter

One may hope the process will be "more expeditious than evolution." The experimenter can trace causes of weakness and introduce targeted (non-random) improvements, and is not restricted to random mutations. Survival of the fittest is slow; experimenter judgment speeds it.

## Teaching Mechanisms

- Simple child machines can be constructed or programmed on a punishments-and-rewards principle. Events shortly preceding a punishment signal become less likely to be repeated; reward signals increase probability.
- These definitions "do not presuppose any feelings on the part of the machine."
- Turing reports having done some experiments with one such child machine and taught it "a few things," but the method was "too unorthodox for the experiment to be considered really successful."
- "Unemotional" channels of communication (e.g., symbolic language) are crucial. If the teacher has no other means, the information that can reach the pupil does not exceed the total number of rewards and punishments. Symbolic orders transmitted through unemotional channels "will diminish greatly the number of punishments and rewards required."

## Imperatives and Logical Systems

Opinions vary on suitable complexity for the child machine. One might try minimal consistent with general principles, or build in a complete system of logical inference. In the latter case the store is largely occupied with definitions and propositions of various status (well-established facts, conjectures, proved theorems, statements from authority, logical forms without belief-value).

Certain propositions may be described as "imperatives." The machine should be so constructed that as soon as an imperative is classed as "well established" the appropriate action automatically takes place.

Example: teacher says "Do your homework now."
- This may cause "Teacher says 'Do your homework now'" to become a well-established fact.
- Another fact: "Everything that teacher says is true."
- Combining yields the imperative "Do your homework now" as well-established, which by machine construction causes homework to start.

The processes of inference "need not be such as would satisfy the most exacting logicians. There might for instance be no hierarchy of types." Suitable imperatives (e.g., "Do not use a class unless it is a subclass of one which has been mentioned by teacher") can prevent type fallacies without full type theory. "We are not bound to fall over unfenced cliffs."

Imperatives for a machine without limbs will be "of a rather intellectual character."

## Random Element

"It is probably wise to include a random element in a learning machine." A random element is useful when searching for a solution (example: finding a number between 50 and 200 equal to the square of the sum of its digits — systematic vs. random trial). The random method is often better because one does not have to keep track of values already tried, and there may be several satisfactory solutions. Evolution itself uses the random (systematic enumeration of genetical combinations is impossible).

## "Subcritical" and "Supercritical" Minds

Return to Lady Lovelace: an idea presented to a mind may "on average give rise to less than one idea in reply" (subcritical) or may generate a whole theory (supercritical). Most human minds are subcritical; some are supercritical. Animals are "very definitely subcritical." Question: "Can a machine be made to be supercritical?"

The skin-of-an-onion analogy: operations we can explain mechanically are called "not the real mind"; stripping leaves further skins. In the end the whole mind may be mechanical (though not necessarily discrete-state).

These are "recitations tending to produce belief" rather than fully convincing arguments. The real test will be running the experiment at the end of the century.

## Relation to Other Vault Content

- The direct ancestor of all modern "train on data + fine-tune + RLHF + iterative improvement" paradigms. The child-machine + education framing is echoed in curriculum learning, foundation models, agent scaffolding, and the vault's own incremental ingest process.
- Random element prefigures stochastic sampling, temperature, and evolutionary strategies in AI.
- Imperatives inside the system parallel tool-use policies, constitutional AI, and schema-enforced behavior in this vault (SCHEMA.md functions as a high-level imperative set that the agent is constructed to treat as well-established).

## Vault Meta / AI

The vault maintenance process is itself an instance of Turing learning-machine education:
- Initial "child" state = SCHEMA + seed index + a few pages (minimal mechanism + blank sheets).
- "Education" = successive ingests (experience), targeted edits, cross-linking, lint passes (self-critique), and experimenter (human + agent) judgment selecting what is retained and expanded.
- Random/exploratory elements = following interesting leads, best-of-n experiments, subagent exploration.
- "Unemotional channels" = the structured markdown + frontmatter + wikilinks that transmit instructions efficiently without requiring emotional valence on every edit.
- The goal is a "supercritical" knowledge structure that generates further ideas, connections, and pages with minimal external prompting.

## Related

- [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]], [[Thinkers/Alan Turing]]
- [[Concepts/Imitation Game (Turing)]], [[Concepts/Universal Machine (Turing)]], [[Concepts/Lady Lovelace's Objection]]
- [[Thinkers/Garry Kasparov]] (deliberate practice and iterative improvement as the human side of the learning-machine story)
- Modern vault AI sources (Grok/Claude/Gemini tutorials and tips describe exactly the "programming + education" of contemporary child machines)

*Concept page created 2026-06-04 during ingest of Turing 1950 (cluster indexing + cross-links completed 2026-06-04). The practical programme — child machines + education + evolution-like iteration — that Turing offered as the route to machine intelligence.*

---

*We may hope that machines will eventually compete with men in all purely intellectual fields.* (Turing, §7)
