# AGENTS.md — Vault Operating Manual

This vault is the long-term memory for AI agents.

## Runtime vs. skills

This vault is the **runtime memory** (what you know). **Executable procedures live in
skills**, catalogued under `$BRAIN_SKILLS_DIR` (see `skills/skills-library.md` if present).
"Load the brain" means read this vault for context; "use a skill" means run a specific
procedure from the skills directory. Don't hardcode skill paths — resolve them from
`$BRAIN_SKILLS_DIR`.

## Read Recipe

1. Read `index.md`.
2. Pick 1-3 relevant pages.
3. Read each page's `summary:` first.
4. Open full bodies only when needed.
5. Cite used pages as `[[page-name]]`.

## Write Recipe

1. Create atomic notes: one idea per page.
2. Use frontmatter with `title`, `category`, `tags`, `sources`, `summary`, `created`, `updated`.
3. Add at least one `[[wikilink]]` to an existing page.
4. Update `index.md`, `hot.md`, and `log.md`.
5. Run `python3 _meta/validate.py`.
6. Periodically run `python3 _meta/dedup.py` and merge or cross-link any flagged
   duplicate pairs (the detector only suggests; you decide and merge).

## Skill scorecards

Skills under `$BRAIN_SKILLS_DIR` carry a scorecard in their frontmatter — this vault is a
*rated skills library*, not just notes:

```yaml
uses: 0          # bumped by `brain skill use <name>` when you apply it
score: 0.0       # running average quality vote (1–5)
votes: 0
last_used: '-'
```

After applying a skill, run `brain skill use <name>`; vote on quality with
`brain skill rate <name> <1-5> [note]`. `brain skill list` ranks the library by value.

## Categories

- `concepts/` — mental models and principles.
- `references/` — how-to notes and source summaries.
- `synthesis/` — maps of content.
- `skills/` — skill catalogs and procedures.
- `projects/` — project-specific overview notes.
- `entities/` — people, tools, products, roles.
- `journal/` — dated observations.

