---
name: wiki-update
description: Use when revising existing wiki pages because information changed, a source contradicts the current wiki, or the user wants to edit wiki content directly.
---

# Wiki Update

Revise existing wiki pages carefully. Show the change, the reason, and the source before writing.

## Pre-condition

1. Find `kb/AGENTS.md`.
2. Find `kb/REPO_WIKI_SPEC.md`.
3. Read both files before updating anything.

## Process

### 1. Identify the target pages

The user may provide:
- specific page names
- new information that affects existing pages
- a lint result that points to pages needing updates

Read the current target pages in full.

### 2. Propose the change

For each page, show:

- Current
- Proposed
- Reason
- Source

Ask for confirmation before writing each page.

### 3. Check downstream effects

Search the full wiki for pages that link to or depend on the updated page.

If another page may now be stale or contradictory, flag it and offer to update it too.

### 4. Run a contradiction sweep

If the change corrects or replaces a claim, search the wiki for other occurrences of that claim and update them as needed.

### 5. Update control pages when needed

- update `wiki/index.md` if summaries or page placement changed
- update `wiki/overview.md` if the overall synthesis changed
- append to `wiki/log.md`

## Common Mistakes

- updating without a source
- updating one page while leaving dependent pages stale
- searching only one category directory
- batching multiple writes without clear confirmation
