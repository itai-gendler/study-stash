---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Rename on a lecture and types a new title.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product changes the lecture title and preserves it for future writing.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Title
  contexts: *id001
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
  target: engine/src/StudyStash.Core/Store.cs
---

# Rename lecture

## Trigger

A lecture’s title is not the one the student wants.

## Outcome

The lecture keeps the student’s title, also when its notes are written again.

## Edge cases

- Empty titles and titles longer than 200 characters are refused.
- A lecture still queued or writing must finish before it is renamed.
