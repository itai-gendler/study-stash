---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Only my notes on the desktop.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product filters the displayed lecture notes to the student’s marked words.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Study notes
    - Your notes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/TypedNotes.cs
---

# Read only the student’s words

## Trigger

The student chooses Only my notes on the desktop.

## Outcome

The view shows the marked student lines while the full notes remain intact.
