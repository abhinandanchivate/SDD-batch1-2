# Implementation Report: [Feature Name]

**Branch**: `[###-feature-name]`
**Date**: YYYY-MM-DD
**Constitution Version**: [X.Y.Z]

## Summary
[2–3 sentences: what was built, which stories delivered]

## Task Completion
| Phase                   | Tasks      | Completed | Status |
|-------------------------|------------|-----------|--------|
| 1. Setup                | T001–T004  | 4/4       | ✅     |
| 2. Foundational         | T005–T010  | 6/6       | ✅     |
| 3. US1 (P1) MVP         | T011–T018  | 8/8       | ✅     |
| 4. US2 (P2)             | T019–T024  | 6/6       | ✅     |
| N. Polish               | TXXX–TXXX  | N/N       | ✅     |

## Test Results
| Suite        | Passed | Failed | Skipped |
|--------------|--------|--------|---------|
| Contract     | [N]    | 0      | 0       |
| Integration  | [N]    | 0      | 0       |
| Unit         | [N]    | 0      | 0       |
| **Coverage** | [N]% (constitution target: ≥ X%)        |

## Requirement Verification
| Spec Item   | Verified By            | Result |
|-------------|------------------------|--------|
| FR-001      | T011, T016             | ✅     |
| NFR-001     | Performance test T030  | ✅ p95 = [N]ms |
| SC-001      | Quickstart scenario 1  | ✅     |

## Constitution Quality Gates
| Gate                   | Result |
|------------------------|--------|
| Lint                   | ✅     |
| Tests passing          | ✅     |
| Coverage ≥ X%          | ✅     |
| Security checks        | ✅     |
| Code review            | ⏳ Pending human review |

## Deviations from Plan
| Item                    | Change                    | Reason                        |
|-------------------------|---------------------------|-------------------------------|
| [Component]             | [What differed]           | [Why; spec/plan updated?]     |

## Known Issues / Follow-ups
- [Issue or deferred item]

## Next Steps
- Open PR linked to spec.md and tasks.md
- Human code review per constitution
- Merge after review approval