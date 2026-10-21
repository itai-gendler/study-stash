---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student confirms deletion in the desktop library.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product puts the lecture in deleted state.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Filed copy
    from: Filed
    to: Deleted
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

# Delete with recovery time

## Trigger

The student confirms deletion in the desktop library.

## Outcome

The lecture leaves the active library and the desktop offers Undo while it remains recoverable.

## Edge cases

- The desktop keeps the latest deletion notice for five minutes; the library retains its trash for ten minutes.
