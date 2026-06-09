# SCHEMA.md

Configuration for the LLM Wiki in this vault. The agent (Claude, Grok, or other) **reads this file first** every session that touches the wiki, then follows it.

> If running in Claude Code / Codex, keep one-line `CLAUDE.md` and `GROK.md` stubs at the vault root pointing here. This file is the single source of truth.

---

## The Idea

The agent maintains a persistent, interlinked markdown wiki that sits between you and raw sources. When you add a source, the agent reads it and **integrates** it into the existing wiki — updating pages, adding cross-references, flagging contradictions — rather than just indexing it for later retrieval. Knowledge is compiled once and kept current, so it compounds. You curate sources and ask questions; the agent does all writing and bookkeeping. Obsidian is the IDE, the agent is the programmer, the wiki is the codebase.

## Architecture

1. **`raw/`** — immutable source documents. The agent reads but never edits these.
2. **`wiki/`** — all agent-generated pages. The agent owns this layer entirely.
3. **`SCHEMA.md`** — this file. The rules.

## Structure

```
GrokVault/
├── SCHEMA.md
├── CLAUDE.md / GROK.md      # one-line stubs → "Read SCHEMA.md first"
├── raw/                     # immutable sources (+ raw/assets/ for images)
└── wiki/
    ├── index.md             # lean catalog — see Index Rules
    ├── log.md               # append-only change history
    ├── Sources/             # one source-summary per ingested source
    ├── Concepts/            # eudaimonia, logos, falsifiability, ...
    ├── Thinkers/            # philosophers, scientists, authors
    ├── Schools/             # Stoicism, Empiricism, ...
    ├── Arguments/           # recurring lines of reasoning
    └── Contradictions/      # major unresolved tensions
```

Use `[[wikilinks]]` for all cross-references. Create subfolders as new domains require.

## Current Domain Focus

```
Active leg:   AI & Cognitive Science
Next leg:     History of Ideas
Full plan:    Philosophy → Phil. of Science → AI & Cognitive Science
              → History of Ideas → Religion-as-Philosophy → Domain Depth
```

**Leg transition note (2026-06-04)**: With the ingest of A. M. Turing's "Computing Machinery and Intelligence" (1950), the vault has initiated the planned AI & Cognitive Science leg. The paper supplies the Imitation Game (operational behavioral criterion), the demonstration that digital computers are universal discrete-state machines, the famous storage/prediction horizon, the nine-objection rebuttal (especially Jefferson consciousness and Lady Lovelace originality), and the concrete "learning machines" research programme (child machines + education). It is the single canonical bridge text from the completed Phil of Science cluster (now including Hacking's experimental turn) into machine intelligence, philosophy of mind, and cognitive science. Cross-references established to Descartes (dualism challenge), Locke (consciousness & personal identity), Kasparov (Deep Blue as historical test of the criterion + creativity boundary), MasterClass "human creativity vs machines" theme, and the vault's own 2026 AI sources (Grok/Claude/Gemini tutorials as partial realizations). Per SCHEMA, Page Types reviewed (no new types required yet); a lint pass is recommended. This ingest completes the source-summary + thinker + 6 concepts; index and log updated.

**Prior leg note (2026-06-04)**: With the ingest of Ian Hacking's *Representing and Intervening* ..., the vault completed the core 20th-c. post-positivist set and moved into the Phil of Science / Epistemology leg (see full prior note in git history or earlier SCHEMA version).

Before starting a new leg: update this block, review the Page Types table, run a lint pass.

## Page Types

Set `type:` in frontmatter:

| type | for | folder |
|---|---|---|
| `source-summary` | one per raw source | `Sources/` |
| `thinker` | a person | `Thinkers/` |
| `school` | a movement/tradition | `Schools/` |
| `concept` | a single idea/term | `Concepts/` |
| `argument` | a recurring line of reasoning | `Arguments/` |
| `contradiction` | a major tension between pages | `Contradictions/` |
| `analysis` | a filed answer to a query | `wiki/` |
| `note` / `overview` | scratch, landing pages | `wiki/` |

Add new types to this table when a new leg needs them (e.g. `paper`, `event`, `case`).

## Page Anatomy

```markdown
---
title: "Page Title"
type: concept
domains: [ethics, epistemology]
created: "2026-06-04"
updated: "2026-06-04"
sources: ["raw-filename.md"]
tags: [philosophy]
---

# Page Title
> One-sentence hook.

## Summary
(Synthesis reflecting ALL sources so far, not just the latest.)

## Key Claims / Positions
(For concept pages: "How Different Thinkers Use This" with explicit agreements/disagreements.)

## Contradictions / Open Questions
- > [!warning] Conflicts with [[Other Page]] on X — see [[Contradictions/...]]

## Sources
- [[Sources/source-page]]

## Related
- [[Linked Page]]
```

Never invent data — leave a field blank if the info isn't in the source.

---

## Operations

### Ingest (one source at a time)

1. Read the new file in `raw/` fully.
2. Write a **source-summary** page in `Sources/`.
3. Create or update the relevant **thinker / concept / school / argument** pages. **Search the wiki first and update existing pages — do not create duplicates.** Note what this source adds and any agreements/contradictions with prior entries.
4. Add `[[wikilinks]]` to every entity that has or should have a page.
5. **Index** — see Index Rules below.
6. **Log** — append one line to `log.md`.

A source typically touches 5–15 pages. Ingest sources one at a time so each can see everything already in the wiki.

### Index Rules (PERFORMANCE-CRITICAL)

`index.md` is a lean catalog, **not** a mirror of the log. To keep ingests fast:

- **Never rewrite the whole index.** Only add or edit the specific line(s) for pages created or substantially changed this ingest, using a targeted search-replace.
- One line per page: `- [[Sources/Page]] — one-line description | type | domains`
- Group by folder under simple `##` headers. Add a new line under the right header; if the page already has a line, edit only that line.
- Minor edits to an existing page (a new cross-link, a tweak) do **not** require an index change. The index only changes when a page is **created** or its description/scope materially changes.
- If the index ever exceeds a few hundred lines, split it (`index-Concepts.md`, `index-Thinkers.md`) rather than letting one file grow without bound.

### Log Rules

`log.md` carries the full change history so the index doesn't have to. Append-only, one entry per operation:

```
## [2026-06-04] ingest | Source Title — pages: created X,Y / updated Z / contradictions: none
## [2026-06-04] query  | <question> — filed [[Analysis - ...]]
## [2026-06-04] lint   | <findings + actions>
```

Never rewrite past log entries.

### Query

Read `index.md` first, then `grep` (scoped to `wiki/`) and read relevant pages. Synthesize with inline `[[wikilinks]]`. File substantial answers as `type: analysis` pages, add one index line, log it.

### Contradictions

- **Minor:** a `> [!warning]` callout on both conflicting pages, each linking the other.
- **Major / recurring** (Plato vs. Aristotle on Forms; Stoic determinism vs. Aristotelian contingency; Hume vs. rationalist a priori): a dedicated `Contradictions/` page stating each position and the pages holding it, linked from both sides and from the index. These are the highest-value pages in the wiki — flag, never silently reconcile.

### Lint (run periodically and at every leg transition)

Check for: unflagged contradictions, stale claims, orphan pages, concepts mentioned but lacking a page, missing cross-references, cross-domain concepts lacking a unified page, index/frontmatter drift. Fix, then log as `lint`.

---

## Tool & Edit Discipline

- Prefer **targeted search-replace over full-file rewrites** — especially for `index.md`. Full rewrites of large files are the main cause of stalls.
- Read a file before editing it.
- After changing wiki content, update the index (per Index Rules) and append to the log — but do the **minimum** edit each requires.
- When moving a page, fix inbound `[[wikilinks]]` and verify with `grep` that no link points to the old location.
- Vault path: `/var/home/msteitz/gdrive/AI/Obsidian/GrokVault`.

## Tips

Obsidian Web Clipper → save articles to `raw/`. Set attachments to `raw/assets/`. Graph view shows hubs and orphans. `git init` the vault for rollback. Consistent frontmatter powers Dataview tables.

---

*Slimmed 2026-06-04: index made append-only/lean to fix ingest stalls; log carries change history. See log.md.*
