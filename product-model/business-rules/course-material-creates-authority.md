---
appliesTo:
- type: entity
  id: course-material
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
permits:
- actors:
  - student
- unattended: true
---

# Course material arrives only by syncing Canvas

Modules’ files and pages are mirrored from Canvas when the student chooses Sync now or the regular sync runs.
