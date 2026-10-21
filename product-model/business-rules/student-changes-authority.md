---
appliesTo:
- type: entity
  id: student
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
permits:
- actors:
  - student
---

# Only the student changes their own name and connections

The name on recordings, the library connection and AI app connections are the student’s.
