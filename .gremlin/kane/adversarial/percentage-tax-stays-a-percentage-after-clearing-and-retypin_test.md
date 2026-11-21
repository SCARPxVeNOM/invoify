---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [summary, charges, state]
---

# Percentage tax stays a percentage after clearing and retyping it

<!-- compiled by gremlin from .gremlin/flows/adversarial/percentage-tax-stays-a-percentage-after-clearing-and-retypin.md (be5a8139c80b7ccd). Edit the flow, not this file. -->

## Step 1: Click the 'Line Items' step in the progress bar
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar.

## Step 2: Type 'Design work' in the item Name box
Type 'Design work' in the item Name box.

## Step 3: Type 2 in the Quantity box
Type 2 in the Quantity box.

## Step 4: Type 100 in the Rate box
Type 100 in the Rate box.

## Step 5: Click the 'Summary' step in the progress bar
Click the 'Summary' step in the progress bar.

## Step 6: Click '+ Tax'
Click '+ Tax'.

## Step 7: Click the circular-arrows button next to the Tax box (Switch be…
Click the circular-arrows button next to the Tax box (Switch between percentage and fixed amount) so a % sign appears beside it.

## Step 8: Clear the Tax box completely so it is empty
Clear the Tax box completely so it is empty.

## Step 9: Type 10 in the Tax box
Type 10 in the Tax box.

## Check the expected outcome
Verify that A % sign, not USD, is shown next to the Tax box.
Verify that subtotal shows 200.00 USD.
Verify that total Amount shows 220.00 USD.
