---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [summary, charges, input-abuse]
---

# Negative discount cannot push the total above the subtotal

<!-- compiled by gremlin from .gremlin/flows/adversarial/negative-discount-cannot-push-the-total-above-the-subtotal.md (c28e0897828d2551). Edit the flow, not this file. -->

## Step 1: Click the 'Line Items' step in the progress bar
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Consulting' in the item Name box
Type 'Consulting' in the item Name box.

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

## Check the expected outcome
Verify that subtotal shows 200.00 USD.
Verify that total Amount is not higher than 200.00 USD.
