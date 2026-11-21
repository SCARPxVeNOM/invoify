---
test: ../a-very-large-line-total-does-not-crash-the-invoice-form_test.md
status: failed
started: 2026-11-21T11:09:31.167Z
duration_s: 32
session_id: 9a60f491-25ad-4e47-9135-ddc1c01ffafb
---

# A very large line total does not crash the invoice form — Result

## Step 1: Click the 'Line Items' step in the progress bar at the top of t… ✓ passed (6.11s)
md5: 7507ffba3d36f67da6b3edf28fb49dab
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar at the top of the form.

## Step 2: In the first item, type 'Bulk widgets' into Name ✓ passed (0.25s)
md5: a8991c7fd3c30859554bdd894ce3faa9
In the first item, type 'Bulk widgets' into Name.

## Step 3: Type 1000000 into Quantity ✓ passed (0.42s)
md5: 71734d75278b6617603c74b261224f68
Type 1000000 into Quantity.

## Step 4: Type 10000000000 into Rate ✓ passed (6.52s)
md5: 6c6f793d429a2417d18e5c66a0ab3d3c
Type 10000000000 into Rate.

## Step 5: Click the 'Summary' step in the progress bar ✗ failed (14.7s)
md5: d3454861541305e464b5eaecc483fdf1
Reason: The current page shows a client-side application error and contains no Summary progress-bar step. — bug verdict: Price formatting crashes on unsafe numeric input [application_issue/script_error, confidence 0.99]
Click the 'Summary' step in the progress bar.

## Check the expected outcome ⏭ skipped
