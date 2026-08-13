---
title: "Prediction Error Minimization (Hohwy)"
type: concept
domains: [philosophy-of-mind, cognitive-science, neuroscience]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["The Predictive Mind - Jakob Hohwy (2013).md"]
tags: [prediction-error-minimization, pem, predictive-processing, generative-model, surprisal, free-energy, hohwy, friston]
---

# Prediction Error Minimization (Hohwy)
> The brain's *only* job is to minimize the mismatch between the sensory input it predicted and the sensory input it got. Perception, action, and attention are three ways of doing that one thing.

## Summary

Prediction-error minimization (PEM) is the single mechanism of [[Thinkers/Jakob Hohwy]]'s *The Predictive Mind*. The vault already had the same family of ideas under Clark's label [[Concepts/Predictive Processing (Clark)]]. Hohwy's version is stricter: it is not a toolkit but a unificatory claim. "A single type of mechanism, reiterated throughout the brain, manages everything" (p. 2). The mechanism uses standard statistical tools — priors, likelihoods, expected precisions, complexity penalties — but it is "just a causal neuronal mechanism" and so "sits well with a reductionist, materialist view of the mind" (p. 2).

The problem PEM solves is the problem of perception recast as causal inference: states of the world cause sensory effects; the brain has only the effects and must infer the hidden causes ([[Concepts/Perception as Causal Inference (Hohwy)]]). A **generative model** produces a "fantasy" of expected sensory input (p. 54). The discrepancy between that fantasy and the data is **prediction error** — "the book's central term" (p. 43). Minimizing it maximizes likelihood and thereby the posterior. Functional reversal: rich worldly representation is *top-down*; only error is sent bottom-up. Friston's line, which Hohwy adopts: "forward connections are the feedback connections" (p. 47). Perceptual content *is* "the predictions of the currently best hypothesis about the world" (p. 48).

Supervision is by the world itself. Prediction error is an "objective corrective caused by the objects in the world" (pp. 33–34). Slogan: "The world is the truth. The feedback signal is the actual statistical regularities caused in us by the world itself" (p. 49). Causes nevertheless "remain hidden behind the veil of sensory input and can only be inferred" (p. 50). That last clause is the seed of [[Concepts/Secluded Mind and the Sensory Boundary (Hohwy)]].

Surprisal of sensation cannot be assessed directly from inside the skull. Prediction error is a tractable upper bound (under simplifying assumptions, variational free energy). Hohwy mostly stays with the epistemic PEM vocabulary; he uses free energy "obliquely" (p. 4). Recognition — inverting the generative model — is *implicit* in hierarchical PE minimization, not an extra invert-the-model step.

Chapters 3–4 complete the mechanism. **Expected precision** is second-order inference about when PE is trustworthy, implemented as gain on PE units; attention *is* optimizing those expectations. **Active inference** is the other direction of fit: change the world (especially proprioceptive input) so the fantasy comes true. Perception tightens the bound on surprise; only action reduces surprise; they must alternate. We are not "dark-room phenotypes" (p. 87).

## Key Claims / Positions

- **One mechanism, extreme parsimony.** Context, hierarchy, precision, action, and complexity are not extra principles; they are PEM applied to first- and second-order statistics.
- **Representation is a by-product.** The "dam-plugger" need not try to represent; "all that is needed… is hierarchical prediction error minimization" (p. 63).
- **Unsupervised, generative, hierarchical.** PEM differs from back-propagation: it needs no labelled training data, generates data top-down rather than classifying bottom-up, and works in deep hierarchies (Hinton 2007, at p. 8).
- **Not interested in veridicality as such.** The system charts "a precarious route towards the truth" because it minimizes *average* PE, not truth for truth's sake (pp. 140, 143). Illusions are parasitic on mostly-good automatic inference.
- **Challenges Hohwy lists (pp. 93–95).** (1) Testability: is the brain *only* doing PEM, or is this unfalsifiable just-so Bayes? Reply: quantitative models (DCM, RL, attention, saccades, illusions). (2) Explanatory reach: a principle this general risks explaining nothing. Reply: inference to the best explanation plus a mechanism that actually *starts* to solve the problem of perception.

## How Different Thinkers Use This

- **[[Thinkers/Jakob Hohwy]]**: PEM is the fundamental principle of the brain, located in the nervous system, implying seclusion.
- **[[Thinkers/Andy Clark]]**: same Helmholtz/Friston family, labelled "predictive processing," treated as the internal organ of *extended* minds. Clark's four-element toolkit (generative model, predictions, prediction errors, precisions) is Hohwy's mechanism without the "this is all there is" imperialism and without seclusion.
- **[[Thinkers/Karl Friston]]**: the formal source (hierarchical predictive coding, free energy, precision, active inference). Hohwy's book is the translation.

## Contradictions / Open Questions
- > [!warning] Same mechanism, opposite location of the mind — see [[Contradictions/Hohwy vs Clark - Secluded Inference vs Extended Mind]].
- > [!warning] Hohwy's "this is all the brain ever does" is the claim he says "few would agree" with (p. 7). The book is an IBE, hostage to empirical fortune.

## Sources
- [[Sources/The Predictive Mind - Jakob Hohwy (2013)]]

## Related
- [[Concepts/Perception as Causal Inference (Hohwy)]]
- [[Concepts/Predictive Processing (Clark)]]
- [[Concepts/Precision-Weighting (Clark)]]
- [[Concepts/Active Inference and Action (Clark)]]
- [[Concepts/Secluded Mind and the Sensory Boundary (Hohwy)]]
- [[Thinkers/Jakob Hohwy]]
- [[Thinkers/Karl Friston]]
