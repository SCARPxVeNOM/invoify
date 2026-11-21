---
title: Percentage tax stays a percentage after clearing and retyping it
type: adversarial
platforms:
  - web
start: /en
source: breaker
status: active
tags:
  - summary
  - charges
  - state
attack: state.percentage-type-reset-on-empty
created: 2026-11-21T10:56:35.791Z
---

1. Click the 'Line Items' step in the progress bar
2. Type 'Design work' in the item Name box
3. Type 2 in the Quantity box
4. Type 100 in the Rate box
5. Click the 'Summary' step in the progress bar
6. Click '+ Tax'
7. Click the circular-arrows button next to the Tax box (Switch between percentage and fixed amount) so a % sign appears beside it
8. Clear the Tax box completely so it is empty
9. Type 10 in the Tax box

## Expect

- A % sign, not USD, is shown next to the Tax box
- Subtotal shows 200.00 USD
- Total Amount shows 220.00 USD

## Notes

Breaker's suspicion: In contexts/ChargesContext.tsx, when the box is empty parseFloat('') is NaN, so calculateTotal skips the tax block but still writes taxDetails.amountType = 'amount' (its local default). On the next keystroke the type-sync effect reads that 'amount' back and calls setTaxType('amount'). That silently turns 10% into 10 USD.
