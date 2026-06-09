---
title: "Reasoning Scaffolds"
type: concept
greek: ""
schools: []
domains: []
source_count: 1
created: 2026-06-03
updated: 2026-06-03
tags: [prompting, reasoning, ai-best-practices, 2026]
sources: ["AI_Tips_Chat_Export_June_2_2026.docx"]
---

# Reasoning Scaffolds

> Structured techniques that force or encourage LLMs to externalize and organize their thinking process (step-by-step, branching, self-evaluation) instead of jumping straight to a final answer.

## Summary

Even powerful 2026 models benefit enormously from explicit reasoning scaffolds. These reduce hallucinations and improve quality on complex tasks.

Highlighted in [[Daily Advanced AI Tips - 2026-06-02]]:

- **Chain of Thought (CoT)**: Always instruct "reason step by step" for anything non-trivial.
- **Tree of Thoughts (ToT)**: Explore multiple distinct approaches in parallel, evaluate them against explicit criteria, then select + refine the winner.
- **Self-Consistency + Self-Critique**: After producing an answer, have the model score it (e.g. 1-10 on accuracy, completeness, originality), then revise to improve the weakest dimensions.

## Why These Work

Models are essentially doing compressed simulation of thought. Externalizing the process:
- Makes errors visible (to the model and to you).
- Allows intervention/correction at intermediate steps.
- Turns one forward pass into something closer to search / iteration.

## Examples in Use

- Complex analysis or synthesis: "First list the key facts from the sources. Then identify tensions. Then propose 3 possible framings. Evaluate each. Pick the strongest and flesh it out."
- Code or wiki edits: "Before editing, diagnose the current state, list options, critique each, then apply the best with explanation."
- This vault's own operations (ingest/query): Grok is instructed (via [[GROK]]) to always read index first, use tools for grounding, update multiple pages consistently, then log exactly what was done. This is a form of scaffolded agentic reasoning.

## Related Techniques

- Self-Consistency decoding (sampling multiple paths, majority vote).
- Reflexion / self-refine loops.
- Constitutional AI / rubric-driven critique (see also rubrics section of the tips source).

## Related Pages

- [[Context Engineering]]
- [[Agentic Workflows]]
- [[Daily Advanced AI Tips - 2026-06-02]]
- [[LLM Wiki]] (the maintenance process here uses scaffolds)

## Contradictions / Open Questions

None identified in current sources. Future guides may introduce new scaffolds or rate their effectiveness differently.

## Sources

- As listed in frontmatter.

## Status

Created during initial source ingest. Future pages and operations can reference specific scaffold patterns used.
