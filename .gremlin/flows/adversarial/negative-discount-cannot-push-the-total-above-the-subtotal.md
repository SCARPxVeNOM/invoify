---
title: Negative discount cannot push the total above the subtotal
type: adversarial
platforms:
  - web
start: /en
source: breaker
status: draft
tags:
  - summary
  - charges
  - input-abuse
attack: input.negative-discount
created: 2026-11-21T10:59:49.248Z
---

1. Click the 'Line Items' step in the progress bar
2. Type 'Consulting' in the item Name box
3. Type 2 in the Quantity box
4. Type 100 in the Rate box
5. Click the 'Summary' step in the progress bar
6. Click '+ Discount'
7. Clear the Discount box and type -50

## Expect

- Subtotal shows 200.00 USD
- Total Amount is not higher than 200.00 USD

## Notes

Breaker's suspicion: lib/schemas.ts validates discountDetails.amount with stringToNumberWithMax (z.coerce.number().max(1000000)), which has no minimum. contexts/ChargesContext.tsx does total -= discountAmount, so -50 adds 50. The min="0" on the input in ChargeInput.tsx is only a browser hint and does not stop the live total or the server-side schema.
