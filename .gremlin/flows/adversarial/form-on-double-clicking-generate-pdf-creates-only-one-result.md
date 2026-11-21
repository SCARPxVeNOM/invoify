---
title: 'Form on /: double-clicking "Generate PDF" creates only one result'
type: adversarial
platforms:
  - web
start: /
source: breaker
status: active
tags:
  - form
  - timing
attack: timing.double-submit
created: 2026-11-21T11:18:07.450Z
---

1. Go to /.
2. Fill the form with ordinary valid values.
3. Double-click "Generate PDF" as fast as possible.
4. Open the page that lists what was created, if there is one.

## Expect

- Exactly one new entry was created, not two
- No error message is visible
