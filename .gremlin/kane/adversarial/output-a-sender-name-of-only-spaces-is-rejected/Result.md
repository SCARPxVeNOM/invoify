---
test: ../a-sender-name-of-only-spaces-is-rejected_test.md
status: failed
started: 2026-11-21T11:17:27.669Z
duration_s: 34
session_id: 24409391-e1b0-4b2b-b5fe-eb4afaf71c39
---

# A sender name of only spaces is rejected — Result

## Step 1: In the Bill From section, click into the Name field and press t… ✓ passed (5.6s)
md5: 19e737983f6b8058e3b14a5af18b4d0c
Start on http://localhost:5299/en. In the Bill From section, click into the Name field and press the space bar three times, so the field holds only three spaces and nothing else.

## Step 2: Press Tab to leave the Name field and move to the Bill From Add… ✓ passed (0.66s)
md5: 5e524d308ba532a80ea95e0a75af48f0
Press Tab to leave the Name field and move to the Bill From Address field.

## Step 3: Type 1 Test Street into the Bill From Address field ✓ passed (0.23s)
md5: 2b00d9b022940e2cdf7d30ea5ec7aae8
Type 1 Test Street into the Bill From Address field.

## Check the expected outcome ✗ failed (23.7s)
md5: ad0c87f8d2e6a55fa5cc8fe622ed1f30
Reason: Final verification failed: "an error message is shown directly under the Bill From Name field saying the name is required or too short (for example "Must be at least 2 characters")" — bug verdict: Validation assertion run before opening invoice form [automation_bug/state_transition_bug, confidence 0.98]
Verify that an error message is shown directly under the Bill From Name field saying the name is required or too short (for example "Must be at least 2 characters"), even though the Name field looks blank.
