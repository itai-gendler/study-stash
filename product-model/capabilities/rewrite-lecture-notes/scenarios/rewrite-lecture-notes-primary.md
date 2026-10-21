---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student asks another engine to write the lecture’s notes and picks it.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
- text: The Product starts a rewrite for the lecture.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Transcript
    - Your notes
  - entity: rewrite
    effect: creates
    facts:
    - Engine
    - Progress
    - Started
    - Problem
    to: Working
  contexts:
    desktop:
      place: desktop::lecture
  actor: student
- text: The Product completes the rewrite and offers a notes draft.
  kind: product
  entities:
  - entity: rewrite
    effect: changes
    facts:
    - Progress
    from: Working
    to: Ready
  - entity: notes-draft
    effect: creates
    facts:
    - Text
    - Writer
    - Created
    - Source attachments
    to: Proposed
  contexts:
    desktop:
      place: desktop::lecture
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Rewrite lecture notes

## Trigger

The student wants to see what another AI makes of a lecture’s notes.

## Outcome

New notes are written while the current ones stay on screen, and are offered for the student to choose.

## Edge cases

- Another active rewrite, insufficient source material, ongoing initial writing or an engine not set up prevents a new attempt.
- The original student text and the attachment text available at the start are supplied to the rewrite.
