# Skill Query Templates

Pre-optimized query sets by detected project type. Select the matching project profile and use those queries as a starting point, then supplement with additional queries based on specific technologies detected.

## React / Next.js Project

Detected by: `next.config.*`, `react` in package.json dependencies

| Priority | Query                                    | Targets                            |
| -------- | ---------------------------------------- | ---------------------------------- |
| 1        | `nextjs react`                           | Core framework skills              |
| 2        | `react components`                       | Component patterns, hooks          |
| 3        | `typescript react`                       | Type safety in React               |
| 4        | `jest testing react` or `vitest testing` | Unit/component testing             |
| 5        | `tailwind css`                           | Styling (if Tailwind detected)     |
| 6        | `prisma database` or `drizzle database`  | Database (if ORM detected)         |
| 7        | `github actions ci`                      | CI/CD (if GitHub Actions detected) |
| 8        | `vercel deployment`                      | Deployment (if Vercel detected)    |

## Vue / Nuxt Project

Detected by: `nuxt.config.*`, `vue` in package.json dependencies

| Priority | Query               | Targets               |
| -------- | ------------------- | --------------------- |
| 1        | `nuxt vue`          | Core framework skills |
| 2        | `vue components`    | Vue-specific patterns |
| 3        | `typescript vue`    | Type safety           |
| 4        | `vitest testing`    | Testing               |
| 5        | `tailwind css`      | Styling (if detected) |
| 6        | `github actions ci` | CI/CD                 |

## Python Web Project (Django / Flask / FastAPI)

Detected by: `manage.py`, `django`/`flask`/`fastapi` in dependencies

| Priority | Query                                                 | Targets                          |
| -------- | ----------------------------------------------------- | -------------------------------- |
| 1        | `django python` or `fastapi python` or `flask python` | Core framework                   |
| 2        | `python best practices`                               | Language patterns                |
| 3        | `pytest python testing`                               | Testing                          |
| 4        | `python api rest`                                     | API development                  |
| 5        | `sqlalchemy database` or `django orm`                 | Database/ORM                     |
| 6        | `docker containers`                                   | Containerization (if detected)   |
| 7        | `github actions ci`                                   | CI/CD                            |
| 8        | `celery python tasks`                                 | Async tasks (if Celery detected) |

## Python Data / ML Project

Detected by: `torch`, `tensorflow`, `pandas`, `numpy`, `scikit-learn` in dependencies

| Priority | Query                   | Targets                                    |
| -------- | ----------------------- | ------------------------------------------ |
| 1        | `python data science`   | Data workflow                              |
| 2        | `machine learning`      | ML patterns                                |
| 3        | `python best practices` | Language patterns                          |
| 4        | `pytest python testing` | Testing                                    |
| 5        | `jupyter notebook`      | Notebook workflows (if notebooks detected) |
| 6        | `docker containers`     | Containerization                           |

## Rust Project

Detected by: `Cargo.toml`

| Priority | Query                 | Targets                                       |
| -------- | --------------------- | --------------------------------------------- |
| 1        | `rust cargo`          | Core language skills                          |
| 2        | `rust best practices` | Patterns and idioms                           |
| 3        | `rust testing`        | Testing                                       |
| 4        | `rust web api`        | Web framework (if axum/actix/rocket detected) |
| 5        | `rust cli`            | CLI tools (if clap detected)                  |
| 6        | `github actions ci`   | CI/CD                                         |

## Go Project

Detected by: `go.mod`

| Priority | Query                   | Targets                                    |
| -------- | ----------------------- | ------------------------------------------ |
| 1        | `golang go`             | Core language skills                       |
| 2        | `golang best practices` | Patterns and idioms                        |
| 3        | `golang testing`        | Testing                                    |
| 4        | `golang web api`        | Web framework (if gin/echo/fiber detected) |
| 5        | `docker containers`     | Containerization (if detected)             |
| 6        | `kubernetes deployment` | K8s (if detected)                          |

## Ruby on Rails Project

Detected by: `Gemfile` with `rails`, `config/routes.rb`

| Priority | Query                       | Targets           |
| -------- | --------------------------- | ----------------- |
| 1        | `rails ruby`                | Core framework    |
| 2        | `ruby best practices`       | Language patterns |
| 3        | `rspec ruby testing`        | Testing           |
| 4        | `rails database migrations` | Database          |
| 5        | `docker containers`         | Containerization  |
| 6        | `github actions ci`         | CI/CD             |

## Java / Spring Boot Project

Detected by: `pom.xml` or `build.gradle` with Spring dependencies

| Priority | Query                   | Targets           |
| -------- | ----------------------- | ----------------- |
| 1        | `spring java`           | Core framework    |
| 2        | `java best practices`   | Language patterns |
| 3        | `java testing junit`    | Testing           |
| 4        | `docker containers`     | Containerization  |
| 5        | `kubernetes deployment` | K8s (if detected) |
| 6        | `github actions ci`     | CI/CD             |

## Monorepo Project

Detected by: `turbo.json`, `nx.json`, `lerna.json`, `pnpm-workspace.yaml`

| Priority | Query                                 | Targets                |
| -------- | ------------------------------------- | ---------------------- |
| 1        | `monorepo turborepo` or `monorepo nx` | Monorepo tooling       |
| 2        | (primary framework query)             | Framework for main app |
| 3        | `typescript`                          | Shared types           |
| 4        | (testing query per detected runner)   | Testing                |
| 5        | `github actions ci`                   | CI/CD                  |
| 6        | `docker containers`                   | Containerization       |

## Mobile Project (React Native / Flutter)

Detected by: `react-native` in deps, `pubspec.yaml`

| Priority | Query                                 | Targets         |
| -------- | ------------------------------------- | --------------- |
| 1        | `react native expo` or `flutter dart` | Core framework  |
| 2        | `mobile app`                          | Mobile patterns |
| 3        | `typescript react` or `dart`          | Language        |
| 4        | `jest testing` or `flutter testing`   | Testing         |
| 5        | `github actions ci`                   | CI/CD           |

## Static Site / Documentation

Detected by: `astro.config.*`, `docusaurus.config.*`, `hugo.toml`, `mkdocs.yml`

| Priority | Query                                       | Targets               |
| -------- | ------------------------------------------- | --------------------- |
| 1        | `astro` or `docusaurus` or `hugo`           | SSG framework         |
| 2        | `mdx documentation`                         | Content authoring     |
| 3        | `tailwind css`                              | Styling (if detected) |
| 4        | `github actions ci`                         | CI/CD                 |
| 5        | `vercel deployment` or `netlify deployment` | Hosting               |

## Docker / Kubernetes Project

Detected by: `Dockerfile`, `docker-compose.yml`, `k8s/`, `Chart.yaml`

| Priority | Query                      | Targets                  |
| -------- | -------------------------- | ------------------------ |
| 1        | `docker containers`        | Docker skills            |
| 2        | `kubernetes deployment`    | K8s skills (if detected) |
| 3        | `helm kubernetes`          | Helm (if detected)       |
| 4        | `terraform infrastructure` | IaC (if detected)        |
| 5        | (primary language query)   | Language skills          |
| 6        | `github actions ci`        | CI/CD                    |

## CLI / Library Project

Detected by: `bin` field in package.json, `[[bin]]` in Cargo.toml, console_scripts in setup.py

| Priority | Query                                      | Targets               |
| -------- | ------------------------------------------ | --------------------- |
| 1        | (primary language query)                   | Language skills       |
| 2        | (language) `cli`                           | CLI-specific patterns |
| 3        | (language) `testing`                       | Testing               |
| 4        | `github actions ci`                        | CI/CD                 |
| 5        | `npm publish` or `cargo publish` or `pypi` | Publishing            |

## AI / LLM Project

Detected by: `anthropic`, `openai`, `langchain`, `@modelcontextprotocol` in deps

| Priority | Query                                | Targets                 |
| -------- | ------------------------------------ | ----------------------- |
| 1        | `claude anthropic ai` or `openai ai` | AI SDK skills           |
| 2        | `mcp model context protocol`         | MCP (if detected)       |
| 3        | `langchain ai`                       | LangChain (if detected) |
| 4        | (primary language query)             | Language skills         |
| 5        | (testing query)                      | Testing                 |
| 6        | `docker containers`                  | Containerization        |
