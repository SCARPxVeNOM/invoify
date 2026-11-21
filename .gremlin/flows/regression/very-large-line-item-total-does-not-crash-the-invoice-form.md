---
title: Very large line item total does not crash the invoice form
type: regression
platforms:
  - web
start: /en
source: breaker
status: active
tags:
  - line-items
  - input-abuse
attack: input.huge-number-total-in-words
bug: BUG-001
fail_first: RUN-20261121-162325-b889e8
created: 2026-11-21T10:53:25.270Z
---

1. Click the 'Line Items' step in the progress bar
2. Type 'Server rack lease' in the item Name box
3. Type 1000000000 in the Rate box
4. Type 10000000 in the Quantity box
5. Wait two seconds

## Expect

- The Line Items form is still on screen with the Name, Quantity and Rate boxes visible
- No 'Application error' or 'client-side exception' message is shown
- The item's Total shows 10000000000000000.00 USD

## Notes

Breaker's suspicion: contexts/ChargesContext.tsx calculateTotal always calls formatPriceToString (lib/helpers.ts), which passes the total to number-to-words toWords(). That throws a RangeError for any value above Number.MAX_SAFE_INTEGER. lib/schemas.ts caps unitPrice but not quantity, and there is no error.tsx boundary, so a throw inside this useEffect unmounts the whole app.
