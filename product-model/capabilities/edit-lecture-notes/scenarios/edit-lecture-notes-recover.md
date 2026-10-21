---
kind: alternate
routes:
  desktop: Desktop app
steps:
- text: The student returns to a lecture with locally saved unsaved typing.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product restores the edit draft into the lecture editor.
  kind: product
  entities:
  - entity: edit-draft
    effect: reads
    facts:
    - Text
    - Original notes
    - Kept at
  - entity: lecture
    effect: reads
    facts: []
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

# Recover unsaved typing

## Trigger

The student returns to a lecture with locally saved unsaved typing.

## Outcome

The editor restores the text and its original base, including after an app restart.

## Edge cases

- Drafts not reopened within 30 days are no longer restored.
