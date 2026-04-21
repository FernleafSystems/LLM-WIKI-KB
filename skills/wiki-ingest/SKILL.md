---
name: wiki-ingest
description: Use when adding a new raw source document to a repo-local wiki. One ingest may touch several wiki pages.
---

# Wiki Ingest

Ingest a raw source document into the wiki. Read the source, check existing wiki context, write a source page, update affected topic pages, and maintain the control pages.

## Pre-condition

1. Find `kb/AGENTS.md`.
2. Find `kb/REPO_WIKI_SPEC.md` in the same `kb/` directory.
3. Read both files before doing anything else.
4. Confirm the source already exists in `kb/raw/`.

If the source is not already in `kb/raw/`, stop and tell the user to import it first. Do not copy, fetch, or save new files into `raw/` as part of ingest.

## Process

### 1. Accept the source

Accept a raw source filename or path inside `kb/raw/`.

### 2. Read the source in full

Read all content. For long sources, read it in sections. Do not skip.

### 3. Surface takeaways before writing

Tell the user:
- 3-5 key takeaways
- which existing pages or categories this source is likely to affect
- whether it appears to contradict anything already in the wiki

Ask:

`Anything specific you want me to emphasize or de-emphasize?`

Wait for the reply before writing.

### 4. Create the source page

Create `wiki/sources/<slug>.md` with:
- `type: source`
- `category: sources`
- `sources: [<raw filename>]`

Keep the page simple:
- one-line summary
- source metadata
- summary
- key takeaways
- affected pages or topics
- related pages

### 5. Update affected topic pages

For each topic touched by the source:
- find the correct category from `REPO_WIKI_SPEC.md`
- update the existing page if it already exists
- otherwise create `wiki/<category>/<slug>.md`

Use:
- `type: topic`
- `category: <repo category>`
- `sources: [deduped raw filenames]`

### 6. Run a backlink audit

Check existing wiki pages for places that should now link to the new or updated pages. Add useful backlinks.

Do not scan only one directory. Check the wiki as a whole.

### 7. Update control pages

- update `wiki/index.md`
- update `wiki/overview.md` if the source changes the current synthesis
- update `wiki/glossary.md` if terminology changes
- append to `wiki/log.md`

### 8. Report to the user

Report:
- source page written
- topic pages created or updated
- backlink edits made
- control pages updated

## Common Mistakes

- ingesting from outside `kb/raw/`
- answering from memory instead of the source and wiki
- skipping the takeaway checkpoint
- skipping backlink work
- hardcoding a category instead of reading `REPO_WIKI_SPEC.md`
