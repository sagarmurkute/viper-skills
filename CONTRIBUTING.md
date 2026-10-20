# Contributing to Viper Skills 🐍

Thank you for your interest in contributing to **Viper Skills**! This project is maintained by students and open-source enthusiasts. We welcome contributions of all levels, from fixing typos to proposing new AI coding skills.

---

## 🧭 Ways to Contribute

1. **Skills (`skills/`)**: Propose, refine, or review AI coding skills across any defined category.
2. **CLI Package (`packages/cli/`)**: Assist in building the command-line interface for installing skills.
3. **Web Application (`apps/website/`)**: Help develop and style the interactive catalog web app.
4. **Validation Scripts (`scripts/`)**: Improve schema checkers, markdown linters, or metadata generators.
5. **Testing (`tests/`)**: Expand automated tests for skill formats and CLI operations.
6. **Documentation**: Clarify guides, fix examples, and improve project clarity.

---

## 🛠️ General Contribution Workflow

1. **Fork and Clone** the repository.
2. **Create a Feature Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Keep Changes Focused**: Each pull request should address a single skill, bug fix, or feature.
4. **Follow Folder Conventions**:
   - Place skills only inside their appropriate category within `skills/<category>/<skill-name>/`.
   - Ensure skill documentation adheres to the project's standard structure.
5. **Test Your Changes**: Verify that files pass linting and validation once scripts are introduced.
6. **Commit and Push**:
   ```bash
   git commit -m "feat(skills): add react-query-migration skill"
   git push origin feature/your-feature-name
   ```
7. **Open a Pull Request**: Provide a descriptive title and a summary of what changed and why.

---

## 📐 Skill Contribution Standards

When authoring skills in later phases, ensure each skill follows these core rules:

- **Predictable Outcomes**: Write instructions that provide clear, repeatable steps for an AI model.
- **No Hallucinated Tools**: Only reference real, verified libraries, CLI tools, and API patterns.
- **Context-Efficient**: Keep instructions concise, avoiding bloated prose or unhelpful fluff.
- **Categorization**: Match the skill to one of the 8 canonical categories (`frontend`, `backend`, `database`, `devops`, `testing`, `security`, `architecture`, `automation`).

---

## 💬 Community & Etiquette

- **Be Welcoming**: Everyone is learning. Be supportive, constructive, and kind in code reviews and discussions.
- **Ask Questions**: If unsure about where a skill fits or how to structure an idea, open an Issue first for discussion.
