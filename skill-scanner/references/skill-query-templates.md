# Skill Query Templates

Pre-built query sets organized by project type. When the project matches one of these profiles, use these queries as your starting point — then adjust based on whatever else you found in the scan.

Each profile lists queries in priority order. Pick the top ones that apply (remember the 8-query cap) and swap in alternatives if the project uses different tools than the default.

---

## React / Next.js

**Detected by**: `next.config.*`, or `react` + `react-dom` in package.json

| #   | Query                                    | What it finds                                          |
| --- | ---------------------------------------- | ------------------------------------------------------ |
| 1   | `nextjs react`                           | Next.js-specific patterns and best practices           |
| 2   | `react components`                       | Component patterns, hooks, state management            |
| 3   | `typescript react`                       | Type-safe React patterns                               |
| 4   | `vitest testing` or `jest testing react` | Unit/component testing (pick based on detected runner) |
| 5   | `tailwind css`                           | Styling patterns (if Tailwind detected)                |
| 6   | `prisma database` or `drizzle database`  | ORM skills (if database detected)                      |
| 7   | `github actions ci`                      | CI/CD (if GitHub Actions detected)                     |
| 8   | `vercel deployment`                      | Deployment (if Vercel detected)                        |

## Vue / Nuxt

**Detected by**: `nuxt.config.*`, or `vue` in package.json

| #   | Query               | What it finds               |
| --- | ------------------- | --------------------------- |
| 1   | `nuxt vue`          | Nuxt/Vue framework patterns |
| 2   | `vue components`    | Vue component patterns      |
| 3   | `typescript vue`    | TypeScript + Vue            |
| 4   | `vitest testing`    | Testing                     |
| 5   | `tailwind css`      | Styling (if detected)       |
| 6   | `github actions ci` | CI/CD                       |

## Svelte / SvelteKit

**Detected by**: `svelte.config.*`

| #   | Query                                        | What it finds         |
| --- | -------------------------------------------- | --------------------- |
| 1   | `svelte sveltekit`                           | SvelteKit patterns    |
| 2   | `typescript`                                 | TypeScript patterns   |
| 3   | `vitest testing` or `playwright e2e testing` | Testing               |
| 4   | `tailwind css`                               | Styling (if detected) |
| 5   | `github actions ci`                          | CI/CD                 |

## Python Web (Django / Flask / FastAPI)

**Detected by**: `manage.py`, or `django`/`flask`/`fastapi` in dependencies

| #   | Query                                                 | What it finds                             |
| --- | ----------------------------------------------------- | ----------------------------------------- |
| 1   | `django python` or `fastapi python` or `flask python` | Framework-specific skills                 |
| 2   | `python best practices`                               | Language patterns                         |
| 3   | `pytest python testing`                               | Testing                                   |
| 4   | `python api rest`                                     | API development                           |
| 5   | `sqlalchemy python database` or `django orm`          | ORM/database (based on detected ORM)      |
| 6   | `docker containers`                                   | Containerization (if Dockerfile detected) |
| 7   | `github actions ci`                                   | CI/CD                                     |
| 8   | `celery python tasks`                                 | Async tasks (if Celery detected)          |

## Python Data Science / ML

**Detected by**: `torch`, `tensorflow`, `pandas`, `numpy`, `scikit-learn`, `transformers` in dependencies

| #   | Query                   | What it finds          |
| --- | ----------------------- | ---------------------- |
| 1   | `python data science`   | Data workflow patterns |
| 2   | `machine learning`      | ML patterns            |
| 3   | `python best practices` | Language patterns      |
| 4   | `pytest python testing` | Testing                |
| 5   | `docker containers`     | Containerization       |

## Rust

**Detected by**: `Cargo.toml`

| #   | Query                 | What it finds                                 |
| --- | --------------------- | --------------------------------------------- |
| 1   | `rust cargo`          | Rust ecosystem skills                         |
| 2   | `rust best practices` | Rust idioms and patterns                      |
| 3   | `rust testing`        | Testing                                       |
| 4   | `rust web api`        | Web framework (if axum/actix/rocket detected) |
| 5   | `rust cli`            | CLI tooling (if clap/structopt detected)      |
| 6   | `github actions ci`   | CI/CD                                         |

## Go

**Detected by**: `go.mod`

| #   | Query                   | What it finds                              |
| --- | ----------------------- | ------------------------------------------ |
| 1   | `golang go`             | Go ecosystem skills                        |
| 2   | `golang best practices` | Go idioms                                  |
| 3   | `golang testing`        | Testing                                    |
| 4   | `golang web api`        | Web framework (if gin/echo/fiber detected) |
| 5   | `docker containers`     | Containerization (if detected)             |
| 6   | `kubernetes deployment` | K8s (if detected)                          |

## Ruby on Rails

**Detected by**: `Gemfile` with `rails`, `config/routes.rb`

| #   | Query                       | What it finds          |
| --- | --------------------------- | ---------------------- |
| 1   | `rails ruby`                | Rails framework skills |
| 2   | `ruby best practices`       | Ruby patterns          |
| 3   | `rspec ruby testing`        | Testing                |
| 4   | `rails database migrations` | Database/migrations    |
| 5   | `docker containers`         | Containerization       |
| 6   | `github actions ci`         | CI/CD                  |

## Java / Spring Boot

**Detected by**: `pom.xml` or `build.gradle` with Spring dependencies

| #   | Query                   | What it finds        |
| --- | ----------------------- | -------------------- |
| 1   | `spring java`           | Spring Boot patterns |
| 2   | `java best practices`   | Java patterns        |
| 3   | `java testing junit`    | Testing              |
| 4   | `docker containers`     | Containerization     |
| 5   | `kubernetes deployment` | K8s (if detected)    |
| 6   | `github actions ci`     | CI/CD                |

## .NET / C#

**Detected by**: `*.csproj`, `*.sln`

| #   | Query                                    | What it finds         |
| --- | ---------------------------------------- | --------------------- |
| 1   | `dotnet csharp`                          | .NET ecosystem skills |
| 2   | `csharp best practices`                  | C# patterns           |
| 3   | `dotnet testing`                         | Testing               |
| 4   | `docker containers`                      | Containerization      |
| 5   | `azure devops ci` or `github actions ci` | CI/CD                 |

## PHP / Laravel

**Detected by**: `composer.json` with Laravel

| #   | Query                 | What it finds            |
| --- | --------------------- | ------------------------ |
| 1   | `laravel php`         | Laravel framework skills |
| 2   | `php best practices`  | PHP patterns             |
| 3   | `phpunit php testing` | Testing                  |
| 4   | `docker containers`   | Containerization         |
| 5   | `github actions ci`   | CI/CD                    |

## Monorepo

**Detected by**: `turbo.json`, `nx.json`, `lerna.json`, `pnpm-workspace.yaml`

| #   | Query                                 | What it finds                                  |
| --- | ------------------------------------- | ---------------------------------------------- |
| 1   | `monorepo turborepo` or `monorepo nx` | Monorepo tooling (pick based on detected tool) |
| 2   | _(primary framework query)_           | Framework for the main app                     |
| 3   | `typescript`                          | Shared types/config                            |
| 4   | _(testing query)_                     | Testing (per detected runner)                  |
| 5   | `github actions ci`                   | CI/CD                                          |
| 6   | `docker containers`                   | Containerization                               |

## Mobile (React Native / Flutter)

**Detected by**: `react-native` in deps, `pubspec.yaml`, `app.json` with expo

| #   | Query                                 | What it finds           |
| --- | ------------------------------------- | ----------------------- |
| 1   | `react native expo` or `flutter dart` | Mobile framework skills |
| 2   | `mobile app`                          | General mobile patterns |
| 3   | `typescript react` or `dart`          | Language skills         |
| 4   | `jest testing` or `flutter testing`   | Testing                 |
| 5   | `github actions ci`                   | CI/CD                   |

## Electron / Desktop

**Detected by**: `electron` in deps, `electron-builder.*`

| #   | Query                                  | What it finds                              |
| --- | -------------------------------------- | ------------------------------------------ |
| 1   | `electron desktop`                     | Electron patterns                          |
| 2   | `react components` or `vue components` | UI framework (based on detected framework) |
| 3   | `typescript`                           | TypeScript patterns                        |
| 4   | `vitest testing` or `jest testing`     | Testing                                    |

## Static Site / Docs

**Detected by**: `astro.config.*`, `docusaurus.config.*`, `hugo.toml`, `mkdocs.yml`

| #   | Query                                       | What it finds         |
| --- | ------------------------------------------- | --------------------- |
| 1   | `astro` or `docusaurus` or `hugo`           | SSG framework         |
| 2   | `mdx documentation`                         | Content authoring     |
| 3   | `tailwind css`                              | Styling (if detected) |
| 4   | `github actions ci`                         | CI/CD                 |
| 5   | `vercel deployment` or `netlify deployment` | Hosting               |

## Docker / Kubernetes / Infrastructure

**Detected by**: `Dockerfile`, `docker-compose.yml`, `k8s/`, `Chart.yaml`, `*.tf`

| #   | Query                      | What it finds      |
| --- | -------------------------- | ------------------ |
| 1   | `docker containers`        | Docker skills      |
| 2   | `kubernetes deployment`    | K8s (if detected)  |
| 3   | `helm kubernetes`          | Helm (if detected) |
| 4   | `terraform infrastructure` | IaC (if detected)  |
| 5   | _(primary language query)_ | Language skills    |
| 6   | `github actions ci`        | CI/CD              |

## AI / LLM Project

**Detected by**: `anthropic`, `openai`, `langchain`, `@modelcontextprotocol` in deps

| #   | Query                                | What it finds           |
| --- | ------------------------------------ | ----------------------- |
| 1   | `claude anthropic ai` or `openai ai` | AI SDK skills           |
| 2   | `mcp model context protocol`         | MCP (if detected)       |
| 3   | `langchain ai`                       | LangChain (if detected) |
| 4   | _(primary language query)_           | Language skills         |
| 5   | _(testing query)_                    | Testing                 |
| 6   | `docker containers`                  | Containerization        |

## CLI / Library

**Detected by**: `bin` in package.json, `[[bin]]` in Cargo.toml, `console_scripts` in setup.py

| #   | Query                                      | What it finds         |
| --- | ------------------------------------------ | --------------------- |
| 1   | _(primary language query)_                 | Language skills       |
| 2   | _(language)_ `cli`                         | CLI-specific patterns |
| 3   | _(language)_ `testing`                     | Testing               |
| 4   | `github actions ci`                        | CI/CD                 |
| 5   | `npm publish` or `cargo publish` or `pypi` | Package publishing    |
