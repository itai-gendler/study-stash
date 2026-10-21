---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Cancel while new notes are being written.
  kind: actor
  actor: student
  entities:
  - entity: rewrite
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product marks the rewrite cancelled.
  kind: product
  entities:
  - entity: rewrite
    effect: changes
    facts: []
    from: Working
    to: Cancelled
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Cancel rewrite

## Trigger

The student no longer wants the rewrite in progress.

## Outcome

The rewrite stops and the lecture keeps its current notes.
