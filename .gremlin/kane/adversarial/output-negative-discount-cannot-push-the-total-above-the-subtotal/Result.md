---
test: ../negative-discount-cannot-push-the-total-above-the-subtotal_test.md
status: failed
started: 2026-11-21T11:02:35.728Z
duration_s: 47
session_id: 911f62ae-b492-45eb-974c-8025a58b6de7
---

# Negative discount cannot push the total above the subtotal — Result

## Step 1: Click the 'Line Items' step in the progress bar ✓ passed (5.79s)
md5: 1427442882b95a0877465b5378545093
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Consulting' in the item Name box ✓ passed (0.29s)
md5: 29e9395f5ee262924d92fefaa8ea16dc
Type 'Consulting' in the item Name box.

## Step 3: Type 2 in the Quantity box ✓ passed (0.45s)
md5: 43167f32fdf3812a9001f56e5d59643b
Type 2 in the Quantity box.

## Step 4: Type 100 in the Rate box ✓ passed (0.46s)
md5: a8f0f1e6830db239f709aa619c025491
Type 100 in the Rate box.

## Step 5: Click the 'Summary' step in the progress bar ✓ passed (0.86s)
md5: d3454861541305e464b5eaecc483fdf1
Click the 'Summary' step in the progress bar.

## Step 6: Click '+ Discount' ✓ passed (0.78s)
md5: eb1c5db08cba8c6f2f9ad72d51c28e1e
Click '+ Discount'.

## Step 7: Clear the Discount box and type -50 ✓ passed (0.23s)
md5: 54d81af5f8188b93819faba0f3a0d7d5
Clear the Discount box and type -50.

## Check the expected outcome ✗ failed (34.4s)
md5: 25c71ce2486d6113c3ac57b9cb9a9f58
Reason: Final verification failed: "total Amount is not higher than 200.00 USD" — bug verdict: Invoice summary was not reached before amount assertion [automation_bug/state_transition_bug, confidence 0.96]
Verify that subtotal shows 200.00 USD.
Verify that total Amount is not higher than 200.00 USD.
