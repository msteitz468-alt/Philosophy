# Skill Observation Log

Observations captured during task-oriented work. Each entry identifies a
potential skill improvement or new skill opportunity.

**Status key:** OPEN = not yet actioned | ACTIONED = skill updated/created |
DECLINED = user decided not to pursue

---

## 2026-08-12 Groundwork ingest

### Observation 1: Misleading source filename caused a false outstanding-source

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Kant *Groundwork* (Gregor/Korsgaard Cambridge). Vault already held the same work under `Sources/Metaphysics of Morals - Immanuel Kant`, listed as 1797 in Ingested Sources.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — search first; File Ingested Sources; Outstanding Sources bookkeeping

**Issue:** Outstanding Sources said "Kant is in mainly via the later *Metaphysics of Morals*" and listed Groundwork as next #5. The already-ingested file *was* the 1785 Groundwork (Wood/Yale). The source-summary filename and Ingested Sources date (1797) taught later agents the wrong bibliographic fact. The ingest protocol says "search the wiki first — update existing pages, never create duplicates," which caught the collision, but the catalog layer (Ingested / Outstanding) had already drifted.

**Suggested improvement:** SCHEMA / ingest protocol should require that `title:` and the Ingested Sources date name the *work*, not the file or the later system the work prepares. When a volume title disagrees with the work it contains, the source-summary title and the catalog row must follow the work. Add a one-line check to Outstanding Sources updates: grep existing source-summaries for the work-title before listing it as missing.

**Principle:** Catalogs that use a container's name instead of the work's name will systematically reopen holes that are already closed.

## 2026-08-12 Jackson 1982 ingest

### Observation 2: Concurrent related-source ingests raced on shared pages

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** User asked to ingest Jackson 1982 ("Epiphenomenal Qualia") while another session ingested Jackson 1986 ("What Mary Didn't Know"). Both papers share Thinkers/Frank Jackson and Arguments/Knowledge Argument.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — search first; Index Rules; one source at a time

**Issue:** Two sessions wrote the same thinker and argument pages and each added index lines. Result: duplicate catalog entries (two source lines for 1986, two thinker lines, two argument lines) and a last-writer-wins race on shared prose. The 1986 session noted the collision in the log; this session collapsed the duplicate index lines after the fact. SCHEMA says "ingest one source at a time" and "search the wiki first," which does not prevent two sessions from ingesting *different* sources that share entity pages.

**Suggested improvement:** Before creating a thinker/argument/concept page, grep `raw/` (not just `wiki/`) for companion sources by the same author on the same debate. If a companion is sitting in `raw/` un-ingested, either ingest both in one session or treat the shared entity pages as already claimed and update rather than recreate. Index rule: before adding a catalog line, grep the index for the exact `[[path]]` and edit the existing line.

**Principle:** "Search the wiki first" is necessary but not sufficient when two related sources are ingested in parallel. Shared entity pages need an existence check immediately before write, not only at planning time.

## 2026-08-12 Extended Mind ingest

### Observation 3: Concept pages built from later books are not a completed ingest of the original paper

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Clark and Chalmers, "The Extended Mind" (Analysis 1998). A Concepts/Extended Mind page already existed from The Experience Machine (2023) and Reality+ (2022).
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — search first; short-source protocol; update existing pages

**Issue:** SCHEMA says search the wiki first and update rather than duplicate. That correctly blocked a second Extended Mind concept page. It did not say to treat the existing page as a completed ingest of the 1998 paper. The page had the parity slogan, Otto/Inga in one sentence, and the later mechanism/smartphone update — and was missing active vs Putnam/Burge externalism, the Tetris/implant cases, Twin Otto, the four coupling features, the explicit refusal to extend consciousness, and the 1998 judgment that the Internet typically fails those features. Reception had flattened the argument into a slogan.

**Suggested improvement:** SCHEMA ingest step 3 should add: if a concept/argument page already exists from a later commentary or popularization, ingesting the original paper is a *primary-source rewrite* of that page, not a light cross-link. Check the existing page's `sources:` frontmatter; if the original is absent, rewrite the summary from the original and keep later material in dated subsections.

**Principle:** A page that cites a thesis is not the same as a page that has read the paper. Reception-first stubs systematically drop the distinctions the original was written to make.

### Observation 4: Publisher-hash PDF filenames need a metadata identification step before ingest

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** User asked to ingest `1467-8284_00096 -- 2a9d9f8645497d7bf20720e2335e96a1.pdf`. ISSN 1467-8284 is Analysis; PDF metadata title was "The Extended Mind"; metadata author was the journal editor Peter Smith, not Clark and Chalmers.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA File Ingested Sources
**Type:** internal
**Phase/Area:** Ingest — identify the work; File Ingested Sources

**Issue:** The queue filename carried no author or title. pdfinfo author was the journal production name, which would have mis-catalogued the paper if trusted. Identification required ISSN lookup + first-page byline. Filing then renamed to a work-title filename so the Ingested/ folder remains searchable.

**Suggested improvement:** For hash/ISSN/DOI-style filenames, the first ingest step is identify-the-work (pdfinfo + first page + ISSN/DOI), and never take PDF `Author` as the paper's author for journal scans. File into `raw/Ingested/` under `Title - Author (year).pdf` plus a converted `.md`, recording the original filename in the source-summary.

**Principle:** Catalogs keyed to publisher junk names lose the work; catalogs keyed to PDF Author metadata on journal scans often credit the editor.

### Observation 5: Outstanding Sources "or" rows hide remaining holes

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Foucault *Discipline and Punish*. Outstanding Sources listed "*Discipline and Punish* (1975) or *History of Sexuality* I (1976)" as a single row, then treated "those last three (Foucault, Sartre, Husserl)" as the same structural problem.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Outstanding Sources bookkeeping; File Ingested Sources

**Issue:** An "A or B" catalog row encodes a priority choice, not a single hole. Ingesting A left B still sitting in `raw/` (History of Sexuality Vol. 1 PDF), but the struck-through combined row plus the "last three" summary would have taught a later agent that the Foucault-primary hole was closed. The same pattern exists on other rows (Hadot *Philosophy as a Way of Life* or *The Inner Citadel*; Husserl *Cartesian Meditations* or *Ideas* I). This session split the Foucault row after the fact.

**Suggested improvement:** Outstanding Sources should list one work per row. "Or" is a note in the Why column ("cheaper start if X is too large"), never the source name. After ingesting one of a pair, rewrite any summary sentence that still groups the author with the unfixed structural problem.

**Principle:** A catalog row that names two works as alternatives will be checked off when either lands, silently reopening the other as a false "done."

### Observation 6: Re-read catalog files immediately before each edit during concurrent ingests

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Hadot *Philosophy as a Way of Life* while other sessions were ingesting Foucault *Discipline and Punish*, Clark/Chalmers "Extended Mind," and starting Kant CPR.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Index Rules; Tool & Edit Discipline; concurrent-session hygiene

**Issue:** Mid-ingest, the Foucault thinker frontmatter gained a Discipline-and-Punish source the session-start snapshot did not have; index.md Last-updated was rewritten by the Extended Mind ingest; Outstanding Sources Last-updated drifted. Targeted search-replace against the start-of-session text failed or would have clobbered another session's source. The SCHEMA rule "read a file before editing it" is necessary but not sufficient when parallel sessions write the same catalog files: the read must be immediately before the edit, not once at planning time.

**Suggested improvement:** SCHEMA / ingest protocol should treat index.md, log.md, Ingested Sources, Outstanding Sources, and any thinker page another ingest might touch (Foucault, Kant, Clark) as shared mutable state. Re-read immediately before each replace. Prefer append-only log entries and additive frontmatter list edits over replacing a whole sources: line from a stale snapshot. After ingesting one work from an "A or B" Outstanding row, split the row (this session applied Observation 5 to Hadot / Inner Citadel).

**Principle:** When several writers share a catalog, a plan-time read is a stale cache. Check-then-act-then-verify on the file you are about to change.

### Observation 7: ABBYY FineReader PDFs need a PyMuPDF extraction path

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Foucault *The History of Sexuality* I. The 164-page PDF is an ABBYY FineReader 9.0 scan.
**Skill:** New skill candidate: wiki-ingest (internal) / convert-documents-to-markdown
**Type:** internal
**Phase/Area:** Ingest — convert the raw file before reading

**Issue:** `pdftotext -layout` (and pdftotext without -layout) produced letter-spaced OCR ("T h e H i s t o r y of S e x u a l i t y", "W e Other Victorians") that is unreadable as a source. pdfinfo showed Producer: ABBYY FineReader 9.0. PyMuPDF `page.get_text("text")` extracted clean, usable text from the same file. The convert-documents-to-markdown skill recommends anydoc; the pdf skill recommends pdftotext first. Neither path would have produced a readable ingest file.

**Suggested improvement:** SCHEMA / ingest convert step should try PyMuPDF `get_text` before pdftotext on PDFs whose Producer is ABBYY or whose first-page sample is letter-spaced. Do not treat a successful pdftotext exit code as a usable conversion.

**Principle:** A conversion that exits 0 can still destroy the source. Sample the first page for letter-spacing before committing to an extractor.


### Observation 8: DJVU sources need djvutxt, not anydoc

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Husserl *Cartesian Meditations*. The raw file was a 10 MB multi-page DJVU.
**Skill:** convert-documents-to-markdown / New skill candidate: wiki-ingest (internal)
**Type:** internal
**Phase/Area:** Ingest — convert the raw file before reading

**Issue:** The convert-documents-to-markdown skill lists doc/docx/pdf/epub/pptx/xlsx and does not mention DJVU. anydoc would have failed. `djvutxt` (and `ddjvu`) were already on the machine and produced a 61k-word markdown file good enough to ingest, with messy OCR (hyphenation, page headers, garbled italics) that subagents could reconstruct.

**Suggested improvement:** SCHEMA / ingest convert step should detect DJVU (`file` reports "DjVu multiple page document") and use `djvutxt` before any PDF/anydoc path. Sample the first page for hyphenation/page-header noise and tell section-readers to reconstruct rather than quote garbled strings blindly.

**Principle:** Format detection must precede the default converter. A skill that lists supported extensions will silently skip the format that is actually on disk.


### Observation 9: Do not import later jargon into an earlier systematic source

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Hohwy, *The Predictive Mind* (2013), after Clark's *Experience Machine* (2023) was already in the vault.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — large-volume; search first; later-popularization already present

**Issue:** The later predictive-processing literature (and this agent's prior knowledge) uses "Markov blanket" for Hohwy's seclusion thesis. The 2013 book never uses that phrase. It uses "veil of sensory input," "seclusion," "sensory boundary," "skull-bound." The planned page title almost became "Secluded Mind and the Markov Blanket (Hohwy)." The same session had Clark pages already built from the 2023 popularization; rewriting those as if they were Hohwy would have flattened Hohwy's imperialism (PEM is *all* the brain does), his refusal of the hard problem, and his opposite delusion story (low sensory gain, not high-precision PE).

**Suggested improvement:** SCHEMA ingest step 3 should add: (1) when a later popularization is already ingested, create the earlier systematic author's pages under *that author's terms and titles*, then update the later pages — do not absorb the earlier book into the later author's concept names; (2) a later-literature term that the source does not use must not appear in the page title or as a claim the author made. Subagent prompts should say "ONLY use term X if the words appear."

**Principle:** A page that cites a thesis in the vocabulary of its reception is not a page that has read the book. Later jargon on an earlier source is the same flattening as a slogan-only stub.

### Observation 10: Kindle AZW3 needs a Calibre hop before anydoc

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Dehaene, *Consciousness and the Brain* (2014). Queue file was `.azw3`.
**Skill:** convert-documents-to-markdown / New skill candidate: wiki-ingest (internal)
**Type:** internal
**Phase/Area:** Ingest — identify the work; convert before reading

**Issue:** The convert-documents skill lists PDF/EPUB/Office but not Kindle formats. `ebook-convert` also cannot write `.md` directly (`No plugin to handle output format: md`). The working path was AZW3 → EPUB via Calibre, then anydoc to markdown. A MOBI is sitting in the same `raw/` queue (`Human Compatible`, `Anarchy, State, and Utopia`). Without this hop documented, the next Kindle ingest will stall on the same two errors.

**Suggested improvement:** SCHEMA / convert step: if extension is `.azw3` / `.mobi` / `.azw`, run `ebook-convert file.azw3 /tmp/work.epub` then anydoc on the EPUB. Do not pass AZW3 to anydoc or ask Calibre for markdown.

**Principle:** Format detection must precede the default converter. A skill that lists supported extensions will silently skip the format that is actually on disk.

### Observation 11: Scholarly translation apparatus is load-bearing, not paratext

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Ziporyn's 2023 *Daodejing* (Liveright). The 81 chapters are short; the Introduction and "A Note on the Translation" carry the A/B reversal, the renderings *course* / *virtuosity* / *nondoing*, and the "minimally discernible position."
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — identify what counts as the source; short-source vs large-volume

**Issue:** SCHEMA's short-source protocol says read the source fully. For a translated classic the "source" is easy to treat as the 81 chapters only, with the translator's intro filed as optional bibliography. That would have dropped Ziporyn's load-bearing claims: *dao* ironically reversed from purposive how-to into nonpurposive "course"; *de* as unlearned potency; the A/B value inversion; the corpus as a commonplace book rather than a single-authored treatise. Those claims structure every concept page. The chapters alone do not name "A/B" or justify "course" over "Way."

**Suggested improvement:** SCHEMA ingest step 1 should treat a scholarly translator's introduction and key-term note as part of the source whenever the edition is chosen *as that edition*. Quote the translator's renderings consistently and flag the translation layer. Do not discard apparatus as paratext for classics whose wording is constitutively ambiguous.

**Principle:** When the vault ingests a specific translation of an ambiguous classic, the translator's frame is part of what is being ingested. Dropping it produces a generic "Tao Te Ching" page that no actual edition wrote.

### Observation 12: EPUB conversion — anydoc max_xml_depth, Calibre txt fallback

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Pseudo-Dionysius, *The Mystical Theology and The Divine Names* (Dover EPUB).
**Skill:** convert-documents-to-markdown / New skill candidate: wiki-ingest (internal)
**Type:** internal
**Phase/Area:** Ingest — identify and convert the raw source

**Issue:** `npx @firecrawl/anydoc` on the Anna's Archive EPUB failed with `resource limit exceeded (max_xml_depth): element nesting exceeds 256`. `ebook-convert` has no markdown writer. `ebook-convert … .txt` succeeded (7258 lines, ~96k words) and was copied to a `.md` sidecar. The convert-documents-to-markdown skill documents only the anydoc CLI and does not mention this failure mode or the Calibre fallback.

**Suggested improvement:** Add a conversion fallback to convert-documents-to-markdown (or the internal wiki-ingest protocol): if anydoc exits on `max_xml_depth` / nesting, use Calibre `ebook-convert` to `.txt` (or `.html` then pandoc) and write the sidecar next to the EPUB. Do not treat anydoc failure as "cannot read this book."

**Principle:** A conversion tool that dies on publisher markup is not a source-identification failure. The ingest continues with the next available converter; the original binary is still what gets filed.

### Observation 13: Index "Last updated" line is the hottest race on multi-ingest days

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Anil Seth, *Being You* (2021), while Dehaene, Russell *Human Compatible*, Ziporyn *Daodejing*, and Pseudo-Dionysius were also writing `wiki/index.md`.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA Index Rules
**Type:** internal
**Phase/Area:** Index Rules; one source at a time; concurrent sessions

**Issue:** SCHEMA says never rewrite the whole index and only add/edit specific lines. The one-line "Last updated:" banner at the top of `index.md` is still a single shared slot. Between planning and write, the banner changed from Hohwy to Human Compatible. Targeted replace of the old Hohwy string failed; a re-read was required before the Seth banner could be inserted and the previous ingest pushed to "Prior:". Observation 2 already covers thinker/argument page races. This is the catalog-banner version of the same collision: last writer owns "what just happened," and a stale replace drops the other session's ingest from the recency stack.

**Suggested improvement:** Before editing the "Last updated:" line, re-read the first 15 lines of `index.md`. If the current Last-updated is not this ingest, insert this ingest as Last-updated and keep the previous one as the first Prior (do not replace a different ingest's banner). Index rule addendum: the banner is shared state; treat it like a claimed entity page.

**Principle:** Lean catalogs still have a single recency slot. Targeted replace of a remembered banner string is a race; targeted replace of the *live* banner is not.


### Observation 14: Outstanding Sources can attribute a later book to an earlier title

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Damasio, *Descartes' Error* (1994). Outstanding Sources listed it as "Body, emotion, Spinoza (already in)."
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Step 1 Cross-Links Anticipated; Outstanding Sources bookkeeping; never invent

**Issue:** Outstanding Sources taught the ingest that this book is a Spinoza source. The 2005 flyleaf names *Looking for Spinoza* as a later book. Subagents found zero occurrences of "Spinoza" in the 1994 text. The vault comparison (3def3, conatus, organism-as-ensemble) is real and useful, but it is not a citation. Without an explicit grep-the-source check, the orchestrator would have written "Damasio's declared philosophical home" into the source-summary from the catalog, not the book.

**Suggested improvement:** SCHEMA Step 1 / Outstanding Sources update: anticipated interlocutors are hypotheses. Before writing "Thinker X is cited," grep the raw source for the name. Catalog kinship ("feeds Clark; rhymes with Spinoza") must be labeled as vault comparison when the name is absent. Do not promote a later book from a flyleaf into the ingest of an earlier one.

**Principle:** A queue note that names the author's later work will systematically mis-cite the book in hand. Search the source, not the catalog, for who is actually in the text.

### Observation 15: MOBI is not an anydoc input; Calibre EPUB is the bridge

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nozick, *Anarchy, State, and Utopia*. Source arrived as a 720KB MOBI in `raw/`.
**Skill:** convert-documents-to-markdown; New skill candidate: wiki-ingest (internal)
**Type:** internal
**Phase/Area:** Ingest — convert before read; File Ingested Sources

**Issue:** The convert-documents skill lists EPUB/PDF/Office formats and uses anydoc. Calibre `ebook-convert` refuses `.md` as an output format. The working path on this machine is MOBI → EPUB via Calibre, then EPUB → Markdown via anydoc. A Human Compatible ingest filed MOBI + converted `.txt`; this one filed MOBI + converted `.md`. Without a documented bridge, agents will try anydoc on MOBI or Calibre-to-md and stall.

**Suggested improvement:** convert-documents (or a wiki-ingest extras note): for Kindle formats (`.mobi`, `.azw3`), convert to EPUB with Calibre first, then anydoc to `.md`. File both the original ebook and the converted markdown. Do not treat `.txt` and `.md` as interchangeable house styles — prefer `.md` to match the rest of `raw/`.

**Principle:** A conversion skill that names its CLI but not the format bridges will fail on the formats the queue actually contains.


### Observation 16: Named opponent without a primary gets a one-sided contradiction, not a closed debate

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nozick, *Anarchy, State, and Utopia*. Ch. 7 is a long critique of Rawls, *A Theory of Justice* (1971). Rawls is not a vault primary.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA Contradictions
**Type:** internal
**Phase/Area:** Step 2c contradiction pages; Outstanding Sources; never invent

**Issue:** SCHEMA says major recurring tensions get a dedicated Contradictions page stating both positions. For a one-sided ingest the temptation is either (a) skip the contradiction until the opponent is ingested, leaving the vault without a place to hang the debate, or (b) write Rawls's side from general knowledge as if it were a primary. This session filed the contradiction, marked Rawls as reported from Nozick's presentation plus the existing Buchanan-veil note, and added *A Theory of Justice* to Outstanding Sources as the hole the ingest opened.

**Suggested improvement:** SCHEMA Contradictions: when only one side is a primary, create the page, label the missing side "reported, not primary," and add the missing work to Outstanding Sources in the same turn. Do not close the contradiction. Do not write the missing side from training data.

**Principle:** A debate page that pretends both books have been read will be overwritten badly when the second book arrives; a debate page that admits it is one-sided is ready to be rewritten.


### Observation 17: anydoc reports no text on ocrmypdf PDFs that PyMuPDF can read

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Clark *Surfing Uncertainty* (OUP 2016; 2019 reprint). 412-page PDF, Producer pikepdf / Creator ocrmypdf 11.4.1 + Tesseract OCR-PDF.
**Skill:** convert-documents-to-markdown / pdf / New skill candidate: wiki-ingest (internal)
**Type:** internal
**Phase/Area:** Ingest — convert the raw file before reading

**Issue:** `npx @firecrawl/anydoc` failed with `unsupported input: PDF has no extractable text (TextBased, 412 pages): OCR is required`. The file already had an OCR text layer. `pdftotext` and PyMuPDF `page.get_text("text")` extracted ~1.0M characters of usable (hyphenated) text. Observation 7 covered ABBYY FineReader letter-spacing; this is a different failure: anydoc's extractability heuristic rejects a text-layer OCR-PDF that other extractors read.

**Suggested improvement:** SCHEMA / convert-documents step should treat anydoc "no extractable text" as a *probe failure*, not a scan diagnosis. Next: sample with PyMuPDF `get_text`. If chars > 0, extract via PyMuPDF (page markers) and do not re-OCR. If chars = 0, then ocrmypdf/tesseract. Do not trust anydoc's OCR-required message as ground truth.

**Principle:** A converter that cannot see a text layer is not evidence that the layer is missing. Probe with a second extractor before spending an OCR pass or abandoning the file.

### Observation 18: Volume ISBN in the filename does not mean the file is the volume

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** User asked to ingest `CB, 2016 -- Cambridge -- isbn13 9781107706965 -- … -- Anna’s Archive.pdf`. ISBN 9781107706965 is the ebook ISBN of Goldberg (ed.), *The Brain in a Vat* (CUP 2016, ~270 pp.). pdfinfo reported 15 pages / 125 KB. The text was chapter 6 only (Pritchard and Ranalli).
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA File Ingested Sources
**Type:** internal
**Phase/Area:** Ingest — identify the work (extends Observation 4)

**Issue:** Observation 4 covered hash/ISSN filenames and untrustworthy PDF Author metadata. This file had a *correct* volume ISBN and a Cambridge year, which looks like the whole book. It was a Cambridge Core single-chapter download (DOI …1107706965.006). Cataloguing it as the Goldberg volume would have invented twelve unread essays. The working checks were page count, file size, and the first heading — not the ISBN.

**Suggested improvement:** Identify-the-work must include a page-count / first-heading check *after* ISBN lookup. If ISBN says 270 pages and the file is 15, ingest the chapter that is actually on disk, record the original filename and hash, and leave the rest of the volume on Outstanding Sources. Do not promote a chapter download to a book ingest.

**Principle:** Bibliographic identifiers name a work; the file on disk may be a slice of that work. Ingest the slice, and say so.

### Observation 19: Two works share a near-identical title

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Ogden & Richards, *The Meaning of Meaning* (1923), while Outstanding Sources already listed Putnam's "The Meaning of 'Meaning'" as a remaining hole and a concurrent session had just ingested Pritchard/Ranalli on Putnam's BIV argument.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — identify the work; Outstanding Sources bookkeeping

**Issue:** The user said "ingest The meaning of meaning." The queue PDF was Ogden & Richards 1923. Outstanding Sources and a same-day Putnam ingest used the nearly identical title "The Meaning of 'Meaning'." Without an identify-the-work step, an agent could have filed this book as the Putnam paper (or struck the Putnam row). The works share a slogan and a topic (reference) and almost nothing else: triangle/word-magic vs Twin Earth/externalism.

**Suggested improvement:** SCHEMA ingest step 0 should treat quoted-vs-unquoted titles and author as load-bearing. When the user names a work that collides with an Outstanding row or an existing source-summary, confirm author+year before writing. Outstanding rows that share a title fragment with a different ingested work must carry an explicit "Not X" note (this session added one to the Putnam row).

**Principle:** Title-collision across works is a catalog failure mode distinct from filename-collision. The quotes, the author, and the year are the disambiguators; the slogan is not.

### Observation 20: Reception ingest of a combined Outstanding row must split the row

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** User asked to ingest *Isaiah Berlin and the Politics of Freedom* (Baum/Nichols 2013), a commemorative reception of Berlin’s 1958 “Two Concepts of Liberty.” Outstanding Sources had one History of Ideas row: `"Two Concepts of Liberty" / *The Crooked Timber of Humanity*`.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol (extends Observations 3 and 5)
**Type:** internal
**Phase/Area:** Ingest — Outstanding Sources bookkeeping; reception vs primary

**Issue:** Observation 3 already says concept pages from a later book are not a completed ingest of the original. Observation 5 says “or” rows hide remaining holes. This case is both at once, plus a third title: the user named a *reception volume* of work A, while the outstanding row bundled A with unrelated-method book B (*Crooked Timber*). Leaving the row intact after creating Berlin concept pages would have looked like the lecture and *Crooked Timber* were done. Cataloguing the 2013 book as “Two Concepts” would have invented a primary.

**Suggested improvement:** When the requested title is reception, commentary, or a 50-years-later collection of a still-outstanding primary: (1) ingest it as reception and say so on the source-summary and thinker page; (2) split any combined Outstanding row *in the same ingest* so the primary and any sibling titles stay listed; (3) do not credit the reception as the Lovejoy-leg “method” book if that job belongs to a different title still in `raw/`.

**Principle:** A reception volume installs vocabulary and debate; it does not retire the primary, and it must not retire a second book that happened to share a catalog row.

### Observation 21: Revised-edition recanting introductions are a second voice

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of *The Embodied Mind* (Varela, Thompson, Rosch), 2016 MIT revised edition of the 1991 text. Thompson and Rosch each wrote a new introduction; the 1991 chapters are unchanged.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA Large-Volume Protocol
**Type:** internal
**Phase/Area:** Ingest — scholarly apparatus; Observation 9 (do not import later jargon); Observation 11 (translation apparatus is load-bearing)

**Issue:** Thompson 2016 recants three 1991 strategies (Husserl as failed; Buddhist philosophy as meditation-derived; mindfulness as inner observation) and imports later terms (grounded cognition, adaptively autonomous, neurophenomenology). Rosch 2016 disagrees with Thompson on the Dreyfus objection and splits enaction into phase 1/2. Treating the 2016 intros as the book's own claims would have overwritten the 1991 argument and collapsed two living disagreements. Autopoiesis, named in the 2016 apparatus, is *not* a word in the 1991 ch. 7–8 body (operational closure / structural coupling).

**Suggested improvement:** For a revised edition with new authorial introductions, run the paratext as its own section cycle. Tag 2016 (or later) restatements as apparatus. Do not create concept pages from later programs the new intro reports (here: neurophenomenology, autopoiesis) unless the original body defines them. If co-authors disagree in new intros, put the disagreement on the thinker pages, not into the 1991 concept definitions.

**Principle:** A recanting preface is evidence about the later author, not a license to rewrite the book they recanted.

### Observation 22: EPUB publisher metadata can name the wrong translator

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Merleau-Ponty, *Phenomenology of Perception*. Queue EPUB filename attributed the book to Colin Smith and the old *International Library of Philosophy and Scientific Method*. Converted text was the Donald A. Landes 2012 Routledge translation (Carman foreword, Lefort intro, bilingual TOC).
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA File Ingested Sources
**Type:** internal
**Phase/Area:** Ingest — identify the work; Observation 4 (hash/ISSN filenames)

**Issue:** Observation 4 covered journal-scan PDFs whose `Author` metadata names the editor. This was the EPUB analogue: the container filename preserved a previous translator and series, while the file itself was a later translation. Cataloguing as "Smith" would have been a bibliographic error and would have taught later agents the wrong pagination and key-term choices (*sens*, *le corps propre*, *schéma corporel*, *motricité*). Identification required reading the title page / translator's introduction, not trusting the Anna's Archive filename.

**Suggested improvement:** For EPUB/PDF queue files whose filename includes a translator, series, or ISBN that disagrees with the title page, the first ingest step is identify-the-edition (title page + translator introduction). Catalog `title:`, Ingested Sources, and citations by the work and the edition actually on disk. Record the junk filename in `sources:` frontmatter.

**Principle:** Filenames travel with the download, not with the work. Identify the edition from the text before writing any wiki page.


### Observation 23: Reception slogans must not be written as the primary's wording

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Merleau-Ponty, *Phenomenology of Perception*. Existing Dreyfus pages treated "maximum grasp" as Merleau-Ponty's term. The Landes text never uses "maximum grasp" or "optimal grip"; it says hold / optimum equilibrium / scope of this hold. Planned concept "Intercorporeity" was likewise a later-MP / 4E name absent from the 1945 book.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA Large-Volume Protocol; Observation 3 (reception-first stubs)
**Type:** internal
**Phase/Area:** Ingest — search first; primary-source rewrite; concept naming

**Issue:** Observation 3 said a later commentary page is not a completed ingest of the original. It did not say: when the commentary *coins a slogan* for the original, that slogan will leak into the planned page list and get created as if it were the author's term. Subagent instructions that asked "does maximum grasp appear?" and "does intercorporeity appear?" caught both. Without that check, the vault would have taught "maximum grasp" as MP and "intercorporeity" as 1945.

**Suggested improvement:** When a later source in the vault already names a concept after an earlier author (Dreyfus's "maximum grasp"; 4E "intercorporeity"), the primary-source section plan must treat those names as *hypotheses*. Subagent prompts should ask whether the phrase occurs, and what the book's actual wording is. Create the page under the book's term; put the reception slogan on the later thinker's page as a gloss.

**Principle:** A famous later name for a doctrine is evidence about the reception, not a license to rename the source.


### Observation 24: Earlier book may already contain later-book vocabulary

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of William James, *The Varieties of Religious Experience* (1902), with *Pragmatism* (1907) already in the vault.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA large-volume ingest
**Type:** internal
**Phase/Area:** Ingest — Observation 9 analog (do not import later jargon); Cross-Links Anticipated

**Issue:** The Clark 2016 ingest established "do not import 2023 slogans into the 2016 book." The same rule was applied here: do not import 1907 *Pragmatism* jargon into 1902. The rule is right, but publication order is not a reliable filter. Lecture XVIII of *Varieties* already uses Peirce's "principle of *pragmatism*," "cash-value," and "every difference must *make* a difference." A blanket ban would have dropped 1902's own wording. The 1907 slogans that are *not* here ("corridor in a hotel," "the true is the expedient in the way of our thinking") still must stay out. The same pattern hit "meliorism": the word appears in 1902 Lectures IV–V as evolutionist progress-religion, not as the 1907 midpoint between optimism and pessimism.

**Suggested improvement:** SCHEMA / ingest protocol: "Do not import later-book jargon" is a search rule, not a date rule. Before writing the earlier book's pages, grep that book for the later book's load-bearing terms. Keep the words that are actually there; keep the later book's *distinctive* formulas out. When the same word appears in both, state the two senses on the page rather than merging them.

**Principle:** A later book can reuse a word it already coined, or reuse a word in a new sense. Date-order bans drop the first use and flatten the second. Search the text you are ingesting.

### Observation 25: Reception-then-primary needs two source-layers on one thinker page

**Date:** 2026-08-12
**Session context:** Ingest of Isaiah Berlin, *The Crooked Timber of Humanity* (2013), after the same-day 2013 Baum/Nichols reception of “Two Concepts of Liberty”
**Skill:** New skill candidate: philosophy-wiki-ingest (internal) / SCHEMA Large-Volume Protocol
**Type:** internal
**Phase/Area:** Step 3 synthesis — updating an existing reception-first thinker page from a later primary

**Issue:** The vault already had [[Thinkers/Isaiah Berlin]] and [[Concepts/Value Pluralism (Berlin)]] built from a reception volume. Outstanding Sources had listed *Crooked Timber* as the History-of-Ideas *method* after Lovejoy, and “Two Concepts” as a separate primary. The primary ingest had to deepen those pages without (a) deleting the reception layer, (b) treating Crooked Timber as a substitute for the still-outstanding 1958 lecture, or (c) creating a second Berlin thinker page. Quotes from Hardy *Liberty* (TC/IN) must stay labeled reception.

**Suggested improvement:** When a thinker or concept page exists from reception and a primary arrives, rewrite the hook and Summary from the primary, keep a clearly marked “as quoted in reception” section, and leave the still-outstanding primary named. Do not merge distinct works that share a thinker into one voice.

**Principle:** A reception page and a later primary are two source-layers on one page, not a replacement. Search-first-update is not enough; the page must keep the layers distinguishable so a later ingest of the remaining primary can still correct the reception layer.

### Observation 26: Series-year in an EPUB filename can name a different translation of the same title

**Status:** OPEN

**Date:** 2026-08-12
**Session context:** Ingest of Confucius, *The Analects* — queue file `The Analects -- Confucius -- 1979 -- Penguin Books Ltd -- …epub`
**Skill:** New skill candidate: philosophy-wiki-ingest (internal) / convert-documents-to-markdown
**Type:** internal
**Phase/Area:** Identification before Step 1 — title page vs Anna’s Archive / publisher filename

**Issue:** The EPUB filename said Penguin 1979, which is the well-known D. C. Lau *Analects*. The converted title page is Annping Chin’s 2014 Penguin Classics translation (eBook ISBN 978-0-698-15351-6; “This translation first published in Penguin Books 2014”). Same series, same classical title, different translator, different apparatus. Opening the file was the only way to see it. A Lau-shaped ingest (no Chin commentary, different term choices) would have been the wrong book.

**Suggested improvement:** After conversion, read the title page / copyright page before writing the source-summary stub. Record translator, first-publication year, and ISBN on the stub. If the filename year and the title-page year disagree, treat that as a different work until proven otherwise — not as a reprint of the named edition. Do not call a Penguin *Analects* “Lau 1979” from the folder name.

**Principle:** For frequently retranslated classics, the publisher-year in a pirate/archive filename often names the series or an earlier edition, not the file. Translator + copyright year on the title page are the identity. Filename matching is not bibliographic identification.


### Observation 27: Long books misfiled as "cheap papers" in Outstanding Sources

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *The Gay Science* (Kaufmann Vintage 1974, 415 pp.)
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — identify the work; choose Short vs Large-Volume protocol

**Issue:** Outstanding Sources listed *The Gay Science* under "Cheap papers that punch above their length" with the note that *amor fati* was in via Holiday. The file on disk was a 415-page Kaufmann edition (383 numbered sections + preface + prelude + songs). Treating it as a short-source "paper" would have collapsed Books I–V into a slogan ingest. The Large-Volume Protocol was the correct path; the catalog category was wrong.

**Suggested improvement:** Outstanding Sources rows should state protocol (short vs large-volume) from page/section count, not from how a later popularizer used one phrase. A "cheap paper" row that names a multi-book treatise is a catalog error. When identifying a queue PDF, record page count in the row before ingest.

**Principle:** A book that contains a famous slogan is not a paper about that slogan. Protocol follows the work's size and internal structure, not the hole it closes.

### Observation 28: Collected-works EPUB must be extracted per work, never filed as a whole

**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *Human, All Too Human* from *The Friedrich Nietzsche Collection: 22 Classic Works* while Zarathustra, Genealogy-Johnston, Case of Wagner, and Twilight were being extracted from the same EPUB
**Skill:** New skill candidate: collected-works ingest / wiki large-volume ingest
**Type:** internal
**Phase/Area:** File Ingested Sources + Large-Volume Protocol Step 1 identification
**Status:** OPEN

**Issue:** The 2013 22-work Nietzsche EPUB is one file containing many titles, some truncated (HATH is only Preface + Vol. I chs. I–III), some duplicated, and with mixed translators. Multiple same-day sessions each needed a different work. Filing the EPUB into `raw/Ingested/` after any one ingest would have hidden the remaining queue. Concurrent writers also raced the shared Free Spirit concept page (BGE Ch. II vs 1878 HATH). Overwriting would have dropped one book's voice.

**Suggested improvement:** For collected works: (1) identify the requested title inside the file and whether it is complete; (2) extract a sidecar named for that work/translator; (3) leave the collection in `raw/` until every work that will be ingested has its own source-summary; (4) if another session has already created a concept page the new book also needs, merge a dated layer — do not replace the page. Reuse Observation 18 (filename is not the volume) and Observation 21 (revised-edition preface is a second voice).

**Principle:** A collected-works file is a queue, not a source. Each title is a source. Shared concept pages need layers by date of the primary, not last-writer-wins.

### Observation 29: One collection EPUB, several titled works, concurrent ingests race the thinker page

**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche, *The Case of Wagner* (1888) from *The Friedrich Nietzsche Collection: 22 Classic Works*
**Skill:** New skill candidate: philosophy-wiki ingest (internal) / SCHEMA.md large-volume and collected-works rules
**Type:** internal
**Phase/Area:** Ingest — collected works; identity of the work; concurrent sessions
**Status:** OPEN

**Issue:** The 2013 22-work collection TOC lists both an *Ecce Homo* chapter headed "The Wagner Case" and the 1888 pamphlet "The Case of Wagner: A Musician’s Problem." The user's phrase "the wagner case" matches the chapter heading first. The pamphlet is the primary. Same file, same day, other sessions were extracting *Zarathustra*, *Human, All Too Human*, Johnston *Genealogy*, and *Twilight* from the same EPUB. Shared surfaces (*Thinkers/Nietzsche.md* `source_count`/`sources:`, `wiki/index.md` Last-updated banner, `wiki/log.md` top insertion) were overwritten between read and write. Collection must stay in `raw/` until every work has its own complete source-summary.

**Suggested improvement:** In SCHEMA collected-works / ingest rules: (1) when the user names one work inside a collection, identify it from that work's own title page and opening, not from the first TOC hit; flag lookalike headings (here: Ecce Homo chapter vs pamphlet). (2) Do not file the collection EPUB when only one work is ingested. (3) On shared hub pages during concurrent collection ingests, re-read frontmatter immediately before every increment; add the new source to the live list rather than replacing a snapshot. (4) Index Last-updated: re-read the live banner immediately before replace (already required; this session confirmed the race is routine on collection days).

**Principle:** A collected volume is a queue, not one source. The work the user named is the ingest; neighbouring titles in the same file are not bonuses. Shared thinker/index/log pages need a live read at write time whenever more than one session is drawing from the same collection.

### Observation 30: Second translation of an already-ingested book is a new source, not a rewrite

**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *On the Genealogy of Morals* from the 2013 22-work collection after the 2026-06-04 Samuel/Levy Internet Archive ingest
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA Large-Volume Protocol; Observation 25 (two source-layers); Observation 26 (identify translator); Observation 28 (collection extract)
**Type:** internal
**Phase/Area:** Ingest — search first; second-edition / second-translation
**Status:** OPEN

**Issue:** The vault already had a full primary ingest of *Genealogy* from Horace B. Samuel. The collection contained Ian Johnston (unnamed on the title page; identified from "knowledgeable people," "PROLOGUE," gray). Replacing the Samuel source-summary or rewriting concept hooks in Johnston English would have erased the first translation and taught the vault that one English *is* the book. The 2026-06-04 Essay III digest was thin; the hole was real. The method page that ingest claimed and retracted was still missing, and Foucault's Genealogy page had been speaking for Nietzsche.

**Suggested improvement:** When a queue file is a second translation of a work already ingested: (1) create a *new* source-summary named for the translator; (2) keep the first translation's page and label its quotes; (3) add a dated "translator layer" on existing concept pages rather than rewriting the hook; (4) create only the pages the first ingest claimed and never wrote, or that a later neighbour (here: Foucault) now requires; (5) identify the translator from the text, not the collection filename. Do not merge "we knowers" with "knowledgeable people," grey with gray, or *ressentiment* with resentment.

**Principle:** A second translation is a second source of the same work. Layers keep both voices. Overwrite teaches the last English as the German.


### Observation 31: Collection TOC can modernize a work's title while the body is an older translation

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *Thus Spoke Zarathustra* from *The Friedrich Nietzsche Collection: 22 Classic Works* (2013)
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA File Ingested Sources; Observation 22, 26, 28
**Type:** internal
**Phase/Area:** Ingest — identify the edition from the work's body, not the collection TOC

**Issue:** The collection TOC and extracted heading say *Thus Spoke Zarathustra* (Kaufmann's 1954 English title). The body is Thomas Common 1909: internal *THUS SPAKE ZARATHUSTRA*, *Superman* (not overman), *Backworldsmen*, archaic *hath/spake/unto*. Sibling works in the same EPUB are other translators (Zimmern BGE, Ludovici Wagner, Johnston Genealogy). Trusting the TOC title or a sibling extract's translator would have catalogued Common as Kaufmann.

**Suggested improvement:** For collected-works files, identify *each* requested work from that work's own first discourses and distinctive term choices, not from the collection title page, the TOC wording, or a neighbouring extract. Record translator on the source-summary stub before any concept page is named (here: "Superman" is Common; do not write Kaufmann "overman" into 1883).

**Principle:** A collection can modernize titles and mix translators. The identity of a work is its body. TOC English is marketing.


### Observation 32: A source-summary row is not a finished book

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** User asked to ingest *Beyond Good and Evil* from the 2013 Nietzsche collection. Vault already had a June 4 source-summary and an Ingested Sources row; that ingest had stopped after Preface + Chapter I §§1–9 (and even those skipped §§10–23). Same-day sessions were extracting other works from the same EPUB.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — search first; Large-Volume status; File Ingested Sources

**Issue:** Search-the-wiki-first correctly blocked a second BGE source page. It did not say the existing page was *unfinished*. Status was absent (not `in-progress`). Ingested Sources listed 1886 as done. Outstanding Sources did not list BGE. A later agent could have treated the work as ingested and moved on. Completing the book required a primary-layer rewrite of Master/Slave (Genealogy-first) and splitting "free spirits" from "philosophers of the future" — distinctions Chapter I never made.

**Suggested improvement:** SCHEMA ingest step 1 / search-first: if a source-summary exists, read its Section Plan or last heading before treating the work as done. Missing `status: complete`, a "further chapters pending" closer, or a Section Plan with pending rows means *complete the existing page*, not skip. Do not strike or omit a work from Outstanding solely because a stub or chunk-1 page exists.

**Principle:** A catalog line names a file; `status: complete` names a finished reading. Those are different facts.


### Observation 33: Two sessions extracted the same collection-work under different filenames

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *Twilight of the Idols* (Kaufmann Portable text) from the 2013 22-work collection, while other sessions split the same EPUB (Zarathustra, HATH, Wagner, Johnston Genealogy, and sidecar extracts of *Antichrist*, *Ecce Homo*, *Will to Power*).
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA File Ingested Sources
**Type:** internal
**Phase/Area:** Ingest — extract a single work from a collected-works file; File Ingested Sources

**Issue:** This session extracted Twilight to `Twilight of the Idols - Nietzsche (Kaufmann).md`. A parallel session extracted the same span to `Twilight of the Idols - Nietzsche (Kaufmann, Collection 2013).md`. Both sat in `raw/` until one was ingested. Leaving the second extract in `raw/` would have reopened a hole the source-summary had just closed. The container EPUB correctly stayed in `raw/` for uningested companions.

**Suggested improvement:** When extracting a work from a collected-works volume, grep `raw/` and `raw/Ingested/` for the work-title before writing a sidecar. If a sibling extract already exists, reuse it. After ingest, move *every* sidecar of that work into `Ingested/`, not only the filename listed in `sources:` at planning time.

**Principle:** A collected-works file can be split by more than one session at once. The queue is the folder, not the filename you happened to write.

### Observation 34: Incomplete posthumous compilations must not be completed from memory

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *The Will to Power* from the 2013 22-work collection (Kaufmann notes 1–134 + 466–617 only)
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA large-volume protocol
**Type:** internal
**Phase/Area:** Ingest — identify the work; do not invent; File Ingested Sources

**Issue:** The collection prints "Note: Books II & IV are not available" and then jumps from Book I n.134 to Book III.I n.466. The most-quoted notebook sentence in the secondary literature (Kaufmann n.1067, "This world is the will to power — and nothing besides!") is not in the file. An ingest that treated *The Will to Power* as "Nietzsche's book" or filled the missing books from training data would have invented a published treatise and a cosmology the excerpt does not contain. Existing vault copy already said "Do not treat the unpublished Will to Power notebook as this book" on the published-will-to-power page — that warning had to become a sourced notebook layer, not a reason to skip the excerpt.

**Suggested improvement:** SCHEMA ingest identification step should require, for posthumous / notebook / collected-works excerpts: (1) state editorial status in the source-summary first paragraph; (2) record the first and last note/section numbers actually present; (3) list famous passages the secondary literature associates with the title and confirm each is in the file before quoting; (4) if the container says a book or part is unavailable, treat that as load-bearing, not as a prompt to supply it.

**Principle:** A famous title on an incomplete compilation is a trap. Quote only what the file contains; name what it lacks.

### Observation 35: Same-year companion compilations are a different genre

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of *Nietzsche Contra Wagner* after *The Case of Wagner* was already in from the same 2013 collection.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA ingest protocol
**Type:** internal
**Phase/Area:** Ingest — search first; do not duplicate; reception vs primary layers

**Issue:** Two 1888 Wagner texts sit adjacent in one EPUB. Search-first correctly blocked a second Decadence/Cagliostro/Histrionics page. It did not say what *Nietzsche Contra Wagner* uniquely is: a Christmas 1888 *selection* of earlier writings (some 1877) whose thesis is "we are antipodes," not another case-write-up. Levy also appended 1878 Nachlass after the Epilogue; Kaufmann's NCW stops at the Epilogue. Treating the appendix as the 1888 book would have invented chapters Nietzsche did not place there.

**Suggested improvement:** When two short works share an author, year, and subject, the first ingest step is genre (new polemic vs compilation vs later self-review). If the file continues past the work's last authorial heading into editor-titled fragments, stop and label the rest as appendix. Do not ingest the next heading in the collection as part of this work.

**Principle:** A companion that *selects* earlier pages is a different primary from the pamphlet that *diagnoses* the same case. Same folder, same year, different act.

### Observation 36: Same-title chapter and book in one collected-works file

**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *The Birth of Tragedy* from *The Friedrich Nietzsche Collection: 22 Classic Works*
**Skill:** New skill candidate: collected-works ingest / wiki large-volume ingest
**Type:** internal
**Phase/Area:** Ingest — identify the work from its own title page, not the first TOC hit
**Status:** OPEN

**Issue:** This collection already produced Observation 29 (*Ecce Homo* chapter “The Wagner Case” vs pamphlet *The Case of Wagner*). The same file also has two headings **The Birth of Tragedy**: an *Ecce Homo* self-review (collection line 9437) and the 1872 treatise (line 17203, then numbered §§1–25). The user said “the birth of tragedy from the nietzsche collection.” A TOC-first grep hits the chapter. Genre markers distinguish them: the book opens “Much will have been gained for aesthetics…” and runs §§1–25; the chapter opens “In order to be fair to the Birth of Tragedy (1872) it is necessary to forget a few things.” Concurrent sessions were still racing Nietzsche.md / index Last-updated / Outstanding Sources.

**Suggested improvement:** When a collected-works file contains a later self-review of an earlier book, expect *two* headings with the same title. Identify the requested work from opening sentence + internal structure (numbered treatise vs first-person retrospective), not from the first TOC or grep hit. Reuse Observation 29’s live-read rule on shared hub pages.

**Principle:** In an author’s collected works, a chapter that reviews a book will often bear the book’s title. The work the user named is the book unless they named the review.

### Observation 37: A Nachlass essay’s famous English slogan is translator-specific

**Date:** 2026-08-12
**Session context:** Ingest of Nietzsche *On Truth and Lies in a Nonmoral Sense* from *The Friedrich Nietzsche Collection: 22 Classic Works*
**Skill:** New skill candidate: collected-works ingest / wiki large-volume ingest
**Type:** internal
**Phase/Area:** Ingest — identify translator from the work’s own wording (Observation 31)
**Status:** OPEN

**Issue:** Reception and training data almost always quote Kaufmann’s Portable line “a mobile army of metaphors” and his title *On Truth and Lie in an Extra-Moral Sense*. This collection prints Breazeale’s title and “a **movable host** of metaphors.” Filing Kaufmann’s slogan on the source-summary would have taught the last-famous English as the 1873 German. Same pattern as Common *Superman* vs Kaufmann *overman* (Observation 31) and Samuel *ressentiment* vs Johnston *resentment* (Observation 30).

**Suggested improvement:** For unpublished / Nachlass pieces that exist in several standard Englishings, identify the translator from one load-bearing formula before any concept page is titled. Put that formula in the concept hook. Note the more famous rival English as a warning, not as the page’s wording.

**Principle:** A famous English sentence is not the text. Quote the file. Name the rival translation so later writers do not “correct” it back.


### Observation 38: Cambridge "and Other Writings" volumes are three books in one EPUB

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Schopenhauer *On the Fourfold Root* from Cambridge 2012 EPUB titled *On the Fourfold Root … and Other Writings*
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA identify-the-work
**Type:** internal
**Phase/Area:** Ingest — identify the work; File Ingested Sources

**Issue:** The queue EPUB's title names Fourfold Root, but the volume also contains *On Vision and Colours* and *On Will in Nature* (~19k lines). The user asked only for Fourfold Root. Extracting the whole volume as one source would have mixed three works and two later books into the 1847 dissertation rewrite. The extract kept only FR (plus the editorial intro *to FR*). The EPUB was left in `raw/` so the companions remain visible as outstanding.

**Suggested improvement:** For Cambridge Schopenhauer (and similar "and Other Writings") volumes, Step 0 is list every work in the table of contents. Ingest the named work only unless the user asked for the volume. Leave the container in `raw/` until every contained work has a source-summary.

**Principle:** A volume title that leads with one treatise will hide the other treatises if the agent files the container as done.

### Observation 39: Systematic primary must precede its popular companion when both are queued

**Status:** OPEN
**Date:** 2026-08-12
**Session context:** Ingest of Schopenhauer *WWR* Volume 2 while *Parerga* Volume 2 finished first the same day.
**Skill:** New skill candidate: wiki-ingest (internal) / SCHEMA large-volume protocol
**Type:** internal
**Phase/Area:** Ingest — search first; Observation 3 (primary rewrite); concurrent related sources

**Issue:** *Parerga* II (popular essays that presuppose the system) created Affirmation and Denial, Indestructibility, and Vanity pages from the *paralipomena*. *WWR* II is the systematic primary those essays cite as already treated "consistently and fully in my chief work." The WWR II ingest then had to primary-rewrite those pages instead of creating them. Observation 3 already covers later commentary vs original paper; this is the same flattening when the *popular companion* lands first.

**Suggested improvement:** SCHEMA Step 1 / Cross-Links Anticipated: if a systematic treatise and its popular companion (or "additional remarks" volume) are both in `raw/`, ingest the systematic treatise first. The companion then updates those pages. If the companion finishes first, the treatise ingest is a primary-source rewrite, not a new-page pass.

**Principle:** A page written from the popular restatement will systematically drop the distinctions the systematic work was written to make. Queue order is part of search-first.
