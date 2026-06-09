# GrokVault

Personal LLM Wiki (powered by Grok).

**Primary entry points:**

- Open **wiki/Overview.md** for the friendly introduction.
- See **wiki/index.md** for the full catalog of pages.
- Read **GROK.md** (this directory) for the complete operating manual and conventions that Grok follows.
- Check **wiki/log.md** for the activity timeline.

## Quick Start

1. Drop source material (markdown articles, notes, etc.) into the `raw/` folder.
2. Ask Grok in this chat: "Ingest the latest source from raw/" or similar.
3. Browse results live in Obsidian while Grok works.
4. Ask questions; Grok will synthesize from (and add value back to) the wiki.

See `GROK.md` and `wiki/Overview.md` for full details on the pattern and this vault's implementation.

This entire vault (especially `wiki/`) is designed to compound in value over time with minimal manual maintenance.

---

*Initialized 2026-06-03. All wiki content is LLM-maintained.*

## Faster searches in the index and wiki (using qmd)

The `wiki/index.md` is the lean master catalog (per SCHEMA.md). For fast, ranked, snippet-rich searches (BM25 full-text + optional semantic/hybrid with local models), we use [qmd](https://github.com/tobi/qmd) (local on-device search engine for markdown KBs).

Collections configured:
- `grokvault`: full `wiki/` content (all pages for broad searches)
- `grok-index`: just `wiki/index.md` (targeted catalog searches)

**Usage (from vault root):**
```bash
# Search just the catalog/index
npx @tobilu/qmd search "your terms" -c grok-index -n 5 --md

# Hybrid query across whole wiki (best results; requires `npx @tobilu/qmd embed` first)
npx @tobilu/qmd query "natural language question about the vault" -c grokvault --json

# Get specific page
npx @tobilu/qmd get qmd://grok-index/index.md

# Update after edits
npx @tobilu/qmd update
```

See `npx @tobilu/qmd --help` and the qmd README for MCP/agent integration, context, etc.

This replaces (or augments) manual `read_file` + `grep` for "read index first" and wiki searches, making operations faster and more precise.
