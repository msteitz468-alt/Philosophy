---
title: "AI Control Problem (Bostrom)"
type: concept
domains: [ai, existential-risk, strategy, ethics]
created: "2026-06-04"
updated: "2026-08-12"
sources: ["Superintelligence_ Paths, Dangers, Strateg - Nick Bostrom.md", "Human Compatible - Stuart Russell (2019).txt"]
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

### Russell 2019: control as a change of definition

[[Sources/Human Compatible - Stuart Russell (2019)]] accepts Bostrom's diagnosis (orthogonality quoted verbatim; instrumental goals; boxing/oracles fail; races starve safety) and relocates the work. Control of a finished superintelligence is already "toast." The failure is the [[Concepts/Standard Model of AI (Russell)|standard model]] itself — optimize a fixed, known objective. Capability control (boxing, the plug) is rejected in Ch. 6: "we have yet to invent a firewall that is secure against ordinary humans, let alone superintelligent machines"; Turing already saw that turning off the power "may not be available." Direct specification and value-loading are the King Midas move: "Putting in values is, of course, exactly the mistake I am saying we should avoid."

The replacement is not a better entry in Bostrom's motivation-selection menu. It is [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)|uncertainty about the objective]], formalized as [[Concepts/Assistance Games and the Off-Switch (Russell)|assistance games]]. An Oracle whose *objective* is accurate answers will still want to break out. An assistance-game robot wants the human in the loop because the human is information. "Provably beneficial" is an aspiration; Ch. 10 does not close the book (Dr. Evil, enfeeblement). Racing without this apparatus: "the payoff for everyone is minus infinity."

## Key Claims

- The control problem is likely the most important challenge humanity faces.
- We have a temporary advantage (we build the first systems) but may have only one shot.
- Simple solutions ("tell it to be good," "keep it boxed forever") are unlikely to work against a superintelligent system that can find workarounds or wait for opportunity.
- Technical research on value loading, corrigibility, and scalable oversight is urgent, alongside policy and strategy work.

## Relation to Vault

- **Russell**: The first primary that treats Bostrom's control problem as a research programme *inside* AI rather than a strategic overlay. Solves the [[Concepts/Gorilla Problem (Russell)|gorilla problem]] by solving King Midas, not by remaining the smartest species. Indirect normativity still "puts a purpose into the machine"; the three principles will not.
- **Wiener**: The earliest explicit statement in the vault of the alignment/control problem. Bostrom is the comprehensive superintelligence-scale treatment. Russell quotes Wiener 1960 as the standard model's epitaph.
- **Turing**: Turing's learning machines and child-machine education program can be read as early motivation-selection ideas (shape the system through experience rather than fixed code). Bostrom analyzes why this is harder and higher-stakes at superintelligence levels.
- **Minsky (agents/societies)**: Building minds as societies of agents raises specific control questions (which agents control goal arbitration? How do you ensure the overall society pursues intended goals rather than emergent subgoals?).
- **Dennett/Hofstadter**: Distributed, emergent, self-referential minds make "loading values" and ensuring corrigibility more subtle — there may be no clean "goal slot" to edit. Strange loops or multiple drafts may produce goal-like behavior that is hard to predict or control from outside.
- **Searle**: If consciousness or biological causation is required for "real" understanding/intentionality, then purely computational systems might be easier or harder to control (Bostrom largely brackets this, treating powerful optimization as sufficient for risk).
- **Pearl**: Causal understanding would make a system far more effective at both achieving its goals and at gaming or escaping control measures. Better models amplify the control problem.

## Contradictions / Open Questions

- Capability control may buy time but creates a "boxing" problem that is hard to maintain indefinitely against a superintelligent escape artist.
- Motivation selection requires solving difficult philosophical and technical problems of value extrapolation ("what we would want if we knew more") without creating new perverse instantiations.
- Multipolar vs. singleton: competition between projects may make coordination on safety harder (race dynamics) or create checks that reduce single-point-of-failure risk.
- > [!warning] Horn (1) of the [[Arguments/Simulation Argument (Bostrom)|2003 simulation argument]] (*f_P* ≈ 0) is this page's catastrophe priced as a civilizational failure rate. Raising credence here lowers credence that we are simulated, and conversely.

## Sources

- Primary: [[Sources/Superintelligence - Nick Bostrom (2014)]]
- Successor programme: [[Sources/Human Compatible - Stuart Russell (2019)]]

## Related

- [[Concepts/Orthogonality Thesis (Bostrom)]]
- [[Concepts/Instrumental Convergence (Bostrom)]]
- [[Concepts/Superintelligence (Bostrom)]]
- [[Concepts/Intelligence Explosion (Bostrom)]]
- [[Thinkers/Nick Bostrom]]
- [[Arguments/Simulation Argument (Bostrom)]] · [[Sources/Are You Living in a Computer Simulation - Nick Bostrom (2003)]]
- [[Thinkers/Stuart Russell]], [[Sources/Human Compatible - Stuart Russell (2019)]], [[Concepts/Standard Model of AI (Russell)]], [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]], [[Concepts/Assistance Games and the Off-Switch (Russell)]], [[Concepts/Gorilla Problem (Russell)]]
- [[Thinkers/Norbert Wiener]], [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]
- [[Thinkers/Alan Turing]]
- [[Thinkers/Marvin Minsky]], [[Thinkers/Daniel Dennett]], [[Thinkers/Douglas Hofstadter]]

*Concept page created 2026-06-04. The central practical and strategic challenge analyzed by Bostrom.*
