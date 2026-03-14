# Bug Fix Skill

> Scope-limited GitHub issue resolution — read the issue, touch only what's broken, and summarize what changed.

Built for agents and developers who need a disciplined, repeatable process for fixing bugs without scope creep.

---

## What It Does

Guides Claude through a structured, minimal-change bug fix workflow tied to a specific GitHub issue. It enforces reading the issue fully, understanding the codebase context from `CLAUDE.md`, touching only the relevant files, and delivering a clear summary of what changed and why.

---

## When To Use This Skill

- You've been assigned a GitHub issue to fix a bug or implement a small feature
- A coding agent needs a defined process to avoid unintended side effects
- You want a repeatable, auditable fix workflow with a built-in review checklist

**Trigger phrases:** "fix this issue", "resolve this bug", "implement this ticket", "patch this", "there's a regression in..."

---

## Process Overview

| Step | Action |
|---|---|
| 1 | Read the issue completely — scope, expected behavior, acceptance criteria |
| 2 | Read `CLAUDE.md` for architecture, conventions, and file map |
| 3 | Read only the files directly implicated by the issue |
| 4 | Make the minimal fix — no refactoring, no unrelated changes |
| 5 | Verify against acceptance criteria (or confirm the bug is gone) |
| 6 | Summarize changes, what was left alone, and any out-of-scope observations |

---

## Output

Every fix produces a structured summary:

```
## Changes Made
- [file]: [what changed and why]

## What I Did Not Change
- [anything intentionally left alone]

## Notes for Review
- [anything the reviewer should check or be aware of]
```

---

## Hard Rules

**Never do without explicit instruction:**
- Full file structure audits
- Refactoring outside the issue scope
- Adding npm/pip packages
- Changing working, unrelated code

**Always do:**
- Read `CLAUDE.md` before any source file
- Summarize changes at the end
- Flag out-of-scope issues rather than fixing them silently

---

## Skill File

[`SKILL_bug-fix.md`](SKILL_bug-fix.md)
