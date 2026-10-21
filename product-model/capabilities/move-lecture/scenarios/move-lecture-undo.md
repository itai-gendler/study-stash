---
kind: alternate
routes:
  desktop: Desktop app
steps:
- text: The student chooses Undo while the move notice is available.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product restores the lecture’s previous filing choice.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Class
    - Filing choice
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
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# Undo the last move

## Trigger

The student chooses Undo while the move notice is available.

## Outcome

The lecture returns to its preceding class.
