---
kind: primary
routes:
  desktop: desktop
  library-web-library: library-web-library
steps:
- text: The student saves choices in Notes and sorting.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::notes-settings
    library-web-library:
      place: library-web::library::notes-settings
- text: The Product saves the library settings for notes and sorting.
  kind: product
  actor: student
  entities:
  - entity: library-settings
    effect: changes
    facts:
    - Notes enabled
    - AI enabled
    - Filing confidence
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
---

# Change Notes settings

## Trigger

The student saves choices in Notes and sorting.

## Outcome

Subsequent processing uses the selected note-writing and sorting choices.
