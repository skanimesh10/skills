# Detection Patterns

A lookup table mapping file patterns to technologies and recommended `npx skills find` queries. When you detect a file from this table during the project scan, use the corresponding query in Phase 2.

---

## Languages

| Pattern                                                        | Technology  | Category | Query               |
| -------------------------------------------------------------- | ----------- | -------- | ------------------- |
| `package.json`                                                 | Node.js     | Language | `nodejs javascript` |
| `*.ts` / `tsconfig.json`                                       | TypeScript  | Language | `typescript`        |
| `requirements.txt` / `pyproject.toml` / `setup.py` / `Pipfile` | Python      | Language | `python`            |
| `Cargo.toml`                                                   | Rust        | Language | `rust cargo`        |
| `go.mod`                                                       | Go          | Language | `golang go`         |
| `Gemfile` / `*.gemspec`                                        | Ruby        | Language | `ruby`              |
| `pom.xml` / `build.gradle` / `build.gradle.kts`                | Java/Kotlin | Language | `java kotlin`       |
| `composer.json`                                                | PHP         | Language | `php`               |
| `pubspec.yaml`                                                 | Dart        | Language | `dart flutter`      |
| `mix.exs`                                                      | Elixir      | Language | `elixir phoenix`    |
| `Package.swift`                                                | Swift       | Language | `swift ios`         |
| `*.csproj` / `*.sln`                                           | C# / .NET   | Language | `dotnet csharp`     |
| `deno.json` / `deno.jsonc`                                     | Deno        | Language | `deno typescript`   |
| `*.scala` / `build.sbt`                                        | Scala       | Language | `scala`             |
| `*.clj` / `deps.edn`                                           | Clojure     | Language | `clojure`           |
| `*.zig` / `build.zig`                                          | Zig         | Language | `zig`               |
| `*.lua`                                                        | Lua         | Language | `lua`               |
| `*.jl`                                                         | Julia       | Language | `julia`             |
| `*.r` / `*.R` / `DESCRIPTION`                                  | R           | Language | `r statistics`      |

## Frameworks — JavaScript / TypeScript

| Pattern                                       | Technology          | Category  | Query                   |
| --------------------------------------------- | ------------------- | --------- | ----------------------- |
| `next.config.*`                               | Next.js             | Framework | `nextjs react`          |
| `nuxt.config.*`                               | Nuxt                | Framework | `nuxt vue`              |
| `svelte.config.*`                             | SvelteKit           | Framework | `svelte sveltekit`      |
| `astro.config.*`                              | Astro               | Framework | `astro`                 |
| `remix.config.*` / `remix.env.d.ts`           | Remix               | Framework | `remix react`           |
| `gatsby-config.*`                             | Gatsby              | Framework | `gatsby react`          |
| `angular.json`                                | Angular             | Framework | `angular typescript`    |
| `electron-builder.*`                          | Electron            | Framework | `electron desktop`      |
| `expo` in package.json / `app.json` with expo | Expo / React Native | Framework | `react native expo`     |
| `payload.config.*`                            | Payload CMS         | Framework | `payload cms`           |
| `sanity.config.*` / `sanity.json`             | Sanity              | Framework | `sanity cms`            |
| `contentlayer.config.*`                       | Contentlayer        | Framework | `contentlayer mdx`      |
| `solid-start` in deps                         | SolidStart          | Framework | `solid javascript`      |
| `qwik` in deps                                | Qwik                | Framework | `qwik`                  |
| `hono` in deps                                | Hono                | Framework | `hono api`              |
| `express` in deps                             | Express             | Framework | `express nodejs api`    |
| `fastify` in deps                             | Fastify             | Framework | `fastify nodejs api`    |
| `nestjs` / `@nestjs/core` in deps             | NestJS              | Framework | `nestjs typescript api` |

## Frameworks — Python

| Pattern                        | Technology | Category  | Query                 |
| ------------------------------ | ---------- | --------- | --------------------- |
| `manage.py` / `django` in deps | Django     | Framework | `django python`       |
| `flask` in deps                | Flask      | Framework | `flask python api`    |
| `fastapi` in deps              | FastAPI    | Framework | `fastapi python api`  |
| `streamlit` in deps            | Streamlit  | Framework | `streamlit python`    |
| `scrapy.cfg`                   | Scrapy     | Framework | `scrapy python`       |
| `celery` in deps               | Celery     | Framework | `celery python tasks` |
| `gradio` in deps               | Gradio     | Framework | `gradio python`       |

## Frameworks — Other Languages

| Pattern                                       | Technology    | Category  | Query            |
| --------------------------------------------- | ------------- | --------- | ---------------- |
| `config/routes.rb`                            | Ruby on Rails | Framework | `rails ruby`     |
| `actix-web` / `axum` / `rocket` in Cargo.toml | Rust web      | Framework | `rust web api`   |
| `gin` / `echo` / `fiber` in go.mod            | Go web        | Framework | `golang web api` |
| `Spring` in pom.xml / build.gradle            | Spring Boot   | Framework | `spring java`    |
| `Laravel` in composer.json                    | Laravel       | Framework | `laravel php`    |
| `Symfony` in composer.json                    | Symfony       | Framework | `symfony php`    |
| `Phoenix` in mix.exs                          | Phoenix       | Framework | `phoenix elixir` |

## Build Tools & Bundlers

| Pattern                         | Technology   | Category | Query                |
| ------------------------------- | ------------ | -------- | -------------------- |
| `webpack.config.*`              | Webpack      | Build    | `webpack bundler`    |
| `vite.config.*`                 | Vite         | Build    | `vite`               |
| `rollup.config.*`               | Rollup       | Build    | `rollup bundler`     |
| `tsup.config.*` / `esbuild.*`   | esbuild/tsup | Build    | `esbuild typescript` |
| `turbo.json`                    | Turborepo    | Build    | `turborepo monorepo` |
| `nx.json`                       | Nx           | Build    | `nx monorepo`        |
| `Makefile`                      | Make         | Build    | `makefile`           |
| `justfile`                      | Just         | Build    | `just taskrunner`    |
| `Taskfile.yml`                  | Task         | Build    | `taskfile`           |
| `CMakeLists.txt`                | CMake        | Build    | `cmake cpp`          |
| `bazel` / `BUILD` / `WORKSPACE` | Bazel        | Build    | `bazel`              |
| `meson.build`                   | Meson        | Build    | `meson`              |
| `Earthfile`                     | Earthly      | Build    | `earthly`            |

## Testing

| Pattern                                                          | Technology       | Category | Query                     |
| ---------------------------------------------------------------- | ---------------- | -------- | ------------------------- |
| `jest.config.*` / `jest` in package.json                         | Jest             | Testing  | `jest testing javascript` |
| `vitest.config.*` / `vitest` in package.json                     | Vitest           | Testing  | `vitest testing`          |
| `cypress.config.*` / `cypress/`                                  | Cypress          | Testing  | `cypress e2e testing`     |
| `playwright.config.*` / `playwright/`                            | Playwright       | Testing  | `playwright e2e testing`  |
| `.storybook/` / `*.stories.*`                                    | Storybook        | Testing  | `storybook components`    |
| `pytest.ini` / `conftest.py` / `[tool.pytest]` in pyproject.toml | pytest           | Testing  | `pytest python testing`   |
| `phpunit.xml`                                                    | PHPUnit          | Testing  | `phpunit php testing`     |
| `rspec` / `spec/` / `.rspec`                                     | RSpec            | Testing  | `rspec ruby testing`      |
| `*_test.go`                                                      | Go tests         | Testing  | `golang testing`          |
| `*.test.rs` / `#[cfg(test)]`                                     | Rust tests       | Testing  | `rust testing`            |
| `*.spec.ts` / `*.test.ts`                                        | TypeScript tests | Testing  | `typescript testing`      |
| `karma.conf.*`                                                   | Karma            | Testing  | `karma testing`           |
| `ava` in package.json                                            | AVA              | Testing  | `ava testing`             |

## CI/CD

| Pattern                   | Technology          | Category | Query               |
| ------------------------- | ------------------- | -------- | ------------------- |
| `.github/workflows/*.yml` | GitHub Actions      | CI/CD    | `github actions ci` |
| `.gitlab-ci.yml`          | GitLab CI           | CI/CD    | `gitlab ci`         |
| `Jenkinsfile`             | Jenkins             | CI/CD    | `jenkins ci`        |
| `.circleci/config.yml`    | CircleCI            | CI/CD    | `circleci ci`       |
| `.travis.yml`             | Travis CI           | CI/CD    | `travis ci`         |
| `bitbucket-pipelines.yml` | Bitbucket Pipelines | CI/CD    | `bitbucket ci`      |
| `.buildkite/`             | Buildkite           | CI/CD    | `buildkite ci`      |
| `azure-pipelines.yml`     | Azure DevOps        | CI/CD    | `azure devops ci`   |
| `cloudbuild.yaml`         | Google Cloud Build  | CI/CD    | `gcp cloud build`   |
| `.woodpecker/`            | Woodpecker CI       | CI/CD    | `woodpecker ci`     |

## Database & ORM

| Pattern                          | Technology       | Category | Query                        |
| -------------------------------- | ---------------- | -------- | ---------------------------- |
| `prisma/schema.prisma`           | Prisma           | Database | `prisma database orm`        |
| `drizzle.config.*` / `drizzle/`  | Drizzle          | Database | `drizzle database orm`       |
| `knexfile.*`                     | Knex             | Database | `knex database sql`          |
| `sequelize` in deps              | Sequelize        | Database | `sequelize database orm`     |
| `typeorm` in deps                | TypeORM          | Database | `typeorm database orm`       |
| `alembic/` / `alembic.ini`       | Alembic          | Database | `alembic python database`    |
| `sqlalchemy` in deps             | SQLAlchemy       | Database | `sqlalchemy python database` |
| `db/migrate/`                    | ActiveRecord     | Database | `rails database migrations`  |
| `diesel.toml`                    | Diesel           | Database | `diesel rust database`       |
| `mongoose` in deps               | MongoDB/Mongoose | Database | `mongodb database`           |
| `redis` in deps                  | Redis            | Database | `redis caching`              |
| `supabase/` / `supabase` in deps | Supabase         | Database | `supabase database`          |
| `firebase` / `firestore` in deps | Firebase         | Database | `firebase database`          |

## Infrastructure & Deployment

| Pattern                              | Technology           | Category       | Query                      |
| ------------------------------------ | -------------------- | -------------- | -------------------------- |
| `Dockerfile` / `Dockerfile.*`        | Docker               | Infrastructure | `docker containers`        |
| `docker-compose.yml` / `compose.yml` | Docker Compose       | Infrastructure | `docker compose`           |
| `*.tf` / `terraform/`                | Terraform            | Infrastructure | `terraform infrastructure` |
| `Pulumi.yaml` / `pulumi/`            | Pulumi               | Infrastructure | `pulumi infrastructure`    |
| `cdk.json` / `cdk/`                  | AWS CDK              | Infrastructure | `aws cdk infrastructure`   |
| `serverless.yml` / `serverless.ts`   | Serverless Framework | Infrastructure | `serverless aws lambda`    |
| `k8s/` / `kubernetes/`               | Kubernetes           | Infrastructure | `kubernetes deployment`    |
| `Chart.yaml` / `helm/`               | Helm                 | Infrastructure | `helm kubernetes`          |
| `fly.toml`                           | Fly.io               | Infrastructure | `fly deployment`           |
| `vercel.json`                        | Vercel               | Infrastructure | `vercel deployment`        |
| `netlify.toml`                       | Netlify              | Infrastructure | `netlify deployment`       |
| `render.yaml`                        | Render               | Infrastructure | `render deployment`        |
| `Procfile` / `heroku.yml`            | Heroku               | Infrastructure | `heroku deployment`        |
| `railway.json` / `railway.toml`      | Railway              | Infrastructure | `railway deployment`       |
| `ansible/` / `playbook.yml`          | Ansible              | Infrastructure | `ansible automation`       |

## API & Communication

| Pattern                                       | Technology              | Category  | Query                 |
| --------------------------------------------- | ----------------------- | --------- | --------------------- |
| `*.proto`                                     | gRPC / Protocol Buffers | API       | `grpc protobuf api`   |
| `*.graphql` / `*.gql` / `codegen.yml`         | GraphQL                 | API       | `graphql api`         |
| `openapi.yaml` / `openapi.json` / `swagger.*` | OpenAPI                 | API       | `openapi rest api`    |
| `trpc` in deps                                | tRPC                    | API       | `trpc typescript api` |
| `kafka` in deps                               | Kafka                   | Messaging | `kafka messaging`     |
| `rabbitmq` / `amqp` in deps                   | RabbitMQ                | Messaging | `rabbitmq messaging`  |

## Linting & Formatting

| Pattern                              | Technology    | Category   | Query                 |
| ------------------------------------ | ------------- | ---------- | --------------------- |
| `.eslintrc*` / `eslint.config.*`     | ESLint        | Linting    | `eslint javascript`   |
| `biome.json` / `biome.jsonc`         | Biome         | Linting    | `biome formatting`    |
| `.prettierrc*` / `prettier.config.*` | Prettier      | Formatting | `prettier formatting` |
| `.stylelintrc*`                      | Stylelint     | Linting    | `stylelint css`       |
| `ruff.toml` / `[tool.ruff]`          | Ruff          | Linting    | `ruff python linting` |
| `.rubocop.yml`                       | RuboCop       | Linting    | `rubocop ruby`        |
| `.golangci.yml`                      | golangci-lint | Linting    | `golang linting`      |

## CSS & Styling

| Pattern                          | Technology        | Category | Query                   |
| -------------------------------- | ----------------- | -------- | ----------------------- |
| `tailwind.config.*`              | Tailwind CSS      | Styling  | `tailwind css`          |
| `styled-components` in deps      | styled-components | Styling  | `styled components css` |
| `*.module.css` / `*.module.scss` | CSS Modules       | Styling  | `css modules styling`   |
| `sass` / `*.scss`                | Sass              | Styling  | `sass scss css`         |

## AI & ML

| Pattern                                         | Technology    | Category | Query                        |
| ----------------------------------------------- | ------------- | -------- | ---------------------------- |
| `anthropic` / `@anthropic-ai/sdk` in deps       | Claude API    | AI       | `claude anthropic ai`        |
| `openai` in deps                                | OpenAI API    | AI       | `openai ai`                  |
| `langchain` in deps                             | LangChain     | AI       | `langchain ai`               |
| `transformers` / `torch` / `tensorflow` in deps | ML frameworks | AI       | `machine learning`           |
| `@modelcontextprotocol` / `mcp` in deps         | MCP           | AI       | `mcp model context protocol` |
| `llamaindex` in deps                            | LlamaIndex    | AI       | `llamaindex ai`              |

## Monorepo

| Pattern               | Technology      | Category | Query                |
| --------------------- | --------------- | -------- | -------------------- |
| `pnpm-workspace.yaml` | pnpm workspaces | Monorepo | `monorepo pnpm`      |
| `lerna.json`          | Lerna           | Monorepo | `monorepo lerna`     |
| `nx.json`             | Nx              | Monorepo | `monorepo nx`        |
| `turbo.json`          | Turborepo       | Monorepo | `monorepo turborepo` |
| `rush.json`           | Rush            | Monorepo | `monorepo rush`      |

## Documentation

| Pattern                             | Technology | Category | Query                      |
| ----------------------------------- | ---------- | -------- | -------------------------- |
| `docusaurus.config.*`               | Docusaurus | Docs     | `docusaurus documentation` |
| `mkdocs.yml`                        | MkDocs     | Docs     | `mkdocs documentation`     |
| `*.mdx`                             | MDX        | Docs     | `mdx documentation`        |
| `hugo.toml` / `hugo.yaml`           | Hugo       | Docs     | `hugo static site`         |
| `_config.yml` (Jekyll)              | Jekyll     | Docs     | `jekyll static site`       |
| `vitepress` in deps / `.vitepress/` | VitePress  | Docs     | `vitepress documentation`  |
