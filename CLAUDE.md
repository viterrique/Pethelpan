# Pethelpan — CLAUDE.md

> **Assistente para adoção e resgate de animais em situação de risco**
> Assistant for the adoption and rescue of at-risk animals.

This file is the authoritative guide for AI assistants (Claude Code and others) working on this repository. Keep it updated as the project evolves.

---

## Project Overview

| Field | Value |
|---|---|
| Name | Pethelpan |
| Purpose | Help people adopt or rescue animals in danger |
| Target language | Portuguese (pt-BR) |
| License | MIT |
| Owner | viterrique |
| GitHub | `viterrique/Pethelpan` |

The application connects people who want to adopt or rescue animals with those who need help placing animals in safe situations. UI text, user-facing strings, and domain terminology are in Portuguese.

---

## Repository Status

This repository is in its **initial setup phase**. Only a `LICENSE` file exists. This CLAUDE.md establishes conventions so that the first lines of code land in a consistent, well-structured project.

When you add the first real code, update the sections marked **[TBD]** below.

---

## Tech Stack [TBD]

Not yet decided. When chosen, document here:

- **Language / Runtime**: e.g., Node.js 22, Python 3.12
- **Framework**: e.g., Next.js, FastAPI, Django
- **Database**: e.g., PostgreSQL, SQLite
- **ORM / Query layer**: e.g., Prisma, SQLAlchemy
- **Testing framework**: e.g., Jest, pytest
- **Package manager**: e.g., npm, pnpm, uv, pip

---

## Project Structure [TBD]

Document the directory layout once scaffolded. Example placeholder:

```
/
├── src/          # Application source code
├── tests/        # Test files
├── docs/         # Documentation
├── LICENSE
└── CLAUDE.md
```

---

## Commands [TBD]

Fill in once the stack is chosen:

```bash
# Install dependencies
<command>

# Start development server
<command>

# Run tests
<command>

# Lint / format
<command>

# Build for production
<command>
```

---

## Development Workflow

### Branches

| Pattern | Purpose |
|---|---|
| `main` | Stable, production-ready code — never push directly |
| `feat/short-description` | New features |
| `fix/short-description` | Bug fixes |
| `chore/short-description` | Maintenance, config, deps |
| `docs/short-description` | Documentation only |
| `claude/description-hash` | AI-generated branches (auto-assigned) |

### Commit Messages

Use **Conventional Commits** style:

```
feat: add pet search by location
fix: correct rescue request form validation
docs: update README with setup steps
chore: upgrade dependencies
```

- One concern per commit
- Imperative mood ("add", not "added")
- No period at end of subject line

### Pull Requests

- Open a PR for every change to `main`
- Keep PRs focused on one concern
- Describe *why*, not just *what*

---

## Coding Conventions

### Language in Code vs. UI

- **Code** (variables, functions, comments): English
- **User-facing strings, labels, error messages**: Portuguese (pt-BR)
- **Domain terms** (e.g., "adoção", "resgate"): use Portuguese; add English translation in comments only when non-obvious

### General Rules

- No comments unless the **why** is non-obvious (hidden constraint, workaround, subtle invariant)
- Never explain *what* the code does — well-named identifiers do that
- No speculative or future-proof abstractions — three similar lines beat a premature helper
- No error handling for scenarios that cannot happen — trust framework guarantees
- Validate only at system boundaries (user input, external API responses)

### Testing

- Tests live alongside source or in a dedicated `tests/` directory — decide and document once the stack is chosen
- Each public function/endpoint should have at least one test covering the happy path
- Test names describe behavior: `should return 404 when pet not found`

---

## AI Assistant Guidelines

When working in this repository:

1. **Check before creating** — search for existing utilities, patterns, and components before writing new ones
2. **Update this file** — when the tech stack, structure, or major conventions change, reflect it here
3. **Branch naming** — AI-generated branches use `claude/description-hash` format
4. **Scope discipline** — implement only what is requested; no extra cleanup, refactors, or features
5. **Commit early and clearly** — use conventional commit messages that explain the *why*
6. **No force-push to main** — always confirm before destructive git operations
7. **Portuguese context** — the project serves a Portuguese-speaking audience; respect that in string choices and domain naming

---

## License

MIT — see [LICENSE](./LICENSE).
