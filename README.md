# ai-workflow-toolkit

> Reusable Claude skills and CLAUDE.md templates that make AI-assisted development actually consistent.

Most AI coding sessions start the same way: re-explain the stack, re-establish conventions, watch the model make the same wrong assumptions it made yesterday. This repo fixes that. Drop a skill into your workflow or a CLAUDE.md into your repo, and Claude starts every session with the context it needs to be useful.

---

## Features

- **Ready-to-use skills** — structured instructions that guide Claude through specific tasks like writing READMEs, generating CLAUDE.md files, fixing bugs, reviewing code, and editing content
- **CLAUDE.md templates** — starter templates so Claude understands your project from the first prompt
- **Workflow resources** — standalone files for idea tracking, retros, deploy checklists, commit conventions, and more
- **No dependencies, no build step** — pure Markdown, copy what you need

---

## What's Included

### Skills

| Skill | Description |
|---|---|
| [claudemd-generator](skills/claudmd-generator/SKILL_claudemd-generator.md) | Generate a complete, production-ready CLAUDE.md for any project |
| [readme-writer](skills/readme-writer/SKILL_readme-writer.md) | Generate a professional README.md tailored to a specific project |
| [bug-fix](skills/bug-fix/SKILL_bug-fix.md) | Fix GitHub issues with a disciplined, scope-limited process |
| [code-review](skills/code-review/SKILL_code-review.md) | Review code critically and return a structured PASS or FAIL with actionable feedback |
| [content-editor](skills/content-editor/SKILL_content-editor.md) | Edit and improve written content with SEO optimization and AI slop elimination |

### Templates

| Template | Description |
|---|---|
| [CLAUDE.md](templates/CLAUDE.md) | Starter CLAUDE.md template for any repository |

### Workflow Resources

Standalone files you can drop into any project to support a repeatable solo dev workflow.

| Resource | Description |
|---|---|
| [IDEA.md](workflow-resources/IDEA.md) | Idea backlog — dump ideas fast, triage weekly |
| [RETRO.md](workflow-resources/RETRO.md) | Retro log — one sentence per deploy, review monthly |
| [github-issue-template.md](workflow-resources/github-issue-template.md) | GitHub issue template for features with scope, non-goals, and done criteria |
| [commit-cheatsheet.html](workflow-resources/commit-cheatsheet.html) | Commit message cheat sheet — conventional commits reference |
| [deploy-checklist.html](workflow-resources/deploy-checklist.html) | Pre-deploy checklist — catch the things that always get missed |
| [workflow-diagram.html](workflow-resources/workflow-diagram.html) | Solo dev workflow diagram — visual overview of the full development cycle |

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

### Using a Workflow Resource

Copy any file from `workflow-resources/` into your project:

```bash
cp workflow-resources/IDEA.md /path/to/your/project/IDEA.md
cp workflow-resources/deploy-checklist.html /path/to/your/project/deploy-checklist.html
```

Open the HTML files directly in a browser. The Markdown files work as standalone documents in any editor.

---

## Project Structure

```
ai-workflow-toolkit/
├── skills/
│   ├── bug-fix/
│   │   └── SKILL_bug-fix.md
│   ├── claudmd-generator/
│   │   └── SKILL_claudemd-generator.md
│   ├── code-review/
│   │   └── SKILL_code-review.md
│   ├── content-editor/
│   │   └── SKILL_content-editor.md
│   └── readme-writer/
│       └── SKILL_readme-writer.md
├── templates/
│   └── CLAUDE.md
├── workflow-resources/
│   ├── IDEA.md
│   ├── RETRO.md
│   ├── commit-cheatsheet.html
│   ├── deploy-checklist.html
│   ├── github-issue-template.md
│   └── workflow-diagram.html
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
