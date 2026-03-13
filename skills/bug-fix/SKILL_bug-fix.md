# Skill: GitHub Issue Bug Fix

## When To Use This Skill
When assigned a GitHub issue to fix a bug, implement a small feature,
or make a targeted change to an existing codebase.

---

## Process — Follow In Order

### Step 1: Read the issue completely
Understand the full scope before touching any file.
Identify:
- What is broken or missing?
- What is the expected behavior?
- What files are likely involved?
- Are there acceptance criteria? If so, treat them as your definition of done.

### Step 2: Read CLAUDE.md
Always read the project's CLAUDE.md (or copilot-instructions.md) before
reading any source files. It contains:
- Architecture decisions you must not violate
- File map so you know exactly where to look
- Conventions to follow
- Current project state

### Step 3: Read only relevant files
Read ONLY the files directly implicated by the issue.
Do NOT audit the full file structure.
Do NOT read files "just in case."
The CLAUDE.md file map tells you what lives where.

### Step 4: Make the minimal fix
- Change only what the issue requires
- Do not refactor working code while you're in the file
- Do not rename things that aren't broken
- Do not add abstractions that weren't asked for
- If you notice other bugs while fixing this one — note them, don't fix them

### Step 5: Verify against acceptance criteria
Before finishing, check each acceptance criterion in the issue.
If any are not met, continue working.
If the issue has no acceptance criteria, verify the original
bug is fixed and nothing adjacent is broken.

### Step 6: Summarize your changes
Output a brief summary:
```
## Changes Made
- [file]: [what changed and why]

## What I Did Not Change
- [anything you intentionally left alone]

## Notes for Review
- [anything the reviewer should check or be aware of]
```

---

## Hard Rules

**Never do these without explicit instruction:**
- Full file structure audits
- Refactoring outside the issue scope
- Adding npm/pip packages
- Changing working, unrelated code
- Splitting files that were intentionally single-file
- Adding new state management patterns
- Changing styling conventions mid-project

**Always do these:**
- Read CLAUDE.md first
- Summarize changes at the end
- Flag anything that looks wrong but is out of scope
- Ask if the issue is ambiguous rather than guessing

---

## Code Review Checklist
After generating a fix, verify:
- [ ] Only issue-relevant files were modified
- [ ] Existing conventions are preserved (check CLAUDE.md)
- [ ] No new dependencies added without flagging
- [ ] No unrelated refactoring
- [ ] Fix actually addresses the stated issue
- [ ] Summary is included
