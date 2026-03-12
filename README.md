# ai-workflow-toolkit

> Reusable Claude skills and CLAUDE.md templates that make AI-assisted development actually consistent.

Most AI coding sessions start the same way: re-explain the stack, re-establish conventions, watch the model make the same wrong assumptions it made yesterday. This repo fixes that. Drop a skill into your workflow or a CLAUDE.md into your repo, and Claude starts every session with the context it needs to be useful.

---

## Features

- **Ready-to-use skills** — structured instructions that guide Claude through specific tasks like writing READMEs, generating CLAUDE.md files, and fixing bugs from GitHub issues
- **CLAUDE.md templates** — starter templates so Claude understands your project from the first prompt
- **No dependencies, no build step** — pure Markdown, copy what you need

---

## What's Included

### Skills

| Skill | Description |
|---|---|
| [claudemd-generator](skills/claudemd-generator/SKILL_claudemd-generator.md) | Generate a complete, production-ready CLAUDE.md for any project |
| [readme-writer](skills/readme-writer/SKILL_readme-writer.md) | Generate a professional README.md tailored to a specific project |
| [bug-fix](skills/bug-fix/SKILL_bug-fix.md) | Fix GitHub issues with a disciplined, scope-limited process |

### Templates

| Template | Description |
|---|---|
| [CLAUDE.md](templates/CLAUDE.md) | Starter CLAUDE.md template for any repository |

---

## Getting Started

### Prerequisites

- A project where you use [Claude](https://claude.ai) for development
- That's it

### Installation

```bash
# Clone the repo
git clone https://github.com/southwestmogrown/ai-workflow-toolkit.git
cd ai-workflow-toolkit
```

No install commands, no environment variables. Everything here is Markdown.

---

## Usage

### Using a Skill

Skills are self-contained instruction sets. Copy a skill file into your project or reference it directly when prompting Claude.

```
Use the readme-writer skill located at /skills/readme-writer/SKILL_readme-writer.md
to generate the README for my project.
```

Each skill defines when it should be triggered, the process to follow, a template for output, and hard rules to keep results consistent.

### Using a Template

Copy a template into your project root and fill it in:

```bash
cp templates/CLAUDE.md /path/to/your/project/CLAUDE.md
```

Claude reads `CLAUDE.md` automatically at the start of every session — no extra prompting required.

---

## Project Structure

```
ai-workflow-toolkit/
├── skills/
│   ├── bug-fix/
│   │   └── SKILL_bug-fix.md
│   ├── claudemd-generator/
│   │   └── SKILL_claudemd-generator.md
│   └── readme-writer/
│       └── SKILL_readme-writer.md
├── templates/
│   └── CLAUDE.md
├── LICENSE
└── README.md
```

---

## Contributing

Pull requests are welcome. If you've built a skill that makes Claude better at a repeatable task, open a PR. For major changes, please open an issue first to discuss what you'd like to change.

**Skill file conventions:**
- One skill per directory under `skills/`
- File name format: `SKILL_[skill-name].md`
- Include a clear trigger description, step-by-step process, output template, and hard rules

---

## License

[MIT](LICENSE)
