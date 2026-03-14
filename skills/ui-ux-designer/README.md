# UI/UX Designer Skill — Developer Tools

> Interface design for tools developers actually use — information-dense, visually calm, keyboard-first, built for long sessions.

Grounded in documented pain points from real developer tool usage. Makes things disappear until the user needs them, not pop.

---

## What It Does

Produces structured design briefs for developer-facing interfaces: dashboards, CLIs, IDEs, monitoring tools, data explorers, and productivity apps. Covers visual foundation (palette, typography, spacing), component specifications, long-session ergonomics, and a validation checklist against known developer tool pain points.

---

## When To Use This Skill

- Designing a new developer tool interface from scratch
- Redesigning an existing tool based on user complaints
- Critiquing a UI that feels wrong but you can't articulate why
- Establishing a design system for a developer-facing product

**Trigger phrases:** "design this dashboard", "redesign this UI", "what's wrong with this interface?", "developer tool UX", "make this less overwhelming", "design the settings panel", "keyboard navigation"

---

## Process Overview

| Step | Action |
|---|---|
| 1 | Identify tool category — dashboard, IDE, CLI, data explorer, project management, or settings |
| 2 | Audit existing pain points — list every user complaint before proposing a solution |
| 3 | Define the visual foundation — palette, type scale, spacing unit, elevation model |
| 4 | Design for the long session — apply ergonomic rules to every component |
| 5 | Specify components — purpose, state inventory, keyboard behavior, data density, responsive behavior |
| 6 | Validate against the pain points checklist |

---

## Common Developer Tool Pain Points Addressed

| Pain point | Fix |
|---|---|
| Too-sparse dashboards force excessive scrolling | 60% viewport for primary data; secondary context at the periphery |
| Dark mode that's just an inverted light theme | Design on `#0D1117` base; one accent, semantic color only |
| Animations over 200ms — most common complaint in dev tool reviews | Cap at 120ms ease-out; never animate repeated actions |
| Three-click navigation to frequently-used views | Surface top 5 actions; everything else behind `⌘K` command palette |
| Flat configuration lists with no grouping | Group by domain, show sane defaults, inline validation |
| Truncated important columns in tables | User-resizable, ordered by usage frequency, monospace for IDs/timestamps |
| Generic "Something went wrong" errors | Every error answers: what happened, why, what to do next |

---

## Output Format

```
## Interface: [Name]

### Category
### User Pain Points Addressed
### Visual Foundation
### Layout
### Component Specs
### Long-Session Notes
### What Was Deliberately Omitted
```

---

## Hard Rules

**Never do:**
- More than one accent color unless each has a distinct semantic meaning
- Animate loading states that resolve in under 300ms
- Navigation structures deeper than three levels
- Color alone to convey state — pair with an icon or label
- Mobile-first for tools used exclusively on desktop

**Always do:**
- Keyboard navigation on every interactive element
- Command palette entry point for power users
- Specify exact hex values, not descriptors like "dark gray"
- Design the default state to be visually calm — energy is reserved for alerts and focus

---

## Skill File

[`SKILL_ui-ux-designer.md`](SKILL_ui-ux-designer.md)
