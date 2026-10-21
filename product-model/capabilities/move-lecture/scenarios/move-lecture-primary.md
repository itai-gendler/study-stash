---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student chooses Move to folder on a lecture and picks a class or Unsorted.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  - entity: class
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
- text: The Product changes the lecture class and records the human filing choice.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Class
    - Filing choice
  - entity: class
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
  actor: student
- text: The Product moves the linked attachment files with their lecture.
  kind: product
  entities:
  - entity: attachment
    effect: changes
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibraryModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# Move lecture

## Trigger

A lecture is filed under the wrong class, or sits in Unsorted.

## Outcome

The lecture and its attachments are in the chosen class, later processing keeps that choice, and the desktop offers Undo.

## Edge cases

- An unknown destination is refused.
- A move made while notes are being written is retained when filing finishes.
