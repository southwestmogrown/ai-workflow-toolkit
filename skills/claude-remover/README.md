# Claude / AI Artifact Remover Skill

> Pre-deploy cleanup for AI development residue — scan, categorize, confirm, then remove.

Finds and strips the files, comments, and code patterns that AI tools leave behind during development so they never reach production.

---

## What It Does

Runs a systematic scan of a codebase for AI-generated artifacts: instruction files (`CLAUDE.md`, `.cursorrules`), hardcoded API keys and model strings, debug prompts, over-verbose AI comments, and tool-specific config. Presents every hit in a categorized report before touching anything. Nothing is deleted without explicit confirmation.

---

## When To Use This Skill

- Before a production deploy or public release
- When auditing a codebase for AI development leftovers
- After an extended AI-assisted development session
- When the team wants to verify `.gitignore` covers all AI tooling artifacts

**Trigger phrases:** "going to production", "prod deploy", "clean up AI stuff", "remove Claude artifacts", "pre-deploy cleanup", "strip dev artifacts", "what AI files shouldn't ship?"

---

## Process Overview

| Step | Action |
|---|---|
| 1 | Scan — find AI config files, hardcoded keys, AI comment patterns, debug prompts, hardcoded model strings |
| 2 | Categorize every hit: Safe to Delete / Needs Edit / Flag Only |
| 3 | Present the full hit list, grouped by bucket, before taking any action |
| 4 | Execute safe deletes — only after explicit user confirmation |
| 5 | Execute edits — show before/after diff for each, confirm before writing |
| 6 | Verify `.gitignore` covers all artifact patterns |
| 7 | Run a second scan pass to confirm the project is clean |

---

## Hit List Format

```
── AI ARTIFACT SCAN RESULTS ─────────────────────────────────────

SAFE TO DELETE (confirm to remove)
  ./CLAUDE.md                          AI instruction file
  ./.cursorrules                       Cursor IDE config

NEEDS EDIT (will show diffs)
  ./src/lib/ai.ts : 12                 Hardcoded model string → use process.env.CLAUDE_MODEL

FLAG ONLY (review manually)
  ./.env.local : 3                     Possible API key — verify it's in .gitignore

────────────────────────────────────────────────────────────────
```

---

## What This Skill Does NOT Remove

- `CLAUDE.md` files inside `.github/` that are genuinely part of repo documentation
- AI feature code itself (chat UI, API calls, prompt logic) — that's the product
- Type definitions or imports from `@anthropic-ai/sdk` — those are runtime deps
- Test files that test AI features

When in doubt, it flags rather than deletes.

---

## References

- [`SKILL_claude-remover.md`](SKILL_claude-remover.md) — full skill definition
- [`artifact-types.md`](artifact-types.md) — complete catalogue of AI tool artifacts by tool (Claude, Cursor, Copilot, Aider, Continue, Codeium, Tabnine)
