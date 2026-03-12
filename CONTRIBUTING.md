## We Are Mobi · Git Convention v1.0

### Philosophy

This convention is platform-agnostic by design. It works on GitHub, GitLab, or any Git host. No tooling lock-in.

### Spec Driven Development

- No code without an approved SPEC
- Every feature issue must reference a SPEC
- SPEC lives in `docs/` — versioned and merged before implementation begins
- Branch scope and commit scope map directly to the SPEC name
- A SPEC is approved when it is merged into `main` via PR

---

### Issues

- Title: no prefix, lowercase, descriptive
- Mandatory label: `feature` · `bug` · `chore` · `docs`
- Reference the SPEC: `Ref: docs/SPEC-*.md`

### Branches

```
feat/spec-initial
feat/prompt-bar
fix/theme-toggle
chore/update-deps
docs/git-convention
```

### Commits — Conventional Commits

```
feat(scope): short description
fix(scope): short description
chore(scope): short description
docs(scope): short description
```

- Scope = SPEC name or component name
- Present tense, imperative, lowercase
- No period at the end

### Pull Requests

- Title: matches the issue title, no prefix
- Body must include:
  - Link to the issue
  - Definition of Done checklist from the SPEC

---

*We Are Mobi · Git Convention v1.0*

---
