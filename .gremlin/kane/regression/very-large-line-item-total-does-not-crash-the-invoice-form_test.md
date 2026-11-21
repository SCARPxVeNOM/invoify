---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [line-items, input-abuse]
---

# Very large line item total does not crash the invoice form

<!-- compiled by gremlin from .gremlin/flows/regression/very-large-line-item-total-does-not-crash-the-invoice-form.md (61b68822397b97b2). Edit the flow, not this file. -->

## Step 1: Click the 'Line Items' step in the progress bar
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Server rack lease' in the item Name box
Type 'Server rack lease' in the item Name box.

## Step 3: Type 1000000000 in the Rate box
Type 1000000000 in the Rate box.

## Step 4: Type 10000000 in the Quantity box
Type 10000000 in the Quantity box.

## Step 5: Wait two seconds
Wait two seconds.

## Check the expected outcome
Verify that the Line Items form is still on screen with the Name, Quantity and Rate boxes visible.
Verify that no 'Application error' or 'client-side exception' message is shown.
Verify that the item's Total shows 10000000000000000.00 USD.
