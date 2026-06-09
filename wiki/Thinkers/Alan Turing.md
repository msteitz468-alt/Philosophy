---
title: "Alan Turing"
type: thinker
era: "20th century"
schools: [Computationalism, Functionalism, Philosophy of Computation]
domains: [epistemology, philosophy-of-mind, computation, ai, history-of-science]
created: "2026-06-04"
updated: "2026-06-04"
source_count: 1
tags: [turing, imitation-game, turing-test, universal-machine, digital-computers, learning-machines, philosophy-of-mind, ai, computation, 1950, babbage]
sources: ["Computing Machinery and Intelligence - Alan Turing.txt", "Godel's Proof - Ernest Nagel.txt", "Superintelligence_ Paths, Dangers, Strateg - Nick Bostrom.txt", "Artificial Intelligence - Melanie Mitchell.txt"]
---

# Alan Turing

> Alan Mathison Turing (1912–1954), British mathematician, logician, cryptanalyst, and computer scientist. In the 1950 paper "Computing Machinery and Intelligence" (Mind) he reformulated the question "Can machines think?" as the Imitation Game (the operational test now known as the Turing Test), proved that digital computers are universal machines capable of mimicking any discrete-state process given adequate storage and programming, predicted near-term practical success, rebutted nine classic objections (including the consciousness and "no originality" arguments), and outlined a concrete research programme for building "learning machines" by educating child programmes rather than hand-coding adult minds. Foundational text for the philosophy of computation, AI, and cognitive science.

## Profile

- **Dates / life**: 1912–1954. Key wartime work at Bletchley Park on Enigma cryptanalysis (contributed to design of the Bombe, statistical methods, early computing ideas). Post-war: designed the Automatic Computing Engine (ACE) at NPL; worked on early Manchester computers; wrote the 1950 *Mind* paper; developed interests in mathematical biology (morphogenesis) and the chemical basis of pattern formation. Prosecuted in 1952 for homosexual acts, underwent chemical castration; died by cyanide poisoning in 1954 (official inquest suicide; some debate). Received OBE for war work; elected FRS 1951.

- **Major works**: "On Computable Numbers, with an Application to the Entscheidungsproblem" (1936) — defined computable numbers via Turing machines and proved the halting problem undecidable; contributions to Enigma breaking and early computer design; "Computing Machinery and Intelligence" (1950) — the primary source here; "The Chemical Basis of Morphogenesis" (1952).

- **In the vault**: Primary source [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]]. The canonical origin point for the operational study of machine intelligence and the learning-machine research agenda. Bridges the vault's completed Philosophy of Science / Epistemology leg (Ayer–Popper–Kuhn–Quine–Feyerabend–Hacking) into the planned AI & Cognitive Science leg. Cross-references to Kasparov (Deep Blue as historical test of the imitation-game idea), Descartes (mind-body), Locke (personal identity via consciousness), and modern vault AI sources.

## Core Positions (from "Computing Machinery and Intelligence")

- **Imitation Game as replacement question**: The original "Can machines think?" is too vague and risks a statistical Gallup-poll definition. Replace it with a game that draws a "fairly sharp line between the physical and the intellectual capacities of a man." Machine takes the part of the man; success = interrogator fooled at rates comparable to the man/woman version. Text-only (teleprinter) to eliminate tone/appearance cues.

- **Digital computers as the machines in question**: Store (information + instruction table), executive unit (operations), control (obeys instructions, enables branching/loops). "Programming" = supplying the appropriate instruction table. Not limited to current hardware; "imaginable computers."

- **Universality**: Digital computers are universal machines. Any discrete-state machine (states sufficiently distinct; next state determined by current state + input) can be mimicked by a digital computer with sufficient storage capacity and speed, suitably programmed. Babbage's Analytical Engine (mechanical, never completed) already contained the essential ideas; use of electricity is theoretically superficial.

- **Prediction**: In ~50 years (i.e., ~2000), computers with ~10^9 storage can be programmed to play the imitation game so that "an average interrogator will not have more than 70 per cent chance of making the right identification after five minutes of questioning." By century's end, educated opinion will accept speaking of "machines thinking" without contradiction. Storage of 10^7 already practicable; 10^9 sufficient (compare Encyclopædia Britannica ~2×10^9 characters).

- **Nine objections addressed** (see source-summary for details):
  1. Theological (souls): limits divine power arbitrarily.
  2. Heads in the sand: not a serious argument.
  3. Mathematical (Gödel et al.): limits shown for particular machines, not proven for human intellect; humans also err. The clearest exposition of the underlying Gödel 1931 results is [[Sources/Gödel’s Proof - Ernest Nagel and James R. Newman (1958)]] (with the new dedicated [[Thinkers/Kurt Gödel]] page); Turing's rebuttal aligns with Hofstadter's later reading.
  4. Consciousness (Jefferson): leads to solipsism; practical tests (viva voce) already accept understanding without feeling the inner life.
  5. Various disabilities: mostly induction from today's limited machines; machines can simulate "errors," be their own subject matter, surprise us.
  6. Lady Lovelace ("no pretensions to originate"): evidence at the time was limited; machines do surprise; the "all consequences seen at once" assumption is false.
  7. Continuity of nervous system: game conditions do not allow the interrogator to exploit the difference; continuous machines (e.g., differential analyser) can still be mimicked sufficiently.
  8. Informality of behaviour: confuses conscious rules of conduct with scientific laws of behaviour; small programmes already produce opaque behaviour.
  9. Extrasensory perception: if real, tighten the test with a telepathy-proof room.

- **Learning machines as the way forward**: Do not attempt to programme an adult mind directly. Programme a "child machine" (minimal mechanism, "blank sheets") and educate it. Analogy to evolution: hereditary material = machine structure; mutation = changes to the child machine; selection = experimenter judgment (faster and directed, not purely random). Include random element for search. Punishments/rewards work but "unemotional" symbolic channels (language) are far more efficient. Imperatives can be encoded in logical systems. "We may hope that machines will eventually compete with men in all purely intellectual fields."

## Influence, Reception, and Contrasts in the Vault

- **With [[Thinkers/Garry Kasparov]]**: Kasparov's Deep Blue matches (1996 win, 1997 loss) and *Deep Thinking* are direct historical experiments in the imitation-game space Turing defined. Kasparov reflects on where "machine intelligence ends and human creativity begins" — exactly the consciousness/originality/disability objections Turing addressed. Chess as laboratory echoes Turing's specimen questions.

- **With [[Thinkers/Descartes]]**: Turing offers a thoroughgoing mechanistic, physical, discrete-state account of thought that directly challenges Cartesian dualism (res cogitans vs. res extensa) and the requirement of a non-mechanical soul or "ghost in the machine." Yet both are foundational for modern philosophy of mind.

- **With [[Thinkers/Locke]] and personal identity**: Locke's "consciousness makes personal identity" (same thinking thing) is tested behaviorally by the imitation game; the game asks whether we can attribute the same "thinking" to a machine on the basis of its outputs without direct access to inner consciousness.

- **With [[Thinkers/Bertrand Russell]]**: Operates in the same early analytic/empiricist milieu (Russell's logical analysis, sense-data, limits of knowledge). Turing's focus on what is *computable* and *programmable* gives a precise technical realization to questions of method and knowledge that Russell surveyed historically.

- **With [[Thinkers/Douglas Hofstadter]]**: Hofstadter's *GEB* (1979) reads Turing's halting problem (1936) through the lens of Gödelian incompleteness — both are facets of the same fundamental self-referential limit of formal systems, and both are, for Hofstadter, structural mirrors of the strange loop that constitutes mind. Turing's rebuttal of the mathematical objection (Gödel et al.) in the 1950 paper explicitly parallels Hofstadter's rebuttal of the Lucas-Penrose anti-AI argument: incompleteness shows limits of *particular* formal systems, not of all possible machine behavior. Hofstadter is the strongest intellectual ally of the computationalist reading of Turing in the vault. The shared technical foundation is the Nagel/Newman exposition [[Sources/Gödel’s Proof - Ernest Nagel and James R. Newman (1958)]] (Hofstadter's own foreword records the personal link). See [[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]] and new [[Thinkers/Kurt Gödel]].

- **With [[Thinkers/Daniel Dennett]]** (strong alliance, later philosophical support): Dennett's *Consciousness Explained* (1991) defends the spirit of the Imitation Game framework and the computationalist program Turing inaugurated. Dennett's Systems Reply to Searle's Chinese Room directly rebuts Searle's attempt to refute Turing-style functionalism: it is illegitimate to imagine only a toy system and then declare understanding absent; the full complexity of a Turing-test-passing program cannot be dismissed on those grounds. Dennett also provides the evolutionary story (Joycean machine, Baldwin Effect, memes) for how human minds came to be the kind of things that could — in principle — be implemented in other substrates. See [[Thinkers/Daniel Dennett]] and [[Sources/Consciousness Explained - Daniel C. Dennett (1991)]].

- **With [[Thinkers/Judea Pearl]]** (on AI criteria, later challenge): Pearl's "mini-Turing test" (*The Book of Why*, 2018) proposes that the real criterion for human-level AI is not behavioral imitation (rung 1) but the ability to answer causal and counterfactual questions (rungs 2–3). Pearl argues that Turing's imitation game is a rung-1 criterion — a machine can pass it by sophisticated pattern-matching without genuine causal reasoning. Pearl's alternative: "Can the machine reason about the consequences of its own actions?" This is a reframing, not a refutation — Turing's 1950 paper predates the rung-1/2/3 distinction, and Turing himself acknowledged that behavioral criteria are proxies for underlying intelligence. See [[Thinkers/Judea Pearl]], [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]], and [[Concepts/Ladder of Causation (Pearl)]].

- **With [[Thinkers/Norbert Wiener]]**: Wiener's *The Human Use of Human Beings* (1950) and Turing's "Computing Machinery and Intelligence" (1950) are published in the same year and orbit the same questions about machine intelligence. Both endorse learning machines over rigid, pre-programmed systems; both anticipate modern AI. Turing focuses on the behavioral criterion (imitation game), universality of digital computers, and the child-machine learning program. Wiener focuses on feedback physiology, the social impact of automation, and the alignment danger. Wiener explicitly advocates Turing-style learning (modifiable "preference" vs. rigid "constraint") but adds the social/political analysis Turing omits — including the first formal statement of what we now call the alignment problem (Monkey's Paw / Bottled Djinnee). The two works are complementary: computation (Turing) + control and communication (Wiener) = the digital-cybernetic revolution. See [[Thinkers/Norbert Wiener]] and [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]].

- **With philosophy-of-science cluster (Popper, Kuhn, etc.)**: The 1950 paper sits chronologically between the logical-positivist moment (Ayer) and the post-positivist reactions. It is itself a bold conjecture about future machine performance, offered with explicit fallibilism ("conjectures are of great importance") and a clear criterion that could in principle be refuted by experiment.

- **Modern AI sources in vault**: The 2026 Grok/Claude/Gemini tips, tutorials, and agentic workflows are partial, practical fulfillments and extensions of Turing's 1950 programme (programming/education of systems, context as "child machine" state, tool use as intervention, reasoning scaffolds as instruction tables). The vault's own maintenance (ingest = education of the wiki "child") is meta-application.

## Relevance to the Vault and Meta

- **Foundational for the AI & Cognitive Science leg**: This is the single text that first posed the question in a form that could be engineered and tested. Every subsequent discussion of "machine intelligence," LLMs, agentic systems, and the boundary with human creativity stands in its shadow.

- **Wiki / agentic as learning machine**: The vault itself can be read as a Turing child machine: minimal initial structure (SCHEMA + seed pages), educated by successive ingests (experience + "instruction tables" in the form of targeted edits and cross-links), with random/exploratory elements and experimenter (human + agent) judgment selecting what survives and grows. Ingest = supervised education; lint = self-critique; index = compressed memory.

- **"If you can programme it to play the game..."**: Practical criterion for the vault: focus on what the system (Grok + tools + wiki) can actually *do* in sustained interaction rather than on unverifiable inner states or full "understanding."

- **Random element and surprise**: Turing's defense of randomness and his own frequent surprises from machines license exploratory, non-deterministic tool use and the value of being genuinely surprised by outputs.

## Related

- [[Sources/Computing Machinery and Intelligence - Alan Turing (1950)]] (primary)
- [[Sources/Gödel’s Proof - Ernest Nagel and James R. Newman (1958)]] (technical foundation for the Gödel-based mathematical objection that Turing directly rebuts)
- [[Sources/Superintelligence - Nick Bostrom (2014)]] (modern analysis of post-threshold dynamics, control problem, and risks building on Turing's vision)
- [[Sources/Artificial Intelligence - Melanie Mitchell (2019)]] (Turing test chapter and assessment of behavioral success vs. understanding in modern AI systems)
- [[Sources/Artificial Intelligence - Melanie Mitchell (2019)]] (dedicated discussion of the Turing test as a measure of intelligence; Mitchell explores its legacy, variants (e.g., in Watson, translation, games), and limitations — behavioral success on narrow tasks does not entail the flexible understanding or common sense humans use; updates Turing's vision with post-DL reality check)
- [[Concepts/Imitation Game (Turing)]], [[Concepts/Universal Machine (Turing)]], [[Concepts/Discrete-State Machine (Turing)]], [[Concepts/Learning Machines (Turing)]], [[Concepts/Lady Lovelace's Objection]], [[Concepts/Argument from Consciousness (Jefferson)]]
- [[Thinkers/Garry Kasparov]] (Deep Blue as 20th-c. experiment in the imitation game; human vs. machine creativity boundary)
- [[Sources/MasterClass Collection - 2026]] (human creativity vs machines across disciplines)
- [[Thinkers/Descartes]], [[Thinkers/Locke]], [[Thinkers/Bertrand Russell]]
- [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]], daily AI tips sources, [[Sources/Claude AI Advanced User Guide - 2026]] (contemporary systems as realizations of the programme)
- [[Contradictions/Popper vs Kuhn - Falsification vs Paradigms]] (extended context: Turing's conjectural, experimental attitude toward machine intelligence)
- [[Thinkers/Douglas Hofstadter]] (halting problem as computational parallel to Gödel; both rebut Lucas-Penrose; Hofstadter as computationalist ally)
- [[Thinkers/Kurt Gödel]] (the 1931 results behind the "mathematical objection"; clearest exposition in the Nagel/Newman source that Turing engages)
- [[Thinkers/Ernest Nagel]], [[Thinkers/James R. Newman]] (authors of the primary technical popularization of Gödel that grounds the objection and the Hofstadter response)
- [[Thinkers/Daniel Dennett]] (Systems Reply as direct defense of Turing-style functionalism against Searle; evolutionary account of how minds arose; Joycean machine as development of the learning-machine programme)
- [[Thinkers/Judea Pearl]] (mini-Turing test proposes causal reasoning as AI criterion in place of behavioral imitation; rung-1 critique of deep learning applies to Turing-style behavioral tests)
- [[Concepts/Ladder of Causation (Pearl)]], [[Contradictions/Pearl vs. Statistics Orthodoxy - Causation Purged and Recovered]]
- [[Contradictions/Hofstadter vs Searle - Strange Loops vs Chinese Room]] (the vault's main AI & Cognitive Science tension, with Turing's paper at the origin)
- [[Thinkers/Norbert Wiener]] (co-1950 AI founding; complementary frames — computation vs. control; Wiener adds social/alignment analysis Turing omits)
- [[Thinkers/Nick Bostrom]], [[Sources/Superintelligence - Nick Bostrom (2014)]] (detailed strategic analysis of what happens after Turing's predicted threshold: intelligence explosion, orthogonality of goals, control problem, existential stakes)
- [[Concepts/Alignment Problem - Sorcerer's Apprentice (Wiener)]] (Wiener's parallel 1950 concern about learning machines)

*Thinker page created 2026-06-04 during ingest of the 1950 Mind paper (full cluster + index + log + cross-links completed 2026-06-04). The vault's primary source for the Imitation Game criterion, universality of digital computers, and the learning-machine research agenda that initiates the AI & Cognitive Science leg.*

---

*It is not possible to produce a set of rules purporting to describe what a man should do in every conceivable set of circumstances.* (Turing, §8, paraphrased in objection he then addresses)
