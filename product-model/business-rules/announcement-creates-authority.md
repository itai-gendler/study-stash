---
appliesTo:
- type: entity
  id: announcement
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
permits:
- actors:
  - student
- unattended: true
---

# Announcements arrive only by syncing Canvas

Announcements are mirrored from Canvas when the student chooses Sync now or the regular sync runs; nothing is posted from Study Stash.
