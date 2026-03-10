# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

This is the **skills** repository — a collection of Claude Code skills for project analysis and developer workflow automation. Licensed under MIT.

## Repository Structure

```
skills/
├── scan-to-skill/          # Project scanner skill (v1, manually written)
│   ├── SKILL.md
│   └── references/
│       ├── detection-patterns.md
│       └── skill-query-templates.md
├── skill-scanner/         # Project scanner skill (v2, built with skill-creator)
│   ├── SKILL.md
│   └── references/
│       ├── detection-patterns.md
│       └── skill-query-templates.md
├── CLAUDE.md
├── README.md
├── LICENSE
├── pyproject.toml
└── main.py
```

## Skills

### scan-to-skill / skill-scanner

Proactive project scanners that analyze a codebase's tech stack and architecture, then:

1. Recommend existing skills from the ecosystem via `npx skills find`
2. Suggest custom skills that could be built for the project

Each skill follows a 3-phase approach: **Scan** (detect tech stack) → **Match** (find ecosystem skills) → **Suggest** (propose custom skills).

Both skills use reference files in `references/` to keep the main SKILL.md lean:

- `detection-patterns.md` — ~120 file-to-technology mappings with search queries
- `skill-query-templates.md` — pre-optimized query sets for ~15 project types

## Conventions

- Each skill lives in its own top-level directory with a `SKILL.md`
- Large lookup tables go in `references/` subdirectories, not in the main SKILL.md
- No `scripts/` directories — skills rely on the agent's native tools (Glob, Read, Bash)
- Use `npx skills find` for ecosystem searches, capped at 8 calls per scan
- Use the `skill-creator` skill when building new skills
