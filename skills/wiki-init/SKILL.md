---
name: wiki-init
description: Use when bootstrapping a repo-local wiki in a software development repository.
---

# Wiki Init

Bootstrap a new `kb/` wiki for a software repository using the universal schema plus a minimal repo-local spec.

## Pre-flight

If `kb/AGENTS.md` already exists nearby, confirm whether the user wants to reinitialize or continue with the existing wiki.

## Gather minimal configuration

Ask only for:
1. repo name
2. one-sentence wiki purpose
3. active topic categories and their order

Use the universal defaults for everything else.

## Create the structure

Create:

```text
kb/
  AGENTS.md
  REPO_WIKI_SPEC.md
  raw/
  wiki/
    index.md
    log.md
    overview.md
    glossary.md
    sources/
    analyses/
    <repo category dirs>
```

## Write the docs

- `AGENTS.md` should contain the universal wiki rules
- `REPO_WIKI_SPEC.md` should contain only repo-local configuration
- the seed pages under `wiki/` should match the universal schema exactly

Do not invent a second schema in the skill. The generated files must match the current universal contract.

## Confirm

Tell the user:
- where the wiki was initialized
- which categories were configured
- that new source documents must be imported into `kb/raw/`
- that the other wiki skills will read both `AGENTS.md` and `REPO_WIKI_SPEC.md`

## Common Mistakes

- hardcoding repo-local details into `AGENTS.md`
- omitting `REPO_WIKI_SPEC.md`
- creating a flat `wiki/pages/` layout
- generating seed files that do not match the universal schema
