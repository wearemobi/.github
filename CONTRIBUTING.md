# <img src="https://wearemobi.com/icon-light.svg" width="24" height="24" valign="middle"> M.O.B.I.™ · Git Convention v1.3

### Philosophy
This convention is platform-agnostic and designed for **Spec-Driven Development**. It ensures every line of code is backed by a deliberate decision, providing a clear audit trail for the startup's evolution.

### Spec Driven Development
- No code without an approved SPEC.
- Every issue must be created **before** the SPEC is written.
- SPEC lives in `docs/` — versioned and merged before implementation begins.
- A SPEC is approved when it is merged into `main` via PR.

---

## Spec Cycle — Full Flow

```
1. Issue      — Trigger for everything
2. Branch     — docs/spec-vX.X
3. SPEC       — Write, review, approve
4. Commit     — docs(vX.X): add SPEC-vX.X
5. PR         — Rebase merge → main
6. Branch     — feat/v1.2-description (implementation)
7. Review     — Verify history alignment with SPEC
8. Execute    — One commit per change (atomic)
9. PR         — Squash merge → main
```

> [!IMPORTANT]
> **Emergency Hotfix Exception:** If production is down, you may bypass the SPEC. Use the branch `hotfix/description` and merge directly via PR. A post-mortem issue must be created after the fix.

---

## Commits — Conventional Commits

**Format:** `<type>(<scope>)<!>: <description>`

### Types
- `feat`: New feature or capability.
- `fix`: Bug fix (not an enhancement).
- `chore`: Maintenance (dependencies, build scripts, Gradle, Next.js config).
- `docs`: Documentation only (includes SPECs).
- `style`: Visual changes, assets, logos, or formatting (no logic changes).
- `test`: Adding or fixing tests (Kover, JUnit, etc.).

### Scopes
- **SPEC:** Use the version (e.g., `v1.3`).
- **Implementation:** Use the component, module, or layer (e.g., `ui`, `data`, `auth`, `gradle`).

### Breaking Changes
If a change breaks compatibility (e.g., API change, DB migration), add `!` after the type:
`feat(api)!: change payment provider to PayPal Business`

---

## Branches

| Purpose | Pattern | Example |
| :--- | :--- | :--- |
| **SPEC** | `docs/spec-vX.X` | `docs/spec-v1.3` |
| **Feature** | `feat/vX.X` | `feat/v1.3` or  `feat/v1.3-context-description` |
| **Fix** | `fix/description` | `fix/theme-toggle` |
| **Hotfix** | `hotfix/description` | `hotfix/api-crash` |
| **Maintenance**| `chore/description` | `chore/update-kover` |

---

## Pull Requests & Merging

- **Title:** Matches the Issue title (lowercase, no prefix).
- **Body:** Must include `closes #N` and the **Definition of Done** from the SPEC.

**Merge Strategies:**
- **Specs (`docs/`):** Rebase and merge (keep history linear).
- **Code (`feat/`, `fix/`):** Squash and merge (clean `main` history).

---
Copyright © 2026 **M.O.B.I.™** (Machine Oriented Brilliant Ideas™)  
Transforming ideas into high-impact digital solutions. 🚀  
[wearemobi.com](https://wearemobi.com) · contact@wearemobi.com

