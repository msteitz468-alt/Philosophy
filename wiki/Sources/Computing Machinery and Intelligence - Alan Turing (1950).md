---
title: "Computing Machinery and Intelligence - Alan Turing (1950)"
type: source-summary
domains: [epistemology, philosophy-of-mind, computation, ai]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [turing, imitation-game, turing-test, digital-computers, universal-machine, learning-machines, philosophy-of-mind, ai, computation, 1950]
sources: ["Computing Machinery and Intelligence - Alan Turing.txt"]
---

# Computing Machinery and Intelligence - Alan Turing (1950)

> A. M. Turing's landmark 1950 paper in *Mind* that replaces the vague question "Can machines think?" with the operational Imitation Game, demonstrates that digital computers are universal machines capable of mimicking any discrete-state process, predicts they will pass the game by the end of the century with ~10^9 storage, and systematically rebuts nine contrary objections while sketching a research programme for "learning machines" built from child programmes plus education.

**Full citation**: A. M. Turing (1950) Computing Machinery and Intelligence. *Mind* 49: 433-460.

## Summary

Turing opens by rejecting a Gallup-poll definition of "machine" and "think" and instead substitutes the "imitation game." Three players: man (A), woman (B), interrogator (C) in separate room. C asks questions (ideally via teleprinter) to determine which is the man and which the woman. A tries to cause wrong identification; B tries to help. The new question: "What will happen when a machine takes the part of A in this game?" Will C be fooled as often?

The game draws a sharp line between physical and intellectual capacities (no need to simulate skin, voice, or beauty contests). Specimen questions illustrate: sonnet on Forth Bridge ("Count me out"), arithmetic (pause then correct sum), chess (mate in one).

"Machine" is restricted to digital computers (electronic, following instruction tables). Turing gives an outline of their architecture: store (like paper + book of rules), executive unit (operations), control (ensures instructions obeyed in order; enables loops and conditionals via "obey instruction at position X"). Digital computers can be constructed and can closely mimic a human computer performing complex operations ("programming").

Digital computers are *universal*: any discrete-state machine (one whose states are sufficiently distinct, predictable from prior state + input) can be mimicked by a suitably programmed and sufficiently capacious/fast digital computer. Babbage's (never completed) Analytical Engine was a mechanical precursor with the essential ideas; its non-electrical nature shows electricity is theoretically superficial (nervous system mixes chemical/electrical too). Storage capacity measured in "states" (e.g., Manchester machine ~10^50,000 states, ~165,000 digits).

Turing's famous prediction: "I believe that in about fifty years' time it will be possible to programme computers, with a storage capacity of about 10^9, to make them play the imitation game so well that an average interrogator will not have more than 70 per cent chance of making the right identification after five minutes of questioning." He further believes that "at the end of the century the use of words and general educated opinion will have altered so much that one will be able to speak of machines thinking without expecting to be contradicted."

He then turns to nine "Contrary Views on the Main Question":

(1) **Theological objection**: Thinking requires an immortal soul; God gives souls only to men and women. Reply: this arbitrarily limits divine omnipotence (God could give a soul to an elephant or a machine if fitting); we are instruments of His will both in procreation and in constructing machines.

(2) **"Heads in the sand" objection**: The consequences of machines thinking would be too dreadful; let us hope they cannot. Reply: not substantial enough to require refutation; consolation perhaps in transmigration.

(3) **Mathematical objection**: Gödel (1931), Church (1936), Kleene, Rosser, Turing (1937) show limitations on discrete-state machines (certain questions a given machine cannot answer correctly or at all). Reply: limitations on any *particular* machine have been shown, but it has only been *asserted* (no proof) that no such limitations apply to the human intellect. We too give wrong answers; superiority over one machine does not prove superiority over all possible machines.

(4) **Argument from consciousness** (quoted from Jefferson's 1949 Lister Oration): Not until a machine can write a sonnet or compose a concerto "because of thoughts and emotions felt, and not by the chance fall of symbols," and "know that it had written it," could we agree machine equals brain. No mechanism could *feel*. Reply: this is solipsism in extreme form (the only way to know anyone thinks is to *be* that person). In practice we use viva voce examinations to test real understanding vs. parroting, without access to inner feelings. If a sonnet-writing machine could sustain the kind of answers in a viva ("It wouldn't scan"; "nobody wants to be compared to a winter's day"), Jefferson would likely accept it. Mysteries of consciousness exist but need not be solved to answer the paper's question.

(5) **Arguments from various disabilities**: "You grant machines can do A–Z but never X" (be kind, resourceful, beautiful, have initiative, sense of humour, tell right from wrong, make mistakes, fall in love, enjoy strawberries and cream, learn from experience, be subject of own thought, have diversity of behaviour, do something really new). Reply: largely unconscious induction from current machines' small storage and narrow design. Machines can be programmed to *introduce* arithmetic mistakes deliberately to confuse the interrogator. A machine can be its own subject matter (self-modifying programmes, predicting effects of alterations). "Nothing new under the sun" and the assumption that all consequences are seen simultaneously are fallacies.

(6) **Lady Lovelace's objection** (from her 1842 memoir on Babbage): "The Analytical Engine has no pretensions to originate anything. It can do whatever we know how to order it to perform." (Hartree adds that machines of the time had not shown the property of thinking for themselves.) Reply: the evidence available to Lovelace was limited; it is possible machines have (or will have) the property. Turing is frequently surprised by machines; the "no surprise" view assumes the mind sees all consequences at once, which is false. A better variant ("never take us by surprise") is met directly by experience. The fallacy is common to philosophers and mathematicians.

(7) **Argument from continuity in the nervous system**: The nervous system is continuous (small errors in impulse size produce large differences downstream); discrete-state machines cannot mimic it. Reply: under the conditions of the imitation game the interrogator cannot exploit the difference. A continuous differential analyser can still give the right *sort* of answer (with appropriate random choice among nearby values); the game does not require exact replication of every physical detail.

(8) **Argument from informality of behaviour**: It is not possible to produce a set of rules covering every conceivable set of circumstances for a man; therefore men cannot be machines. Reply: distinguish "rules of conduct" (conscious precepts) from "laws of behaviour" (scientific laws governing the body). The argument shows the undistributed middle. We may be machines governed by (as yet undiscovered) laws of behaviour; the fact that we cannot yet state complete rules does not prove we are not machines. A small 1,000-unit storage programme on the Manchester machine already produces behaviour from which the programme cannot easily be recovered by observation.

(9) **Argument from extrasensory perception**: Statistical evidence (especially for telepathy) is overwhelming and would allow a telepathic man to beat a machine in the game. Reply: if telepathy is admitted the test must be tightened (place competitors in a "telepathy-proof room"). The situation becomes analogous to the interrogator talking to himself while one competitor listens at the wall.

Positive evidence and programme: Turing offers no fully convincing positive arguments but "recitations tending to produce belief." Return to Lady Lovelace: ideas "injected" into a subcritical mind produce less than one idea in reply; supercritical minds generate whole theories. Human minds are mostly subcritical; some are supercritical. Can a machine be made supercritical? The "skin of an onion" analogy: stripping mechanical layers may leave only mechanism. The real support will be running the experiment at century's end, but steps now: the problem is mainly programming. Storage estimates for brain vary 10^10–10^15 binary digits; Turing inclines low and believes ~10^9 suffices for the game (at least vs blind interrogator). Electronics already ~1000x faster than nerves → margin. Strategy: do not try to programme an adult mind directly; programme a child machine (little mechanism, "blank sheets") and subject it to an appropriate education. The child machine + education process are tightly linked. Analogy to evolution: child-machine structure = hereditary material; changes = mutations; natural selection = judgment of experimenter (faster and non-random). Simple child machines can use punishments/rewards; "unemotional" channels (symbolic language) greatly reduce the number needed. Imperatives ("Do your homework now") can be built into logical systems with suitable safeguards against type fallacies. Random elements are useful for search (as in evolution). "We may hope that machines will eventually compete with men in all purely intellectual fields." Best domains to start: abstract (chess) or full sensory + language? Both should be tried. "We can only see a short distance ahead, but we can see plenty there that needs to be done."

## Key Claims / Positions

- The Imitation Game is a satisfactory and relatively unambiguous substitute for "Can machines think?"; it focuses on intellectual capacities while neutralizing irrelevant physical and "display" advantages.

- Digital computers are discrete-state universal machines: with adequate storage and speed, a single digital computer suitably programmed can mimic any other discrete-state machine (including, potentially, the human "computer").

- Practical prediction (circa 2000): 10^9 storage + programming advances suffice for a machine to play the imitation game at a level where interrogators are correct <70% of the time after 5 minutes.

- Nine classic objections can be answered or neutralized without abandoning the game as test; the consciousness and "originate anything" objections are the most persistent but lead toward solipsism or demonstrably false assumptions about surprise and consequence-drawing.

- The productive research direction is "learning machines": build child machines with minimal built-in mechanism and educate them (evolution analogy; random element; punishments/rewards plus symbolic channels; imperatives in the system).

## Contradictions / Open Questions

- > [!warning] The Argument from Consciousness (Jefferson) directly tensions with any purely behavioral/functional criterion. Turing concedes there is "something of a paradox connected with any attempt to localise" consciousness and that the extreme view leads to solipsism, yet argues the game (or viva) is the practical standard we already use. Links to [[Thinkers/Descartes]] (res cogitans, clear and distinct ideas, mind-body union) and [[Concepts/Identity and Diversity - Personal Identity (Locke)]] (consciousness as the criterion that makes "the same thinking thing" the same person over time). Later philosophy of mind (qualia, inverted spectra, Chinese Room) continues this exact line.

- Lady Lovelace's "no pretensions to originate anything" vs. Turing's defense via surprise, self-modification, and learning: ancestor to all modern debates on whether LLMs/AI systems generate novel content or merely remix training data. See [[Thinkers/Garry Kasparov]] (Deep Blue matches and *Deep Thinking*: "where machine intelligence ends and human creativity begins") and the MasterClass collection's "human creativity vs machines" theme.

- Mathematical limits (Gödel/Turing) on any particular discrete machine vs. human intellect: Turing notes the lack of proof that humans escape analogous limits on the relevant questions. Still open; relevant to whether "true AGI" requires going beyond classical computation.

- Informality of behaviour and the possibility of complete "laws of behaviour": Turing's Manchester-machine reverse-engineering challenge prefigures modern questions about interpretability and whether black-box models can be fully understood.

- ESP: Turing takes the then-statistical case seriously and proposes concrete test modifications. Largely set aside in later AI but illustrates his willingness to adjust the criterion in light of anomalous evidence.

## Sources

- Primary: `raw/Computing Machinery and Intelligence - Alan Turing.txt` (complete 1950 *Mind* paper, sections 1–7 including the nine objections and closing programme for learning machines).

## Related

- [[Thinkers/Alan Turing]] (new entity page)
- [[Concepts/Imitation Game (Turing)]], [[Concepts/Universal Machine (Turing)]], [[Concepts/Discrete-State Machine (Turing)]], [[Concepts/Learning Machines (Turing)]], [[Concepts/Lady Lovelace's Objection]], [[Concepts/Argument from Consciousness (Jefferson)]]
- [[Thinkers/Garry Kasparov]] (Deep Blue 1997 as historical realization of the imitation-game challenge; reflections on the boundary between machine calculation and human creativity/judgment)
- [[Sources/MasterClass Collection - 2026]] (recurring "human creativity vs machines" thread across lessons)
- [[Thinkers/Descartes]] (mind-body dualism and the nature of thinking substance challenged by a physical, discrete-state, educable machine account)
- [[Concepts/Identity and Diversity - Personal Identity (Locke)]] (Locke's use of consciousness as personal-identity criterion; Turing's game tests observable functional equivalence without direct access to inner consciousness)
- [[Sources/The Problems of Philosophy - Bertrand Russell (1912)]] and [[Sources/A History of Western Philosophy - Bertrand Russell (1945)]] (Russell's sense-data, acquaintance, and logical-analysis programme as 20th-c. analytic context; Turing operates in the same broad empiricist/analytic milieu)
- Modern vault AI sources: [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]], [[Sources/Daily Advanced AI Tips - 2026-06-02]], [[Sources/Daily Advanced AI Tips - 2026-06-03]], [[Sources/Claude AI Advanced User Guide - 2026]] (contemporary systems as partial fulfillments and extensions of Turing's 1950 programme and research agenda)

*Source-summary created 2026-06-04 during ingest of the Turing primary text (source-summary + thinker + 6 concepts; index + log + cross-links + SCHEMA leg transition completed same session). This paper is the canonical origin point for the operational study of machine intelligence and supplies the Imitation Game criterion plus the learning-machine agenda that initiates the vault's AI & Cognitive Science leg.*

---

*We can only see a short distance ahead, but we can see plenty there that needs to be done.* (A. M. Turing, final sentence of the paper)
