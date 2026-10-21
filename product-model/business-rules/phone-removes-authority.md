---
appliesTo:
- type: entity
  id: phone
  effect: removes
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

# Only the student removes a paired phone

A phone is removed from the library’s computer, or removes itself from its own settings.
