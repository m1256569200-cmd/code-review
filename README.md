# code-review

An agent skill for structured, no-noise code reviews. Give it a diff, branch, or PR and get findings grouped by severity — blockers first, nits last, zero invented problems.

## Install

Copy `SKILL.md` into your skills folder, e.g.:

- Claude Code: `~/.claude/skills/code-review/SKILL.md`
- Cursor: `.cursor/skills/code-review/SKILL.md` (project) or `~/.cursor/skills/` (global)

Then ask your agent: "review this PR" or "review my changes before I merge".

## What it does

Three passes in order — **correctness**, **security**, **maintainability** — then reports:

```
## 🔴 Blockers (must fix)
- `api/users.ts:42` — missing auth check on DELETE /users/:id …

## 🟡 Suggestions (consider)
- …

## 🟢 Nits (optional)
- …
```

Every finding cites a file and line. If the code is clean, it says so in one line instead of inventing issues. Formatting is left to linters.

## License

MIT
