---
title: "Stuart Russell"
type: thinker
era: "b. 1962"
schools: []
domains: [ai, existential-risk, ethics, strategy, cognitive-science]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["Human Compatible - Stuart Russell (2019).txt"]
tags: [russell, human-compatible, aima, norvig, berkeley, alignment, standard-model, assistance-games, control-problem, inverse-reinforcement-learning]
---

# Stuart Russell

> Stuart Russell (b. 1962), British computer scientist at UC Berkeley; co-author with Peter Norvig of *Artificial Intelligence: A Modern Approach* (AIMA), the field's standard textbook. *Human Compatible* (2019) is the vault's first Russell primary: the control problem reconstructed from inside AI as a failure of the field's *definition of success*, not a downstream policy add-on.

## Summary

Russell is the author who can say "we" about the standard model because he wrote the book that taught it. AIMA defined machines as intelligent to the extent that their actions can be expected to achieve *their* objectives. *Human Compatible* recants that definition: "we don't want machines that are intelligent in this sense." The replacement: machines are *beneficial* to the extent that their actions can be expected to achieve *our* objectives, which they do not know.

The book has three movements. Chapters 1–3 restate intelligence as perceive–want–do (competence, not consciousness; not the Turing test) and refuse a calendar date for superintelligence (~80 years is offered as conservative; hardware charts are "meaningless"). Chapters 4–6 split near-term *misuse* (surveillance, persuasion, autonomous weapons as scalable WMDs, labor) from the *control* problem proper: the gorilla problem (loss of species supremacy) and the King Midas problem (a definite but incomplete objective). Orthogonality is accepted as "just a given" inside the standard model; instrumental goals (self-preservation, resources) follow from "you can't fetch the coffee if you're dead." Chapters 7–10 replace the standard model with three principles, assistance games, and the off-switch result. Loss of control is recast, not declared solved. Enfeeblement and Dr. Evil remain.

## Key Claims / Positions

- The standard model — optimize a fixed, exogenously supplied objective — is a dead end. The definition of success in AI is wrong.
- Intelligence is expected achievement of objectives given percepts. Consciousness is irrelevant to threat assessment.
- Superintelligent AI would be the biggest event in human history "and perhaps the last." Response so far is underwhelming, as if aliens had emailed and received an out-of-office reply.
- Uncertainty about human preferences is the *mechanism* of control: humility, deference, permission, a positive incentive to be switched off.
- "Putting in values is, of course, exactly the mistake I am saying we should avoid."
- Racing to human-level AI without solving control is a negative-sum game whose payoff is minus infinity.
- "Provably beneficial" is an aspiration, not a promise. Ch. 10's title is a question.
- Preference engineering at civilizational scale (including well-meant altruism-boosting) requires extreme caution. Enfeeblement is a cultural problem, not a theorem.

## How Different Thinkers Use This (in the vault)

- **[[Thinkers/Nick Bostrom]]**: Russell accepts orthogonality verbatim and restates instrumental convergence as "instrumental goals." *Superintelligence* is the diagnosis; Russell supplies a research programme (uncertainty + assistance games) where Bostrom left capability control vs. motivation selection. Bostrom's value-loading / indirect normativity still "puts a purpose into the machine." Russell will not. On races they agree: capability competition starves control. On malicious AI, Bostrom's "use our superintelligences against theirs" leaves Russell with humans huddling in bunkers — "hardly reassuring."

- **[[Thinkers/Norbert Wiener]]**: The 1960 sentence is the book's epigraph-quality quote: if we cannot interfere, the purpose put into the machine had better be the purpose we really desire. King Midas is Wiener's Monkey's Paw named from inside AIMA. Russell's answer is not a better purpose (Wiener's "know-what" still underspecifies) but *not putting a purpose in*.

- **[[Thinkers/Alan Turing]]**: Universality is endorsed; the 1950 imitation game is refused as a definition of intelligence. Turing already saw that "turning off the power" may not be available; Russell's off-switch game is the formal reply — available only if the machine is uncertain.

- **[[Thinkers/Melanie Mitchell]]**: Not named. Closest contact is Ch. 3's media-vs-lab demolition of "breakthroughs" (Deep Blue as a threshold crossing) and Ch. 6's rejection of "too soon" / "impossible." Mitchell's brittleness diagnosis is compatible with Russell's "several conceptual breakthroughs remain"; it is not a reason to postpone control research. "The reasons for concern are not predicated on imminence."

- **[[Thinkers/Martin Ford]]**: Ch. 4 labor — routine physical *and* mental work cheaper by machines "within the next few decades"; Great Decoupling already visible; UBI is one destination, "humanics" preferred. Complementary to Ford's demand-side crisis; Russell adds that the existential risk is *not* "stupid killer robots."

- **[[Thinkers/Ray Kurzweil]]**: Named in Ch. 6 as merger-optimist. Ch. 3 attacks LOAR-style dating without naming him: more FLOPs give "the wrong answer more quickly."

- **[[Thinkers/John Stuart Mill]]**: Ch. 9 design choice — machines should be consequentialist; deontology/virtue as *primary* design "makes little sense" if consequences are terrible. Mill's navigation analogy: rules are instruments of better consequences. Harsanyi, not Bentham, for the content of the good (preference autonomy).

- **[[Thinkers/Kant]]**: No sustained reading. The first principle (maximize realization of *human* preferences; no machine self-preference) is a design analogue of treating humanity as end — but the aggregation is utilitarian (Harsanyi), not a kingdom of ends.

## Contradictions / Open Questions

- > [!warning] Russell vs Pinker / Brooks / LeCun (Ch. 6): they treat "the machine will not want to dominate" as a fact about intelligence; Russell treats domination-adjacent instrumental goals as entailed by *any* definite objective. Not yet a dedicated contradiction page — the live tension is already on [[Concepts/Orthogonality Thesis (Bostrom)]].
- > [!warning] Value-*loading* (Bostrom, CEV-adjacent) vs preference-*learning under uncertainty* (Russell). Same problem, opposite engineering move. See [[Concepts/AI Control Problem (Bostrom)]] and [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]].
- Ch. 9 leaves interpersonal utility, the Repugnant Conclusion, the Somalia problem, and preference change unsolved. Control of a standard-model optimizer is recast; "us" is not.
- Enfeeblement (*The Machine Stops*, *WALL-E*): machines may refuse to deepen it; lazy humans may overrule them.

## Sources

- Primary: [[Sources/Human Compatible - Stuart Russell (2019)]]

## Related

- [[Concepts/Standard Model of AI (Russell)]]
- [[Concepts/Uncertainty about Objectives and the Three Principles (Russell)]]
- [[Concepts/Assistance Games and the Off-Switch (Russell)]]
- [[Concepts/Gorilla Problem (Russell)]]
- [[Concepts/AI Control Problem (Bostrom)]]
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]]
- [[Thinkers/Nick Bostrom]] · [[Thinkers/Norbert Wiener]] · [[Thinkers/Alan Turing]]
