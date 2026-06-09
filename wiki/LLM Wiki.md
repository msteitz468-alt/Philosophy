---
title: "LLM Wiki"
type: concept
greek: ""
schools: []
domains: []
source_count: 10
created: 2026-06-03
updated: 2026-06-04
tags: [pkm, llm, meta, classical-philosophy, patristics, memory, grace]
sources: ["AI_Tips_Chat_Export_June_2_2026.docx", "Claude_AI_Advanced_User_Guide.docx", "Grok_4.3_Tutorial_Detailed_Notes.docx", "Plato - Timaeus & Critias (Oxford, 2008).docx", "Reality Transurfing I - V.pdf", "Plato - Republic (Cambridge, 2000).pdf", "daily_advanced_ai_tips_june_3_2026.md", "CPCU 552 Commercial Property Insurance - Study Materials", "MasterClass Collection - 2026", "Confessions - Augustine.txt"]
---

# LLM Wiki

> A pattern for building personal knowledge bases using LLMs as disciplined, long-term maintainers.

This page describes the core idea implemented by this very vault (GrokVault).

## Summary

Instead of one-shot RAG over raw documents, an LLM incrementally compiles knowledge into a persistent, interlinked wiki of markdown files. Every new source is integrated (not just indexed). Queries benefit from the already-synthesized state. Valuable query results are filed back into the wiki.

The LLM does the heavy bookkeeping (cross-references, updates, consistency). The human curates sources and asks good questions.

## Key Layers

- **Raw sources** (`raw/` in this vault): Immutable inputs. Articles, papers, notes, images.
- **The wiki** (`wiki/`): LLM-owned living documents — entity pages, concepts, source summaries, analyses, etc.
- **The schema** (`GROK.md` at vault root): This vault's detailed instructions for how Grok should ingest, query, lint, format pages, use tools, and evolve the system.

See also:
- [[Overview]]
- [[index]]
- [[GROK]]

Recent expansions (e.g., Confessions - Augustine) illustrate the pattern: personal "examined life" / memory work (Book X) and "pilgrimage" / compounding toward rest parallel the wiki's honest ingest, cross-referencing, and integration of classical sources into unified vision. Grace/nature motif (Aquinas) maps to human curation + LLM maintenance perfecting the "nature" of raw files and prior pages. Memory as deliberate interior search models context engineering and persistent KB as externalized self-knowledge.
- [[log]]
- [[GROK]] (vault root)

## Why It Compounds

Maintenance cost approaches zero. Cross-links, contradictions, and syntheses are kept current automatically. Over time the wiki becomes a high-fidelity map of everything you've read and thought about in the domain.

## Related Concepts

- Memex (Vannevar Bush, 1945)
- Zettelkasten / Evergreen notes (but LLM-automated)
- Personal knowledge management (PKM) systems
- Fan wikis and comprehensive world-building wikis

## Status in This Vault

This concept page was created during initial bootstrap as a seed. It will be expanded with more detail, examples, and links as sources are ingested and the wiki evolves.

### First Source: Daily Advanced AI Tips (2026-06-02)

The first ingested source ([[Sources/Daily Advanced AI Tips - 2026-06-02]]) is meta-relevant:
- It describes exactly the prompting, context, agentic, and verification techniques used by Grok when maintaining this vault.
- "Skills" for persistent custom expertise (GROK.md + the wiki as always-on context is a concrete example).
- Grok Build / Composer capabilities (agentic tool use, long-running structured work, MCP) power the file operations, synthesis, and edits performed during ingest.
- Many of the recommended scaffolds (context engineering first, reasoning, sub-agents, self-critique, rubrics) are embodied in the workflows documented in [[GROK]].

See also the new concept pages created alongside this source:
- [[Concepts/Context Engineering]]
- [[Concepts/Agentic Workflows]]
- [[Concepts/Reasoning Scaffolds]]
- [[Concepts/Cross-Model Routing]]

And the synthesis:
- [[Syntheses/Frontier AI Capabilities - June 2026]]

This source will be referenced by future "daily tips" ingests as the series evolves.

### Second Source: Claude AI Advanced User Guide (2026-05-31)

The [[Sources/Claude AI Advanced User Guide - 2026]] is a direct blueprint for advanced LLM-powered systems and has striking parallels to GrokVault:

- **Skills** described with `SKILL.md` (YAML frontmatter + body) + optional scripts/references/assets/ folders — *identical* to the structure in `~/.grok/skills/*/SKILL.md` and how [[GROK]] functions as the persistent schema/instructions for this agent.
- **Projects** as persistent knowledge + custom instructions workspaces — analogous to the wiki/ + [[GROK]] + index providing always-available curated context.
- **Artifacts** as produced, iterated, shareable interactive outputs — maps to the wiki pages, syntheses, and filed analyses we create and refine.
- **Claude Code** (agentic with tools/permissions/Plan Mode/parallel sub-agents/Skills integration/CLAUDE.md awareness) — mirrors how this Grok agent uses tools (read_file, grep, search_replace, run_terminal, todo_write) in structured ingest/query/lint loops, following the "plan" in [[GROK]].
- Explicit emphasis on verification loops, strong context curation, modular/reusable capabilities, and treating the LLM platform as configurable "infrastructure" / "AI OS".

Combined with the June 2 AI Tips source, these two documents (May 31 + June 2, 2026) provide a rich paired view of Claude capabilities and prompting/agentic best practices that directly inform and validate the LLM Wiki pattern, GROK.md conventions, and our use of sub-agents/tool-calling for knowledge base maintenance.

See also new/updated coverage in [[Concepts/Claude (Anthropic)]], [[Concepts/Agentic Workflows]], and potential future Concepts for "Claude Artifacts", "Claude Skills", "Claude Projects", "Claude Code".

### Third Source: Grok 4.3 Tutorial Detailed Notes (2026-05-11/31)

The [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]] (from a May 11 video tutorial) is perhaps the single highest-signal document yet for operating *this* Grok-powered system:

- Custom Instructions + Memory as foundation for "personal system" (our [[GROK]] + wiki/index/log as persistent context/memory exactly).
- Projects for persistent shared context (the wiki/ itself).
- Modes (Auto/Fast/Expert/Grok 4.3 Beta/Heavy) + mode discipline (we operate in Expert/agentic for maintenance).
- Native web + X search, file upload/analysis, code execution, structured outputs (all native tools here: web_search, x_*, read_file, run_terminal, etc.).
- Imagine/video generation + agent mode (matches our image_gen/edit/to-video/reference_to_video + agentic use).
- Voice + Tasks (scheduled background prompts; analogous to periodic lint or recurring source processing).
- Agent Roles prompting (Harper=research, Benjamin=logic, Lucas=critic, Grok=synthesis) + explicit agentic chains with handoffs/steps/outputs (our ingest is precisely such a chain: discover/read source → extract/integrate facts + flag contradictions → write/update pages + bookkeeping in index/log + verify).
- Three workflows (Research with gap-surfacing; Content with "pick a side"; Analysis with confidence flags) — directly embodied in how we process sources, synthesize, and health-check.
- Emphasis on *habit* over raw capability, and building explicit multi-step workflows.

This source (paired with the Claude Advanced User Guide) explains *why* the LLM Wiki pattern + disciplined [[GROK]]-driven agentic maintenance works so well, and gives concrete patterns to evolve it (more explicit role prompting in workflows, dedicated Concepts for Grok agent roles/modes/Tasks, using structured outputs more, etc.).

See also [[Concepts/Grok (xAI)]], [[Concepts/Grok Build]], [[GROK]], and the other AI sources for the 2026 ecosystem view.

### Later Source Example: Timaeus and Critias (Plato, Oxford 2008)
Ingest of [[Sources/Timaeus and Critias - Plato (Oxford, 2008)]] demonstrates the "Reading a book" use case from [[GROK]]: one source → source summary + entity page (Plato) + concept page (Atlantis) + updates to index/log/Overview. Builds dedicated pages for themes (cosmogony, demiurge/teleology, Atlantis myth as political allegory), cross-references, and notes potential links to other "models of reality" sources (e.g. Reality Transurfing once fully ingested). Shows how the pattern scales to entirely new domains (classical philosophy) while keeping everything interlinked and maintainable. Frontmatter sources list and [[LLM Wiki]] itself updated as part of bookkeeping.

### 2026-06-04 Batch Example: Professional Development + Craft Mastery (CPCU + MasterClass Collection)
Large batch ingest of ~70 new files demonstrated the pattern at scale across domains:
- **CPCU 552 Commercial Property series** (14 files: core + 7 modules on BPP/BIC/assessing needs/income losses/gaps/transit/tailoring/critical thinking + workbooks): new dedicated source summary page. Updated [[Concepts/CPCU Designation]], [[Mack Steitz]], [[Concepts/Alliant Insurance Services]], and career concepts (Book of Business, Prospecting Playbook). Shows "personal + professional development" use case — technical study directly feeds the promotion/sales playbook and risk consultant positioning.
- **MasterClass Collection 2026** (~55+ PDFs + BBQ notes): one synthesized collection page with full inventory, thematic clusters (storytelling, culinary craft, business/leadership/entrepreneurship, creative/performing arts, personal mastery, strategy/chess/poker/negotiation/sales), and cross-cutting lessons (lived-pain origin stories, "jump in" despite cost, values/profits not enemies, team + direct feedback + routines, behavioral persuasion science, deliberate practice + human creativity vs machines, precision craft). Created [[Thinkers/Garry Kasparov]] (Deep Blue/human-AI creativity boundary + strategy). Strong links to AI domain (Kasparov), career (Pink sales science + Schultz/Wintour/Blakely leadership + routines), and philosophy (storytelling as craft/myth).
- Daily AI Tips June 3 added as fresh meta source; updated Frontier synthesis and AI entities.
- 0B Gemini/NotebookLM placeholders re-confirmed empty (titles as signals only).
- Bookkeeping: new source pages, entity, collection synthesis, index refresh (stats + sections), Overview update, comprehensive log entry. Touched 10-20+ pages in one logical batch while preserving the "one source → 5-15+ integrated pages" discipline via thematic grouping.

This batch shows the wiki handling volume and domain jumps (insurance ed + broad craft/leadership library) without losing coherence, thanks to index-first orientation, explicit cross-links, and the collection-page pattern for large homogeneous drops. Exemplifies both "Personal" (career tracking + craft for performance) and "Research / Reading a book / hobby deep-dives" use cases from [[GROK]].

See [[log]] for the full batch entry and [[Sources/MasterClass Collection - 2026]] + [[Sources/CPCU 552 Commercial Property Insurance - Study Materials]] for details.


