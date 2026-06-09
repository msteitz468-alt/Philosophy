---
title: "Claude (Anthropic)"
type: concept
greek: ""
schools: []
domains: [ai]
source_count: 2
created: 2026-06-03
updated: 2026-06-03
tags: [ai-models, anthropic, claude, 2026]
sources: ["AI_Tips_Chat_Export_June_2_2026.docx", "Claude_AI_Advanced_User_Guide.docx"]
---

# Claude (Anthropic)

> Anthropic's model family, known for strong coding, reasoning, agentic capabilities, and safety-oriented design. Opus series is flagship.

## June 2026 Snapshot (from [[Daily Advanced AI Tips - 2026-06-02]])

- **Claude Opus 4.8** (May 28): Big improvements in coding, agentic skills, reasoning, knowledge work. Notably lower hallucination on code and better at flagging its own flaws. Improved computer use.
- **Dynamic Workflows** (Claude Code research preview): Can orchestrate hundreds of parallel sub-agents with built-in planning, execution, and verification. Especially strong for large/complex engineering.
- Effort Control slider (Low/Medium/High...) with fast mode ~2.5x speed/cost improvement.
- Mid-session system prompt changes without cache invalidation.
- Claude Cowork, plugins, ongoing computer use enhancements.

## Strengths (per source)
- Reliable coding and long-running agentic work.
- Self-critique and flaw detection.
- Large-scale parallel agent orchestration.

## Related in This Vault

- [[Frontier AI Capabilities - June 2026]]
- [[Agentic Workflows]]
- [[Reasoning Scaffolds]]
- [[Daily Advanced AI Tips - 2026-06-02]]

## Advanced User Guide (May 31, 2026) - [[Sources/Claude AI Advanced User Guide - 2026]]

Comprehensive power-user coverage of the full platform as an "interactive development and workflow platform" / personal AI OS:

- **Projects**: Persistent long-term contexts with custom instructions + uploaded knowledge base (curated files). One per workstream/domain. Acts as template + RAG without extra eng. Use CLAUDE.md for code projects (overview, stack, conventions, patterns — prioritized by Claude Code).
- **Artifacts**: Standalone interactive/editable/shareable outputs (>15 lines): reports, code, full SPAs (HTML/JS/React), viz, games, sims, dashboards, AI-powered (embed Claude calls), MCP-connected for real external actions. Live iteration, versions, sharing via madewithclaude.com. Ground with Project knowledge; test thoroughly.
- **Skills**: Reusable workflows as folders with `SKILL.md` (YAML frontmatter name/desc + instructions/procedures/examples + optional scripts/references/assets/). Progressive load (frontmatter light, full on relevance). Token efficient. For recurring processes (code review, brand voice, analysis frameworks, onboarding). Stackable; deep integration in Claude Code (auto-activation, subagents, hooks). **Exact structural parallel to this vault's GROK.md + .grok/skills/ setup.**
- **Claude Code**: Agentic env (CLI/IDE/desktop) with FS/tools (permissions), Plan Mode, parallel sub-agents/dynamic workflows (hundreds for migrations), Skills + CLAUDE.md awareness, bundled verification skills. Treat as senior pair programmer + oversight. Excels at full apps, refactors, custom tooling, demo videos.
- **API/Production**: Tool calling, structured outputs, caching, vision, search/code exec; agentic loops; evals/guardrails/cost. MCP extends.
- **Integrated**: Project → Skill → Artifact → MCP → share. Best practices on verification, context (curate, Skills over bloat), privacy (MCP/shared), cost, prompting (specific + examples + strong project context), pitfalls (vague Skills, overload Projects, skip review).
- High-leverage for: rapid MVPs as Artifacts, consistent systems, data-to-dashboards, education tools, personal productivity stateful apps, eng acceleration.

**Vault Connections**: This guide + prior AI Tips form core 2026 Claude knowledge. Directly validates/ inspires GrokVault design (persistent schema as Skills/custom instr, wiki as Project knowledge + Artifacts, agentic tool loops as Code, subdirs/organization). See expanded coverage in [[LLM Wiki]] "First Source(s)" and [[GROK]].

**Strengths**: Reliable agentic/coding/reasoning + self-critique; large-scale orchestration (Dynamic Workflows); mature tooling (Artifacts, Skills, Code) for production-like workflows; explicit control (effort slider, Plan Mode).

*Expanded with Claude Advanced User Guide ingest (2026-06-03).*
