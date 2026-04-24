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

## Tech Stack

| Layer | Choice |
|---|---|
| **Frontend** | Next.js 16 (App Router), TypeScript, Tailwind CSS |
| **Backend** | Spring Boot 3.4, Java 21, Maven |
| **Frontend runtime** | Node.js 22 / npm |
| **Backend runtime** | OpenJDK 21 |
| **Database** | [TBD] |
| **ORM / Query layer** | [TBD] |

---

## Project Structure

```
/
├── frontend/                        # Next.js application
│   ├── app/                         # App Router pages and layouts
│   ├── public/                      # Static assets
│   ├── package.json
│   ├── tsconfig.json
│   ├── tailwind.config.ts
│   └── next.config.ts
│
├── backend/                         # Spring Boot application
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/pethelpan/backend/
│   │   │   │   └── BackendApplication.java
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   │       └── java/com/pethelpan/backend/
│   │           └── BackendApplicationTests.java
│   ├── pom.xml
│   └── mvnw
│
├── .gitignore
├── package.json                     # Root — npm workspaces + convenience scripts
├── LICENSE
└── CLAUDE.md
```

---

## Commands

```bash
# Install all frontend dependencies
npm install

# ── Frontend ──────────────────────────────────────────────────────
# Start Next.js dev server (http://localhost:3000)
npm run dev

# Build frontend for production
npm run build

# Lint frontend
npm run lint

# ── Backend ───────────────────────────────────────────────────────
# Start Spring Boot dev server (http://localhost:8080)
npm run backend:dev
# or directly:
cd backend && ./mvnw spring-boot:run

# Run backend tests
npm run backend:test
# or:
cd backend && ./mvnw test

# Build backend JAR
npm run backend:build
# or:
cd backend && ./mvnw clean package -DskipTests
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

- **Code** (variables, functions, Java classes, React components): English
- **User-facing strings, labels, error messages**: Portuguese (pt-BR)
- **Domain terms** (e.g., "adoção", "resgate"): use Portuguese; add English translation in comments only when non-obvious

### Frontend (Next.js)

- App Router only — no Pages Router
- Components co-located with the route that owns them; shared components go in `frontend/components/`
- Tailwind utility classes directly in JSX — no separate CSS files unless unavoidable
- TypeScript strict mode; no `any` without a comment explaining why

### Backend (Spring Boot)

- Package structure: `com.pethelpan.backend.<feature>` (e.g., `.pet`, `.adoption`, `.rescue`)
- Each feature package owns its controller, service, and repository
- DTOs for all request/response bodies — no entity classes exposed directly to the API
- Bean Validation (`@Valid`) on all controller method parameters
- `application.properties` for config; secrets via environment variables only

### General Rules

- No comments unless the **why** is non-obvious (hidden constraint, workaround, subtle invariant)
- Never explain *what* the code does — well-named identifiers do that
- No speculative or future-proof abstractions — three similar lines beat a premature helper
- No error handling for scenarios that cannot happen — trust framework guarantees
- Validate only at system boundaries (user input, external API responses)

### Testing

- **Frontend**: Jest + React Testing Library; test files co-located as `*.test.tsx`
- **Backend**: JUnit 5 + Spring Boot Test; test files mirror source structure under `src/test/`
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
8. **Monorepo awareness** — frontend changes live under `frontend/`, backend changes under `backend/`; root files (`package.json`, `.gitignore`) affect the whole repo

---

## License

MIT — see [LICENSE](./LICENSE).
