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

### Ingest — Short Sources (under ~150 pages)

For articles, papers, short treatises, and dialogues that fit in a single reading pass:

1. Read the source fully in one pass.
2. Write a **source-summary** page in `Sources/`.
3. Create or update the relevant **thinker / concept / school / argument** pages.
   **Search the wiki first — update existing pages, never create duplicates.**
   Note what this source adds and any agreements or contradictions with prior entries.
4. Add `[[wikilinks]]` to every entity that has or should have a page.
5. **Index** — see Index Rules below.
6. **Log** — append one line to `log.md`.

A source typically touches 5–15 pages. Ingest one source at a time.

---

### Ingest — Large-Volume Protocol (over ~150 pages)

Dense philosophical works — multi-book treatises, collected works, major
systematic texts — cannot be read usefully in a single pass without losing
the internal argument structure. A claim in Book I of the *Enneads* often
only resolves in Book VI. The *Summa Theologica* builds each question on
prior ones. The *Critique of Pure Reason* front-loads vocabulary that the
argument consumes later. Mechanical token-chunking destroys these
dependencies. This protocol preserves them.

**The discipline:** read one logical section at a time, write all affected
pages to disk before reading the next section. Context is ephemeral; disk
is permanent. Never hold two sections in context simultaneously.

#### Step 1 — Structural Map (before reading any content)

Read only the table of contents, the preface or introduction, and the
conclusion or final section if present. Do not read chapter content yet.

From this, write a **source-summary stub** in `Sources/` containing:

```markdown
---
title: "[Source Title]"
type: source-summary
status: in-progress
---

# [Source Title]
## Argument Spine
[2–4 sentences: what is the central argument of the whole work,
 as stated in the introduction or inferable from the structure.]

## Section Plan
| Section | Content | Key Terms Introduced | Pages Affected |
|---|---|---|---|
| [Book/Part/Chapter group] | [what it covers] | [new concepts, arguments] | [wiki pages to create or update] |
...

## Cross-Links Anticipated
[concepts, thinkers, contradictions already in the wiki that this
 source will touch — list them now so each section write-up connects properly]
```

Save this stub to disk before reading any section content.
The Argument Spine and Cross-Links Anticipated are load-bearing —
they keep each section's pages connected to the whole work's thesis
even when the whole work is not in context.

#### Step 2 — Section Cycle (repeat for each section in the plan)

One complete cycle per section. Do not read ahead.

**2a. Read the section.**
Read the full text of the section. Hold it in context for steps 2b–2d only.

**2b. Identify all pages affected.**
Before writing anything, list:
- Pages to create (with proposed file names)
- Pages to update (with what changes)
- Contradictions to flag (with which existing pages they touch)

This list prevents unconsciously prioritizing whatever is freshest in
context over what was introduced earlier in the section.

**2c. Write all affected pages.**
Write or update every page on the list:
- Full content, not stubs
- All frontmatter fields filled
- All `[[wikilinks]]` to existing wiki pages and to pages planned
  in the Section Plan (even if not yet written — forward links are fine)
- For concept pages: add a "How [Thinker] Uses This" subsection
  that explicitly compares to prior thinkers already in the wiki
- For contradiction pages: state both positions fully, link both sides

**2d. Commit to disk.**
Write every file created or updated in this cycle to disk.
Confirm each by reading its path back before proceeding.
A section whose pages exist only in context is lost when
the next section is read. This step is not optional.

**2e. Update source-summary and log.**
- Add a completion note to the section row in the Section Plan:
  `[pages created: N] [pages updated: N]`
- Append a section log entry:
  `## [YYYY-MM-DD] section | [Source] | [Section] | created: N | updated: N`

**2f. Advance.**
Only after 2d and 2e are complete, read the next section.

#### Step 3 — Synthesis Pass

After all sections are processed, do a synthesis pass with only the
source-summary page and index.md in context (not the raw source text):

- Read all pages created or updated from this source
- Add cross-links that only become visible at the whole-work level —
  the connection between a claim in Book I and its resolution in Book VI
  is invisible when processing each section in isolation
- Update the source-summary:
  - Change `status: in-progress` to `status: complete`
  - Add a **Whole-Work Assessment** section: 3–5 sentences on what
    the work contributes to the vault as a whole, how it shifts or
    deepens existing pages, and what contradictions it opens or closes
- Check the Argument Spine written in Step 1 against what was actually
  found in the text — correct it if the introduction misrepresented
  the argument (this happens)

#### Step 4 — Final Log and Index

```
## [YYYY-MM-DD] ingest-complete | [Source Title] | sections: N | created: N | updated: N
```

Update index.md per Index Rules — add lines for all new pages,
edit lines for materially changed pages. One targeted operation,
not a full rewrite.

---

### Large-Volume Protocol: Applied to Specific Text Types

**Multi-book systematic treatises** (Plotinus *Enneads*, Aquinas *Summa*,
Aristotle *Metaphysics*, Hegel *Phenomenology*, Kant *Critique of Pure Reason*):
- Section boundaries follow the author's own divisions (Books, Parts, Questions)
- Never split mid-argument — if a proof spans two chapters, keep them together
- The Argument Spine in Step 1 is especially important here: these works
  are often misread because individual sections are processed without the
  teleological structure (what the work is ultimately trying to establish)

**Collected works and anthologies** (Presocratic fragments, Stoic collections,
Berkeley *Works*, Leibniz *Philosophical Papers*):
- Group by thinker or theme, not by editorial section numbering
- Each thinker-group is one section cycle
- Flag fragments that contradict each other within the same thinker's corpus
  — these are often the most philosophically productive tensions

**Long dialogues and multi-dialogue series** (Plato's late dialogues,
Hume's *Treatise*, Berkeley's Three Dialogues + Principles together):
- Read the introduction or scholarly preface first to establish the
  interpretive debate before reading the primary text
- Each dialogue or major division is one section cycle
- The scholarly preface counts as its own section cycle —
  write the historiography note on the thinker page from it
  before reading the primary text, so the primary text is read
  against its reception history

**Dense epistemological and metaphysical texts** (Kant, Hegel, Heidegger,
Wittgenstein *Tractatus*, Spinoza *Ethics*):
- These introduce technical vocabulary that is redefined as the argument
  proceeds. In Step 1, extract the key technical terms from the
  introduction and add them to Cross-Links Anticipated as
  concept stubs — even before their meaning is established.
  Each section cycle will deepen those stubs rather than
  creating them from scratch at the end.
- The synthesis pass (Step 3) is especially important for these texts —
  the meaning of early sections often only resolves after the final sections

---

### Index Rules (PERFORMANCE-CRITICAL)

`index.md` is a lean catalog, **not** a mirror of the log. To keep ingests fast:

- **Never rewrite the whole index.** Only add or edit the specific line(s)
  for pages created or substantially changed this ingest, using targeted search-replace.
- One line per page: `- [[Sources/Page]] — one-line description | type | domains`
- Group by folder under simple `##` headers. Add a new line under the right header;
  if the page already has a line, edit only that line.
- Minor edits (a new cross-link, a small update) do **not** require an index change.
  Index only changes when a page is **created** or its scope materially changes.
- If the index ever exceeds a few hundred lines, split it
  (`index-Concepts.md`, `index-Thinkers.md`) rather than letting it grow without bound.

### Log Rules

`log.md` carries the full change history so the index doesn't have to.
Append-only, one entry per operation:

```
## [2026-06-04] ingest | Source Title — pages: created X,Y / updated Z / contradictions: none
## [2026-06-04] section | Source Title | Book II — created: 3 | updated: 5
## [2026-06-04] ingest-complete | Source Title | sections: 6 | created: 14 | updated: 9
## [2026-06-04] query  | <question> — filed [[Analysis - ...]]
## [2026-06-04] lint   | <findings + actions>
```

Never rewrite past log entries.

### Query

Read `index.md` first, then `grep` (scoped to `wiki/`) and read relevant pages.
Synthesize with inline `[[wikilinks]]`. File substantial answers as `type: analysis`
pages, add one index line, log it.

### Contradictions

- **Minor:** a `> [!warning]` callout on both conflicting pages, each linking the other.
- **Major / recurring** (Plato vs. Aristotle on Forms; Stoic determinism vs.
  Aristotelian contingency; Hume vs. rationalist a priori): a dedicated
  `Contradictions/` page stating each position and the pages holding it,
  linked from both sides and from the index.
  These are the highest-value pages in the wiki — flag, never silently reconcile.

### Lint (run periodically and at every leg transition)

Check for: unflagged contradictions, stale claims, orphan pages, concepts mentioned
but lacking a page, missing cross-references, cross-domain concepts lacking a unified
page, index/frontmatter drift, source-summary pages with `status: in-progress`
that were never completed. Fix, then log as `lint`.

---

## Tool & Edit Discipline

- Prefer **targeted search-replace over full-file rewrites** — especially for `index.md`.
  Full rewrites of large files are the main cause of stalls.
- Read a file before editing it.
- After changing wiki content, update the index (per Index Rules) and append to
  the log — but do the **minimum** edit each requires.
- When moving a page, fix inbound `[[wikilinks]]` and verify with `grep` that
  no link points to the old location.
- Vault path: `/var/home/msteitz/gdrive/AI/Obsidian/GrokVault`.

## Tips

Obsidian Web Clipper → save articles to `raw/`. Set attachments to `raw/assets/`.
Graph view shows hubs and orphans. `git init` the vault for rollback.
Consistent frontmatter powers Dataview tables.

---

*Large-volume ingest protocol added [current date]: section-cycle discipline,
argument spine, synthesis pass. Index/log rules and performance constraints unchanged.*
