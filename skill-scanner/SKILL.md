---
name: skill-scanner
description: >-
  Proactively scans and analyzes any project's tech stack, architecture, and
  development workflows to recommend existing skills from the ecosystem and
  suggest custom skills worth building. Use this skill whenever the user says
  things like "scan this project", "what skills does this project need",
  "analyze project for skills", "audit my project", "onboard onto this
  codebase", "what skills should I install", "scan my repo", "analyze this
  codebase", "set up skills for this project", or when they're new to a
  codebase and want to know what tooling would help. Also trigger when the user
  asks about improving their development workflow, wants to know what they're
  missing, or says anything that implies they want a comprehensive project
  audit from a skills perspective. Even if they don't use the word "skill" —
  if they're asking "what can I do to improve my dev setup" or "help me get
  started with this project", this skill is relevant.
---

# skill-scanner

This skill scans a project in three phases — **Scan** (detect the full tech stack), **Match** (find existing skills that fit), **Suggest** (propose custom skills for gaps the ecosystem doesn't cover). The goal is to give the user a complete, actionable skill audit tailored to their specific project.

---

## Phase 1: Project Scan

Build a structured tech stack profile by reading the project's files in priority order. Start with the highest-signal files and work down — you don't need to read everything, just enough to understand what's going on.

### Step 1.1 — Get the file tree

If inside a git repo, run:

```bash
git ls-files
```

Otherwise, use Glob to list files, **excluding** these directories (they're noise):
`node_modules`, `.git`, `vendor`, `dist`, `build`, `__pycache__`, `.next`, `target`, `.venv`, `env`, `.tox`, `coverage`, `.nyc_output`, `.turbo`, `.cache`, `.parcel-cache`

Hold onto the full file list — you'll reference it throughout the scan.

### Step 1.2 — Tier 1: Dependency manifests

These are the highest-signal files in any project. Read whichever exist:

| File                                                                         | What it reveals                                                    |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| `package.json`                                                               | Node.js ecosystem — frameworks, test runners, build tools, scripts |
| `requirements.txt` / `pyproject.toml` / `setup.py` / `setup.cfg` / `Pipfile` | Python ecosystem                                                   |
| `Cargo.toml`                                                                 | Rust crates and edition                                            |
| `go.mod`                                                                     | Go modules and version                                             |
| `Gemfile` / `*.gemspec`                                                      | Ruby gems                                                          |
| `pom.xml` / `build.gradle` / `build.gradle.kts`                              | Java/Kotlin/JVM ecosystem                                          |
| `composer.json`                                                              | PHP packages                                                       |
| `pubspec.yaml`                                                               | Dart/Flutter                                                       |
| `mix.exs`                                                                    | Elixir                                                             |
| `Package.swift`                                                              | Swift                                                              |
| `*.csproj` / `*.sln`                                                         | .NET/C#                                                            |
| `deno.json` / `deno.jsonc`                                                   | Deno                                                               |

From these, extract: language(s), framework(s), test runner(s), build tools, and key libraries. Pay special attention to `scripts` in `package.json` — they often reveal custom workflows worth encoding as skills later.

### Step 1.3 — Tier 2: Configuration files

These reveal tooling choices. Read whichever exist (up to ~8 files):

- **Type system**: `tsconfig.json`, `jsconfig.json`
- **Linting/formatting**: `.eslintrc*`, `eslint.config.*`, `biome.json`, `.prettierrc*`, `ruff.toml`
- **Bundlers**: `webpack.config.*`, `vite.config.*`, `rollup.config.*`, `esbuild.*`, `turbopack.*`
- **Frameworks**: `next.config.*`, `nuxt.config.*`, `svelte.config.*`, `astro.config.*`, `angular.json`, `remix.config.*`
- **Testing**: `jest.config.*`, `vitest.config.*`, `playwright.config.*`, `cypress.config.*`, `pytest.ini`, `conftest.py`
- **Containers**: `Dockerfile*`, `docker-compose*.yml`, `docker-compose*.yaml`, `compose.yml`
- **CI/CD**: `.github/workflows/*.yml`, `.gitlab-ci.yml`, `.circleci/config.yml`, `Jenkinsfile`
- **Infrastructure**: `terraform/*.tf`, `serverless.yml`, `cdk.json`, `fly.toml`, `vercel.json`
- **Database**: `prisma/schema.prisma`, `drizzle.config.*`, `knexfile.*`, `alembic.ini`
- **Task runners**: `Makefile`, `justfile`, `Taskfile.yml`
- **CSS**: `tailwind.config.*`, `postcss.config.*`
- **AI config**: `CLAUDE.md`, `.cursorrules`

### Step 1.4 — Tier 3: Architecture indicators

Glob for these patterns to understand the project's shape:

- **Monorepo signals**: `pnpm-workspace.yaml`, `lerna.json`, `nx.json`, `turbo.json`, `rush.json`, `packages/*/package.json`, `apps/*/package.json`
- **API definitions**: `*.proto`, `*.graphql`, `*.gql`, `openapi.yaml`, `swagger.json`
- **Database migrations**: `migrations/`, `db/migrate/`, `alembic/`, `prisma/migrations/`
- **Infrastructure**: `terraform/`, `k8s/`, `helm/`, `Chart.yaml`
- **Mobile**: `android/`, `ios/`, `*.xcodeproj`
- **Component docs**: `.storybook/`, `*.stories.*`
- **E2E tests**: `e2e/`, `cypress/`, `playwright/`

### Step 1.5 — Sample source files

Read 2–3 source files from the main source directory (`src/`, `app/`, `lib/`, or wherever the bulk of the code lives). The purpose is to understand:

- Coding patterns and conventions the team follows
- Import structure and module organization
- Any domain-specific patterns that might warrant a custom skill

Pick files that look representative — not test files, not config, not generated code.

### Step 1.6 — Check already-installed skills

Look for skills that are already available so you don't recommend duplicates:

```bash
ls ~/.claude/skills/ 2>/dev/null
ls .agents/skills/ 2>/dev/null
ls .claude/skills/ 2>/dev/null
```

For each directory that exists, look for `SKILL.md` files and note their names.

### Step 1.7 — Compile the tech stack summary

Assemble everything into a structured summary. This becomes the input for Phase 2:

```
Languages:        [e.g., TypeScript, Python]
Frameworks:       [e.g., Next.js 14, FastAPI]
Build tools:      [e.g., pnpm, Turbopack, Vite]
Test runners:     [e.g., Vitest, Playwright]
CI/CD:            [e.g., GitHub Actions]
Database/ORM:     [e.g., Prisma + PostgreSQL]
Infrastructure:   [e.g., Docker, Vercel]
Architecture:     [e.g., monorepo with Turborepo]
Key libraries:    [e.g., tRPC, Zod, Tailwind]
Installed skills: [e.g., skill-creator, find-skills]
```

---

## Phase 2: Skill Matching

Now that you know what the project uses, find skills from the ecosystem that would help.

### Step 2.1 — Load the detection patterns

Read `references/detection-patterns.md` from this skill's directory. It maps detected files and technologies to optimized search queries for `npx skills find`.

### Step 2.2 — Choose search queries

Based on the tech stack summary, pick up to **8** queries. Prioritize them in this order:

1. **Primary framework** — the thing the project is built on (e.g., `nextjs react`, `django python`)
2. **Primary language** — especially if there isn't a dominant framework (e.g., `rust`, `golang`)
3. **Testing stack** — the test runner and any testing libraries (e.g., `vitest testing`, `pytest python`)
4. **CI/CD platform** — whatever runs the pipeline (e.g., `github actions ci`)
5. **Specialized domains** — ORMs, API protocols, cloud platforms (e.g., `prisma database`, `graphql api`)
6. **Architecture patterns** — monorepo tools, microservice patterns (e.g., `turborepo monorepo`)

Consult `references/skill-query-templates.md` for pre-optimized query sets — if the project matches a known profile (React/Next.js, Python web, Rust, etc.), start with those queries and adjust.

### Step 2.3 — Run the searches

Execute each query:

```bash
npx skills find "<query>"
```

Run these in parallel where possible — use multiple Bash tool calls in the same turn. **Hard cap: 8 calls total.** Fewer is fine if the project's stack is narrow.

### Step 2.4 — Process and categorize results

Take all the results and:

1. **Deduplicate** — same skill from multiple queries? Keep it once
2. **Filter out installed skills** — anything found in Step 1.6 gets excluded
3. **Categorize** into groups:
   - **Core Development** — language/framework best practices, coding patterns
   - **Testing & Quality** — test runners, linting, code review
   - **DevOps & CI/CD** — deployment, pipelines, containers
   - **Database & Data** — ORMs, migrations, data pipelines
   - **Specialized** — domain-specific skills (AI, mobile, etc.)
4. **Rank** within each category by how relevant they are to _this specific project_

Drop any category that has no results — don't show empty sections.

---

## Phase 3: Custom Skill Suggestions

The ecosystem won't cover everything. This is where you identify project-specific opportunities that a custom skill could address.

### Step 3.1 — Look for automation opportunities

Go back to what you learned in Phase 1 and look for:

- **Custom deployment workflows**: Scripts in `Makefile`, `package.json` scripts, `justfile`, or CI configs that encode project-specific multi-step deploy processes. These are prime candidates for a skill because they encode tribal knowledge.
- **Project conventions**: Naming patterns, file organization rules, import ordering, or code style that goes beyond what linters enforce. If there's a `CLAUDE.md` or `CONTRIBUTING.md` that describes conventions, that's a strong signal.
- **Repetitive scaffolding**: If the project has a pattern for adding new components, endpoints, services, or modules, a skill could automate the boilerplate.
- **Domain logic**: Business rules, data transformations, or API patterns specific to this project that a developer would need to learn.
- **Multi-service orchestration**: If the project involves running multiple services locally, a "dev environment" skill could help.
- **Complex scripts**: Any shell scripts or npm scripts longer than a few lines that someone clearly spent time getting right.

### Step 3.2 — Write up suggestions

For each opportunity, provide:

- **Name**: kebab-case, descriptive (e.g., `deploy-staging`, `new-api-endpoint`, `seed-test-data`)
- **Purpose**: One sentence — what it automates
- **What it encodes**: The specific tribal knowledge or workflow steps it captures
- **Complexity**: Low (quick to build, < 1 hour) / Medium (1-3 hours) / High (3+ hours)
- **Priority**: High (used daily), Medium (used weekly), Low (occasional but valuable)

Aim for 2–5 suggestions. If the project is simple and well-covered by existing skills, fewer is fine — don't pad the list.

### Step 3.3 — Mention skill-creator

If you're suggesting custom skills, let the user know they can use the `skill-creator` skill to build them:

```
npx skills add skill-creator
```

Or if it's already installed, just remind them they can ask Claude to create any of the suggested skills.

---

## Output Format

Present the final report using this template. Adapt it to the project — skip sections that don't apply, and add specificity everywhere. Generic recommendations are useless; everything should be tied to something you actually found in the scan.

````markdown
# Project Scan: [project-name]

## Tech Stack Summary

| Category       | Detected |
| -------------- | -------- |
| Languages      | ...      |
| Frameworks     | ...      |
| Build Tools    | ...      |
| Testing        | ...      |
| CI/CD          | ...      |
| Database       | ...      |
| Infrastructure | ...      |
| Architecture   | ...      |

## Recommended Skills

### Core Development

| Skill        | Why it fits this project      | Install                     |
| ------------ | ----------------------------- | --------------------------- |
| `skill-name` | Specific reason based on scan | `npx skills add skill-name` |

### Testing & Quality

| Skill | Why it fits this project | Install |
| ----- | ------------------------ | ------- |
| ...   | ...                      | ...     |

### DevOps & CI/CD

| Skill | Why it fits this project | Install |
| ----- | ------------------------ | ------- |
| ...   | ...                      | ...     |

_(Only include categories that have results.)_

## Custom Skill Suggestions

### 1. `suggested-name`

- **Purpose**: What it would do
- **Encodes**: What knowledge it captures
- **Complexity**: Low / Medium / High
- **Priority**: High / Medium / Low

### 2. ...

## Quick Install

All recommended skills in one command:

```bash
npx skills add skill-1 skill-2 skill-3
```
````

## Already Installed

- skill-a _(global)_
- skill-b _(project)_

```

### Important guidance for the output

- **Be specific, not generic.** "This project uses Next.js 14 with the App Router and tRPC, so this skill's patterns for server components and type-safe API calls are directly applicable" — good. "This might be useful for your project" — bad.
- **Don't over-recommend.** 3-5 strong, well-justified recommendations beat 15 spray-and-pray suggestions. If the ecosystem only has 2 relevant skills, recommend 2.
- **Acknowledge what's already good.** If the project has solid tooling coverage, say so. Not everything needs a skill.
- **Install commands must be copy-pasteable.** Every recommendation needs a working `npx skills add` command.
```
