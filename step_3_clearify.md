# Feature Specification: [Feature Name]

**Feature Branch**: `[###-feature-name]`
**Created**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
**Status**: Clarified
**Input**: "[Original feature description given to /speckit.specify]"
**Constitution Version**: [e.g., 1.0.0]

---

## Overview
What this feature is, the problem it solves, and why it matters.

## Goals
- **G-1**: [User or business outcome]
- **G-2**: [User or business outcome]

## Users & Roles
| Role       | Description              | Key Needs                 |
|------------|--------------------------|---------------------------|
| [Role 1]   | [Who they are]           | [What they need]          |
| [Role 2]   | [Who they are]           | [What they need]          |

## Glossary
<!-- Clarified: terms defined during clarify to remove ambiguity -->
| Term       | Definition                                     |
|------------|------------------------------------------------|
| [Term 1]   | [Single agreed meaning used throughout spec]   |
| [Term 2]   | [Single agreed meaning]                        |

---

## Clarifications

### Session YYYY-MM-DD
- Q1 [Category]: [Question] → A: [Answer]
- Q2 [Category]: [Question] → A: [Answer]
- Q3 [Category]: [Question] → A: [Answer]
- Q4 [Category]: [Question] → A: [Answer]
- Q5 [Category]: [Question] → A: [Answer]

### Session YYYY-MM-DD (if re-run)
- Q1 [Category]: [Question] → A: [Answer]

---

## User Scenarios & Testing (MANDATORY)

### User Story 1 – [Title] (Priority: P1)
As a [role], I want to [action], so that [benefit].

**Why this priority**: [Reason this is MVP-critical]
**Independent Test**: [How this story is verified on its own]

**Acceptance Scenarios**:
1. **Given** [state], **When** [action], **Then** [result]
2. **Given** [state], **When** [action], **Then** [result]
3. **Given** [state], **When** [action], **Then** [result]
   <!-- Clarified: Q1 -->

### User Story 2 – [Title] (Priority: P2)
As a [role], I want to [action], so that [benefit].

**Why this priority**: [Reason]
**Independent Test**: [How verified]

**Acceptance Scenarios**:
1. **Given** [state], **When** [action], **Then** [result]
2. **Given** [state], **When** [action], **Then** [result]

### User Story 3 – [Title] (Priority: P3)
...

---

## User Flow
<!-- Clarified: missing steps and states resolved -->
1. [Entry point]
2. [Step]
3. [Decision point] → [Path A] / [Path B]
4. [Completion state]

**UI States**:
- **Empty**: [What the user sees with no data]
- **Loading**: [Behavior while waiting]
- **Error**: [What the user sees and can do]
- **Success**: [Confirmation shown]

---

## Edge Cases
| ID    | Scenario                                 | Expected Behavior                  |
|-------|------------------------------------------|------------------------------------|
| EC-01 | [Boundary condition]                     | [Defined behavior]                 |
| EC-02 | [Duplicate / conflicting input]          | [Defined behavior]                 |
| EC-03 | [Unauthorized action]                    | [Defined behavior]                 |
| EC-04 | [Concurrent update]                      | [Defined behavior] <!-- Q2 -->     |
| EC-05 | [External dependency unavailable]        | [Defined behavior] <!-- Q4 -->     |

---

## Requirements (MANDATORY)

### Functional Requirements
- **FR-001**: System MUST [capability]
- **FR-002**: Users MUST be able to [action]
- **FR-003**: System MUST [validation/business rule]
- **FR-004**: System MUST [behavior resolved in clarify] <!-- Clarified: Q1 -->
- **FR-005**: System MUST [behavior] <!-- Clarified: Q3 -->
- **FR-006**: System MUST NOT [explicitly prohibited behavior]

### Non-Functional Requirements
<!-- Clarified: measurable targets replace vague wording -->
- **NFR-001 (Performance)**: [e.g., Results shown within 2 seconds for 95% of requests]
- **NFR-002 (Scale)**: [e.g., Supports up to N concurrent users]
- **NFR-003 (Availability)**: [e.g., 99.5% during business hours]
- **NFR-004 (Accessibility)**: [e.g., WCAG 2.1 AA]
- **NFR-005 (Security/Privacy)**: [e.g., Only owners and managers can view records]
- **NFR-006 (Auditability)**: [e.g., All status changes recorded with who and when]

### Key Entities
<!-- Clarified: attributes, relationships, and lifecycle confirmed -->
- **[Entity 1]**: [What it represents]
  - Key attributes: [attr], [attr], [attr]
  - Uniqueness: [What must be unique]
  - Lifecycle states: [State A] → [State B] → [State C]
- **[Entity 2]**: [What it represents]
  - Relationship: [One Entity 1 has many Entity 2]

### Business Rules
- **BR-001**: [Rule, e.g., limits, quotas, eligibility]
- **BR-002**: [Rule] <!-- Clarified: Q5 -->

---

## Integrations & Dependencies
| Dependency          | Purpose                  | Failure Behavior                 |
|---------------------|--------------------------|----------------------------------|
| [System/Feature A]  | [Why needed]             | [What happens if unavailable]    |
| [Team/Service B]    | [Why needed]             | [Fallback]                       |

---

## Success Criteria (MANDATORY)
- **SC-001**: [Measurable, technology-agnostic outcome]
- **SC-002**: [Measurable outcome]
- **SC-003**: [Measurable outcome]

## Assumptions
- **A-1**: [Assumption confirmed or accepted during clarify]
- **A-2**: [Assumption]

## Constraints
- [Regulatory, business, or timeline constraint]

## Out of Scope
- [Explicitly excluded capability]
- [Deferred to a future feature] <!-- Clarified: Q3 -->

## Risks
| Risk                          | Impact   | Mitigation                    |
|-------------------------------|----------|-------------------------------|
| [Risk description]            | H / M / L| [How addressed]               |

---

## Constitution Alignment
| Principle                 | How This Spec Complies                          |
|---------------------------|-------------------------------------------------|
| I. Test-First             | Every story has testable acceptance scenarios   |
| II. Simplicity            | [No unnecessary features/scope]                 |
| Security & Compliance     | [Relevant NFRs and rules above]                 |
| Quality Gates             | [Criteria are measurable and verifiable]        |

---

## Clarification Coverage Summary
| Category              | Status      | Notes                         |
|-----------------------|-------------|-------------------------------|
| Functional Scope      | Resolved    | [Q1, Q3]                      |
| Data & Entities       | Resolved    | [Q2]                          |
| User Flow             | Clear       | No questions needed           |
| Non-Functional        | Resolved    | [Q4]                          |
| Integrations          | Resolved    | [Q4]                          |
| Edge Cases            | Resolved    | [Q2]                          |
| Constraints           | Clear       |                               |
| Terminology           | Resolved    | [Glossary added]              |
| Completion Signals    | Clear       |                               |
| Deferred              | [Item]      | [Why low impact; revisit in plan] |

---

## Review Checklist
- [ ] No implementation details (languages, frameworks, APIs, schemas)
- [ ] Focused on user value and business needs
- [ ] All requirements testable and unambiguous
- [ ] Success criteria and NFRs measurable
- [ ] Zero unresolved [NEEDS CLARIFICATION] markers
- [ ] Every clarification answer reflected in a section, not just the log
- [ ] Scope clearly bounded (Out of Scope filled)
- [ ] Aligned with constitution [version]

