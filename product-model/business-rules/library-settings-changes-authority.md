---
appliesTo:
- type: entity
  id: library-settings
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
permits:
- actors:
  - student
---

# Only the student changes library settings

The library’s name, password, notes and sorting choices, uses and update and login choices are the student’s.
