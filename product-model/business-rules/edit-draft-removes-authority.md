---
appliesTo:
- type: entity
  id: edit-draft
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
permits:
- actors:
  - student
---

# Only the student saves or discards an edit draft

Saving or cancelling the edit ends the draft.
