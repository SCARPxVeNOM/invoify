---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [line-items, totals, input-abuse]
---

# A very large line total does not crash the invoice form

<!-- compiled by gremlin from .gremlin/flows/adversarial/a-very-large-line-total-does-not-crash-the-invoice-form.md (a0979e10c8328b2b). Edit the flow, not this file. -->

## Step 1: Click the 'Line Items' step in the progress bar at the top of t…
Start on http://localhost:5299/en. Click the 'Line Items' step in the progress bar at the top of the form.

## Step 2: In the first item, type 'Bulk widgets' into Name
In the first item, type 'Bulk widgets' into Name.

## Step 3: Type 1000000 into Quantity
Type 1000000 into Quantity.

## Step 4: Type 10000000000 into Rate
Type 10000000000 into Rate.

## Step 5: Click the 'Summary' step in the progress bar
Click the 'Summary' step in the progress bar.

## Check the expected outcome
Verify that the invoice form is still on screen with the Summary step open.
Verify that A Total Amount value is shown on the Summary step.
Verify that no 'Application error' or 'client-side exception' message is shown.
