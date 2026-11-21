---
test: ../a-valid-client-email-longer-than-30-characters-is-accepted_test.md
status: failed
started: 2026-11-21T11:11:38.674Z
duration_s: 44
session_id: 35a4bfc5-05eb-40a6-885a-514b242d1eaa
---

# A valid client email longer than 30 characters is accepted — Result

## Step 1: In the Bill To section, type 'accounts-receivable@example.test'… ✓ passed (5.24s)
md5: aa20c3479cd56ee645340064f27c6aa8
Start on http://localhost:5299/en. In the Bill To section, type 'accounts-receivable@example.test' into Email.

## Step 2: Click into the Bill To Phone field ✓ passed (0.93s)
md5: 07bd957ab61416340f65b85dbdf3bbb1
Click into the Bill To Phone field.

## Check the expected outcome ✗ failed (33s)
md5: 748b3fddeec80cdd5214bcad9a62d5a9
Reason: Final verification failed: "no error message is shown under the Bill To Email field" — bug verdict: Bill To Email rejects a valid 32-character address [application_issue/validation_defect, confidence 0.95]
Verify that the Bill To Email field still reads accounts-receivable@example.test.
Verify that no error message is shown under the Bill To Email field.
