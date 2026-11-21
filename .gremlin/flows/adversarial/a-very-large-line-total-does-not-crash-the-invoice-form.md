---
title: A very large line total does not crash the invoice form
type: adversarial
platforms:
  - web
start: /en
source: breaker
status: confirmed
tags:
  - line-items
  - totals
  - input-abuse
attack: input.huge-line-total
bug: BUG-002
fail_first: RUN-20261121-163731-925382
created: 2026-11-21T11:07:31.057Z
---

1. Click the 'Line Items' step in the progress bar at the top of the form
2. In the first item, type 'Bulk widgets' into Name
3. Type 1000000 into Quantity
4. Type 10000000000 into Rate
5. Click the 'Summary' step in the progress bar

## Expect

- The invoice form is still on screen with the Summary step open
- A Total Amount value is shown on the Summary step
- No 'Application error' or 'client-side exception' message is shown

## Notes

Breaker's suspicion: contexts/ChargesContext.tsx calculateTotal runs in a useEffect and calls formatPriceToString (lib/helpers.ts), which passes the total to number-to-words toWords. That function throws a RangeError for anything above Number.MAX_SAFE_INTEGER (node_modules/number-to-words/src/toWords.js:42). Quantity has no upper bound in lib/schemas.ts, so 1e6 × 1e10 = 1e16 throws inside the effect. There is no error boundary under app/, so the whole page goes down. The draft is also flushed on unmount, so the bad values may come back after a reload.
