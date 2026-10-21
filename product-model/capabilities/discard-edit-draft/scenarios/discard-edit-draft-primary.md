---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Cancel while editing the notes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product removes the edit draft and returns to the current notes.
  kind: product
  entities:
  - entity: edit-draft
    effect: removes
  - entity: lecture
    effect: reads
    facts:
    - Study notes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
---

# Cancel notes edit

## Trigger

The student does not want to keep what they typed in the notes editor.

## Outcome

The unsaved typing is discarded and the lecture’s notes are as they were.
