---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student changes a class’s description, other names or group.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::classes
    library-web-library:
      place: library-web::library::classes
- text: The Product keeps the class’s new description, other names and group.
  kind: product
  entities:
  - entity: class
    effect: changes
    facts:
    - Description
    - Other names
    - Group
  contexts:
    desktop:
      place: desktop::classes
    library-web-library:
      place: library-web::library::classes
  actor: student
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
---

# Edit class

## Trigger

What a class covers, or the names it goes by, has changed.

## Outcome

The class keeps its lectures and material with the new details, which sorting uses for later lectures.

## Edge cases

- Class names are unique without regard to case, up to 60 characters, and cannot be Unsorted.
