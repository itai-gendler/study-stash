---
appliesTo:
- type: entity
  id: pairing-code
  effect: removes
permits:
- actors:
  - student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
---

# Only the student pairing a phone uses up its code

A pairing code works once.
