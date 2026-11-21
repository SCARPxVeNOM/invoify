---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [from-and-to, validation, input-abuse]
---

# A valid client email longer than 30 characters is accepted

<!-- compiled by gremlin from .gremlin/flows/adversarial/a-valid-client-email-longer-than-30-characters-is-accepted.md (19c87b014f0e1ba7). Edit the flow, not this file. -->

## Step 1: In the Bill To section, type 'accounts-receivable@example.test'…
Start on http://localhost:5299/en. In the Bill To section, type 'accounts-receivable@example.test' into Email.

## Step 2: Click into the Bill To Phone field
Click into the Bill To Phone field.

## Check the expected outcome
Verify that the Bill To Email field still reads accounts-receivable@example.test.
Verify that no error message is shown under the Bill To Email field.
