---
appliesTo:
- type: entity
  id: phone
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

# Only the student pairs a phone

A phone is paired with the code the student was shown.
