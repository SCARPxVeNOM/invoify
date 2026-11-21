---
title: A sender name of only spaces is rejected
type: adversarial
platforms:
  - web
start: /en
source: breaker
status: draft
tags:
  - from-and-to
  - validation
  - input-abuse
attack: input.whitespace-only-name
created: 2026-11-21T11:12:29.306Z
---

1. In the Bill From section, click into the Name field and press the space bar three times, so the field holds only three spaces and nothing else
2. Press Tab to leave the Name field and move to the Bill From Address field
3. Type 1 Test Street into the Bill From Address field

## Expect

- An error message is shown directly under the Bill From Name field saying the name is required or too short (for example "Must be at least 2 characters"), even though the Name field looks blank

## Notes

Breaker's suspicion: lib/schemas.ts fieldValidators.name is z.string().min(2) with no trim, so '   ' passes validation and an invoice with a blank sender can be generated. WizardProgress.tsx does trim when deciding whether a step is filled, so the step shows as incomplete while no error is shown.

Revised after Kane's triage of RUN-20261121-164229-aaa08f: rewrote the steps so Kane can check them
