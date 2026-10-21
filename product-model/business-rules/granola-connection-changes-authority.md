---
appliesTo:
- type: entity
  id: granola-connection
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
permits:
- actors:
  - student
---

# Only the student connects, disconnects or sets notifications for Granola

Signing in happens on Granola’s own page; Study Stash never sees the password.
