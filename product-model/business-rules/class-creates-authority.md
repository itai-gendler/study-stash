---
appliesTo:
- type: entity
  id: class
  effect: creates
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
---

# Only the student adds a class

Classes are the student’s own list, including one created while matching a Canvas course to it.
