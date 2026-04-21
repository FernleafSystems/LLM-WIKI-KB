# LLM-WIKI-KB

Portable repo-local wiki/knowledge-base pattern for software development repositories.

This is a small system for keeping durable project knowledge in a structured place that an LLM can read, maintain, and query without repeatedly digging through raw documents.

It is inspired by Andrej Karpathy's LLM wiki idea. A local copy of that note is included at [ref/karpathy-llm-wiki.md](ref/karpathy-llm-wiki.md).

## What This Is

- `kb/AGENTS.md` defines the universal wiki rules and page schema.
- `kb/REPO_WIKI_SPEC.md` defines the minimal repo-local configuration.
- `kb/raw/` stores imported source documents.
- `kb/wiki/` stores the maintained wiki pages.
- `skills/` contains the workflow skills for init, ingest, query, update, and lint.

## How It Works

1. Import source material into `kb/raw/`.
2. Use the wiki skills to turn those raw documents into structured wiki pages under `kb/wiki/`.
3. Keep durable summaries, concepts, plans, and analyses cross-linked and up to date.
4. Query the wiki first, then file useful answers back into it when appropriate.

The split is deliberate:

- `kb/AGENTS.md` stays generic and reusable across repos.
- `kb/REPO_WIKI_SPEC.md` is the only file you should usually need to tailor for a new repo.

## Add It To Another Repo

1. Copy `kb/` into the target repository.
2. Install the wiki skills from `skills/` into that repo's `.codex/skills/`, or adapt them to your agent runtime.
3. Update `kb/REPO_WIKI_SPEC.md` for that repo.
4. Add a short reference in the target repo's top-level `AGENTS.md` pointing agents to `kb/AGENTS.md`, `kb/REPO_WIKI_SPEC.md`, and `kb/wiki/index.md`.
5. Import documents into `kb/raw/`.
6. Start using the wiki skills.

## Notes

- Keep the repo spec small.
- Keep source documents immutable once placed in `kb/raw/`.
- Add new topic categories only when the repo shows real need for them.
