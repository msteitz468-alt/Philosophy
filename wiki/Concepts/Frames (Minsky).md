---
title: "Frames (Minsky)"
type: concept
domains: [ai, cognitive-science, philosophy-of-mind, knowledge-representation]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["Society of Mind - Marvin Minsky.txt"]
tags: [minsky, frames, uniframes, knowledge-representation, defaults, learning, society-of-mind]
---

# Frames (Minsky)

> Minsky's (and AI's) fundamental knowledge-representation structure: a "frame" is a stereotyped, data-structure-like description of a situation, object, or action with slots (terminals) that can hold defaults, expectations, attached procedures ("what to do if..."), and relations to other frames. Frames allow rapid recognition, inference, and action by filling in missing details from prior experience rather than deriving everything from scratch. "Uniframes" are compact versions that cover multiple instances by enforcing key relations, preventing bad ones, and tolerating irrelevant variation.

## Summary

From the blocks example: after seeing several structures, the child arrives at a description like "a top supported by two standing blocks that do not touch." This is a uniframe — one description that applies to different concrete arrangements. It *enforces* support relations, *prevents* the standing blocks from touching, and shows *tolerance* for the top's exact shape or material.

Frames are not rigid templates; they support reformulation, trans-framing (bridging structure and function), and exception-handling. They embody the principle that "most differences are redundant" or accidental for a given purpose — we should not store or notice too much.

Minsky introduced frames in AI (1974 paper) as an alternative or complement to logic and semantic nets; the 1986 book integrates them into the society-of-mind story as one important kind of agent-society organization for knowledge.

## Key Claims

- Much of perception, understanding, and action consists of matching current input to stored frames and filling/defaulting the slots.
- Learning involves building, debugging, merging, and reformulating frames (and uniframes) rather than just accumulating facts.
- We need many different kinds of learning strategies; no single "generalizer" will do.
- Frames make knowledge *usable* by keeping expectations and procedures close to the descriptions.

## Relation to Vault

- **Dennett**: Frames are one of the "drafts" or content structures that participate in the ongoing editorial processes; they are revised, overwritten, or fused as new information arrives.
- **Hofstadter**: Frames are isomorphisms — structure-preserving mappings from past experience to present situations. Uniframes are the recognition of common patterns across levels.
- **Turing / learning**: Frames (and the administrative machinery around them) are part of what gets installed in child machines through experience.

## Sources

- [[Sources/The Society of Mind - Marvin Minsky (1986)]]

## Related

- [[Concepts/Society of Mind (Minsky)]]
- [[Concepts/Mental Agents (Minsky)]]
- [[Concepts/K-lines (Minsky)]]
- [[Thinkers/Marvin Minsky]]
- [[Concepts/Formal Systems and Isomorphism (Hofstadter)]]

*Concept page created 2026-06-04. Minsky's (and AI's) classic knowledge structure for stereotyped situations with defaults and attached procedures.*
