---
title: 'Form on /: emoji and right-to-left text in "Name:"'
type: adversarial
platforms:
  - web
start: /
source: breaker
status: active
tags:
  - form
  - input
  - i18n
attack: input.emoji
created: 2026-11-21T11:21:24.795Z
---

1. Go to /.
2. Type "Zoë 🦄 李 مرحبا" into the "Name:" field, fill every other required field with ordinary valid values, and press "Generate PDF".

## Expect

- The app accepts the text or explains politely which characters are allowed
- No error page, stack trace, blank screen or "something went wrong" message appears
