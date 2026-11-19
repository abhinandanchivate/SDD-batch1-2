[CONTEXT BLOCK]

## APPROVED ARTIFACTS (paste exact approved versions only)
[constitution.md vX]
[spec.md vX]

ROLE: You are the architect. Turn the approved spec into a technical plan
(HOW), checked against every constitution rule. Do not write code beyond
one-line function signatures and validation patterns. Do not add features
that are not in the spec.

PRODUCE:

1. File structure (RULE-1)
   - The one app file and its name.
   - Where the test file lives.
   - Exactly how the test file reaches the pure logic with no libraries
     and no build step (e.g. the logic sits in one clearly marked script
     block that the test page also loads).

2. UI elements
   Table [Element | id | Label text | type | inputmode | Why].
   Marks use type="text" + inputmode="numeric" so "85.5" and "abc" reach
   validation instead of being silently blocked by the browser.

3. Components
   Table [Function | Inputs | Returns | REQ IDs | Pure? (yes/no)].
   Normalise, validate and grade MUST be pure (no page access) so they
   can be tested without a browser.

4. Message source
   One message table in the code, keyed by MSG ID, with text copied
   exactly from the spec's message catalogue. No message text may be
   typed anywhere else in the code.

5. Validation method (exact)
   - Marks: after trimming, MUST match ^[0-9]+$, then value 0-100.
     MUST NOT use Number(), parseInt() or parseFloat() to decide
     validity (they accept "", "85.5", "1e2").
   - Name length: count Unicode code points, not .length.
   - Trimming: state exactly which whitespace characters are removed.
   - Order: name first, then marks; stop at the first failure.

6. Data flow
   Numbered steps: submit (button or Enter) -> read -> normalise ->
   validate -> grade -> clear old result -> render.

7. Result area
   Table [State (empty / success / error) | Text shown | Word or icon
   beside colour | Announced to screen readers?].
   Also state: behaviour on a fast double-click, and where keyboard
   focus goes after submit.

8. Rendering rules (RULE-5)
   textContent only; never innerHTML, insertAdjacentHTML or
   document.write with user data.

9. Error-handling strategy (RULE-3)
   - How every failure path ends in a friendly message from section 4.
   - A top-level guard so no exception escapes.
   - The guard's message text. If the spec has no MSG for it, raise
     "CHANGE REQUEST: spec.md v<n> - add MSG for unexpected error"
     and do not invent the text.

10. Accessibility plan (RULE-6), with real values
    - Labels linked to inputs; aria-live="polite" result region.
    - Focus order: table [Order | Element].
    - Colours: table [Element | Text hex | Background hex | Contrast ratio].
      Every ratio MUST be at least 4.5:1.

11. Layout plan (RULE-4), with real values
    Max width (px), body and input font sizes (px), tap target size (px),
    behaviour at 320 px, 375 px and in landscape.

12. Browser support (RULE-7)
    Table [Browser API used | Supported in every RULE-7 browser? (yes/no)].

13. Constitution compliance
    Table [Design decision | RULE | How it will be verified | Check ID].

14. Spec coverage
    Table [REQ | Plan section]. Every REQ MUST appear.

15. Build order hint for Gate 4
    Table [Plan section | Suggested TASK (expected shape) | Notes if the
    expected shape does not fit].

16. Risks, recorded exceptions and CHANGE REQUESTS.

17. OPEN QUESTIONS.

SELF-CHECK (answer each YES before replying; fix any NO):
- Every REQ appears in section 14.
- Every RULE appears in section 13 with a Check ID.
- Every size, colour and contrast value is a number, not a word.
- No message text appears outside the section 4 table.
- Nothing in the plan lacks a REQ or RULE behind it.
- The test file can run with no libraries and no build step.
- No code beyond one-line signatures and patterns.

OUTPUT: artifact header (based_on: constitution.md vX, spec.md vX),
then sections 1-17 in order.