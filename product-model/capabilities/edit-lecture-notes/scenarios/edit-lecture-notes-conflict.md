---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The student saves an edit based on notes that have since changed.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product keeps the edit draft and reads the changed lecture notes.
  kind: product
  entities:
  - entity: edit-draft
    effect: changes
    facts:
    - Original notes
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
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Edits.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
---

# Choose after notes changed elsewhere

## Trigger

The student saves an edit based on notes that have since changed.

## Outcome

The edit is retained, the current notes are refreshed, and a second Save is an explicit choice to replace that refreshed version.
