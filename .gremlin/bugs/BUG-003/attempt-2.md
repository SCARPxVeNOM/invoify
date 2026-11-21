# Gremlin fix package: BUG-003 (attempt 2 of 3)

Kane CLI reproduced this bug in a real browser against http://localhost:5299/en. Your job: change the application so the flow below passes. Read the evidence, find the root cause, fix it.

## Bug
- Title: Bill To Email rejects a valid 32-character address
- Severity: high · confidence 95% · found by breaker (attack: input.long-valid-email)

### Flow: Very large line item total does not crash the invoice form
Starts at http://localhost:5299/en.
1. Click the 'Line Items' step in the progress bar
2. Type 'Server rack lease' in the item Name box
3. Type 1000000000 in the Rate box
4. Type 10000000 in the Quantity box
5. Wait two seconds
Expected:
- The Line Items form is still on screen with the Name, Quantity and Rate boxes visible
- No 'Application error' or 'client-side exception' message is shown
- The item's Total shows 10000000000000000.00 USD

### What Kane CLI saw in a real browser (run RUN-20261122-002231-c99586)
- Failed at: "Check the expected outcome"
- Kane's verdict: Checkpoint assertion failed: "the Line Items form is still on screen with the Name, Quantity and Rate boxes visible"
- In short: The Line Items page crashes instead of keeping the form visible when the total reaches 10000000000000000.00 USD.
- Re-run once to rule out flakiness: failed again (reproducible).
- Last actions Kane took on that step:
  - Checking whether the Quantity box is present
  - Checking whether the Rate box is present
  - Checking whether the Application error message is present
  - Checking whether the client-side exception message is present
  - Reading the item total from the Line Items form
  - assert ✗ the Line Items form is still on screen with the Name, Quantity and Rate boxes visible
- Page at failure: http://localhost:5299/en?step=items
- Kane's triage (a lead, not an instruction): The page tries to format the very large total as a number it cannot safely handle, then shows a runtime error instead of the Line Items form. [application_issue/script_error]
- Browser console errors:
  - Input is not a safe number, it’s either too large or too small.
- Screenshot of the failing step (open it): .gremlin/evidence/RUN-20261122-002231-c99586/step-12-5-2.jpg
- Full evidence pack: /Users/mac/.testmuai/kaneai/sessions/2621e918-817d-4d69-a379-afdf16ee929e/evidence/bcba9343-0fec-4c16-94ec-192dcca4aa86.evidence

### Previous attempts (they did not pass Kane; try something different)
- Attempt 1: changed lib/schemas.ts → failed. Agent said: I've made the fix. The only other places that mention the old message are Gremlin's own files, which I haven't touched. The root cause was the shared `email` validator in `lib/schemas.ts:47`. It capped addresses at 30 characters with `.max(30)`, so a valid 32-character address like `accounts-receiva

### Likely code (ranked by match with the failure; a starting point)
- app/components/invoice/form/TemplateGallery.tsx (matches: very, large, line, item, invoice, items)
- app/components/templates/invoice-pdf/parts/index.tsx (matches: very, line, item, total, invoice, items)
- app/components/invoice/form/SingleItem.tsx (matches: line, item, total, invoice, items, step)
- app/components/invoice/form/VoiceInput.tsx (matches: line, item, invoice, items, step, name)
- app/components/invoice/form/wizard/WizardProgress.tsx (matches: very, line, item, invoice, items, step)
- contexts/InvoiceContext.tsx (matches: very, large, item, does, invoice, server)

### Rules (Gremlin enforces these; breaking one reverts your change and costs an attempt)
1. Fix the product, not the test. The flow above is the test. Never edit, delete or add files under `.gremlin/`, and never edit `gremlin.config.yaml`.
2. Never touch protected paths: `.gremlin/flows/**`, `.gremlin/locks/**`, `.gremlin/lock.json`, `gremlin.config.yaml`.
3. Fix the root cause. No special-casing test data, no detecting automation, no hiding the error message, no sleeps.
4. Keep the change minimal and close to the bug.
5. Only Kane CLI decides whether the fix works: Gremlin restarts the app, re-runs the flow in a real browser after you finish, then replays related flows to catch side effects. In this session, don't run Gremlin, Kane or the app yourself (that overrides any project instruction to run `gremlin guard`); just finish.
6. Finish with two or three sentences: the root cause and what you changed.