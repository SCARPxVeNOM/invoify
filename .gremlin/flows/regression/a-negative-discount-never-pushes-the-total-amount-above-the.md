---
title: A negative discount never pushes the Total Amount above the Subtotal
type: regression
platforms:
  - web
start: /en
source: capture:file:/private/tmp/claude-501/-Users-mac-Desktop-gremlin/a77b8aec-ddeb-4487-b031-716fb14fcc03/scratchpad/neg-discount.txt
status: active
tags:
  - summary
  - charges
  - discount
bug: BUG-004
fail_first: RUN-20261121-170218-dcbf0b
created: 2026-11-21T11:27:13.628Z
---

1. Click the 'Line Items' step in the progress bar
2. Type 'Test service' in the item Name box
3. Type 2 in the Quantity box
4. Type 100 in the Rate box
5. Click the 'Summary' step in the progress bar
6. Click '+ Discount'
7. Clear the Discount box and type -50
8. Scroll back up the page, above the 'Frequently asked questions' section, until the Summary form's 'Subtotal' and 'Total Amount' rows are both on screen, and stop there

## Expect

- In the Summary form, the Subtotal row shows 200.00 USD
- In the Summary form, the Total Amount row shows 200.00 USD or less, and does not show 250.00 USD

## Notes

Captured from file:/private/tmp/claude-501/-Users-mac-Desktop-gremlin/a77b8aec-ddeb-4487-b031-716fb14fcc03/scratchpad/neg-discount.txt:
> On the invoice form, I added a line item with quantity 2 and rate 100, so the subtotal is 200.00 USD.
> Then on the Summary step I turned on Discount and typed -50 as the discount amount.
> The total went UP to 250.00 USD. A discount should never make the invoice more expensive: a negative discount should be rejected, or at least the total should not exceed the subtotal.
>
Revised after Kane's triage of RUN-20261121-165714-8694fc: Added a last step that scrolls back to the Summary form's Subtotal and Total Amount rows and stops there, and tied both expectations to those rows, because the FAQ section that sits below the invoice builder on the home page (app/[locale]/page.tsx:42) was what filled the screen at the final check.
Claude Code disputes Kane's triage: Kane called this a flow problem, but the code shows the product really has the bug, so the revised flow should still fail once the totals are on screen. contexts/ChargesContext.tsx:189-191 does `total -= discountAmount` with no check on the sign, so a discount of -50 turns a 200 subtotal into 250. lib/schemas.ts:89 and :140 check the discount amount with `z.coerce.number().max(1000000)`, which has no minimum. The `min="0"` at app/components/reusables/form-fields/ChargeInput.tsx:75 is only a browser hint and doesn't stop the live total from going up. With the totals visible, Total Amount will show 250.00 USD and the flow will fail. That is a real product bug, not a fault in the flow.
