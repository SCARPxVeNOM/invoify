---
mode: testing
url: http://localhost:5299/
max_steps: 40
tags: [form, timing]
---

# Form on /: double-clicking "Generate PDF" creates only one result

<!-- compiled by gremlin from .gremlin/flows/adversarial/form-on-double-clicking-generate-pdf-creates-only-one-result.md (4ddb9aa1c87b3cb6). Edit the flow, not this file. -->

## Step 1: Go to /
Go to /.

## Step 2: Fill the form with ordinary valid values
Fill the form with ordinary valid values.

## Step 3: Double-click Generate PDF as fast as possible
Double-click "Generate PDF" as fast as possible.

## Step 4: Open the page that lists what was created, if there is one
Open the page that lists what was created, if there is one.

## Check the expected outcome
Verify that exactly one new entry was created, not two.
Verify that no error message is visible.
