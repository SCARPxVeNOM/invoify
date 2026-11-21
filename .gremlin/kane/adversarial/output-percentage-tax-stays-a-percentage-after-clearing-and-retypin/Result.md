---
test: ../percentage-tax-stays-a-percentage-after-clearing-and-retypin_test.md
status: passed
started: 2026-11-21T10:56:39.090Z
duration_s: 162
session_id: a0cec241-cae1-4c7c-a1c4-04f18bbc3be0
---

# Percentage tax stays a percentage after clearing and retyping it — Result

## Step 1: Click the 'Line Items' step in the progress bar ✓ passed (17.6s)
md5: 1427442882b95a0877465b5378545093
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Design work' in the item Name box ✓ passed (11s)
md5: 2db292b3116d118f675c133d5f277ad1
Type 'Design work' in the item Name box.

## Step 3: Type 2 in the Quantity box ✓ passed (13s)
md5: 43167f32fdf3812a9001f56e5d59643b
Type 2 in the Quantity box.

## Step 4: Type 100 in the Rate box ✓ passed (11.5s)
md5: a8f0f1e6830db239f709aa619c025491
Type 100 in the Rate box.

## Step 5: Click the 'Summary' step in the progress bar ✓ passed (13.3s)
md5: d3454861541305e464b5eaecc483fdf1
Click the 'Summary' step in the progress bar.

## Step 6: Click '+ Tax' ✓ passed (12.1s)
md5: 66041d38c15010e8688ca3d6eacc8426
Click '+ Tax'.

## Step 7: Click the circular-arrows button next to the Tax box (Switch be… ✓ passed (12.5s)
md5: a6f96878eaa191a1794638464c4fa397
Click the circular-arrows button next to the Tax box (Switch between percentage and fixed amount) so a % sign appears beside it.

## Step 8: Clear the Tax box completely so it is empty ✓ passed (15.5s)
md5: e1770f3ac4c0468004d2c421f71b55e6
Clear the Tax box completely so it is empty.

## Step 9: Type 10 in the Tax box ✓ passed (13.1s)
md5: a3506fd37fe09eb57b090812b1825013
Type 10 in the Tax box.

## Check the expected outcome ✓ passed (38.1s)
md5: fbc06dbfea09d4502974ce2a1e5bae63
Verify that A % sign, not USD, is shown next to the Tax box.
Verify that subtotal shows 200.00 USD.
Verify that total Amount shows 220.00 USD.
