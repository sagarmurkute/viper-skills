# Viper Skills — The 50 Skills Catalogue 🐍

This catalogue defines the official roster of **50 distinct AI coding skills** for Viper Skills. Every skill is designed to guide AI coding assistants through specialized, production-ready vibe coding and software engineering workflows.

---

## 📐 Catalog Taxonomy & Design Principles

1. **Self-Contained & Reusable**: Each skill addresses a reusable engineering problem applicable across multiple projects, rather than being bound to a single framework or proprietary application.
2. **Deterministic Boundaries**: Skills have explicit, non-overlapping responsibilities. One skill does not step on another skill's domain.
3. **Format Compliance**: Every skill is specified in `.viper` format (see [VIPER_FORMAT.md](file:///d:/All%20Projects/Skills/docs/VIPER_FORMAT.md)) and compiles into an agent-compatible `SKILL.md`.
4. **Group Distribution**: Organized into 5 distinct groups of 10 skills each for clear progression and modular consumption.

---

## 🎨 Group 1: UI/UX & Frontend Engineering (Skills 1–10)

Focused on visual aesthetics, modern design systems, accessibility, component architectures, and responsive user interfaces.

| # | Skill Name | Category | Description | Primary Responsibility |
| :-: | :--- | :--- | :--- | :--- |
| **01** | `clean-react-component` | `frontend` | Scaffolds modular, accessible React components with clean props, hooks, and TypeScript interfaces. | Structure presentational and container components with strict typing, prop validation, and ARIA roles. |
| **02** | `tailwind-vibe-styler` | `frontend` | Crafts modern, aesthetic Tailwind CSS interfaces with curated color palettes, dark mode, and glassmorphism. | Transform rough markup into visually stunning UI using consistent spacing, typography scale, gradients, and theme tokens. |
| **03** | `framer-motion-delight` | `frontend` | Implements smooth micro-interactions, layout transitions, and spring animations with Framer Motion. | Add responsive hover states, enter/exit animations, page transitions, and gestures without degrading performance. |
| **04** | `responsive-navbar-drawer` | `frontend` | Builds responsive navigation headers with mobile slide-over drawers, keyboard trapping, and focus management. | Construct desktop and mobile navigation layouts adhering to WAI-ARIA dialog and disclosure guidelines. |
| **05** | `form-wizard-validator` | `frontend` | Manages complex multi-step forms with schema-driven validation, draft persistence, and step transitions. | Orchestrate step navigation, per-field validation with Zod/React Hook Form, and local storage recovery. |
| **06** | `data-table-pro` | `frontend` | Implements high-performance data tables with column sorting, fuzzy filtering, pagination, and CSV export. | Handle tabular data display, virtualized rows for large datasets, multi-column search, and client-side data exports. |
| **07** | `nextjs-app-router` | `frontend` | Architects Next.js App Router applications with optimal server/client component boundaries and streaming. | Structure route groups, loading skeletons, error boundaries, parallel routes, and dynamic SEO metadata. |
| **08** | `state-machine-flow` | `frontend` | Models predictable UI state machines for complex flows like checkout, onboarding, and async tasks. | Eliminate impossible UI states by implementing explicit state transitions, guards, and context reducers. |
| **09** | `theme-mode-switch` | `frontend` | Implements flicker-free light, dark, and system theme switching with CSS variables and local storage. | Manage theme toggles, synchronize with OS `prefers-color-scheme`, and inject blocking head scripts to prevent theme flashing. |
| **10** | `dashboard-chart-builder` | `frontend` | Builds responsive, interactive analytics charts and metric stat cards using modern SVG charting libraries. | Format timeseries, bar, and donut charts with accessible data tooltips, legends, and dynamic resize handling. |

---

## ⚡ Group 2: Backend Systems & API Development (Skills 11–20)

Focused on robust API routing, authentication protocols, third-party integrations, streaming, and error handling.

| # | Skill Name | Category | Description | Primary Responsibility |
| :-: | :--- | :--- | :--- | :--- |
| **11** | `rest-api-scaffold` | `backend` | Generates standardized RESTful API endpoints with controller-service-repository layered architecture. | Define structured request routing, business logic isolation, parameter extraction, and standard HTTP response envelopes. |
| **12** | `jwt-auth-flow` | `backend` | Implements secure JWT authentication with short-lived access tokens, refresh tokens, and HTTP-only cookies. | Handle user login, token rotation, token revocation blacklisting, and CSRF protection headers. |
| **13** | `trpc-fast-api` | `backend` | Builds end-to-end type-safe API procedures with tRPC routers, inputs, outputs, and contextual middleware. | Create query and mutation procedures with automatic client-side TypeScript inference and request context injection. |
| **14** | `stripe-payment-webhook` | `backend` | Implements idempotent Stripe checkout flows, subscription lifecycles, and cryptographic webhook verification. | Process checkout sessions, invoice updates, cancellation events, and prevent duplicate webhook execution. |
| **15** | `file-upload-s3` | `backend` | Implements secure direct-to-cloud file uploads using pre-signed URLs, MIME whitelisting, and size quotas. | Generate time-limited upload signatures, validate file headers, and sanitize public storage keys. |
| **16** | `websocket-live-sync` | `backend` | Builds real-time WebSocket communication channels with room partitioning and heartbeat reconnection. | Manage client connection registries, broadcast room events, handle ping-pong heartbeats, and reconnect backoff. |
| **17** | `rate-limiter-guard` | `backend` | Implements token bucket and sliding window rate limiting across API routes using Redis or in-memory stores. | Protect public endpoints against brute force, scraping, and DoS attacks by inspecting IP and authenticated user keys. |
| **18** | `api-error-handler` | `backend` | Centralizes API error handling producing RFC 7807 Problem Details with sanitized public messages and private error tracing. | Catch unhandled exceptions, map domain errors to standard HTTP status codes, and attach unique request tracking IDs. |
| **19** | `graphql-schema-builder` | `backend` | Defines GraphQL schemas, type definitions, resolvers, and dataloaders to eliminate N+1 query problems. | Author type-safe query and mutation resolvers, batch database lookups, and validate input arguments. |
| **20** | `email-template-dispatcher` | `backend` | Renders responsive transactional HTML emails and dispatches them via SMTP or third-party email APIs. | Compile dynamic email templates (welcome, password reset, receipts), generate plain-text fallbacks, and queue sends. |

---

## 💾 Group 3: Data Architecture, Storage & Caching (Skills 21–30)

Focused on data modeling, schema safety, fast querying, cache synchronization, and indexing strategies.

| # | Skill Name | Category | Description | Primary Responsibility |
| :-: | :--- | :--- | :--- | :--- |
| **21** | `prisma-schema-master` | `database` | Models relational databases in Prisma with strict relations, indexes, compound keys, and cascade rules. | Structure one-to-one, one-to-many, and many-to-many schemas, add composite unique constraints, and manage Prisma client generation. |
| **22** | `drizzle-orm-ninja` | `database` | Authors high-performance SQL schemas, relational queries, and schema migrations using Drizzle ORM. | Define type-safe SQL tables, write composable joins, and handle atomic transaction blocks with minimal runtime overhead. |
| **23** | `sql-migration-safety` | `database` | Plans and validates zero-downtime database migrations with backward-compatible schema changes and rollbacks. | Execute expand-and-contract column renames, safe index creation without table locking, and data backfill scripts. |
| **24** | `redis-cache-layer` | `database` | Implements cache-aside patterns with time-to-live expiration, atomic cache invalidation, and stampede protection. | Intercept expensive query reads, cache JSON payloads with adaptive TTLs, and invalidate cache keys upon mutations. |
| **25** | `postgres-fulltext-search` | `database` | Implements fast full-text search in PostgreSQL using tsvector columns, GIN indexes, and trigram fuzzy matching. | Index text fields, generate ranked search results with headline highlighting, and handle typo-tolerant search queries. |
| **26** | `database-seeder-mock` | `database` | Generates deterministic, relational mock datasets for local development, integration tests, and staging environments. | Populate interconnected user, product, order, and audit log records with realistic faker data adhering to foreign keys. |
| **27** | `vector-embedding-search` | `database` | Stores, indexes, and queries vector embeddings using pgvector or specialized vector databases for similarity search. | Generate text embeddings, configure HNSW/IVFFlat indexes, and execute cosine similarity top-k semantic searches. |
| **28** | `database-transaction-manager` | `database` | Orchestrates ACID transactions with isolation levels, pessimistic/optimistic locking, and automatic rollback on failure. | Coordinate multi-table operations (e.g., balance transfers, inventory deductions) safely under concurrent read/write loads. |
| **29** | `mongodb-aggregation-pipeline` | `database` | Builds optimized MongoDB aggregation pipelines with filtering, grouping, lookups, and projection stages. | Author multi-stage aggregations (`$match`, `$lookup`, `$group`, `$facet`) with covered indexes for high-throughput analytics. |
| **30** | `audit-log-tracker` | `database` | Implements append-only audit trail logging for tracking record creation, modification, actor IDs, and state diffs. | Capture who changed what, store before/after JSON diffs in tamper-resistant tables, and index by entity ID and timestamp. |

---

## 🧪 Group 4: Testing, Quality Assurance & Debugging (Skills 31–40)

Focused on automated verification, test suites, edge case detection, and deep debugging.

| # | Skill Name | Category | Description | Primary Responsibility |
| :-: | :--- | :--- | :--- | :--- |
| **31** | `vitest-unit-mastery` | `testing` | Writes isolated unit tests with fast execution, mock fixtures, spies, and deterministic assertion checks. | Test pure business logic functions, utility helpers, and service modules covering edge cases and boundary conditions. |
| **32** | `react-testing-library` | `testing` | Tests React components from the end-user's perspective using accessibility queries and realistic user interactions. | Assert element visibility via `findByRole`, fire keyboard/pointer events, and verify accessible user journeys without testing implementation details. |
| **33** | `playwright-e2e-suite` | `testing` | Builds resilient end-to-end browser automation suites using the Page Object Model and network mocking. | Automate multi-page critical user flows (signup, checkout, settings) with automatic retries, screenshot comparisons, and trace recording. |
| **34** | `api-contract-testing` | `testing` | Validates HTTP API responses against OpenAPI or Zod schemas to detect breaking schema contract drifts. | Verify response payload status codes, headers, and property types against formal API specifications automatically. |
| **35** | `mock-service-worker` | `testing` | Intercepts browser and Node.js network requests at the network level using Mock Service Worker (MSW). | Simulate realistic REST and GraphQL responses, network latencies, and error codes during development and automated tests. |
| **36** | `edge-case-fuzzer` | `testing` | Identifies software vulnerabilities and logic crashes by generating pathological, random, and boundary inputs. | Feed unexpected values (nulls, overflow integers, emojis, malformed JSON, SQL strings) into parsers and handlers. |
| **37** | `root-cause-debugger` | `testing` | Analyzes stack traces, application logs, and reproduction steps to isolate the root cause of elusive runtime bugs. | Formulate hypotheses, trace execution flows, inspect variable mutations, and propose minimal, targeted fixes. |
| **38** | `performance-profiler` | `testing` | Profiles frontend render times, memory leaks, bundle sizes, and backend event-loop bottlenecks. | Identify unnecessary React re-renders, uncollected DOM nodes, heavy third-party bundles, and slow server event-loop operations. |
| **39** | `accessibility-audit-axe` | `testing` | Runs automated WCAG 2.1 AA accessibility audits to detect color contrast, missing labels, and keyboard traps. | Evaluate DOM structures with axe-core, highlight violations, and supply exact remediation code for compliance. |
| **40** | `visual-regression-detector` | `testing` | Detects unexpected UI layout shifts and styling regressions using pixel-diff screenshot comparisons. | Capture baseline component and page screenshots across viewports, flag visual regressions, and produce diff overlays. |

---

## 🚀 Group 5: DevOps, Cloud, Security & Architecture (Skills 41–50)

Focused on containerization, CI/CD pipelines, security audits, clean architectural abstractions, and git automation.

| # | Skill Name | Category | Description | Primary Responsibility |
| :-: | :--- | :--- | :--- | :--- |
| **41** | `docker-multistage-node` | `devops` | Authors production-ready, multi-stage Dockerfiles with layer caching, non-root users, and minimal base images. | Optimize container build speeds, strip devDependencies from final images, and configure unprivileged runtime users. |
| **42** | `github-actions-ci` | `devops` | Configures GitHub Actions CI/CD workflows for parallel linting, type-checking, automated testing, and artifact caching. | Write YAML pipeline workflows with matrix testing, dependency caching (`npm`/`pnpm`), and branch protection checks. |
| **43** | `nginx-reverse-proxy` | `devops` | Configures Nginx reverse proxies with SSL termination, gzip/brotli compression, and proxy header forwarding. | Route incoming HTTP traffic, enforce HTTPS redirects, manage WebSocket upgrades, and tune cache-control headers. |
| **44** | `vercel-deploy-optimizer` | `devops` | Optimizes web deployments on Vercel with edge middleware, incremental static regeneration (ISR), and build caching. | Configure route rewrites, edge caching headers, preview deployment environments, and serverless bundle limits. |
| **45** | `docker-compose-dev` | `devops` | Orchestrates cohesive local development environments with containers for web, database, cache, and mail services. | Author `docker-compose.yml` with health checks, persistent volume mounts, environment injection, and internal networking. |
| **46** | `owasp-top-10-audit` | `security` | Audits codebases for OWASP Top 10 vulnerabilities including SQL injection, XSS, insecure deserialization, and SSRF. | Review code patterns, identify dangerous sinks, verify sanitization layers, and prescribe defensive remediation patterns. |
| **47** | `input-sanitizer-zod` | `security` | Enforces strict input boundary validation, entity encoding, and payload whitelisting using Zod schemas. | Strip unexpected object properties, validate string length/patterns, and sanitize raw HTML inputs before processing. |
| **48** | `rbac-permission-engine` | `security` | Implements role-based access control (RBAC) and attribute-based permissions with declarative middleware guards. | Evaluate user roles, resource ownership, and permission policies across API routes and UI action buttons. |
| **49** | `clean-architecture-refactor` | `architecture` | Refactors coupled spaghetti code into clean, modular architecture separating domain entities, use cases, and adapters. | Untangle business logic from database and web frameworks, introduce dependency inversion, and create clear interface boundaries. |
| **50** | `vibe-git-workflow` | `automation` | Automates git branching, Conventional Commit messages, change summarization, and pull request generation. | Format semantic git commits, generate structured PR descriptions with change checklists, and enforce clean branch hygiene. |
