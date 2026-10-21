---
kind: alternate
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student saves a new class name.
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
- text: The Product changes the class name and other names.
  kind: product
  entities:
  - entity: class
    effect: changes
    facts:
    - Name
    - Other names
  contexts: *id001
  actor: student
- text: The Product updates the class carried by the lecture and its attachments.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Class
  - entity: attachment
    effect: changes
    facts: []
  - entity: class
    effect: reads
    facts: []
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

# Rename without leaving lectures behind

## Trigger

The student saves a new class name.

## Outcome

The class’s lectures, folder and linked material follow; its former name remains an alias.

## Edge cases

- Renaming waits while Canvas is syncing.
- A batch rename can report partial completion when a later class cannot move.
