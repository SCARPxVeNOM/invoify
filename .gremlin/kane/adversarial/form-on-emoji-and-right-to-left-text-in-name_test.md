---
mode: testing
url: http://localhost:5299/
max_steps: 40
tags: [form, input, i18n]
---

# Form on /: emoji and right-to-left text in "Name:"

<!-- compiled by gremlin from .gremlin/flows/adversarial/form-on-emoji-and-right-to-left-text-in-name.md (de07b3d902293ddf). Edit the flow, not this file. -->

## Step 1: Go to /
Go to /.

## Step 2: Type Zoë 🦄 李 مرحبا into the Name: field, fill every other requ…
Type "Zoë 🦄 李 مرحبا" into the "Name:" field, fill every other required field with ordinary valid values, and press "Generate PDF".

## Check the expected outcome
Verify that the app accepts the text or explains politely which characters are allowed.
Verify that no error page, stack trace, blank screen or "something went wrong" message appears.
