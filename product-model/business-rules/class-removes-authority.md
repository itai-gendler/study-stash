---
appliesTo:
- type: entity
  id: class
  effect: removes
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

# Only the student removes a class

Removing a class leaves its filed lectures readable under its name.
