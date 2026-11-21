---
title: A valid client email longer than 30 characters is accepted
type: regression
platforms:
  - web
start: /en
source: breaker
status: active
tags:
  - from-and-to
  - validation
  - input-abuse
attack: input.long-valid-email
bug: BUG-003
fail_first: RUN-20261121-164009-ad6076
created: 2026-11-21T11:10:09.292Z
---

1. In the Bill To section, type 'accounts-receivable@example.test' into Email
2. Click into the Bill To Phone field

## Expect

- The Bill To Email field still reads accounts-receivable@example.test
- No error message is shown under the Bill To Email field

## Notes

Breaker's suspicion: lib/schemas.ts fieldValidators.email adds .max(30, 'Must be between 5 and 30 characters'), so ordinary business addresses are rejected. This one is 32 characters. The form uses mode 'onTouched' (contexts/Providers.tsx), so the error appears as soon as the user leaves the field.
