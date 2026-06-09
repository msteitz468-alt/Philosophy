---
title: "Feedback and Control (Wiener)"
type: concept
domains: [cybernetics, ai, information-theory, philosophy-of-mind, biology, engineering]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [wiener, feedback, control, negative-feedback, homeostasis, servomechanism, intention-tremor, parkinsonism, learning]
sources: ["The Human Use of Human Beings - Norbert Wiener.txt"]
---

# Feedback and Control (Wiener)

> The central technical mechanism of cybernetics: output of a process is fed back as input to regulate the next cycle, allowing the system to correct its own behavior toward a goal. Wiener establishes that negative feedback is the universal anti-entropic mechanism in mechanical systems (Watt governor, ship steering engine, anti-aircraft predictor) and biological systems (homeostasis, nervous system, voluntary motion). Feedback is not merely a useful engineering device — it is the physical basis of purposive behavior, learning, and identity itself. When feedback is overloaded or disrupted, purposive behavior breaks down in characteristic, diagnosable ways (intention tremor, Parkinsonism).

## Summary

### Structure of a Feedback Loop

A feedback control system has five elements:

1. **Goal**: a target state (desired position of a ship's rudder, desired body temperature, desired trajectory of a reaching hand)
2. **Sensor**: observation of the actual current state
3. **Error signal**: difference between actual and desired
4. **Actuator**: mechanism that acts to reduce the error
5. **Effector**: the output that changes the world, generating new sensory input

The loop is **negative feedback** when the correction opposes the deviation (stabilizing). It is **positive feedback** when the correction amplifies the deviation (destabilizing, leading to runaway or oscillation).

### Canonical Examples in Wiener

**Watt Steam Governor (1788)**: Two balls on a spinning governor arm fly outward as the engine speeds up; their outward motion mechanically reduces steam admission; the engine slows. Maxwell (1868) gave the first mathematical stability analysis. *The simplest instance of negative feedback in a machine.*

**Ship's Steering Engine**: The helmsman's small motion on the wheel is amplified by a servo into the large force required to move the rudder. Error = (desired heading − actual heading). The steering engine continuously corrects this error. One man can steer a ship that otherwise would require ten men pulling in an emergency.

**Anti-Aircraft Predictor (WWII)**: Wiener's own contribution. Given noisy radar data on a target aircraft, compute the aircraft's probable future position (accounting for evasive maneuvers modeled statistically) and aim the gun at the predicted position. The prediction is updated continuously as new observation comes in. *This is where Wiener's formal feedback theory originated.*

**Homeostasis (Body Temperature, Blood Chemistry)**: Body temperature is maintained at 98.6°F by a dense network of negative-feedback loops: if temperature rises, sweat glands activate, blood vessels dilate; if it falls, shivering begins, vessels constrict. The same structure governs blood oxygen, CO₂, hormones, pH. *The biological instance of feedback as anti-entropic maintenance of pattern.*

**Nervous System and Voluntary Motion**: Reaching for a glass of water: the eye observes the hand's position; the cerebellum computes the motor error; corrective signals travel to muscles; the hand adjusts; the cycle repeats until the glass is grasped. The feedback loop runs at ~10Hz through the nervous system, too fast for conscious awareness.

### Feedback Breakdown: Intention Tremor and Parkinsonism

Wiener and collaborators (Rosenblueth, Bigelow) used their tropism machine ("moth" / "bedbug" — a phototropic cart with adjustable feedback amplification) to model neurological breakdown:

**Intention Tremor** (cerebellum damage): When **voluntary feedback** is overloaded (amplification too high), the reaching motion oscillates — the hand swings wider and wider instead of converging on the target. The oscillations only appear when purposive motion is invoked. Analogy: the moth's phototropic feedback overloaded → oscillatory search that grows rather than converges.

**Parkinsonism** (postural feedback disorder): When **postural feedback** (background muscle tone regulation) is overloaded, tremor appears at *rest* and subsides when the voluntary feedback becomes active (because voluntary and postural feedback partially cancel). The "resting tremor that subsides on purpose" = Parkinsonism. The machine analog: the cart's secondary feedback (rudder positioning) oscillates when there is no light source to invoke the voluntary feedback.

This mechanical modeling of neurological disorders was the first use of feedback control theory to generate testable predictions in neuroscience.

### Feedback as the Basis of Learning

Wiener extends the feedback principle to learning itself. A system learns when:
- Its past outputs are monitored for performance
- Poor performance generates a feedback signal that modifies the system's future behavior
- This modification (not just the output) is the learning

This is the biological mechanism behind conditioned reflexes (Pavlov) at the elemental level and human cultural development at the complex level. The learning machine's "preference" (statistically adjustable tendency) is feedback-based; its "constraint" (rigid rule) is not. See [[Concepts/Learning vs Rigidity (Wiener)]].

## Key Claims / Positions

- Negative feedback is the universal mechanism of purposive behavior in both machines and living systems.
- Feedback is the physical basis of homeostasis — the maintenance of life against entropy.
- Feedback breakdown (overloaded amplification) produces characteristic failure modes that map onto neurological disorders.
- Learning = feedback on past performance that modifies future behavior; it is not a separate phenomenon from control.
- Control and communication are unified: error signals ARE messages.

## Contradictions / Open Questions

- > [!warning] Shannon's information theory treats the channel/signal abstractly without feedback between sender and receiver; it is a one-way model (source → transmitter → noisy channel → receiver). Wiener's cybernetics is fundamentally bidirectional (output → observation → correction → output). The two frameworks are complementary but their relationship is not fully formalized in either work. See [[Contradictions/Wiener vs Shannon - Information and Meaning]].
- Does the feedback model of purposive behavior explain or merely describe intentionality? Wiener demonstrates that feedback produces goal-directed behavior; whether this constitutes genuine "purpose" or merely the appearance of it is the same question Searle raises about syntax and semantics. See [[Thinkers/John Searle]].
- The anti-aircraft predictor was designed to track a human pilot trying to evade. Wiener was deeply troubled by the use of his work in weapons systems — see [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]].

## Sources

- Primary: [[Sources/The Human Use of Human Beings - Norbert Wiener (1950)]] (Chapters I, II, X; the moth/bedbug machine described in Chapter X)

## Related

- [[Thinkers/Norbert Wiener]]
- [[Concepts/Cybernetics (Wiener)]] (the general framework)
- [[Concepts/Entropy and Information (Wiener)]] (feedback as anti-entropic mechanism)
- [[Concepts/Learning vs Rigidity (Wiener)]] (learning as feedback-based modification)
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]] (what happens when feedback loops achieve goals in unintended ways)
- [[Thinkers/Claude Shannon]] (information transmission without feedback — the complementary model)

*Concept page created 2026-06-04 during Wiener 1950 ingest. The core mechanism of cybernetics: negative feedback as the universal anti-entropic mechanism governing purposive behavior in machines and living systems.*

---

*"The Watt governor keeps the engine from running wild... If it starts to run wild, the balls of the governor fly upward from centrifugal action, and in their upward flight they move a lever which partly cuts off the admission of steam."* (Wiener, Chapter IX)
