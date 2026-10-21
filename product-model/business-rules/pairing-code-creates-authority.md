---
appliesTo:
- type: entity
  id: pairing-code
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
permits:
- actors:
  - student
---

# Only the student shows a pairing code

A code appears when the student chooses Add a phone.
