---
appliesTo:
- type: entity
  id: course-material
  effect: changes
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

# Course material changes only by syncing Canvas

A mirrored page or file follows its Canvas original.
