---
title: "Predictive Processing (Clark)"
type: concept
domains: [philosophy-of-mind, cognitive-science, neuroscience]
created: "2026-07-01"
updated: "2026-08-12"
sources: ["Surfing Uncertainty - Andy Clark (2016).md", "The Experience Machine How Our Minds Predict and Shape Reality (Andy Clark) (z-library.sk, 1lib.sk, z-lib.sk).md", "The Predictive Mind - Jakob Hohwy (2013).md", "Being You - Anil Seth (2021).md"]
tags: [predictive-processing, prediction-error, controlled-hallucination, helmholtz, friston, active-inference]
---

# Predictive Processing (Clark)
> The brain is not a passive receiver of sensory data but a multilevel prediction machine: it constantly guesses the causes of its sensory signals top-down, and uses only the *errors* in those guesses to update itself.

## Summary

Predictive processing is the framework of Andy Clark's *Surfing Uncertainty* (2016) — now the technical primary — and of the later popularization *The Experience Machine* (2023). It is a family of theories (including "hierarchical predictive coding" and "active inference") holding that the brain's core activity is generating predictions of its own sensory signals and correcting them against incoming evidence. Clark's 2016 name for the agents: "proactive predictivores." The 2023 slogan: "reality as we experience it is built from our own predictions."

What distinguishes PP from mere **predictive coding**, Clark insists, "is not simply the use of the data compression strategy… Rather, it is the use of that strategy in the very special context of hierarchical… systems deploying probabilistic generative models" (1.7). Forward flow is residual **prediction error** (surprisal); backward and lateral flow is prediction. Architecture is duplex: representation units vs error units (conjecturally deep vs superficial pyramidal cells). "When the flow of prediction adequately accounts for the incoming signal, the visual scene is perceived" (1.1).

The framework **inverts** the traditional feedforward picture. The rejected "smart camera" model has sensory information processed from the outside in, step by step, building up a representation. Predictive processing reverses the dominant flow: predictions cascade *downward/backward* from higher cortical areas toward the sensory peripheries, and what flows *upward* is only **prediction error** — the "news," the residual mismatch between what the brain expected and what it got. "We see the world by predicting the world. But where prediction errors ensue, the brain must predict again."

Clark marshals neuroanatomy and information theory in support. Backward/downward cortical connectivity outweighs forward connectivity (by up to 4:1), which the smart-camera model cannot explain but the prediction model predicts; and predictive coding is radically efficient in the way data compression is (JPEG, MP3, interframe video transmit only deviations from what is predicted), which helps explain how a 20%-of-energy organ does so much. The architecture is **hierarchical**: higher levels (words, sentences) predict lower levels (letters, phonemes), and each level passes up only its errors.

## Key Claims / Positions

- **Perception is prediction-driven, not stimulus-driven.** The historical root is Hermann von Helmholtz's "unconscious inference," which Clark glosses as the brain asking: "Given everything I know, how must the world be for me to be receiving the pattern of signals currently present?"
- **Prediction error is the brain's currency.** Mismatches drive each improved round of guessing and are the engine of learning — failed predictions (as in artificial neural networks starting from random weights) are what the world uses to correct the model.
- **"Woods before the trees":** processing runs coarse-gist-first, then detail, consistent with top-down guessing being filled in by error correction.
- **Unified scope.** The same machinery builds perception, action (see [[Concepts/Active Inference and Action (Clark)]]), bodily sensation and emotion (see [[Concepts/Interoception and Constructed Emotion (Clark)]]), and pathology (see [[Concepts/Precision-Weighting (Clark)]]). 2016 names the inner half of this a [[Concepts/Cognitive Package Deal (Clark)|cognitive package deal]] and the outer half an [[Concepts/Action-Oriented Engagement Machine (Clark)|action-oriented engagement machine]].
- **Bootstrap heaven.** Learning and online processing use the same resources: attempting to predict the sensory stream installs the models that make later predictions succeed (1.3). Empirical Bayes; the animal's perspective has no observer's map — only changing receptor energies (1.2).
- **Two stories** (Introduction). A broad vision of multilevel probabilistic prediction could survive even if many details of the specific PP schema fail.
- **Four-element toolkit** (2023 Appendix; already implicit in 2016): a **generative model**, **predictions**, **prediction errors**, and **precisions**. Karl Friston's free-energy/active-inference framing is named in the 2016 acknowledgements and Appendix 2.

## How This Relates to Prior Thinkers

- **[[Thinkers/Kant]] / Helmholtz**: the Kantian insight that the mind actively structures experience is here given a mechanistic, Helmholtzian form. The world does not stamp itself on a passive mind ([[Thinkers/Descartes]]'s rejected wax-imprint model); the mind hypothesizes the world.
- **[[Thinkers/George Berkeley]]**: predictive processing is a naturalist descendant of the idea that experienced reality is mind-constructed — but Clark's construct is *constrained* by sensory error, keeping it "porous to the world" rather than idealist.
- **[[Concepts/Simulation Hypothesis (Virk)]]**: both make experience a rendered/generated construct; Clark's version locates the "rendering engine" in the biological brain and insists on world-anchoring via error.
- **[[Thinkers/Jakob Hohwy]]**: the systematic 2013 statement of the same family, under the name [[Concepts/Prediction Error Minimization (Hohwy)]]. Hohwy is stricter (PEM is *all* the brain does) and internalist (the mind stays behind a sensory boundary). Clark's "porous to the world" is exactly the direction Hohwy refuses. See [[Contradictions/Hohwy vs Clark - Secluded Inference vs Extended Mind]].
- **[[Thinkers/Anil Seth]]**: Sussex colleague; *Being You* (2021) now primary. Seth splits the family: predictive processing is a theory of *how brains work*; [[Concepts/Controlled Hallucination (Clark)|controlled hallucination]] is that theory applied to *phenomenology*. He names Clark as champion of action-oriented PP (*Surfing Uncertainty*) and does not credit him for the slogan. Seth's distinctive next step is biologization — PEM exists to regulate a living body ([[Concepts/Beast Machine Theory (Seth)]]) — not Clark's extension into world and tech.

## Contradictions / Open Questions
- > [!warning] Same mechanism, opposite location of the mind — see [[Contradictions/Hohwy vs Clark - Secluded Inference vs Extended Mind]].

## Sources
- [[Sources/Surfing Uncertainty - Andy Clark (2016)]] (technical primary)
- [[Sources/The Experience Machine - Andy Clark (2023)]]
- [[Sources/The Predictive Mind - Jakob Hohwy (2013)]]
- [[Sources/Being You - Anil Seth (2021)]]

## Related
- [[Concepts/Action-Oriented Engagement Machine (Clark)]]
- [[Concepts/Cognitive Package Deal (Clark)]]
- [[Concepts/Productive Laziness and Cognitive Niches (Clark)]]
- [[Concepts/Controlled Hallucination (Clark)]]
- [[Concepts/Precision-Weighting (Clark)]]
- [[Concepts/Active Inference and Action (Clark)]]
- [[Concepts/Extended Mind (Clark and Chalmers)]]
- [[Concepts/Prediction Error Minimization (Hohwy)]]
- [[Thinkers/Andy Clark]]
- [[Thinkers/Jakob Hohwy]]
