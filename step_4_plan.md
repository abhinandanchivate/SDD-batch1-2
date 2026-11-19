# Implementation Plan: [Feature Name]

**Branch**: `[###-feature-name]`
**Date**: YYYY-MM-DD
**Spec**: specs/[###-feature-name]/spec.md
**Constitution Version**: [e.g., 1.0.0]
**Status**: Draft | Approved

---

## Summary
Primary requirement from the spec in 2–3 sentences, plus the chosen
technical approach in 1–2 sentences.

---

## Technical Context
| Item                   | Decision                                        |
|------------------------|-------------------------------------------------|
| Language/Version       | [e.g., Java 21]                                 |
| Primary Dependencies   | [e.g., Spring Boot 3.x, React 18]               |
| Storage                | [e.g., PostgreSQL 16] or N/A                    |
| Testing                | [e.g., JUnit 5, Testcontainers, Playwright]     |
| Target Platform        | [e.g., Linux containers on AWS ECS, browsers]   |
| Project Type           | single / web (frontend + backend) / mobile + API|
| Performance Goals      | [From NFRs, e.g., p95 < 2s]                     |
| Constraints            | [e.g., must use company SSO, GDPR]              |
| Scale/Scope            | [e.g., 5k users, 20 screens]                    |
| Unknowns               | [NEEDS RESEARCH: item] → resolved in research.md|

---

## Constitution Check (GATE)
*Must pass before Phase 0. Re-check after Phase 1 design.*

| Principle              | Check                                  | Status          |
|------------------------|----------------------------------------|-----------------|
| I. Test-First          | Contract & integration tests precede code | Pass / Fail  |
| II. Simplicity         | ≤ 3 projects; no premature abstraction | Pass / Fail     |
| Technology Stack       | Only approved stack used               | Pass / Fail     |
| Security & Compliance  | Parameterized queries; secrets in vault| Pass / Fail     |
| Quality Gates          | Lint, coverage ≥ X%, review planned    | Pass / Fail     |

**Initial Check**: Pass / Fail
**Post-Design Check**: Pass / Fail
*Any Fail must be fixed or justified in Complexity Tracking.*

---

## Project Structure

### Documentation (this feature)
specs/[###-feature-name]/
├── plan.md
├── research.md
├── data-model.md
├── quickstart.md
├── contracts/
└── tasks.md        # Created by /speckit.tasks, NOT by plan

### Source Code (repository root)
<!-- Keep only the option that applies; delete the others -->

# Option 1: Single project
src/
├── models/
├── services/
├── cli/ or api/
└── lib/
tests/
├── contract/
├── integration/
└── unit/

# Option 2: Web application
backend/
├── src/ (models/, services/, api/)
└── tests/
frontend/
├── src/ (components/, pages/, services/)
└── tests/

# Option 3: Mobile + API
api/
└── [same as backend above]
ios/ or android/
└── [platform-specific structure]

**Structure Decision**: [Chosen option and why]

---

## Phase 0: Outline & Research → research.md
1. Extract every unknown from Technical Context.
2. Research each unknown and each key dependency's best practices.
3. Record each decision with rationale and rejected alternatives.

**Output**: research.md with zero remaining NEEDS RESEARCH items.

---

## Phase 1: Design & Contracts
*Prerequisite: research.md complete*

1. **Entities → data-model.md**: fields, validation, relationships,
   state transitions (from spec Key Entities).
2. **Requirements → contracts/**: one endpoint/operation per user
   action; OpenAPI or GraphQL schema.
3. **Contracts → contract tests**: one test file per endpoint,
   asserting request/response schemas. Tests must fail (no code yet).
4. **Stories → integration test scenarios**: one per acceptance
   scenario in spec.md.
5. **quickstart.md**: steps to validate the feature end to end.
6. **Agent context update**: add new tech to the agent file
   (e.g., CLAUDE.md, copilot-instructions.md).

**Output**: data-model.md, contracts/*, failing contract tests,
quickstart.md, updated agent context.

---

## Phase 2: Task Planning Approach
*Describes how /speckit.tasks will work. Do NOT create tasks.md here.*

**Task Generation Strategy**:
- Each contract → contract test task [P]
- Each entity → model creation task [P]
- Each user story → integration test task
- Implementation tasks to make tests pass

**Ordering Strategy**:
- TDD order: tests before implementation
- Dependency order: models → services → API → UI
- [P] marks tasks that can run in parallel (independent files)

**Estimated Output**: [~N] numbered, ordered tasks in tasks.md

---

## Requirement Traceability
| Spec Item       | Design Element                  | Test                    |
|-----------------|---------------------------------|-------------------------|
| FR-001          | [Endpoint / service / entity]   | [Contract/integration]  |
| FR-002          | [...]                           | [...]                   |
| NFR-001         | [Caching, indexing, etc.]       | [Performance test]      |
| User Story 1    | [Flow / components]             | [Integration scenario]  |

---

## Risks & Mitigations
| Risk                         | Impact    | Mitigation                    |
|------------------------------|-----------|-------------------------------|
| [Technical risk]             | H / M / L | [Approach]                    |

---

## Complexity Tracking
*Fill ONLY if the Constitution Check has violations to justify.*

| Violation                  | Why Needed                 | Simpler Alternative Rejected Because |
|----------------------------|----------------------------|--------------------------------------|
| [e.g., 4th project]        | [Current need]             | [Why 3 projects insufficient]        |

---

## Progress Tracking
**Phase Status**:
- [ ] Phase 0: Research complete
- [ ] Phase 1: Design complete
- [ ] Phase 2: Task approach described
- [ ] Phase 3: Tasks generated (/speckit.tasks)
- [ ] Phase 4: Implementation complete
- [ ] Phase 5: Validation passed

**Gate Status**:
- [ ] Initial Constitution Check: PASS
- [ ] Post-Design Constitution Check: PASS
- [ ] All NEEDS RESEARCH resolved
- [ ] Complexity deviations documented

