---
availability:
- place: desktop
- place: library-web::library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClassRename.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
domain: classes
---

# Remove class

Remove a class from the configured class list; already-filed lectures remain accessible under their class name.
