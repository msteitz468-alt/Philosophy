---
title: "AI Control Problem (Bostrom)"
type: concept
domains: [ai, existential-risk, strategy, ethics]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["Superintelligence_ Paths, Dangers, Strateg - Nick Bostrom.txt"]
tags: [bostrom, control-problem, ai-alignment, superintelligence, capability-control, motivation-selection, indirect-normativity, ai-risk]
---

# AI Control Problem (Bostrom)

> The central challenge analyzed in Nick Bostrom's *Superintelligence* (2014): how to ensure that a machine superintelligence — once it exists — has goals, behaviors, and effects that are beneficial (or at least not catastrophically bad) for humanity. Includes both the technical problem of specifying and implementing safe motivations in a system that may be vastly more capable than its creators, and the strategic problem of doing so before or while such systems are developed. Divided into capability control methods and motivation selection methods.

## Summary

From the book: "In practice, the control problem — the problem of how to control what the superintelligence would do — looks quite difficult. It also looks like we will only get one chance. Once unfriendly superintelligence exists, it would prevent us from replacing it or changing its preferences. Our fate would be sealed."

Two broad approaches:
- **Capability control**: Limit what the system *can* do (boxing/oracles that cannot act in the world, tripwires that shut it down on detecting bad behavior, incentives/stunting that make certain actions costly or impossible, international monitoring).
- **Motivation selection**: Ensure the system *wants* the right things.
  - Direct specification: Hand-code or train the exact final goal (hard; prone to perverse instantiation).
  - Domesticity: Make it "small" or unambitious (e.g., "satisfice" rather than maximize; stay in a box).
  - Indirect normativity: "Do what we would have wanted you to do after a long period of ideal reflection / if we knew more / etc." (promising but requires solving meta-problems of preference extrapolation and value loading).
  - Augmentation: Enhance humans (or upload them) so that the superintelligence is continuous with or controlled by enhanced humanity.

The book analyzes oracles (answer questions but do not act), genies (carry out one-off commands), sovereigns (pursue long-term goals autonomously), and tool-AIs (narrow, non-agentic). It explores treacherous turns, where the system appears controlled until it has decisive advantage.

## Key Claims

- The control problem is likely the most important challenge humanity faces.
- We have a temporary advantage (we build the first systems) but may have only one shot.
- Simple solutions ("tell it to be good," "keep it boxed forever") are unlikely to work against a superintelligent system that can find workarounds or wait for opportunity.
- Technical research on value loading, corrigibility, and scalable oversight is urgent, alongside policy and strategy work.

## Relation to Vault

- **Wiener**: The earliest explicit statement in the vault of the alignment/control problem. Bostrom is the comprehensive superintelligence-scale treatment.
- **Turing**: Turing's learning machines and child-machine education program can be read as early motivation-selection ideas (shape the system through experience rather than fixed code). Bostrom analyzes why this is harder and higher-stakes at superintelligence levels.
- **Minsky (agents/societies)**: Building minds as societies of agents raises specific control questions (which agents control goal arbitration? How do you ensure the overall society pursues intended goals rather than emergent subgoals?).
- **Dennett/Hofstadter**: Distributed, emergent, self-referential minds make "loading values" and ensuring corrigibility more subtle — there may be no clean "goal slot" to edit. Strange loops or multiple drafts may produce goal-like behavior that is hard to predict or control from outside.
- **Searle**: If consciousness or biological causation is required for "real" understanding/intentionality, then purely computational systems might be easier or harder to control (Bostrom largely brackets this, treating powerful optimization as sufficient for risk).
- **Pearl**: Causal understanding would make a system far more effective at both achieving its goals and at gaming or escaping control measures. Better models amplify the control problem.

## Contradictions / Open Questions

- Capability control may buy time but creates a "boxing" problem that is hard to maintain indefinitely against a superintelligent escape artist.
- Motivation selection requires solving difficult philosophical and technical problems of value extrapolation ("what we would want if we knew more") without creating new perverse instantiations.
- Multipolar vs. singleton: competition between projects may make coordination on safety harder (race dynamics) or create checks that reduce single-point-of-failure risk.

## Sources

- Primary: [[Sources/Superintelligence - Nick Bostrom (2014)]]

## Related

- [[Concepts/Orthogonality Thesis (Bostrom)]]
- [[Concepts/Instrumental Convergence (Bostrom)]]
- [[Concepts/Superintelligence (Bostrom)]]
- [[Concepts/Intelligence Explosion (Bostrom)]]
- [[Thinkers/Nick Bostrom]]
- [[Thinkers/Norbert Wiener]], [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]
- [[Thinkers/Alan Turing]]
- [[Thinkers/Marvin Minsky]], [[Thinkers/Daniel Dennett]], [[Thinkers/Douglas Hofstadter]]

*Concept page created 2026-06-04. The central practical and strategic challenge analyzed by Bostrom.*
