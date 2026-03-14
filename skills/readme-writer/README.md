# README Writer Skill

> Generate complete, professional README files that tell visitors what a project is, get developers running in minutes, and build trust — without boilerplate padding.

A README is the first thing anyone reads. This skill makes sure it's worth reading.

---

## What It Does

Gathers project context — name, purpose, stack, install steps, and usage — then writes a focused, professional README tailored to the project type. Adapts structure based on whether the project is a CLI tool, web app, library, internal tool, or teaching project. Cuts sections that don't carry weight.

---

## When To Use This Skill

- Creating a README for a new or existing project
- Improving a stub README that says "coming soon"
- Polishing a project before public release or open sourcing
- Documenting a project for teammates or contributors

**Trigger phrases:** "write a README", "create documentation", "my repo needs a README", "polish this for GitHub", "preparing for public release", "it doesn't have a README yet"

---

## Process Overview

| Step | Action |
|---|---|
| 1 | Gather project context — extract from conversation, files, or `CLAUDE.md`; ask only for what's missing |
| 2 | Write the README — use the template, adapt sections to the project type, cut anything that doesn't carry weight |
| 3 | Tone check — first sentence explains what it is, a developer would trust the project based on this alone |
| 4 | Deliver — present in a code block; remind the user to add screenshots if the project has a UI |

---

## README Sections

| Section | Included when |
|---|---|
| Project name + tagline | Always |
| Features | The project has 3+ distinct value points |
| Tech Stack | Always (table format) |
| Prerequisites | There are non-obvious setup requirements |
| Installation | Always |
| Usage | Always — adapted to project type |
| Architecture | Technical projects with meaningful structure |
| Screenshots | Any project with a UI |
| Roadmap | Active projects with planned features |
| Contributing | Open source projects |
| License | Always |

---

## Project Type Adaptations

| Type | Emphasis |
|---|---|
| CLI tool | Installation and usage examples with command snippets |
| Web app | Features, screenshots, and live demo link |
| Library/package | API reference, code examples, installation |
| Internal tool | Setup, purpose, and who maintains it |
| Teaching project | What it demonstrates and how to explore it |

---

## Rules

- The first line after the project name must be a `>` blockquote — short, punchy, specific
- Never use filler phrases like "This project aims to..." or "This is a tool that..."
- Code blocks for every install and run command, no exceptions
- Use tables for the tech stack
- A focused one-page README beats a sprawling five-page one every time
- If the user has a `CLAUDE.md`, use it as the primary source of truth

---

## Skill File

[`SKILL_readme-writer.md`](SKILL_readme-writer.md)
