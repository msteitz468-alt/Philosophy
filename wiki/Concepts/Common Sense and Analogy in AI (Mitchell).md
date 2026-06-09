---
title: "Common Sense and Analogy in AI (Mitchell)"
type: concept
domains: [ai, cognitive-science, philosophy-of-mind]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["Artificial Intelligence - Melanie Mitchell.txt"]
tags: [mitchell, common-sense, analogy, understanding, abstraction, deep-learning-limits, hofstadter, ai]
---

# Common Sense and Analogy in AI (Mitchell)

> Melanie Mitchell (2019) argues that human-like intelligence crucially depends on common sense (everyday knowledge of how the world works, enabling robust generalization) and analogy-making (recognizing abstract similarities across situations, the "core of cognition" per her and Hofstadter's research). Current AI (especially deep learning) excels at narrow statistical pattern matching but largely lacks these, leading to brittleness and "shallowness" even in impressive systems (e.g., translation, vision, game-playing). True progress toward general AI requires addressing these missing ingredients, not just scaling data and compute.

## Summary

From *Artificial Intelligence: A Guide for Thinking Humans*:

Mitchell, building on her work with Douglas Hofstadter, emphasizes that what makes humans intelligent is not just pattern recognition but the ability to form concepts, draw analogies ("this is like that"), and apply common-sense knowledge flexibly across novel situations.

Examples of current AI shortfalls:
- Winograd schemas (pronoun resolution requiring world knowledge/common sense, e.g., "The trophy doesn't fit in the suitcase because it's too big/small").
- Image captioning or visual QA that describes scenes without grasping meaning or physics.
- Machine translation that produces fluent but semantically off or culturally tone-deaf output (Hofstadter's "shallow" critique).
- Self-driving or robotics failures in edge cases outside training data ("long tail").
- Adversarial examples: imperceptible changes fool classifiers.

DL systems are powerful "approximators" but don't build the causal, abstract, analogical models humans use for understanding and robust action. Analogy (structure-mapping, conceptual blending) is central to creativity, learning from few examples, and transferring knowledge — areas where current AI struggles.

Mitchell notes that symbolic AI tried (and partially succeeded in narrow domains) to encode common sense explicitly (e.g., Cyc project), but scaling it is hard; connectionist approaches excel at perception but lack the "higher-level concepts."

Hybrid or new approaches will be needed for systems that truly "understand" in ways that interact safely and usefully with humans.

## Key Claims

- Common sense and analogy are not peripheral but foundational to intelligence and understanding.
- Current AI's successes are real but narrow and "brittle" precisely because they bypass these mechanisms via statistics on big data.
- Behavioral benchmarks (Turing test variants, ImageNet accuracy, game wins) can be passed without the underlying conceptual grasp.
- Overhyping risks repeating AI winters or harmful deployments (e.g., in medicine, law, autonomous systems) without acknowledging limits.

## Relation to Vault

- **Hofstadter (GEB)**: Mitchell was his student; her emphasis on analogy echoes GEB's core (isomorphism, tangled hierarchies, meaning from structure-mapping). The 2014 Google meeting and her book update GEB's speculations in light of DL progress (some brute-force wins) vs. persistent gaps in conceptual depth. Cross to Hofstadter thinker + GEB source + concepts (Formal Systems and Isomorphism, Strange Loops, Emergence).

- **Minsky (Society of Mind, Frames)**: Frames as structured knowledge with defaults/expectations are one way to capture common sense. Agent societies could in principle support analogical reasoning across sub-agents. Mitchell's history of perceptrons/Minsky-Papert critique and symbolic vs. subsymbolic debate. Cross to Minsky concepts (Frames, Society of Mind, Mental Agents).

- **Turing**: Turing test as insufficient measure (Mitchell chapter); current systems pass narrow versions without the "understanding" Turing's learning machines were meant to approach. Cross to Turing Imitation Game/Universal Machine/Learning Machines.

- **Bostrom**: Singularity/superintelligence scenarios assume rapid crossing to general/super human-like intelligence; Mitchell's limits (no common sense/analogy) suggest current paths may plateau or require fundamental new ideas, making timelines/risks more uncertain. Cross to Bostrom Orthogonality/Control/Superintelligence concepts.

- **Pearl (causality)**: DL stuck at rung 1 (association); common sense requires rung 2/3 (intervention, counterfactuals) — exactly the causal/analogical reasoning Mitchell says is missing. Cross to Pearl Ladder/Do-operator/Confounding.

- **Dennett**: Human understanding as distributed, narrative, embodied processes (drafts, Joycean machine); current AI lacks the richness. Cross to Dennett Multiple Drafts/Center of Narrative Gravity.

- **Recent AI sources (2026)**: Capabilities celebrated (agent chaining, structured reasoning) are still largely pattern-based; Mitchell warns they may not generalize robustly without common sense/analogy layers. Cross to Grok/Claude/Gemini tutorials, daily tips, agentic workflows.

- **Wiener**: "Know-what" (purposes, common sense about values/world) vs. pure "know-how" (capabilities). Cross to Wiener alignment.

Also to ethics (deploying systems without understanding risks) and strategy (AI as tool with real but bounded power).

## Contradictions / Open Questions

- > [!warning] Optimism in 2026 capability sources (scaling + scaffolding + multi-agent as path to generality) vs. Mitchell's view: without addressing common sense, analogy, and abstraction, systems remain narrow and brittle, however impressive on benchmarks. Risk of hype cycles or over-reliance.

- Symbolic (explicit common sense encoding, e.g., Cyc) vs. subsymbolic (DL emergence): Mitchell sees value in both; pure emergence may not suffice for robust understanding.

- "Different kind of understanding": Some argue AI doesn't need human-like common sense/analogy. Mitchell counters that for safe, useful interaction with humans/world, it does (or equivalent robustness).

- How to instill it: Hybrid architectures? Better world models/causal learning (Pearl link)? Embodied/analogical training? Still open research.

## Sources

- Primary: [[Sources/Artificial Intelligence - Melanie Mitchell (2019)]]

## Related

- [[Thinkers/Melanie Mitchell]]
- [[Thinkers/Douglas Hofstadter]], [[Sources/Gödel, Escher, Bach - Douglas Hofstadter (1979)]]
- [[Thinkers/Marvin Minsky]], [[Sources/The Society of Mind - Marvin Minsky (1986)]], [[Concepts/Frames (Minsky)]], [[Concepts/Society of Mind (Minsky)]]
- [[Thinkers/Alan Turing]], [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]]
- [[Thinkers/Nick Bostrom]], [[Sources/Superintelligence - Nick Bostrom (2014)]]
- [[Thinkers/Judea Pearl]], [[Sources/The Book of Why - Judea Pearl (2018)]], [[Concepts/Ladder of Causation (Pearl)]]
- [[Thinkers/Daniel Dennett]]
- 2026 AI sources (Grok 4.3 Tutorial, Claude/Gemini, daily tips, agentic workflows) — hype vs. limits
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]

*Concept page created 2026-06-04. Mitchell's emphasis on the missing foundations of robust intelligence in current AI.*
