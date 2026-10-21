---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Keep old under the proposed notes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product dismisses the notes draft.
  kind: product
  entities:
  - entity: notes-draft
    effect: changes
    facts: []
    from: Proposed
    to: Dismissed
  contexts: *id001
  actor: student
- text: The Product clears the dismissed notes draft.
  kind: product
  entities:
  - entity: notes-draft
    effect: removes
    from: Dismissed
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

# Keep old notes

## Trigger

A rewrite of a lecture’s notes is ready, but the student prefers the current notes.

## Outcome

The lecture keeps its current notes and the proposal is cleared.
