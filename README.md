# Skills

A collection of Claude Code skills for project analysis and developer workflow automation.

## What are Skills?

Skills are reusable instruction sets that extend Claude Code's capabilities. They trigger automatically based on context and guide Claude through specialized workflows.

## Available Skills

### scan-to-skill

Proactively scans any project folder, analyzes its tech stack, and recommends skills from the ecosystem — plus suggests custom skills worth building.

**Install:**

```bash
npx skills add ./scan-to-skill
```

### skill-scanner

Same concept as scan-to-skill, built using the `skill-creator` skill for a more structured approach.

**Install:**

```bash
npx skills add ./skill-scanner
```

## How It Works

Both scanner skills follow a 3-phase approach:

1. **Scan** — Detect the project's languages, frameworks, build tools, testing setup, CI/CD, database, and architecture
2. **Match** — Search the skill ecosystem (`npx skills find`) for relevant skills, deduplicate, and categorize
3. **Suggest** — Identify gaps and propose custom skills the team could build

The output is a structured report with a tech stack summary, categorized recommendations with install commands, and custom skill suggestions with complexity estimates.

## Usage

After installing a scanner skill, just ask Claude:

- "scan this project"
- "what skills does this project need?"
- "analyze this codebase for skills"
- "audit my project"
- "help me onboard onto this codebase"

## License

MIT
