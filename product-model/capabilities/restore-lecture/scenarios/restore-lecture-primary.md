---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Undo on the notice after deleting a lecture.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::home
- text: The Product restores the deleted lecture.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Filed copy
    from: Deleted
    to: Filed
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibraryModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
---

# Undo lecture deletion

## Trigger

The student deleted a lecture by mistake.

## Outcome

The lecture is back where it was, with its notes, transcript and search passages.

## Edge cases

- An item no longer in the trash cannot be restored.
- A lecture deleted while writing resumes queued processing when restored.

- Restarting the library clears its previous trash, so an earlier deletion can no longer be restored.
