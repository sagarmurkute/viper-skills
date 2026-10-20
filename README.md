# Viper Skills 🐍

> A curated collection of 50 reusable, high-leverage AI coding skills designed for modern software developers and AI agent environments.

---

## 📌 Project Overview

**Viper Skills** is an open-source library of 50 modular, standardized AI coding skills. Each skill is designed to guide AI coding assistants (such as Antigravity, Claude Code, Cursor, Windsurf, GitHub Copilot, and custom agent workflows) through specialized development tasks with predictable, production-ready results.

Instead of writing repetitive, ad-hoc system prompts or debugging prompt drift, developers can install or reference Viper Skills directly in their projects.

---

## 🚀 Planned Distribution Channels

Viper Skills is designed to be accessible across multiple workflows:

1. **GitHub Repository**
   - Central home for open-source development, community contributions, and versioned releases.
   - Developers can browse skills in markdown format or vendor them directly into their repositories.

2. **npm CLI (`packages/cli`)**
   - Command-line tool (e.g., `npx viper-skills add <skill-name>`).
   - Seamlessly discovers, validates, and installs skills into local configuration directories (such as `.agents/skills/`, `.cursor/rules/`, or custom agent paths).

3. **Web Catalog (`apps/website`)**
   - Searchable, category-based web application.
   - Live markdown previews, syntax-highlighted examples, one-click clipboard copying, and single-click `.zip` or `.md` downloads.

---

## 📁 Repository Structure

```text
skills-monorepo/
├── docs/                 # Format specifications, schemas, and usage guides
│   ├── VIPER_FORMAT.md   # Official .viper file format specification
│   └── examples/         # Sample .viper and equivalent SKILL.md files
├── skills/               # Source files for the 50 reusable skills
│   ├── frontend/         # UI components, state management, styling, and web frameworks
│   ├── backend/          # APIs, authentication, business logic, and servers
│   ├── database/         # Schemas, migrations, query optimization, and ORMs
│   ├── devops/           # CI/CD, containers, infrastructure as code, and deployment
│   ├── testing/          # Unit, integration, E2E, and regression testing suites
│   ├── security/         # Vulnerability audits, auth best practices, and sanitization
│   ├── architecture/     # System design patterns, refactoring, and code organization
│   └── automation/       # Tooling, scripting, code generators, and dev workflows
├── packages/
│   └── cli/              # Source code for the future npm CLI tool (local only)
├── apps/
│   └── website/          # Source code for the future browsing portal (local only)
├── scripts/              # Validation schemas, linters, and build utilities
├── tests/                # Automated tests (schema validation, CLI tests, integration)
├── CONTRIBUTING.md       # Guidelines for community contributions
├── LICENSE               # License placeholder (pending maintainer selection)
└── README.md             # Project overview and roadmap
```

---

## 🗺️ Project Phases

- [x] **Phase 1: Project Foundation** — Monorepo layout, documentation, category taxonomy, and contribution guidelines.
- [x] **Phase 2: Skill Specifications & Schema** — Standardized `.viper` format, validation rules, and agent-compatible conversion.
- [ ] **Phase 3: Core Skills Library** — Authoring and validating the 50 specialized AI coding skills.
- [ ] **Phase 4: CLI Development** — Building the npm package for skill discovery and local installation.
- [ ] **Phase 5: Web Platform** — Building the responsive web application for searching and downloading skills.
- [ ] **Phase 6: Verification & Release** — Comprehensive automated testing, end-to-end audits, and public launch.

---

## 🤝 Contributing

Contributions from students and open-source developers are welcome! Please read [CONTRIBUTING.md](file:///d:/All%20Projects/Skills/CONTRIBUTING.md) to get started.
