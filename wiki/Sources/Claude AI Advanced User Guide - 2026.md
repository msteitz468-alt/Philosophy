---
title: "Claude AI Advanced User Guide - 2026"
type: source-summary
domains: []
source_count: 2
created: 2026-06-03
updated: 2026-06-03
tags: [claude, anthropic, ai-tools, projects, artifacts, skills, claude-code, 2026-05]
sources: ["Claude_AI_Advanced_User_Guide.docx", "Claude_AI_Advanced_User_Guide.md"]
---

# Claude AI Advanced User Guide - 2026

> Mastering Artifacts, Projects, Skills, Claude Code, and Production Workflows. A comprehensive guide for power users. Claude has evolved into a full interactive development and workflow platform / "personal AI operating system".

**Source**: `raw/Claude_AI_Advanced_User_Guide.docx` (May 31, 2026; comprehensive power-user guide drawing from official docs, madewithclaude.com, real deployments).

**Core Thesis**: The pillars — Projects (persistent memory/organization), Artifacts (interactive editable outputs/apps), Skills (reusable dynamically loaded workflows), Claude Code (agentic coding env with parallel exec), and API — combine into something much more powerful than chat.

This source is highly meta for GrokVault: the described structures (SKILL.md + scripts/references/assets, persistent instructions like CLAUDE.md, Projects as long-term context, Artifacts as produced/iterated deliverables, Claude Code agentic patterns) map directly onto this wiki's use of [[GROK]], subdirectories, tool-driven agentic maintenance (ingest loops), and filed outputs (pages, syntheses).

---

## 1. Projects: Persistent Workspaces with Knowledge and Instructions

- Isolated, long-term contexts. Every chat inherits the same knowledge base + custom instructions. Solves context drift.
- Setup: One Project per major recurring workstream/domain (e.g. "Client X", "Personal Finance", "Codebase Refactors"). Avoid giant single project.
- Rich custom instructions: role/persona, purpose/success criteria, tone/format/structures, standing rules, decision frameworks, tools/verification steps.
- Upload curated files to knowledge base (docs, PDFs, code, transcripts, style guides). ~30MB/file; fit context. Auto RAG-like referencing.
- Advanced: Treat as templates (duplicate for similar work); combine with Artifacts; for code use CLAUDE.md (root or uploaded) with overview, stack, conventions, patterns (Claude Code prioritizes it); organize/star chats inside project; switch cleanly.
- Use cases: consistent content systems, client work with history, software projects, research hubs, learning with rubrics/materials.

**Vault Parallel**: The entire GrokVault functions as a persistent "Project" (wiki/ as knowledge base + [[GROK]] as custom instructions/schema). Index + log + specific pages provide the "uploaded files" context on every operation. Subdirs (Sources/, Concepts/) organize workstreams.

---

## 2. Artifacts: Interactive Outputs, Apps, and Tools

- Standalone significant content (>15 lines) in dedicated pane. For iteration, reuse, sharing outside chat. Auto-detected or explicit ("Build as Artifact").
- Types: Markdown reports, code (w/ preview), single-page web apps (HTML/JS/React SPAs fully interactive), SVGs/diagrams, interactive viz/dashboards (Plotly etc), games/simulators/tools.
- Features: Live updates on prompt changes; version selector/branching via edit prior msgs; multiple artifacts per chat; export underlying code; "Try fixing with Claude" for errors.
- AI-Powered Artifacts: Embed Claude intelligence in the artifact (text API for Q&A, coaching, gen inside app). Runs on Anthropic infra; consumers use own quotas.
- MCP Integration: Connect artifacts to external services (Asana, Calendar, Slack, custom MCP) for real read/write. User approves per artifact.
- Persistent Storage (higher plans): Up to 20MB text-only per; stateful apps; personal or shared visibility. Unpublish clears. 
- Sharing: Links, embed, remix via communities (madewithclaude.com).
- Examples: Quizzes, score trackers, Pomodoro, resume builders, 3D physics sims, SpaceX landing sim, audio viz, dashboards, Snake game, business trackers (MCP-linked), recipe managers, "Claude-in-Claude" self-referential tools.
- Best practices: Create for anything iterated/referenced/shared; test thoroughly (esp interactive/MCP); deliberate on shared/storage/privacy; use versions/branching; ground with Project knowledge.

**Vault Parallel**: Our "filed" wiki pages (source summaries, syntheses, analyses, entity/concept pages) act as persistent Artifacts — produced, iterated (via search_replace), linked, "shared" in the graph/Obsidian, versioned via git potential. The agentic process produces structured outputs that live on as first-class knowledge.

---

## 3. Skills: Reusable, Dynamically Loaded Workflows (Highest Meta Relevance)

- Solve repetitive prompting by packaging instructions, checklists, examples, resources into portable folders. Load efficiently (progressive disclosure), work across tools.
- **Structure**: Folder with required `SKILL.md` (+ optional scripts/, references/, assets/).
  - SKILL.md: YAML frontmatter (name, description — critical for triggering/relevance) + Markdown body (detailed instructions, procedures, examples, rules).
- How work: Frontmatter loads lightly for detection. Full content + linked files load only when relevant. Token-efficient.
- Building/using: For recurring multi-step: custom code review, brand-voice gen, analysis frameworks, onboarding, sprint planning, data workflows. Test simple first. Upload/enable in settings or direct in Claude Code. Stack multiple. Use official + community libs.
- In Claude Code: Deeper auto-activation, subagent exec, hooks, dynamic context.
- Advanced: Modular/composable; combine with Projects (project-specific skills) + Artifacts (skills that enhance/output artifacts); "AI OS" patterns — chains of specialized capabilities.

**Vault Parallel (Exact Match)**: This GrokVault + the broader .grok/skills/ setup **is** the Skills pattern applied to LLM wiki maintenance and agent operation.
- [[GROK]] is the SKILL.md equivalent (frontmatter-like structure + detailed instructions/procedures for ingest/query/lint, conventions, tool use).
- skills/ folders follow "SKILL.md + scripts/ references/ assets/" exactly (see the docx skill, imagine, etc.).
- The wiki subdirs + index act as persistent "Project" knowledge.
- Agent (Grok) "loads" the skill via reading GROK + index + pages only as needed.
- Our todo_write, search_replace discipline, logging etc are the "procedures/examples".
- This source (and the AI Tips one) will be cross-referenced as we evolve the schema.

---

## 4. Claude Code: Agentic Development Environment

- Beyond chat: CLI/IDE integrations (VS Code/JetBrains), desktop/web. Tools, permissions, planning, orchestration.
- Key: FS + terminal/tools access (w/ approvals); Plan Mode (think/outline first); Parallel execution + dynamic workflows (sub-agents for migrations/refactors); Deep Skills integration + CLAUDE.md awareness; Bundled skills (code review, debug, batch, loop) + verification loops.
- Power patterns: Plan first for non-trivial; parallel sub-agents + worktrees; strong CLAUDE.md + Skills; explicit verification/critique prompts ("This is not architecturally coherent"); combine with Artifacts for UI previews.
- Excels at: full app building (FE+BE), Remotion video pulling real components, large refactors, custom tooling, doc gen from code.
- Treat as senior pair programmer with oversight, not autonomous magic.

**Vault Parallel**: The way this agent operates on the vault (list_dir/read_file/grep to research, write/search_replace to "code"/edit pages, run_terminal for extraction, todo for planning, log for verification, following GROK "plan" ) is a Claude Code-like agentic workflow applied to knowledge base "development". The "CLAUDE.md" in guide is our [[GROK.md]]. Sub-agents via role prompting or parallel tool use.

---

## 5. API and Production Systems + Integrated Workflows

- API for custom agents/integrations/scaled: strong tool use/function calling (Tool Search/examples for reliability), extended thinking, structured outputs, prompt caching, vision, web search/code exec.
- Build agentic loops (single → parallel multi-tool → full runners).
- MCP concepts extend to custom.
- Production: evals, guardrails, cost, rate limits, batch.
- Most users: web/desktop + Artifacts/Projects/Skills covers 80-90%; API for embedded/high-volume.
- High-leverage combos: Project (knowledge/instr) → Skill (standardized process) → Artifact (interactive deliverable) → MCP (external actions) → publish/share.
- Claude Code for heavy impl + Artifacts for UI/UX iteration.
- Skills stack for repeatable quality; Projects for context.
- Use cases: rapid internal tools/MVPs as Artifacts, consistent brand content systems, data analysis to interactive dashboards, educational (quizzes/simulators/adaptive), personal productivity (stateful trackers), software eng accel (refactors, reviews, component libs, demo videos), self-contained AI apps shared.

**Best Practices / Pitfalls**:
- Context/efficiency: Skills for reusable (avoid bloat), Projects for facts, curate uploads, caching.
- Verification: Always review (esp code/data/actions); explicit critique; test Artifacts.
- Planning/iter: Plan Mode or outlining; branch/edit msgs; version awareness.
- Privacy/security: Review MCP/shared carefully; sensitive data caution in published.
- Cost: Monitor (API, loops, large contexts). Higher plans for storage/MCP/full.
- Prompting: Specific/structured + examples + role + constraints + format. Strong project context > vague for code.
- Pitfalls: Overload single Projects; vague Skill frontmatter (bad trigger); skip Artifact verification; ignore Code permissions; treat as one-off chat.
- Scaling: Template Projects/Skills; build reusable libs; teams use shared + org controls.

**Resources**: Official help/docs, madewithclaude.com, skills library, r/ClaudeAI, X, Simon Willison blogs, YouTube, API cookbooks.

---

## Relation to This Vault & Prior Sources

This guide (May 31, 2026) + the [[Daily Advanced AI Tips - 2026-06-02]] (June 2) form a powerful paired view of 2026 Claude + cross-model capabilities. The "Skills" and "CLAUDE.md" descriptions are almost instructional for how to operate/maintain a system like GrokVault using persistent schemas and agentic patterns.

- Directly informs evolution of [[GROK]] (make more SKILL.md-like with better frontmatter/triggering?).
- Validates our subdir organization, index as "knowledge base", log for verification, tool use for grounding.
- Suggests potential expansions: "Artifacts" as published interactive pages (Marp slides, dashboards via code?); more "Skills" for specific ingest/query patterns; stronger "Project"-like isolation if multiple domains.
- [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]] (Grok side) will complement for cross-model routing/custom instr/memory/agent roles.

See also updated [[Concepts/Claude (Anthropic)]], [[LLM Wiki]], [[Concepts/Agentic Workflows]], [[Concepts/Context Engineering]] etc.

## Sources & Provenance
- Original: `raw/Claude_AI_Advanced_User_Guide.docx`
- Text companion: `raw/Claude_AI_Advanced_User_Guide.md`
- Generated ~May 31, 2026 from official + community sources.

## Related Pages
- [[Concepts/Claude (Anthropic)]]
- [[LLM Wiki]]
- [[GROK]]
- [[Daily Advanced AI Tips - 2026-06-02]]
- [[Syntheses/Frontier AI Capabilities - June 2026]]
- [[Concepts/Skills]] (to be expanded or new)
- [[Concepts/Artifacts (Claude)]]
- (New pages for Projects, Claude Code, etc. as needed)

---
*Ingested as part of batch of new files on 2026-06-03. Extremely high signal for the LLM Wiki pattern itself.*
