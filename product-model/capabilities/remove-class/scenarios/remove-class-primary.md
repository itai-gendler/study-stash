---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student removes a class, leaving what is filed under it in place.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::classes
    library-web-library:
      place: library-web::library::classes
- text: The Product removes the class definition from the configured list.
  kind: product
  entities:
  - entity: class
    effect: removes
  contexts: *id001
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

# Remove class

## Trigger

A class is no longer one the student wants to file into.

## Outcome

The class leaves the class list; lectures already filed under it stay readable under its name.
