# Detection Patterns

Mapping of file patterns to technologies and recommended `npx skills find` queries.

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
| `*.rb`                                                         | Ruby        | Language | `ruby`              |
| `*.py`                                                         | Python      | Language | `python`            |
| `*.rs`                                                         | Rust        | Language | `rust`              |
| `*.go`                                                         | Go          | Language | `golang`            |
| `*.swift`                                                      | Swift       | Language | `swift`             |
| `*.kt` / `*.kts`                                               | Kotlin      | Language | `kotlin`            |
| `*.scala`                                                      | Scala       | Language | `scala`             |
| `*.clj`                                                        | Clojure     | Language | `clojure`           |
| `*.zig`                                                        | Zig         | Language | `zig`               |

## Frameworks — JavaScript/TypeScript

| Pattern                                    | Technology          | Category  | Query                |
| ------------------------------------------ | ------------------- | --------- | -------------------- |
| `next.config.*`                            | Next.js             | Framework | `nextjs react`       |
| `nuxt.config.*`                            | Nuxt                | Framework | `nuxt vue`           |
| `svelte.config.*`                          | SvelteKit           | Framework | `svelte sveltekit`   |
| `astro.config.*`                           | Astro               | Framework | `astro`              |
| `remix.config.*` / `remix.env.d.ts`        | Remix               | Framework | `remix react`        |
| `gatsby-config.*`                          | Gatsby              | Framework | `gatsby react`       |
| `angular.json`                             | Angular             | Framework | `angular typescript` |
| `vite.config.*` (with vue plugin)          | Vue                 | Framework | `vue vite`           |
| `electron-builder.*` / `electron.config.*` | Electron            | Framework | `electron desktop`   |
| `expo-constants` / `app.json` (with expo)  | Expo / React Native | Framework | `react native expo`  |
| `contentlayer.config.*`                    | Contentlayer        | Framework | `contentlayer mdx`   |
| `payload.config.*`                         | Payload CMS         | Framework | `payload cms`        |
| `sanity.config.*` / `sanity.json`          | Sanity              | Framework | `sanity cms`         |
| `strapi` (in package.json)                 | Strapi              | Framework | `strapi cms`         |

## Frameworks — Python

| Pattern                        | Technology | Category  | Query                 |
| ------------------------------ | ---------- | --------- | --------------------- |
| `manage.py` / `django` in deps | Django     | Framework | `django python`       |
| `flask` in deps                | Flask      | Framework | `flask python api`    |
| `fastapi` in deps              | FastAPI    | Framework | `fastapi python api`  |
| `streamlit` in deps            | Streamlit  | Framework | `streamlit python`    |
| `scrapy.cfg`                   | Scrapy     | Framework | `scrapy python`       |
| `celery` in deps               | Celery     | Framework | `celery python tasks` |

## Frameworks — Other Languages

| Pattern                                       | Technology    | Category  | Query            |
| --------------------------------------------- | ------------- | --------- | ---------------- |
| `config/routes.rb`                            | Ruby on Rails | Framework | `rails ruby`     |
| `actix-web` / `axum` / `rocket` in Cargo.toml | Rust web      | Framework | `rust web api`   |
| `gin` / `echo` / `fiber` in go.mod            | Go web        | Framework | `golang web api` |
| `Spring` in pom.xml/build.gradle              | Spring Boot   | Framework | `spring java`    |
| `Laravel` in composer.json                    | Laravel       | Framework | `laravel php`    |
| `Symfony` in composer.json                    | Symfony       | Framework | `symfony php`    |

## Build Tools & Bundlers

| Pattern                         | Technology   | Category | Query                |
| ------------------------------- | ------------ | -------- | -------------------- |
| `webpack.config.*`              | Webpack      | Build    | `webpack bundler`    |
| `vite.config.*`                 | Vite         | Build    | `vite`               |
| `rollup.config.*`               | Rollup       | Build    | `rollup bundler`     |
| `esbuild.*` / `tsup.config.*`   | esbuild/tsup | Build    | `esbuild typescript` |
| `turbo.json`                    | Turborepo    | Build    | `turborepo monorepo` |
| `nx.json`                       | Nx           | Build    | `nx monorepo`        |
| `Makefile`                      | Make         | Build    | `makefile`           |
| `justfile`                      | Just         | Build    | `just taskrunner`    |
| `Taskfile.yml`                  | Task         | Build    | `taskfile`           |
| `Gruntfile.*`                   | Grunt        | Build    | `grunt`              |
| `gulpfile.*`                    | Gulp         | Build    | `gulp`               |
| `CMakeLists.txt`                | CMake        | Build    | `cmake cpp`          |
| `meson.build`                   | Meson        | Build    | `meson`              |
| `bazel` / `BUILD` / `WORKSPACE` | Bazel        | Build    | `bazel`              |

## Testing

| Pattern                                                       | Technology | Category | Query                     |
| ------------------------------------------------------------- | ---------- | -------- | ------------------------- |
| `jest.config.*` / `jest` in package.json                      | Jest       | Testing  | `jest testing javascript` |
| `vitest.config.*` / `vitest` in package.json                  | Vitest     | Testing  | `vitest testing`          |
| `cypress.config.*` / `cypress/`                               | Cypress    | Testing  | `cypress e2e testing`     |
| `playwright.config.*`                                         | Playwright | Testing  | `playwright e2e testing`  |
| `.storybook/`                                                 | Storybook  | Testing  | `storybook components`    |
| `pytest.ini` / `conftest.py` / `pyproject.toml` [tool.pytest] | pytest     | Testing  | `pytest python testing`   |
| `phpunit.xml`                                                 | PHPUnit    | Testing  | `phpunit php testing`     |
| `*.test.rs` / `#[cfg(test)]`                                  | Rust tests | Testing  | `rust testing`            |
| `*_test.go`                                                   | Go tests   | Testing  | `golang testing`          |
| `rspec` / `spec/`                                             | RSpec      | Testing  | `rspec ruby testing`      |
| `*.spec.ts` / `*.spec.js`                                     | Spec files | Testing  | `testing`                 |

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
| `appveyor.yml`            | AppVeyor            | CI/CD    | `appveyor ci`       |
| `.woodpecker/`            | Woodpecker CI       | CI/CD    | `woodpecker ci`     |

## Database & ORM

| Pattern                          | Technology              | Category | Query                        |
| -------------------------------- | ----------------------- | -------- | ---------------------------- |
| `prisma/schema.prisma`           | Prisma                  | Database | `prisma database orm`        |
| `drizzle.config.*` / `drizzle/`  | Drizzle                 | Database | `drizzle database orm`       |
| `knexfile.*`                     | Knex                    | Database | `knex database sql`          |
| `sequelize` in deps              | Sequelize               | Database | `sequelize database orm`     |
| `typeorm` in deps                | TypeORM                 | Database | `typeorm database orm`       |
| `alembic/` / `alembic.ini`       | Alembic                 | Database | `alembic python database`    |
| `sqlalchemy` in deps             | SQLAlchemy              | Database | `sqlalchemy python database` |
| `db/migrate/`                    | ActiveRecord migrations | Database | `rails database migrations`  |
| `diesel.toml`                    | Diesel                  | Database | `diesel rust database`       |
| `mongosh` / `mongoose` in deps   | MongoDB                 | Database | `mongodb database`           |
| `redis` in deps                  | Redis                   | Database | `redis caching`              |
| `supabase/` / `supabase` in deps | Supabase                | Database | `supabase database`          |

## Infrastructure & Deployment

| Pattern                                                      | Technology           | Category       | Query                      |
| ------------------------------------------------------------ | -------------------- | -------------- | -------------------------- |
| `Dockerfile`                                                 | Docker               | Infrastructure | `docker containers`        |
| `docker-compose.yml` / `docker-compose.yaml` / `compose.yml` | Docker Compose       | Infrastructure | `docker compose`           |
| `*.tf` / `terraform/`                                        | Terraform            | Infrastructure | `terraform infrastructure` |
| `pulumi/` / `Pulumi.yaml`                                    | Pulumi               | Infrastructure | `pulumi infrastructure`    |
| `cdk.json` / `cdk/`                                          | AWS CDK              | Infrastructure | `aws cdk infrastructure`   |
| `serverless.yml` / `serverless.ts`                           | Serverless Framework | Infrastructure | `serverless aws lambda`    |
| `k8s/` / `kubernetes/` / `*.k8s.yml`                         | Kubernetes           | Infrastructure | `kubernetes deployment`    |
| `helm/` / `Chart.yaml`                                       | Helm                 | Infrastructure | `helm kubernetes`          |
| `fly.toml`                                                   | Fly.io               | Infrastructure | `fly deployment`           |
| `vercel.json`                                                | Vercel               | Infrastructure | `vercel deployment`        |
| `netlify.toml`                                               | Netlify              | Infrastructure | `netlify deployment`       |
| `render.yaml`                                                | Render               | Infrastructure | `render deployment`        |
| `railway.json` / `railway.toml`                              | Railway              | Infrastructure | `railway deployment`       |
| `heroku.yml` / `Procfile`                                    | Heroku               | Infrastructure | `heroku deployment`        |
| `ansible/` / `playbook.yml`                                  | Ansible              | Infrastructure | `ansible automation`       |

## API & Communication

| Pattern                                       | Technology              | Category | Query                 |
| --------------------------------------------- | ----------------------- | -------- | --------------------- |
| `*.proto`                                     | Protocol Buffers / gRPC | API      | `grpc protobuf api`   |
| `*.graphql` / `*.gql` / `codegen.yml`         | GraphQL                 | API      | `graphql api`         |
| `openapi.yaml` / `openapi.json` / `swagger.*` | OpenAPI / Swagger       | API      | `openapi rest api`    |
| `trpc` in deps                                | tRPC                    | API      | `trpc typescript api` |
| `*.wsdl`                                      | SOAP                    | API      | `soap xml api`        |
| `kafka` in deps                               | Kafka                   | API      | `kafka messaging`     |
| `rabbitmq` / `amqp` in deps                   | RabbitMQ                | API      | `rabbitmq messaging`  |

## Linting & Formatting

| Pattern                                       | Technology    | Category | Query                 |
| --------------------------------------------- | ------------- | -------- | --------------------- |
| `.eslintrc*` / `eslint.config.*`              | ESLint        | Linting  | `eslint javascript`   |
| `biome.json` / `biome.jsonc`                  | Biome         | Linting  | `biome formatting`    |
| `.prettierrc*` / `prettier.config.*`          | Prettier      | Linting  | `prettier formatting` |
| `.stylelintrc*`                               | Stylelint     | Linting  | `stylelint css`       |
| `ruff.toml` / `[tool.ruff]` in pyproject.toml | Ruff          | Linting  | `ruff python linting` |
| `.rubocop.yml`                                | RuboCop       | Linting  | `rubocop ruby`        |
| `clippy` (Rust)                               | Clippy        | Linting  | `rust clippy linting` |
| `golangci-lint` / `.golangci.yml`             | golangci-lint | Linting  | `golang linting`      |

## CSS & Styling

| Pattern                          | Technology        | Category | Query                   |
| -------------------------------- | ----------------- | -------- | ----------------------- |
| `tailwind.config.*`              | Tailwind CSS      | Styling  | `tailwind css`          |
| `styled-components` in deps      | styled-components | Styling  | `styled components css` |
| `*.module.css` / `*.module.scss` | CSS Modules       | Styling  | `css modules styling`   |
| `sass` / `*.scss`                | Sass              | Styling  | `sass scss css`         |

## AI & ML

| Pattern                                    | Technology    | Category | Query                        |
| ------------------------------------------ | ------------- | -------- | ---------------------------- |
| `anthropic` / `@anthropic-ai/sdk` in deps  | Claude API    | AI       | `claude anthropic ai`        |
| `openai` in deps                           | OpenAI        | AI       | `openai ai`                  |
| `langchain` in deps                        | LangChain     | AI       | `langchain ai`               |
| `transformers` in deps                     | Hugging Face  | AI       | `huggingface ml`             |
| `tensorflow` / `torch` / `pytorch` in deps | ML frameworks | AI       | `machine learning`           |
| `mcp` / `@modelcontextprotocol` in deps    | MCP           | AI       | `mcp model context protocol` |

## Monorepo

| Pattern                   | Technology      | Category | Query                 |
| ------------------------- | --------------- | -------- | --------------------- |
| `pnpm-workspace.yaml`     | pnpm workspaces | Monorepo | `monorepo pnpm`       |
| `lerna.json`              | Lerna           | Monorepo | `monorepo lerna`      |
| `nx.json`                 | Nx              | Monorepo | `monorepo nx`         |
| `turbo.json`              | Turborepo       | Monorepo | `monorepo turborepo`  |
| `rush.json`               | Rush            | Monorepo | `monorepo rush`       |
| `packages/*/package.json` | Workspaces      | Monorepo | `monorepo workspaces` |

## Documentation & Content

| Pattern                   | Technology | Category | Query                      |
| ------------------------- | ---------- | -------- | -------------------------- |
| `*.mdx`                   | MDX        | Docs     | `mdx documentation`        |
| `docusaurus.config.*`     | Docusaurus | Docs     | `docusaurus documentation` |
| `mkdocs.yml`              | MkDocs     | Docs     | `mkdocs documentation`     |
| `_config.yml` (Jekyll)    | Jekyll     | Docs     | `jekyll static site`       |
| `hugo.toml` / `hugo.yaml` | Hugo       | Docs     | `hugo static site`         |
