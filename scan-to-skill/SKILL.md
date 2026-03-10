---
name: scan-to-skill
description: >-
  Proactively scans and analyzes any project's tech stack, architecture, and
  conventions to recommend existing skills from the ecosystem and suggest custom
  skills that should be built. Use when the user says things like "scan this
  project", "what skills does this project need", "analyze project for skills",
  "audit my project", "onboard onto this codebase", "what skills should I
  install", or "help me set up skills for this project".
---

# scan-to-skill

Scan a project, match it to existing skills, and suggest custom skills — a 3-phase proactive analysis.

## Phase 1: Project Scan

Scan the project to build a structured tech stack summary. Work through tiers of files, starting with the most informative.

### Step 1.1 — Gather the file tree

Run `git ls-files` if inside a git repo. Otherwise use Glob with these exclusions:

- **Never scan**: `node_modules`, `.git`, `vendor`, `dist`, `build`, `__pycache__`, `.next`, `target`, `.venv`, `env`, `.tox`, `coverage`, `.nyc_output`, `.turbo`, `.cache`

Store the full file list for reference throughout the scan.

### Step 1.2 — Read Tier 1 files (dependency manifests)

These are the highest-signal files. Read whichever exist:

| File                                                                         | Stack signal                                             |
| ---------------------------------------------------------------------------- | -------------------------------------------------------- |
| `package.json`                                                               | Node.js ecosystem, frameworks, test runners, build tools |
| `requirements.txt` / `pyproject.toml` / `setup.py` / `setup.cfg` / `Pipfile` | Python ecosystem                                         |
| `Cargo.toml`                                                                 | Rust ecosystem                                           |
| `go.mod` / `go.sum`                                                          | Go ecosystem                                             |
| `Gemfile` / `*.gemspec`                                                      | Ruby ecosystem                                           |
| `pom.xml` / `build.gradle` / `build.gradle.kts`                              | Java/Kotlin ecosystem                                    |
| `composer.json`                                                              | PHP ecosystem                                            |
| `pubspec.yaml`                                                               | Dart/Flutter ecosystem                                   |
| `mix.exs`                                                                    | Elixir ecosystem                                         |
| `Package.swift`                                                              | Swift ecosystem                                          |
| `*.csproj` / `*.sln`                                                         | .NET/C# ecosystem                                        |
| `deno.json` / `deno.jsonc`                                                   | Deno ecosystem                                           |
| `bun.lockb` / `bunfig.toml`                                                  | Bun runtime                                              |

Extract: language, framework(s), test runner(s), build tools, key libraries.

### Step 1.3 — Read Tier 2 files (config and tooling)

Read whichever exist to identify tooling choices:

| File                                                                             | Signal                     |
| -------------------------------------------------------------------------------- | -------------------------- |
| `tsconfig.json` / `jsconfig.json`                                                | TypeScript/JS config       |
| `.eslintrc*` / `eslint.config.*` / `biome.json`                                  | Linting                    |
| `prettier.config.*` / `.prettierrc*`                                             | Formatting                 |
| `Dockerfile` / `docker-compose.yml` / `docker-compose.yaml`                      | Containerization           |
| `.github/workflows/*.yml`                                                        | GitHub Actions CI/CD       |
| `.gitlab-ci.yml`                                                                 | GitLab CI                  |
| `Jenkinsfile`                                                                    | Jenkins CI                 |
| `.circleci/config.yml`                                                           | CircleCI                   |
| `jest.config.*` / `vitest.config.*` / `cypress.config.*` / `playwright.config.*` | Testing config             |
| `.storybook/`                                                                    | Component documentation    |
| `webpack.config.*` / `vite.config.*` / `rollup.config.*` / `esbuild.*`           | Bundler                    |
| `tailwind.config.*` / `postcss.config.*`                                         | CSS tooling                |
| `prisma/schema.prisma` / `drizzle.config.*`                                      | ORM/Database               |
| `.env.example` / `.env.local`                                                    | Environment config pattern |
| `Makefile` / `Taskfile.yml` / `justfile`                                         | Task runners               |
| `CLAUDE.md` / `.cursorrules` / `.windsurfrules`                                  | AI assistant config        |

### Step 1.4 — Glob for Tier 3 patterns (architecture indicators)

Check for these structural patterns:

- **Monorepo**: `pnpm-workspace.yaml`, `lerna.json`, `nx.json`, `turbo.json`, `rush.json`, `packages/*/package.json`, `apps/*/package.json`
- **API definitions**: `*.proto`, `*.graphql`, `*.gql`, `openapi.yaml`, `swagger.json`
- **Database**: `migrations/`, `db/migrate/`, `alembic/`, `prisma/migrations/`, `drizzle/`
- **Infrastructure**: `terraform/`, `*.tf`, `pulumi/`, `cdk.json`, `serverless.yml`, `k8s/`, `helm/`
- **Mobile**: `android/`, `ios/`, `*.xcodeproj`, `*.xcworkspace`
- **Documentation**: `docs/`, `storybook/`, `*.stories.*`

### Step 1.5 — Sample source files

Read 2–3 source files from the main source directory (typically `src/`, `app/`, `lib/`, or root-level source files) to identify:

- Coding patterns and conventions
- Domain-specific logic
- Common imports and utilities

### Step 1.6 — Check already-installed skills

Check these locations for skills already available:

- `~/.claude/skills/` — globally installed skills
- `.agents/skills/` — project-level skills (relative to project root)
- Run `ls ~/.claude/skills/ 2>/dev/null` and `ls .agents/skills/ 2>/dev/null`

Record installed skill names to exclude from recommendations later.

### Step 1.7 — Compile tech stack summary

Build a structured summary:

```
Language(s): ...
Framework(s): ...
Build tool(s): ...
Test runner(s): ...
CI/CD: ...
Database/ORM: ...
Containerization: ...
Architecture: (monolith | monorepo | microservices | library | CLI)
Key libraries: ...
Already installed skills: ...
```

## Phase 2: Skill Matching

Use the tech stack summary to find relevant skills from the ecosystem.

### Step 2.1 — Load detection patterns

Read `references/detection-patterns.md` from this skill's directory. This maps detected technologies to optimized search queries.

### Step 2.2 — Build search queries

Based on detected technologies, select up to **8** search queries. Prioritize:

1. Primary framework (e.g., `nextjs react`, `django python`)
2. Primary language (e.g., `rust`, `go`, `python`)
3. Testing stack (e.g., `jest testing`, `pytest python`)
4. CI/CD platform (e.g., `github actions`)
5. Specialized domains (e.g., `docker kubernetes`, `graphql api`, `prisma database`)
6. Architecture patterns (e.g., `monorepo`, `microservices`)

Also consult `references/skill-query-templates.md` for pre-optimized query sets by project type.

### Step 2.3 — Execute searches

Run each query using:

```
npx skills find <query>
```

Run queries in parallel where possible (use multiple Bash tool calls). Cap at **8 total calls**.

### Step 2.4 — Process results

- **Deduplicate** skills that appear across multiple queries
- **Exclude** skills already installed (from Step 1.6)
- **Categorize** results into groups:
  - Core Development (language/framework best practices)
  - Testing & Quality
  - DevOps & CI/CD
  - Database & Data
  - Architecture & Patterns
  - Specialized / Domain-specific
- **Rank** within each category by relevance to the specific project

## Phase 3: Custom Skill Suggestions

Analyze gaps between what the ecosystem offers and what the project could benefit from.

### Step 3.1 — Identify automation opportunities

Look for:

- **Custom deployment workflows**: Scripts in `Makefile`, `package.json` scripts, `justfile`, or CI configs that encode project-specific deploy logic
- **Project conventions**: Naming patterns, file organization rules, code style beyond what linters enforce
- **Domain logic**: Business rules, data transformations, or API patterns specific to this project
- **Repetitive tasks**: Commands or sequences the team likely runs frequently (build, test, deploy, migrate, seed)
- **Integration glue**: Custom scripts that connect multiple tools or services

### Step 3.2 — Generate suggestions

For each suggested custom skill, provide:

- **Name**: A descriptive skill name (e.g., `project-deploy`, `api-scaffolder`, `migration-helper`)
- **Purpose**: What it would automate or encode
- **What it encodes**: Specific knowledge or workflow steps
- **Complexity**: Low (< 1 hour to build) / Medium (1-3 hours) / High (3+ hours)
- **Priority**: High (daily use) / Medium (weekly use) / Low (occasional use)

### Step 3.3 — Check for skill-creator

If custom skills are suggested, note that the user can use the `skill-creator` skill to build them:

```
npx skills add skill-creator
```

## Output Template

Present the final report using this structure:

````markdown
# Project Scan Report

## Tech Stack Summary

- **Language(s)**: ...
- **Framework(s)**: ...
- **Build tool(s)**: ...
- **Test runner(s)**: ...
- **CI/CD**: ...
- **Database/ORM**: ...
- **Architecture**: ...
- **Key libraries**: ...

## Recommended Skills

### Core Development

| Skill        | Description  | Install                     |
| ------------ | ------------ | --------------------------- |
| `skill-name` | What it does | `npx skills add skill-name` |

### Testing & Quality

| Skill | Description | Install |
| ----- | ----------- | ------- |
| ...   | ...         | ...     |

### DevOps & CI/CD

| Skill | Description | Install |
| ----- | ----------- | ------- |
| ...   | ...         | ...     |

_(Include only categories that have results. Omit empty categories.)_

## Custom Skill Suggestions

### 1. `suggested-skill-name`

- **Purpose**: ...
- **Encodes**: ...
- **Complexity**: Low | Medium | High
- **Priority**: High | Medium | Low

_(List 2-5 suggestions, ordered by priority)_

## Quick Install

Install all recommended skills at once:

```bash
npx skills add skill-1 skill-2 skill-3
```
````

---

_Scanned by scan-to-skill_

```

## Important Notes

- Always present results even if `npx skills find` returns few or no results — the custom skill suggestions section is still valuable.
- If the project is very simple (e.g., a single script), scale down the report accordingly. Don't over-recommend.
- If the project already has many skills installed, focus the report on gaps and custom suggestions.
- Be specific in rationale — don't just say "this might be useful", explain *why* based on what was detected in the scan.
```
