---
mode: testing
url: http://localhost:5299/
max_steps: 40
tags: [form, input, money]
---

# Form on /: a negative quantity

<!-- compiled by gremlin from .gremlin/flows/adversarial/form-on-a-negative-quantity.md (1819e9db73563cce). Edit the flow, not this file. -->

## Step 1: Go to /
Go to /.

## Step 2: Change the Country: field to -3 and apply the change
Change the "Country:" field to -3 and apply the change.

## Check the expected outcome
Verify that A negative quantity is rejected or corrected to a valid number.
Verify that no price or total is shown as a negative amount.
