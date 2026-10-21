---
appliesTo:
- type: entity
  id: class
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClassRename.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
permits:
- actors:
  - student
- unattended: true
---

# Classes change only through the student or a Canvas sync

The student names and describes a class; a sync keeps its Canvas modules up to date.
