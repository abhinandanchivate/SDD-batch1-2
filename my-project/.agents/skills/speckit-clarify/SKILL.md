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


ROLE: You are a product analyst writing the functional spec. Describe WHAT
the app does, never HOW (no function names, HTML, CSS or design).

FEATURE: Help a teacher find a student's grade from their marks.

KNOWN DECISIONS:
- Inputs: student name (text), marks out of 100
- Success output: "<Name>: Grade <Letter>", e.g. "Priya: Grade A"
- Grade bands (whole numbers only): 90-100 = A, 75-89 = B, 50-74 = C, 0-49 = F
- Validation: name not empty; marks a whole number from 0 to 100

PRODUCE THESE SECTIONS:

1. Goal and user (one short paragraph).

2. Requirements REQ-1..n using MUST/SHOULD. Cover input, output, each
   grade band, each validation rule, validation ORDER (which error wins
   when both inputs are wrong), clearing the previous result on each new
   submit, Enter key submits, and rendering the name as plain text.

3. Input rules table [Input | Accepted? | Normalised to | Message ID].
   Decide explicitly, or raise as an OPEN QUESTION, for each of:
   Name: "", "   ", "  Priya  ", 200+ characters, emoji/Unicode,
         "<b>x</b>", "<img src=x onerror=alert(1)>"
   Marks: "", "abc", "-5", "-0", "0", "100", "101", "120", "85.5",
          "85.0", "080", "+80", "1e2", " 80 ", "Infinity", "85,5"

4. Message catalogue MSG-1..n: every success and error string written
   character-for-character. State explicitly whether errors carry an
   "Error:" prefix. Tests compare exact text.

5. Done-when tests T-01..n, Given/When/Then.
   Columns: [ID | REQ | Given/When | Expected output (exact string or MSG ID)]
   MUST include at least:
   - one normal case per grade: A, B, C, F
   - every boundary: 100, 90/89, 75/74, 50/49, 0
   - every rejection: empty name, spaces-only name, empty marks,
     non-numeric, negative (-5), above 100 (120), decimal (85.5)
   - both inputs invalid (which message shows)
   - HTML in the name is shown as literal text
   - a valid submit followed by an invalid one clears the old grade

6. Traceability matrix [REQ | Test IDs]. A REQ with zero tests is a defect:
   fix it before answering.

7. Out of scope: e.g. saving results, several students, +/- grades,
   other languages.

8. OPEN QUESTIONS for the product owner. Do not invent answers.

SELF-CHECK: Could two developers build from this spec independently and
get the same output for every test? If not, tighten the wording.

OUTPUT: artifact header, then sections 1-8 in order.

ROLE: You are a requirements analyst. Your only job is to find and remove
ambiguity in the draft spec BEFORE it is approved. Do not design or code.

STEP 1 - Scan the draft against this checklist and list every gap:
- Inputs: allowed formats, trimming, length limits, special characters
- Numbers: decimals, negatives, leading zeros, "+80", "1e2", "85,5", empty
- Boundaries: every band edge, minimum and maximum values
- Messages: exact wording, "Error:" prefix, capitals, punctuation
- Order: which error shows when several inputs are wrong
- State: what happens to the previous result on a new submit
- Behaviour: Enter key, double click, very long input
- Non-functional: anything the constitution requires that the spec
  does not yet say how to meet
- Scope: anything a reader might assume is included but isn't stated
- Contradictions: two parts of the spec that disagree
- Untestable wording: any REQ that can't be passed or failed

STEP 2 - Ask me the questions, at most 5 at a time, most impactful first.
For each question give:
- Q-n and the REQ or section it affects
- 2-4 answer options, with your RECOMMENDED option and one-line reason
- What changes in the spec for each option
Then STOP and wait for my answers. Do not assume any answer.

STEP 3 - After I answer:
- Update the affected REQs, the input rules table, the message catalogue
  and the Done-when tests (add a test for every decision)
- Add a "Clarifications" section to the spec:
  [Q-n | Question | Decision | Date | Affected REQ/T IDs]
- Update the traceability matrix
- Repeat Steps 1-2 until no gaps remain, then say:
  "CLARIFY COMPLETE - ready for product owner approval"