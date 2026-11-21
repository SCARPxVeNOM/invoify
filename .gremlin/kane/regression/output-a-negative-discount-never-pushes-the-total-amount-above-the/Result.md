---
test: ../a-negative-discount-never-pushes-the-total-amount-above-the_test.md
status: passed
started: 2026-11-21T11:36:28.793Z
duration_s: 52
session_id: b262d4a5-3517-45b7-9c85-9310fd2181bb
---

# A negative discount never pushes the Total Amount above the Subtotal — Result

## Step 1: Click the 'Line Items' step in the progress bar ✓ passed (7.03s)
md5: 1427442882b95a0877465b5378545093
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Test service' in the item Name box ✓ passed (0.28s)
md5: 337401fd6b609a46befd7c3bfe7e0299
Type 'Test service' in the item Name box.

## Step 3: Type 2 in the Quantity box ✓ passed (0.42s)
md5: 43167f32fdf3812a9001f56e5d59643b
Type 2 in the Quantity box.

## Step 4: Type 100 in the Rate box ✓ passed (0.43s)
md5: a8f0f1e6830db239f709aa619c025491
Type 100 in the Rate box.

## Step 5: Click the 'Summary' step in the progress bar ✓ passed (0.88s)
md5: d3454861541305e464b5eaecc483fdf1
Click the 'Summary' step in the progress bar.

## Step 6: Click '+ Discount' ✓ passed (0.76s)
md5: eb1c5db08cba8c6f2f9ad72d51c28e1e
Click '+ Discount'.

## Step 7: Clear the Discount box and type -50 ✓ passed (0.25s)
md5: 54d81af5f8188b93819faba0f3a0d7d5
Clear the Discount box and type -50.

## Step 8: Scroll back up the page, above the 'Frequently asked questions'… ✓ passed (3.91s)
md5: b77b3a7c6ddcf9cca433cd7181307b69
Scroll back up the page, above the 'Frequently asked questions' section, until the Summary form's 'Subtotal' and 'Total Amount' rows are both on screen, and stop there.

## Check the expected outcome ✓ passed (33s)
md5: 7e345327f0ae3372e10d94f3387345fb
Verify that in the Summary form, the Subtotal row shows 200.00 USD.
Verify that in the Summary form, the Total Amount row shows 200.00 USD or less, and does not show 250.00 USD.
