---
appliesTo:
- type: entity
  id: edit-draft
  effect: creates
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

# Edit drafts come only from the student’s typing

An edit draft is what the student typed in the notes editor and has not saved.
