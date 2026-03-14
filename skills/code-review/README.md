# Code Review Skill

> A quality gate that returns PASS or FAIL with specific, actionable feedback — not vibes.

Built for agent workflows and manual review tasks where "looks fine to me" is not an acceptable output.

---

## What It Does

Applies a senior engineer's review lens to any submitted code. Checks for correctness, edge cases, readability, and side effects — universally, regardless of language or framework. Pulls additional criteria from the project's `CLAUDE.md` to enforce project-specific conventions, architecture patterns, and anti-patterns.

Returns exactly one verdict: **PASS** with a brief justification, or **FAIL** with specific, located, actionable feedback for every issue found.

---

## When To Use This Skill

- As a quality gate step in an agent workflow before code proceeds
- When reviewing AI-generated code before merging
- Any time you need a structured, consistent review that goes beyond syntax

**Trigger phrases:** "review this code", "is this ready to merge?", "check this before I ship it", "quality gate", "evaluate this implementation"

---

## What Gets Checked

### Always (universal criteria)

| Criterion | What's Evaluated |
|---|---|
| Correctness | Does it do what it's supposed to? Does it handle failure? |
| Edge cases | Empty input, null values, unexpected types, off-by-one conditions |
| Readability | Can another developer understand this without asking questions? |
| Side effects | Does it modify state it doesn't own? Make calls it wasn't asked to make? |

### From project context (`CLAUDE.md`)

- Language and framework conventions
- Architectural patterns to enforce or avoid
- Specific APIs or libraries in use
- Anti-patterns explicitly called out in `CLAUDE.md`

---

## Output Format

**PASS**
```
Brief justification (1–2 sentences). What makes this code acceptable.
```

**FAIL**
```
- What the problem is
- Where it is (function name, line reference, or code snippet)
- What the fix should be
```

Vague feedback is not returned. "This could be improved" is not actionable. "The retry loop on line 24 has no exit condition — add a max_retries check before the recursive call" is.

---

## Skill File

[`SKILL_code-review.md`](SKILL_code-review.md)
