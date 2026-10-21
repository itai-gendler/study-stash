---
appliesTo:
- type: entity
  id: announcement
  effect: changes
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

# Announcements change only by syncing Canvas or by the student reading them

A sync refreshes what Canvas says; reading an announcement in Study Stash clears its new mark.
