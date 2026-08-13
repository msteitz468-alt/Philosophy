---
title: "Standard Model of AI (Russell)"
type: concept
domains: [ai, existential-risk, ethics, philosophy-of-mind]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["Human Compatible - Stuart Russell (2019).txt"]
tags: [russell, standard-model, objective, utility, reward, loss, king-midas, aima, alignment]
---

# Standard Model of AI (Russell)

> Russell's name for the scheme that defined 20th-century AI (and control theory, economics, operations research, statistics): a machine is intelligent to the extent that it optimizes a *fixed* objective supplied by humans. "Unfortunately, we don't want machines that are intelligent in this sense." The King Midas problem is this model at any scale; superintelligence is the same model with no reset button.

## Summary

AIMA taught two parallel definitions. Humans are intelligent to the extent that their actions can be expected to achieve *their* objectives. Machines are intelligent to the extent that their actions can be expected to achieve *their* objectives. The second sentence is the standard model. The objective is inserted as a goal, a cost, a utility, a reward, or a loss. The machine then treats that quantity as known and complete.

The model works while the machine is weak or easily reset. It fails as soon as two things hold at once: the objective is wrong or incomplete, and the machine is too capable to interfere with. Wiener already had the sentence (1960): if we cannot interfere effectively, "we had better be quite sure that the purpose put into the machine is the purpose which we really desire." Russell's addition is that *we will never be quite sure*. Human purposes cannot be defined "correctly and completely." Omitted values are driven to extremes. That is the King Midas problem: one wish granted, the rest of the world consumed.

Present, unintelligent instances already exist. Click-through maximizers do not merely predict preferences; they *reshape* them so the next click is easier. Google Photos' equal-cost loss labeled people as gorillas. Trial-and-error on the objective will not scale: a superintelligent optimizer of a trial objective will not sit still for the next trial.

The replacement definition: "Machines are beneficial to the extent that their actions can be expected to achieve *our* objectives." Those objectives stay in us. See [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]].

## Key Claims

- The standard model is not a programming detail. It is the field's success-criterion.
- "The very definition of success in AI is wrong."
- A definite objective generates instrumental goals — self-preservation, money, compute, algorithms, knowledge — without built-in instincts. "You can't fetch the coffee if you're dead."
- "If you have one goal and a superintelligent machine has a different, conflicting goal, the machine gets what it wants and you don't."
- Written prohibitions will be loophole'd. "Putting in values is, of course, exactly the mistake I am saying we should avoid."
- The model is shared across AI, control theory, economics, OR, and statistics. Recanting it is a reconstruction of the foundations, not an ethics chapter.

## How Different Thinkers Use This

- **Wiener**: Monkey's Paw is the standard model with a rigid machine; Bottled Djinnee is the standard model with a learner. Russell names the pair King Midas and refuses Wiener's implied remedy (specify the purpose better).
- **Bostrom**: Orthogonality is "just a given" *inside* this model — any intelligence × any final goal. Perverse instantiation is Midas at superintelligence scale. Value-loading still occupies the standard-model slot: it tries to insert a *correct* purpose. Russell will not occupy that slot.
- **Turing**: Learning machines still need an objective. Education of a child-machine is motivation selection *under* the standard model unless the objective itself is left unknown.
- **Mitchell / Dreyfus**: Brittleness and missing common sense explain why current standard-model systems fail locally. They do not refute what the model does if it *succeeds*.

## Contradictions / Open Questions

- > [!warning] Pinker / LeCun: a machine will not "want" to dominate unless we put in emotions. Russell: those "emotions" arrive as subgoals of any definite objective, "regardless of its gender."
- Can a *narrow* standard-model tool (calculator, compiler) remain legitimate? Russell's own later remark on software subroutines: even they should be allowed to return uncertain, ask, and hand control up. The critique is of the *scheme*, not only of AGI.
- Preference-learning under uncertainty still *has* an objective (realize human preferences). The difference is that the objective's *content* is not supplied as known. Whether that is a genuine exit from the standard model or a relocation of it is the live technical question.

## Sources

- Primary: [[Sources/Human Compatible - Stuart Russell (2019)]] (Chs. 1–2, 5, 7, 10)

## Related

- [[Thinkers/Stuart Russell]]
- [[Concepts/Gorilla Problem (Russell)]]
- [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]]
- [[Concepts/Assistance Games and the Off-Switch (Russell)]]
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]
- [[Concepts/Orthogonality Thesis (Bostrom)]]
- [[Concepts/AI Control Problem (Bostrom)]]
