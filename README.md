# changelog-gen

An agent skill that turns git history into a clean, human-readable changelog entry. No more staring at 40 commit messages trying to write release notes.

## Install

Copy `SKILL.md` into your skills folder, e.g.:

- Claude Code: `~/.claude/skills/changelog-gen/SKILL.md`
- Cursor: `.cursor/skills/changelog-gen/SKILL.md` (project) or `~/.cursor/skills/` (global)

Then ask your agent: "write a changelog entry for the last release" or "summarize what changed since v1.3.0".

## What it does

1. Reads the commit range (since last tag, or whatever range you give it).
2. Groups by intent — Added / Fixed / Changed — not by commit.
3. Merges duplicates, drops noise (merge commits, trivial chores), writes for humans.
4. Outputs a Markdown section ready to paste under `## [Unreleased]`:

```markdown
## [1.4.0] - 2026-10-12

### Added
- OAuth2 refresh token rotation (#128)

### Fixed
- Crash when uploading files over 100MB (#131)
```

Large ranges get themed summaries instead of endless bullet lists.

## License

MIT
