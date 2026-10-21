---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student opens a lecture whose new notes are ready.
  kind: actor
  actor: student
  entities:
  - entity: notes-draft
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
- text: The Product presents the notes draft beside the current lecture notes.
  kind: product
  entities:
  - entity: notes-draft
    effect: reads
    facts:
    - Text
    - Writer
    - Created
    - Source attachments
  - entity: lecture
    effect: reads
    facts:
    - Study notes
    - Writer
  contexts:
    desktop:
      place: desktop::lecture
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Compare notes draft

## Trigger

A rewrite has finished and its notes wait for the student’s choice.

## Outcome

The proposed notes can be read with the engine that wrote them, while the current notes stay as they are until the student chooses Use new or Keep old.
