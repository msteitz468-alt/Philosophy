---
title: "Grok (xAI)"
type: concept
greek: ""
schools: []
domains: [ai]
source_count: 2
created: 2026-06-03
updated: 2026-06-03
tags: [ai-models, xai, grok, 2026]
sources: ["AI_Tips_Chat_Export_June_2_2026.docx", "Grok_4.3_Tutorial_Detailed_Notes.docx"]
---

# Grok (xAI)

> xAI's frontier model family and associated tooling (Grok Build, Composer, Imagine, etc.). This vault runs on Grok capabilities.

## Current Snapshot (early June 2026)

Key recent developments from [[Daily Advanced AI Tips - 2026-06-02]] and [[Frontier AI Capabilities - June 2026]]:

- **Composer 2.5** (June 1, 2026): Available in Grok Build. Excellent for long-running tasks, strong instruction following, agentic coding and creative work.
- **Grok Build 0.1** (public beta API): Fast specialized coding model for agentic workflows, web dev, debugging. Supports **MCP** (tool calling / integrations). Powers CLI agents and this TUI environment.
- **Grok Imagine**: Significant video generation/editing improvements (text-to-video, image-to-video, longer clips, audio, resolution).
- Multi-agent orchestration (Grok 4.20+): Coordinator + specialist agents (research, logic, contrarian analysis).
- Real-time X data, context compaction, streaming STT.
- **Skills**: Persistent custom expertise and instructions that carry across conversations (this [[GROK]] file and the wiki maintenance loops are a concrete realization of the "Skills" pattern).

## Strengths (per 2026 tips)
- Real-time / unfiltered perspectives and humor.
- Agentic coding and long-horizon creative/maintenance tasks.
- Tool use and MCP ecosystem.
- Integration with X platform data.

## Role in GrokVault

Grok is the active maintainer:
- Reads sources and wiki state via tools.
- Performs structured ingest (extract → integrate across many pages → update index + log).
- Uses search_replace + write for precise edits.
- Follows the persistent schema in [[GROK]] (analogous to the Skills feature).
- This entire system is an example of using Grok's agentic + persistent capabilities for compounding knowledge work.

## Related

- [[Frontier AI Capabilities - June 2026]]
- [[Agentic Workflows]]
- [[Grok Build]]
- [[Daily Advanced AI Tips - 2026-06-02]]
- [[LLM Wiki]]

## Status

Entity page created on first source ingest (the tips doc that heavily features Grok tooling). Will track further releases and usage patterns observed while maintaining this vault.

## Grok 4.3 Tutorial Notes (May 2026) - [[Sources/Grok 4.3 Tutorial Detailed Notes - 2026]]

Detailed notes from ~32min "Ultimate GROK Tutorial" video (May 11 upload). Emphasizes treating Grok 4.3 as a full workflow system via deliberate use of modes, persistent setup, tools, and agentic patterns rather than basic chat.

Key sections:
- **Interface/Setup**: grok.com primary; attachments (files/images/PDFs/etc); mode selector; Imagine; sidebar with Projects (persistent shared context).
- **Custom Instructions & Memory**: Highest leverage. Persistent across chats (example persona + style). Memory on for cross-convo retention. Makes Grok "personal system".
- **Modes & SuperGrok**: Auto (router default), Fast (simple), Expert (reasoning/multi-step), Grok 4.3 Beta (flagship serious work), Heavy (max). SuperGrok unlocks structured/code/advanced agentic. Discipline in mode choice is key skill.
- **Search (Web + X)**: Native real-time X + web as differentiator. Patterns: trend pulse, sentiment delta, contrarian scan, explain X posts.
- **Long Context/File Analysis**: Direct upload for extraction/contradiction finding across docs/codebases. Video link analysis (shots, timestamps).
- **Imagine & Video**: In-chat or dedicated richer mode. Refine in chat then paste. Agent Mode (beta) for full briefs → scene planning + consistency + sequences. Short clips from images (~10s).
- **Voice & Tasks**: Voice mode (multi-personality, low latency, saved as text) for on-the-go. Scheduled/recurring Tasks (e.g. weekly industry brief) that run background + notify.
- **Structured Outputs & Code Execution**: JSON etc for automation; Python in-chat (CSV analysis, calcs, flags).
- **Agent Roles Prompting (Powerful Framework)**: Turn one Grok into multi-agent via roles in prompt:
  - Harper: Research (sources, X, facts).
  - Benjamin: Logic/analysis/math.
  - Lucas: Critic/devil's advocate/strategy critique.
  - Grok: Final synthesis/polish.
  - Chain them explicitly with handoffs.
- **Agentic Chains & Workflows**: Define full sequence + outputs per step + final format in one prompt. Three high-value end-to-end:
  1. Research (Expert + template surfacing "question nobody asks" + gaps/contradictions).
  2. Content (research first same chat; "pick a side" for stronger output).
  3. Analysis (upload data → Expert → patterns/anomalies/insights + explicit confidence incl lows).
- Takeaways: Mode discipline; agent role prompting for complex; set Custom Instr + Memory immediately; structured + code exec for automation; adopt the 3 workflows consistently (habit > capability gap).

**Vault Connections**: This is practically a user manual for the agent maintaining GrokVault.
- [[GROK]] + index/log/wiki files = Custom Instructions + Memory + Projects (persistent context).
- Tool use (web/x search, file read/grep, terminal python, write/edit) = native search + code exec + analysis.
- Ingest = Research + Analysis + Content workflows + verification (log).
- Multi-page synthesis + cross-ref = agentic chain (roles via schema steps).
- image_* tools = Imagine/video.
- todo_write + structured pages = structured outputs + planning.
- The "underuse as basic chatbot" warning is exactly why the LLM Wiki pattern (persistent compounding artifact + disciplined maintenance) exists instead of pure RAG/chat.
- Complements the Claude guide (May 31) and AI Tips (June 2) for mastery of this specific Grok 4.3 + ecosystem.

See expanded in [[LLM Wiki]], [[GROK]], [[Concepts/Grok Build]] (MCP/tools/Composer/agentic), and Concepts for Grok Modes, Agent Roles, Custom Instructions/Memory, Imagine/Video, Tasks, Projects.

*Updated 2026-06-03 with Grok 4.3 tutorial notes ingest.*
