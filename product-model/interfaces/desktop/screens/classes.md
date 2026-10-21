---
entities:
- entity: class
  shows:
  - Name
  - Description
  - Other names
  - Group
  - Canvas course
  - Modules
  - Lecture count
  collects:
  - Name
  - Description
  - Other names
  - Group
- entity: lecture
  shows:
  - Class
- entity: attachment
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClassRename.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
---

# Classes

The class list: each class or folder with what it covers, the other names it goes by, its group and how many lectures it holds.
