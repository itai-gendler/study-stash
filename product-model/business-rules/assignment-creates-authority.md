---
appliesTo:
- type: entity
  id: assignment
  effect: creates
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

# Assignments arrive only by syncing Canvas

Assignments, with their rubrics, submissions and feedback, are mirrored from Canvas when the student chooses Sync now or the regular sync runs.
