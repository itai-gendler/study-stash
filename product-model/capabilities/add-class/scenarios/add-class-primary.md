---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student adds a class or folder with its name, and optionally what it covers and its group.
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
- text: The Product adds the class.
  kind: product
  entities:
  - entity: class
    effect: creates
    facts:
    - Name
    - Description
    - Other names
    - Group
    - Canvas course
    - Modules
    - Lecture count
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

# Add class

## Trigger

The student wants a new class or folder for lectures to be filed under.

## Outcome

The class is in the class list, and new lectures can be filed under it.

## Edge cases

- Class names are unique without regard to case, up to 60 characters, and cannot be Unsorted.
