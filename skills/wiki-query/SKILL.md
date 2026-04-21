---
name: wiki-query
description: Use when answering a question against a repo-local wiki. Read the wiki first, answer with citations, and offer to file the result.
---

# Wiki Query

Answer a question from the wiki, not from memory.

## Pre-condition

1. Find `kb/AGENTS.md`.
2. Find `kb/REPO_WIKI_SPEC.md`.
3. Read both files before answering.

## Process

### 1. Read `wiki/index.md` first

Use the index to find the relevant pages.

### 2. Read the relevant pages

Read the selected pages in full. Follow nearby wikilinks when they are clearly relevant.

### 3. Answer from the wiki

Write a response that:
- is grounded in the pages you read
- uses `[[wikilinks]]` as citations
- notes agreement, disagreement, and obvious gaps
- suggests follow-up ingest or update work when useful

### 4. Offer to file the answer

Ask whether the answer should be filed.

If approved:
- save it as `wiki/analyses/<slug>.md`
- use `type: analysis`
- use `category: analyses`
- set `sources` to the deduped raw source filenames from the cited pages
- update `wiki/index.md`
- append to `wiki/log.md`

If not approved:
- append a short query entry to `wiki/log.md`

## Common Mistakes

- answering from general knowledge
- skipping the index
- making uncited factual claims
- saving an answer without approval
