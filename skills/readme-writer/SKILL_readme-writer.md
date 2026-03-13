---
name: readme-writer
description: Generate a complete, professional README.md for any project or repository. Use this skill whenever a user asks to write, create, generate, or improve a README file. Also trigger when a user says their repo needs documentation, wants to polish their GitHub profile, is preparing a project for public release, or mentions that their project "doesn't have a README yet." If a user shares a project description, codebase context, or CLAUDE.md and wants a README, use this skill immediately.
---

# README Writer

A skill for generating complete, professional, and human-feeling README files tailored to a specific project.

## What Makes a Good README?

A good README does three things:
1. Tells a visitor what the project is and why it exists — in under 30 seconds
2. Gets a developer from zero to running in as few steps as possible
3. Communicates that the person who built this knows what they're doing

A bad README is either a wall of boilerplate no one reads, or a stub that says "coming soon." Both are worse than a well-written one-pager.

---

## Process

### Step 1: Gather Project Context

Extract what you can from the conversation, any uploaded files, or a CLAUDE.md if present. Ask the user only for what's missing.

**Required:**
- Project name
- What it does (one sentence)
- Who it's for
- Primary tech stack
- How to install and run it

**Recommended:**
- Screenshots or demo link (ask if it's a UI project)
- Key features (3-5 max)
- Architecture overview (for technical projects)
- Contributing guidelines (if open source)
- License

**Nice to have:**
- Badges (build status, npm version, license)
- Roadmap or "coming soon" features
- Motivation / origin story (1-2 sentences — makes it human)

---

### Step 2: Write the README

Use the template below as the structure. Adapt sections based on the project type:

- **CLI tool** → emphasize installation and usage examples
- **Web app** → emphasize features, screenshots, and live demo link
- **Library/package** → emphasize API, code examples, and installation
- **Internal tool** → emphasize setup, purpose, and who maintains it
- **Teaching project** → emphasize what it demonstrates and how to explore it

Never include a section just to have it. A focused 1-page README beats a sprawling 5-page one every time.

---

## README Template

```markdown
# [Project Name]

> [One-line description. What it does. Who it's for. Make it count.]

[Optional: 1-2 sentence origin story or motivation. Why does this exist?]

---

## Features

- [Feature 1 — describe the value, not just the function]
- [Feature 2]
- [Feature 3]

---

## Tech Stack

| Layer | Technology |
|---|---|
| [Layer] | [Technology] |
| [Layer] | [Technology] |

---

## Getting Started

### Prerequisites

- [Requirement 1, e.g. Node.js 20+]
- [Requirement 2, e.g. PostgreSQL running locally]

### Installation

```bash
# Clone the repo
git clone https://github.com/[username]/[repo-name]
cd [repo-name]

# Install dependencies
[install command]

# Set up environment variables
cp .env.example .env
# Edit .env with your values

# Run the project
[start command]
```

---

## Usage

[Short description of how to use the project once it's running.
For CLIs: show command examples.
For web apps: describe the main workflow.
For libraries: show a code snippet.]

```[language]
[example code or command]
```

---

## Architecture

[Optional — include for technical projects or multi-service apps.
1-3 sentences or a simple diagram describing how the pieces fit together.]

---

## Screenshots

[Optional — include for any project with a UI.]

---

## Roadmap

- [ ] [Planned feature 1]
- [ ] [Planned feature 2]

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## License

[MIT](LICENSE) — or specify the appropriate license.
```

---

### Step 3: Tone Check

Before delivering, read the README back and ask:

- Does the first sentence tell me exactly what this is?
- Would a developer trust this project based on this README alone?
- Is there anything here that exists just to fill space?

Cut anything that doesn't pass. A README that's 60% of this template but tight is better than one that's 100% of it and padded.

---

### Step 4: Deliver

- Present the completed README in a code block for easy copying
- Save it as a downloadable file if the `present_files` tool is available
- If the project has a UI, remind the user to add screenshots — it's the single highest-ROI addition to any README

---

## Rules

- Never use filler phrases like "This project aims to..." or "This is a tool that..."
- The first line after the project name should be a `>` blockquote — short, punchy, specific
- Use tables for the tech stack — easier to scan than a bulleted list
- Code blocks for every install/run command, no exceptions
- If the user has a CLAUDE.md, use it as the primary source of truth for stack and architecture
- Match the tone to the project: a terminal chess game can have personality; an internal EOS reporting tool should be clear and professional
