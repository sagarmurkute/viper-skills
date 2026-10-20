# Skills Directory 📚

This directory will house the source files for our **50 reusable AI coding skills**, categorized logically for easy maintenance, discovery, and automated distribution.

---

## 🗂️ Skill Categories

| Category | Description | Target Scope |
| :--- | :--- | :--- |
| `frontend/` | Client-side UI, modern web frameworks, state management, styling, and accessibility. | 7-8 skills |
| `backend/` | REST/GraphQL APIs, server patterns, microservices, auth flows, and middleware. | 7-8 skills |
| `database/` | Database modeling, SQL/NoSQL schema migrations, indexing, and ORM query tuning. | 6-7 skills |
| `devops/` | CI/CD pipelines, Docker containerization, Kubernetes basics, cloud deployment, and IaC. | 6-7 skills |
| `testing/` | Unit testing, integration tests, E2E automation (Playwright/Cypress), and mocking. | 6-7 skills |
| `security/` | Vulnerability assessment, OWASP Top 10 mitigation, token handling, and input sanitization. | 5-6 skills |
| `architecture/` | System design, clean code refactoring, domain-driven design, and design patterns. | 5-6 skills |
| `automation/` | Developer tooling, code scaffolding, git automation, and maintenance workflows. | 5-6 skills |

**Total Target**: 50 battle-tested skills.

---

## 📄 Skill File Formats

Skills in this project are authored and distributed using our **`.viper` format** (see [VIPER_FORMAT.md](file:///d:/All%20Projects/Skills/docs/VIPER_FORMAT.md)).

```text
skills/<category>/<skill-name>/
├── skill.viper         # Source of truth in .viper format (metadata + instructions)
├── SKILL.md            # Generated agent-compatible format (for Antigravity/Cursor/Claude)
└── examples/           # (Optional) Reference code or fixtures
```

> **Note**: AI coding agents do not natively parse `.viper` files directly. The `.viper` format serves as our distribution, cataloging, and validation format, which compiles into standard `SKILL.md` when installed into agent environments.

