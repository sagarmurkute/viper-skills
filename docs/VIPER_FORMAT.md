# The `.viper` Skill File Specification 🐍

**Specification Version**: `1.0.0`  
**Status**: Stable Draft  

---

## 1. Overview & Purpose

The `.viper` format is the official authoring, packaging, and distribution format for **Viper Skills**. It is a human-readable, Markdown-based document that pairs machine-parseable YAML frontmatter with standardized Markdown sections.

> [!IMPORTANT]  
> **Distribution Format vs. Agent Runtime**: AI coding agents (such as Antigravity, Cursor, Claude Code, and Copilot) do not natively recognize `.viper` files out of the box. The `.viper` format is our project's single source of truth. When users install or download a skill, our CLI or web platform compiles the `.viper` file into a native `SKILL.md` (or equivalent rule file) compatible with their AI environment.

---

## 2. File Format Structure

Every `.viper` file consists of two primary parts:
1. **Header Metadata**: YAML frontmatter enclosed by triple-dash lines (`---`).
2. **Body Content**: Standardized Markdown sections detailing instructions, guardrails, and criteria.

```text
---
name: <kebab-case-name>
version: <semver>
description: <concise summary>
category: <canonical-category>
tags: [<optional>, <tags>]
---

# <Skill Title>

## Overview
...

## Workflow
...

## Constraints
...

## Examples
...

## Completion Criteria
...
```

---

## 3. Required & Optional Metadata

The frontmatter MUST contain the following four mandatory fields:

| Field | Type | Requirement | Description |
| :--- | :--- | :--- | :--- |
| `name` | String | **Required** | Unique skill identifier in `kebab-case` (e.g., `clean-react-component`). Pattern: `^[a-z0-9-]+$` |
| `version` | String | **Required** | Semantic versioning format `MAJOR.MINOR.PATCH` (e.g., `1.0.0`). |
| `description` | String | **Required** | A clear, single-sentence summary explaining what the skill accomplishes and when to trigger it. |
| `category` | String | **Required** | Must match one of the 8 canonical categories: `frontend`, `backend`, `database`, `devops`, `testing`, `security`, `architecture`, `automation`. |
| `tags` | Array/List | Optional | Search keywords for indexing in the web portal and CLI. |
| `compatibility`| Array/List | Optional | Target agent environments (e.g., `antigravity`, `claude-code`, `cursor`). |
| `author` | String | Optional | Skill author or contributor handle. |

---

## 4. Standard Body Sections

The Markdown body provides clear, deterministic instructions to guide the AI model without ambiguity:

1. **`# <Skill Title>`**: The human-readable title of the skill.
2. **`## Overview`**: Contextual explanation of the problem solved and prerequisites.
3. **`## Workflow`**: Sequentially numbered, step-by-step procedure the AI must follow.
4. **`## Constraints`**: Hard guardrails, anti-patterns to avoid, and architectural rules.
5. **`## Examples`**: Concrete input-output pairs or code snippets demonstrating target quality.
6. **`## Completion Criteria`**: An actionable markdown checklist (`- [ ]`) verifying full task completion.

---

## 5. Pure Node.js Parsing (Zero Dependencies)

The `.viper` format is intentionally designed to be parsed easily in Node.js without requiring external npm packages like `gray-matter` or `yaml`:

```javascript
/**
 * Parses a .viper file into metadata and markdown body.
 * @param {string} content - Raw content of the .viper file.
 * @returns {{ metadata: Record<string, string>, body: string }}
 */
function parseViper(content) {
  const parts = content.split(/^---$/m);
  if (parts.length < 3) {
    throw new Error("Invalid .viper format: missing opening or closing '---' frontmatter boundary");
  }

  const frontmatter = parts[1].trim();
  const body = parts.slice(2).join('---').trim();

  const metadata = {};
  const lines = frontmatter.split(/\r?\n/);
  
  for (const line of lines) {
    const trimmed = line.trim();
    if (!trimmed || trimmed.startsWith('#')) continue;
    
    const colonIdx = trimmed.indexOf(':');
    if (colonIdx === -1) continue;
    
    const key = trimmed.slice(0, colonIdx).trim();
    const value = trimmed.slice(colonIdx + 1).trim().replace(/^['"](.*)['"]$/, '$1');
    metadata[key] = value;
  }

  // Validate mandatory fields
  const required = ['name', 'version', 'description', 'category'];
  for (const field of required) {
    if (!metadata[field]) {
      throw new Error(`Validation Error: Missing required field '${field}'`);
    }
  }

  return { metadata, body };
}
```

---

## 6. Converting `.viper` to `SKILL.md`

Agent platforms like **Antigravity**, **Claude Code**, and **Cursor** expect a `SKILL.md` file with a minimal frontmatter header (`name` and `description`) followed by execution instructions.

### Conversion Logic
1. Extract `name` and `description` from the `.viper` frontmatter.
2. Construct the standard `SKILL.md` YAML frontmatter with `name` and `description`.
3. Retain the complete body (Workflow, Constraints, Examples, Completion Criteria) verbatim.

### Pure Node.js Converter
```javascript
/**
 * Converts a .viper file string to a compatible SKILL.md string.
 * @param {string} viperContent
 * @returns {string} Compatible SKILL.md content
 */
function viperToSkillMd(viperContent) {
  const { metadata, body } = parseViper(viperContent);
  
  return [
    '---',
    `name: ${metadata.name}`,
    `description: ${metadata.description}`,
    '---',
    '',
    body,
    ''
  ].join('\n');
}
```

---

## 7. Validation Rules & Compatibility Guarantees

### Validation Checklist
- [x] File must begin with `---` on line 1.
- [x] Frontmatter must close with `---` on a subsequent line.
- [x] All 4 mandatory fields (`name`, `version`, `description`, `category`) must exist and have non-empty values.
- [x] `category` must match one of the 8 canonical categories.
- [x] Body must contain at least `## Workflow`, `## Constraints`, and `## Completion Criteria`.

### Forward & Backward Compatibility
- **Open-World Metadata**: Parsers must ignore unknown keys in the frontmatter, allowing future versions to add new metadata (e.g., `dependencies`, `min_agent_version`) without breaking older parsers.
- **Section Tolerance**: Additional markdown sections (e.g., `## Troubleshooting`, `## Alternatives`) are permitted and will be preserved during conversion.
- **Semver Evolution**: Breaking changes to the `.viper` format specification will bump the specification version's MAJOR number.
