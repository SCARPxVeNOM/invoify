---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [summary, charges, discount]
---

# A negative discount never pushes the Total Amount above the Subtotal

<!-- compiled by gremlin from .gremlin/flows/regression/a-negative-discount-never-pushes-the-total-amount-above-the.md (bf9391dc8c87771f). Edit the flow, not this file. -->

## Step 1: Click the 'Line Items' step in the progress bar
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Test service' in the item Name box
Type 'Test service' in the item Name box.

## Step 3: Type 2 in the Quantity box
Type 2 in the Quantity box.

## Step 4: Type 100 in the Rate box
Type 100 in the Rate box.

## Step 5: Click the 'Summary' step in the progress bar
Click the 'Summary' step in the progress bar.

## Step 6: Click '+ Discount'
Click '+ Discount'.

## Step 7: Clear the Discount box and type -50
Clear the Discount box and type -50.

## Step 8: Scroll back up the page, above the 'Frequently asked questions'…
Scroll back up the page, above the 'Frequently asked questions' section, until the Summary form's 'Subtotal' and 'Total Amount' rows are both on screen, and stop there.

## Check the expected outcome
Verify that in the Summary form, the Subtotal row shows 200.00 USD.
Verify that in the Summary form, the Total Amount row shows 200.00 USD or less, and does not show 250.00 USD.
