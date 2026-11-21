---
title: "Form on /: a negative quantity"
type: adversarial
platforms:
  - web
start: /
source: breaker
status: active
tags:
  - form
  - input
  - money
attack: input.negative
created: 2026-11-21T11:24:18.719Z
---

1. Go to /.
2. Change the "Country:" field to -3 and apply the change.

## Expect

- A negative quantity is rejected or corrected to a valid number
- No price or total is shown as a negative amount
