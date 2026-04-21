---
name: wiki-lint
description: Use when auditing a repo-local wiki for contradictions, broken links, stale claims, orphan pages, missing cross-links, or schema drift.
---

# Wiki Lint

Audit the wiki, report concrete findings, offer fixes, and log the result.

## Pre-condition

1. Find `kb/AGENTS.md`.
2. Find `kb/REPO_WIKI_SPEC.md`.
3. Read both files before linting.

## Process

### 1. Build the inventory

Read:
- `wiki/index.md`
- `wiki/overview.md`
- `wiki/glossary.md`
- all other markdown pages under `wiki/`

Build a map of:
- existing pages
- page types
- categories
- wikilinks
- raw source filenames listed in frontmatter

### 2. Run the checks

Report:
- broken wikilinks
- frontmatter missing required fields
- invalid `type` values
- invalid or mismatched `category` values against the universal categories and the repo-defined topic categories
- pages in the wrong directory for their category
- orphan pages
- contradictions
- stale claims
- missing cross-links
- signs that a new repo category may be needed

### 3. Report findings before writing

Show a categorized report in the chat first.

If the user wants the report filed, save it as an `analysis` page under `wiki/analyses/` and update `wiki/index.md`.

### 4. Offer concrete fixes

For local, fixable issues, offer the exact fixes and apply only what the user approves.

### 5. Update the log

Append a lint entry to `wiki/log.md`.

## Common Mistakes

- scanning only one content directory
- inventing schema fields that are not defined in `AGENTS.md`
- auto-creating topic categories that are not in `REPO_WIKI_SPEC.md`
- treating a lint artifact as mandatory when the user did not approve filing it
