---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Use new under the proposed notes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product accepts the notes draft and replaces the lecture write-up.
  kind: product
  entities:
  - entity: notes-draft
    effect: changes
    facts: []
    from: Proposed
    to: Accepted
  - entity: lecture
    effect: changes
    facts:
    - Study notes
    - Writer
  contexts: *id001
  actor: student
- text: The Product clears the accepted notes draft.
  kind: product
  entities:
  - entity: notes-draft
    effect: removes
    from: Accepted
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

# Use new notes

## Trigger

A rewrite of a lecture’s notes is ready and the student prefers it to the current notes.

## Outcome

The proposed notes become the lecture’s study notes, credited to the engine that wrote them, and the proposal is cleared.

## Edge cases

- There must be a nonempty ready proposal, and initial lecture processing must not be queued or working.
- Rich notes requested for the accepted text can arrive later.
