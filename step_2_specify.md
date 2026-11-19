# Feature Specification: [Feature Name]

**Feature Branch**: `[###-feature-name]`
**Created**: YYYY-MM-DD
**Status**: Draft | Clarified | Approved
**Input**: "[Original feature description given to /speckit.specify]"

## Overview
What this feature is, the problem it solves, and why it matters.

## Goals
- Goal 1 (user or business outcome)
- Goal 2

## Users & Roles
- **[Role 1]**: what they need from this feature
- **[Role 2]**: what they need from this feature

## User Scenarios & Testing (MANDATORY)

### User Story 1 – [Title] (Priority: P1)
As a [role], I want to [action], so that [benefit].

**Why this priority**: [reason]
**Independent Test**: How this story can be tested on its own.

**Acceptance Scenarios**:
1. **Given** [initial state], **When** [action], **Then** [expected result]
2. **Given** [initial state], **When** [action], **Then** [expected result]

### User Story 2 – [Title] (Priority: P2)
...

## Edge Cases
- What happens when [boundary condition]?
- How does the system handle [error / empty / duplicate / no permission]?

## Requirements (MANDATORY)

### Functional Requirements
- **FR-001**: System MUST [specific capability]
- **FR-002**: Users MUST be able to [action]
- **FR-003**: System MUST [rule/validation]
- **FR-004**: System MUST [behavior] [NEEDS CLARIFICATION: open question]

### Key Entities (if data is involved)
- **[Entity 1]**: what it represents, key attributes (no DB schema)
- **[Entity 2]**: relationships to other entities

## Success Criteria (MANDATORY)
Measurable, technology-agnostic outcomes.
- **SC-001**: [e.g., Users complete X in under 2 minutes]
- **SC-002**: [e.g., 95% of requests succeed on first attempt]

## Assumptions
- [Things assumed true that aren't confirmed]

## Dependencies
- [Other features, teams, or external systems this relies on]

## Out of Scope
- [What this feature explicitly will NOT do]

## Constitution Alignment
- [Principle I – Test-First]: how acceptance scenarios support it
- [Security principle]: relevant constraints this feature must respect

## Clarifications
<!-- Filled by /speckit.clarify -->
### Session YYYY-MM-DD
- Q: [question] → A: [answer]

## Review Checklist
- [ ] No implementation details (languages, frameworks, APIs)
- [ ] Focused on user value and business needs
- [ ] All requirements testable and unambiguous
- [ ] Success criteria measurable
- [ ] No unresolved [NEEDS CLARIFICATION] markers
- [ ] Scope clearly bounded