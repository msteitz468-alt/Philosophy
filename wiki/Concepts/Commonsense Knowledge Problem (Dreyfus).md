---
title: "Commonsense Knowledge Problem (Dreyfus)"
type: concept
domains: [ai, philosophy-of-mind, epistemology, phenomenology]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["What Computers Still Can't Do - Hubert Dreyfus.md"]
tags: [dreyfus, commonsense, know-how, cyc, frames, micro-worlds, relevance]
---

# Commonsense Knowledge Problem (Dreyfus)
> The stall in classical AI was not a missing catalog of facts. Everyday understanding is know-how — interests, feelings, a body — and making that preconceptual background explicit as symbols is, Dreyfus thinks, hopeless.

## Summary

The children's-story programs of the late 1960s lacked "the common sense of a four-year-old, and no one knew how to give them the background knowledge necessary for understanding even the simplest stories." [[Thinkers/Marvin Minsky]] had hoped it was "just a question of cataloging 10 million facts." [[Thinkers/Hubert Dreyfus]]'s 1992 introduction splits what got called the **commonsense-knowledge problem** into three problems:

1. How everyday knowledge must be organized so that one can make inferences from it.
2. How skills or know-how can be represented as knowing-that.
3. How relevant knowledge can be brought to bear in particular situations.

The second and third are the ones that do the philosophical work. Background understanding is a kind of **know-how**, not a theory of the domain. Representationalism (Descartes–Kant–Frege, inherited by GOFAI) treats everyday understanding as a huge structure of implicit propositional beliefs. Dreyfus: you cannot make that structure explicit without losing what made it a background.

**Micro-worlds do not compose.** Phase III (1967–72) isolated gamelike domains — SHRDLU's blocks world, Guzman–Waltz vision, Winston's learning, Shakey. Minsky and Papert: a micro-world is "a fairyland in which things are so simplified that almost every statement about them would be literally false if asserted about the real world." A micro-world is a *universe* of facts, not a *world* of purposes and practices. "There is no way they can be combined and extended to the world of everyday life." Saying SHRDLU understands a little English is a metaphor.

**Frames and scripts still treat the background as an object.** Phase IV (1972–77) — Minsky frames, Schank scripts, KRL prototypes — is the attempt to represent everyday understanding. A frame is a stereotyped situation with defaults; a script is a stereotyped sequence (restaurant: ATRANS, PTRANS, INGEST). Story understanders fail on abnormal cases, script-selection, relevance-in-a-story, the infinity of life-themes, and the *ceteris paribus* regress (Charniak's birthday *it*). A program in KRL "is not always-already-in-a-situation." Husserl's outer horizon and Heidegger's cultural background are what the formalism keeps trying to add as one more formal object.

**Knowledge engineering is not the same problem.** DENDRAL, MYCIN, and chess programs can succeed where relevance is pre-fixed and primitives are context-free. That is not general intelligence. The 1979 introduction is careful to concede the engineers their domains.

**CYC as last defense.** Lenat and Feigenbaum propose to formalize "consensus knowledge" by task-neutral ontological engineering. Dreyfus's objections: the body and deixis ("the-cup-I-am-drinking-from"); imagination and metaphor (citing [[Thinkers/John Searle]]); retrieval scaling (more facts make machines slower, humans faster); gift-*savoir faire* (Bourdieu: do not read breakdown-rules back into fluent practice); innovation; analogy and style. Commonsense physics is case-discrimination, not a theory. "Mary saw a dog in the window. She wanted it" is not solved by adding a fact.

**The holist circle vs the reductionist regress.** Similarity depends on relevance and relevance on similarity. Intelligence is situated and "cannot be separated from the rest of human life." McCarthy still treats common knowledge as *facts*. Dreyfus: "all intelligibility and all intelligent behavior must be traced back to our sense of what we *are*… something we can never explicitly *know*."

## Key Claims / Positions

### How Different Thinkers Use This

- **[[Thinkers/Hubert Dreyfus]]**: three problems, not one; know-how cannot be converted into knowing-that without remainder.
- **[[Thinkers/Marvin Minsky]]**: a large but finite data base (~10^5 elements, ~10^6 for "very great intelligence") plus frames. Dreyfus: the estimate already assumes the [[Concepts/Four Assumptions of Artificial Reason (Dreyfus)|ontological assumption]].
- **[[Thinkers/Melanie Mitchell]]**: later names the same gap [[Concepts/Common Sense and Analogy in AI (Mitchell)|common sense and analogy]] — Winograd schemas, the long tail — as what deep learning still lacks. Empirical ally; no Heidegger.
- **[[Thinkers/Andy Clark]]**: predictive processing and the [[Concepts/Extended Mind (Clark and Chalmers)|extended mind]] try to dissolve the "store the world" problem by letting the world be its own model — the slogan Dreyfus already quotes from Chapman. Clark is more confident the prediction machine can do the recruiting.
- **[[Thinkers/Wittgenstein]]**: *ceteris paribus* conditions and [[Concepts/Forms of Life (Wittgenstein)|forms of life]] as the unformalizable halt to the context regress.

## Contradictions / Open Questions

- > [!warning] Whether a large trained net "has" commonsense or only mimics local regularities is the live form of this problem after 2012 — see [[Contradictions/Dreyfus vs Computationalism - Skilled Coping vs Formal Rules]].
- Knowledge engineering's successes (MYCIN-style) are real. Dreyfus's claim is that they do not scale to the background that made the domain isolable.

## Sources

- [[Sources/What Computers Still Can't Do - Hubert Dreyfus (1992)]]

## Related

- [[Thinkers/Hubert Dreyfus]]
- [[Concepts/GOFAI as Degenerating Research Program (Dreyfus)]]
- [[Concepts/Skilled Coping and the Five Stages of Expertise (Dreyfus)]]
- [[Concepts/Frames (Minsky)]]
- [[Concepts/Common Sense and Analogy in AI (Mitchell)]]
- [[Concepts/Forms of Life (Wittgenstein)]]
- [[Thinkers/Marvin Minsky]], [[Thinkers/Melanie Mitchell]], [[Thinkers/Andy Clark]]
