---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student confirms deletion on a library web note.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    library-web-library:
      place: library-web::library::lecture
- text: The Product takes the lecture and its note file out of the library into the trash.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    from: Filed
    to: Deleted
    facts:
    - Filed copy
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibraryModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# Delete from the library web page

## Trigger

The student confirms deletion on a library web note.

## Outcome

The lecture leaves every list, search and answer at once.

## Edge cases

- The web page offers no Undo of its own; the deletion becomes final once the trash is emptied.
