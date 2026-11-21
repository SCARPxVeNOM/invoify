---
mode: testing
url: http://localhost:5299/en
max_steps: 40
tags: [from-and-to, validation, input-abuse]
---

# A sender name of only spaces is rejected

<!-- compiled by gremlin from .gremlin/flows/adversarial/a-sender-name-of-only-spaces-is-rejected.md (badf471460d3c4cf). Edit the flow, not this file. -->

## Step 1: In the Bill From section, click into the Name field and press t…
Start on http://localhost:5299/en. In the Bill From section, click into the Name field and press the space bar three times, so the field holds only three spaces and nothing else.

## Step 2: Press Tab to leave the Name field and move to the Bill From Add…
Press Tab to leave the Name field and move to the Bill From Address field.

## Step 3: Type 1 Test Street into the Bill From Address field
Type 1 Test Street into the Bill From Address field.

## Check the expected outcome
Verify that an error message is shown directly under the Bill From Name field saying the name is required or too short (for example "Must be at least 2 characters"), even though the Name field looks blank.
