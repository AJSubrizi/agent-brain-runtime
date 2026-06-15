# Changelog

## Unreleased

- `validate.py` now warns on knowledge rot in addition to integrity errors:
  orphan notes (no links in or out), notes missing from `index.md`, and
  `category` frontmatter that does not match the folder. Warnings do not fail CI.

## 0.1.0

- Initial public starter kit.
- Added `brain` shim.
- Added vault skeleton.
- Added global AGENTS/CLAUDE/GEMINI templates.
- Added RTK recommendation docs.

