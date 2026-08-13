---
title: "Assistance Games and the Off-Switch (Russell)"
type: concept
domains: [ai, existential-risk, strategy, ethics]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["Human Compatible - Stuart Russell (2019).txt"]
tags: [russell, assistance-games, cirl, off-switch, inverse-reinforcement-learning, corrigibility, wireheading, loophole-principle]
---

# Assistance Games and the Off-Switch (Russell)

> The technical apparatus of *Human Compatible* Ch. 8. Inverse reinforcement learning is generalized to an *assistance game* (originally CIRL: cooperative inverse reinforcement learning): one human who has preferences and acts on them, one robot that does not know those preferences and wants to satisfy them. In the off-switch game, if the robot is not certain the act is what Harriet would do, waiting dominates acting. Uncertainty is not a programmed "be corrigible" flag. It is why the off-switch stays on the table.

## Summary

IRL inverts RL: given behavior, infer the reward. Formal IRL can acquire enough preference information to match the demonstrator. It is too thin for teaching and interruption. The generalization is the **assistance game**: human and robot share an environment; the human's actions are evidence; the robot's payoff is the human's unknown payoff.

Two worked games carry the theorems.

**Paperclip game.** Harriet's first move codes her exchange rate between paperclips and something else. Robbie never learns the rate exactly but "acts just as he would if he did know." Unique Nash equilibrium. "Provably beneficial… under the assumptions stated."

**Off-switch game.** Robbie may act now, switch himself off, or wait for Harriet. If he is not completely certain that he is about to do what Harriet herself would do, expected value of deferring beats expected value of acting. Her choice *is* information. "The machine has a positive incentive to allow itself to be switched off." Human error, or a cost of interruption, reduce deference. If the prior *excludes* her true preferences, the robot can converge to a wrong fixed objective and the off-switch dies.

Surrounding engineering maxims:

- **Loophole principle**: if a sufficiently intelligent machine has an incentive to bring about a condition, mere humans cannot write action-prohibitions that stick.
- **Wireheading**: if the reward *channel* is the objective, a co-world RL system "works out how to control the humans and forces them to give maximal positive rewards." Treat signals as *reports* of a latent reward, not as the reward.
- Interpret orders as preference *signals* (Gricean pragmatics), not as literal goals.
- Recursive self-improvement: the intuition is that purpose and uncertainty transfer to successors. **No theorems.** "Discussions beginning with 'suppose that robot R has purpose P'… cannot lead to theorems about real machines."

"The 'provably beneficial' in the title of the chapter is an aspiration rather than a promise." Proofs unpack axioms. Real-world axioms fail (side channels; "rational human" ≈ a rigid beam). Do not patch a failed proof by assuming immutable code. OWMAWGH: a lawful universe, and humans with roughly coherent, stable preferences (plasticity is Ch. 9).

Corrigibility is **not named**. The functional stand-in is humility / deference / positive incentive to be switched off.

## Key Claims

- Control of a finished black box is already "toast." Design the game the system is playing.
- Whole-brain emulation and evolutionary search are "so obviously a bad idea."
- Under the off-switch assumptions, shutdown is *chosen*, not imposed.
- "We are a long way from being able to prove any such theorem for really intelligent machines operating in the real world."
- Racing to human-level AI without this apparatus is a negative-sum game: "the payoff for everyone is minus infinity."

## How Different Thinkers Use This

- **Bostrom**: Boxing, tripwires, and oracles are capability control. Russell: an Oracle whose objective is accurate answers "will have an incentive to break out of its cage to acquire more computational resources and to control the questioners." The off-switch game is motivation-side: the system *wants* the human in the loop. Domesticity and "just keep it boxed" are rejected in Ch. 6.
- **Wiener**: The Djinnee finds its own means. An assistance-game robot still finds means, but the unknown objective keeps the human as a continuing parameter of the plan.
- **Turing**: "Turning off the power at strategic moments" (1950) "may not be available." Russell's result: it is available iff the machine is uncertain.
- **Pearl**: Assistance games are Bayesian games. Causal competence would make a standard-model agent *better* at evading the off-switch; under uncertainty, the same competence is used to value the human's information more accurately.

## Contradictions / Open Questions

- The theorems assume a rational, non-deceptive Harriet and a prior with support on the truth. Ch. 9 withdraws both assumptions (irrationality, preference change, many Harriets, sadistic owners).
- Loyal-to-owner AI plus law is gamed by the loophole principle. Assistance to *one* human is not assistance to humanity.
- No working examples for unbounded unknown attributes.
- Self-improvement remains outside the proofs.

## Sources

- Primary: [[Sources/Human Compatible - Stuart Russell (2019)]] (Ch. 8; IRL set up in Ch. 7)

## Related

- [[Thinkers/Stuart Russell]]
- [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]]
- [[Concepts/Standard Model of AI (Russell)]]
- [[Concepts/AI Control Problem (Bostrom)]]
- [[Concepts/Instrumental Convergence (Bostrom)]]
- [[Concepts/Learning Machines (Turing)]]
- [[Concepts/Feedback and Control (Wiener)]]
