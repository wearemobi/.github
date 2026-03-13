# We Are Mobi · Git Convention v1.1

### Philosophy

This convention is platform-agnostic by design. It works on GitHub, GitLab, or any Git host. No tooling lock-in.

### Spec Driven Development

- No code without an approved SPEC
- Every issue must be created **before** the SPEC is written
- SPEC lives in `docs/` — versioned and merged before implementation begins
- Branch scope and commit scope map directly to the SPEC name
- A SPEC is approved when it is merged into `main` via PR

---

## Spec Cycle — Full Flow

Every feature, fix, or chore follows this exact sequence:

```
1. Issue       — create before anything else
2. Branch      — docs/spec-vX.X
3. SPEC        — write, review, approve
4. Commit      — docs(vX.X): add SPEC-vX.X
5. PR          — rebase merge → main
6. Branch      — feat/vX.X-description
7. Review      — read commit history before touching code
8. Execute     — one commit per change
9. PR          — squash merge → main
```

---

## Issues

- Title: no prefix, lowercase, descriptive
- Mandatory label: `feature` · `bug` · `chore` · `docs`
- Reference the SPEC: `Ref: docs/SPEC-*.md`
- Issue is created **before** the SPEC — the issue is the trigger

---

## Branches

```
docs/spec-v1.2          ← SPEC branch always uses this pattern
feat/v1.2-polish        ← implementation branch
feat/prompt-bar
fix/theme-toggle
chore/update-deps
docs/git-convention
```

---

## Commits — Conventional Commits

```
feat(scope): short description
fix(scope): short description
chore(scope): short description
docs(scope): short description
```

**Scope rules:**

| Context               | Scope                                               |
|-----------------------|-----------------------------------------------------|
| SPEC commit           | version — e.g. `v1.2`                               |
| Implementation commit | component or change — e.g. `logo-block`, `prettier` |

- Present tense, imperative, lowercase
- No period at the end

**Examples:**
```
docs(v1.2): add SPEC-v1.2
feat(logo-block): add trademark symbol
fix(chat-input): increase border contrast light mode
chore(prettier): add .prettierrc and .eslintrc
```

---

## Pull Requests

- Title: matches the issue title, no prefix
- Body must include:
  - Link to the issue (`closes #N`)
  - Definition of Done checklist from the SPEC

**Merge strategy:**

| Branch type   | Strategy         |
|---------------|------------------|
| `docs/spec-*` | Rebase and merge |
| All others    | Squash and merge |

---

*We Are Mobi · Git Convention v1.1*
