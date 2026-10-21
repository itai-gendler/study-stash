---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Edit on a lecture’s notes, changes them and chooses Save.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product keeps an edit draft with the text and original notes.
  kind: product
  entities:
  - entity: edit-draft
    effect: creates
    facts:
    - Text
    - Original notes
    - Kept at
  contexts: *id001
  actor: student
- text: The Product saves the lecture notes and clears the edit draft.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Study notes
  - entity: edit-draft
    effect: removes
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

# Edit lecture notes

## Trigger

The student wants to fix or add to a lecture’s notes.

## Outcome

The lecture’s notes are the student’s version, and the lines they changed or added count as their own words.

## Edge cases

- Blank notes are refused.
- The notes cannot be saved while initial processing is queued or working.
- A failed save keeps the typing available in the editor.
- Changed or added prose lines become the student’s own marked words; diagram content survives the editor’s placeholders.
