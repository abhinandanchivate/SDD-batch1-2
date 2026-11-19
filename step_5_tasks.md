# Tasks: [Feature Name]

**Branch**: `[###-feature-name]`
**Input**: specs/[###-feature-name]/ (plan.md, spec.md, data-model.md,
contracts/, research.md, quickstart.md)
**Prerequisites**: plan.md (required), spec.md (required)

---

## Format: `[ID] [P?] [Story] Description`
- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: User story this task belongs to (US1, US2, US3)
- Every task includes an exact file path

## Path Conventions
- Single project: `src/`, `tests/`
- Web app: `backend/src/`, `frontend/src/`
- Mobile: `api/src/`, `ios/src/` or `android/src/`
*(Use the structure chosen in plan.md)*

---

## Phase 1: Setup (Shared Infrastructure)
**Purpose**: Project initialization and basic structure

- [ ] T001 Create project structure per plan.md
- [ ] T002 Initialize [language] project with [framework] dependencies
- [ ] T003 [P] Configure linting and formatting tools
- [ ] T004 [P] Configure test framework and coverage reporting

---

## Phase 2: Foundational (Blocking Prerequisites)
**Purpose**: Core infrastructure that MUST exist before any user story

⚠️ **CRITICAL**: No user story work begins until this phase is complete

- [ ] T005 Set up database schema and migrations framework in [path]
- [ ] T006 [P] Implement authentication/authorization in [path]
- [ ] T007 [P] Set up API routing and middleware in [path]
- [ ] T008 Create base entities shared by all stories in [path]
- [ ] T009 Configure error handling and logging in [path]
- [ ] T010 Configure environment/secrets management in [path]

**Checkpoint**: Foundation ready — user stories can begin (in parallel if staffed)

---

## Phase 3: User Story 1 – [Title] (Priority: P1) 🎯 MVP
**Goal**: [What this story delivers]
**Independent Test**: [How to verify this story alone]

### Tests for User Story 1 (write FIRST, ensure they FAIL)
- [ ] T011 [P] [US1] Contract test for [endpoint] in tests/contract/test_[name].[ext]
- [ ] T012 [P] [US1] Integration test for [scenario] in tests/integration/test_[name].[ext]

### Implementation for User Story 1
- [ ] T013 [P] [US1] Create [Entity1] model in src/models/[entity1].[ext]
- [ ] T014 [P] [US1] Create [Entity2] model in src/models/[entity2].[ext]
- [ ] T015 [US1] Implement [Service] in src/services/[service].[ext] (depends on T013, T014)
- [ ] T016 [US1] Implement [endpoint] in src/api/[file].[ext]
- [ ] T017 [US1] Add validation and error handling (FR-00X, EC-0X)
- [ ] T018 [US1] Build [UI screen/component] in [path]

**Checkpoint**: User Story 1 fully functional and independently testable

---

## Phase 4: User Story 2 – [Title] (Priority: P2)
**Goal**: [What this story delivers]
**Independent Test**: [How to verify this story alone]

### Tests for User Story 2 (write FIRST, ensure they FAIL)
- [ ] T019 [P] [US2] Contract test for [endpoint] in [path]
- [ ] T020 [P] [US2] Integration test for [scenario] in [path]

### Implementation for User Story 2
- [ ] T021 [P] [US2] Create [Entity] model in [path]
- [ ] T022 [US2] Implement [Service] in [path]
- [ ] T023 [US2] Implement [endpoint/feature] in [path]
- [ ] T024 [US2] Integrate with User Story 1 components (if needed)

**Checkpoint**: User Stories 1 and 2 both work independently

---

## Phase 5: User Story 3 – [Title] (Priority: P3)
*(Same pattern: tests first, then implementation, then checkpoint)*

---

## Phase N: Polish & Cross-Cutting Concerns
**Purpose**: Improvements affecting multiple stories

- [ ] TXXX [P] Unit tests for edge cases in tests/unit/
- [ ] TXXX [P] Performance validation against NFR-001
- [ ] TXXX [P] Accessibility check against NFR-004
- [ ] TXXX Security hardening and review (constitution Security section)
- [ ] TXXX [P] Documentation updates in docs/
- [ ] TXXX Code cleanup and refactoring
- [ ] TXXX Run quickstart.md validation end to end

---

## Dependencies & Execution Order

### Phase Dependencies
- **Setup (Phase 1)**: No dependencies — start immediately
- **Foundational (Phase 2)**: Depends on Setup — BLOCKS all user stories
- **User Stories (Phase 3+)**: Depend on Foundational
  - Can proceed in parallel (if staffed) or sequentially by priority
- **Polish (Final)**: Depends on all desired stories being complete

### Within Each User Story
- Tests MUST be written and FAIL before implementation
- Models → Services → Endpoints → UI
- Story complete before moving to next priority

### Parallel Opportunities
- All [P] tasks in the same phase can run together
- Different user stories can be worked on by different people
  once Foundational is done

---

## Parallel Example: User Story 1
Launch together:
- T011 Contract test for [endpoint]
- T012 Integration test for [scenario]

Then together:
- T013 Create [Entity1] model
- T014 Create [Entity2] model

---

## Implementation Strategy

### MVP First (User Story 1 Only)
1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational
3. Complete Phase 3: User Story 1
4. **STOP and VALIDATE**: Test US1 independently
5. Deploy/demo if ready

### Incremental Delivery
Setup + Foundational → US1 (MVP) → US2 → US3 → Polish
Each story adds value without breaking previous ones.

### Parallel Team Strategy
After Foundational: Dev A → US1, Dev B → US2, Dev C → US3

---

## Requirement Coverage
| Spec Item     | Tasks                 |
|---------------|-----------------------|
| FR-001        | T011, T015, T016      |
| FR-002        | T019, T022            |
| NFR-001       | TXXX (performance)    |
| EC-01         | T017                  |

---

## Notes
- [P] = different files, no dependencies
- [Story] label maps each task to a user story for traceability
- Commit after each task or logical group
- Stop at any checkpoint to validate the story independently
- Avoid: vague tasks, two [P] tasks editing the same file,
  cross-story dependencies that break independence

**Next step**: /speckit.analyze (recommended) → /speckit.implement