---
title: "Four Assumptions of Artificial Reason (Dreyfus)"
type: concept
domains: [ai, philosophy-of-mind, epistemology, metaphysics]
created: "2026-08-12"
updated: "2026-08-12"
sources: ["What Computers Still Can't Do - Hubert Dreyfus.md"]
tags: [dreyfus, four-assumptions, biological, psychological, epistemological, ontological, gofai]
---

# Four Assumptions of Artificial Reason (Dreyfus)
> Optimism in classical AI is not licensed by results. It is licensed by four hypotheses treated as axioms: that the brain is digital, that the mind follows formal rules, that all knowledge can be formalized, and that the world is a set of independent facts.

## Summary

[[Thinkers/Hubert Dreyfus]] argues that after the 1957–67 stall, workers in Cognitive Simulation and AI remained "unqualifiedly optimistic" because they took human intelligence to be information processing of the same elementary kind as a digital computer's. That conviction unpacks into four assumptions, "seldom articulated and never called into question" (*What Computers Still Can't Do*, p. 156):

1. **Biological.** "On some level of operation — usually supposed to be that of the neurons — the brain processes information in discrete operations by way of some biological equivalent of on/off switches."
2. **Psychological.** "The mind can be viewed as a device operating on bits of information according to formal rules."
3. **Epistemological.** "All knowledge can be formalized" — even if humans do not *follow* the rules, intelligent behavior is *formalizable* in terms of rules a machine can use to reproduce it. Two sub-claims: (a) all nonarbitrary behavior can be formalized; (b) the formalism can reproduce the behavior.
4. **Ontological.** "What there is, is a set of facts each logically independent of all the others." Everything essential to intelligent behavior is understandable as determinate independent elements. Computer data "must be discrete, explicit, and determinate."

The first is empirical. The last three are philosophical and generate conceptual difficulties.

**Against the biological assumption.** Even if the brain were digital, that would not help heuristic AI: it might be a randomly wired net (perceptrons), and a simulated net is "in no sense a heuristic program." Digital vs analogue is a logical distinction, not a hardware one; all-or-none spikes do not entail digital processing if rate, volleys, or fields matter. von Neumann: the evidence "rather *tends to indicate that the human nervous system uses different principles and procedures*." Insofar as biology is relevant, it counts against the computer-brain equation.

**Against the psychological assumption.** Whether the *brain* is digital is for neurophysiology. Whether the *mind* is, is a level of discourse that "has to be introduced." Cognitive Simulation equivocates on "information" (ordinary meaning vs Shannon bits — and Shannon had bracketed semantics). Protocol-to-trace matching is nongeneral and circular: parsimony *postulates* discrete elementary processes, then the same programs are cited as confirming them ("the hypothesis *produces* the evidence by which it is later confirmed"). Miller et al. define a complete description of behavior as a set of instructions (a Plan = a program) — Plato's *Euthyphro* demand restated. The leftover human capacities — zeroing-in, essential/inessential discrimination, and (named at p. 206) fringe consciousness, ambiguity tolerance, and perspicuous grouping — look programmable only if one already assumes the computer-mind thesis.

**Against the epistemological assumption.** The planets are not solving differential equations. Lawful behavior *according to* a rule is not rule-following, and a digital simulation of the nervous system's physics would process *different* information (properties of the analogue), not mental-level facts about the world. Chomsky formalizes *competence*; AI needs *performance*. Odd but intelligible uses ("The idea is in the pen") and unnoticed errors are neither arbitrary nor strictly rulelike; machines have only those two options. Metarules for breaking rules regress. Wittgenstein: complete rule-theory needs rules for applying rules; humans stop when interpretation is "simply evident"; computers stop only at "context-free, completely determinate data."

**Against the ontological assumption.** "There is no reason to suppose that such data about the human world are available to the computer and several reasons to suggest that no such data exist." A chair is not a set of isolable facts; the implicit situation makes facts explicit. The world is not a universe of context-free atoms (the line from Plato's simples through Leibniz, Hume, Russell, and the *Tractatus*). McCarthy's identification of *situation* with a phase-space point confuses a token physical state with a type of human situation ("being at home"). Context is antinomic: relevant facts are situation-relative; recognizing the situation needs a broader context — infinite regress, or an unprogrammable ultimate context ([[Concepts/Forms of Life (Wittgenstein)|forms of life]]). Escape: deny the fact/situation split. Facts exist only as situationally relevant; intelligence is already *in* a situation.

**Part II verdict.** The biological assumption "no longer fits the evidence." The other three lead to conceptual difficulties. Without the four axioms, the decade of stagnation is "grounds for pessimism," and the failures "may reveal the limitations of technology" as the culmination of Western metaphysics (Heidegger: cybernetics as the end of *rechnende Denken*).

## Key Claims / Positions

### How Different Thinkers Use This

- **[[Thinkers/Hubert Dreyfus]]**: the four are hypotheses, not axioms. Drop them and GOFAI's record is disconfirmation, not delay.
- **[[Thinkers/Marvin Minsky]]** / Newell–Simon: the psychological and ontological assumptions are working science — "general-purpose symbol-manipulating devices" executing "elementary information processes functionally quite like those executed by the brain."
- **[[Thinkers/Alan Turing]]**: Dreyfus reads the discrete-state machine as making the ontological assumption hardware. Turing's "laws of behaviour" vs "rules of conduct" distinction is used *against* the epistemological assumption (lawful ≠ programmable-as-rules).
- **[[Thinkers/John Searle]]**: shares the rejection of the psychological assumption (thinking is not formal symbol manipulation) but replaces it with biological naturalism, not with being-in-the-world. Searle would keep a version of the biological assumption (the brain's specific causal powers) that Dreyfus treats as the wrong level.
- **[[Thinkers/Wittgenstein]]**: *Tractatus* as the "purest formulation" of the ontological assumption; later work as its self-critique (no strict-rule use; forms of life as what has to be accepted).
- **[[Thinkers/Thomas Kuhn]]**: used against CS methodology (exceptions treated as five special cases rather than anomalies that threaten a paradigm) and, in Part III, as evidence that without a paradigm all facts are "equally relevant."

## Contradictions / Open Questions

- > [!warning] If connectionist or predictive-processing models drop the psychological assumption (no explicit rules) but keep a version of the ontological one (the world as statistically regular features), has Dreyfus's quartet been answered or only relocated? See [[Contradictions/Dreyfus vs Computationalism - Skilled Coping vs Formal Rules]].
- The biological assumption's failure is dated to 1960s–70s neurophysiology. Later computational neuroscience can be read either as vindicating mixed analogue-digital brains (Dreyfus's side) or as vindicating information-processing at another grain (the CS side).

## Sources

- [[Sources/What Computers Still Can't Do - Hubert Dreyfus (1992)]]

## Related

- [[Thinkers/Hubert Dreyfus]]
- [[Concepts/GOFAI as Degenerating Research Program (Dreyfus)]]
- [[Concepts/Commonsense Knowledge Problem (Dreyfus)]]
- [[Concepts/Embodied Intelligence and the Role of the Body (Dreyfus)]]
- [[Concepts/Forms of Life (Wittgenstein)]]
- [[Concepts/Rule-Following (Wittgenstein)]]
- [[Contradictions/Dreyfus vs Computationalism - Skilled Coping vs Formal Rules]]
