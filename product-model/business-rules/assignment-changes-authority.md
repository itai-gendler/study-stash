---
appliesTo:
- type: entity
  id: assignment
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/Assignments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
permits:
- actors:
  - student
- unattended: true
---

# Assignments change only by syncing Canvas

Status, submission and feedback follow Canvas; nothing about an assignment is changed from Study Stash.
