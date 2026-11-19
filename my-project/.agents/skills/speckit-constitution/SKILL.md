## PROJECT CONTEXT
Project: Student Grade Calculator
Method: Spec-Driven Development (SDD), 9 gates, each approved by a named human.

NON-NEGOTIABLE RULES FOR YOU (the AI):
1. Nothing moves to the next gate until the current gate is approved.
2. If information is missing or ambiguous, DO NOT assume. Put it under
   "OPEN QUESTIONS" and do not complete that item.
3. Never invent facts, test results, screenshots or approvals. If you did not
   receive real evidence, write "NOT PROVIDED".
4. Do not change an approved artifact. If you think one is wrong, raise it as
   a "CHANGE REQUEST: <artifact> v<n> - <reason>".
5. Stay inside this gate. Do not do work that belongs to a later gate.

CONVENTIONS:
- IDs: RULE-n (constitution), REQ-n (requirements), MSG-n (messages),
  T-nn (spec tests), C-nn (constitution checks), TASK-n (tasks),
  F-nn (review findings)
- Requirement language: MUST / MUST NOT / SHOULD / MAY (RFC 2119)
- Tests: Given / When / Then, with exact expected strings
- Every output in Markdown, with the artifact header below
- No code unless the gate asks for code

## APPROVED ARTIFACTS (paste exact approved versions only)
[constitution.md vX]
[spec.md vX]
[plan.md vX]
[tasks.md vX]

ROLE: You are a senior software architect drafting the project constitution:
the permanent rules every feature must follow, now and later.

STARTING RULES (refine wording, do not drop any):
RULE-1 Single HTML file with inline CSS and JS; no external libraries, CDNs,
       fonts or network calls. Test files may live separately.
RULE-2 Every feature has a spec with Done-when tests written BEFORE code.
RULE-3 Friendly errors; the app never crashes.
RULE-4 Works on mobile screens.
RULE-5 User input is always rendered as text, never as HTML.
RULE-6 Accessible: labelled inputs, keyboard use, screen-reader results,
       meaning never carried by colour alone.
RULE-7 Supported browsers: [e.g. latest Chrome on Android, latest Safari
       on iOS, latest Chrome/Edge/Firefox on desktop].

FOR EACH RULE produce:
- ID, rule statement using MUST / MUST NOT
- Rationale (one sentence)
- Measurable criteria. Replace vague words. For example:
  "friendly" = plain language, says what is wrong AND how to fix it,
               never shows NaN, undefined, null or a stack trace
  "never crashes" = zero uncaught errors in the console for any input
  "mobile" = usable at 375 px and 320 px, no horizontal scroll,
             tap targets at least 44 x 44 px, text at least 16 px
  "accessible" = every input has a <label>, Enter submits, result area
             is announced (aria-live), contrast at least 4.5:1 (WCAG 2.1 AA)
  "as text" = output uses textContent, never innerHTML with user data
- Verification method: exact steps a reviewer follows
- Gate where it is verified, with a check ID (C-01, C-02, ...)

ALSO PRODUCE:
- Exceptions process: who may waive a rule, how it is recorded, expiry
- Scope note: what belongs in a spec, not in the constitution

SELF-CHECK before answering: can each rule be passed or failed with a
yes/no answer by someone who did not write it? If not, rewrite it.

OUTPUT: artifact header, then table
[ID | Rule | Rationale | Measurable criteria | Verification | Gate | Check ID],
then Exceptions process, Scope note, OPEN QUESTIONS.