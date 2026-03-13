---
name: claudemd-generator
description: Generate a complete, production-ready CLAUDE.md file for any project. Use this skill whenever a user asks to create, generate, scaffold, or write a CLAUDE.md file, or when they want Claude to understand their codebase, set up AI context for a project, or configure Claude for agent workflows. Also trigger when a user mentions wanting better results from Claude in their repo, or says things like "Claude keeps making wrong assumptions about my project."
---

# CLAUDE.md Generator

A skill for generating complete, well-structured CLAUDE.md files tailored to a specific project.

## What is a CLAUDE.md?

A `CLAUDE.md` is a plain Markdown file placed in the root of a repository. Claude reads it automatically at the start of every session — no prompting required. It acts as an onboarding document for your AI collaborator: stack, architecture, conventions, anti-patterns, and agent instructions all in one place.

A good `CLAUDE.md` eliminates the need to re-establish context every session, reduces token waste, and produces more consistent, convention-aware output from Claude.

---

## Process

### Step 1: Gather Project Context

Before writing, collect the following. Extract what you can from the conversation or any files already shared. Ask the user only for what's missing.

**Required:**
- Project name and one-line description
- Primary language(s) and framework(s)
- Database and ORM (if any)
- Package manager
- Testing framework(s)

**Recommended:**
- High-level architecture (monolith, microservices, multi-service, etc.)
- Key directories and what lives in them
- Naming conventions (files, components, functions, variables)
- State management approach (if frontend)
- Error handling pattern
- Any files or directories that should never be modified by an agent

**Agent-specific (ask if project uses Claude as a coding agent):**
- What does a "completed issue" look like?
- Should agents do full file audits? (Default: NO — scope to the issue)
- Any CI checks that must pass before merge?

---

### Step 2: Write the CLAUDE.md

Use the template below. Fill in every section with the gathered context. Remove sections that don't apply. Never leave placeholder text in the output — either fill it in or omit the section entirely.

---

## CLAUDE.md Template

```markdown
# CLAUDE.md

> AI context file. Claude reads this automatically at the start of every session.

---

## Project Overview

**[Project Name]** — [One-line description of what the project does and who it's for.]

---

## Stack

| Layer | Technology |
|---|---|
| Framework | [e.g. Next.js 16, React 19, Express] |
| Language | [e.g. TypeScript strict, JavaScript ES2022] |
| Database | [e.g. PostgreSQL via Prisma 7] |
| Styling | [e.g. Tailwind CSS v4, inline styles] |
| Testing | [e.g. Vitest, Playwright, Mocha/Chai] |
| Package Manager | [e.g. pnpm, npm, yarn] |
| Runtime | [e.g. Node.js 20, Python 3.11] |

---

## Architecture

[2-4 sentences describing the high-level structure. Examples:]
- "Monolithic Next.js App Router application. All DB routes are force-dynamic. Business logic lives in /lib. Components in /components."
- "Three-service architecture: React frontend (port 3000), Node/Express backend (port 5000), Python FastAPI AI service (port 8000)."
- "Single-file React component intentionally. Do not split."

---

## Directory Structure

[project-root]/
├── [key directory] — [what lives here]
├── [key directory] — [what lives here]
└── [key directory] — [what lives here]

---

## Conventions

### Naming
- [e.g. Components: PascalCase. Utilities: camelCase. Files: kebab-case.]
- [e.g. Database models: PascalCase. Table names: snake_case plural.]

### Components / Modules
- [e.g. Use named exports for all components.]
- [e.g. Co-locate tests with the files they test.]
- [e.g. One component per file.]

### State Management
- [e.g. Local state via useState. Global state via Zustand. No Redux.]

### Error Handling
- [e.g. Result pattern — no raw throws in business logic.]
- [e.g. All API errors return { error: string, status: number }.]

### Styling
- [e.g. Tailwind utility classes only. No custom CSS files.]
- [e.g. Accent color: #f97316. Dark theme background: #0a0d14.]

---

## Anti-Patterns

These must never happen without explicit instruction:

- [ ] Do not split single-file components
- [ ] Do not install new dependencies without flagging them first
- [ ] Do not modify [specific protected file or directory]
- [ ] Do not add inline styles if Tailwind classes exist for the purpose
- [ ] Do not change function signatures unless the task requires it
- [ ] Do not refactor code outside the scope of the current task

---

## Agent Instructions

These rules apply when Claude is assigned to a GitHub issue or automated task:

- **Scope:** Work only within the files relevant to the current issue. Do not audit unrelated files.
- **Completion criteria:** A task is complete when [e.g. lint, typecheck, and tests pass].
- **Flag before proceeding if:** The fix requires touching more than [N] files, or a new dependency is needed.
- **Commit style:** [e.g. conventional commits — feat:, fix:, chore:, docs:]
- **Do not:** Open new issues, modify CI config, or change package.json scripts without explicit instruction.

---

## Running the Project

```bash
# Install dependencies
[install command]

# Start development server
[dev command]

# Run tests
[test command]

# Build for production
[build command]


---

## Notes

[Any additional context that doesn't fit above. Examples: known quirks, external services, environment variable requirements, deployment targets.]

```
---

### Step 3: Review and Deliver

- Present the completed CLAUDE.md in a code block for easy copying
- Also save it as a downloadable file if the `present_files` tool is available
- Remind the user: an imperfect CLAUDE.md today is worth more than a perfect one never written — they can refine it as the project evolves

---

## Rules

- Never leave placeholder text in the output. Fill it in or remove the section.
- Keep the Anti-Patterns section as a checklist — it's easier to scan.
- The Agent Instructions section is optional but strongly recommended for any project using Claude as a coding agent.
- CLAUDE.md should read like it was written by the lead developer on the project, not generated by AI.
- Prefer concrete specifics over vague generalities. "Use named exports" is better than "follow good export practices."
