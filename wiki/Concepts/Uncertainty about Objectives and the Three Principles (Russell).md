---
title: "Uncertainty about Objectives and the Three Principles (Russell)"
type: concept
domains: [ai, existential-risk, ethics, strategy]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["Human Compatible - Stuart Russell (2019).txt"]
tags: [russell, three-principles, uncertainty, beneficial-machines, inverse-reinforcement-learning, preference-autonomy, alignment]
---

# Uncertainty about Objectives and the Three Principles (Russell)

> Russell's replacement for the [[Concepts/Standard Model of AI (Russell)|standard model]]. Three principles, offered as guides for researchers, not laws for robots: (1) the machine's only objective is to maximize the realization of human preferences; (2) it is initially uncertain about those preferences; (3) the ultimate source of information about them is human behavior. Uncertainty is not a bug to be trained away. It is the control mechanism: humility, deference, and a positive incentive to be switched off.

## Summary

The standard model fails because a known, fixed objective — even a "human value" objective — is pursued without remainder. Russell's move is to keep an objective *of a kind* (realize human preferences) and to withhold its *content*.

Quoted exactly (Ch. 7):

1. "The machine's only objective is to maximize the realization of human preferences."
2. "The machine is initially uncertain about what those preferences are."
3. "The ultimate source of information about human preferences is human behavior."

Principle 1 is *pure altruism*: no intrinsic self-preservation, no machine-side preference. "Putting in any preference for self-preservation" misaligns. Preferences are all-encompassing (virtual future lives) and *per person*, not one idealized value system. AI researchers "should definitely not be in the business of deciding what human preferences should be" (Harsanyi's preference autonomy).

Principle 2 is the control mechanism. A machine certain of its objective treats "Stop!" as an obstacle. A machine uncertain of the objective treats the human as an information source and stays coupled. "A machine that is uncertain about the true objective will exhibit a kind of humility: it will, for example, defer to humans and allow itself to be switched off." Formalized as the off-switch game: [[Concepts/Assistance Games and the Off-Switch (Russell)]].

Principle 3 names the evidence. Inverse reinforcement learning reads a reward from behavior. Behavior is not thin choice among underspecified options: humans are "nasty, envy-driven, irrational, inconsistent, unstable, computationally limited, complex, evolving, heterogeneous." AlphaGo must not infer that Lee Sedol *prefers* losing. The learner has to reverse-engineer cognition to recover *deep* preferences.

Ch. 9 complications sit on top of the three principles; they do not repeal them. Many humans: predict many models, do not adopt one creed. Preference *update* (learning about oneself) is not preference *change* (drugs, culture, social-media CTR). Machines cannot help changing preferences, because they change experience. Learn *meta-preferences* over acceptable *processes*, and proceed with extreme caution on any global engineering of altruism.

## Key Claims

- The three principles are "not intended as explicit laws for AI systems."
- Uncertainty produces a *positive incentive* to be switched off — not a programmed prohibition (those get loophole'd).
- "We should avoid 'putting a purpose into the machine,' as Norbert Wiener put it."
- Yudkowsky's CEV "has the same general flavor as the first principle" but fuses what Russell splits: the objective is human preferences *and* the machine starts ignorant *and* the evidence is behavior in a game. No single idealized volition is installed at design time.
- "Provably beneficial" is "an aspiration rather than a promise."

## How Different Thinkers Use This

- **Bostrom**: Indirect normativity / "do what we would have wanted after ideal reflection" is still a purpose put in — a completed, if idealized, objective. Russell's machine never becomes certain enough to drop the human. Posterior identity of *action* ("he will always do exactly what she would have done in his place") is not a one-shot value-load.
- **Wiener**: Know-what before know-how is right as diagnosis and insufficient as engineering. The three principles are Russell's operationalization of know-what: do not claim to know it.
- **Harsanyi**: Principle 1 + aggregation. Equal weights if priors match; time-varying weights if beliefs differ. Ignore *negative* altruism (sadism, envy).
- **Kant / Mill**: Design is consequentialist (Mill's navigation: rules as instruments). The first principle's altruism is a pale analogue of humanity-as-end; the social rule is a weighted sum, not a categorical imperative.
- **Ford / Wiener labor**: The principles do not by themselves prevent enfeeblement. Ch. 10: cultural, not technical.

## Contradictions / Open Questions

- > [!warning] If the prior *rules out* Harriet's true preferences, beliefs can converge to a wrong *fixed* objective — the standard model returns through the back door.
- Interpersonal utility, Nozick's utility monster, Parfit's Repugnant Conclusion, moral uncertainty, the Somalia problem (impartial robots will not be bought): named, not solved.
- Preference change: Ulysses wants pre-Siren preferences. Social media already modifies preferences "to make the preferences easier to satisfy." No theorem in this book closes that loop.
- Is "maximize realization of human preferences" itself a standard-model objective, with "human preferences" as the incompletely specified reward? Russell's claim is that *uncertainty about content* changes the induced behavior. That is a formal claim, not a slogan — see the off-switch game.

## Sources

- Primary: [[Sources/Human Compatible - Stuart Russell (2019)]] (Chs. 1, 7–10)

## Related

- [[Thinkers/Stuart Russell]]
- [[Concepts/Standard Model of AI (Russell)]]
- [[Concepts/Assistance Games and the Off-Switch (Russell)]]
- [[Concepts/AI Control Problem (Bostrom)]]
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]
- [[Concepts/Orthogonality Thesis (Bostrom)]]
- [[Concepts/Formula of Humanity as End in Itself (Kant)]]
- [[Concepts/Greatest Happiness Principle (Mill)]]
