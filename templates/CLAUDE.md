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

```
[project-root]/
├── [key directory] — [what lives here]
├── [key directory] — [what lives here]
└── [key directory] — [what lives here]
```

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
```

---

## Notes

[Any additional context that doesn't fit above. Examples: known quirks, external services, environment variable requirements, deployment targets.]
