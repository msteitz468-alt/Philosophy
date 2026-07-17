---
title: "Predictive Processing (Clark)"
type: concept
domains: [philosophy-of-mind, cognitive-science, neuroscience]
created: "2026-07-01"
updated: "2026-07-01"
sources: ["The Experience Machine How Our Minds Predict and Shape Reality (Andy Clark) (z-library.sk, 1lib.sk, z-lib.sk).txt"]
tags: [predictive-processing, prediction-error, controlled-hallucination, helmholtz, friston, active-inference]
---

# Predictive Processing (Clark)
> The brain is not a passive receiver of sensory data but a multilevel prediction machine: it constantly guesses the causes of its sensory signals top-down, and uses only the *errors* in those guesses to update itself.

## Summary

Predictive processing is the framework at the heart of Andy Clark's *The Experience Machine* (2023) — a family of theories (including "hierarchical predictive coding" and "active inference") holding that the brain's core activity is generating predictions of its own sensory signals and correcting them against incoming evidence. Clark's central claim: "reality as we experience it is built from our own predictions."

The framework **inverts** the traditional feedforward picture. The rejected "smart camera" model has sensory information processed from the outside in, step by step, building up a representation. Predictive processing reverses the dominant flow: predictions cascade *downward/backward* from higher cortical areas toward the sensory peripheries, and what flows *upward* is only **prediction error** — the "news," the residual mismatch between what the brain expected and what it got. "We see the world by predicting the world. But where prediction errors ensue, the brain must predict again."

Clark marshals neuroanatomy and information theory in support. Backward/downward cortical connectivity outweighs forward connectivity (by up to 4:1), which the smart-camera model cannot explain but the prediction model predicts; and predictive coding is radically efficient in the way data compression is (JPEG, MP3, interframe video transmit only deviations from what is predicted), which helps explain how a 20%-of-energy organ does so much. The architecture is **hierarchical**: higher levels (words, sentences) predict lower levels (letters, phonemes), and each level passes up only its errors.

## Key Claims / Positions

- **Perception is prediction-driven, not stimulus-driven.** The historical root is Hermann von Helmholtz's "unconscious inference," which Clark glosses as the brain asking: "Given everything I know, how must the world be for me to be receiving the pattern of signals currently present?"
- **Prediction error is the brain's currency.** Mismatches drive each improved round of guessing and are the engine of learning — failed predictions (as in artificial neural networks starting from random weights) are what the world uses to correct the model.
- **"Woods before the trees":** processing runs coarse-gist-first, then detail, consistent with top-down guessing being filled in by error correction.
- **Unified scope.** The same machinery builds perception, action (see [[Concepts/Active Inference and Action (Clark)]]), bodily sensation and emotion (see [[Concepts/Interoception and Constructed Emotion (Clark)]]), and pathology (see [[Concepts/Precision-Weighting (Clark)]]).
- **Four-element toolkit** (Clark's Appendix): a **generative model** (a resource that can generate instances of the kind of data it knows about), **predictions** (top-down guesses it issues), **prediction errors** (mismatch signals), and **precisions** (reliability weightings). Karl Friston's free-energy/active-inference framing underlies the account (named in Clark's notes and acknowledgments).

## How This Relates to Prior Thinkers

- **[[Thinkers/Kant]] / Helmholtz**: the Kantian insight that the mind actively structures experience is here given a mechanistic, Helmholtzian form. The world does not stamp itself on a passive mind ([[Thinkers/Descartes]]'s rejected wax-imprint model); the mind hypothesizes the world.
- **[[Thinkers/George Berkeley]]**: predictive processing is a naturalist descendant of the idea that experienced reality is mind-constructed — but Clark's construct is *constrained* by sensory error, keeping it "porous to the world" rather than idealist.
- **[[Concepts/Simulation Hypothesis (Virk)]]**: both make experience a rendered/generated construct; Clark's version locates the "rendering engine" in the biological brain and insists on world-anchoring via error.

## Sources
- [[Sources/The Experience Machine - Andy Clark (2023)]]

## Related
- [[Concepts/Controlled Hallucination (Clark)]]
- [[Concepts/Precision-Weighting (Clark)]]
- [[Concepts/Active Inference and Action (Clark)]]
- [[Thinkers/Andy Clark]]
