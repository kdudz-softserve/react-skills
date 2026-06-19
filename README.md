# Advanced React Skills

This repository contains a shareable skill suite for agents working as advanced React developers. The skills are written as reusable workflow instructions with focused reference notes for deeper guidance.

## What's Included

| Skill | Use when working on |
|---|---|
| `react-frontend-architecture` | App structure, feature boundaries, routing ownership, state placement, hooks patterns, and React Server Components. |
| `react-code-review` | React diffs, pull requests, component risks, hooks, TypeScript quality, accessibility regressions, and test gaps. |
| `react-testing-strategy` | Unit, integration, component, browser, end-to-end, visual, and accessibility testing decisions. |
| `react-refactoring` | Component splitting, hook extraction, modularization, duplication reduction, and behavior-preserving cleanup. |
| `react-performance` | Rendering performance, bundle size, lazy loading, memoization, data waterfalls, and Core Web Vitals. |
| `react-fullstack-integration` | REST, GraphQL, RPC, Next.js APIs, Server Actions, RSC, validation, caching, and backend interop. |
| `react-auth-architecture` | Authentication, authorization, sessions, route guards, OAuth/OIDC, Better Auth, RBAC, ABAC, and protected API access. |
| `react-data-database-integration` | Data flows, database-facing API contracts, schema-driven types, query caches, mutations, optimistic updates, and pagination. |
| `design-to-react-implementation` | Figma-to-React implementation, design tokens, shadcn/ui patterns, accessibility semantics, responsive layouts, and visual QA. |
| `react-template-documentation-devops` | README, onboarding, ADRs, GitHub Actions, CI checks, contribution guidance, and release hygiene. |

## Repository Layout

```text
.
|-- AGENTS.md
|-- README.md
|-- docs/
|   `-- superpowers/
|       |-- plans/
|       `-- specs/
`-- skills/
    `-- <skill-name>/
        |-- SKILL.md
        `-- references/
```

Each `SKILL.md` starts with front matter:

```yaml
---
name: skill-name
description: Use when ...
---
```

The agent should read a matching `SKILL.md` before starting related work, then read only the referenced files needed for the task.

## How Teammates Can Use This

1. Clone or download this repository.
2. Copy the desired folders from `skills/` into the agent's skill directory, or configure the agent to load skills from this repository if your tooling supports repository-backed skills.
3. Keep `AGENTS.md` in the repository root so agents know to check for Superpowers workflows and use the React skill suite.
4. Start a new agent session in the repository and ask it to use the relevant skill by name, for example:

```text
Use react-code-review to review this PR.
```

## Maintaining The Skill Suite

- Keep every skill in `skills/<skill-name>/SKILL.md`.
- Keep deeper guidance in `skills/<skill-name>/references/`.
- When a `SKILL.md` mentions a reference file, make sure that file exists.
- Keep planning documents in `docs/superpowers/plans/`.
- Keep design specs in `docs/superpowers/specs/`.
- Do not include local operating-system files, editor caches, dependency folders, or generated build output.

## Pre-Upload Checklist

Run these checks before sharing the repository:

```bash
find skills -mindepth 2 -maxdepth 2 -name SKILL.md -print
find skills -name '*.md' -print
find . -name .DS_Store -print
rg -n "TODO|FIXME|TBD" skills AGENTS.md docs
rg -n "/Users" skills AGENTS.md docs
```

Expected result:

- Each skill folder has one `SKILL.md`.
- Markdown files are present under each `references/` folder.
- No `.DS_Store` files are found.
- No local machine paths or unresolved placeholders are found.
