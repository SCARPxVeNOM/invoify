---
test: ../a-valid-client-email-longer-than-30-characters-is-accepted_test.md
status: passed
started: 2026-11-21T18:51:34.355Z
duration_s: 41
session_id: 06766eee-0a18-481f-954b-358ef704c8fc
---

# A valid client email longer than 30 characters is accepted — Result

## Step 1: In the Bill To section, type 'accounts-receivable@example.test'… ✓ passed (6.49s)
md5: aa20c3479cd56ee645340064f27c6aa8
Start on http://localhost:5299/en. In the Bill To section, type 'accounts-receivable@example.test' into Email.

## Step 2: Click into the Bill To Phone field ✓ passed (0.89s)
md5: 07bd957ab61416340f65b85dbdf3bbb1
Click into the Bill To Phone field.

## Check the expected outcome ✓ passed (28.1s)
md5: 748b3fddeec80cdd5214bcad9a62d5a9
Verify that the Bill To Email field still reads accounts-receivable@example.test.
Verify that no error message is shown under the Bill To Email field.
