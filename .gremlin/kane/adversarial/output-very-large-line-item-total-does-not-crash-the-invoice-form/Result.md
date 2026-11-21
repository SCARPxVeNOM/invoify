---
test: ../very-large-line-item-total-does-not-crash-the-invoice-form_test.md
status: passed
started: 2026-11-21T18:49:37.960Z
duration_s: 46
session_id: 09269181-f8b2-4b13-a7ed-a29068da9229
---

# Very large line item total does not crash the invoice form — Result

## Step 1: Click the 'Line Items' step in the progress bar ✓ passed (7.42s)
md5: 1427442882b95a0877465b5378545093
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Server rack lease' in the item Name box ✓ passed (0.27s)
md5: 820b939da53864f95bc244a1a52a4a06
Type 'Server rack lease' in the item Name box.

## Step 3: Type 1000000000 in the Rate box ✓ passed (0.43s)
md5: dbdfe9100c2eff5b7b4c2f0d7c45e707
Type 1000000000 in the Rate box.

## Step 4: Type 10000000 in the Quantity box ✓ passed (0.45s)
md5: 6f7b74e1ea8ffa5a83332de82a4d3f21
Type 10000000 in the Quantity box.

## Step 5: Wait two seconds ✓ passed (2.11s)
md5: 970fc9fdc8d1565689488a232937127b
Wait two seconds.

## Check the expected outcome ✓ passed (30.1s)
md5: 25b12a8c5ad4cce14336721f3ebce34e
Verify that the Line Items form is still on screen with the Name, Quantity and Rate boxes visible.
Verify that no 'Application error' or 'client-side exception' message is shown.
Verify that the item's Total shows 10000000000000000.00 USD.
