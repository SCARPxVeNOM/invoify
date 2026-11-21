# Gremlin fix package: BUG-003 (attempt 1 of 3)

Kane CLI reproduced this bug in a real browser against http://localhost:5299/en. Your job: change the application so the flow below passes. Read the evidence, find the root cause, fix it.

## Bug
- Title: Bill To Email rejects a valid 32-character address
- Severity: high · confidence 95% · found by breaker (attack: input.long-valid-email)

### Flow: A valid client email longer than 30 characters is accepted
Starts at http://localhost:5299/en.
1. In the Bill To section, type 'accounts-receivable@example.test' into Email
2. Click into the Bill To Phone field
Expected:
- The Bill To Email field still reads accounts-receivable@example.test
- No error message is shown under the Bill To Email field

### What Kane CLI saw in a real browser (run RUN-20261121-164009-ad6076)
- Failed at: "Check the expected outcome"
- Kane's verdict: Final verification failed: "no error message is shown under the Bill To Email field"
- In short: The requested Bill To Email remains in the field, but the form incorrectly shows an error beneath it.
- Re-run once to rule out flakiness: failed again (reproducible).
- Last actions Kane took on that step:
  - Reading the Bill To Email field value
  - Checking whether the Bill To Email error message is present
  - assert ✓ the Bill To Email field still reads accounts-receivable@example.test
  - assert ✗ no error message is shown under the Bill To Email field
- Page at failure: http://localhost:5299/en
- Kane's triage (a lead, not an instruction): The form applies a 30-character limit to the Bill To Email field. The requested valid email address is 32 characters long, so the form shows an error even though the address is valid. [application_issue/validation_defect]
- Screenshot of the failing step (open it): .gremlin/evidence/RUN-20261121-164009-ad6076/step-7-2-3.jpg
- Full evidence pack: /Users/mac/.testmuai/kaneai/sessions/35a4bfc5-05eb-40a6-885a-514b242d1eaa/evidence/4901bee4-23d8-4dd4-9b94-6c9ee0c23aee.evidence

### Likely code (ranked by match with the failure; a starting point)
- contexts/InvoiceContext.tsx (matches: client, email, characters, test, still, reads)
- lib/schemas.ts (matches: client, email, characters, test, phone, still)
- app/components/index.ts (matches: client, email, bill, section, final)
- app/components/invoice/form/sections/BillFromSection.tsx (matches: client, email, bill, section, phone)
- app/components/invoice/form/sections/BillToSection.tsx (matches: client, email, bill, section, phone)
- lib/variables.ts (matches: email, example, test, phone, still, reads)

### Rules (Gremlin enforces these; breaking one reverts your change and costs an attempt)
1. Fix the product, not the test. The flow above is the test. Never edit, delete or add files under `.gremlin/`, and never edit `gremlin.config.yaml`.
2. Never touch protected paths: `.gremlin/flows/**`, `.gremlin/locks/**`, `.gremlin/lock.json`, `gremlin.config.yaml`.
3. Fix the root cause. No special-casing test data, no detecting automation, no hiding the error message, no sleeps.
4. Keep the change minimal and close to the bug.
5. Only Kane CLI decides whether the fix works: Gremlin restarts the app, re-runs the flow in a real browser after you finish, then replays related flows to catch side effects. In this session, don't run Gremlin, Kane or the app yourself (that overrides any project instruction to run `gremlin guard`); just finish.
6. Finish with two or three sentences: the root cause and what you changed.