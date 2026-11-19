# Specification Analysis Report: [Feature Name]

**Branch**: `[###-feature-name]`
**Date**: YYYY-MM-DD
**Artifacts Analyzed**: constitution.md (v[X.Y.Z]), spec.md, plan.md,
data-model.md, contracts/, tasks.md
**Mode**: Read-only (no files modified)

---

## Findings

| ID  | Category        | Severity | Location(s)              | Summary                              | Recommendation                     |
|-----|-----------------|----------|--------------------------|--------------------------------------|------------------------------------|
| A1  | Duplication     | HIGH     | spec.md L120–134         | FR-004 and FR-009 describe same rule | Merge; keep clearer wording        |
| B1  | Ambiguity       | HIGH     | spec.md NFR-002          | "Handle many users" not measurable   | Define target (e.g., 500 concurrent)|
| C1  | Underspec       | MEDIUM   | tasks.md T017            | References undefined ErrorMapper     | Add to plan.md structure or rename |
| D1  | Constitution    | CRITICAL | plan.md Project Structure| 4 projects; constitution allows 3    | Merge projects or justify + amend  |
| E1  | Coverage Gap    | CRITICAL | spec.md FR-006           | No task implements FR-006            | Add test + implementation tasks    |
| E2  | Coverage Gap    | MEDIUM   | spec.md NFR-004          | Accessibility has no task            | Add polish-phase task              |
| F1  | Inconsistency   | MEDIUM   | spec.md vs plan.md       | "Request" vs "Application" used      | Standardize per glossary           |
| F2  | Inconsistency   | HIGH     | tasks.md T015 / T013     | T015 ordered before model it needs   | Reorder dependencies               |

*(Max ~50 findings; remainder summarized in overflow note)*

---

## Coverage Summary

| Requirement Key | Has Task? | Task IDs          | Notes                          |
|-----------------|-----------|-------------------|--------------------------------|
| FR-001          | ✅        | T011, T015, T016  |                                |
| FR-002          | ✅        | T019, T022        |                                |
| FR-006          | ❌        | —                 | See E1                         |
| NFR-001         | ✅        | T030              | Performance validation         |
| NFR-004         | ❌        | —                 | See E2                         |
| User Story 1    | ✅        | T011–T018         |                                |
| EC-02           | ⚠️ Partial| T017              | Test exists, no explicit check |

---

## Constitution Alignment Issues

| Principle            | Issue                                   | Severity |
|----------------------|-----------------------------------------|----------|
| II. Simplicity       | 4 projects exceed limit of 3 (D1)       | CRITICAL |
| I. Test-First        | T024 has no preceding test task         | CRITICAL |

*(None found → "No constitution violations detected.")*

---

## Unmapped Tasks
Tasks not traceable to any requirement or story:
- T027 "Add caching layer" — no NFR requires it; possible over-engineering

---

## Metrics

| Metric                         | Value   |
|--------------------------------|---------|
| Total Requirements (FR + NFR)  | [N]     |
| Total Tasks                    | [N]     |
| Coverage % (reqs with ≥1 task) | [N]%    |
| Ambiguity Count                | [N]     |
| Duplication Count              | [N]     |
| Critical Issues                | [N]     |
| High Issues                    | [N]     |

---

## Next Actions

**If CRITICAL issues exist**: Resolve before /speckit.implement.
- D1 → Revise plan.md structure, or amend constitution via /speckit.constitution
- E1 → Re-run /speckit.tasks or manually add tasks for FR-006

**If only HIGH/MEDIUM/LOW**: You may proceed, but address:
- B1 → Run /speckit.specify refinement or edit NFR-002
- F1 → Standardize terminology across artifacts

**Suggested commands**:
- /speckit.clarify   (for ambiguity findings)
- /speckit.plan      (for architecture/constitution findings)
- /speckit.tasks     (for coverage gaps)

---

## Remediation Offer
"Would you like me to suggest concrete remediation edits for the
top [N] issues?" *(Edits are only applied after explicit approval.)*